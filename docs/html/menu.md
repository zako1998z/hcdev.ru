---
description: Описание тега menu
---

# &lt;menu&gt;

HTML-элемент **`<menu>`** представляет группу команд, которые пользователь может выполнить или активировать. Он включает как меню-списки, которые могут отображаться в верхней части экрана, так и контекстные меню, например, такие, что могут появиться под кнопкой после нажатия.

## Атрибуты

К этому элементу применимы [глобальные атрибуты](./uni-attr.md).

### `label`

Название меню, отображаемое пользователю. Используется во вложенных меню для указания метки, через которую можно получить доступ к подменю. Должно быть указано только в том случае, если родительским элементом является `<menu>` в состоянии контекстного меню.

### `type`

Этот атрибут указывает на тип объявляемого меню и может иметь одно из двух значений.

-   `context` Устарело: Указывает на состояние всплывающего меню, которое представляет собой группу команд, активизируемых через другой элемент. Это может быть меню кнопки, на которое ссылается атрибут menu элемента `<button>`, или контекстное меню для элемента с атрибутом contextmenu (en-US). Это значение используется по умолчанию, если атрибут отсутствует, а родительский элемент также является элементом `<menu>`.

-   `toolbar`: Указывает на состояние панели инструментов, которая представляет собой панель инструментов, состоящую из ряда команд для взаимодействия с пользователем. Это может быть неупорядоченный список элементов `<li>` или, если элемент не имеет дочерних элементов `<li>`, потоковое содержимое, описывающее доступные команды. Это значение используется по умолчанию, если атрибут отсутствует.

## Спецификации

-   [HTML Living Standard](https://html.spec.whatwg.org/multipage/grouping-content.html#the-menu-element)
-   [HTML 5.1](https://www.w3.org/TR/html51/interactive-elements.html#the-menu-element)
