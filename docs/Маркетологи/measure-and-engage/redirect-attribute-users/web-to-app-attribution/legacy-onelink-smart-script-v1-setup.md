---
title: '[Устаревшая версия] Настройка OneLink Smart Script V1'
deprecated: true
metadata:
  keywords:
    - OneLink
    - Advertisers
    - Developers
    - Marketers
    - Smart Banners and Scripts
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-asaf-mashiah
    - Marketers
    - Smart Banners and Scripts
  created_at: '2022-01-02T17:00:19Z'
  edited_at: '2026-09-02T00:33:55Z'
  id: 4415354290321
  locale: ru
  section: Web-to-app attribution
  section_id: 6551240476177
  url: https://support.appsflyer.com/hc/ru/articles/4415354290321
---
> **Вкратце:** Используйте OneLink Smart Script для конверсии посетителей мобильной версии сайта, приходящих из любых источников, в пользователей мобильного приложения, и их атрибуции. **Примечание**: Хотя это и не обязательно, рекомендуем перейти на <Anchor target="_blank" href="/marketers/ru/docs/set-up-smart-script-to-convert-web-visitors">OneLink Smart Script V2</Anchor>.

<Image align="center" alt="7901_Smart_Script_flow_1920x1080_2__1_.png" src="https://files.readme.io/5181971c27e89974a86afeb83f48eb5c127b64765334bc3b5644ed47adb974e8-30193884510225.png" />

<div id="setup" />

## Настройка

Существует две версии OneLink Smart Script:

<Anchor target="_blank" href="/marketers/ru/docs/set-up-smart-script-to-convert-web-visitors">**OneLink Smart Script V2 (рекомендуется)**</Anchor>:  Если вы впервые настраиваете OneLink Smart Script, лучше всего использовать эту версию. С ней проще работать разработчику, а также ее можно настроить с помощью Google Tag Manager. **Примечание**: Хотя это и не обязательно, рассмотрите возможность перехода на версию V2. 

**OneLink Smart Script V1 (устаревшая версия)**: Если у вас уже настроен OneLink Smart Script, используйте документацию по этой версии, чтобы поддерживать и редактировать этот скрипт. 

<div id="responsibilities" />

<Accordion title="Зоны ответственности">

