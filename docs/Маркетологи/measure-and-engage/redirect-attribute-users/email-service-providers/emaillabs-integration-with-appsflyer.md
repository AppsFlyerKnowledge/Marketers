---
title: Интеграция EmailLabs с AppsFlyer
metadata:
  keywords:
    - Advertisers
    - Marketers
    - OneLink
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-asaf-mashiah
    - Marketers
    - OneLink
  created_at: '2022-01-31T14:00:18Z'
  edited_at: '2026-09-01T00:35:14Z'
  id: 4419148952721
  locale: ru
  section: Email service providers
  section_id: 6551247620881
  url: https://support.appsflyer.com/hc/ru/articles/4419148952721
---
> **At a glance:** EmailLabs, платформа доставки и аналитики электронной почты, встраивает OneLink AppsFlyer в электронные письма. Когда получатели электронных писем переходят по ссылке, они перенаправляются по диплинку в ваше приложение.

<Image align="center" alt="emaillabs-af-logo.png" src="https://files.readme.io/467ee1fbcea8a36dff40172b1dbc97780a7e6cafd958ecb5b520a612c3308231-49839289267857.png" />

<div id="introduction" />

## Введение

ESP (поставщики услуг электронной почты) могут быть отличными источниками сегментированного пользовательского трафика.

Одна из сложностей при использовании ESP — записывать клики, сохраняя при этом функциональность диплинкинга. ESP оборачивают URL-адрес диплинка в собственный домен для записи кликов. Это действие часто приводит к сбоям универсальных ссылок iOS.

Однако при использовании ESP, которые поддерживают универсальные ссылки поверх своего домена отслеживания кликов, диплинкинг и отслеживание кликов по-прежнему можно успешно выполнять.

<div id="sdk-version-prerequisites" />

## Требования к версии SDK

<Tabs>
<Tab title="https://files.readme.io/f28d0aac1797ee18fdc6083d9ea6d5d2f87d37a894a6c27ab0ea9b6ca51c53a1-49839256665233.png">

* AppsFlyer iOS SDK версии 6.0.4

</Tab>

<Tab title="Android;">

* SDK AppsFlyer для Android версии 6.0.0

</Tab>
</Tabs>

<div id="step-1-integration-setup-in-emaillabs" />

## Шаг 1. Настройка интеграции в EmailLabs

**Чтобы настроить интеграцию в EmailLabs:**

1. Настройте свой домен в соответствии с <Anchor target="_blank" href="https://docs.emaillabs.io/get_started/getting-started/">этой статьей</Anchor>
2. Настройте свой домен для записи кликов в соответствии с <Anchor target="_blank" href="http://docs.emaillabs.io/user-panel/smtp-applications/whitelabel-2/">этой статьей</Anchor> и снимком экрана ниже.  
   <Image align="center" alt="whitelabel-section-2.png" src="https://files.readme.io/a5b992868a0abd94b2f24097ead760a98e6529e4f83ecfaf713d681800de4631-49839273475217.png" />
3. Включите отслеживание ссылок в соответствии с <Anchor target="_blank" href="http://docs.emaillabs.io/user-panel/smtp-applications/link-tracking/">этой статьей</Anchor> и снимком экрана ниже.  
   <Image align="center" alt="link-tracking-section-3.png" src="https://files.readme.io/3c1d0f13d3fcc2b49754cf4beb653592b9fffc27ad27775cf56986f78f9ea53b-49839289275153.png" />
4. Свяжитесь со службой поддержки EmailLabs по адресу [bok@emaillabs.pl](mailto:bok@emaillabs.pl) и попросите включить SSL.
5. В EmailLabs перейдите в раздел **Панель** > **Учетные записи** **SMTP** > **Настройки** > **Диплинки** и установите флажок «Активировано». Для приложений iOS введите <Anchor target="_blank" href="https://developer.apple.com/library/archive/documentation/General/Conceptual/DevPedia-CocoaCore/AppID.html">Apple Application ID</Anchor> в соответствующее поле.  
   <Image align="center" alt="deeplinking-section-5.png" src="https://files.readme.io/15a5b45a58c1a130de6bfe2c3e9e3b379537b4fc549c1c3fcce41ef54b8653e9-49839289277073.png" />

<div id="step-2-configuring-your-appsflyer-sdk" />

### Шаг 2: Настройка SDK AppsFlyer

> 📘 **Note**
>
> **Примечание**
>
> Если вы еще этого не сделали, убедитесь, что ваше приложение настроено для поддержки <Anchor target="_blank" href="/marketers/ru/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink">диплинкинга с помощью OneLink</Anchor>.

После настройки домена отслеживания кликов для поддержки Universal Links, как описано выше, необходимо настроить приложение для диплинкинга и обработки соответствующей Universal Link.

1. Свяжите домен записи кликов в Xcode:  
   <Image align="center" alt="configure-xcode-deeplinking-domain.png" src="https://files.readme.io/90d0dcc0eba2d7d081ab7d5d4ea697e9257b9107af463fa8c973169f8a2651db-49839256220433.png" />
