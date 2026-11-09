---
title: Общие сведения о функциях OneLink Smart Script
metadata:
  keywords:
    - OneLink
    - Adwords
    - Advertisers
    - referral
    - referal
    - landing
    - redirect
    - gclid
    - facebook
    - landing page
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
  created_at: '2018-12-12T16:32:47Z'
  edited_at: '2026-08-18T00:36:29Z'
  id: 360000677217
  locale: ru
  section: Web-to-app attribution
  section_id: 6551240476177
  url: https://support.appsflyer.com/hc/ru/articles/360000677217
---
> **Вкратце:** Используйте OneLink Smart Script, чтобы конвертировать посетителей мобильной версии сайта, приходящих из любых источников, в пользователей мобильного приложения и атрибутировать их.

<Image align="center" alt="7901_Smart_Script_flow_1920x1080_2__1_.png" src="https://files.readme.io/5181971c27e89974a86afeb83f48eb5c127b64765334bc3b5644ed47adb974e8-30193884510225.png" />

<div id="about-onelink-smart-script" />

## OneLink Smart Script

Прежде чем перейти на вашу страницу в магазине приложений, пользователи попадают на мобильную версию сайта либо органически, либо после взаимодействия с рекламными кампаниями. При этом имеют место два клика:

* переход на веб-страницу;
* переход с веб-страницы в магазин приложений.

В этом сценарии выполнять атрибуцию и диплинкинг довольно проблематично. Установки по пользователям, которые в итоге скачивают приложение, могут атрибутироваться не тому источнику или регистрироваться как органические. Это может происходить, даже если первый клик сделан в рекламной сети, поиске Google или в собственном медиа-источнике.

OneLink Smart Script решает эти проблемы следующим образом:

* На основе входящих URL-адресов, ведущих на веб-страницу, динамически генерирует уникальные исходящие длинные URL-адреса OneLink, перенаправляющие в магазин приложений.
* Обеспечивает точную атрибуцию при переходе из веба в приложение по всем медиа-источникам, включая рекламные сети, SRN, клики в Google и собственные медиа.
* Может использоваться для диплинкинга.
* Легко запускается на любой веб-странице или лендинге.
* Не требует использования смарт-баннеров.   
  **Примечание**: Смарт-баннеры могут быть отличным инструментом конверсии для многих вертикалей, и для их настройки не требуется привлечение разработчика, однако они добавляют в путь пользователя еще один шаг — сам баннер.
* Может быть настроен маркетологом в Google Tag Manager.

Существует две версии OneLink Smart Script:

<Anchor target="_blank" href="/marketers/ru/docs/set-up-smart-script-to-convert-web-visitors">**OneLink Smart Script V2 (рекомендуется)**</Anchor>:  Если вы впервые настраиваете OneLink Smart Script, лучше всего использовать эту версию. Ее можно настроить в пользовательском интерфейсе AppsFlyer, она упростит работу разработчикам, а также настроить ее можно с помощью Google Менеджера тегов.

<Anchor target="_blank" href="/marketers/ru/docs/legacy-onelink-smart-script-v1-setup">**OneLink Smart Script V1 (устарело)**</Anchor>: Если у вас уже настроен Onelink Smart Script, используйте документацию к этой версии, чтобы поддерживать и редактировать этот скрипт. **Примечание**: Хотя это и не обязательно, рассмотрите возможность перехода на версию V2. 

<div id="note" />

> 📘 **Примечание:**
>
> Еще не определились, подходит ли вам OneLink Smart Script как решение? <Anchor target="_blank" href="/marketers/ru/docs/convert-your-mobile-web-visitors-to-app-users">Сравните</Anchor> OneLink Smart Script с другими Web-to-App решениями AppsFlyer.

<div id="examples" />

### Примеры

Приведенные в этом разделе примеры показывают, как использовать OneLink Smart Script для генерации исходящих ссылок OneLink, обеспечивающих точную атрибуцию или функциональность диплинкинга. Примеры по типам кампаний с конкретными медиа-источниками доступны в разделе <Anchor target="_blank" href="/marketers/ru/docs/set-up-smart-script-to-convert-web-visitors#примеры-использования">Примеры использования</Anchor>.

<div id="attribution" />

<Accordion title="Атрибуция">

Марк — маркетолог сети отелей. Он отправляет электронное письмо с рекламой отдыха в отеле в Орландо, штат Флорида. Ссылка в письме выглядит следующим образом:  https://hotel.me/pid=email&c=orlando

Ссылка перенаправляет пользователей на мобильный сайт отеля. Там пользователи видят кнопки, приглашающие их загрузить мобильное приложение отеля. OneLink Smart Script автоматически генерирует URL-адрес, который содержит те же параметры **pid** и **c**, что и исходная ссылка в письме. Ссылка выглядит следующим образом:  https://hotel.onelink.me/Ac4G?pid=email&c=orlando

Когда в мобильной версии сайта пользователь нажимает кнопку для скачивания приложения, установка приложения атрибутируется рассылке Марка по Орландо.

</Accordion>

<div id="deep-linking" />

<Accordion title="Диплинкинг">

Эмма получает письмо с рекламой отдыха в отеле в Орландо, штат Флорида.

Ссылка в письме выглядит следующим образом: https://hotel.me?type=email&campaign=Florida&city=orlando

При клике ссылка перенаправляет ее на мобильную версию сайта. Здесь она видит кнопки для скачивания мобильного приложения отеля. OneLink Smart Script автоматически генерирует URL-адрес, который содержит те же параметры **pid** и **c**, что и исходная ссылка в письме. Ссылка выглядит следующим образом: https://hotel.onelink.me/Ac4G?pid=email&c=Florida&deep_link_value=orlando

**При нажатии кнопки в мобильной версии сайта Эмма попадает в магазин приложений. А когда она скачивает и запускает приложение — перенаправляется по диплинку на страницу приложения, посвященную отдыху в Орландо.**

<div id="note-1" />

> 📘 **Примечание:**
>
> Диплинкинг выполняется в соответствии с настройками приложения, заданными разработчиком приложения. <Anchor target="_blank" href="/marketers/ru/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#создание-ссылки-onelink">Подробнее</Anchor>.

</Accordion>

<div data-zendesk-anchors="about-onelink-smart-script=onelink-smart-script h_01HE7RW9G26CNME9TP350GFGS4=onelink-smart-script h_01HE7RW9G2BV2NFJ0YZ9QKAA2V=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%87%D0%B0%D0%BD%D0%B8%D0%B5 examples=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%80%D1%8B h_01HE7RW9G2WBZ1A0RS66CJ7BNH=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%80%D1%8B h_01HE7RW9G24Y604NTZFGKJJXSS=attribution h_01HE7RW9G2ZDDWE1M1B2G175ZF=deep-linking h_01HE7RW9G3W5GKQ2CD2BZW8YAW=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%87%D0%B0%D0%BD%D0%B8%D0%B5-1" />
