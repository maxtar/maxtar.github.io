---
title: "GitHub"
date: 2022-10-03T21:37:57+03:00
tags: ["программирование", "git"]
---

Разная информация по работе с [GitHub.com](https://github.com)

{{< toc >}}

## Влить исходный репозиторий в свой форканый

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
