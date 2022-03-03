# Secure Software Development at Mattermost

This document provides guidelines to secure software development at Mattermost. The document is at the moment a [1% draft](/company/about-mattermost/mindsets#drafts-at-1-50-99) and not conclusive.

## Document scope

This document covers the secure software development practices on all source repositories used to create software products offered by Mattermost.

The product security team is overall in charge of secure software development practices by providing help and guidance and performing various verification activities, including code reviews and testing. Development teams are encouraged to adopt the secure software development practices described here. Third-party plugin developers are also welcome to use this document for guidance.

## Recommended reading

* [OSSF Scorecard Action Check Documentation](https://github.com/ossf/scorecard/blob/main/docs/checks.md)
* [Overview of Software Supply Chain Attacks](https://www.crowdstrike.com/cybersecurity-101/cyberattacks/supply-chain-attacks/) by [Crowdstrike](https://www.crowdstrike.com/)

## Code reviews

### Manual code reviews

The product security team performs reviews on new features and plugins when necessary. Here's some of the things included in the checks:

* TODO.

### Automated code reviews

The key Mattermost repositories have (or should have) automated code security analysis tools set up. In practice, we use [CodeQL](https://codeql.github.com/) as a Github Action to automatically analyze all pull requests. Additionally, the use of the [OSSF Security Scorecards GitHub Action](https://github.com/ossf/scorecard) is strongly encouraged. This document addresses many of the best practices checked by the Scorecards action.

## Dependency pinning

Dependency pinning hardens the software development workflow against [software supply chain attacks](https://www.crowdstrike.com/cybersecurity-101/cyberattacks/supply-chain-attacks/). In this context, the specific threat being mitigated is upstream dependencies being taken over by attackers and replaced with malicious content. The risk commonly involves referring to dependencies without explicitly specifying a computed hash value for the dependency. In case of a dependency takeover, pulling the _latest_ version of it realizes the risk. The risk probability is considered low for supply chain attacks, but the effect can be pretty bad.

Practically, defining build-time dependencies with an explicit hash is the preferred solution. When specifying hashes to existing dependencies that did not use hashed references before, picking the hash of the currently used dependency is a good starting point as it is often not practical to do a full audit of all dependencies. Picking a hash and sticking to it doesn't ensure that said hash represents a safe version, it only ensures that a possibly malicious later version is not introduced in the build process afterwards.

Please note also that pinning dependencies to a specific version (for example, `@2.1.1`) does not guard against malicious updates to the dependency. It is necessary to pin a dependency to a specific checksum (which is a cryptograhic guarantee to the uniqueness of the actual content).

### Npm dependencies

With npm, replace `npm install` with `npm ci` everywhere in the build/CI pipeline. This ensures that only packages matching `package-lock.json` are installed, see [this Stackoverflow answer](https://stackoverflow.com/questions/52499617/what-is-the-difference-between-npm-install-and-npm-ci) for more details and a reference to the npm documentation.

### Docker

Docker image dependencies exist in Dockerfiles and elsewhere, such as in CircleCI config files. The [Dockpin](https://github.com/Jille/dockpin) tool can be used to pin Docker base images to their currently latest versions. To pin a dockerfile, `dockpin docker pin -f Dockerfile`. To pin Docker base image dependencies elsewhere, `dockpin docker resolve [base-image]`, for example, `dockpin docker resolve ubuntu@20.04`. Here's a handy script to do this on CircleCI yaml files, replacing the image reference with one with a hash, and additionally commenting with the timestamp the hash was obtained:

```
#!/bin/bash

ymlfile=$1

if [ -z "$1" ] ; then
    echo usage: $0 circleci-config-ymlfile
    echo example: $0 ./.circleci/config.yml
    exit 0
fi

for x in `grep -A1 docker $1|grep -- '- image:'|sed 's/.*image:\ \(.*\)/\1/g'|sed "s/'//g"|sort|uniq`;do
    hashed=`dockpin docker resolve $x`
    echo base $x hashed $hashed
    sed -i "s~$x~$hashed\ #\ $x,\ `date`~g" $ymlfile
done
```

### Go

When adding a Go dependency using `go get`, the dependency can be installed specifying either a specific version (`go get example.com/theirmodule@v1.3.4`), or the latest available version (`go get example.com/theirmodule@latest`), or a commit hash (`go get example.com/theirmodule@4cf76c2`) or a branchname (`@branchname`). In all cases, the used dependencies are listed in the automatically generated `go.mod` file and the content hashes of the dependencies are written to the `go.sum` file. Make sure to commit the `go.mod` and `go.sum` files to your repository. This ensures that subsequent builds download exactly the same dependencies.

### Github Actions

GitHub Actions are specified in the `.yml` files in the `.github/workflows` directory inside the Github repository. Check [this nice tool](https://app.stepsecurity.io/) by [Stepsecurity](https://www.stepsecurity.io/) that can harden the workflow spec. Check at least the "Restrict permissions..." and "Pin actions..." boxes, then paste the workflow `.yml` file and click Secure workflow. Then, review the changes and paste the result back into the workflow `.yml` file.
