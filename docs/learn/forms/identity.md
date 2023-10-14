---
description: Узнайте, как построить безопасные и доступные формы регистрации и входа в систему, а также как помочь пользователям изменить настройки учетной записи.
icon: material/account
---

# Идентификация

<big>Узнайте, как построить безопасные и доступные формы регистрации и входа в систему, а также как помочь пользователям изменить настройки учетной записи.</big>

!!!warning ""

    Аутентификация учетных записей пользователей [https://cheatsheetseries.owasp.org/cheatsheets/Authentication_Cheat_Sheet.html] - сложный вопрос с точки зрения конфиденциальности и безопасности. Чтобы гарантировать безопасность учетных записей пользователей, возможно, лучше использовать [стороннего провайдера идентификации](https://web.dev/articles/sign-up-form-best-practices#federated-login), а не создавать собственную безопасную систему аутентификации.

    Подробнее о [лучших практиках аутентификации учетных записей и управления паролями](https://cloud.google.com/blog/products/identity-security/account-authentication-and-password-management-best-practices).

## Помогите пользователям при регистрации

Форма регистрации - это часто первое взаимодействие с формой на вашем сайте. Хороший дизайн формы регистрации имеет решающее значение, а безопасная форма является обязательным условием.

!!!note ""

    Требуйте регистрации только в том случае, если это действительно необходимо. Если вы хотите хранить информацию только между переходами, рассмотрите вариант [использования хранилища на стороне клиента](https://web.dev/articles/storage-for-the-web). Для форм оформления заказа по умолчанию добавьте гостевую регистрацию. Вы можете спросить новых покупателей, хотят ли они зарегистрироваться после совершения покупки или при вводе адресных данных.

Давайте рассмотрим форму регистрации и то, как можно помочь пользователям зарегистрироваться на вашем сайте.

<iframe loading="lazy" src="https://codepen.io/web-dot-dev/embed/42a33b97484873a214f8a945a3b55f71?height=450&amp;theme-id=light&amp;default-tab=result&amp;editable=true" style="height: 500px; width: 100%; border: 0;"></iframe>

Форма регистрации должна быть минимальной и отображать только необходимые элементы управления для создания учетной записи. Не стоит дублировать элементы управления формой, чтобы помочь пользователям правильно указать данные учетной записи. Вместо этого отправьте подтверждение по электронной почте.

### Помогите пользователям в заполнении учетных данных

Вы можете помочь пользователям заполнить данные учетной записи, используя соответствующий атрибут `autocomplete`. Используйте `autocomplete="email"` для поля `email` и `autocomplete="new-password"` для поля `new-password`.

Подробнее о [элементах управления вводом с автозаполнением](autofill.md).

!!!warning ""

    Не запрещайте вставку в поля паролей. Это раздражает пользователей, способствует созданию запоминающихся и менее надежных паролей, а также усложняет работу менеджеров паролей, предлагающих и автоматически заполняющих надежные пароли.

    Подробнее о том, почему всегда следует [разрешать вставку паролей](https://www.ncsc.gov.uk/blog-post/let-them-paste-passwords).

Вы также можете помочь пользователям ввести надежный пароль, предложив кнопку раскрытия пароля `<button>`. Подробнее о шаблоне [reveal-password](javascript.md#ensure-users-can-see-the-password-they-entered).

### Обеспечьте безопасность формы регистрации

Никогда не храните и не передавайте пароли в виде обычного текста. Обязательно используйте [соль и хеширование](https://cheatsheetseries.owasp.org/cheatsheets/Password_Storage_Cheat_Sheet.html#Use_a_cryptographically_strong_credential-specific_salt) паролей - и [не пытайтесь изобрести свой собственный алгоритм хеширования](https://www.schneier.com/blog/archives/2011/04/schneiers_law.html).

Предлагайте [многофакторную аутентификацию](https://cheatsheetseries.owasp.org/cheatsheets/Multifactor_Authentication_Cheat_Sheet.html), особенно если вы храните личные или конфиденциальные данные. В [SMS OTP best practices](https://web.dev/articles/sms-otp-form) и [Enabling Strong Authentication with WebAuthn](https://developer.chrome.com/blog/webauthn/) описано, как реализовать многофакторную аутентификацию.

Убедитесь, что пользователи не используют скомпрометированные пароли. Например, используйте API из [Have I Been Pwned](https://haveibeenpwned.com/API/) для обнаружения скомпрометированных паролей и предложите пользователям ввести другой пароль или предупредите их о том, что их пароль скомпрометирован.

## Помогите пользователям при входе в систему

Давайте посмотрим, как построить форму входа, чтобы пользователи могли легко войти на ваш сайт.

<iframe loading="lazy" src="https://codepen.io/web-dot-dev/embed/89610184f6c51990ab9484b593e1d951?height=500&amp;theme-id=light&amp;default-tab=result&amp;editable=true" style="height: 500px; width: 100%; border: 0;"></iframe>

Сделайте расположение кнопок регистрации и входа очевидным. Убедитесь, что форма удобна для использования на сенсорных устройствах:

-   [tap target size](https://web.dev/articles/accessible-tap-targets) кнопок должен быть не менее 48px.
-   Размер шрифта `font-size` элементов формы достаточно большой (`20px` как раз подходит для мобильных устройств).
-   Между элементами формы достаточно пространства (`margin`), а вводимые данные достаточно крупные (используйте по крайней мере `padding: 15px` на мобильных устройствах).

### Помогите пользователям в заполнении электронной почты и пароля

Помогите браузерам и менеджерам паролей автоматически заполнять данные учетной записи. Используйте `autocomplete="email"` для поля email и `autocomplete="current-password"` для поля текущего пароля.

Чтобы помочь пользователям вручную заполнять данные учетной записи, используйте атрибут `type="email"` для поля email, чтобы на мобильных устройствах отображалась соответствующая экранная клавиатура.

Используйте атрибут `required` для полей электронной почты и пароля, чтобы предупреждать о недопустимых значениях при отправке формы пользователем. Рассмотрите возможность использования [проверки в реальном времени](javascript.md#ensure-users-are-notified-about-errors-in-real-time), чтобы помочь пользователям исправлять недействительные данные сразу после их ввода, а не дожидаться отправки формы.

### Убедитесь, что пользователи могут видеть введенный ими пароль

Текст, который вы вводите в поле `<input type="password">`, по умолчанию скрыт, чтобы соблюсти конфиденциальность пользователей. Помогите пользователям ввести пароль, показав кнопку `<button>` для переключения видимости введенного текста.

<iframe loading="lazy" src="https://codepen.io/web-dot-dev/embed/bd8577c5380c436dba2788c7a2c8652a?height=300&amp;theme-id=light&amp;default-tab=result&amp;editable=true" style="height: 300px; width: 100%; border: 0;" ></iframe>

Подробнее о [реализации функции раскрытия пароля `<button>`](javascript.md#ensure-users-can-see-the-password-they-entered).

## Убедитесь в работоспособности форм входа и регистрации

Регулярно тестируйте формы входа и регистрации на реальных людях, чтобы убедиться, что аутентификация работает так, как ожидается. Используйте аналитику и [Real User Measurement (RUM)](https://web.dev/articles/user-centric-performance-metrics) для сбора полевых данных, а также такие инструменты, как [Lighthouse](https://developer.chrome.com/docs/lighthouse/overview/) и [PageSpeed Insights](https://pagespeed.web.dev/), для самостоятельного проведения тестов. Подробнее о [тестировании на удобство использования](usability-testing.md) и [сборе аналитических данных](data.md).

Убедитесь, что формы работают в разных браузерах и на разных платформах. Проверьте работу формы на экранах разных размеров, с использованием только клавиатуры или с помощью программы чтения с экрана, например [VoiceOver](https://www.youtube.com/watch?v=5R-6WvAihms&list=PLNYkxOF6rcICWx0C9LVWWVqvHlYJyqw7g&index=6) на Mac или [NVDA](https://www.nvaccess.org/) на Windows.

## Помогите пользователям изменить настройки учетной записи

Убедитесь, что пользователи могут изменить все параметры учетной записи, включая адреса электронной почты, пароли и имена пользователей.

Обеспечьте прозрачность хранения данных и возможность в любой момент загрузить все свои персональные данные. Убедитесь, что пользователи могут удалить свою учетную запись, если они этого хотят. В некоторых регионах такие функции управления учетными записями могут быть обязательными.

### Обеспечьте пользователям возможность обновлять свои пароли

Обеспечьте пользователям возможность легко обновлять свои пароли.

<iframe loading="lazy" src="https://codepen.io/web-dot-dev/embed/dd3ac6198324f644774583c02bf0fbd8?height=450&amp;theme-id=light&amp;default-tab=result&amp;editable=true" style="height: 500px; width: 100%; border: 0;"></iframe>

Запрашивать у пользователей текущий пароль перед его сменой, а также отправлять по электронной почте сообщение о смене пароля с возможностью отмены и блокировки учетной записи.

Добавьте возможность запроса нового пароля и рассмотрите возможность предоставления [`.well-known` URL](https://web.dev/articles/change-password-url) для запроса нового пароля.

## Ресурсы

-   [Шпаргалка по хранению паролей](https://cheatsheetseries.owasp.org/cheatsheets/Password_Storage_Cheat_Sheet.html)
-   [Понимание основной причины захвата учетных записей](https://security.googleblog.com/2017/11/new-research-understanding-root-cause.html)
-   [Безопасность пароля: сложность против длины](https://resources.infosecinstitute.com/topic/password-security-complexity-vs-length/)
-   [Лучшие практики использования формы регистрации](https://web.dev/articles/sign-up-form-best-practices)
-   [Лучшие практики работы с формой регистрации](https://web.dev/articles/sign-in-form-best-practices)
-   [Эффективное управление паролями | Сессия](https://www.youtube.com/watch?v=4Ve2kw_AN84)

:material-information-outline: Источник &mdash; [Identity](https://web.dev/learn/forms/identity)