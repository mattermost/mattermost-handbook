# Dot Release Process

Dot releases are done for high priority and high severity security issues and customer bugs. The general steps are:

1. The issue is escalated by customers, customer support team, community members or internally.
2. Our developer team investigates the issue as soon as possible.
3. A pull request for the issue is submitted and dev/QA reviewed, and then merged.
4. The bug fix is cherry-picked to the relevant release branch.
5. A release candidate (e.g. 7.2.1-RC1) is cut for quick final smoke tests.
6. After QA approval, a final release build is cut (e.g. 7.2.1) which is ready to be shared with the customer.

The time-to-fix varies, but urgent dot releases are always prioritized.

Please refer to [the Dot Release Playbook](https://community.mattermost.com/playbooks/playbooks/hjn1xnc3gfnmzeqwssyu6dsa3w/outline) for a most up-to-date checklist.
