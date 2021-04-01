---
description: Свойство z-index определяет положение элемента и нижестоящих элементов по оси z
---

# z-index

Свойство **`z-index`** определяет положение элемента и нижестоящих элементов по оси z. В случае перекрытия элементов, это значение определяет порядок наложения. В общем случае, элементы с большим `z-index` перекрывают элементы с меньшим.

Для позиционируемого контейнера свойство `z-index` определяет:

- порядок наложения в текущем контексте наложения;
- создаёт ли контейнер локальный контекст наложения.

??? info "Позиционирование"

    <div class="col3" markdown="1">

    - [bottom](bottom.md)
    - [clear](clear.md)
    - [display](display.md)
    - [float](float.md)
    - [left](left.md)
    - [position](position.md)
    - [right](right.md)
    - [top](top.md)
    - **z-index**

    </div>

## Синтаксис

```css
/* Значение - ключевое слово */
z-index: auto;

/* <целочисленные> значения */
z-index: 0;
z-index: 3;
z-index: 289;
z-index: -1; /* Отрицательные значения понижают приоритет */

/* Глобальные значения */
z-index: inherit;
z-index: initial;
z-index: unset;
```

## Значения

В качестве значения используются целые числа (положительные, отрицательные и ноль). Чем больше значение, тем выше находится элемент по сравнению с теми элементами, у которых оно меньше. При равном значении `z-index`, на переднем плане находится тот элемент, который в коде HTML описан ниже. Допустимо использовать отрицательное значение.

Кроме числовых значений применяется `auto` — порядок элементов в этом случае строится автоматически, исходя из их положения в коде HTML и принадлежности к родителю, поскольку дочерние элементы имеют тот же номер, что их родительский элемент.

`auto`
: Контейнер не будет создавать локального контекста наложения. Уровень контейнера в текущем контексте наложения такой же, как и у родительского.

`<integer>`
: Целое число определяет уровень контейнера в текущем контексте наложения. Контейнер также будет создавать локальный контекст наложения, в котором его собственный уровень будет равен `0`. Это значит, что значения `z-index` нижестоящих элементов не будут сравниваться с z-индексами элементов вне этого контейнера.

Значение по-умолчанию: `auto`

Применяется к позиционированным элементам

## Спецификации

- [CSS Level 2 (Revision 1)](http://www.w3.org/TR/CSS2/visuren.html#z-index)

## Пример

```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8" />
    <title>Порядок карт</title>
    <style>
      .card {
        position: relative;
      }
      .three {
        top: 50px;
        left: 55px;
        z-index: 5;
      }
      .seven {
        left: -120px;
        top: 25px;
        z-index: 2;
      }
      .ace {
        left: -295px;
        z-index: 1;
      }
      .card:hover {
        z-index: 10;
      }
    </style>
  </head>
  <body>
    <img src="image/3.png" alt="3" class="card three" />
    <img src="image/7.png" alt="7" class="card seven" />
    <img src="image/ace.png" alt="Туз" class="card ace" />
  </body>
</html>
```