---
description: Тег meta (от англ. meta information — мета информация) определяет данные (они называются ещё метатеги), которые используются для хранения информации, предназначенной для браузеров и поисковых систем
---

# &lt;meta&gt;

Тег **`<meta>`** _(от англ. **meta** information — мета информация)_ определяет данные (они называются ещё метатеги), которые используются для хранения информации, предназначенной для браузеров и поисковых систем.

Например, механизмы поисковых систем обращаются к метатегам для получения описания сайта, ключевых слов и других данных. Разрешается использовать более чем один метатег, все они размещаются в контейнере [`<head>`](head.md). Как правило, атрибуты любого метатега сводятся к парам «`имя=значение`», имена которых определяются ключевыми словами `content`, `name` или `http-equiv`.

??? info "Метаданные документа"

    <div class="col4" markdown="1">

    - [base](base.md)
    - [link](link.md)
    - **meta**
    - [style](style.md)
    - [title](title.md)

    </div>

## Синтаксис

```html
<head>
    <meta />
</head>
```

Закрывающий тег не требуется.

## Атрибуты

[`charset`](#charset)

: Задаёт кодировку документа.

[`content`](#content)

: Устанавливает значение атрибута, заданного с помощью `name` или `http-equiv`.

[`http-equiv`](#http-equiv)

: Предназначен для конвертирования метатега в заголовок HTTP.

[`name`](#name)

: Имя метатега, также косвенно устанавливает его предназначение.

### charset

Указывает кодировку документа. Атрибут введён в HTML5 и предназначен для сокращения формы `<meta>`, которая задавала кодировку в предыдущих версиях HTML и XHTML.

**Синтаксис**

```html
<meta charset="<кодировка>" />
```

**Значения**

Название кодировки, например UTF-8.

**Значение по умолчанию**

Нет.

### content

`content` устанавливает значение атрибута, заданного с помощью `name` или `http-equiv`. Атрибут `content` может содержать более одного значения, в этом случае они разделяются запятыми или точкой с запятой.

Некоторые значения атрибута `content` для `<meta name="robots">`, предназначенных для поисковых роботов, приведены в табл. 1.

<table>
<caption>Табл. 1. Значения для <code>meta name="robots"</code></caption>
<tr><th>Значение</th><th>Описание</th></tr>
<tr><td><code>index</code></td><td>Разрешает роботу индексировать данную страницу.</td></tr>
<tr><td><code>noindex</code></td><td>Запрещает роботу индексировать текущую страницу. Она не попадает в базу поисковика и её невозможно будет найти через поисковую систему.</td></tr>
<tr><td><code>follow</code></td><td>Разрешает роботу переходить по ссылкам на данной странице.</td></tr>
<tr><td><code>nofollow</code></td><td>Запрещает роботу переходить по ссылкам на данной странице. При этом всем ссылкам не передаётся ТИЦ (тематический индекс цитирования) и PagePank.</td></tr>
<tr><td><code>noarchive</code></td><td>Запрещает роботу кэшировать данную страницу.</td></tr>
</table>

Допустимые значения атрибута `content` для `<meta name="viewport">`, которые предназначены для управления просмотром сайта на мобильных устройствах, приведены в табл. 2.

<table class="table">
<caption>Табл. 2. Значения для <code>meta name="viewport"</code></caption>
<tr><th>Значение</th><th>Допустимые значения</th><th>Описание</th></tr>
<tr><td><code>width</code></td><td>device-width или целое положительное число</td><td>Устанавливает ширину области просмотра в пикселях.</td></tr>
<tr><td><code>height</code></td><td>device-height или целое положительное число</td><td>Устанавливает высоту области просмотра в пикселях.</td></tr>
<tr><td><code>initial-scale</code></td><td>Число от 0.0 до 10.0</td><td>Устанавливает соотношение между шириной устройства (device-width в портретном режиме или device-height в ландшафтном режиме) и размером области просмотра.</td></tr>
<tr><td><code>maximum-scale</code></td><td>Число от 0.0 до 10.0</td><td>Задаёт максимальное значение масштаба. Должно быть больше или равно minimum-scale, в противном случае игнорируется.</td></tr>
<tr><td><code>minimum-scale</code></td><td>Число от 0.0 до 10.0</td><td>Задаёт минимальное значение масштаба. Должно быть меньше или равно maximum-scale, в противном случае игнорируется.</td></tr>
<tr><td><code>user-scalable</code></td><td>yes или no</td><td>Если указано no, то пользователь не сможет масштабировать веб-страницу. По умолчанию используется yes.</td></tr>
</table>

**Синтаксис**

```html
<meta content="..." />
```

**Значения**

Строка символов, которую надо взять в одинарные или двойные кавычки.

**Значение по умолчанию**

Нет.

### http-equiv

Браузеры преобразовывают значение атрибута `http-equiv`, заданное с помощью `content`, в формат заголовка ответа HTTP и обрабатывают их, как будто они прибыли непосредственно от сервера.

**Синтаксис**

```html
<meta http-equiv="<значение>" />
```

**Значения**

Любой подходящий идентификатор. Ниже приведены некоторые допустимые значения атрибута `http-equiv`.

`Content-Type`

: Тип кодировки документа.

`expires`

: Устанавливает дату и время, после которой информация в документе будет считаться устаревшей.

`pragma`

: Способ кэширования документа.

`refresh`

: Загружает другой документ в текущее окно браузера.

**Значение по умолчанию**

Нет.

### name

Устанавливает идентификатор метатега для пары «`имя=значение`». Одновременно использовать атрибуты `name` и `http-equiv` не допускается.

**Синтаксис**

```html
<meta name="<значение>" />
```

**Значения**

Любой подходящий идентификатор. Ниже приведены некоторые допустимые значения атрибута `name`.

`author`

: Имя автора документа.

`description`

: Описание текущего документа.

`keywords`

: Список ключевых слов, встречающихся на странице.

`viewport`

: Управляет просмотром сайта на мобильных устройствах.

**Значение по умолчанию**

Нет.

## Спецификации

-   [Referrer Policy](https://w3c.github.io/webappsec-referrer-policy/#referrer-policy-delivery-meta)
-   [HTML Living Standard](https://html.spec.whatwg.org/multipage/semantics.html#the-meta-element)
-   [HTML 5](http://www.w3.org/TR/html5/document-metadata.html#the-meta-element)
-   [HTML 4.01 Specification](http://www.w3.org/TR/html401/struct/global.html#h-7.4.4.2)

## Описание и примеры

```html
<!doctype html>
<html>
    <head>
        <title>META</title>
        <meta charset="utf-8" />
        <meta
            name="GENERATOR"
            content="Microsoft FrontPage 4.0"
        />
        <meta
            name="ProgId"
            content="FrontPage.Editor.Document"
        />
    </head>
    <body>
        <p>...</p>
    </body>
</html>
```

## Ссылки

-   Тег [`<meta>`](https://developer.mozilla.org/ru/docs/Web/HTML/Element/meta) <sup><small>MDN (рус.)</small></sup>
