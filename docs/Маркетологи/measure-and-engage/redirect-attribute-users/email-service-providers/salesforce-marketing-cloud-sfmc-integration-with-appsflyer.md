---
title: Интеграция Salesforce Marketing Cloud (SFMC) с AppsFlyer
metadata:
  keywords:
    - Marketers
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  created_at: '2026-09-01T14:53:41Z'
  edited_at: '2026-09-23T00:21:46Z'
  id: 50431751712529
  locale: ru
  section: Email service providers
  section_id: 6551247620881
  url: https://support.appsflyer.com/hc/ru/articles/50431751712529
---
> **At a glance:** Интегрируйте AppsFlyer с Salesforce Marketing Cloud (SFMC), чтобы с помощью диплинкинга направлять пользователей из email-кампаний к контенту в приложении. Синхронизируйте данные о событиях в приложении с SFMC, чтобы создавать аудитории и запускать пути на основе реального поведения в приложении.

<div id="about-the-integration" />

## Об интеграции

SFMC позволяет повторно вовлекать существующих пользователей через email-кампании, направляя их с помощью диплинков к определенному контенту в приложении, например к промоакции или персонализированному предложению.

Есть два варианта интеграции:

* **Стандартный email-диплинкинг в SFMC**: создайте в AppsFlyer ссылки OneLink для кампании, а затем добавьте их в электронные письма.
* **Расширенная интеграция AppExchange с SFMC**: создавайте ссылки OneLink для кампаний прямо в Salesforce и автоматически импортируйте данные о событиях в приложении, чтобы формировать аудитории для повторного вовлечения. Это премиум-функция.

<div id="comparison-standard-vs-advanced" />

## Сравнение: Standard vs. Advanced

| Возможность | Стандартный email-диплинкинг в SFMC | Расширенная интеграция AppExchange с SFMC |
| --- | --- | --- |
| Отложенные диплинки | Да | Да |
| Прямые диплинки | Да | Да |
| Измерение диплинков | Да | Да |
| Создание ссылок | В AppsFlyer | В специальном приложении Salesforce |
| Постбэки SFMC (синхронизация событий в приложении) | Ни один | Да |

<div id="prerequisites" />

## Предварительные требования

<Tabs>
<Tab title="https://files.readme.io/f28d0aac1797ee18fdc6083d9ea6d5d2f87d37a894a6c27ab0ea9b6ca51c53a1-49839256665233.png">

* SDK AppsFlyer для iOS версии 4.9.0+
* Для универсальных ссылок iOS в вашей среде SFMC выполните следующие действия: приобретите и внедрите <Anchor target="_blank" href="https://help.salesforce.com/articleView?id=mc_es_sender_authentication_package.htm&type=5">Sender Authentication Package</Anchor> (SAP), а также приобретите сертификат SSL (конфигурация SSL) и отправьте форму запроса SSL. Чтобы получить оба варианта, обратитесь к представителю Salesforce по вашему аккаунту или отправьте кейс в поддержку по доставляемости через Salesforce Help.

</Tab>

<Tab title="Android;">

* SDK AppsFlyer для Android версии 4.9.0+
* SFMC не поддерживает Android App Links, поэтому вместо них используется диплинкинг по <Anchor target="_blank" href="/marketers/ru/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#general-settings">схеме URI</Anchor>. Никаких специальных действий для поддержки диплинкинга в приложениях Android из SFMC не требуется.

</Tab>
</Tabs>

<div id="set-up-standard-sfmc-email-deep-linking" />

## Настройка стандартных диплинков для электронных писем SFMC

**См. инструкции по настройке интеграции:**

<Accordion title="Шаг 1: Настройте свой домен для записи кликов в SFMC">

Чтобы настроить домен для записи кликов, следуйте официальным руководствам SFMC:

* <Anchor target="_blank" href="https://help.salesforce.com/articleView?id=mc_es_implement_ios_universal_link.htm&type=5">Внедрение универсальных ссылок iOS</Anchor>
* <Anchor target="_blank" href="https://help.salesforce.com/articleView?id=mc_es_dns_record_maintenance.htm&type=5">Обслуживание записей DNS</Anchor>

</Accordion>

<Accordion title="Шаг 2: Загрузите свой SSL-сертификат в SFMC">

