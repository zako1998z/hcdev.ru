---
description: Сделать заполнение форм более удобным для пользователей.
icon: material/auto-fix
---

# Помогите избежать повторного ввода данных

<big>Сделать заполнение форм более удобным для пользователей.</big>

После изучения элемента [форма](form-element.md) и способов создания [интерактивной формы](form-fields.md) давайте посмотрим, как можно помочь пользователям избежать повторного ввода данных.

## Используйте автозаполнение по максимуму

Заполнение форм может отнимать много времени. Например, повторное введение адреса на каждом сайте, где вы хотите что-то купить, - не лучший способ совершения покупок.

Здесь вам поможет автозаполнение. Вы вводите свой адрес один раз. С этого момента браузер предложит вам возможность автоматически вводить тот же адрес в другие формы.

Вы переехали в другой город? Не беспокойтесь о том, что старый адрес навсегда останется в качестве опции. Вы можете отредактировать сохраненные браузером адресные данные, чтобы сохранить их в актуальном состоянии.

!!!note ""

    Браузеры также помогают запоминать данные. Вы регистрируетесь на каком-либо сайте. В поле для ввода пароля вам предлагается сгенерировать и сохранить надежный пароль. Если впоследствии вы захотите войти на тот же сайт, браузер предложит вам ввести сохраненный пароль.

## Как работает автозаполнение в браузере?

На разных сайтах адресное поле может выглядеть совершенно по-разному. Как браузер определяет, что это поле адреса?

Браузеры используют эвристику для идентификации адресного поля. Каковы значения атрибутов `name`, `type` и `id`? Присутствует ли на элементе управления формы атрибут [`автозаполнение`](auto.md#autocomplete)?

На основе этой информации браузеры могут предложить возможность автозаполнения поля ранее введенными данными того же типа. Браузеры могут даже предложить автозаполнение всей формы.

## Помощь браузерам с автозаполнением

Давайте посмотрим, что можно сделать, чтобы браузеры предлагали правильные варианты автозаполнения.

### Используйте разумные значения атрибутов

Как вы уже узнали, браузеры могут определять тип данных, глядя на атрибуты элемента управления формы.

```html
<label for="email">Email</label>
<input type="email" name="email" id="email" />
```

У вас есть поле, в которое пользователи должны вводить свой адрес электронной почты? Используйте `email` в качестве значения для атрибутов `name`, `id` и `type`. Три подсказки браузеру, что это поле электронной почты.

### Атрибут автозаполнения {: #autocomplete}

Существуют и другие примеры, в которых браузеру может быть сложно определить тип данных только по атрибутам `name`, `id` и `type`. Здесь можно помочь, используя атрибут `autocomplete`.

<iframe src="https://codepen.io/web-dot-dev/embed/9a2262c52b978968f6ce181f32357f31?height=300&amp;theme-id=light&amp;default-tab=html%2Cresult&amp;editable=true" style="height: 400px; width: 100%; border: 0;" loading="lazy"></iframe>

Вводили ли вы ранее имя в используемом браузере? Вероятно, в демонстрационном примере браузер предложит вам ввести его снова для этого поля.

Подробнее об использовании [autocomplete и autofill](autofill.md) вы можете узнать в одном из следующих модулей.

## Ресурсы

-   [Атрибут автозаполнения](https://developer.mozilla.org/docs/Web/HTML/Attributes/autocomplete)
-   [Автозаполнение: что должны знать веб-разработчики, но не знают](https://cloudfour.com/thinks/autofill-what-web-devs-should-know-but-dont)

:material-information-outline: Источник &mdash; [Help users avoid re-entering data in forms](https://web.dev/learn/forms/auto/)