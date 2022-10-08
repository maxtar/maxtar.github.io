---
title: "Firefox"
date: 2022-10-09T01:25:11+03:00
tags: [администрирование, firefox]
---

В этом разделе собраны разные настройки Mozilla Firefox.

{{< toc >}}

## Чтобы новые вкладки открывались в конце

1. Открываем Firefox
2. В адресной строке пишем: `about:config`
3. Соглашаемся, что будем осторожны.
4. Вводим в строке поиска: `browser.tabs.insertRelatedAfterCurrent`
5. Устанавливаем `false`.

---

## Отключение прокрутки вкладок

Чтобы отключить прокрутку, для начала необходимо найти, где находится профайл пользователя.

* В Windows: `%APPDATA%\Mozilla\Firefox\Profiles\<user_profile>`.
* В Linux: `~/.mozilla/firefox/<user_profile>`.

Более подробная информация: [Profile_folder](http://kb.mozillazine.org/Profile_folder).
В каталоге профайла пользователя создать каталог `chrome`, если он не существует.
В нём создать файл `userChrome.css` (для linux регистр важен!) со следующим содержимым:

```css
@namespace url(http://www.mozilla.org/keymaster/gatekeeper/there.is.only.xul);
.tabbrowser-tab[fadein]:not([pinned]) {
min-width: 16px !important;
}
```

Перезапустить firefox, если запущен.
Дополнительная информация: [userChrome.css](http://kb.mozillazine.org/index.php?title=UserChrome.css).
В версиях, начиная с 69 возможно надо будет установить `toolkit.legacyUserProfileCustomizations.stylesheets` в `true`.

---

## Проблемы при воспроизведении видео

Иногда, вместо видео, может появляться сообщение "видео в поддерживаемом формате и типе mime не найдено". В таком случае нужно обратить на параметр `media.mediasource.enabled` в настройках Firefox.
Открываем `about:config` и там ищем параметр `media.mediasource.enabled`. В новых версиях Firefox (на момент написания этой заметки была актуальна версия 53.0.3) значение параметра равно `true`. Возможно нужно поменять его на `false`.

---

## Чтобы закладки всегда открывались в новой вкладке

В `about:config` найти настройку `browser.tabs.loadBookmarksInTabs` и установить у неё значение `true`.

---

## Указание директории для кеша

В `about:config` создать свойство `browser.cache.disk.parent_directory` и в нём указать путь до директории, где должен находится кеш страниц.

---

## Чтобы грузились локальные ресурсы

В `about:config` свойство `privacy.file_unique_origin` выставить в `true`.
