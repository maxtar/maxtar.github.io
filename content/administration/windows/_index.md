---
title: "Windows"
date: 2022-10-09T14:54:20+03:00
tags: [администрирование, windows]
---

Различная информация по Windows.

{{< toc >}}

## Просмотр IP с которого было подключение по RDP

Открыть системную оснастку ***Просмотр событий/Event viewer***. Далее открыть ***Журналы приложений и служб/Microsoft/TerminalServices-RemoteConnectionManager/Operational*** (***Applications and Services Logs/Microsoft/TerminalServices-RemoteConnectionManager/Operational***).
В списке нужно найти запись с `EventID=1149` за требуемое время.
В этом событие будет информация типа:

```txt
Remote Desktop Services: User authentication succeeded:

User: <user>
Domain: <domain>
Source Network Address: 50.24.123.168
```

---

## Просмотр доменных групп, в которых состоит пользователь

```cmd
gpresult /USER <domen>\<user> /V
```

## Как собрать дампы памяти

TODO: добавить небольшое описание со страницы [WER Settings](https://msdn.microsoft.com/en-us/library/windows/desktop/bb513638(v=vs.85).aspx)

[Различные способы собрать дампы памяти в Windows](https://blogs.msdn.microsoft.com/cobold/2010/03/01/collecting-crash-dumps)
