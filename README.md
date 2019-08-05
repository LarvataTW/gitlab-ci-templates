# GitLab CI Templates

From https://gitlab.com/gitlab-org/gitlab-ce/tree/master/lib/gitlab/ci/templates

Lastest Sync Commit: b297cdcb

## Auto-DevOps

在自己的專案引入通用的 Auto-DevOps 流程：

1. 在專案目錄下建立 .gitlab-ci.yml 檔案
2. 填入以下內容。

```yml
include:
  - project: 'larvata/devops/gitlab-ci-templates'
    ref: master
    file: 'Auto-DevOps.gitlab-ci.yml'
```

## CI for Rails Projects

1. 在專案目錄下建立 .gitlab-ci.yml 檔案
2. 填入以下內容。

```yml
include:
  - project: 'larvata/devops/gitlab-ci-templates'
    ref: master
    file: 'Rails.gitlab-ci.yml'
```

## CI for Laravel Projects

1. 在專案目錄下建立 .gitlab-ci.yml 檔案
2. 填入以下內容。

```yml
include:
  - project: 'larvata/devops/gitlab-ci-templates'
    ref: master
    file: 'Laravel.gitlab-ci.yml'
```

## CI for Golang Projects

1. 在專案目錄下建立 .gitlab-ci.yml 檔案
2. 填入以下內容。

```yml
include:
  - project: 'larvata/devops/gitlab-ci-templates'
    ref: master
    file: 'Golang.gitlab-ci.yml'
```