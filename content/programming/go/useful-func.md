---
title: "Полезные функции"
date: 2022-10-05T01:32:25+03:00
tags: [go, программирование]
---

{{< toc >}}

## Перехват Ctrl+C

Информация взята из блога [Mat Ryer](https://medium.com/@matryer/make-ctrl-c-cancel-the-context-context-bd006a8ad6ff).

```go
func main() {
    ctx := context.Background()

    // trap Ctrl#C and call cancel on the context
    ctx, cancel := context.WithCancel(ctx)
    c := make(chan os.Signal, 1)
    signal.Notify(c, os.Interrupt)
    defer func() {
        signal.Stop(c)
        cancel()
    }()
    go func() {
        select {
        case <-c:
            cancel()
        case <-ctx.Done():
        }
    }()

    doSomethingAwesome(ctx)
}
```

### Более простой вариант

```go
func main() {
    c := make(chan os.Signal, 1)
    signal.Notify(c, os.Interrupt)
// Wait for Ctrl#C
    <-c
}
```

------

## Как правильно реализовать Singletone

Вариант взят отсюда [singleton-pattern-in-go](http://marcio.io/2015/07/singleton-pattern-in-go/).

```go
package singleton

import (
    "sync"
)

type singleton struct {
}

var instance *singleton
var once sync.Once

func GetInstance() *singleton {
    once.Do(func() {
        instance = &singleton{}
    })
    return instance
}
```

------

## Ожидание нажатия Enter в консоли

```go
func main() {
    fmt.Println("Press Enter...")
    bufio.NewReader(os.Stdin).ReadLine()
    fmt.Println("Exit")
}
```

------

## Логирование из тестов

Чтобы вывести произвольную информацию из теста Go можно использовать метод `testing.T.Logf()`.
Чтобы информация из него выводилась в консоль при запуске теста необходимо запускать тесты с ключом **-v**:

```go
go test -v
```

------

## Создание собственного типа аргумента командной строки

Допустим, хотим заполнить тип `time.Time` на основании значения, принятого из командной строки.
Чтобы создать свой флаг необходимо имплементировать интерфейс `time.Value` имеющий следующий вид:

```go
type Value interface {
        String() string
        Set(string) error
}
```

Соответственно, нужно имплементировать эти два метода на нашей структуре.
Создаём следующую структуру.

```go
// DateTimeFlag представляет аргумент командной строки для даты.
type DateTimeFlag struct {
    time.Time
}

func (dtf *DateTimeFlag) String() string {
    return fmt.Sprint(*dtf)
}

// Set вызывается в момент разбора аргумента командной строки.
func (dtf *DateTimeFlag) Set(value string) (err error) {
    dtf.Time, err = time.Parse("2006.01.02", value)
    return
}
```

В данном конкретно случае, так как у нас в структуре анонимный тип `time.Time` уже имплементирует метод `String()`, то его можно пропустить.

Чтобы добавить в свою программу возможность использования данного типа делаем следующее:

* Объявить переменные созданного типа
* Добавить в секцию `init()` регистрацию этих переменных в качестве флагов.

```go
var date DateTimeFlag

func init() {
    flag.Var(&date, "date", "date from command line")
}
```

Дальнейшее использование как обычно:

```go
flag.Parse()
```

после чего, в случае корректно переданного параметра переменная проинициализируется соответствующим значением.
Единственное отличие в использовании от встроенных типов данных в том, что обращаться к переменной надо напрямую, а не по ссылке.

```go
// Правильно
fmt.Println(date)
// Неправильно
fmt.Println(*date)
```

------

## Удаление элемента из slice

Информация взята из [SliceTricks](https://github.com/golang/go/wiki/SliceTricks).

```go
a = append(a[:i], a[i+1:]...)
```

------

## Подключение к Microsoft IIS по SSL

В случае ошибки подключения по ssl `local error: tls: no renegotiation`.
Необходимо настроить транспорт следующим образом:

```go
transport := &http.Transport{
        TLSClientConfig: &tls.Config{
            Certificates: []tls.Certificate{cert},
            RootCAs:       caCertPool, // Если надо. Инициализацию смотри ниже.
            Renegotiation: tls.RenegotiateFreelyAsClient, // Собственно этот параметр и включает совместимость.
        }}
```

И затем использовать его в HTTP-клиенте:

```go
client := http.Client{Transport: transport}
```

При этом загрузка корневых сертификатов (при необходимости) происходит следующим образом:

```go
caCert, err := ioutil.ReadFile("<path_to_ca.pem>")
if err != nil {
    log.Fatalf("Error read ca certs: %v", err)
}
caCertPool := x509.NewCertPool()
caCertPool.AppendCertsFromPEM(caCert)
```

------

## Вычисление абсолютного значения целых чисел

```go
func absInt32(n int32) int32 {
    y := n >> 31
    return (n ^ y) - y
}
```

```go
func absInt64(n int64) int64 {
    y := n >> 63
    return (n ^ y) - y
}
```
