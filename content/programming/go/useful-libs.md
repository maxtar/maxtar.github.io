---
title: "Полезные библиотеки"
date: 2022-10-05T00:55:20+03:00
tags: [go, программирование]
---

{{< toc >}}

## Конфигурация и всё такое

* [viper](https://github.com/spf13/viper) Чтение и сохранение конфигурации в различных форматах.
* [Работа с командной строкой: создание флагов командной строки в POSIX формате, автоматическая генерация "как использовать"](https://github.com/spf13/cobra).
* [Kingpin](https://github.com/alecthomas/kingpin) - ещё одна реализация работы с флагами. [Godoc](https://godoc.org/github.com/alecthomas/kingpin).
* [Flaggy](https://github.com/integrii/flaggy). Также работа с командной, возможность создания подкоманд. [Godoc](https://godoc.org/github.com/integrii/flaggy).
* [Go-Config](https://github.com/micro/go-config). Позволяет собирать конфигурацию из различных источников (файлы, командная строка и т.д.). [Godoc](https://godoc.org/github.com/micro/go-config). [Описание в блоге](https://micro.mu/blog/2018/07/04/go-config.html).
* [Gonfig](https://github.com/tkanos/gonfig) - позволяет читать конфигурацию из json и переменных окружения.
* [Venom](https://github.com/moogar0880/venom). Также позволяет конфигурировать из различных источников. [GoDoc](https://godoc.org/github.com/moogar0880/venom).
* Реализация формата [HOCON](https://github.com/lightbend/config/blob/master/HOCON.md) [configuration](https://github.com/go-akka/configuration). [GoDoc](https://godoc.org/github.com/go-akka/configuration).
* [Yaml](https://github.com/go-yaml/yaml) - работа с YAML от [Canonical](https://www.canonical.com/). [API](https://gopkg.in/yaml.v3). [Blog](https://blog.ubuntu.com/2019/04/05/api-v3-of-the-yaml-package-for-go-is-available).
* [promptui](https://github.com/manifoldco/promptui) - позволяет запрашивать у пользователя информацию в процессе работает. Интегрируется, например с [cobra](https://github.com/spf13/cobra) и другими подобными библиотеками. [GoDoc](https://pkg.go.dev/github.com/manifoldco/promptui?tab=doc).
* [cli](https://github.com/urfave/cli) - ещё одна библиотека для расширения флагов командной строки. [GoDoc](https://pkg.go.dev/github.com/urfave/cli?tab=doc).
* [koanf](https://github.com/knadh/koanf) - позиционируется как более легковесный конкурент [viper](https://github.com/spf13/viper).

---

## Логгирование

* Библиотека от Google [Glog](https://github.com/golang/glog). [Документация](https://godoc.org/github.com/golang/glog).
* Библиотека от juju [Loggo](https://github.com/juju/loggo). [Документация](https://godoc.org/github.com/juju/loggo).
* Библиотека от Uber [Zap](https://github.com/uber-go/zap). [Документация](https://godoc.org/go.uber.org/zap).
* [Logrus](https://github.com/sirupsen/logrus). Наверное наиболее популярный. Используется в Docker. [API](https://godoc.org/github.com/sirupsen/logrus).
* Вроде как самая маленькая библиотека [go-logging](https://github.com/op/go-logging). [API](https://godoc.org/github.com/op/go-logging).
* [zerolog](https://github.com/rs/zerolog) - логирование в формате json. [GoDoc](https://godoc.org/github.com/rs/zerolog). Также может логировать в нормальном виде.
* [go-spew](https://github.com/davecgh/go-spew) - красивый вывод в консоль данных для отладки. [GoDoc](https://pkg.go.dev/github.com/davecgh/go-spew@v1.1.1/spew?tab=doc).
* [httpretty](https://github.com/henvic/httpretty) - удобное логирование в консоль http запросов как на сервере, так и на клиенте. [GoDoc](https://pkg.go.dev/github.com/henvic/httpretty?tab=doc).
* [zlog](https://github.com/m-mizutani/zlog) - логер позволяет скрывать чувствительную информацию из логирования. [GoDoc](https://pkg.go.dev/github.com/m-mizutani/zlog@v0.2.0).

---

## GUI

* Пользовательский интерфейс в терминале
  [Отличная статья](https://appliedgo.net/tui) с обзором разных библиотек для написания text-based GUI.
  * [Пользовательский интерфейс в терминале (https://github.com/nsf/termbox-go)](https://github.com/nsf/termbox-go).
  * [Ещё одна реализация (https://github.com/gdamore/tcell)](https://github.com/gdamore/tcell). Почти полностью совместима с [termbox-go](https://github.com/nsf/termbox-go).
  * [gocui](https://github.com/jroimartin/gocui). [Godoc](https://godoc.org/github.com/jroimartin/gocui).
  * [TermUI](https://github.com/gizak/termui). [Документация](https://github.com/gizak/termui/wiki).
  * [Bubble Tea (Bubble Tea)](https://github.com/charmbracelet/bubbletea) - от создателей [Glow](https://github.com/charmbracelet/glow).
* [Реализация node.js socket (https://github.com/googollee/go-socket.io)](https://github.com/googollee/go-socket.io). Полезно при использовании [electron](http://electron.atom.io) в качестве UI.
* [Библиотека для написания GUI на Electron (https://github.com/asticode/go-astilectron)](https://github.com/asticode/go-astilectron).
* [Walk.](https://github.com/lxn/walk) Библиотека позволяет писать GUI под Windows. Является обёрткой над win32 API.
* [duit](https://github.com/mjl-/duit). Развивающаяся библиотека. Кроссплатформенная. [Вводная информация](https://www.ueber.net/who/mjl/blog/p/duit-developer-ui-toolkit/).
* [WebView](https://github.com/zserge/webview) - вызов встроенного в GUI операционки просмотрщика HTML. Кросплатформенный. [GoDoc](https://godoc.org/github.com/zserge/webview).
* [QT(https://github.com/therecipe/qt)](https://github.com/therecipe/qt) - биндинг QT для Go. [Wiki](https://github.com/therecipe/qt/wiki).
* [WUI(https://github.com/gonutz/wui)](https://github.com/gonutz/wui) - позволяет создавать простые GUI в Windows. [GoDoc](https://godoc.org/github.com/gonutz/wui).
* [Systray](https://github.com/getlantern/systray) - позволяет выводить информацию в tray.
* [Gio](https://git.sr.ht/~eliasnaur/gio) - пилит чувак из Google. Надо следить. Основной сайт  [gioui](https://gioui.org).
* [Gi](https://github.com/goki/gi) - ещё один framework, но зависит от cgo.
* [fyne](https://github.com/fyne-io/fyne) - кроссплатформенная библиотека. Под виндой собралась. [GoDoc](https://pkg.go.dev/fyne.io/fyne?tab=doc). Документация на [сайте разработчика](https://fyne.io/develop/).
* [giu](https://github.com/AllenDang/giu) - обёртка над [Dear ImGui](https://github.com/ocornut/imgui). Поддерживает lua. [GoDoc](https://pkg.go.dev/github.com/AllenDang/giu?tab=doc).
* [govcl(https://github.com/ying32/govcl)](https://github.com/ying32/govcl) - биндинг над графической библиотекой lazurus. Мне кажется очень перспективная. [README](https://github.com/ying32/govcl/blob/master/README.en-US.md).
* [pix](https://embeddedgo.github.io/2022/03/09/pix_a_minimalistic_graphic_library_part1.html) - какая-то минималистическая библиотека. [GoDoc](https://pkg.go.dev/github.com/embeddedgo/display/pix).

---

## Консоль

* [go-pretty](https://github.com/jedib0t/go-pretty) - упрощает вывод текста, таблиц, списков в консоль. Progressbar. [GoDoc.](https://pkg.go.dev/github.com/jedib0t/go-pretty?tab=doc)
* [gchalk](https://github.com/jwalton/gchalk) - позволяет выводить в консоль разноцветный текст. [GoDoc](https://pkg.go.dev/github.com/jwalton/gchalk?readme=expanded#section-documentation).
* [PTerm](https://pterm.sh) - ещё одна реализация цветного терминала. Очень прикольный. [GitHub](https://github.com/pterm/pterm).
* [lipgloss](https://github.com/charmbracelet/lipgloss) - ещё одна библиотека для создания интерфсов в терминале.
* Анимация в командной строке [Wow](https://github.com/gernest/wow).
* [progressbar](https://github.com/schollz/progressbar) - простой progressbar в консоли. [GoDoc](https://godoc.org/github.com/schollz/progressbar).
* [progressbar](https://github.com/schollz/progressbar) от автора croc. [GoDoc](https://pkg.go.dev/github.com/schollz/progressbar/v3).

---

## Работа с БД

* [sqlx](https://github.com/jmoiron/sqlx). Работа с данными как со структурами.
* [sqlboiler](https://github.com/volatiletech/sqlboiler). Ещё одна библиотека для генерации данных на основании схемы. [Документация](https://godoc.org/github.com/volatiletech/sqlboiler).
* [Драйвер для MS SQL (https://github.com/denisenkom/go-mssqldb)](https://github.com/denisenkom/go-mssqldb).
* [Bolt (embeded key/value база данных) (https://github.com/boltdb/bolt)](https://github.com/boltdb/bolt) (например, используется в [InfluxDB](https://influxdata.com/)).
  * [Список проектов, использующих bolt](https://github.com/boltdb/bolt#other-projects-using-bolt). Среди них много интересных.
* [Budger](https://github.com/dgraph-io/badger).
* [Драйвер для sqllite (https://github.com/mattn/go-sqlite3)](https://github.com/mattn/go-sqlite3)
* [ql](https://github.com/cznic/ql) - embedded SQL database. [GoDoc](https://godoc.org/github.com/cznic/ql).
* [Gorm](http://gorm.io/) - ORM для Go. [Github](https://github.com/jinzhu/gorm). [GoDoc](https://godoc.org/github.com/jinzhu/gorm). [Docs](http://gorm.io/docs/).
* [go-sqlbuilder](https://github.com/huandu/go-sqlbuilder) - постритель запросов к базе. [GoDoc](https://pkg.go.dev/github.com/huandu/go-sqlbuilder?tab=doc).
* [squirrel](https://github.com/Masterminds/squirrel) - sql генератор. [GoDoc](https://pkg.go.dev/github.com/Masterminds/squirrel?tab=doc).

---

## Работа с json, XML

* [jsoniter](https://github.com/json-iterator/java).
* Проекты Tidwall
  * [gjson](https://github.com/tidwall/gjson). Библиотека для работы с json. Можно получать значение по пути.
  * [sjson](https://github.com/tidwall/sjson). Библиотека, противоположная gjson. Позволяет устанавливать значения по пути.
  * [jj](https://github.com/tidwall/jj) - обработка json на потоке.
* [fastjson](https://github.com/valyala/fastjson). Библиотека от создателя [fasthttp](https://github.com/valyala/fasthttp). [API](https://godoc.org/github.com/valyala/fastjson).
* [gojsonq](https://github.com/thedevsaddam/gojsonq) A simple Go package to Query over JSON/YAML/XML/CSV Data. [GoDoc](https://godoc.org/github.com/thedevsaddam/gojsonq).
* [easyjson](https://github.com/mailru/easyjson) - серилизатор без reflection от mail.ru.
* [hujson](https://github.com/tailscale/hujson) - HumanJson - позволяет парсить json с комментариями и запятыми после последнего элемента. [GoDoc](https://pkg.go.dev/github.com/tailscale/hujson?tab=doc).
* [go-json](https://github.com/goccy/go-json) - очередной быстрый заменитель стандартной библиотеки.
* [sonic](https://github.com/bytedance/sonic) - библиотека от создателей Tik-Tok. Используют ассемблер. [GoDoc](https://pkg.go.dev/github.com/bytedance/sonic).

---

## HTML, парсинг сайтов

* [goquery](https://github.com/PuerkitoBio/goquery) - позволяет работать со страницой как Jquery только на GO. Удобно для разбора. [GoDoc](https://pkg.go.dev/github.com/PuerkitoBio/goquery?tab=doc).
* [goquery](https://github.com/PuerkitoBio/goquery) - типа j-qury на Go. Позволяет работать с html через запросы.

---

## Работа с файлами

* [fslock](https://github.com/juju/fslock) - блокировка файлов. [Godoc](https://godoc.org/github.com/juju/fslock).
* [fsnotify](https://github.com/fsnotify/fsnotify) - отслеживание изменений ФС. [GoDoc](https://godoc.org/github.com/fsnotify/fsnotify).

---

## Тестирование

* Bdd test framework [ginkgo](http://onsi.github.io/ginkgo). [GitHub](https://github.com/onsi/ginkgo).
  * [gomega](https://onsi.github.io/gomega) - библиотека для сравнения, интегрируется с ginkgo.
* [goblin](https://github.com/franela/goblin) - ещё один BDD.
* [Godoc](https://github.com/DATA-DOG/godog). Пакет для создание и запуска тестов на Cucumber в Go.
  * [Как использовать godoc для создания заглушек на основании feature-файлов](https://semaphoreci.com/community/tutorials/how-to-use-godog-for-behavior-driven-development-in-go)
  * [Gherkin parser Go](https://github.com/cucumber/gherkin-go).
* [Testify](https://github.com/stretchr/testify) - библиотека по принципу *unit. Добавляет методы assert.
* [GoConvey](http://goconvey.co/). [Github](https://github.com/smartystreets/goconvey).
* [RobotGo](https://github.com/go-vgo/robotgo) - позволяет управлять GUI из Go.[GoDoc](https://godoc.org/github.com/go-vgo/robotgo). [ApiDoc](https://github.com/go-vgo/robotgo/blob/master/docs/doc.md).
* [Rapid](https://github.com/flyingmutant/rapid) - property-based тестирование. [GoDoc](https://godoc.org/github.com/flyingmutant/rapid).
* [go-cmp](https://github.com/google/go-cmp) - библиотека для сравнения значений двух структур. [GoDoc](https://godoc.org/github.com/google/go-cmp/cmp).
* [quicktest](https://github.com/frankban/quicktest) - набор удобных методов.
* [chromedr](https://github.com/chromedp/chromedp) - реализация Chrome driver API на Go. [GoDoc](https://pkg.go.dev/github.com/chromedp/chromedp?tab=doc).
* [gocheck](https://labix.org/gocheck) - конкурент [testify](https://github.com/stretchr/testify).

---

## HTTP

* [fasthttp](https://github.com/valyala/fasthttp) - на сегодняшний момент самая быстрая реализация http сервера на Go. [API](https://godoc.org/github.com/valyala/fasthttp)
* [resty](https://github.com/go-resty/resty) - rest-client, позволяющий удобно делать запросы и разбирать ответы. Автоматически измеряет время ответа от сервера. [GoDoc](https://godoc.org/gopkg.in/resty.v1).

---

## WEB-приложения

* [Gorilla web toolkit](http://www.gorillatoolkit.org). [Небольшая вводная](https://www.activestate.com/blog/2017/04/creating-web-app-using-golang-gorilla-web-toolkit).
* [Revel](https://revel.github.io/). Framework типа [Grails](https://grails.org/) для Go.
* Компилятор Go в JS [GopherJs](https://github.com/gopherjs/gopherjs).
* [GoWebApp](https://github.com/josephspurrier/gowebapp) - MVC web application на Go. [Blue Jay - Blueprint](https://github.com/blue-jay/blueprint) - Более продвинутая реализация.
* Framework [macaron](https://go-macaron.com). [Документация](https://go-macaron.com/docs). [Github](https://github.com/go-macaron/macaron).
* [hutplate](https://github.com/usmanhalalit/hutplate) - надстройка над http для облегчения авторизации, сессионностии прочее.
* [Bufallo](https://gobuffalo.io/) - ещё один web-framewrok. [Документация](https://beego.me/docs/intro). [Github](https://github.com/gobuffalo/buffalo).
* [Beego](https://beego.me) web-framework. [Github](https://github.com/astaxie/beego). [Godoc](https://godoc.org/github.com/astaxie/beego).
* [quicktemplate](https://github.com/valyala/quicktemplate) - замена работы с шаблонами в Go. Похожа на работу с Jsp в Java. [API](https://godoc.org/github.com/valyala/quicktemplate).
* [gramework](https://github.com/gramework/gramework) - от создателя [fasthttp](https://github.com/valyala/fasthttp).
* [chi](https://github.com/go-chi/chi) - простой легковесный роутер как [Gorilla](http://www.gorillatoolkit.org), только легче и идеоматичней. [Godoc](https://godoc.org/github.com/go-chi/chi).
* [echo](https://echo.labstack.com/) - легковесный web-framework.
* [Gin](https://github.com/gin-gonic/gin) - вроде как шустрый web-framework. [Офицальный сайт](https://gin-gonic.com/). [GoDoc](https://godoc.org/github.com/gin-gonic/gin).
* [authboss](https://github.com/volatiletech/authboss) - библиотека для аутентификации, авторизации. [GoDoc](https://godoc.org/github.com/volatiletech/authboss).
* [sessionup](https://github.com/swithek/sessionup) - позволяет управлять сессиями. [GoDoc](https://godoc.org/github.com/swithek/sessionup)
* [Secure](https://github.com/unrolled/secure) - прослойка позволяет настраивать некоторую безопасность для web-приложений. [GoDoc](https://pkg.go.dev/github.com/unrolled/secure?tab=doc).
* [nosurf](https://github.com/justinas/nosurf) - помогает осущесвлять проверку безопасности для web-серверов. [GoDoc](https://pkg.go.dev/github.com/justinas/nosurf?tab=doc).
* [go-kit](https://gokit.io/) - набор для создания микросервисов. [GitHub](https://github.com/go-kit/kit).
* [webrtc](https://github.com/pion/webrtc) - реализация WebRTC на GO.
* [goa](https://goa.design) - библиотека позволяет быстро создавать api и микросервисы. Имеет свой DSL для описания. [GitHub](https://github.com/goadesign/goa).
* [go-app](https://go-app.dev) - ещё один интересный проект написания progressive web apps (PWA). С декларативным синтаксисом. [GitHub](https://github.com/maxence-charriere/go-app).
* [ldpap](https://github.com/go-ldap/ldap) - реализация LDAP 3 на GO.
* [Zepto](https://go-zepto.com) - обещают легковесный framework в Go-стиле.
* [GopherJS](https://github.com/gopherjs/gopherjs) - компилятор из go в JS. [GoDoc](https://pkg.go.dev/github.com/gopherjs/gopherjs/js).
* [flogo](https://www.flogo.io) - framework для создания микро-сервисов. [GitHub](https://github.com/project-flogo).
* [bud](https://github.com/livebud/bud) - очередной мощный фреймворк для создания сайтов. Пока требует node.js. Будем наблюдать.

---

## OpenAPI

* [ogen](https://github.com/ogen-go/ogen). [Официальный сайт](https://ogen.dev).

---

## Работа с сетью

* [Evio](https://github.com/tidwall/evio) - работа с сетью, основанная на событиях.
* [Noise](https://github.com/perlin-network/noise). Библиотека, позволяющая писать децентрализованные P2P приложения. [Godoc](https://godoc.org/github.com/perlin-network/noise).
* [limiter](https://github.com/ulule/limiter) - библиотека для разных ограничений в сети, типа количества запросов в секунду.

---

## Работа со строками

* [Dateparse](https://github.com/araddon/dateparse) - библиотека для парсинга строк, представляющих из себя различные форматы дат. [Документация](https://godoc.org/github.com/araddon/dateparse).
* [GoAWK](https://github.com/benhoyt/goawk) - реализация парсера языка AWK на Go. Есть возможность использовать прямо внутри Go. [GoDoc](https://godoc.org/github.com/benhoyt/goawk).

---

## Работа со временем

* [Now](https://github.com/jinzhu/now) - библиотека расширяет некоторые методы для работы с датой. [Документация](https://godoc.org/github.com/jinzhu/now).
* [cron](https://github.com/robfig/cron) - реализация cron на GO. [GoDoc](https://pkg.go.dev/github.com/robfig/cron).

---

## Генерация различных ID

Информация взята [отсюда](https://blog.kowalczyk.info/article/JyRZ/generating-good-random-and-unique-ids-in-go.html?utm_source=golangweekly&utm_medium=email).

| Пакет | Пример | Описание формата |
| - | - | - |
| [ksuid](https://github.com/segmentio/ksuid) | 0pPKHjWprnVxGH7dEsAoXX2YQvU | 4 bytes of time (seconds) # 16 random bytes |
| [xid](https://github.com/rs/) | b50vl5e54p1000fo3gh0 | 4 bytes of time (seconds) # 3 byte machine id # 2 byte process id # 3 bytes random |
| [betterguid](https://github.com/kjk/betterguid) | -Kmdih_fs4ZZccpx2Hl1 | 8 bytes of time (milliseconds) # 9 random bytes |
| [sonyflake](https://github.com/sony/sonyflake) | 20f8707d6000108 | ~6 bytes of time (10 ms) # 1 byte sequence # 2 bytes machine id |
| [ulid](https://github.com/oklog/ulid) | 01BJMVNPBBZC3E36FJTGVF0C4S | 6 bytes of time (milliseconds) # 8 bytes random |
| [sid](https://github.com/chilts/sid) | 1JADkqpWxPx-4qaWY47~FqI | 8 bytes of time (ns) # 8 random bytes |
| [go.uuid](https://github.com/satori/go.uuid) | 5b52d72c-82b3-4f8e-beb5-437a974842c | UUIDv4 from [RFC 4112](http://tools.ietf.org/html/rfc4122) for comparison |
| [uuid](https://github.com/google/uuid) | UUIDs based on RFC 4122 |  |

---

## Работа с hardware

* [Gobot](https://gobot.io)\
  Библиотека позволяет программировать различные устройства. Репозиторий на [Guthub](https://github.com/hybridgroup/gobot). [Документация](https://gobot.io/documentation).
* [Emgo](https://github.com/ziutek/emgo)\
  Позволяет писать микропрограммы для ARM Cortex-M based MCUs. Репозиторий на [Github](https://github.com/ziutek/emgo). [Блог](https://ziutek.github.io/2018/03/30/go_on_very_small_hardware.html) как это всё работает.
* [Periph](https://periph.io/) от команды google [GitHub](https://github.com/google/periph). [GoDoc](https://godoc.org/periph.io/x/periph).
* [Tinygo](https://tinygo.org/) [GitHub](https://github.com/tinygo-org/tinygo).
* [TamaGo](https://github.com/f-secure-foundry/tamago) - bare metal Go for ARM SoCs . Позволяет писать на GO для голых чипов AMD

---

## Сетевые framework

* [TarsGo](https://github.com/TarsCloud/TarsGo). Реализация tars протокола для Go. [GoDoc](https://godoc.org/github.com/TarsCloud/TarsGo/tars).

## Списки и наборы

* [Go-Set](https://github.com/scylladb/go-set) - набор разных типов коллекций и операций с ними. [GoDoc](https://godoc.org/github.com/scylladb/go-set).
* [Enumer](https://github.com/alvaroloes/enumer) - генератор для enum.
* [concurrent-map](https://github.com/orcaman/concurrent-map) - конкурентная мапа.

---

## Игры

* [Ebiten](https://hajimehoshi.github.io/ebiten/). Позволяет писать двухмерные игры. [Godoc](https://godoc.org/github.com/hajimehoshi/ebiten). Краткая [справка](https://github.com/hajimehoshi/ebiten/wiki/Cheat-Sheet). [GitHub](https://hajimehoshi.github.io/ebiten).
* [Prototype](https://github.com/gonutz/prototype). Простая библиотека для работы с канвой. [GoDoc](https://godoc.org/github.com/gonutz/prototype/draw).
* Библиотека для написания игр [pixel](https://github.com/faiface/pixel).

---

## Графика

* [Draw2d](https://github.com/llgcode/draw2d) - библиотека для вывода графики. [Godoc](https://godoc.org/github.com/llgcode/draw2d).
* [Gg](https://github.com/fogleman/gg) - визуализация двухмерной графики. [Godoc](https://godoc.org/github.com/fogleman/gg).
* [colorgrad](https://github.com/mazznoer/colorgrad) - позволяет делать градиенты, шкалы цветов и всё такое. [GoDoc](https://pkg.go.dev/github.com/mazznoer/colorgrad).
* [generativeart](https://github.com/jdxyw/generativeart) - позволяет создавать абстрактные рисунки.
* [imaging](https://github.com/disintegration/imaging) - изменение изображений - изменение масштаба, поворот и т.д.

---

## Видео

* [Go Fluent FFmpeg](https://github.com/modfy/go-fluent-ffmpeg) - wrapper для ffmpeg. Позволяет работать с видеофайлами из программы на Go. [GoDoc](https://pkg.go.dev/github.com/modfy/fluent-ffmpeg#section-readme).

---

## Статистика и математика

* [Tachymeter](https://github.com/jamiealquiza/tachymeter) - подсчёт статистики с выводом в виде json, histogram и в консоль. [GoDoc](https://godoc.org/github.com/jamiealquiza/tachymeter).
* [Gonum](https://www.gonum.org) - мощная библиотека для различной математики и статистики. [Github](https://github.com/gonum/gonum). [GoDoc](https://godoc.org/gonum.org/v1/gonum).
* [decimal](https://github.com/shopspring/decimal) - работа с числами с заданной точностью. [GoDoc](https://pkg.go.dev/github.com/shopspring/decimal).

---

## Обработка данных на потоке и прочее

* [Machinery](https://github.com/RichardKnop/machinery) обработка сообщений. Работа с различными источниками. [Godoc](https://godoc.org/github.com/RichardKnop/machinery/v1).
* [Bigslice](https://bigslice.io/) - аналог Spark на Go. [GitHub](https://github.com/grailbio/bigslice). [GoDoc](https://pkg.go.dev/github.com/grailbio/bigslice?tab=doc).
* [watermill](https://github.com/ThreeDotsLabs/watermill) - работа с сообщениями. Возможность интегрироваться с Kafka, RabbitMQ.

---

## Парсеры

* Интерпретатор GO [Yaegi](https://github.com/containous/yaegi). [Введение](https://blog.containo.us/announcing-yaegi-263a1e2d070a). [GoDoc](https://godoc.org/github.com/containous/yaegi). Работает как библиотека, так и как приложение командной строки. Позволяет парсить и запускать код на Go.

---

## Коллекции

* [ristretto](https://github.com/dgraph-io/ristretto) - конкурентный кеш. [Описание в блоге](https://blog.dgraph.io/post/introducing-ristretto-high-perf-go-cache/). [Godoc](https://godoc.org/github.com/dgraph-io/ristretto).
* [olric](https://github.com/buraksezer/olric) - распределённый in-memory кеш, ключ-значение. [GoDoc](https://pkg.go.dev/github.com/buraksezer/olric).

---

## Встраивание ресурсов (теперь не актуально, так как с версии 1.6 есть встроенный механизм)

* [esc](https://github.com/mjibson/esc) - встраивает файлы в бинарник, при этом их сжимая. [GoDoc](https://godoc.org/github.com/mjibson/esc).
* [Rice](https://github.com/GeertJohan/go.rice) - упаковка ресурсов в исполняемый файл. [GoDoc](https://godoc.org/github.com/GeertJohan/go.rice).
* [packr](https://github.com/gobuffalo/packr) -создан на основе rice, но улучшен. [GoDoc](https://godoc.org/github.com/gobuffalo/packr).
* [statik](https://github.com/rakyll/statik) - чем-то похож на esc. [GoDoc](https://godoc.org/github.com/rakyll/statik).
* [broccoli](https://github.com/aletheia-icu/broccoli) - встраивает и сжимает ресурсы в бинарник. [GoDoc](https://pkg.go.dev/aletheia.icu/broccoli/fs?tab=doc).
* [binclude](https://github.com/lu4p/binclude) - тоже умеет сжимать. Обращение к ерсурсам практически также, как и к ресурсам системы. [GoDoc](https://pkg.go.dev/github.com/lu4p/binclude?tab=doc).

---

## Вспомогательные утилиты

* [Goweight](https://github.com/jondot/goweight) - анализ размера используемых пакетов.
* [go-mod-outdated (go-mod-outdated)](https://github.com/psampaz/go-mod-outdated) - анализ устаревших пакетов в зависимостях.
* [Spaghetti](https://github.com/adonovan/spaghetti) - анализ зависимостей в браузере.
* [Go binary size SVG treemap](https://github.com/nikolaydubina/go-binsize-treemap) - рисует SVG карту библиотек в бинарнике. Примерно как Goweight.

---

## Работа со звуком

* [beep](https://github.com/faiface/beep) - работа со звуком в форматах WAV, MP3, OGG, and FLAC. [GoDoc](https://pkg.go.dev/github.com/faiface/beep?tab=doc).

---

## Мониторинг

* [ExpvarMon](https://github.com/divan/expvarmon) - библиотека позволяет мониторить в консоли программу на Go.
* [fgprof](https://github.com/felixge/fgprof) - мониторинг загрузки процессора. Достаточно простой и наглядный. [GoDoc.](https://pkg.go.dev/github.com/felixge/fgprof?tab=doc)
* [statviz](https://github.com/arl/statsviz) - рисует разные графики в runtime.

---

## OpenCV

* [gocv](https://gocv.io/) - библиотека для работы с OpenCv из Go. [GitHub](https://github.com/hybridgroup/gocv).
* [Работа с открытой библиотека OpenCV](https://github.com/go-opencv/go-opencv) - wrapper для OpenCv на Go.

---

## Офис

* [excelize](https://github.com/360EntSecGroup-Skylar/excelize) - работа с excel файлами из Go. [Документация](https://xuri.me/excelize). [GoDoc](https://pkg.go.dev/github.com/360EntSecGroup-Skylar/excelize/v2).

---

## goroutines

* [Runner для goroutines](https://github.com/matryer/runner/blob/master/runner.go). Позволяет легко управлять запущенными goroutines.
* [ants](https://github.com/panjf2000/ants). Позволяет создавать с пулом goroutings. [GoDoc](https://godoc.org/github.com/panjf2000/ants).
* Управление gouroutines [Run](https://github.com/oklog/run). [Godoc](https://godoc.org/github.com/oklog/run).
* [tunny](https://github.com/Jeffail/tunny) - создание пулов gorouting. Похоже как в джаве сделаны Executors. [GoDoc](https://pkg.go.dev/github.com/Jeffail/tunny).

---

## Шифровние

* [age](https://github.com/FiloSottile/age) -библиотека для семмитричного и ассиметриченого шифрования. Может использоватся как отдельная утилита [GoDoc](https://pkg.go.dev/filippo.io/age#section-documentation).

---

## События

* [Колокол](https://github.com/nuttech/bell) - простая библиотека для работы с событиями. Статья от авторов на [Хабре](https://habr.com/ru/post/651453).
* [RxGo](https://github.com/ReactiveX/RxGo) - одна из самых популярных библиотек для работы на событиях.

---

## Разное

* [Распознавание естественных языков](https://github.com/abadojack/whatlanggo).
* [Фильтрация строк из ридера как в Groovy и Unix](https://github.com/msoap/byline). [Документация](https://godoc.org/github.com/msoap/byline).
* [linq, как в C# в Go](https://github.com/ahmetb/go-linq). [Документация](https://godoc.org/github.com/ahmetb/go-linq).
* [Множество библиотек для web](https://github.com/gowww).
* [Etree](https://github.com/beevik/etree). Библиотека для работы с XML.
* Рисование графиков
  * [go-chart](https://github.com/wcharczuk/go-chart).
  * [Glot](https://github.com/Arafatk/glot). [Документация](https://godoc.org/github.com/Arafatk/glot).
* [Список проектов для работы с железом](https://github.com/rakyll/go-hardware).
* Reducemap на Go [gleam](https://github.com/chrislusf/gleam). Анализ данных.
* Паук для web [Colly](https://github.com/asciimoo/colly). [Документация](https://godoc.org/github.com/asciimoo/colly).
* Работа с клавиатурой [keyboard](https://github.com/eiannone/keyboard).
* Глобальных перехват Ctrl+C и прочих прерываний [Goodbye](https://github.com/TheCodeTeam/goodbye). [Статья от автора](https://blog.thecodeteam.com/2017/10/02/say-hello-goodbye/).
* Работа с изображениями [govips](https://github.com/davidbyttow/govips).
* Клиент для [elasticsearch](https://github.com/olivere/elastic).  Запись в [блоге](https://www.ribice.ba/golang-elastic).
* [Gosec](https://github.com/securego/gosec). Библиотека для сканирования исходного кода на Go и выявление проблем с безопасностью.
* [Detective](https://github.com/sohamkamani/detective) - мониторинг распределённых систем. [GoDoc](https://godoc.org/github.com/sohamkamani/detective).
* [Charlatan](https://github.com/percolate/charlatan) позволяет автоматически создавать заглушки для программных интерфейсов.
* [Fake](https://github.com/icrowley/fake). Библиотека для генерации различных данных на русском и английском языках.   [GoDoc](https://godoc.org/github.com/icrowley/fake).
* [Faker](https://github.com/bxcodec/faker) - ещё одна библиотека. [GoDoc](https://pkg.go.dev/github.com/bxcodec/faker?tab=doc).
* [gofakeit](https://github.com/brianvoe/gofakeit) - тоже для генерации данных.
* [Tablewriter](https://github.com/olekukonko/tablewriter) - вывод таблиц в текстовом форматре.
* [Chroma](https://github.com/alecthomas/chroma) - подсветка синтаксиса. [Godoc](https://godoc.org/github.com/alecthomas/chroma).
* [Prototool](https://github.com/uber/prototool) от Uber. Альтернативная работа с protobuf. [Godoc](https://godoc.org/github.com/uber/prototool).
* [BigMachine](https://github.com/grailbio/bigmachine) - библиотека для развертывания кластера. Например, работает в связке с [Bigslice](https://bigslice.io/).
* [g-locale](https://github.com/Xuanwo/go-locale) - определение установленной локали пользователя. [GoDoc](https://pkg.go.dev/github.com/Xuanwo/go-locale?tab=doc).
* [ASCIIGraph](https://github.com/guptarohit/asciigraph) - вывод графиков в консоли при помощи ASCII символов. [GoDoc](https://pkg.go.dev/github.com/guptarohit/asciigraph?tab=doc).
* [validator](https://github.com/go-playground/validator) - проверка значений в структурах. [GoDoc](https://pkg.go.dev/github.com/go-playground/validator?tab=doc).
* [go-humanize](https://github.com/dustin/go-humanize) - позволяет переводить числа в байты, удобное время и прочее. [GoDoc](https://pkg.go.dev/github.com/dustin/go-humanize?tab=doc).
* [error](https://github.com/cockroachdb/errors) - набор обёрток для обработки ошибок.
* [dagger](https://github.com/autom8ter/dagger) - реализация графов.
* [script](https://pkg.go.dev/github.com/bitfield/script#section-readme) - работа из Go c командами консоли. Возможно написание shell скриптов. [Описание](https://bitfieldconsulting.com/golang/scripting).
