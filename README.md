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
    file: 'Go.gitlab-ci.yml'
```

## CI for Android Projects

current image: https://github.com/lakoo/lakoo-android-ndk

1. 在專案目錄下建立 .gitlab-ci.yml 檔案
2. 填入以下內容。

```yml
include:
  - project: 'larvata/devops/gitlab-ci-templates'
    ref: master
    file: 'android.gitlab-ci.yml'
```

3. 確認要產出的方式為何，然後使用extends並且在script用gradlew指令去進行。有其他buildVariant請先 ./gradlew task 檢查指令
ex:

```yml
lintTest:
  extends: .lint

buildVariant_main_debug:
  only:
    - develop
  extends: .assembleDebug

buildVariant_main_release:
  only:
    - master
  extends: .assembleRelease

buildVariant_main_pushToFirebase:
  only:
    - develop
  extends: .appModuleDebugVerToFirebase
```

4. discord webhook
> * WEBHOOK_URL = discord server channel url
> * DISCORD_SUCCESS_NOTIFY_ROLE_ID / DISCORD_FAILURE_NOTIFY_ROLE_ID = metion id, ex: <@123456>
>> reference: https://birdie0.github.io/discord-webhooks-guide/other/discord_markdown.html