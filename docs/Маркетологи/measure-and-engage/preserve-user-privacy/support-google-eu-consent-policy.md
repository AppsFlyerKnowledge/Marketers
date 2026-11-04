---
title: >-
  Поддержка политики Google в ЕС в отношении согласия пользователей на
  предоставление данных
metadata:
  keywords:
    - Agencies
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
    - Agencies
  created_at: '2024-02-07T07:28:17Z'
  edited_at: '2026-08-19T00:33:26Z'
  id: 22310731147153
  locale: ru
  section: Preserve user privacy
  section_id: 6551440878097
  url: https://support.appsflyer.com/hc/ru/articles/22310731147153
---
> **Краткий обзор:** AppsFlyer помогает маркетологам соблюдать закон о цифровых рынках (DMA) и повышать ценность их рекламы в Google. Найдите ответы на часто задаваемые вопросы о соблюдении требований DMA и оптимизации ценности рекламы.

<div id="overview" />

## Обзор

Компания Google обновляет свою <Anchor target="_blank" href="https://www.google.com/about/company/user-consent-policy/?sjid=15416941068016224808-NA">политику согласия пользователей в ЕС</Anchor> в рамках подготовки к принятию <Anchor target="_blank" href="https://commission.europa.eu/strategy-and-policy/priorities-2019-2024/europe-fit-digital-age/digital-markets-act-ensuring-fair-and-open-digital-markets_en">закона о цифровых рынках</Anchor> (DMA). Являясь <Anchor target="_blank" href="https://ads.google.com/lp/appcampaigns/attribution/">партнёром Google по атрибуции</Anchor>, AppsFlyer адаптируется к изменениям в политике, предоставляя рекламодателям возможность получить максимальную отдачу от рекламы в Google. Обновлённая политика вступила в силу с 6 марта 2024 года.

<div id="relevant-integrations-and-continued-use-of-google-features" />

## Соответствующие интеграции и дальнейшее использование функций Google

<div id="which-integrations-are-involved" />

<Accordion title="Какие интеграции задействованы?">

Следующие интеграции имеют отношение к новой политике Google относительно согласия на предоставление данных пользователей в ЕС:

* `googleadwords_int`Google Adsgoogleadwords\_int
* GMP DV360 (`dv360_int`)

Если конечные пользователи ваших приложений, использующих эти интеграции, находятся в Европейской экономической зоне (ЕЭЗ), обязательно примите необходимые меры, чтобы соответствовать требованиям новой политики Google относительно согласия в ЕС.

<div id="note" />

> 📘 **Примечание**
>
> Интеграция [Устаревшее] Google Marketing Platform DV360/CM (`doubleclick_int`) будет устаревшей и не будет поддерживаться в соответствии с новой политикой Google относительно согласия в ЕС. Если вы используете эту интеграцию, мы рекомендуем <Anchor target="_blank" href="/marketers/ru/docs/bulletin-google-marketing-platform-gmp-integration-transition">перейти на новую интеграцию DV360 (dv360\_int)</Anchor>.

</Accordion>

<div id="what-must-i-do-to-continue-using-googles-features" />

<Accordion title="Что нужно сделать, чтобы продолжать пользоваться функциями Google?">

Маркетологам необходимо получить согласие конечных пользователей в странах ЕЭЗ на использование их персональных данных, чтобы продолжать пользоваться функциями Google Ads и GMP DV360, связанными с измерениями, персонализацией рекламы и ремаркетингом.

</Accordion>

<div id="updating-the-appsflyer-sdk" />

## Обновление AppsFlyer SDK

<div id="what-steps-do-i-need-to-take-to-update-the-appsflyer-sdk" />

<Accordion title="Шаги, необходимые для реализации данных согласия через SDK AppsFlyer">

AppsFlyer SDK (Android: v6.13.0+, iOS: v6.13.1+) может отправлять необходимые данные о согласии с каждым событием, чтобы соответствовать требованиям Google.

* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/sdk-installation">Обновите SDK</Anchor> до последней версии (Android: v6.13.0+, iOS: v6.13.1+), применимой к приложениям для Android или iOS. Применимо к приложениям для Android или iOS.
* После обновления SDK <Anchor target="_blank" href="/marketers/ru/docs/additional-sdk-integration-guide#send-consent-for-dma-compliance">смотрите здесь</Anchor> инструкции по реализации поддержки DMA.

