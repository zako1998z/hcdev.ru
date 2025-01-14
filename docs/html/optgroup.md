---
description: Тег optgroup (от англ. option group — группа параметров) представляет собой контейнер, внутри которого располагаются элементы option, объединённые в одну группу
---

# &lt;optgroup&gt;

Тег **`<optgroup>`** _(от англ. **opt**ion **group** — группа параметров)_ представляет собой контейнер, внутри которого располагаются элементы [`<option>`](option.md), объединённые в одну группу.

Особенностью `<optgroup>` является то, что он не выделяется как обычный элемент списка, акцентируется с помощью жирного начертания, а все элементы, входящие в этот контейнер, смещаются вправо от своего исходного положения.

## Демо

<iframe class="interactive is-tabbed-standard-height" height="200" src="https://interactive-examples.mdn.mozilla.net/pages/tabbed/optgroup.html" title="MDN Web Docs Interactive Example" loading="lazy" data-readystate="complete"></iframe>

??? info "Формы"

    <div class="col4" markdown="1">

    - [button](button.md)
    - [datalist](datalist.md)
    - [fieldset](fieldset.md)
    - [form](form.md)
    - [input](input.md)
    - [label](label.md)
    - [legend](legend.md)
    - [meter](meter.md)
    - **optgroup**
    - [option](option.md)
    - [output](output.md)
    - [progress](progress.md)
    - [select](select.md)
    - [textarea](textarea.md)

    </div>

## Синтаксис

```html
<select>
    <optgroup label="<текст>">
        <option>...</option>
    </optgroup>
</select>
```

Закрывающий тег обязателен.

## Атрибуты

[`disabled`](#disabled)

: Блокирует доступ к группе списка.

[`label`](#label)

: Текст, который будет входить в список в виде заголовка группы.

Также для этого элемента доступны [универсальные атрибуты](uni-attr.md).

### disabled

Блокирует доступ к группе списка, при этом группа отображается другим цветом (обычно серым) и не доступна для выбора.

**Синтаксис**

```html
<optgroup disabled>...</optgroup>
```

**Значения**

Нет.

**Значение по умолчанию**

По умолчанию этот атрибут выключен.

### label

Текст, который будет входить в список в виде заголовка группы. Это обычная текстовая строка без всяких кодов HTML.

**Синтаксис**

```html
<optgroup label="<текст>">...</optgroup>
```

**Значения**

Любая текстовая строка.

**Значение по умолчанию**

Нет.

## Спецификации

-   [WHATWG HTML Living Standard](https://html.spec.whatwg.org/multipage/forms.html#the-optgroup-element)
-   [HTML 5](http://www.w3.org/TR/html5/forms.html#the-optgroup-element)
-   [HTML 4.01 Specification](http://www.w3.org/TR/html401/interact/forms.html#h-17.6)

## Описание и примеры

```html
<!doctype html>
<html>
    <head>
        <meta charset="utf-8" />
        <title>OPTGROUP</title>
    </head>
    <body>
        <form action="handler.php">
            <p>
                <select>
                    <optgroup label="Цвет">
                        <option value="c1">
                            Апельсиновый
                        </option>
                        <option value="c2">Лимонный</option>
                        <option value="c3">
                            Персиковый
                        </option>
                    </optgroup>
                    <optgroup label="Тон">
                        <option value="s1">Светлый</option>
                        <option value="s2">
                            Нормальный
                        </option>
                        <option value="s3">Темный</option>
                    </optgroup>
                </select>
            </p>
            <p>
                <input type="submit" value="Отправить" />
            </p>
        </form>
    </body>
</html>
```

## Ссылки

-   Тег [`<optgroup>`](https://developer.mozilla.org/ru/docs/Web/HTML/Element/optgroup) <sup><small>MDN (рус.)</small></sup>