Чтобы универсальные ссылки iOS работали корректно, ваш домен для регистрации кликов должен включать SSL-сертификат вашего домена, который необходимо установить в вашем аккаунте SFMC. Инструкции по настройке SSL-сертификатов можно найти в <Anchor target="_blank" href="https://help.salesforce.com/articleView?id=mc_es_ssl_certificates.htm&type=5">официальном руководстве SFMC</Anchor>.

</Accordion>

<Accordion title="Шаг 3: Настройка диплинкинга в SFMC">

Чтобы активировать перенаправление по диплинкам из электронных писем SFMC, выполните следующие действия:

1. Войдите в свой аккаунт SFMC и перейдите к представлению **Email Studio**
2. Перейдите на вкладку **Администратор**.
3. В боковом меню нажмите на **диплинкинг**. В этом представлении вы можете настроить новую интеграцию диплинков со своим приложением или изменить существующие.

   <Image align="center" alt="[НЕОБХОДИМ АЛЬТЕРНАТИВНЫЙ ТЕКСТ: опишите экран настройки диплинкинга SFMC]" src="https://files.readme.io/4b7e68abb76163329ab5d487425c4dfe3ee903bb3360893c9b59f40f73486858-50431735587345.png" width="3348px" />
4. Чтобы создать новую конфигурацию, нажмите кнопку **Создать** и введите свой AppID. Значение AppID представляет собой комбинацию идентификатора вашей команды разработчиков Apple и идентификатора пакета. Оба эти значения можно получить из вашего аккаунта Apple Developer.

   <div id="example" />

   > 📄 **Пример**
   >
   > Если префикс идентификатора команды *5UABCDFGH* и идентификатор пакета *com.your.app*, необходимо ввести следующее значение:  
   > 5uabcdfgh.com.your.app
   >
   > <Image align="center" alt="[НЕОБХОДИМ АЛЬТЕРНАТИВНЫЙ ТЕКСТ: опишите показанный здесь экран настройки диплинкинга SFMC]" src="https://files.readme.io/4f5500c6f538b2b8e00db0bae1bcac240fc49b30419f4f4a8b07fb0bd3cf8f4a-50431735587985.png" width="1234px" />

5. Настройка универсальных ссылок и диплинкинга будет завершена после того, как SFMC создаст файл Apple App Site Association (AASA). Этот процесс может занять несколько часов. Сгенерированный файл можно увидеть по следующему URL-адресу:

   ```
   https://<click_recording_link_domain>/apple-app-site-association
   ```

</Accordion>

<Accordion title="Шаг 4: Настройте свой SDK AppsFlyer">

> 📘 **Примечание**
>
> Если вы этого еще не сделали, обязательно настройте приложение на поддержку <Anchor target="_blank" href="/marketers/ru/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink">диплинкинга с OneLink</Anchor>.

После настройки домена регистрации кликов для поддержки универсальных ссылок, как описано выше, вам необходимо настроить приложение на диплинкинг и разрешить универсальные ссылки.

1. Свяжите домен регистрации кликов в Xcode:

   <Image align="center" alt="[НЕОБХОДИМ АЛЬТЕРНАТИВНЫЙ ТЕКСТ: опишите экран связанных доменов в Xcode]" src="https://files.readme.io/02bee3d75c32d494d80719b2718ddf4648440bcb3ebcb2132799e44e38852629-50431735589009.png" width="1135px" />
2. Предоставьте домен регистрации кликов в API SDK `setResolveDeepLinkURLs`. Этот API необходимо вызывать до инициализации SDK. Дополнительные сведения см. в документации SDK по <Anchor target="_blank" href="/marketers/ru/docs/sdk-integration-overview">разрешению URL-адресов диплинков</Anchor>.

   ```swift
   AppsFlyerLib.shared().resolveDeepLinkURLs = ["example.com", "click.example.com"]
   ```

   * **Важно!** Если вы используете Movable Ink (MI) вместе с Salesforce, вам необходимо получить MI CNAME и внутренние домены у своего менеджера по работе с клиентами MI и добавить их в `setResolveDeepLinkURLs`, а также ссылку для кликов для Salesforce. Например:

     ```swift
     AppsFlyerLib.shared().resolveDeepLinkURLs = ["salesforce-click.example.com", "mi.example.com", "example.micpn.com"]
     ```