</Accordion>

<div id="sending-consent-data" />

## Отправка данных о согласии

<div id="how-do-i-send-consent-data-to-appsflyer" />

<Accordion title="Как отправить данные о согласии в AppsFlyer?">

У маркетологов есть два варианта отправки требуемых данных о согласии в AppsFlyer:

* [**Непосредственно через SDK**](#обновление-appsflyer-sdk) **или S2S API:** Маркетологи могут отправлять данные о согласии непосредственно в AppsFlyer, используя SDK. Применимо к приложениям для Android или iOS.
* **Через строки TCF:** Маркетологи, которые в настоящее время используют или планируют использовать платформу управления согласием (CMP), могут отправлять поля данных с помощью стандартных строк IAB TCF (TCF V2.2). Обязательно включите идентификатор поставщика Google (755) в список поставщиков, получивших согласие.

Затем AppsFlyer позволяет клиентам передавать сигналы о согласии в Google. Однако важно отметить, что AppsFlyer не собирает, не изменяет и не контролирует согласие конечных пользователей. Маркетологи, работающие с Google, сами отвечают за сбор необходимых полей согласия.

В <Anchor target="_blank" href="https://appsflyer.wistia.com/medias/0tnlyre8ai">этом видео</Anchor> мы рассказываем о том, как отправить данные о согласии в AppsFlyer.

</Accordion>

<div id="which-consent-values-does-appsflyer-send-to-google" />

<Accordion title="Значения согласия, которые AppsFlyer отправляет в Google">

Значения согласия конечных пользователей отправляются в Google для соответствующих интеграций AppsFlyer (`googleadwords_int` и `dv360_int`) с помощью следующих полей:

| Поле AppsFlyer | Поле Google (1) | Значения | Объяснение поля |
| --- | --- | --- | --- |
| <span id="gdpr_applies"></span>gdpr\_applies | eea | true/false (2) | Применяется ли DMA к этому пользователю? |
| <span id="ad_personalization"></span>ad\_personalization\_enabled | ad\_personalization | true\/false | Дал ли пользователь согласие Google на использование своих данных для персонализированной рекламы? |
| <span id="ad_user_data"></span>ad\_user\_data\_enabled | ad\_user\_data | true\/false | Дал ли пользователь согласие на отправку своих данных в Google? |

1. См. <Anchor target="_blank" href="https://support.google.com/tagmanager/answer/13802165?hl=en">определение Google для каждого поля</Anchor>.
2. Если DMA не применим к пользователю, AppsFlyer советует отправлять только одно поле согласия: `gdpr_applies=false`.

</Accordion>

<div id="sending-consent-datafaq" />

### Отправка данных о согласии – часто задаваемые вопросы

<div id="do-i-have-control-over-consent-data-for-nonue-users" />

<Accordion title="Есть ли возможность не отправлять данные о согласии в Google?">

AppsFlyer позволяет рекламодателям, которые считают, что DMA не распространяется на их конечных пользователей (например, если они не входят в ЕС), не отправлять данные о согласии в Google. Для этого нужно активировать переключатель на соответствующих страницах интеграции.

<div id="important" />

> 🚧 **Двоеточие (:)**
>
> Прежде чем использовать эту опцию, рекомендуется получить одобрение от своих юридических отделов и отделов по защите конфиденциальности, чтобы убедиться, что это соответствует их политике. Определения см. в <Anchor target="_blank" href="https://support.google.com/tagmanager/answer/13802165?hl=en">статье</Anchor> Google о режиме согласия.

**Чтобы воздержаться от передачи данных о согласии в Google:**

1. В AppsFlyer в боковом меню выберите **Сотрудничество**> **Активные интеграции**.
2. Найдите партнёра и нажмите **Управление интеграцией**.
3. На вкладке настройки интеграции включите переключатель **Пользователи из стран, не входящих в ЕС**.

<Image alt="Переключатель «Пользователи не из ЕС» на вкладке настройки интеграции" src="https://files.readme.io/fb141c0bd8885facd6574f3e73c5ec8ae8beb596de7fdf3dd8aed9d4e82686dd-22352319155985.png" width="595px" />

</Accordion>

<div id="is-consent-needed-for-mobile-web-events" />

<Accordion title="Нужно ли согласие для событий в мобильном вебе?">

На данном этапе в Google передаются только события мобильных приложений, поэтому делиться с AppsFlyer согласием на веб-события нет необходимости. Если пользователи переходят из веба в ваше приложение, их согласие будет зарегистрировано в приложении на более позднем этапе в любом случае.

</Accordion>

<div id="which-countries-does-googles-eu-consent-policy-cover" />

<Accordion title="На какие страны распространяется требование DMA о согласии для Google?">

Закон «О цифровых рынках» (DMA) применяется к пользователям в ЕС и ЕЭЗ (Европейская экономическая зона), <Anchor target="_blank" href="https://www.gov.uk/eu-eea">влияя на эти страны</Anchor>. Хотя **Великобритания и Швейцария** не являются частью ЕС, Google в одностороннем порядке расширил свою политику в отношении согласия и на эти страны тоже.

</Accordion>

<div id="whats-the-recommended-way-to-ask-for-user-consent-in-a-compliant-way" />

<Accordion title="Какой способ запроса согласия пользователя рекомендуется для обеспечения соответствия требованиям?">

AppsFlyer рекомендует проконсультироваться с вашими специалистами юридического отдела, чтобы обеспечить получение согласия в соответствии с DMA. Хотя <Anchor target="_blank" href="https://support.google.com/google-ads/answer/14009343?hl=ru&sjid=3762335249108620505-NC#app-consent">Google даёт общие рекомендации</Anchor>, конкретных формулировок для запроса не предлагается.

</Accordion>

<div id="how-is-appsflyer-translating-tcf-strings-to-google-dma-consent-flags" />

<Accordion title="Как AppsFlyer преобразовывает строки TCF во флажки согласия Google (для обеспечения соответствия DMA)?">

После того как AppsFlyer получает строки TCF от вашего CMP (через SDK AppsFlyer или S2S), они обрабатываются и преобразовываются на серверах AppsFlyer. Следующее преобразование сопоставляется и отправляется в Google, как рекомендовано Google:

| Собранные строки AppsFlyer | Флажки согласия Google | Описание |
| --- | --- | --- |
| `gdpr_applies=1/0` | `eea=1/0` | Определяет, применим ли DMA к соответствующему пользователю или нет |
| `ad_user_data` | `ad_user_data=1` | Когда согласие дано Google для цели №1 и согласие/законный интерес дано Google для цели №7 |
| `ad_user_data` | `ad_user_data=0` | Когда согласие не дано Google для цели №1 **и/или** согласие/законный интерес не дано Google для цели №7 |
| `ad_personalization` | `ad_personalization=1` `ad_personalization=0` | Когда согласие дано Google для целей №3 и №4 Когда согласие не дано Google для целей №3 и №4 |

</Accordion>

<div id="if-consent-data-is-sent-via-the-firebase-sdk-do-i-still-need-to-update-the-appsflyer-sdk" />

<Accordion title="Нужно ли мне обновлять и SDK AppsFlyer, и SDK Firebase для отправки данных согласия?">

Да. Google требует, чтобы данные согласия включались в каждое событие, отправляемое из AppsFlyer, так как Google не объединяет данные согласия пользователей из Firebase с данными, отправленными из AppsFlyer. Поэтому данные согласия должны отправляться в AppsFlyer, который затем пересылает их в Google. Аналогично, передача данных согласия только в AppsFlyer недостаточна согласно требованиям для SDK Firebase. Это означает, что вы должны отправлять данные как в AppsFlyer, так и в Firebase.

</Accordion>

<div id="preparing-for-the-upcoming-changes" />

## Подготовка к предстоящим изменениям

<div id="how-can-i-prepare-for-the-upcoming-changes" />

<Accordion title="Выполните следующие подготовительные действия">

<div id="address-user-consent-in-the-european-economic-area-eea" />

#### Запрос согласия пользователей в Европейской экономической зоне (ЕЭЗ)

Сотрудничайте с юрисконсультом вашей компании. Юристы могут предоставить информацию о последствиях европейской политики согласия пользователей для данных, которыми вы делитесь с такими партнёрами, как Google. Если это уместно, используйте подсказки о конфиденциальности, такие как «Настройки конфиденциальности» или «Выбор конфиденциальности», для сбора сигналов согласия пользователей ваших приложений на маркетинг и рекламу.

<div id="verify-cmp-compliance-and-tcf-2223-support" />

#### Проверка соответствия CMP и поддержка TCF 2.2

Убедитесь, что ваша платформа управления согласием (CMP) поддерживает TCF 2.2, которая является самой последней версией Transparency and Consent Framework (TCF). Ваш TCF также должен быть хорошо осведомлён о новых требованиях Google к согласию пользователей в ЕС и может проконсультировать вас о том, как поддержать его через TCF.

<div id="implement-the-newest-sdkserver-to-server-s2s-apis" />

#### Внедрение новейших API SDK/Server-to-Server (S2S)

Рассмотрите следующие варианты отправки новых полей согласия, используя SDK или вызовы S2S API:

* **Использование SDK:**
  * Внедрите последнюю версию AppsFlyer SDK (Android: v6.13.0+, iOS: v6.13.1+) для приложений на iOS и Android.
  * Выберите способ <Anchor target="_blank" href="/marketers/ru/docs/additional-sdk-integration-guide#send-consent-for-dma-compliance">отправки данных о согласии</Anchor>
* **Использование вызовов API** <Anchor target="_blank" href="/marketers/ru/docs/server-to-server-events-api-for-mobile-s2s-mobile?">**S2S**</Anchor>:
  * Прежде чем отправлять события в приложении в AppsFlyer, обновите вызовы API, чтобы включить объект `consent_data` для каждого события. Узнайте, <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/s2s-events-api3-post">как это сделать</Anchor>.

<div id="transition-from-the-legacy-gmp-integration-doubleclick" />

#### Переход от устаревшей интеграции GMP (DoubleClick)

Если вы все ещё используете устаревшую интеграцию GMP AppsFlyer (doubleclick\_int), планируйте завершить переход на более новую версию (dv360\_int) в течение 1 квартала 2024 года. Устаревшая интеграция **не совместима с согласием пользователей в ЕС** и скоро будет отменена. Более подробную информацию можно найти <Anchor target="_blank" href="/marketers/ru/docs/bulletin-google-marketing-platform-gmp-integration-transition">здесь</Anchor>.

</Accordion>

<div id="impact-on-advertising-activityfaq" />

## Влияние на рекламную деятельность – часто задаваемые вопросы

<div id="how-will-the-upcoming-change-impact-my-remarketing-campaigns" />

<Accordion title="Как предстоящее изменение повлияет на атрибуцию моих кампаний?">

Для пользователей из ЕС, отказавшихся от использования их данных Google в рекламных целях (`ad_user_data=0`), не будет запрашиваться атрибуция в Google Ads и DV360. Это означает, что AppsFlyer не сможет их атрибутировать.

Существуют несколько исключений, при которых Google и AppsFlyer всё ещё могут выполнять атрибуцию, при ad\_user\_data=0, основываясь на интерпретации Google регламента DMA.

</Accordion>

<div id="how-will-the-upcoming-change-affect-my-audiences" />

<Accordion title="Как предстоящие изменения повлияют на Аудитории?">

Это изменение может повлиять на количество пользователей из стран ЕЭЗ, которые отображаются в ваших аудиториях и видят кампании ремаркетинга в Google. Пользователи из стран ЕЭЗ должны будут дать согласие на передачу своей информации в Google. Те, кто не дал согласия, будут исключены из аудитории на стороне Google и не увидят ваши кампании. В связи с этим возникает вопрос о том, как получить согласие пользователей и какие последствия это может иметь для вашего бизнеса и рекламных усилий. <Anchor target="_blank" href="/marketers/ru/docs/audiences-user-identifier-policy#eu-digital-markets-act">Узнайте больше об изменениях в Аудиториях</Anchor>.

</Accordion>

<div id="further-information-and-contact-details" />

## Дополнительная информация и контактные данные

Если у вас есть дополнительные вопросы или какие-либо неясности, вы можете ознакомиться со следующими материалами:

* Если у вас возникли вопросы о требованиях Google или о том, как эти обновления могут повлиять на ваши данные Google, ознакомьтесь со <Anchor target="_blank" href="https://www.google.com/about/company/user-consent-policy-help/">справочными статьями Google</Anchor> или обратитесь напрямую к представителю Google.
* По вопросам, связанным с поддержкой AppsFlyer полей согласия конечных пользователей из ЕС, обращайтесь к своему менеджеру AppsFlyer или по адресу [hello@appsflyer.com](mailto:hello@appsflyer.com).
* Определения см. в <Anchor target="_blank" href="https://support.google.com/tagmanager/answer/13802165?hl=en">статье</Anchor> Google о режиме согласия.

<div id="see-also" />

> 📄 **Смотрите также**
>
> * <Anchor target="_blank" href="/marketers/ru/docs/additional-sdk-integration-guide">Интеграция дополнительных средств SDK</Anchor>
> * <Anchor target="_blank" href="/marketers/ru/docs/bulletin-google-marketing-platform-gmp-integration-transition">Переход на новую интеграцию DV360</Anchor>
> * <Anchor target="_blank" href="/marketers/ru/docs/audiences-user-identifier-policy">Политика идентификаторов пользователей в аудиториях</Anchor>

<div data-zendesk-anchors="overview=%D0%BE%D0%B1%D0%B7%D0%BE%D1%80 h_01HP195KV35FD6X67WTMXJWWSZ=%D0%BE%D0%B1%D0%B7%D0%BE%D1%80 relevant-integrations-and-continued-use-of-google-features=%D1%81%D0%BE%D0%BE%D1%82%D0%B2%D0%B5%D1%82%D1%81%D1%82%D0%B2%D1%83%D1%8E%D1%89%D0%B8%D0%B5-%D0%B8%D0%BD%D1%82%D0%B5%D0%B3%D1%80%D0%B0%D1%86%D0%B8%D0%B8-%D0%B8-%D0%B4%D0%B0%D0%BB%D1%8C%D0%BD%D0%B5%D0%B9%D1%88%D0%B5%D0%B5-%D0%B8%D1%81%D0%BF%D0%BE%D0%BB%D1%8C%D0%B7%D0%BE%D0%B2%D0%B0%D0%BD%D0%B8%D0%B5-%D1%84%D1%83%D0%BD%D0%BA%D1%86%D0%B8%D0%B9-google h_01HP1M37V1CYW5T5E4K1ES3NQA=%D1%81%D0%BE%D0%BE%D1%82%D0%B2%D0%B5%D1%82%D1%81%D1%82%D0%B2%D1%83%D1%8E%D1%89%D0%B8%D0%B5-%D0%B8%D0%BD%D1%82%D0%B5%D0%B3%D1%80%D0%B0%D1%86%D0%B8%D0%B8-%D0%B8-%D0%B4%D0%B0%D0%BB%D1%8C%D0%BD%D0%B5%D0%B9%D1%88%D0%B5%D0%B5-%D0%B8%D1%81%D0%BF%D0%BE%D0%BB%D1%8C%D0%B7%D0%BE%D0%B2%D0%B0%D0%BD%D0%B8%D0%B5-%D1%84%D1%83%D0%BD%D0%BA%D1%86%D0%B8%D0%B9-google 01HP1KN2H7NTS2V1S2PGF0C41N=which-integrations-are-involved h_01HP2HRPJR72Z0R5VEG5N36CN2=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%87%D0%B0%D0%BD%D0%B8%D0%B5 h_01HP1K1088SJK60QRSTQF4WF6S=what-must-i-do-to-continue-using-googles-features updating-the-appsflyer-sdk=%D0%BE%D0%B1%D0%BD%D0%BE%D0%B2%D0%BB%D0%B5%D0%BD%D0%B8%D0%B5-appsflyer-sdk h_01HP1Z2G2M56DDQS9T47GMCFHJ=%D0%BE%D0%B1%D0%BD%D0%BE%D0%B2%D0%BB%D0%B5%D0%BD%D0%B8%D0%B5-appsflyer-sdk h_01HP1ZASRQGABCEFV67P961XAV=what-steps-do-i-need-to-take-to-update-the-appsflyer-sdk how-consent-data-is-sent=%D0%BE%D1%82%D0%BF%D1%80%D0%B0%D0%B2%D0%BA%D0%B0-%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D1%85-%D0%BE-%D1%81%D0%BE%D0%B3%D0%BB%D0%B0%D1%81%D0%B8%D0%B8 h_01HP1KPSMCH3EG373BWVQZM4ZT=%D0%BE%D1%82%D0%BF%D1%80%D0%B0%D0%B2%D0%BA%D0%B0-%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D1%85-%D0%BE-%D1%81%D0%BE%D0%B3%D0%BB%D0%B0%D1%81%D0%B8%D0%B8 h_01HP1JJ2AYHYJET9GYMXA93E86=how-do-i-send-consent-data-to-appsflyer h_01HP1JJ2AYWRBREW5GD0KPDF1R=which-consent-values-does-appsflyer-send-to-google sending-consent-data%E2%80%94faq=%D0%BE%D1%82%D0%BF%D1%80%D0%B0%D0%B2%D0%BA%D0%B0-%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D1%85-%D0%BE-%D1%81%D0%BE%D0%B3%D0%BB%D0%B0%D1%81%D0%B8%D0%B8--%D1%87%D0%B0%D1%81%D1%82%D0%BE-%D0%B7%D0%B0%D0%B4%D0%B0%D0%B2%D0%B0%D0%B5%D0%BC%D1%8B%D0%B5-%D0%B2%D0%BE%D0%BF%D1%80%D0%BE%D1%81%D1%8B h_01HR1X08VZ5MEAV01E9X54KAQS=%D0%BE%D1%82%D0%BF%D1%80%D0%B0%D0%B2%D0%BA%D0%B0-%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D1%85-%D0%BE-%D1%81%D0%BE%D0%B3%D0%BB%D0%B0%D1%81%D0%B8%D0%B8--%D1%87%D0%B0%D1%81%D1%82%D0%BE-%D0%B7%D0%B0%D0%B4%D0%B0%D0%B2%D0%B0%D0%B5%D0%BC%D1%8B%D0%B5-%D0%B2%D0%BE%D0%BF%D1%80%D0%BE%D1%81%D1%8B h_01HP1JJ2AYZ57G0GMR8QRDTEZ7=do-i-have-control-over-consent-data-for-nonue-users h_01HP2MRPFA2ECJGAZ93NQHVD2J=%D0%B4%D0%B2%D0%BE%D0%B5%D1%82%D0%BE%D1%87%D0%B8%D0%B5- 01HVE9TVZWTRW3VQ8TSXWA13QM=is-consent-needed-for-mobile-web-events h_01JVYS49FCZT3Z91KNACNR6GET=which-countries-does-googles-eu-consent-policy-cover h_01HRXZYZJBDTP8CHJDHQ187CTN=whats-the-recommended-way-to-ask-for-user-consent-in-a-compliant-way 01HR6SD3PBWN5X9AHT66ZADQ3R=how-is-appsflyer-translating-tcf-strings-to-google-dma-consent-flags 01J2V4XRKRSEPA6KPJFMSTHE1F=if-consent-data-is-sent-via-the-firebase-sdk-do-i-still-need-to-update-the-appsflyer-sdk what-i-can-do-on-my-side=%D0%BF%D0%BE%D0%B4%D0%B3%D0%BE%D1%82%D0%BE%D0%B2%D0%BA%D0%B0-%D0%BA-%D0%BF%D1%80%D0%B5%D0%B4%D1%81%D1%82%D0%BE%D1%8F%D1%89%D0%B8%D0%BC-%D0%B8%D0%B7%D0%BC%D0%B5%D0%BD%D0%B5%D0%BD%D0%B8%D1%8F%D0%BC 01HR1XYXRDVEW6H9Q3WP17E2N3=%D0%BF%D0%BE%D0%B4%D0%B3%D0%BE%D1%82%D0%BE%D0%B2%D0%BA%D0%B0-%D0%BA-%D0%BF%D1%80%D0%B5%D0%B4%D1%81%D1%82%D0%BE%D1%8F%D1%89%D0%B8%D0%BC-%D0%B8%D0%B7%D0%BC%D0%B5%D0%BD%D0%B5%D0%BD%D0%B8%D1%8F%D0%BC h_01HP1JJ2AYFHRRDYZS8YFYE6WP=how-can-i-prepare-for-the-upcoming-changes address-user-consent-in-the-european-economic-area-eea-and-in-the-uk=%D0%B7%D0%B0%D0%BF%D1%80%D0%BE%D1%81-%D1%81%D0%BE%D0%B3%D0%BB%D0%B0%D1%81%D0%B8%D1%8F-%D0%BF%D0%BE%D0%BB%D1%8C%D0%B7%D0%BE%D0%B2%D0%B0%D1%82%D0%B5%D0%BB%D0%B5%D0%B9-%D0%B2-%D0%B5%D0%B2%D1%80%D0%BE%D0%BF%D0%B5%D0%B9%D1%81%D0%BA%D0%BE%D0%B9-%D1%8D%D0%BA%D0%BE%D0%BD%D0%BE%D0%BC%D0%B8%D1%87%D0%B5%D1%81%D0%BA%D0%BE%D0%B9-%D0%B7%D0%BE%D0%BD%D0%B5-%D0%B5%D1%8D%D0%B7 h_01HPGNBQCTJFVZR99BY6E5J2JF=%D0%B7%D0%B0%D0%BF%D1%80%D0%BE%D1%81-%D1%81%D0%BE%D0%B3%D0%BB%D0%B0%D1%81%D0%B8%D1%8F-%D0%BF%D0%BE%D0%BB%D1%8C%D0%B7%D0%BE%D0%B2%D0%B0%D1%82%D0%B5%D0%BB%D0%B5%D0%B9-%D0%B2-%D0%B5%D0%B2%D1%80%D0%BE%D0%BF%D0%B5%D0%B9%D1%81%D0%BA%D0%BE%D0%B9-%D1%8D%D0%BA%D0%BE%D0%BD%D0%BE%D0%BC%D0%B8%D1%87%D0%B5%D1%81%D0%BA%D0%BE%D0%B9-%D0%B7%D0%BE%D0%BD%D0%B5-%D0%B5%D1%8D%D0%B7 verify-cmp-compliance-and-tcf-22-support=%D0%BF%D1%80%D0%BE%D0%B2%D0%B5%D1%80%D0%BA%D0%B0-%D1%81%D0%BE%D0%BE%D1%82%D0%B2%D0%B5%D1%82%D1%81%D1%82%D0%B2%D0%B8%D1%8F-cmp-%D0%B8-%D0%BF%D0%BE%D0%B4%D0%B4%D0%B5%D1%80%D0%B6%D0%BA%D0%B0-tcf-22 h_01HPGNC0HAMA7Z0B4DNV2QSFYG=%D0%BF%D1%80%D0%BE%D0%B2%D0%B5%D1%80%D0%BA%D0%B0-%D1%81%D0%BE%D0%BE%D1%82%D0%B2%D0%B5%D1%82%D1%81%D1%82%D0%B2%D0%B8%D1%8F-cmp-%D0%B8-%D0%BF%D0%BE%D0%B4%D0%B4%D0%B5%D1%80%D0%B6%D0%BA%D0%B0-tcf-22 implement-the-newest-sdkservertoserver-s2s-apis=%D0%B2%D0%BD%D0%B5%D0%B4%D1%80%D0%B5%D0%BD%D0%B8%D0%B5-%D0%BD%D0%BE%D0%B2%D0%B5%D0%B9%D1%88%D0%B8%D1%85-api-sdkserver-to-server-s2s h_01HPGNCAG3M9XPHDTP03WHQQ9F=%D0%B2%D0%BD%D0%B5%D0%B4%D1%80%D0%B5%D0%BD%D0%B8%D0%B5-%D0%BD%D0%BE%D0%B2%D0%B5%D0%B9%D1%88%D0%B8%D1%85-api-sdkserver-to-server-s2s transition-from-the-legacy-gmp-integration-doubleclick=%D0%BF%D0%B5%D1%80%D0%B5%D1%85%D0%BE%D0%B4-%D0%BE%D1%82-%D1%83%D1%81%D1%82%D0%B0%D1%80%D0%B5%D0%B2%D1%88%D0%B5%D0%B9-%D0%B8%D0%BD%D1%82%D0%B5%D0%B3%D1%80%D0%B0%D1%86%D0%B8%D0%B8-gmp-doubleclick h_01HPGNCHP6SSFCVZ3P4AG0N1FB=%D0%BF%D0%B5%D1%80%D0%B5%D1%85%D0%BE%D0%B4-%D0%BE%D1%82-%D1%83%D1%81%D1%82%D0%B0%D1%80%D0%B5%D0%B2%D1%88%D0%B5%D0%B9-%D0%B8%D0%BD%D1%82%D0%B5%D0%B3%D1%80%D0%B0%D1%86%D0%B8%D0%B8-gmp-doubleclick impact-on-my-advertising-activity=%D0%B2%D0%BB%D0%B8%D1%8F%D0%BD%D0%B8%D0%B5-%D0%BD%D0%B0-%D1%80%D0%B5%D0%BA%D0%BB%D0%B0%D0%BC%D0%BD%D1%83%D1%8E-%D0%B4%D0%B5%D1%8F%D1%82%D0%B5%D0%BB%D1%8C%D0%BD%D0%BE%D1%81%D1%82%D1%8C--%D1%87%D0%B0%D1%81%D1%82%D0%BE-%D0%B7%D0%B0%D0%B4%D0%B0%D0%B2%D0%B0%D0%B5%D0%BC%D1%8B%D0%B5-%D0%B2%D0%BE%D0%BF%D1%80%D0%BE%D1%81%D1%8B h_01HP1PKNZN32TQYHGJNNM3JFVZ=%D0%B2%D0%BB%D0%B8%D1%8F%D0%BD%D0%B8%D0%B5-%D0%BD%D0%B0-%D1%80%D0%B5%D0%BA%D0%BB%D0%B0%D0%BC%D0%BD%D1%83%D1%8E-%D0%B4%D0%B5%D1%8F%D1%82%D0%B5%D0%BB%D1%8C%D0%BD%D0%BE%D1%81%D1%82%D1%8C--%D1%87%D0%B0%D1%81%D1%82%D0%BE-%D0%B7%D0%B0%D0%B4%D0%B0%D0%B2%D0%B0%D0%B5%D0%BC%D1%8B%D0%B5-%D0%B2%D0%BE%D0%BF%D1%80%D0%BE%D1%81%D1%8B h_01HP1PKNZN0VJGYAPFHR5JVV5H=how-will-the-upcoming-change-impact-my-remarketing-campaigns h_01HP4K2ZJW11BFSKNPRH7FA092=how-will-the-upcoming-change-affect-my-audiences further-information-and-contact-details=%D0%B4%D0%BE%D0%BF%D0%BE%D0%BB%D0%BD%D0%B8%D1%82%D0%B5%D0%BB%D1%8C%D0%BD%D0%B0%D1%8F-%D0%B8%D0%BD%D1%84%D0%BE%D1%80%D0%BC%D0%B0%D1%86%D0%B8%D1%8F-%D0%B8-%D0%BA%D0%BE%D0%BD%D1%82%D0%B0%D0%BA%D1%82%D0%BD%D1%8B%D0%B5-%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D0%B5 h_01HQ2VJES04CYF4J8YBB4GQS73=%D0%B4%D0%BE%D0%BF%D0%BE%D0%BB%D0%BD%D0%B8%D1%82%D0%B5%D0%BB%D1%8C%D0%BD%D0%B0%D1%8F-%D0%B8%D0%BD%D1%84%D0%BE%D1%80%D0%BC%D0%B0%D1%86%D0%B8%D1%8F-%D0%B8-%D0%BA%D0%BE%D0%BD%D1%82%D0%B0%D0%BA%D1%82%D0%BD%D1%8B%D0%B5-%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D0%B5 h_01KZZYSDB33GZ47RSDRP9ACAH0=%D1%81%D0%BC%D0%BE%D1%82%D1%80%D0%B8%D1%82%D0%B5-%D1%82%D0%B0%D0%BA%D0%B6%D0%B5" />
