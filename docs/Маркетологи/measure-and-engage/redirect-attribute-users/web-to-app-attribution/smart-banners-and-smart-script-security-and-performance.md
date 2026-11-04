---
title: Безопасность и производительность Smart Banners и Smart Script
metadata:
  keywords:
    - Marketers
    - Smart Banners and Scripts
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-asaf-mashiah
    - Marketers
    - Smart Banners and Scripts
  created_at: '2024-01-30T14:54:37Z'
  edited_at: '2026-09-02T00:34:06Z'
  id: 22082177372561
  locale: ru
  section: Web-to-app attribution
  section_id: 6551240476177
  url: https://support.appsflyer.com/hc/ru/articles/22082177372561
---
> **Кратко:** узнайте, как AppsFlyer проактивно решает ваши вопросы по безопасности Smart Banners и Smart Script.

В этом разделе вопросов и ответов мы обсуждаем распространенные вопросы об интеграции Smart Banners & Smart Script, уделяя особое внимание их воздействию на безопасность и скорость сайта.

<div id="smart-banners-api-security" />

## Безопасность API smart banners

<div id="what-data-does-the-smart-banner-capture-when-someone-clicks-or-views-it" />

<Accordion title="Какие данные собирает smart banner, когда пользователь просматривает его или кликает по нему?">

| вашего бизнеса | Специфика |
| --- | --- |
| IP-адрес клиента | IP-адрес используется для определения местоположения (страна, регион и штат) |
| Event Time (Время события) |  |
| User Agent. |  |
| Страница сайта | URL-адрес, с которого был выполнен вызов web SDK |
| Протокол HTTP | HTTP/HTTPS |
| Заголовки | Host, Content-type, Origin, Content-length, Encoding |
| Параметры OneLink |  |
| Параметры баннера | Настройки конфигурации баннера:<ul><li><Anchor target="_blank" href="/marketers/ru/docs/smart-banners-mobile-web-to-app-for-marketers#dismissal-behaviour">Поведение при закрытии</Anchor></li><li><Anchor target="_blank" href="/marketers/ru/docs/smart-banners-mobile-web-to-app-for-marketers#param-table">Входящие параметры</Anchor></li><li>параметры UTM</li><li>параметры AppsFlyer</li><li>параметры по умолчанию</li><li>другие параметры</li></ul> |

</Accordion>

<div id="what-api-calls-are-needed-to-show-a-smart-banner" />

<Accordion title="Какие вызовы API нужны для показа smart banner?">

