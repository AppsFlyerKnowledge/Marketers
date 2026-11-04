---
title: Реализация Android OAID в SDK
metadata:
  keywords:
    - China
    - Marketers
    - Web Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-guy-sarfatty
    - Marketers
    - Web Attribution
  created_at: '2020-02-27T20:21:05Z'
  edited_at: '2024-06-13T19:08:27Z'
  id: 360006278797
  locale: ru
  section: Android platform
  section_id: 6551190827921
  url: https://support.appsflyer.com/hc/ru/articles/360006278797
---
> **Краткий обзор.** Собирайте OAID Android, чтобы атрибутировать установки из сторонних магазинов приложений для Android.

<div id="about-oaid" />

## Об OAID

Открытый анонимный идентификатор устройства (OAID) — это настраиваемый пользователем уникальный идентификатор для устройств Android. Он был представлен Альянсом безопасности мобильной связи (MSA), Китайским научно-исследовательским институтом информации и связи и производителями устройств в качестве сохраняющей конфиденциальность альтернативы не предусматривающим возможность сброса идентификаторам устройств, таким как таким как IMEI.

OAID обычно используют для измерения рекламы и атрибуции установок на устройствах, где сервисы Google Play недоступны (то есть где отсутствует рекламный идентификатор Google).

<span id="supported-devices"></span>OAID можно считать на всех устройствах, использующих SDK, предоставленный MSA, или на устройствах Huawei, использующих SDK Huawei Mobile Service (HMS) Core.

<div id="integration" />

## Интеграция

Интеграция OAID состоит из 3 этапов:

1. Интеграция SDK для генерации и предоставления OAID (либо SDK MSA, либо SDK Huawei HMS).
2. Интеграция модуля плагина OAID AppsFlyer.
3. Интеграция SDK AppsFlyer.

**Примечание**.

* Для приложений, предназначенных для использования в Китае, необходимо использовать SDK MSA.
* Для приложений, предназначенных для использования на устройствах Huawei по всему миру, следует использовать библиотеку Huawei HMS.

<div id="msa-sdk" />

<Accordion title="SDK MSA">

**Для интеграции и использования SDK MSA**:

1. Следуйте инструкциям на [сайте MSA](http://www.msa-alliance.cn/col.jsp?id=120), чтобы зарегистрировать свое приложение.
   * Регистрация позволит вам загрузить SDK.
   * В процессе регистрации вы получаете файл сертификата, который необходимо добавить в приложение.
2. Скажите своим разработчикам, чтобы они следовали <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/oaid#msa-sdk-integration">инструкциям по интеграции</Anchor>.

</Accordion>

<div id="huawei-hms-sdk" />

<Accordion title="SDK Huawei HMS">

**Для интеграции и использования SDK Huawei HMS**:

* Скажите своим разработчикам, чтобы они следовали <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/oaid#huawei-hms-sdk-integration">инструкциям по интеграции</Anchor>.

</Accordion>

<div id="additional-information" />

## Дополнительные сведения

<div id="opting-out-of-oaid-collection" />

<Accordion title="Отказ от сбора OAID">

После завершения интеграции OAID SDK пытается собрать OAID автоматически. Если вы хотите запретить сбор OAID для определенных пользователей, скажите разработчику, чтобы он использовал следующее:

<Tabs>
<Tab title="Android">

<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setcollectoaid">setCollectOAID(false) API</Anchor> или <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#setdisableadvertisingidentifiers">setDisableAdvertisingIdentifiers</Anchor>

</Tab>

<Tab title="Unity">

<Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/api#setcollectoaid">setCollectOAID(false) API</Anchor> или <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/api#setdisableadvertisingidentifiers">setDisableAdvertisingIdentifiers</Anchor>

</Tab>
</Tabs>

<div id="setting-oaid-manually" />

<Accordion title="Настройка OAID вручную">

Если ваше приложение уже собирает OAID, вы можете пропустить интеграцию плагина OAID AppsFlyer и просто задать значение OAID в SDK AppsFlyer вручную, используя <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/oaid#setting-oaid-manually">API setOaidData</Anchor>.

</Accordion>

</Accordion>

<div data-zendesk-anchors="about-oaid=%D0%BE%D0%B1-oaid h_01HG8PXBZS1SN3SY3AAH1EKMNP=%D0%BE%D0%B1-oaid integration=%D0%B8%D0%BD%D1%82%D0%B5%D0%B3%D1%80%D0%B0%D1%86%D0%B8%D1%8F h_01HG8PXBZS26P9X1TQ7J4WQNF5=%D0%B8%D0%BD%D1%82%D0%B5%D0%B3%D1%80%D0%B0%D1%86%D0%B8%D1%8F h_01HG8PXBZSM0QYQE4C9S1FBFB1=msa-sdk h_01HG8PXBZS3HP9X1AZ7HQ8C34Y=huawei-hms-sdk additional-information=%D0%B4%D0%BE%D0%BF%D0%BE%D0%BB%D0%BD%D0%B8%D1%82%D0%B5%D0%BB%D1%8C%D0%BD%D1%8B%D0%B5-%D1%81%D0%B2%D0%B5%D0%B4%D0%B5%D0%BD%D0%B8%D1%8F h_01HG8PXBZSW5HNTTDRQ7DFFF4D=%D0%B4%D0%BE%D0%BF%D0%BE%D0%BB%D0%BD%D0%B8%D1%82%D0%B5%D0%BB%D1%8C%D0%BD%D1%8B%D0%B5-%D1%81%D0%B2%D0%B5%D0%B4%D0%B5%D0%BD%D0%B8%D1%8F h_01HG8PXBZS8Z3MTQWFN5R6FFA8=opting-out-of-oaid-collection h_01HG8PXBZSYNS8R1PCW4YXHFBA=setting-oaid-manually" />
