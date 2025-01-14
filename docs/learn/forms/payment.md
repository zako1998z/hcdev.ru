---
description: Повышение конверсии за счет создания более совершенных форм оплаты.
icon: material/hand-coin-outline
---

# Формы оплаты

<big>Повышение конверсии за счет создания более совершенных форм оплаты.</big>

!!!note ""

    Этот модуль посвящен формам оплаты и не объясняет, как реализовать транзакции на вашем сайте. Вы можете добавить платежную функциональность, реализовав [Web Payments](https://web.dev/explore/payments) или используя стороннюю платежную платформу.

Форма оплаты часто является последним шагом перед совершением покупки. Чтобы максимально увеличить конверсию, убедитесь, что форма оплаты удобна для пользователя и безопасна.

<iframe loading="lazy" src="https://codepen.io/web-dot-dev/embed/0f0da240784a36da7fa958018af29f3f?height=500&amp;theme-id=light&amp;default-tab=result&amp;editable=true" style="height: 500px; width: 100%; border: 0;"></iframe>

## Убедитесь, что пользователи знают, что нужно заполнять

Максимально упростите форму оплаты, отображая только обязательные поля.

!!!note ""

    Нет необходимости добавлять селектор для типа карты - он автоматически вычисляется платежным процессором на основе номера карты. Однако, возможно, вы захотите расширить поле номера карты, указав тип карты на основе введенного номера. Для проверки типа карты можно использовать [regex](https://gist.github.com/michaelkeevildown/9096cd3aac9029c4e6e05588448a8841), а рядом с номером карты `<input>` показать логотип бренда.

Укажите сумму платежа. Для этого идеально подходит кнопка **Submit**.

```html
<button>Pay $300.00</button>
```

Используйте для элементов `<label>` формулировки, не требующие пояснений. Например, используйте "Код безопасности", а не аббревиатуру типа "CVV", которая используется только некоторыми брендами.

!!!note ""

    Используйте один элемент `<input>` для каждого из полей имени и номера карты. Держите пользователя в режиме набора текста и не тратьте его время, заставляя переходить между несколькими полями имени или номера карты.

## Помогите пользователям ввести платежные реквизиты

Чтобы увеличить конверсию, позаботьтесь о том, чтобы пользователи могли заполнить платежную форму как можно быстрее.

Используйте `inputmode="numeric"` для полей номера карты и кода безопасности, чтобы отобразить оптимизированную экранную клавиатуру для ввода цифр.

!!!warning ""

    Используйте `type="number"` только для инкрементных полей, например, количества товара. Браузеры показывают стрелку вверх/вниз для `type="number"`, что не имеет смысла для номеров платежных карт.

Добавьте соответствующие значения `autocomplete` для элементов управления платежной формы, чтобы браузеры обеспечивали автозаполнение. Используйте `autocomplete="cc-name"` для имени, `autocomplete="cc-number"` для номера карты и `autocomplete="cc-exp"` для даты истечения срока действия.

!!!note ""

    Помочь пользователям заполнить правильный формат даты истечения срока действия можно с помощью [маски ввода](https://css-tricks.com/input-masking/). Чтобы убедиться в доступности ввода, протестируйте его на реальных пользователях, используя только клавиатуру и программу чтения с экрана, например [VoiceOver](https://www.youtube.com/watch?v=5R-6WvAihms&list=PLNYkxOF6rcICWx0C9LVWWVqvHlYJyqw7g&index=6) на Mac или [NVDA](https://www.nvaccess.org/) на Windows.

## Убедитесь, что пользователи вводят данные в правильном формате

Используйте атрибут `required` для каждого `<input>`, чтобы пользователи заполняли форму полностью.

Коды безопасности платежных карт могут состоять из трех или четырех цифр. Используйте `minlength="3"` и `maxlength="4"`, чтобы разрешить ввод только трех и четырех цифр.

Убедитесь, что пользователи вводят только цифры для номера карты и кода безопасности. Используйте `pattern="[0-9 ]+"`, чтобы разрешить пользователям включать пробелы при вводе номера карты, поскольку именно так они отображаются на физических картах.

!!!note ""

    Бренды платежных карт используют различные форматы, например, для номеров карт и кодов безопасности. Всегда тестируйте свою платежную форму с каждым поддерживаемым типом карт. Убедитесь, что правила валидации учитывают все возможные форматы.

## Ресурсы

-   [Лучшие практики использования платежных и адресных форм](https://web.dev/articles/payment-and-address-form-best-practices).
-   [Платежные веб-формы](https://web.dev/explore/payments).

:material-information-outline: Источник &mdash; [Payment forms](https://web.dev/learn/forms/payment)
