---
title: "Полезная информация по git"
date: 2022-10-05T00:45:43+03:00
tags: ["программирование", "git", "github"]
---

{{< toc >}}

## Общая информация

Официальная [книга](https://git-scm.com/book/ru/v1) по Git.

[Как содержать репозиторий в чистоте](http://railsware.com/blog/2014/08/11/git-housekeeping-tutorial-clean-up-outdated-branches-in-local-and-remote-repositories/)

Ещё полезная статья на [Habrahabr](https://habrahabr.ru/post/336708/).

## Как удалять ветки

Локальные:

```bash
git branch -d the_local_branch
```

Удалённые:

```bash
git push origin :the_remote_branch
```

## Удаление всех локальных изменений

```bash
git clean -xdf
```

## Настройка работы ssh с несколькими репозиториями

Создать файл `config` в директории `.ssh`.
Со следующим содержимым:

```ssh
# GitLab.com
Host gitlab.com
  Preferredauthentications publickey
  IdentityFile ~/.ssh/gitlab

Host github.com
  Preferredauthentications publickey
  IdentityFile ~/.ssh/github
```

при этом github и gitlab файлы с приватными ключами соответствующих сервисов.

## Разная информация по работе с GitHub.com

### Влить исходный репозиторий в свой форканый

Информация взята из [официальной документации](https://help.github.com/articles/merging-an-upstream-repository-into-your-fork) github.

1. Открыть консоль и перейти в директорию со своим репозиторием.
1. Переключится, если надо на нужную ветку (обычно master)

    ```bash
    git checkout master
    ```

1. Выкачать изменения из оригинального репозитория:

    ```bash
    git pull https://github.com/ORIGINAL_OWNER/ORIGINAL_REPOSITORY.git BRANCH_NAME
    ```

1. Если есть конфликты исправить их.
1. Закоммитить изменения с результатом слияния
1. Закачать изменения в свой репозиторий

    ```bash
    git push origin master
    ```