* API для получения SDK из CDN, расположенной по адресу `https://websdk.appsflyersdk.com`.
* API для генерации ссылки, скрытой за CTA, расположенной по адресу `banner.appsflyer.com`. Этот API вызывается методом SDK [showBanner](https://dev.appsflyer.com/hc/docs/dl_smart_banner_v2#showbanner).
* API для получения креатива баннера из CDN, расположенной по адресу `creatives-cdn-appsflyer.com`.

</Accordion>

<div id="do-these-api-calls-include-an-identifier" />

<Accordion title="Содержат ли эти вызовы API идентификатор?">

Да Да Вызовы API используют уникальный web key клиента в качестве идентификатора, чтобы получать необходимые данные для показа баннера и генерировать URL-адрес OneLink для CTA баннера.

</Accordion>

<div id="is-it-possible-for-a-malicious-entity-to-change-the-url-or-alter-the-apis-web-key" />

<Accordion title="Может ли злоумышленник изменить URL-адрес или web key API?">

№ № Получить доступ к коду, который определяет web key, используемый в вызове API баннера, и изменить его невозможно. Это означает, что злоумышленники не могут манипулировать расчётом баннера и URL-адресом OneLink, генерируемым для CTA баннера.

</Accordion>

<div id="smart-banners-script-hosting-security" />

## Безопасность хостинга скрипта смарт-баннеров

<div id="can-clients-host-a-copy-of-the-smart-banner-script-on-their-server" />

<Accordion title="Могут ли клиенты размещать копию скрипта Smart Banner на своем сервере?">

Клиенты не могут размещать скрипт Smart Banners на своих серверах. Однако они могут использовать <Anchor target="_blank" href="/marketers/ru/docs/set-up-smart-script-to-convert-web-visitors?query=smart%20script">Smart Script</Anchor> для генерации URL-адресов OneLink и внедрения собственных креативов баннеров.

Используя Smart Script вместе с собственными баннерами, вы можете создавать пользовательские креативы, а также дополнительно сопоставлять и настраивать сгенерированные ссылки, устраняя необходимость внедрять SDK баннера на вашем сайте и выполнять внешние вызовы API.

</Accordion>

<div id="can-clients-host-their-own-code-and-still-use-banners" />

<Accordion title="Могут ли клиенты размещать собственный код и при этом использовать баннеры?">

Клиенты могут разрабатывать собственные баннеры, включая дизайн, разработку и интеграцию на сайте, а также использовать <Anchor target="_blank" href="/marketers/ru/docs/set-up-smart-script-to-convert-web-visitors?query=smart%20script">Smart Script</Anchor> для генерации ссылок для призыва к действию (CTA) в своих баннерах.

</Accordion>

<div id="can-smart-banners-be-supported-without-embedding-their-code-snippet-on-the-page" />

<Accordion title="Поддерживаются ли Smart Banners без встраивания их фрагмента кода на странице?">

* Клиенты могут использовать менеджеры тегов для вызова API Smart Banner в качестве альтернативы прямой интеграции фрагмента кода. Чтобы узнать больше о менеджерах тегов, см. <Anchor target="_blank" href="/marketers/ru/docs/smart-banners-website-code-implementation-for-marketers#внедрение-кода-веб-сайта">здесь.</Anchor>
* Запуск скрипта в iFrame не поддерживается.

</Accordion>

<div id="how-does-appsflyer-protect-your-banners-from-postsave-tampering" />

<Accordion title="Как AppsFlyer защищает ваши баннеры от изменений после сохранения">

При редактировании и сохранении креатива баннера в редакторе креативов AppsFlyer злоумышленник может попытаться перехватить запрос, получить над ним контроль и внедрить вредоносный код JavaScript.

Мы применяем несколько мер, чтобы защитить Smart Banners от возможных атак и предотвратить несанкционированное редактирование пользователями вне их собственной учетной записи.

* Наша команда безопасности проводит тесты и проверки, чтобы убедиться, что все наши сервисы (включая Smart Banners) защищены и не содержат уязвимостей.
* Мы регулярно проводим независимые и непредвзятые тесты на проникновение, чтобы обеспечить защиту и безопасность AppsFlyer.
* Внутри компании мы проверяем теги HTML и Script и очищаем их от любых вредоносных скриптов.

</Accordion>

<div id="do-smart-banners-use-cookies" />

<Accordion title="Используют ли Smart Banners файлы cookie?">

По умолчанию Smart Banners не используют файлы cookie. Однако мы предоставляем дополнительную конфигурацию для использования собственных файлов cookie для клиентов, которым нужна повышенная устойчивость (например, чтобы решить проблему нестабильности хранилища в Safari на iOS 26).

Владелец сайта должен явно <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_smart_banner_v2#set-storage-mode-optional">включить эту опцию</Anchor>. Если эта опция включена, владелец сайта также несет ответственность за обновление управления согласием на использование файлов cookie и уведомлений о конфиденциальности в соответствии с применимыми нормативными требованиями.

</Accordion>

<div id="smart-banners-performance" />

## Эффективность смарт-баннеров

<div id="does-the-smart-banner-web-sdk-impact-website-load-speed" />

<Accordion title="Влияет ли веб-SDK Smart Banner на скорость загрузки сайта?">

Хотя добавление на сайт любого дополнительного кода потенциально может повлиять на время загрузки, большая часть работы смарт-баннера выполняется на стороне сервера асинхронно и без блокировки загрузки страницы.

Кроме того, мы используем CDN, чтобы ускорить загрузку страниц и баннеров.

</Accordion>

<div id="can-you-share-some-metrics-regarding-banner-speed-performance" />

<Accordion title="Можете ли вы поделиться метриками производительности по скорости загрузки баннера?">

Скорость загрузки баннера варьируется и зависит от нескольких факторов, в том числе:

* Скорость интернета
* Качество соединения и тип подключения
* Производительность сайта и другие факторы.

Эти факторы вместе с минимальным временем отклика серверов AppsFlyer к браузерам учитываются при расчете времени загрузки баннера.

Поскольку указанные выше переменные не связаны с AppsFlyer, мы не можем указать точные сроки для полного сквозного процесса.

</Accordion>

<div id="how-can-i-actively-improve-the-banner-loading-time" />

<Accordion title="Как активно сократить время загрузки баннера?">

На время загрузки баннера влияет Largest Contentful Paint (LCP), который в первую очередь относится к изображению баннера. Чтобы повысить эффективность загрузки LCP, вы можете::

* Выбрать шаблон баннера меньшего размера.
* Уменьшите размер логотипа и фоновых изображений
  * Рассмотрите возможность заменить фоновое изображение сплошным цветом, чтобы сократить время загрузки ресурсов.
  * Используйте CDN для размещения изображений баннера, чтобы ускорить их загрузку.

* Используйте одинаковую насыщенность шрифта во всем баннере.

</Accordion>

<div id="smart-script-security-and-performance" />

## Безопасность и производительность Smart Script

<div id="does-smart-script-use-cookies" />

<Accordion title="Использует ли Smart Script файлы cookie?">

Нет, в нашем решении Smart Script мы не используем файлы cookie.

</Accordion>

<div id="does-smart-script-make-any-external-calls-to-generate-links" />

<Accordion title="Выполняет ли Smart Script внешние вызовы для создания ссылок?">

Нет, скрипт выполняется локально на сайте клиента, поэтому он не зависит от внешних вызовов, что делает его очень безопасным в использовании.

</Accordion>

<div id="is-there-a-download-time-associated-with-smart-script" />

<Accordion title="Связано ли со Smart Script какое-либо время загрузки?">

Вы можете встроить скрипт прямо на свой сайт, чтобы сократить время на его загрузку. Скрипт загружается быстро, поскольку не требует вызовов к серверу.

</Accordion>

<div data-zendesk-anchors="smart-banners-api-security=%D0%B1%D0%B5%D0%B7%D0%BE%D0%BF%D0%B0%D1%81%D0%BD%D0%BE%D1%81%D1%82%D1%8C-api-smart-banners h_01HNDDT0XHK5Y5NYTQMSXYSCZ4=%D0%B1%D0%B5%D0%B7%D0%BE%D0%BF%D0%B0%D1%81%D0%BD%D0%BE%D1%81%D1%82%D1%8C-api-smart-banners h_01HNDDT0XHY7BZNXA2CRT1W46F=what-data-does-the-smart-banner-capture-when-someone-clicks-or-views-it h_01HNDDT0XJGFJE3XBAXTE0C2K5=what-api-calls-are-needed-to-show-a-smart-banner h_01HNDDT0XJVX8KXSZC10GTJMCS=do-these-api-calls-include-an-identifier h_01HNDDT0XJ7MGPFSZKJ7YRZ2HJ=is-it-possible-for-a-malicious-entity-to-change-the-url-or-alter-the-apis-web-key smart-banners-script-hosting-security=%D0%B1%D0%B5%D0%B7%D0%BE%D0%BF%D0%B0%D1%81%D0%BD%D0%BE%D1%81%D1%82%D1%8C-%D1%85%D0%BE%D1%81%D1%82%D0%B8%D0%BD%D0%B3%D0%B0-%D1%81%D0%BA%D1%80%D0%B8%D0%BF%D1%82%D0%B0-%D1%81%D0%BC%D0%B0%D1%80%D1%82-%D0%B1%D0%B0%D0%BD%D0%BD%D0%B5%D1%80%D0%BE%D0%B2 h_01HNDDT0XJSS77BFVVT2QQV5HP=%D0%B1%D0%B5%D0%B7%D0%BE%D0%BF%D0%B0%D1%81%D0%BD%D0%BE%D1%81%D1%82%D1%8C-%D1%85%D0%BE%D1%81%D1%82%D0%B8%D0%BD%D0%B3%D0%B0-%D1%81%D0%BA%D1%80%D0%B8%D0%BF%D1%82%D0%B0-%D1%81%D0%BC%D0%B0%D1%80%D1%82-%D0%B1%D0%B0%D0%BD%D0%BD%D0%B5%D1%80%D0%BE%D0%B2 h_01HNDDT0XJYW3Y0MQZWW1C1ETJ=can-clients-host-a-copy-of-the-smart-banner-script-on-their-server h_01HNDDT0XJG1SKBMA14KBGKZGD=can-clients-host-their-own-code-and-still-use-banners h_01HNDDT0XJDEGBK5WTBJ52ZVST=can-smart-banners-be-supported-without-embedding-their-code-snippet-on-the-page h_01HNDDT0XJC7FT514HEGN68T68=how-does-appsflyer-protect-your-banners-from-postsave-tampering h_01HNDDT0XJR4BQPN20FNGJPARY=do-smart-banners-use-cookies smart-banner-performance=%D1%8D%D1%84%D1%84%D0%B5%D0%BA%D1%82%D0%B8%D0%B2%D0%BD%D0%BE%D1%81%D1%82%D1%8C-%D1%81%D0%BC%D0%B0%D1%80%D1%82-%D0%B1%D0%B0%D0%BD%D0%BD%D0%B5%D1%80%D0%BE%D0%B2 h_01HNDDT0XJNJXY52BZJS9T1G72=%D1%8D%D1%84%D1%84%D0%B5%D0%BA%D1%82%D0%B8%D0%B2%D0%BD%D0%BE%D1%81%D1%82%D1%8C-%D1%81%D0%BC%D0%B0%D1%80%D1%82-%D0%B1%D0%B0%D0%BD%D0%BD%D0%B5%D1%80%D0%BE%D0%B2 h_01HNDDT0XJ456B4DG38BMMP98W=does-the-smart-banner-web-sdk-impact-website-load-speed h_01HNDDT0XJSEXVNRT8H27EMCNS=can-you-share-some-metrics-regarding-banner-speed-performance h_01HNDDT0XJK99RH6MAJFGQ7FPX=how-can-i-actively-improve-the-banner-loading-time smart-script-security-and-performance=%D0%B1%D0%B5%D0%B7%D0%BE%D0%BF%D0%B0%D1%81%D0%BD%D0%BE%D1%81%D1%82%D1%8C-%D0%B8-%D0%BF%D1%80%D0%BE%D0%B8%D0%B7%D0%B2%D0%BE%D0%B4%D0%B8%D1%82%D0%B5%D0%BB%D1%8C%D0%BD%D0%BE%D1%81%D1%82%D1%8C-smart-script h_01HNDDT0XJSGVRA6SB2YYYAE0P=%D0%B1%D0%B5%D0%B7%D0%BE%D0%BF%D0%B0%D1%81%D0%BD%D0%BE%D1%81%D1%82%D1%8C-%D0%B8-%D0%BF%D1%80%D0%BE%D0%B8%D0%B7%D0%B2%D0%BE%D0%B4%D0%B8%D1%82%D0%B5%D0%BB%D1%8C%D0%BD%D0%BE%D1%81%D1%82%D1%8C-smart-script h_01HNDDT0XJW9B4GJ3J4RMJDG6V=does-smart-script-use-cookies h_01HNDDT0XJNZXGPZN2NDHQ34KF=does-smart-script-make-any-external-calls-to-generate-links h_01HNDDT0XJXV12C5P1CD32FZW3=is-there-a-download-time-associated-with-smart-script" />