3. Когда приложение вызывается кликом по универсальной ссылке, AppsFlyer SDK разрешает диплинк и извлекает ссылку OneLink. Затем все параметры диплинка передаются в <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/ios-sdk-reference-appsflyerlibdelegate#onappopenattribution">API onAppOpenAttribution</Anchor> для выполнения логики диплинка.

</Accordion>

<div id="send-emails-with-standard-sfmc-email-deep-linking" />

## Отправка электронных писем со стандартным диплинкингом email в SFMC

**Чтобы отправлять электронные письма со стандартным диплинкингом email в SFMC:**

1. Создайте <Anchor target="_blank" href="/marketers/ru/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink">ссылку OneLink</Anchor> вручную или на странице ссылок OneLink на дэшборде AppsFlyer.
2. При создании OneLink кодируйте все значения параметров в формате URL. Настоятельно рекомендуется использовать следующие параметры:

| Параметр | Описание | Примечания |
| --- | --- | --- |
| pid | Подписка IAP | Репрезентативный медиа-источник |
| c | Доступно только в <Anchor target="_blank" href="/marketers/ru/docs/about-data-locker-advanced-reports">расширенных отчётах</Anchor>. | Кампания, которой будет присвоена атрибуция |
| af\_dp | URL-адрес диплинка | Адрес перенаправления пользователей по диплинку |
| af\_web\_dp. | Перенаправление на настольную версию | Перенаправление для пользователей настольных компьютеров |
| af\_ios\_url; |  | Перенаправление для пользователей iOS, у которых не установлено приложение |
| af\_android\_url; |  | Перенаправление для пользователей Android, у которых не установлено приложение |

3. Скопируйте ссылку в письмо, которое вы создаете в Salesforce Email Studio. Salesforce Marketing Cloud оборачивает ссылку вашим доменом для регистрации кликов, поэтому любой клик по этому домену перенаправляет на вашу ссылку OneLink для атрибуции.

**Пример** (параметры URL-адреса показаны без кодирования для удобства чтения):

```
https://example.onelink.me/ABcd?pid=Email&c=Spring_Newsletter&af_dp=testapp://path/to/content&af_web_dp=https://www.example.com/path/to/content&af_ios_url=https://www.example.com/path/to/content&af_android_url=https://www.example.com/path/to/content
```

<div id="set-up-the-advanced-sfmc-app-exchange-integration" />

## Настройка расширенной интеграции SFMC AppExchange

**Чтобы настроить расширенную интеграцию SFMC AppExchange:**

<Accordion title="Шаг 1. Установите приложение OneLink из SFMC AppExchange">

1. Попросите вашего CSM или отправьте электронное письмо на hello@appsflyer.com, чтобы включить установку приложения в SFMC AppExchange.
2. В Salesforce перейдите по ссылке AppExchange, которой с вами поделится ваш CSM после включения приложения.
3. Нажмите **Install**.
4. Предоставьте разрешения: попросите администратора Salesforce Marketing Cloud предоставить доступ к приложению отдельным пользователям или бизнес-юнитам. Возможно, потребуется выполнить hard refresh, чтобы увидеть новые разрешения.
5. Предоставьте пользователям доступ к приложению AppsFlyer OneLink: перейдите в **Apps > Installed Packages**, откройте вкладку **ACCESS**, выберите пользователей, которым нужно разрешить использовать OneLink, и нажмите **Save**. Опять же, может потребоваться hard refresh.

</Accordion>

<Accordion title="Шаг 2: Выполните базовую настройку">

