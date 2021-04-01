---
description: Модификатор !important играет роль в том случае, когда пользователи подключают свою собственную таблицу стилей, также применяется для повышения специфичности стилевого правила
---

# !important

Модификатор **`!important`** играет роль в том случае, когда пользователи подключают свою собственную таблицу стилей, также применяется для повышения специфичности стилевого правила. Если возникает противоречие, когда стиль автора страницы и пользователя для одного и того же элемента не совпадает, то `!important` позволяет повысить приоритет стиля.

При использовании пользовательской таблицы стилей или одновременном применении разного стиля автора и пользователя к одному и тому же селектору, браузер руководствуется следующим алгоритмом.

- `!important` добавлен в авторский стиль — будет применяться стиль автора.
- `!important` добавлен в пользовательский стиль — будет применяться стиль пользователя.
- `!important` нет как в авторском стиле, так и стиле пользователя — будет применяться стиль автора.
- `!important` содержится в авторском стиле и стиле пользователя — будет применяться стиль пользователя.

## Синтаксис

```
Свойство: <значение> !important
```

## Спецификации

- [CSS Level 3](http://www.w3.org/TR/css-cascade-3/#importance)
- [CSS Level 2 (Revision 1)](http://www.w3.org/TR/CSS21/cascade.html#important-rules)
- [CSS Level 2](http://www.w3.org/TR/CSS2/cascade.html#important-rules)

## Описание и примеры

```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8" />
    <title>important</title>
    <style>
      p {
        background: url(/example/image/tune1.png) no-repeat !important;
        min-height: 112px; /* Минимальная высота */
        padding-left: 65px; /* Поле слева от текста */
      }
      p {
        background: url(/example/image/tune2.png) no-repeat;
      }
    </style>
  </head>
  <body>
    <p>
      Минорная пентатоника с пониженной V ступенью также
      называется блюзовой пентатоникой.
    </p>
  </body>
</html>
```

В данном примере для одного селектора задается одно и то же свойство с разными значениями. Но поскольку к первому селектору добавляется `!important`, то его стиль и будет применяться на странице.

### Примечание

При добавлении `!important` к значению стилевого свойства его важность повышается. Если переопределить значение того же свойства без `!important`, оно будет игнорироваться браузерами.