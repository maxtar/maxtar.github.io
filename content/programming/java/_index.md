---
title: "Java"
date: 2022-10-02T22:18:04+03:00
tags: [java,программирование]
---

Информация о Java, примеры использования и библиотеки

{{< toc >}}

## JVM

* [Liberica](https://bell-sw.com/pages/products/) - сборка openjdk от BellSoft. Принимают участие в развитии openjdk и вообще всячески лицензированы oracle.
* [GraalVM](https://www.graalvm.org/) - позволяет запускать не только java, но и JavaScript, Python, Ruby, R, C, C++.
* [AdoptOpenJDK](https://adoptopenjdk.net/) - ещё одна сборка openjdk. Также есть реализация Openj9 вирутальной машины.

## Быстрая памятка по настройке логирования в Java

Для добавления логирования в проект надо добавить следующие зависимости:

```gradle
implementation("org.slf4j:slf4j-api:1.7.32") //Поменять на актуальную версию
implementation("ch.qos.logback:logback-classic:1.2.6") //Поменять на актуальную версию
```

В classpath (например в `src/main/resources`) надо добавить файл *logback.xml* со следующим содержимым:

```xml
<?xml version="1.0" encoding="UTF-8"?>
<configuration>
    <appender name="STDOUT" class="ch.qos.logback.core.ConsoleAppender">
        <encoder>
            <pattern>%d{HH:mm:ss.SSS} [%thread] %-5level %logger{36} - %msg%n</pattern>
        </encoder>
    </appender>

    <root level="DEBUG">
        <appender-ref ref="STDOUT"/>
    </root>

    <!-- Следующий логер нужен для исключения сообщений от этого класса в лог -->
    <logger name="org.needed.class" level="OFF"/>
</configuration>
```

В Java используется следующий код для получения logger:

```java
Logger logger = LoggerFactory.getLogger("<Нужный класс>");
```
