---
description: Тег meter (от англ. meter — счетчик, измеритель) используется для вывода значения в некотором известном диапазоне
---

# &lt;meter&gt;

Тег **`<meter>`** _(от англ. **meter** — счетчик, измеритель)_ используется для вывода значения в некотором известном диапазоне.

Применяется преимущественно для отображения числовых значений, например, количества результатов поиска, объёма жидкости, давления и др.

Браузеры, которые поддерживают элемент `<meter>`, отображают значение в виде рисунка, на котором цветом помечается текущее значение в указанном диапазоне. Остальные браузеры выводят текст, написанный внутри `<meter>`.

## Демо

<iframe class="interactive is-tabbed-shorter-height" height="200" src="https://interactive-examples.mdn.mozilla.net/pages/tabbed/meter.html" title="MDN Web Docs Interactive Example" loading="lazy" data-readystate="complete"></iframe>

??? info "Формы"

    <div class="col4" markdown="1">

    - [button](button.md)
    - [datalist](datalist.md)
    - [fieldset](fieldset.md)
    - [form](form.md)
    - [input](input.md)
    - [label](label.md)
    - [legend](legend.md)
    - **meter**
    - [optgroup](optgroup.md)
    - [option](option.md)
    - [output](output.md)
    - [progress](progress.md)
    - [select](select.md)
    - [textarea](textarea.md)

    </div>

## Поддержка браузерами

<p class="ciu_embed" data-feature="meter" data-periods="future_1,current,past_1,past_2">
<a href="http://caniuse.com/#feat=meter">Can I Use meter?</a> Data on support for the meter feature across the major browsers from caniuse.com.
</p>

Полифилы для включения поддержки:

-   [`<meter>` polyfills](https://github.com/Modernizr/Modernizr/wiki/HTML5-Cross-Browser-Polyfills#meter)

## Синтаксис

```html
<meter value="<число>">текст</meter>
```

Закрывающий тег обязателен.

## Атрибуты

[`value`](#value)

: Устанавливает значение.

[`min`](#min)

: Задаёт минимально возможное значение.

[`max`](#max)

: Задаёт максимально возможное значение.

[`low`](#low)

: Определяет предел, при достижении которого значение считается низким.

[`high`](#high)

: Определяет предел, при достижении которого значение считается высоким.

[`optimum`](#optimum)

: Определяет наилучшее или оптимальное значение.

### value

Устанавливает значение единицы измерения. Значение должно быть в диапазоне, задаваемым атрибутами `min` и `max`.

**Синтаксис**

```html
<meter value="<число>"></meter>
```

**Значения**

В качестве значения указывается целое или дробное число. Допускается использование отрицательных значений.

**Значение по умолчанию**

Нет.

### min

Задаёт минимальный порог, который может достигать значение.

**Синтаксис**

```html
<meter value="<число>" min="<минимальное число>"></meter>
```

**Значения**

В качестве значения указывается целое или дробное число. Обязательно должно соблюдаться условие `min` ≤ `value` ≤ `max`.

**Значение по умолчанию**

`0`

### max

Задаёт максимальный порог, который может достигать значение.

**Синтаксис**

```html
<meter value="<число>" max="<число>"></meter>
```

**Значения**

В качестве значения указывается целое или дробное число. Обязательно должно соблюдаться условие `min` ≤ `value` ≤ `max`.

**Значение по умолчанию**

`1`

### low

Определяет предел, при достижении которого значение считается низким.

**Синтаксис**

```html
<meter value="<число>" low="<число>"></meter>
```

**Значения**

В качестве значения указывается целое или дробное число. Обязательно должно соблюдаться условие `min` ≤ `low` ≤ `max`, а также `low` ≤ `high`.

**Значение по умолчанию**

Нет.

### high

Определяет предел, при достижении которого значение считается высоким.

**Синтаксис**

```html
<meter value="<число>" high="<число>"></meter>
```

**Значения**

В качестве значения указывается целое или дробное число. Обязательно должно соблюдаться условие `min` ≤ `high` ≤ `max`, а также `low` ≤ `high`.

**Значение по умолчанию**

Нет.

### optimum

Определяет наилучшее или оптимальное значение.

**Синтаксис**

```html
<meter value="<число>" optimum="<число>"></meter>
```

**Значения**

В качестве значения указывается целое или дробное число. Обязательно должно соблюдаться условие `min` ≤ `optimum` ≤ `max`.

**Значение по умолчанию**

Нет.

## Спецификации

-   [HTML Living Standard](https://html.spec.whatwg.org/multipage/forms.html#the-meter-element)
-   [HTML 5](http://www.w3.org/TR/html5/forms.html#the-meter-element)

## Описание и примеры

```html
<!doctype html>
<html>
    <head>
        <meta charset="utf-8" />
        <title>meter</title>
    </head>
    <body>
        <p>Температура воды</p>
        <meter value="0" max="100" low="10" high="60">
            Низкая
        </meter>
        <meter value="30" max="100" low="10" high="60">
            Нормальная
        </meter>
        <meter value="80" max="100" low="10" high="60">
            Горячая
        </meter>
        <meter value="100" max="100">Кипяток</meter>
    </body>
</html>
```

## Ссылки

-   Тег [`<meter>`](https://developer.mozilla.org/ru/docs/Web/HTML/Element/meter) <sup><small>MDN (рус.)</small></sup>
