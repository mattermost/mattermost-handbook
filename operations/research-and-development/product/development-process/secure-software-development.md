# Secure Software Development at Mattermost

This document provides guidelines to secure software development at Mattermost. The document is at the moment a [50% draft](/company/about-mattermost/mindsets#drafts-at-1-50-99) and not conclusive.

## Document scope

This document covers the secure software development practices on all source repositories used to create software products offered by Mattermost.

The product security team is overall in charge of secure software development practices by providing help and guidance and performing various verification activities, including code reviews and testing. Development teams are encouraged to adopt the secure software development practices described here. Third-party plugin developers are also welcome to use this document for guidance.

## Recommended reading

* [OSSF Scorecard Action Check Documentation](https://github.com/ossf/scorecard/blob/main/docs/checks.md)
* [OWASP Top Ten](https://owasp.org/www-project-top-ten/), a curated and updated list on most common security risks in web applications.
* [OWASP Application Security Verification Standard](https://owasp.org/www-project-application-security-verification-standard/)
* [OWASP Cheat Sheet Series](https://cheatsheetseries.owasp.org/)

## Code reviews

### Manual code reviews

The product security team performs reviews on new features and plugins when necessary. Here's some of the things included in the checks:

* Manual diff review
* Static application security testing (SAST) using multiple tools
* Software composition analysis (SCA)
* Dynamic application security testing (DAST)

Detailed review checklists are documented in the [security team shared drive](https://drive.google.com/drive/folders/1s3paBN6sfGRP-NHNuoekDHY_nrtRVagt), accessible to team members only.

### Automated code reviews

Mattermost production repositories have automated code security analysis tools set up. If this is not the case for a specific repository, please reach out to the product security team for assistance.

The automated tools in each repository depend on the technologies used in the repository. In practice, we use [CodeQL](https://codeql.github.com/) as a Github Action to automatically analyze all pull requests. Additionally, the use of the [OSSF Security Scorecards GitHub Action](https://github.com/ossf/scorecard) is strongly encouraged. This document describes some of the best practices checked by the Scorecards action.

## Dependency pinning

Dependency pinning hardens software development workflows against [software supply chain attacks](https://arstechnica.com/information-technology/2019/08/the-year-long-rash-of-supply-chain-attacks-against-open-source-is-getting-worse/). The specific threat being mitigated is upstream dependencies being taken over by attackers and replaced with malicious content. Attacks are more likely to be successful against projects that refer to their dependencies without explicitly specifying a computed hash value for the dependency: In case of a dependency takeover, pulling the _latest_ version triggers the attack. The likelihood of this risk materializing is low, but the impact can be bad.

In practice, defining build-time dependencies with an explicit hash is the preferred solution. When specifying hashes to existing dependencies that did not use hash-based references before, picking the hash of the currently used dependency is a good starting point as it is often not practical to do a full audit of all dependencies. Picking a hash and sticking to it doesn't ensure that the hash represents a safe version, but it does ensures that a possibly malicious later version is not introduced in the build process afterwards.

Many dependency managers support automatic dependency pinning so that a developer doesn't need to explicitly find and set dependency hashes. For example both Go and npm do, as described below.

### Npm dependencies

With npm, always use `npm ci` instead of `npm install` in build scripts and automated pipelines. This ensures that only packages matching the existing `package-lock.json` file are installed. See [the documentation on `npm ci`](https://docs.npmjs.com/cli/v8/commands/npm-ci) for more details.

When adding new dependencies, prefer [exact versions](https://docs.npmjs.com/cli/v8/commands/npm-install#save-exact) over the default semver range.

### Docker

Docker image dependencies exist in Dockerfiles and elsewhere, such as in CircleCI config files. The [Dockpin](https://github.com/Jille/dockpin) tool can be used to pin Docker base images to their currently latest versions. To pin a dockerfile, run `dockpin docker pin -f Dockerfile`. To pin Docker base image dependencies elsewhere, run `dockpin docker resolve [base-image]`; for example `dockpin docker resolve ubuntu@20.04`.

Here's a handy script to do this on CircleCI yaml files, replacing the image reference with one with a hash, and additionally commenting with the timestamp the hash was obtained:

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

When adding a Go dependency using `go get`, the dependency can be installed specifying either a specific version (`go get example.com/theirmodule@v1.3.4`), the latest available version (`go get example.com/theirmodule@latest`), or a commit hash (`go get example.com/theirmodule@4cf76c2`) or branchname (`@branchname`). In all cases, the installed dependencies are added to the automatically generated `go.mod` file and the content hashes of the dependencies are written to the `go.sum` file. Make sure to commit both the `go.mod` and the `go.sum` file to your repository. This ensures that subsequent builds download exactly the same dependencies.

### Github Actions

GitHub Actions are specified in `.yml` files in the `.github/workflows` directory inside a GitHub repository. Check out [this nice tool](https://app.stepsecurity.io/) by [Stepsecurity](https://www.stepsecurity.io/) that can harden the workflow spec. Check at least the "Restrict permissions..." and "Pin actions..." boxes, then paste in the workflow `.yml` file and click "Secure workflow". Review the changes and paste the result back into your workflow `.yml` file.

## A few other things

(most from the [Scorecard checks](https://github.com/ossf/scorecard#scorecard-checks) -- consult with product security team)

* Check that the git repository doesn't contain any secrets anywhere in its history
* Make sure the `SECURITY.md` file exists and describes the security policy
* [Branch protection policy](https://docs.github.com/en/free-pro-team@latest/github/administering-a-repository/about-protected-branches)
* Set up SAST (static analysis) -- mostly we use [CodeQL](https://docs.github.com/en/free-pro-team@latest/github/finding-security-vulnerabilities-and-errors-in-your-code/enabling-code-scanning-for-a-repository#enabling-code-scanning-using-actions)