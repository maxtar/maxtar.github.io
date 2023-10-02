---
title: "Полезные программы на Go"
date: 2022-10-09T01:46:24+03:00
tags: [go, программы]
---

Различные программы, написанные на Go.

{{< toc >}}

## Разное

* [Простой Web Framework Echo](https://echo.labstack.com)
* [Лёгкая wiki](https://github.com/peterhellberg/wiki).
* [Ketchup CMS](https://ketchuphq.com), [github](https://github.com/ketchuphq/ketchup).
* [matterbridge](https://github.com/42wim/matterbridge). Мост для объединения различных средств общения (slack, tegeram, mattermost и т.д.).
* [Hermes](https://github.com/George3d6/Hermes) - сервер для обмена файлами.
* [Croc](https://github.com/schollz/croc) - клиент-сервер для посылки файлов.
* Go из Shell [neugram](https://neugram.io/).
* Различные утилиты для проверки сетей (сканеры, парсеры сертификатов и т.д.) [Zmap](https://zmap.io/) [Github](https://github.com/zmap)
* Вывод дерева зависимостей [depth](https://github.com/KyleBanks/depth). [Блог](https://kylewbanks.com/blog/visualize-golang-dependency-trees-with-depth).
  * В графическом виде [go-callvis](https://github.com/TrueFurby/go-callvis).
* [qrcp](https://github.com/claudiodangelis/qrcp) - передача файлов с компа на мобилку, например, по QRCode.
* [mage](https://magefile.org) - замена make на Go. Исходники на [GitHub](https://github.com/magefile/mage).

## Консольные приложения

* [wego](https://github.com/schachmat/wego) - показ погоды в консоли.

## Работа с файлами

* [godu](https://github.com/viktomas/godu) - позволяет быстро просматривать каталоги с большим количеством файлов.
* [lf](https://github.com/gokcehan/lf) - консольный менеджер файлов на Go.
* [wzd](https://github.com/eltaline/wzd) - веб-сервер для работы с огромным количеством файлов.
* [duf](https://github.com/muesli/duf) - отображение информации про диски. Работает только под Unix.
* [fsql](https://github.com/kashav/fsql) - поиск файлов в виде SQL.

## Хранение и версионирование кода

* Система хранения и версионирования кода - [Gogs](https://gogs.io/). [Github](https://github.com/gogits/gogs).
* [Gitea](https://gitea.io) - склонированная и расширенная версия Gogs. Разворачивается локально. Исходники на [GitHub](https://github.com/go-gitea/gitea).
* [Lazygit (https://github.com/jesseduffield/lazygit)](https://github.com/jesseduffield/lazygit). Консольный клиент для работы с git.
* [Gitness](https://gitness.com) - opensource проект. Разворачивается локально. [GitHub](https://github.com/harness/gitness).

## Нагрузочное тестирование

* [K6](https://github.com/loadimpact/k6). [Документация](https://docs.k6.io/docs/running-k6).
* [vegeta (https://github.com/tsenart/vegeta)](https://github.com/tsenart/vegeta) - подключается, либо как библиотека, либо используется из командной строки.

## WEB

* [Caddy](https://caddyserver.com) - лёгкий и быстрый http-сервер как Nginx или Apache. [Документация](https://caddyserver.com). Исходники на [github](https://github.com/caddyserver/caddy).
* [FRP](https://github.com/fatedier/frp) - reverse-proxy.
* [Casbin forum](https://github.com/casbin/casbin-forum) - реализация форума на Go и ReactJS.
* [sftpgo](https://github.com/drakkan/sftpgo) - сервер, поддерживающий различные протоколы: SFTP, HTTP, FTP/S and WebDAV. И также различные системы хранения: local filesystem, encrypted local filesystem, S3 (compatible) Object Storage, Google Cloud Storage, Azure Blob Storage.

## Рисование графиков

[Chart](https://github.com/marianogappa/chart) - рисует график на основании данных из стандартного потока ввода. [Примеры отображения](https://marianogappa.github.io/chart). [Статья об использовании](https://movio.co/blog/improving-with-sql-and-charts).

## Обработка и трансформация данных

* [Benthos (https://github.com/Jeffail/benthos)](https://github.com/Jeffail/benthos). [Документация](https://github.com/Jeffail/benthos/blob/master/docs/README.md). [GoDoc](https://godoc.org/github.com/Jeffail/benthos/lib/stream).
* [Watermill](https://watermill.io) - получение/отправка собщений из/в различные источники данных и их обработка. [Документация](https://watermill.io/docs/). [Github](https://github.com/ThreeDotsLabs/watermill).
* [NATS](https://nats.io/) - полноценный сервер для обмена сообщениями. [Документация](https://nats.io/documentation/). [GitHub](https://github.com/nats-io/gnatsd).

## Сеть

* [Termshark](https://github.com/gcla/termshark) - анализатор дампов как WireShark только в консоли.
* [sftpgo](https://github.com/drakkan/sftpgo) - полноценный sftp сервер.
* [Ethr](https://github.com/microsoft/ethr) - измерение пропускной способности сети.
* [sx](https://github.com/v-byte-cpu/sx) - анализатор открытых портов по типу nmap. Собирать, правда надо самому. Есть зависимость на [libpcap](https://www.tcpdump.org).

## Мониторинг

* [Sampler](https://sampler.dev/). [Статья](https://habr.com/ru/post/463441/) на хабре. [Github](https://github.com/sqshq/sampler).
* [gops](https://github.com/google/gops) - позволяет выводить диагностическую информацию в консоль о запущеных GO приложениях. Для полноценной работы используется в качестве библиотеки. Но может показывать информацию о занимаемой памяти, использования процессора и другое даже без внедрения.
* [devdash](https://thedevdash.com) - позволяет мониторить разные системы и отображать в терминале. Исходники на [GitHub](https://github.com/Phantas0s/devdash).
* [SigNoz](https://github.com/signoz/signoz) - какой-то ещё один офигенный мониторинг. [Сайт](https://signoz.io).

## Служебные

* [certigo](https://github.com/square/certigo) - просмотр сертификатов из командной строки.
* [duf](https://github.com/muesli/duf) - утилита для просмотра занятости дисков. Типа юниксовой {{df}}, только посимпатичнее и кроссплатформенная.

## Работа с графикой

* [Gosaic](https://github.com/atongen/gosaic) - создание мозаичного панно из фотографий.

## Работа с JSON

* [Gron (https://github.com/tomnomnom/gron)](https://github.com/tomnomnom/gron) - парсит JSON и выводит пути элементов. Возможна и обратная операция.

## Работа с картами, координатами и т.д.

* [tile38 (https://github.com/tidwall/tile38)](https://github.com/tidwall/tile38) - позволяет в реальном времени, вроде как, строить маршруты, отслеживать пересечения с областями и кучу чего ещё. [Официальный сайт](https://tile38.com).

## Общение

* [ion](https://github.com/pion/ion) - распределённая система общения. [Документация](https://pionion.github.io).

## Соцсети, fediverse

* [GoToSocial](https://github.com/superseriousbusiness/gotosocial) - реализация сервера ActivityPub. Поддерживает mastodon. [Официальная документация](https://docs.gotosocial.org/en/latest).

## Безопасность

* [gitleaks (https://github.com/zricethezav/gitleaks)](https://github.com/zricethezav/gitleaks) - сканирует репозитории кода на всякие утечки типа паролей.

## Базы данных и прочее

* [CocroachDB](https://github.com/cockroachdb/cockroach). Высоконадёжная база данных.
* [Распределённое хранилище файлов (Роб Пайк)](https://upspin.io/). [GitHub](https://github.com/upspin/upspin).
* [Minio Cloud Storage](https://minio.io/) хранилище файлов. [github](https://github.com/minio/minio). [Документация](https://docs.minio.io).
* [Godown(https://github.com/namreg/godown)](https://github.com/namreg/godown) - распределённое хранилище данных, типа Redis и Hazelcast. [GoDoc](https://godoc.org/github.com/namreg/godown/client). Может использоваться как отдельное приложения, так и из кода на Go.
* [rqlite](https://github.com/rqlite/rqlite) - распределённая база данных на Go. Под капотом sqllite. [GoDoc](https://pkg.go.dev/github.com/rqlite/rqlite).
* [immudb](https://www.codenotary.com/technologies/immudb/) - база данных на основе Block-chain. Обеспечивает целостность данных. Можно использовать как библиотеку в программах на Go. [Документация](https://docs.immudb.io/master). [GitHub](https://github.com/codenotary/immudb).
* [usql](https://github.com/xo/usql) - утилита для работы с разными БД. [GoDoc](https://pkg.go.dev/github.com/xo/usql).
* [Vault](https://www.vaultproject.io) - хранение паролей и прочей чувствительной информации. [GitHub](https://github.com/hashicorp/vault).
* [immudb](https://github.com/codenotary/immudb) - база данных для хранения чувствительной информации, например, данных пользователей. [Документация](https://docs.immudb.io/master). [Официальный сайт](https://codenotary.com/technologies/immudb).
