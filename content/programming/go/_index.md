---
title: "Go"
date: 2022-10-02T14:02:40+03:00
tags: ["go", "программирование"]
---

## Различная информация по языку [Go](https://golang.org)

{{< toc-tree >}}

* [Основной репозиторий](https://go.googlesource.com/go), Зеркало на [github.com](https://github.com/golang/go).
* [Документация по разным библиотекам (GoDoc)](https://godoc.org/).
* [Новый сайт с документацией (go.dev)](https://go.dev/).
* [Описание параметров утилиты Go](https://golang.org/cmd/go).
* [Gopm Registry](https://gopm.io/) реестр разных пакетов go. Можно скачать, если на компьютере не установлены программы версионного контроля.
* [Список архитектур и операционок в которые можно компилировать](https://golang.org/doc/install/source#environment).
* [Форум](https://forum.golangbridge.org).
* [Альтернатива Play Golang](https://goplay.space).
* [Go Report Card](https://goreportcard.com). Сервис проверяющий Go репозиторий на соответствие стандартам.
* [Введение в программирование на Go](http://golang-book.ru) - перевод книги [An introduction to programming in Go](http://www.golang-book.com)

## Получение пакетов с зависимостями

```bash
go get package/...
```

Получение пакетов, необходимых для текущего приложения:

```bash
go get .
```

## Полезные статьи и книги

* [Building Web Apps with Go](https://codegangsta.gitbooks.io/building-web-apps-with-go/content/#required-packages).
* [Writing Web Applications](https://golang.org/doc/articles/wiki/).
* [Блог-дайджест](http://yourbasic.org/golang/#language-basics) по основным моментам Go.
* [Essential](https://www.programming-books.io/essential/go) Очень много полезной информации по использованию различных функций и пакетов. Множество примеров.
* [Сайт какого-то энтузиаста.](https://metanit.com/go/) Есть основы по написанию web-приложений.
* [go101.org](https://go101.org/article/unofficial-faq.html) интересные примеры по правильному написанию кода.
* [Go by example](https://gobyexample.com/) - список типовых примеров.
  * [Go в примерах](https://gobyexample.ru/) - то же самое по-русски.
* [Работа с SQL в Go](http://go-database-sql.org/index.html).
* [Описание go tools](https://www.alexedwards.net/blog/an-overview-of-go-tooling) - краткое описание возможностей и команд.
* [Памятка по модулям](https://encore.dev/guide/go.mod).

## Списки проектов

* [Ссылки на полезные проекты Go](https://github.com/golang/go/wiki/Projects).
* [awesome-go](https://awesome-go.com).
* [Non-trivial Golang projects](https://github.com/gophersgang/go-non-trivial-apps)
* [Список Arl](https://github.com/kaxap/arl/blob/master/README-Go.md)

## Поиск библиотек

* [libraries.io](https://libraries.io/go)
* [go-search.org](http://go-search.org)
* [golanglibs.com](https://golanglibs.com/)

## Полезные команды

Просмотр, что убеагает в heap.

```bash
go build -gcflags="-m -m"
```

## Разное

* [On-demand Golang binaries](https://gobinaries.com) - проект, позволяющий автоматически собирать бинарники Go под разные системы. Например через Github CI. [Blog](https://cto.ai/blog/on-demand-go-binaries/) автора.
* [gox](https://github.com/mitchellh/gox) ещё популярное решение. Запись в [блоге](https://www.process-one.net/blog/distributing-prebuilt-go-binaries-on-github-with-gox).
