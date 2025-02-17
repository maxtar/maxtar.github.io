---
title: "Тестирование"
date: 2022-10-09T01:08:20+03:00
tags: [тестирование]
---

Всё, что связано с тестированием и автоматизацией тестирования

{{< toc >}}

## Книги по тестированию

[A Friendly Introduction to Software Testing](https://github.com/laboon/ebook) - opensource книга. Можно собрать самому. [Собранная автором версия](https://github.com/laboon/software-testing).
[Google Code Coverage Best Practices](https://testing.googleblog.com/2020/08/code-coverage-best-practices.html)

## Списки полезных программ

* [Список разных ресурсов и средств тестирования](https://github.com/TheJambo/awesome-testing)
* [Список средств для тестирования UI](https://github.com/mojoaxel/awesome-regression-testing)

## GUI

* [Winium](https://github.com/2gis/Winium) от 2GIS. Позволяет тестировать Desktop и Mobile приложения.
* [katalon](https://www.katalon.com) - позволяет тестировать как Web, так и GUI приложения. [Статья](https://habr.com/ru/company/deutschetelekomitsolutions/blog/530684) на Хабре.
* [TestFX](https://github.com/TestFX/TestFX) - тестирование JavaFX приложений.

## WEB-GUI

* [testcafe](https://testcafe.io) - работает без Seleniun.

## WEB

* Управляемый через REST [BrowserMob Proxy](http://bmp.lightbody.net/). На [GitHub](https://github.com/lightbody/browsermob-proxy). _
Позволяет перенаправлять трафик, ограничивать пропускную способность и ещё [кучу всего](https://github.com/lightbody/browsermob-proxy#rest-api). Очень хорошо интегрируется с [Selenium](http://www.seleniumhq.org/).
* [JDI](http://jdi.epam.com) от EPAM. Проект на [Github](https://github.com/epam/JDI). Тестовый framework позволяющий абстрагироваться от приложения и работать с типовыми элементами.
* [Список property-based testing tools](https://gist.github.com/npryce/4147916).
* [Galen](http://galenframework.com/) - позволяет проверять вёрстку страницы. [GitHub](https://github.com/galenframework/galen). [Документация](http://galenframework.com/docs/all/).

## Сеть

* [toxyproxy](https://github.com/shopify/toxiproxy) - прокси, позволяет ограничивать скорость соединения. Есть обёртки для нескольких языков. Также позволяет запускаться как самостоятельное приложение.

## E-Mail

* [https://github.com/axllent/mailpit](https://github.com/axllent/mailpit) - pop, smtp сервер для тестирования.

## Нагрузочное тестирование

* [SuperBenchmarker](https://github.com/aliostad/SuperBenchmarker) - утилита для нагрузочного тестирования на C#. Рисует графики. Отчёты.
* [Vegeta](https://github.com/tsenart/vegeta) - нагрузка на Go. Также рисует графики. [Документация](https://godoc.org/github.com/tsenart/vegeta/lib).
* [slow_cooker](https://github.com/BuoyantIO/slow_cooker) - также, написанный, на Go пакет для тестирования под заданной нагрузкой.
* [k6](https://k6.io/) - тесты пишутся на JavaScript. Сам фреймоворк написан на Go. [Документация](https://docs.k6.io/docs).
* [Predator](https://www.predator.dev) - распределённая нагрузка в докере. [Документация](https://zooz.github.io/predator/myfirsttest.html). [GitHub](https://github.com/Zooz/predator).
* [Wrk](https://github.com/wg/wrk) Нагрузочная утилита для Linux.

## Тестирование баз

[Описание OpenSource инструментов для тестирования баз.](http://qaat.ru/opensorsnye-instrumenty-dlya-testirovaniya-baz-dannyx)

## Средства управления

* [QuAck](http://testquack.com/) - свободная система написания тест-кейсов. Есть возможность написания плагинов.
* [TestProject](https://testproject.io/) - запуск тестов в облаке, хранение, совместная работа.

## Разное

* [ClusterFuzz](https://opensource.googleblog.com/2019/02/open-sourcing-clusterfuzz.html) от Google. [Github (https://github.com/google/clusterfuzz)](https://github.com/google/clusterfuzz).
* [Чит-лист функционального тестирования, памятка тестировщику](https://habr.com/ru/post/715262).
