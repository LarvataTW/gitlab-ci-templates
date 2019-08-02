# GitLab CI Templates

From https://gitlab.com/gitlab-org/gitlab-ce/tree/master/lib/gitlab/ci/templates
Lastest Sync Commit: b297cdcb

## TL;DR

Put this file to your project's root.

.gitlab-ci.yml
```yml
include:
  - project: 'larvata/devops/gitlab-ci-templates'
    ref: master
    file: 'Auto-DevOps.gitlab-ci.yml'
```