| **Кто участвует**<ul><li>**Рекламодатель**:<ul><li>Определяет, что должен содержать исходящий URL-адрес. Сюда входят данные атрибуции, которые нужно добавить в ссылку, и данные, необходимые для диплинкинга. Либо путем обработки входящего URL-адреса, либо путем принудительной установки определенных значений.</li><li>Проверяет, что все кампании, ведущие на мобильный сайт, имеют входящие URL с параметрами, на которые работает скрипт.</li></ul></li><li>**Веб-разработчик**:<ul><li>Настраивает данные для инициализации скрипта.</li><li>Вводит сеттеры, необходимые для создания исходящих URL-адресов OneLink на основе параметров входящего URL-адреса, предоставленных маркетологом. Сюда входят обязательные и необязательные параметры.</li><li>Встраивает скрипт на сайт или определенные страницы.</li></ul></li></ul> |
| --- |
| **Требования**<ul><li>Аккаунт в AppsFlyer с хотя бы одним Приложение.</li><li><Anchor target="_blank" href="/marketers/ru/docs/create-a-onelink-template#создание-шаблонов-onelink">Шаблон OneLink</Anchor>, который выступает как значение [параметра OneLinkURL](/docs/legacy-onelink-smart-script-v1-setup#parameters).</li></ul> |

**Чтобы реализовать скрипт на веб-странице**:

1. Решите, какие параметры/значения должен содержать автоматически генерируемый исходящий URL-адрес OneLink. См. [список параметров](/docs/legacy-onelink-smart-script-v1-setup#parameters), которые можно использовать.
   * Убедитесь, что у всех кампаний с входящими URL-адресами есть параметры, с которыми работает скрипт (и которые можно подставить как параметры **pid** и **c**).
2. Предоставьте [список параметров](/docs/legacy-onelink-smart-script-v1-setup#parameters) веб-разработчику.
3. Попросите разработчика выполнить <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/onelink-smart-script">инструкции для разработчиков</Anchor> и внедрить скрипт, чтобы создавалась правильная исходящая ссылка.

</Accordion>

<div id="parameters" />

<Accordion title="Параметры">

<div id="parametersvalues-provided-to-the-developer-to-implement-the-smart-script" />

#### Параметры/значения, предоставляемые веб-разработчику для внедрения Smart Script

| Параметр/значение | Специфика | Запишите свои значения (для разработчика) |
| --- | --- | --- |
| oneLinkURL (обязательно) | <ul><li>Укажите домен шаблона OneLink + идентификатор шаблона. **Примечание.** Не пользовательский URL-адрес ссылки OneLink!</li><li>Пример: **yourbrand.onelink.me/A1b2**</li><li>Пример брендированного домена: **click.yourbrand.com/A1b2**</li></ul> |  |
| pidKeysList (медиаисточники) | <ul><li>Перечислите все параметры медиаисточника во входящем URL-адресе, которые будут подставлены как параметр медиаисточника (pid) в исходящий URL-адрес.</li><li>Пример: ['af\_pid', 'utm\_source']</li></ul> |  |
| pidOverrideList | <ul><li>Для медиаисточников, которые вы хотите изменить в исходящей ссылке, перечислите значения медиаисточника во входящем URL-адресе и укажите, на что их нужно заменить.</li><li>Пример: `{`<br />`'twitter': 'twitter_int',`<br />`'snapchat': 'snapchat_int',`<br />`'some_social_net': 'some_social_net_int'`<br />`}`</li></ul> |  |
| pidStaticValue | <ul><li>Укажите, каким должен быть ваш резервный медиаисточник "fallback".</li><li>Если параметр медиаисточника не найден в вашем pidKeysList, в исходящем URL-адресе в качестве медиаисточника (pid) используется pidStaticValue.</li><li>Пример: 'website' или 'landing\_page'</li></ul> |  |
| campaignKeysList (кампании) | <ul><li>Перечислите все параметры кампании во входящем URL-адресе, которые будут переданы как параметр кампании (c) в исходящем URL-адресе.</li><li>Пример: ['af\_campaign', 'utm\_campaign']</li></ul> |  |
| campaignStaticValue | <ul><li>Укажите, какой должна быть ваша резервная кампания.</li><li>Если параметр кампании не найден в вашем campaignKeysList, в исходящем URL-адресе в качестве кампании (c) используется campaignStaticValue.</li><li>Пример: 'website' или 'landing\_page'</li></ul> |  |
| gclIdParam | <ul><li>Укажите, как назвать параметр, который содержит <Anchor target="_blank" href="https://support.google.com/google-ads/answer/9744275?hl=en">GCLID</Anchor>.<br />**Важно!** Для отображения в отчетах AppsFlyer по сырым данным параметр должен быть одним из **af\_sub[1-5]**.</li></ul> |  |
| skipList | <ul><li>Перечислите строки в HTTP-реферере, которые отключают Smart Script для определенного клика (например, Twitter или Facebook). Если строки найдены, Smart Script не запускается. Это может быть полезно для таких SRN, как X Ads и Meta Ads, по которым уже зарегистрированы клики.</li><li>Если вы хотите, чтобы Smart Script всегда запускался, даже для SRN, попросите разработчика передать пустой список исключений.</li></ul> |  |
| Другие параметры запроса | <ul><li>Перечислите любые другие параметры, которые вы хотите включить в исходящий URL-адрес OneLink для атрибуции или диплинкинга.</li><li>Добавьте **deep\_link\_value** для диплинкинга.<ul><li>Помимо добавления параметра, вам и вашему разработчику нужно внедрить логику диплинкинга. <Anchor target="_blank" href="/marketers/ru/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#создание-ссылки-onelink">Подробнее</Anchor>.</li></ul></li><li>Вы можете либо использовать параметры из входящего URL-адреса, либо принудительно задать статическое значение.</li></ul> |  |

</Accordion>

<div id="use-cases" />

## Использование когорты

В следующих разделах представлены примеры использования Smart Script для некоторых распространенных сценариев кампаний / медиа-источников.

<div id="facebook-ads-crossplatform-attribution" />

<Accordion title="Meta ads — кроссплатформенная атрибуция">

Meta ads — это SRN, которая не использует внешние ссылки для атрибуции.

При первом запуске приложения AppsFlyer запрашивает у Meta, взаимодействовал ли пользователь ранее (в течение последних <Anchor target="_blank" href="/marketers/ru/docs/meta-ads-discrepancies#атрибуция-по-нажатиям-и-просмотрам">7 дней</Anchor>) с рекламным объявлением приложения. Если пользователь взаимодействовал с рекламным объявлением рекламодателя в Facebook, Meta выполняет самоатрибуцию. Meta ads также подразумевает кроссплатформенность, а это означает, что пользователь может взаимодействовать с кампаниями любого типа, мобильными и другими, на любой платформе, и при этом Meta ads выполняет атрибуцию самостоятельно.

**Действие**: Попросите разработчика использовать <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/onelink-smart-script#skip-clicks-from-twitter-or-facebook">метод skipList</Anchor>, чтобы отключить Smart Script для Meta ads (или любых других строк по вашему выбору). Если Meta или любая из строк в списке исключений присутствуют в HTTP-реферере клика, Smart Script возвращает `null`.

**Примечание**: на кроссплатформенную атрибуцию Meta может повлиять отказ пользователей предоставлять идентификатор устройства, как и ожидается у пользователей iOS 14 в 2021 году.

</Accordion>

<div id="google-ads-gclid-and-utm-parameters" />

<Accordion title="Google Ads — параметры GCLID и UTM">

Обычный процесс атрибуции установки для кампаний Google Ads (с параметром GCLID) требует, чтобы пользователи, кликнувшие по объявлению, перенаправлялись на URL-адрес страницы приложения в магазине.

Так как в данном случае вы перенаправляете лиды из Google Ads на веб-/лендинг-страницу, скрипт берет параметр GCLID из URL-адреса кампании установки Google Ads и добавляет его в исходящий URL-адрес в выбранный вами выходной параметр **af\_sub[1-5].** **Внимание!** Это относится к кампаниям установки. Для поисковых кампаний, не относящихся к ACI, то есть кампаний повторного вовлечения пользователей, Google может быть атрибутирован в качестве медиа-источника, несмотря на выходные данные Smart Script.

**Необходимое условие**: На дэшборде Google <Anchor target="_blank" href="https://support.google.com/analytics/answer/1033981?hl=en">включите автотеги</Anchor>.   
Если автоматическая пометка включена, URL-адрес содержит параметр *GCLID* .

**Чтобы настроить скрипт для Google Ads**:

1. Составьте список названий параметров медиаисточника и кампании, которые содержатся во входящих ссылках.  
   Например: **utm\_source** и **utm\_campaign**.
2. Выберите параметр в исходящем URL, который будет содержать GCLID.  
   Практические рекомендации: Выбирать **af\_sub[1-5]**, чтобы данные отображались в отчетах по сырым данным AppsFlyer.
3. Предоставьте его веб-разработчику в  [списке параметров.](/docs/legacy-onelink-smart-script-v1-setup#parameters)

**Результат**:

* Значения параметров медиаисточника и кампании (**utm\_source** и **utm\_campaign**) во входящей ссылке используются для заполнения значений параметров **pid** и **c** в исходящей ссылке.
* В исходящем URL-адресе значением параметра **af\_sub[1-5]** является GCLID.

**Чтобы уведомить Google Ads об этих установках:**

1. Получите данные GCLID из параметра **af\_sub[1-5]** через CSV или Push API в режиме реального времени для каждой установки.
2. Загрузите данные GCLID в Google либо <Anchor target="_blank" href="https://support.google.com/adwords/answer/7014069">вручную</Anchor>, либо через <Anchor target="_blank" href="https://developers.google.com/adwords/api/docs/guides/conversion-tracking#importing_conversions">Adwords API</Anchor>.

<div id="note" />

> 📘 **Примечание:**
>
> Это решение GCLID официально не поддерживается и не рекомендуется компанией Google. В случае, если Google прекратит использование параметра GCLID, мы изменим скрипт в соответствии с изменениями. Нажмите кнопку **Подписаться** в заголовке статьи, чтобы получать информацию об обновлении статьи или скрипта.

</Accordion>

<div id="srns-owned-media-and-other-media-source-links" />

<Accordion title="Ссылки в SRN, собственных медиа и других медиа-источниках">

<Anchor target="_blank" href="/marketers/ru/docs/self-reporting-networks-srns#srn-интегрированные-с-appsflyer">SRNs</Anchor>, такие как Snapchat или X Ads, работают иначе, чем Google Ads или кроссплатформенные решения, такие как Meta ads. Кампании этих SRN приводят ваших пользователей на веб-страницу / лендинг, и в ваш счет включаются клики от всех лидов, независимо от полученных мобильных пользователей.

Для этих SRN настройка скрипта такая же, как и для ссылок из собственных медиа или других медиа-источников, которые вы можете использовать.

**Чтобы настроить скрипт**:

1. Составьте список названий параметров для медиа-источников и кампаний, которые содержатся во входящих ссылках.
2. Предоставьте их [в списке параметров](/docs/legacy-onelink-smart-script-v1-setup#parameters) веб-разработчику.  
   Tип SRN/медиаисточника должен быть значением медиаисточника во входящем URL-адресе; скрипт находит его и использует как значение **pid** в исходящем URL-адресе OneLink за кнопкой загрузки на веб-странице/лендинге. Если вы хотите изменить исходящий **pid**, укажите в списке переопределения pid значение входящего источника медиатрафика и новое значение **pid**.

**Результат**: для этих SRN/медиаисточников значения параметров медиаисточника и кампании во входящей ссылке используются для заполнения значений параметров **pid** и **c** в исходящей ссылке.

<div id="example" />

> 📄 **Пример**
>
> **Входящий URL**: https://hotel.me/af_pid=twitter&af_c=big_social
>
> **Исходящий URL**: Нет исходящего URL.

</Accordion>

<div id="appsflyer-attribution-links" />

<Accordion title="Ссылки атрибуции AppsFlyer">

Ссылки атрибуции AppsFlyer можно использовать, когда медиа-источник является рекламной сетью, из которой пришел клик. При настройке такой ссылки в AppsFlyer вы можете добавить параметр ***пути URL-адреса перенаправления (af\_r)*** с нужным URL-путём на ваш мобильный сайт для атрибуции переходов из веб-кампании в приложение.

**Результат**: если во входящей ссылке есть параметры **af\_r** и **af\_redirect=true**, скрипт целевой страницы не вносит никаких изменений. Он оставляет прямые ссылки с веб-/целевой страницы на магазины приложений без изменений. 

<div id="example-1" />

> 📄 **Пример**
>
> **Входящий URL-адрес**: https://app.appsflyer.com/id123456789?pid=click_ad_network_int&c=orlando&af_redirect=true&af_r=hotel.me
>
> **Исходящий URL-адрес**: тот же

</Accordion>

<div id="desktop" />

<Accordion title="Десктоп">

Большинство вариантов использования в этой статье пользователей, пришедших с мобильных устройств. Поэтому, когда они перенаправляются с мобильного сайта в магазин приложений, они могут сразу скачать ваше приложение.

Однако пользователи настольных компьютеров не должны сразу же отправляться в магазин приложений, потому что их устройство (настольный компьютер или ноутбук) не совместимо с загрузкой мобильных приложений.

**Чтобы настроить скрипт для пользователей настольных компьютеров**:

* В вашем <Anchor target="_blank" href="/marketers/ru/docs/create-a-onelink-template#создание-шаблонов-onelink">шаблоне OneLink</Anchor> задайте URL-адрес назначения для параметра **При нажатии на ссылку на компьютере**. URL должен перенаправлять пользователей на специальную страницу / лендинг. Лендинг может содержать веб-форму, в которой они вводят свои данные, чтобы получить SMS или электронное письмо со ссылкой для загрузки приложения. Вы сами должны создать веб-форму и указать ее URL в скрипте.

**Результат:** Скрипт определяет устройство или платформу, на которой находится пользователь. Если это десктоп, скрипт создает исходящий URL-адрес OneLink, который перенаправляет пользователя на специальную страницу / лендинг.

См. также <Anchor target="_blank" href="/marketers/ru/docs/qr-to-app-conversion">Конверсия с ПК в приложение</Anchor>.

</Accordion>

<div id="limitations" />

<Accordion title="Характеристики и ограничения">

| Ограничение | Специфика |
| --- | --- |
| Менеджер тегов | Smart Script нельзя реализовать через менеджер тегов. См. <Anchor target="_blank" href="/marketers/ru/docs/set-up-smart-script-to-convert-web-visitors">OneLink Smart Script V2</Anchor> или <Anchor target="_blank" href="/marketers/ru/docs/smart-banners-mobile-web-to-app-for-marketers">Smart Banners</Anchor> в качестве альтернативного решения для атрибуции Web-to-app. |

</Accordion>

<div data-zendesk-anchors="setup=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0 h_01HDNWHSY8HM30HV1PAF5C3M4E=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0 h_01HDNWHSY8J65EB1RZCFP1606H=responsibilities h_01HDNWHSY8CH29FQ2V5DCG2XSP=parameters parametersvalues-provided-to-the-developer-to-implement-the-smart-script=%D0%BF%D0%B0%D1%80%D0%B0%D0%BC%D0%B5%D1%82%D1%80%D1%8B%D0%B7%D0%BD%D0%B0%D1%87%D0%B5%D0%BD%D0%B8%D1%8F-%D0%BF%D1%80%D0%B5%D0%B4%D0%BE%D1%81%D1%82%D0%B0%D0%B2%D0%BB%D1%8F%D0%B5%D0%BC%D1%8B%D0%B5-%D0%B2%D0%B5%D0%B1-%D1%80%D0%B0%D0%B7%D1%80%D0%B0%D0%B1%D0%BE%D1%82%D1%87%D0%B8%D0%BA%D1%83-%D0%B4%D0%BB%D1%8F-%D0%B2%D0%BD%D0%B5%D0%B4%D1%80%D0%B5%D0%BD%D0%B8%D1%8F-smart-script h_01HDNWHSY8WSPX47VB43MC516Q=%D0%BF%D0%B0%D1%80%D0%B0%D0%BC%D0%B5%D1%82%D1%80%D1%8B%D0%B7%D0%BD%D0%B0%D1%87%D0%B5%D0%BD%D0%B8%D1%8F-%D0%BF%D1%80%D0%B5%D0%B4%D0%BE%D1%81%D1%82%D0%B0%D0%B2%D0%BB%D1%8F%D0%B5%D0%BC%D1%8B%D0%B5-%D0%B2%D0%B5%D0%B1-%D1%80%D0%B0%D0%B7%D1%80%D0%B0%D0%B1%D0%BE%D1%82%D1%87%D0%B8%D0%BA%D1%83-%D0%B4%D0%BB%D1%8F-%D0%B2%D0%BD%D0%B5%D0%B4%D1%80%D0%B5%D0%BD%D0%B8%D1%8F-smart-script use-cases=%D0%B8%D1%81%D0%BF%D0%BE%D0%BB%D1%8C%D0%B7%D0%BE%D0%B2%D0%B0%D0%BD%D0%B8%D0%B5-%D0%BA%D0%BE%D0%B3%D0%BE%D1%80%D1%82%D1%8B h_01HDNWHSY8N77ZH4CK49ZQ2KZB=%D0%B8%D1%81%D0%BF%D0%BE%D0%BB%D1%8C%D0%B7%D0%BE%D0%B2%D0%B0%D0%BD%D0%B8%D0%B5-%D0%BA%D0%BE%D0%B3%D0%BE%D1%80%D1%82%D1%8B facebook-ads%E2%80%94crossplatform-attribution=facebook-ads-crossplatform-attribution h_01HDNWHSY85QFABA6FAX1XTEPE=facebook-ads-crossplatform-attribution google-ads%E2%80%94gclid-and-utm-parameters=google-ads-gclid-and-utm-parameters h_01HDNWHSY878JTPZSN719KF1Y5=google-ads-gclid-and-utm-parameters h_01HDNWHSY8BJH39TAN46W7HE4G=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%87%D0%B0%D0%BD%D0%B8%D0%B5 h_01HDNWHSY8NER2M8X4DGHCWYPJ=srns-owned-media-and-other-media-source-links h_01HDNWHSY828Q587S28GYB85VR=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%80 h_01HDNWHSY8K1AFSEA1RY04KXJ9=appsflyer-attribution-links h_01HDNWHSY8DDTA6VATN0XXBEY5=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%80-1 h_01HDNWHSY821DADGKATKH12PSJ=desktop h_01HDNWHSY80QA9CC4S2BPBTJYG=limitations" />
