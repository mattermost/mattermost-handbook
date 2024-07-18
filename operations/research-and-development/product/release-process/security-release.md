# Security Release Process

Security dot releases are done for high, medium and low level severity security issues based on [the backport policy](https://handbook.mattermost.com/operations/security/product-security/product-vulnerability-process#backport-policy). The general steps are:

1. A pull request for the issue is submitted and dev/QA reviewed, and then merged.
2. The bug fix is cherry-picked to the relevant release branch.
3. A release candidate (e.g. 7.2.1-RC1) is cut for quick final smoke tests.
4. After QA approval, a final release build is cut (e.g. 7.2.1) which is ready to be shared with the customer.

Please refer to [the Dot Release Playbook](https://community.mattermost.com/playbooks/playbooks/hjn1xnc3gfnmzeqwssyu6dsa3w/outline) for a most up-to-date checklist.