Выполните шаги из раздела «[Настройка стандартного диплинкинга для электронной почты SFMC](#настройка-стандартных-диплинков-для-электронных-писем-sfmc)» выше.

</Accordion>

<Accordion title="Шаг 3: Создайте ссылки OneLink в Salesforce с помощью приложения AppsFlyer OneLink">

Создайте отдельную ссылку атрибуции для каждой кампании.

<Image align="center" alt="[НУЖЕН АЛЬТЕРНАТИВНЫЙ ТЕКСТ: сейчас используется имя файла SFMC-AF-app1-en_us.png; опишите показанный экран приложения OneLink]" src="https://files.readme.io/21d7961d03e822dd2a4ccb426dc7b5c85c3700f81a9530bc8950a67e3f1d6237-50431735591185.png" width="684px" />

**Чтобы создать ссылку OneLink:**

1. В **Salesforce** откройте приложение **AppsFlyer** OneLink.
2. Нажмите **Add OneLink**.
3. Введите имя в поле **Link name**. Учтите:
   * Выберите понятное и легко узнаваемое имя.
   * Имя ссылки будет использоваться при применении OneLink к email-кампаниям.
4. В поле **Base URL** введите URL-адрес OneLink в длинном формате, скопированный со страницы **AppsFlyer OneLink custom links**.
   * Используйте URL-адрес в длинном формате, чтобы приложение проанализировало и установило параметры ссылки.
   * Узнайте, как <Anchor target="_blank" href="/marketers/ru/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#testing">скопировать URL-адрес существующей ссылки</Anchor> или <Anchor target="_blank" href="/marketers/ru/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink">создать новую ссылку OneLink</Anchor>.
5. [Необязательно] Чтобы добавить дополнительные параметры, нажмите **Добавить параметр**. См. <Anchor target="_blank" href="/marketers/ru/docs/about-link-structure-and-parameters#параметры-ссылки-атрибуции">список рекомендуемых параметров</Anchor>.
6. [Необязательно] Чтобы задать внутренний макрос Salesforce Marketing Cloud, нажмите значок справа от параметра.
   * Для каждого параметра **OneLink** рекомендуется задать **Subscriber key**.
   * Это позволит связать атрибутированные конверсии из email с вашими данными Salesforce.
7. Нажмите **Создать ссылку**.

</Accordion>

<Accordion title="Шаг 4. Отправка электронных писем с пользовательскими ссылками атрибуции">

1. В **Salesforce Email Studio** создайте новый шаблон или электронное письмо.
2. Нажмите **Редактировать**, перейдите на вкладку **Контент**, затем выберите **Блоки**.
3. Прокрутите вниз и найдите **AppsFlyer Button CB** или **AppsFlyer Image CB**.

   <Image align="center" alt="[НЕОБХОДИМ АЛЬТЕРНАТИВНЫЙ ТЕКСТ: текущее имя файла sf_email_edit_onelink_new.PNG; опишите показанную панель Content Blocks]" src="https://files.readme.io/565a80933451dbdb1606b20f8d71964019a36f14ffd0b0ba295649a96b056cf0-50431751706641.png" width="396px" />
4. Перетащите изображение/кнопку в тело электронного письма.
5. Нажмите на изображение/кнопку, чтобы отредактировать.
6. В поле **Заголовок** укажите название изображения/кнопки.
7. Выберите **ссылку OneLink**.

   <Image align="center" alt="[НЕОБХОДИМ АЛЬТЕРНАТИВНЫЙ ТЕКСТ: опишите показанный селектор ссылок OneLink]" src="https://files.readme.io/1d22268b5ced4d753cb6812decdccd960e92d9d8156213f76fc67db98b52c9c7-50431751707665.png" width="415px" />
8. Сохраните электронное письмо и отправьте его.

<div id="example-1" />

> 📄 **Пример**
>
> Для удобства чтения параметры URL не закодированы в URL-адресе:
>
> ```
> https://example.onelink.me/ABcd?pid=Email&c=Spring_Newsletter&
> af_dp=testapp://path/to/content&af_web_dp=https://www.example.com/path/to/content&
> af_ios_url=https://www.example.com/path/to/content&af_android_url=https://www.example.com/path/to/content
> ```

</Accordion>

<Accordion title="Шаг 5: Протестируйте ссылки">

**Чтобы протестировать ссылки атрибуции:**

1. Создайте соответствующий URL-адрес OneLink.
2. Поместите его в электронное письмо.
3. Отправьте электронное письмо себе.
4. Нажмите ссылку.

* Если приложение установлено на вашем устройстве, оно должно быть вызвано.
* Если реализованы соответствующие API для диплинкинга в AppsFlyer SDK, то вы должны перейти по диплинку на соответствующий контент.
* Клик должен появиться на дэшборде AppsFlyer, атрибутированный к указанному медиа-источнику и кампании.
* Клик появляется в данных Salesforce.

</Accordion>

<div id="dynamic-emails" />

## Динамические письма

Если вам нужно динамически генерировать ссылки, чтобы отображать динамический контент для каждого пользователя, используйте API OneLink.

Для этого в Journey Builder SFMC используйте активность скрипта Automation Studio, которая перед отправкой вызывает API OneLink, записывает сгенерированную глубокую ссылку в поле Data Extension для отправки для каждого контакта, а затем письмо подставляет это поле через простой AMPscript lookup.

<div id="advanced-sfmc-in-app-events-data-sync" />

## Расширенная синхронизация данных о событиях в приложении в SFMC

Эта функция позволяет AppsFlyer автоматически отправлять данные о событиях в приложении из вашего приложения в Salesforce Marketing Cloud, где они хранятся в отдельном Data Extension. Используйте эти данные, чтобы создавать аудитории, запускать пути и персонализировать кампании на основе реального поведения в приложении, например покупок, регистраций или прохождения уровней.

Это премиум-функция, доступная в рамках расширенной интеграции AppExchange для SFMC.

<div id="how-it-works" />

### Принцип действия

Когда пользователь выполняет событие в приложении (например, завершает покупку), AppsFlyer отправляет постбэк в коннектор SFMC. Коннектор записывает данные о событии в Data Extension в вашей учетной записи SFMC, где каждая строка представляет одно событие для одного контакта. После этого используйте Journey Builder или Automation Studio в SFMC, чтобы запускать последующие коммуникации на основе этого события.

**Чтобы настроить расширенную синхронизацию данных:**

<Accordion title="Шаг 1. Включите отправку постбэков в AppsFlyer">

1. В AppsFlyer перейдите в **Collaborate > Active Integrations** и найдите Salesforce Marketing Cloud.
2. Выберите приложение, которое хотите настроить, и нажмите **Set up integration**.
3. На вкладке **Integration** убедитесь, что переключатель **Activate partner** включен.
4. Прокрутите до раздела **In-app event postbacks** и включите переключатель.
5. Нажмите **Add event** и сопоставьте события AppsFlyer, которые хотите отправлять в SFMC. Для каждого события выберите его из списка событий вашего приложения и задайте условие отправки: **This partner only** (отправляются только события, атрибутированные трафику SFMC) или **All media sources, including organic** (рекомендуется для создания аудиторий, так как отправляется каждое срабатывание события независимо от атрибуции).
6. Нажмите **Сохранить интеграцию**.

<div id="note-1" />

> 📘 **Note**
>
> В списке событий отображаются только события, которые AppsFlyer уже получил через ваш SDK или S2S-интеграцию. Если событие отсутствует, сначала проверьте реализацию SDK.

</Accordion>

<Accordion title="Шаг 2. Проверьте Data Extension в SFMC">

После отправки первого постбэка AppsFlyer автоматически создает Data Extension в вашей учетной записи SFMC с именем Installs-`{mid} или Events-{mid}`. Для проверки:

1. В SFMC перейдите в **Email Studio > Data Extensions**.
2. Найдите Data Extension вашего приложения.
3. Убедитесь, что строки заполняются данными о событиях. В каждой строке должны быть идентификатор контакта, название события, временная метка события и параметры события.

Если Data Extension не был создан автоматически, убедитесь, что приложение-коннектор SFMC установлено правильно и что администратор SFMC предоставил ему необходимые разрешения на запись данных.

</Accordion>

<Accordion title="Шаг 3. Используйте данные о событиях в Journey Builder">

1. В SFMC откройте Journey Builder и создайте или измените путь.
2. Укажите **Data Extension** в качестве источника входа и выберите AppsFlyer Data Extension для вашего приложения.
3. Настройте критерии входа, например контакты, у которых event\_name равно af\_purchase.
4. Создайте нужные шаги пути (отправка email, ожидание, ветвление по значению события и т. д.).
5. Активируйте путь.

> 👍 **Tip**
>
> Используйте параметр af\_sub1 в своих OneLink, чтобы передавать ключ подписчика SFMC в качестве идентификатора пользователя. Это позволяет сопоставлять постбэки с правильной записью контакта в Salesforce и использовать персонализацию на уровне контакта, а не только атрибуцию на уровне кампании.

</Accordion>

<div id="postback-data-fields" />

### Поля данных постбэка

Коннектор SFMC создает в вашей учетной записи два Data Extension: один для установок, другой — для событий в приложении. Все поля есть в схеме, но некоторые из них сейчас не заполняются. Поля с пометкой "not written" входят в схему, но всегда будут пустыми.

<Accordion title="Поля данных">

**Поля Data Extension установок (49 полей)**

| Поле | Записано | Примечания |
| --- | --- | --- |
| Тип взаимодействия | Да |  |
| Время касания | Да |  |
| Название события | Да |  |
| Источник события | Да |  |
| Источник медиа | Да |  |
| Доступно только в <Anchor target="_blank" href="/marketers/ru/docs/about-data-locker-advanced-reports">расширенных отчётах</Anchor>. | Да |  |
| Доступно только в <Anchor target="_blank" href="/marketers/ru/docs/about-data-locker-advanced-reports">расширенных отчётах</Anchor>. | Да |  |
| строка | Да |  |
| Sub Param 1–5 | Да | Сопоставьте с ссылками af\_sub1–af\_sub5 в OneLink |
| Подписка IAP | Да |  |
| Код страны | Да |  |
| Ссылка | Да |  |
| Доступно только в <Anchor target="_blank" href="/marketers/ru/docs/about-data-locker-advanced-reports">расширенных отчётах</Anchor>. | Да |  |
| Почтовый индекс | Да |  |
| Подтвержден ли чек | Да |  |
| IP | Да |  |
| AF ID | Да | Уникальный идентификатор устройства AppsFlyer |
| IDFV | Да |  |
| Логическое значение | Да |  |
| Категория устройства | Да |  |
| Это ретаргетинг | Да |  |
| Версия ОС | Да |  |
| Версия приложения | Да |  |
| Версия SDK | Да |  |
| Строка | Да |  |
| Имя приложения | Да |  |
| Is Retargeting (Ретаргетинг) | Да |  |
| Тип сопоставления | Да |  |
| User Agent. | Да |  |
| Время установки | Да |  |
| Время события | Да |  |
| Значение диплинк-ссылки | Да |  |
| deep\_link\_sub1—deep\_link\_sub10 | Ни один | Есть в схеме, не записывается |
| IDFA | Ни один | Есть в схеме, не записывается (идентификатор устройства iOS) |
| ID рекламодателя | Ни один | Есть в схеме, не записывается (GAID Android) |

**Поля расширения данных in-app событий**

Все поля установок выше, а также:

| Поле | Записывается | Примечания |
| --- | --- | --- |
| Is Primary Attribution (Основная атрибуция) | Ни один | Есть в схеме, не записывается |
| Окно повторного вовлечения | Ни один | Есть в схеме, не записывается |
| Значение события | Ни один | Есть в схеме, не записывается |
| Валюта выручки от события | Ни один | Есть в схеме, не записывается |
| Выручка от события в USD | Ни один | Есть в схеме, не записывается |

</Accordion>

<div id="troubleshooting" />

### Устранение неполадок

* **Нет данных в Data Extension**: проверьте, что переключатель активации партнера и переключатель постбэков событий в приложении включены, а нужные вам события сопоставлены. Также убедитесь, что у приложения SFMC есть разрешения на запись данных в вашей учетной записи SFMC.
* **События отображаются, но соответствующие контакты не найдены**: убедитесь, что вы передаете af\_sub1=%%subscriberkey%% в OneLink, чтобы постбэки могли сопоставляться с контактами SFMC.
* **Data Extension не создано**: обратитесь к своему CSM или в службу поддержки AppsFlyer, чтобы убедиться, что коннектор правильно настроен для вашего аккаунта.

<div data-zendesk-anchors="h_01M1EKQ4FWJDKEECDASNHC226Z=%D0%BE%D0%B1-%D0%B8%D0%BD%D1%82%D0%B5%D0%B3%D1%80%D0%B0%D1%86%D0%B8%D0%B8 h_01M1EKQ4FWVTQ3R02AE6QREKKK=%D1%81%D1%80%D0%B0%D0%B2%D0%BD%D0%B5%D0%BD%D0%B8%D0%B5-standard-vs-advanced h_01M1EKQ4FW9XVMFC7FXD8551C1=%D0%BF%D1%80%D0%B5%D0%B4%D0%B2%D0%B0%D1%80%D0%B8%D1%82%D0%B5%D0%BB%D1%8C%D0%BD%D1%8B%D0%B5-%D1%82%D1%80%D0%B5%D0%B1%D0%BE%D0%B2%D0%B0%D0%BD%D0%B8%D1%8F h_01M1EKQ4FW115929RS4BR442QF=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-%D1%81%D1%82%D0%B0%D0%BD%D0%B4%D0%B0%D1%80%D1%82%D0%BD%D1%8B%D1%85-%D0%B4%D0%B8%D0%BF%D0%BB%D0%B8%D0%BD%D0%BA%D0%BE%D0%B2-%D0%B4%D0%BB%D1%8F-%D1%8D%D0%BB%D0%B5%D0%BA%D1%82%D1%80%D0%BE%D0%BD%D0%BD%D1%8B%D1%85-%D0%BF%D0%B8%D1%81%D0%B5%D0%BC-sfmc h_01HE7RCE5NE25563AAGBH0EPZC=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%80 h_01HE7RCE5N1WQA3XEN9W1QY29K=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%87%D0%B0%D0%BD%D0%B8%D0%B5 h_01M1EKQ4FW5Q23VEPA4YJK9MQF=%D0%BE%D1%82%D0%BF%D1%80%D0%B0%D0%B2%D0%BA%D0%B0-%D1%8D%D0%BB%D0%B5%D0%BA%D1%82%D1%80%D0%BE%D0%BD%D0%BD%D1%8B%D1%85-%D0%BF%D0%B8%D1%81%D0%B5%D0%BC-%D1%81%D0%BE-%D1%81%D1%82%D0%B0%D0%BD%D0%B4%D0%B0%D1%80%D1%82%D0%BD%D1%8B%D0%BC-%D0%B4%D0%B8%D0%BF%D0%BB%D0%B8%D0%BD%D0%BA%D0%B8%D0%BD%D0%B3%D0%BE%D0%BC-email-%D0%B2-sfmc h_01M1EKQ4FW91474YRH5GZ0K805=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-%D1%80%D0%B0%D1%81%D1%88%D0%B8%D1%80%D0%B5%D0%BD%D0%BD%D0%BE%D0%B9-%D0%B8%D0%BD%D1%82%D0%B5%D0%B3%D1%80%D0%B0%D1%86%D0%B8%D0%B8-sfmc-appexchange h_01HA51F56HX6VQDYNAQAADKBHJ=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%80-1 h_01M1EKQ4FW48QWSZ9W5J80AZVZ=%D0%B4%D0%B8%D0%BD%D0%B0%D0%BC%D0%B8%D1%87%D0%B5%D1%81%D0%BA%D0%B8%D0%B5-%D0%BF%D0%B8%D1%81%D1%8C%D0%BC%D0%B0 h_01M1EKQ4FW4N9ZGBDGYZ6VAKWN=%D1%80%D0%B0%D1%81%D1%88%D0%B8%D1%80%D0%B5%D0%BD%D0%BD%D0%B0%D1%8F-%D1%81%D0%B8%D0%BD%D1%85%D1%80%D0%BE%D0%BD%D0%B8%D0%B7%D0%B0%D1%86%D0%B8%D1%8F-%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D1%85-%D0%BE-%D1%81%D0%BE%D0%B1%D1%8B%D1%82%D0%B8%D1%8F%D1%85-%D0%B2-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D0%B8-%D0%B2-sfmc h_01M1EKQ4FWVP1A3J89BGQBV8A8=%D0%BF%D1%80%D0%B8%D0%BD%D1%86%D0%B8%D0%BF-%D0%B4%D0%B5%D0%B9%D1%81%D1%82%D0%B2%D0%B8%D1%8F h_01M1EKQ4FWZZS3D4T5QW7HNQ9W=%D0%BF%D0%BE%D0%BB%D1%8F-%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D1%85-%D0%BF%D0%BE%D1%81%D1%82%D0%B1%D1%8D%D0%BA%D0%B0 h_01M1EKQ4FW366GDCCXJS7TDEQS=%D1%83%D1%81%D1%82%D1%80%D0%B0%D0%BD%D0%B5%D0%BD%D0%B8%D0%B5-%D0%BD%D0%B5%D0%BF%D0%BE%D0%BB%D0%B0%D0%B4%D0%BE%D0%BA" />
