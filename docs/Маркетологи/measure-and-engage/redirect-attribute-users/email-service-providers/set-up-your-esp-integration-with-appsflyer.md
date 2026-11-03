---
title: >-
  [Закрытое бета-тестирование – специальный доступ] Настройте интеграцию ESP с
  AppsFlyer
metadata:
  keywords:
    - Premium
    - Marketers
    - OneLink
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-asaf-mashiah
    - Marketers
    - OneLink
  created_at: '2024-07-24T14:10:54Z'
  edited_at: '2026-09-02T00:33:27Z'
  id: 26967438815377
  locale: ru
  section: Email service providers
  section_id: 6551247620881
  url: https://support.appsflyer.com/hc/ru/articles/26967438815377
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **Краткий обзор:** Настройте интеграцию ESP с AppsFlyer, чтобы обеспечить бесшовный и безопасный диплинкинг в ваших email-кампаниях для повышения вовлечённости пользователей и коэффициента конверсии.

## <Image alt="ESP final main KB image.png" src="https://files.readme.io/f14a193bb8d303adb93c01b33dcafba9053359fd92a187378cd324544a94dc88-27434531852049.png" width="613px" />

## Об интеграции AppsFlyer с ESP

Маркетологи часто используют провайдеров услуг электронной почты (ESP) для массовой рассылки в рамках email-кампаний. И хотя это должно быть простым процессом, создающим предсказуемый пользовательский путь, зачастую всё происходит совсем по-другому. Сложность заключается в том, как обычно ESP организуют работу с аналитику, что, как правило, нарушает работу диплинков и негативно сказывается на опыте мобильных пользователей. В результате пользователи иногда перенаправляются на мобильные веб-сайты вместо приложения, что препятствует конверсии.

AppsFlyer решает эту проблему с помощью решения для интеграции, которое позволяет AppsFlyer выступать в качестве посредника между сервером ESP и вашим доменным именем. Эта роль прокси позволяет предоставлять файлы ассоциаций (AASA / ссылки на активы), что облегчает диплинкинг. Кроме того, решение от AppsFlyer отправляет данные измерений обратно вашему ESP, позволяя вам эффективно отслеживать аналитику своих email-кампаний.

Настройте интеграцию ESP с AppsFlyer, чтобы обеспечить бесшовный и безопасный диплинкинг в ваших email-кампаниях для достижения оптимальной вовлечённости мобильных пользователей и увеличения коэффициента конверсии.

Решение AppsFlyer для интеграции ESP — это премиум-функция. Если вы хотите узнать больше или начать работу, свяжитесь с нами по адресу [hello@appsflyer.com](mailto:hello@appsflyer.com).

## Настройка интеграции

<span id="h_01J3JHFXRP57VS9D22FEWS2JZW"></span>В этом разделе описан процесс настройки интеграции AppsFlyer с ESP.

### Необходимые условия

Для того, чтобы начать настройку интеграции с ESP, вам необходима учётная запись у поддерживаемого ESP*. Оттуда вам потребуются следующие данные:

* Новый **домен отслеживания кликов** (описано в [Шаге 1.](#step-1-create-a-onelink-template-for-your-email-campaign))
* **Конечная точка ESP**: конечную точку предоставляет вам ESP, чтобы вы могли перенаправлять свои клики на его серверы. Пример структуры конечной точки ESP: esp.endpoint.com.
* **Специфические требования к интеграции ESP:**
  * **Emarsys** – попросите своего менеджера в Emarsys активировать HTTP-редирект.
  * **Blueshift** – попросите своего менеджера в Blueshift, изменить код состояния HTTP для кликов на 302 (по умолчанию: 307).

**Чтобы настроить интеграцию, выполните следующие действия:**

<div id="step-1-create-a-onelink-template-for-your-email-campaign" />

<Accordion title="Шаг 1. Создайте домен отслеживания кликов на своей платформе ESP (задача для IT/системного администратора)">

Домен отслеживания кликов (CTD) – это доменная часть URL, которая появляется в электронных сообщениях.   
Он состоит из субдомена и вашего основного домена, например mail.yourbrand.com. Разные ESP могут называть это брендингом ссылок, доменом отслеживания, доменом кликов, перезаписью ссылок, отслеживанием кликов, или «white label».

**Создание нового CTD обязательно**, даже если вы уже используете существующий. Это гарантирует отсутствие влияния на трафик текущих активных email-кампаний.

> 📘 **Примечания**
>
> * SSL-сертификат будет обработан AppsFlyer (на Шаге 3).
> * На этом этапе ссылки в электронных письмах, вероятно, не будут защищены, что означает, что префиксом URL будет HTTP, а не HTTPS. Эта проблема будет решена на [Шаге 5](#h_01JMYDQGPF3B9GNH0RY27JW3E4)).).).

</Accordion>

<div id="h_01JMYD02VRGT8353RDBARRPJ2M" />

<Accordion title="Шаг 2. Используйте шаблон OneLink для вашей email-кампании">

Создайте <Anchor target="_blank" href="/marketers/ru/docs/create-a-onelink-template#создание-шаблонов-onelink">шаблон OneLink</Anchor> и настройте ссылки Universal Links/App Links в разделе «**Когда приложение установлено**». Этот шаблон будет использоваться позже для создания ссылок OneLink для ваших email-кампаний.

*Если у вас уже есть существующий настроенный шаблон OneLink, который активирует ссылки Universal Links/App Links, вы можете использовать его.

</Accordion>

<div id="step-3-set-your-esp-integration-in-appsflyer" />

<Accordion title="Шаг 3. Настройте интеграцию вашего ESP в AppsFlyer">

Теперь пришло время настроить интеграцию вашего ESP в AppsFlyer. Пожалуйста, обратите внимание, что этот и следующий шаги («[Шаг 4. Настройте приложение](#step-2-configure-your-app-developer-task)») могут выполняться одновременно.

**Как настроить интеграцию с ESP в AppsFlyer:**

1. В **AppsFlyer**, в боковом меню выберите **Вовлечение (Engage)** > **Интеграция с ESP (ESP integration)**.

<Image alt="From Engage click ESP integration.png" src="https://files.readme.io/7b731446ce6158d5033020b63be5f386105e7899a8c1b291aa3cb13662a59ee5-27063684942481.png" width="196px" />

2. Выберите своего ESP.

<Image alt="select ESP.png" src="https://files.readme.io/526fed3aaf1e6fdbf2404243619159984e298752fdf5913fd3a65cc5a2ed9e1d-27086632495761.png" width="482px" />

3. Выберите шаблон OneLink, который вы хотите использовать для email-кампаний, затем нажмите **Далее**.

![select OneLink template.png](https://files.readme.io/4f96b999740be8596a424ce9108a8f702bda2a7ed025ec1869c553393432d87d-27086632499729.png)

4. Проверьте, чтобы у вас была активная учётная запись у выбранного ESP.

Вам понадобятся следующие данные от своего ESP:

* Домен отслеживания кликов, который вы создали на Шаге 1.
* Конечная точка ESP.

Нажмите **Далее**.

5. Введите свой домен отслеживания кликов и конечную точку ESP, затем нажмите **Проверить соединение**. Это нужно для проверки того, что домен отслеживания кликов указывает на введённую вами конечную точку.

![enter your ctd and esp endpoint.png](https://files.readme.io/d068b7de020bed7ba979b25e0fe866c40a118b00bbfde06a36a4c097485ac885-27086632503441.png)

По завершении нажмите **Далее**.

6. **Направление трафика ссылок на AppsFlyer:**

а. **Скопируйте и отправьте персонализированные предварительно подготовленные в AppsFlyer инструкции вашему IT-отделу или администратору домена.** Им нужно будет перенаправить трафик вашей email-кампании с серверов ESP на серверы AppsFlyer, обновив ваши записи DNS CNAME с новым доменом, предоставленным AppsFlyer.

В результате, каждый раз при нажатии на ссылку, клик будет перенаправляться в AppsFlyer, который, в свою очередь, перенаправит его на конечную точку ESP.

<Image alt="click to Af to ESP image.png" src="https://files.readme.io/8a53fa7e8e2574246ea6b1344cfec0ac2d8f319bb181f6956ecb6db5b05cd0c5-26982377140369.png" width="374px" />

б. После копирования и отправки инструкций нажмите **Готово**.

Ваша интеграция ESP была создана.

**Обратите внимание:**

* Ваша интеграции ESP находится на рассмотрении и начнёт работать только после сопоставления записи CNAME.
* После сопоставления может пройти до 24 часов, прежде чем новая интеграция начнёт работать и станет активной.

</Accordion>

<div id="step-2-configure-your-app-developer-task" />

<Accordion title="Шаг 6. Настройте ссылку OneLink для своей email-кампании в AppsFlyer">

Попросите своего разработчика реализовать следующие настройки в вашем приложении:

* [Настройка приложения для поддержки связанных доменов](#настройка-приложения-для-поддержки-связанных-доменов)
* [Настройка приложения для поддержки диплинкинга.](#настройка-приложения-для-поддержки-диплинкинга)
* [Настройка приложения для обработки веб-ссылок и ссылок на приложения](#настройка-приложения-для-обработки-веб-ссылок-и-ссылок-на-приложения)

#### **[Настройка приложения для поддержки связанных доменов](#настройка-приложения-для-поддержки-связанных-доменов).**

AppsFlyer размещает файлы ассоциации приложения, чтобы активировать <Anchor target="_blank" href="/marketers/ru/docs/appsflyer-knowledge-base-glossary#universal-links-универсальные-ссылки">Universal Links (iOS)</Anchor> и <Anchor target="_blank" href="/marketers/ru/docs/appsflyer-knowledge-base-glossary#android-app-link">App Links (Android)</Anchor>.

**Как настроить ваше приложение для доступа к файлам:**

**Для iOS**  
**Необходимое условие:** Версия SDK от <Anchor target="_blank" href="/marketers/ru/docs/appsflyer-ios-sdk-release-notes">v6.12.3</Anchor>  
Настройте ваше приложение для активации перенаправления по ссылкам Universal Link из сообщения электронной почты в своё приложение.  
Подробнее о настройке <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_ios_init_setup#procedures-for-ios-universal-links">Universal links</Anchor>.  
**Примечание^** Домен отслеживания кликов должен быть добавлен к текущим доменам, уже определённым в связанных доменах.

**Для Android**  
**Необходимое условие:** Версия SDK от **v6.12.5**  
Настройте ваше приложение для активации перенаправления по ссылкам App Link для Android из сообщения электронной почты в своё приложение. Подробнее о настройке <Anchor target="_blank" href="/marketers/ru/docs/appsflyer-knowledge-base-glossary#universal-links-универсальные-ссылки">App links</Anchor> для Android.  
**Примечание^** Домен отслеживания кликов должен быть добавлен к текущим доменам, уже определённым в файле манифеста приложения (AndroidManifest.xml).


#### **Настройка приложения для поддержки диплинкинга.**

Когда пользователь нажимает на ссылку App Link или Universal Link, должно открыться приложение.

**Чтобы дать приложению возможность извлекать OneLink за доменом записи клика и разрешать диплинки:**

1. Предоставьте домен записи клика в resolveDeepLinkURLs в API SDK. Этот API должен быть вызван перед инициализацией SDK.

* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_ios_esp_2_setup">Инструкция для IOS</Anchor>.
* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_android_esp_2_setup#flow-description">Инструкция для Android</Anchor>.

2. Используйте <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_work_flow#implement-unified-deep-linking-udl">Унифицированный API для диплинкинга</Anchor>, чтобы получать параметры диплинков и обрабатывать данные диплинков.


#### **Настройка приложения для обработки веб-ссылок и ссылок на приложения**

Предоставленный код предназначен для управления функциональностью обёрнутых ссылок в рамках email-кампании и направлен, в частности, на два вида: веб-ссылки, предназначенные для открытия веб-сайта, и ссылки, предназначенные для открытия приложения через Universal Link или App link.  
Дополнительная информация для разработчиков ниже:

* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_ios_esp_2_setup">Диплинкинг для iOS – ESP 2.0</Anchor>
* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_android_esp_2_setup">Диплинкинг для Android – ESP 2.0</Anchor>

</Accordion>

<div id="h_01JMYDQGPF3B9GNH0RY27JW3E4" />

<Accordion title="Шаг 5. Проверьте, чтобы на вашей платформе ESP было включено отслеживание кликов по SSL">

Выполните тестирование рассылки, чтобы проверить статус ссылки.   
Если ссылки CTD определяются как HTTP, свяжитесь с командой ESP, чтобы включить отслеживание кликов по SSL.   
Это обеспечит автоматическую конвертацию всех HTTP-ссылок в HTTPS.

Вы можете использовать следующий текст сообщения при обращении к вашему ESP:

Здравствуйте!  
 Включите, пожалуйста, отслеживание кликов по SSL для CTD XXX. В настоящее время он установлен на HTTP вместо HTTPS.   
Благодарим вас за помощь с этим обновлением.

</Accordion>

<div id="step-4-customize-the-onelink-link-for-your-email-campaign" />

<Accordion title="Шаг 8. Спокойно используйте ссылку в своих email-кампаниях">

**Как создать и настроить ссылку OneLink для своей кампании:**

1. В AppsFlyer создайте ссылку OneLink «Email-to-app» на странице управления OneLink (или вручную) в рамках шаблона OneLink, который вы создали ранее. Это ссылка, которую вы будете использовать в своей email-кампании, которая будет атрибутировать и перенаправлять пользователей в соответствии с вашими спецификациями. Узнайте, как создать ссылку <Anchor target="_blank" href="/marketers/ru/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#создание-ссылки-onelink">OneLink</Anchor>.

<Image alt="email-to-app.png" src="https://files.readme.io/4e30986e039ed4cc13b9963ef3d1bb7b933061176bed812dced45a7240023d54-27082280943761.png" width="652px" />

**Практические рекомендации:** используйте одно и то же название кампании как в email-кампании c ESP, так и в ссылках OneLink AppsFlyer, используемых в этой кампании.

</Accordion>

<div id="step-5-test-the-link" />

<Accordion title="Шаг 7. Проверьте интеграцию на вашей платформе ESP">

**Как протестировать интеграцию с созданной вами ссылкой OneLink:**

Вставьте URL-адрес OneLink в тестовое письмо, которое вы создаёте и отправляете себе с помощью редактора электронной почты от ESP.

* Со своего мобильного устройства откройте электронное письмо и нажмите на ссылку. Если у вас установлено приложение, оно откроется, и вы перейдёте к соответствующему контенту. Кроме того, на дэшборде AppsFlyer, а также на вашем аналитическом дэшборде ESP должен появиться мобильный клик, атрибутированный к предоставленному медиаисточнику и кампании.
* Нажмите на веб-ссылку и убедитесь, что она перенаправляет к правильному месту.

Как только тест будет успешно пройдён, вы готовы.

</Accordion>

<div id="step-6-use-the-link-in-your-email-campaigns-then-measure-the-results-use-the-link-confidently-in-your-email-campaigns" />

<Accordion title="Шаг 8. Спокойно используйте ссылку в своих email-кампаниях">

Отлично! Теперь вы можете использовать ссылки в своих email-кампаниях. После этого вы можете просмотреть результаты кампании на своих дэшбордах у ESP или AppsFlyer.

</Accordion>

*Эта интеграция поддерживает следующие ESP: Blueshift, Braze, CleverTap, Customer.io, Emarsys, Expert Sender, Klaviyo, MailExpress, MailGun, Moengage, RDStation, Reteno, Sailthru, Sendgrid, Sparkpost и т. д. См. полный список <Anchor target="_blank" href="/marketers/ru/docs/email-service-provider-esp-integration-guide">здесь</Anchor>. См. полный <Anchor target="_blank" href="/marketers/ru/docs/email-service-provider-esp-integration-guide">список</Anchor>.

## Часто задаваемые вопросы

<div id="do-i-need-to-create-an-ssl-certificate-at-any-point" />

<Accordion title="Нужно ли мне в какой-либо момент создавать SSL-сертификат?">

Нет, AppsFlyer создает SSL-сертификат для вас.

</Accordion>

<div id="if-i-have-the-appsflyer-esp-integration-and-sdk-implemented-for-basic-onelink-deep-linking-do-i-need-to-add-both-the-onelink-domain-and-the-esp-click-tracking-domain-to-ios-associated-domains" />

<Accordion title="Если у меня настроены интеграция ESP AppsFlyer и SDK для базового диплинкинга OneLink, нужно ли добавлять и домен OneLink, и домен отслеживания кликов ESP в iOS Associated Domains?">

* Да Да При настройке универсальных ссылок/App Links ESP и OneLink для диплинкинга необходимо зарегистрировать оба домена в entitlement Associated Domains вашего приложения:
  * **Домен OneLink** — требуется для стандартного диплинкинга с AppsFlyer.
  * **Домен отслеживания кликов ESP** — требуется, чтобы ссылки в электронных письмах, отправленных вашим ESP (например, Braze, Emarsys), распознавались и корректно обрабатывались диплинкингом.
* **Кто размещает файл AASA для домена отслеживания кликов?**  
  В этой конфигурации AppsFlyer размещает файл AASA для домена отслеживания кликов, используемого в ссылках в электронных письмах ESP. Вам нужно только добавить этот домен в связанные домены вашего приложения, и вам не придется самостоятельно управлять размещением AASA.

</Accordion>

<div data-zendesk-anchors="overview=%D0%BE%D0%B1-%D0%B8%D0%BD%D1%82%D0%B5%D0%B3%D1%80%D0%B0%D1%86%D0%B8%D0%B8-appsflyer-%D1%81-esp h_01J6RXTXCS7WC0P5X4J96T8JAP=%D0%BE%D0%B1-%D0%B8%D0%BD%D1%82%D0%B5%D0%B3%D1%80%D0%B0%D1%86%D0%B8%D0%B8-appsflyer-%D1%81-esp h_01J3JHJCCASM6E5QYJB5VHQ8HK=%D0%BE%D0%B1-%D0%B8%D0%BD%D1%82%D0%B5%D0%B3%D1%80%D0%B0%D1%86%D0%B8%D0%B8-appsflyer-%D1%81-esp set-up-your-esp-integration-with-appsflyer=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-%D0%B8%D0%BD%D1%82%D0%B5%D0%B3%D1%80%D0%B0%D1%86%D0%B8%D0%B8 h_01J3JHFRGA6BTMWSK7EEEVGS6T=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-%D0%B8%D0%BD%D1%82%D0%B5%D0%B3%D1%80%D0%B0%D1%86%D0%B8%D0%B8 prerequisites=%D0%BD%D0%B5%D0%BE%D0%B1%D1%85%D0%BE%D0%B4%D0%B8%D0%BC%D1%8B%D0%B5-%D1%83%D1%81%D0%BB%D0%BE%D0%B2%D0%B8%D1%8F h_01J3JJ74GYF5AJT9R2P2CXDXE1=%D0%BD%D0%B5%D0%BE%D0%B1%D1%85%D0%BE%D0%B4%D0%B8%D0%BC%D1%8B%D0%B5-%D1%83%D1%81%D0%BB%D0%BE%D0%B2%D0%B8%D1%8F h_01J3W0Z161XE7BKMMR62SEEZN7=step-1-create-a-onelink-template-for-your-email-campaign h_01JMYJG3CTGE9Y3SBFAECV326G=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%87%D0%B0%D0%BD%D0%B8%D1%8F h_01J3W0Z161T0D075HPE3Y8H3J4=step-3-set-your-esp-integration-in-appsflyer h_01J3W0Z1613XPYM75GH65R793W=step-2-configure-your-app-developer-task configure-your-app-to-support-associated-domains=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D1%8F-%D0%B4%D0%BB%D1%8F-%D0%BF%D0%BE%D0%B4%D0%B4%D0%B5%D1%80%D0%B6%D0%BA%D0%B8-%D1%81%D0%B2%D1%8F%D0%B7%D0%B0%D0%BD%D0%BD%D1%8B%D1%85-%D0%B4%D0%BE%D0%BC%D0%B5%D0%BD%D0%BE%D0%B2 h_01J3W8XR5QS227XNCD453RWYZ9=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D1%8F-%D0%B4%D0%BB%D1%8F-%D0%BF%D0%BE%D0%B4%D0%B4%D0%B5%D1%80%D0%B6%D0%BA%D0%B8-%D1%81%D0%B2%D1%8F%D0%B7%D0%B0%D0%BD%D0%BD%D1%8B%D1%85-%D0%B4%D0%BE%D0%BC%D0%B5%D0%BD%D0%BE%D0%B2 configure-your-app-to-support-deep-linking=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D1%8F-%D0%B4%D0%BB%D1%8F-%D0%BF%D0%BE%D0%B4%D0%B4%D0%B5%D1%80%D0%B6%D0%BA%D0%B8-%D0%B4%D0%B8%D0%BF%D0%BB%D0%B8%D0%BD%D0%BA%D0%B8%D0%BD%D0%B3%D0%B0 h_01J3WS4QWMRT8KSW6J3QHXM9TQ=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D1%8F-%D0%B4%D0%BB%D1%8F-%D0%BF%D0%BE%D0%B4%D0%B4%D0%B5%D1%80%D0%B6%D0%BA%D0%B8-%D0%B4%D0%B8%D0%BF%D0%BB%D0%B8%D0%BD%D0%BA%D0%B8%D0%BD%D0%B3%D0%B0 h_01J3W8Y7FMSWPG7MFF6FMSXFM3=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D1%8F-%D0%B4%D0%BB%D1%8F-%D0%BF%D0%BE%D0%B4%D0%B4%D0%B5%D1%80%D0%B6%D0%BA%D0%B8-%D0%B4%D0%B8%D0%BF%D0%BB%D0%B8%D0%BD%D0%BA%D0%B8%D0%BD%D0%B3%D0%B0 ::250c928e=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D1%8F-%D0%B4%D0%BB%D1%8F-%D0%BE%D0%B1%D1%80%D0%B0%D0%B1%D0%BE%D1%82%D0%BA%D0%B8-%D0%B2%D0%B5%D0%B1-%D1%81%D1%81%D1%8B%D0%BB%D0%BE%D0%BA-%D0%B8-%D1%81%D1%81%D1%8B%D0%BB%D0%BE%D0%BA-%D0%BD%D0%B0-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D1%8F configure-your-app-to-handle-weblinks-and-application-links=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D1%8F-%D0%B4%D0%BB%D1%8F-%D0%BE%D0%B1%D1%80%D0%B0%D0%B1%D0%BE%D1%82%D0%BA%D0%B8-%D0%B2%D0%B5%D0%B1-%D1%81%D1%81%D1%8B%D0%BB%D0%BE%D0%BA-%D0%B8-%D1%81%D1%81%D1%8B%D0%BB%D0%BE%D0%BA-%D0%BD%D0%B0-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D1%8F h_01J3WS4QWMSKZ33APWFR8CG5TZ=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D1%8F-%D0%B4%D0%BB%D1%8F-%D0%BE%D0%B1%D1%80%D0%B0%D0%B1%D0%BE%D1%82%D0%BA%D0%B8-%D0%B2%D0%B5%D0%B1-%D1%81%D1%81%D1%8B%D0%BB%D0%BE%D0%BA-%D0%B8-%D1%81%D1%81%D1%8B%D0%BB%D0%BE%D0%BA-%D0%BD%D0%B0-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D1%8F h_01J3W8ZMHSXQGJPQEVR62Q28X9=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D1%8F-%D0%B4%D0%BB%D1%8F-%D0%BE%D0%B1%D1%80%D0%B0%D0%B1%D0%BE%D1%82%D0%BA%D0%B8-%D0%B2%D0%B5%D0%B1-%D1%81%D1%81%D1%8B%D0%BB%D0%BE%D0%BA-%D0%B8-%D1%81%D1%81%D1%8B%D0%BB%D0%BE%D0%BA-%D0%BD%D0%B0-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D1%8F h_01J3W0Z1616GFFYCS7WPTNCCHT=step-4-customize-the-onelink-link-for-your-email-campaign h_01J3W0Z161M9NDXAN0KZFA9J4G=step-5-test-the-link h_01J3W0Z161RAYTKH3V9VBAADBM=step-6-use-the-link-in-your-email-campaigns-then-measure-the-results-use-the-link-confidently-in-your-email-campaigns faq=%D1%87%D0%B0%D1%81%D1%82%D0%BE-%D0%B7%D0%B0%D0%B4%D0%B0%D0%B2%D0%B0%D0%B5%D0%BC%D1%8B%D0%B5-%D0%B2%D0%BE%D0%BF%D1%80%D0%BE%D1%81%D1%8B h_01K3R6V0K31816PVY95X5WZC4C=%D1%87%D0%B0%D1%81%D1%82%D0%BE-%D0%B7%D0%B0%D0%B4%D0%B0%D0%B2%D0%B0%D0%B5%D0%BC%D1%8B%D0%B5-%D0%B2%D0%BE%D0%BF%D1%80%D0%BE%D1%81%D1%8B h_01K3R6THWT2MCCJHPSXPBAVT8Y=do-i-need-to-create-an-ssl-certificate-at-any-point h_01K3R6THWTG8G8PWPZ2ZRA1CSA=if-i-have-the-appsflyer-esp-integration-and-sdk-implemented-for-basic-onelink-deep-linking-do-i-need-to-add-both-the-onelink-domain-and-the-esp-click-tracking-domain-to-ios-associated-domains" />
