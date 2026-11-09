---
title: Конверсия по QR в приложение
metadata:
  keywords:
    - OneLink
    - Advertisers
    - owned media
    - Marketers
    - Smart Banners and Scripts
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-asaf-mashiah
    - Marketers
    - Smart Banners and Scripts
  created_at: '2020-11-04T09:49:23Z'
  edited_at: '2026-08-18T00:36:08Z'
  id: 360015119718
  locale: ru
  section: Owned media attribution
  section_id: 6551214397585
  url: https://support.appsflyer.com/hc/ru/articles/360015119718
---
> **Краткий обзор.** Превращайте пользователей настольных компьютеров, телевизоров, CTV или офлайн в пользователей мобильных приложений с помощью QR-кодов, созданных на базе OneLink.

<Image align="center" alt="6005_QR_code_4.jpg" src="https://files.readme.io/6db45d7e82bc33ba8af8c6e7d096011d71b06766da9df348dccfa1b3e4aa380d-12368835107601.jpg" />

<div id="converting-mobile-non-mobile-and-offline-traffic-into-mobile-app-users" />

## Преобразуйте мобильный, немобильный и офлайн-трафик в пользователей мобильного приложения

Размещение QR-кодов, сгенерированных OneLink, в рекламе для настольных компьютеров, телевидения, CTV или в офлайне, например, на витринах магазинов, брошюрах и упаковке, дает следующие преимущества:

* Пользователи могут быстро и легко отсканировать код с помощью своего мобильного устройства, чтобы загрузить и установить ваше приложение.
* Пользователи экономят время и силы, затрачиваемые на посещение магазина приложений и поиск вашего приложения, что значительно повышает конверсии по QR-коду в установку приложения.
* Конфиденциальность защищена, поскольку этот метод конверсии обходится без СМС, и пользователям не нужно предоставлять приватную информацию, например номер телефона для отправки СМС.
* Вы можете с легкостью атрибутировать установки и измерить эффективность ваших объявлений.я

QR-коды можно создавать следующими способами:

* [Вручную, в пользовательском интерфейсе AppsFlyer](/docs/qr-to-app-conversion#ручная-настройка-qr-кода)
* [Динамически, с помощью OneLink Smart Script](/docs/qr-to-app-conversion#dynamic-qr-code-setup) (специально разработанного для потоков из веба на ПК в приложение).

<div id="qr-to-app-conversion" />

<Accordion title="Настройте конверсии по QR в приложение">

<div id="manual-qr-code-setup" />

#### Ручная настройка QR-кода

**Необходимые условия:**

* Аккаунт AppsFlyer с хотя бы одним приложением.
* Для атрибуции: <Anchor target="_blank" href="/marketers/ru/docs/integrate-the-appsflyer-sdk">AppsFlyer SDK уже интегрирован</Anchor> в каждое из ваших мобильных приложений.
  * Если SDK еще не установлен в ваших приложениях, можно создать рабочую ссылку для перенаправления, но будут невозможны диплинкинг, отложенный диплинкинг или измерение количества установок на вашем дэшборде.

* <Anchor target="_blank" href="/marketers/ru/docs/create-a-onelink-template#создание-шаблонов-onelink">Шаблон OneLink</Anchor> настроен.

**Чтобы настроить QR-код для конверсий по QR в приложение**:

1. Выполните **одно** из следующих действий:
   * <Anchor target="_blank" href="/marketers/ru/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#создание-ссылки-onelink">Создать отдельное изображение QR-кода</Anchor>
     1. [Рекомендуется] Создайте новую ссылку и задайте пользовательский медиа-источник. Например: **desktop\_web**.  
         Использование QR-кода из существующей ссылки работает. Однако для целей отчетности мы не рекомендуем передавать медиа-источники по другой ссылке. Вместо этого используйте отдельную ссылку с одним медиа-источником.
     2. Когда вы нажмете **Создать ссылку**, на экране появится QR-код.
     3. Нажмите на QR-код, чтобы скачать его в полном разрешении, в формате SVG или PNG.
   * <Anchor target="_blank" href="/marketers/ru/docs/perform-onelink-bulk-actions-via-csv#downloading-a-collection-of-qr-codes">Создать набор изображений QR-кодов</Anchor>
     1. На странице **Bulk Links** создайте коллекцию ссылок.
     2. Загрузите QR-изображения для ссылок в коллекции.
2. Добавьте QR-код в объявление, как вы добавляете любое другое изображение/контент.
   * См. [рекомендации](/docs/qr-to-app-conversion#best-practices).
   * Может потребоваться помощь разработчика.

</Accordion>

<div id="customize-qr-code" />

<Accordion title="Настроить QR-код">

<Image align="center" alt="OnelinkQRFinal__1_.gif" src="https://files.readme.io/6eb996db8c8bcdb8ac46380151fc54c8ef5b686999aaaef3d1a951d627eadc70-11902870808081.gif" />

Вы можете настроить вид QR-кодов, созданных через OneLink:

* Добавить логотип в QR-код.
* Изменить цвет QR-кода.

**Внимание**:

* Настройка QR-кода выполняется на уровне шаблона, а не на уровне отдельной ссылки. Поэтому она затрагивает все QR-коды, созданные на основе отредактированного шаблона.
* QR-коды, созданные с помощью Smart Script, нельзя настроить.

**Чтобы настроить вид QR-кода**:

1. На дэшборде AppsFlyer перейдите в раздел **Интерфейсы и диплинкинг** > **Управление OneLink**.
2. Выберите шаблон, который нужно изменить, и нажмите **Настроить QR-код**.  
   Откроется редактор QR-кодов.
3. Enter the URL where your logo is hosted. For example: https://yourbrand.com/logo.png.

   Требования к логотипу:

   * Формат PNG или JPG
   * Квадратный или круглый с прозрачным фоном
   * Минимальный размер: 400 x 400 пикс.
   * Для печати используйте изображение с максимальным разрешением
4. Задайте цвет QR-кода.
5. Нажмите **Сохранить**.

</Accordion>

<div id="measure-qrtoapp-conversions" />

<Accordion title="Измеряйте конверсии по QR в приложение">

Вы можете измерить эффективность вашего QR-кода и его размещения в различных рекламных объявлениях/медиа-источниках, сравнивая показы (для просмотра страниц на ПК), клики (для сканирования QR-кода) и установки приложений.

**Для измерения конверсий по QR в приложение**:

1. В AppsFlyer проверьте обзорный дэшборд или другие инструменты аналитики AppsFlyer и запишите общее количество **кликов** и **установок** с помощью медиа-источника QR-кода (например, **desktop\_web**).
2. Запишите общее количество просмотров страницы (показов) с помощью программы веб-аналитики.
3. Измеряйте эффективность:
   * <Anchor target="_blank" href="/marketers/ru/docs/about-conversion-rates#этапы-маркетинговой-воронки-и-коэффициенты-конверсии-1">Коэффициент кликабельности</Anchor>
   * <Anchor target="_blank" href="/marketers/ru/docs/about-conversion-rates#этапы-маркетинговой-воронки-и-коэффициенты-конверсии-1">Конверсия кликов в установки</Anchor>

</Accordion>

<div id="best-practices" />

<Accordion title="Практические рекомендации">

Ниже приведены советы по максимизации конверсий по QR в приложение.

* Для настольных компьютеров, если вы используете ручную настройку QR-кода, создайте отдельную страницу на своем сайте для размещения QR-кода.
  * Выберите последний фрагмент URL для страницы, например **/app**, **/download-app** или **/mobile-app**.
  * Сделайте страницу доступной для просмотра только на ПК / большой ширине экрана.
* Для всех объявлений:
  * Сделайте QR-код в своих объявлениях крупным и с высоким разрешением, чтобы его можно было легко отсканировать.
  * Добавьте расположенные на видном месте значки **Скачать из App Store** и **Скачать из Google Play** в качестве визуальных триггеров (не как ссылки).
  * Подумайте о том, чтобы добавить инструкции по сканированию QR-кода.
* Уже пользуетесь OneLink? В *другие* пользовательские ссылки OneLink, используемые в электронных письмах и т. д., добавьте параметр **af\_web\_dp**, значением которого будет URL-адрес страницы, содержащей QR-код. В результате пользователи настольных компьютеров переходят по ссылке на веб-страницу, а не в магазин приложений.

  <Image align="center" alt="" src="https://files.readme.io/1b92d842ac77121e9a5d0e8e2a03fd07fb3e1f05ad231b3954ff0925f8d4b56f-360012661797.jpg" />

</Accordion>

<div id="faq" />

## Часто задаваемые вопросы

В этом разделе вы найдете список часто задаваемых вопросов о QR-кодах.

<div id="qr-with-long-links-vs-short-links---is-there-any-difference" />

<Accordion title="Создание QR-кодов для длинных ссылок и коротких ссылок — есть ли разница?">

Ваш QR-код будет работать как с длинным, так и с коротким URL-адресом. Однако если вы используете короткий URL-адрес, вы сможете обновлять параметры и поведение ссылки через дэшборд OneLink (в разделе Link Management или Bulk Links) без необходимости заменять опубликованный QR-код — поскольку сам короткий URL-адрес остается неизменным.

* **Короткие URL-адреса:** Если вы измените параметры в конфигурации короткого URL-адреса, QR-код останется прежним. Публиковать его заново не нужно.
* **Длинные URL-адреса (например, Smart Script):** Если вы измените параметры в длинном URL-адресе, QR-код также изменится. После публикации вы не сможете удаленно обновить содержимое URL-адреса — потребуется сгенерировать и распространить новый QR-код.

**Совет:** Если создать QR-код с помощью короткого URL-адреса, позже можно будет изменить параметры и поведение ссылки без повторной генерации QR-кода.

</Accordion>

<div id="can-you-create-a-qr-code-and-change-the-behavior-behind-it-retroactively-after-printing-the-qr-for-example" />

<Accordion title="Можно ли создать QR-код и позже изменить его поведение, например после печати?">

Да, можно — если QR-код основан на коротком URL-адресе OneLink, который можно редактировать (например, созданном через интерфейс OneLink). **QR-код — это визуальное представление URL-адреса, который находится за ним**.  Изменение самого URL-адреса приведет к созданию нового соответствующего QR-кода (например, QR-код для mike.onelink.me/123A/shorturl отличается от QR-кода для mike.onelink.me/123A/example).

Однако, поскольку короткий URL-адрес OneLink является хешированным URL-адресом, его параметры и правила перенаправления настраиваются на бэкенде и не отображаются в URL-адресе. Это означает, что вы можете сохранить тот же видимый URL-адрес и QR-код, редактируя его конфигурацию на бэкенде.

</Accordion>

<div id="what-appsflyer-options-are-available-for-generating-qr-codes" />

<Accordion title="Какие варианты AppsFlyer доступны для генерации QR-кодов?">

Доступны следующие варианты:

* **Через дэшборд AppsFlyer → интерфейс OneLink:**
  * Автоматически создает QR-код при создании ссылки
  * Динамическая настройка QR-кода
  * Можно экспортировать в формате SVG или PNG
  * На основе короткого URL-адреса
* **QR-код OneLink API v2:**
  * Следуйте <Anchor target="_blank" href="/marketers/ru/docs/set-up-smart-script-to-convert-web-visitors#qr-codes">инструкциям Smart Script для QR-кода</Anchor>.
* **Массовое создание QR-кодов (на странице «Массовые ссылки»):**
  * Перейдите к объявлению с QR-кодом.
  * Можно экспортировать в SVG или PNG
  * Поддерживает контекстное именование файлов
  * На основе коротких URL-адресов
* Чтобы проверить QR-код:
  * На основе динамически генерируемых длинных URL-адресов
  * QR-коды создаются соответствующим образом
  * **Чтобы настроить QR-код для конверсий из ПК в приложение**:

</Accordion>

<div id="can-you-bulk-create-qr-codes" />

<Accordion title="Можно ли массово создавать QR-коды?">

Да Это дает возможность получить такие данные:

* <Anchor target="_blank" href="/marketers/ru/docs/create-a-onelink-template#создание-шаблонов-onelink">Шаблон OneLink</Anchor> настроен.
* Создайте пользовательскую ссылку OneLink.

</Accordion>

<div data-zendesk-anchors="converting-mobile-nonmobile-and-offline-traffic-into-mobile-app-users=%D0%BF%D1%80%D0%B5%D0%BE%D0%B1%D1%80%D0%B0%D0%B7%D1%83%D0%B9%D1%82%D0%B5-%D0%BC%D0%BE%D0%B1%D0%B8%D0%BB%D1%8C%D0%BD%D1%8B%D0%B9-%D0%BD%D0%B5%D0%BC%D0%BE%D0%B1%D0%B8%D0%BB%D1%8C%D0%BD%D1%8B%D0%B9-%D0%B8-%D0%BE%D1%84%D0%BB%D0%B0%D0%B9%D0%BD-%D1%82%D1%80%D0%B0%D1%84%D0%B8%D0%BA-%D0%B2-%D0%BF%D0%BE%D0%BB%D1%8C%D0%B7%D0%BE%D0%B2%D0%B0%D1%82%D0%B5%D0%BB%D0%B5%D0%B9-%D0%BC%D0%BE%D0%B1%D0%B8%D0%BB%D1%8C%D0%BD%D0%BE%D0%B3%D0%BE-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D1%8F h_01HKWVMKP3QT59EXPHQEPHW8K9=%D0%BF%D1%80%D0%B5%D0%BE%D0%B1%D1%80%D0%B0%D0%B7%D1%83%D0%B9%D1%82%D0%B5-%D0%BC%D0%BE%D0%B1%D0%B8%D0%BB%D1%8C%D0%BD%D1%8B%D0%B9-%D0%BD%D0%B5%D0%BC%D0%BE%D0%B1%D0%B8%D0%BB%D1%8C%D0%BD%D1%8B%D0%B9-%D0%B8-%D0%BE%D1%84%D0%BB%D0%B0%D0%B9%D0%BD-%D1%82%D1%80%D0%B0%D1%84%D0%B8%D0%BA-%D0%B2-%D0%BF%D0%BE%D0%BB%D1%8C%D0%B7%D0%BE%D0%B2%D0%B0%D1%82%D0%B5%D0%BB%D0%B5%D0%B9-%D0%BC%D0%BE%D0%B1%D0%B8%D0%BB%D1%8C%D0%BD%D0%BE%D0%B3%D0%BE-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D1%8F h_01HKWWQXVC11E8M3NV3A03SWYD=qr-to-app-conversion manual-qr-code-setup=%D1%80%D1%83%D1%87%D0%BD%D0%B0%D1%8F-%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-qr-%D0%BA%D0%BE%D0%B4%D0%B0 h_01HKWWQXVCB96WDMBSE9WH9ZC5=%D1%80%D1%83%D1%87%D0%BD%D0%B0%D1%8F-%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-qr-%D0%BA%D0%BE%D0%B4%D0%B0 h_01HKWVMKP3R5C5FPH010ZJZAHS=customize-qr-code h_01HKWVMKP3XTF6NNPNM8J00NWD=measure-qrtoapp-conversions h_01HKWVMKP3P6FNRPP1X7ZTNH10=best-practices qr-code-%E2%80%93-faq=%D1%87%D0%B0%D1%81%D1%82%D0%BE-%D0%B7%D0%B0%D0%B4%D0%B0%D0%B2%D0%B0%D0%B5%D0%BC%D1%8B%D0%B5-%D0%B2%D0%BE%D0%BF%D1%80%D0%BE%D1%81%D1%8B h_01K42Q4QQVNQ4579CCM7QF7MQS=%D1%87%D0%B0%D1%81%D1%82%D0%BE-%D0%B7%D0%B0%D0%B4%D0%B0%D0%B2%D0%B0%D0%B5%D0%BC%D1%8B%D0%B5-%D0%B2%D0%BE%D0%BF%D1%80%D0%BE%D1%81%D1%8B qr-with-long-links-vs-short-links-%E2%80%93-is-there-any-difference=qr-with-long-links-vs-short-links---is-there-any-difference h_01K42Q4QQVKGQZKAS1PZ3B9H20=qr-with-long-links-vs-short-links---is-there-any-difference h_01K42Q4QQVTV0KP280D15JF7NB=can-you-create-a-qr-code-and-change-the-behavior-behind-it-retroactively-after-printing-the-qr-for-example h_01K42Q4QQVV1RZZXZK2Y9W8R58=what-appsflyer-options-are-available-for-generating-qr-codes h_01K42Q4QQVZF4H8FYZCTJPR0RX=can-you-bulk-create-qr-codes" />