2. Передайте домен записи кликов в API SDK `setResolveDeepLinkURLs`. Этот API необходимо вызывать до инициализации SDK. Более подробная информация приведена в документации по SDK <Anchor target="_blank" href="/marketers/ru/docs/sdk-integration-overview">здесь</Anchor>.  

   ```objectivec
   [[AppsFlyerLib shared] resolveDeepLinkURLs = @[@"example.com",@"click.example.com"];
   ```
3. Когда приложение вызывается кликом по универсальной ссылке, AppsFlyer SDK разрешает диплинк и извлекает ссылку OneLink. Затем все параметры диплинка передаются в API onAppOpenAttribution для выполнения логики диплинка.

<div id="step-3-send-emails-with-onelink-through-emaillabs" />

## Шаг 3: Отправка электронных писем с OneLink через EmailLabs

1. Создайте URL-адрес OneLink на странице управления ссылками (или вручную). Необходимо выполнить URL-кодирование значений параметров.
2. [Рекомендуемая практика] Используйте следующие параметры:
   * *pid* (медиаисточник): укажите медиаисточник, отражающий этот сценарий использования, например EmailLabs.
   * *c* (кампания): название кампании
   * *af\_dp*: схема URI для диплинкинга, по которой вы хотите перенаправлять пользователей.
   * *af\_web\_dp:* куда перенаправлять пользователей, переходящих по ссылке на компьютере.
   * *af\_ios\_url*: куда перенаправлять пользователей, у которых нет приложения, при переходе по ссылке на устройстве iOS.
   * *af\_android\_url:* Куда перенаправлять пользователей, у которых нет приложения, при переходе по ссылке на устройстве Android.
3. Вставьте URL-адрес OneLink в электронное письмо.  
   Пример:

   ```html
   <a href="links.example.com data-msys-sublink="appsflyer">Ссылка на ваше приложение!</a>
   ```
4. Если электронное письмо является частью ретаргетинговой кампании, добавьте параметр is\_retargeting=true.  
   Это указывает на то, что ссылка атрибуции относится к ретаргетинговой кампании. <Anchor target="_blank" href="/marketers/ru/docs/retargeting-attribution-guide">Узнать больше о ретаргетинге</Anchor>.
5. EmailLabs оборачивает ссылку в заданный домен кликов, чтобы клик по этому домену перенаправлял на ссылку атрибуции OneLink.

> 📘 **Note**
>
> **Например**
>
> Параметры URL-адреса в следующем примере не закодированы для удобства чтения.
>
> ```http
> https://example.onelink.me/abcd?pid=emaillabs&c=Spring_Newsletter&is_retargeting=true&
> af_dp=testapp://path/to/content&af_web_dp=https://www.example.com/path/to/content&
> af_ios_url=https://www.example.com/path/to/content&af_android_url=https://www.example.com/path/to/content
> ```

<div id="step-4-test-your-links" />

## Шаг 4: Протестируйте ссылки

**Чтобы протестировать интеграцию:**

1. Настройте EmailLabs.
2. Создайте URL-адрес OneLink.
3. Вставьте URL-адрес в электронное письмо.
4. Отправьте себе тестовое электронное письмо.

**Ожидаемый результат:**

* Если приложение установлено, оно должно открыться, и вы перейдете на указанную страницу приложения по диплинку.
* Клик отображается в:
  * Дэшборд AppsFlyer с атрибуцией по медиаисточнику и кампании.
  * Данные EmailLabs.

<div data-zendesk-anchors="introduction=%D0%B2%D0%B2%D0%B5%D0%B4%D0%B5%D0%BD%D0%B8%D0%B5 sdk-version-prerequisites=%D1%82%D1%80%D0%B5%D0%B1%D0%BE%D0%B2%D0%B0%D0%BD%D0%B8%D1%8F-%D0%BA-%D0%B2%D0%B5%D1%80%D1%81%D0%B8%D0%B8-sdk step-1-integration-setup-in-emaillabs=%D1%88%D0%B0%D0%B3-1-%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-%D0%B8%D0%BD%D1%82%D0%B5%D0%B3%D1%80%D0%B0%D1%86%D0%B8%D0%B8-%D0%B2-emaillabs step-2-configuring-your-appsflyer-sdk=%D1%88%D0%B0%D0%B3-2-%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-sdk-appsflyer step-3-send-emails-with-onelink-through-emaillabs=%D1%88%D0%B0%D0%B3-3-%D0%BE%D1%82%D0%BF%D1%80%D0%B0%D0%B2%D0%BA%D0%B0-%D1%8D%D0%BB%D0%B5%D0%BA%D1%82%D1%80%D0%BE%D0%BD%D0%BD%D1%8B%D1%85-%D0%BF%D0%B8%D1%81%D0%B5%D0%BC-%D1%81-onelink-%D1%87%D0%B5%D1%80%D0%B5%D0%B7-emaillabs step-4-test-your-links=%D1%88%D0%B0%D0%B3-4-%D0%BF%D1%80%D0%BE%D1%82%D0%B5%D1%81%D1%82%D0%B8%D1%80%D1%83%D0%B9%D1%82%D0%B5-%D1%81%D1%81%D1%8B%D0%BB%D0%BA%D0%B8" />
