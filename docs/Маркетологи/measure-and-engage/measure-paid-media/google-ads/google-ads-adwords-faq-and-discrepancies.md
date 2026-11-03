---
title: 'Google Ads (AdWords): часто задаваемые вопросы и расхождения'
metadata:
  keywords:
    - Advertisers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
  created_at: '2022-01-20T10:06:31Z'
  edited_at: '2026-08-18T00:30:10Z'
  id: 4417303339921
  locale: ru
  section: Google Ads
  section_id: 6551205645457
  url: https://support.appsflyer.com/hc/ru/articles/4417303339921
---
> **Краткий обзор:** Выявляйте и устраняйте распространённые проблемы и расхождения, связанные с Google Ads.

## Вопросы и ответы по Google Ads

<div id="why-am-i-not-seeing-clicks-from-google-ads" />

<Accordion title="Почему не отображаются данные о кликах из Google Ads?">

Сводные данные о кликах и показах начнут поступать от Google Ads после <Anchor target="_blank" href="/marketers/ru/docs/google-ads-adwords-integration-setup-for-advertisers#step-2-set-up-google-ads-on-appsflyer-mandatory">включения функции получения данных о затратах, кликах и показах</Anchor> на вкладке **Затраты**.

Данные Google Ads о нажатиях и показах стали доступны в августе 2018 г. – сначала для приложений для Android, а потом и для приложений для iOS. Поэтому при анализе данных о нажатиях за 2018 г. или более ранние периоды нужно иметь в виду, что данные о кликах в Google Ads могут отсутствовать или быть неполными.

</Accordion>

<div id="why-am-i-not-seeing-first_open-conversions-on-google-ads" />

<Accordion title="Почему в Google Ads не отображаются конверсии first_open?">

Если вы не видите конверсии first\_open в Google Ads, как показано на рисунке ниже:

![AW_13.png](https://files.readme.io/082f79266fced9fc012cdb373321a836129205992adbe29f7509321516e8f5ab-33743114088849.png)

значит, вам нужно импортировать конверсии в Google Ads. Следуйте инструкции по <Anchor target="_blank" href="/marketers/ru/docs/google-ads-adwords-integration-setup-for-advertisers#step-4-measure-your-app-conversions-mandatory">импорту конверсий</Anchor>.

</Accordion>

<div id="why-don-t-i-see-installs-from-google-ads" />

<Accordion title="Почему я не вижу установки из Google Ads?">

Следуйте этому контрольному списку, чтобы устранить проблемы с отсутствующими установками:

#### Быстрое решение

1. **Активируйте Google Ads в AppsFlyer**  
   В AppsFlyer в боковом меню откройте **Сотрудничество > Активные интеграции**, найдите **Google Ads** и подтвердите, что интеграция активна.
2. **Импортируйте** `first_open`**конверсию в Google Ads**  
   В Google Ads перейдите на страницу <Anchor target="_blank" href="https://ads.google.com/aw/conversions">Сводка конверсий</Anchor> и убедитесь, что `first_open` событие конверсии импортировано. Для получения дополнительной информации смотрите <Anchor target="_blank" href="/marketers/ru/docs/google-ads-adwords-integration-setup-for-advertisers">Импорт конверсий вашего приложения</Anchor>.

#### Все еще не работает?

1. **Проверьте, какой аккаунт Google Ads импортирует конверсии**  
   Определите, отвечает ли **аккаунт Google Ads MCC или субаккаунт** за импорт конверсий:

   * **Если используете MCC (менеджерский аккаунт):** MCC должен импортировать `first_open` конверсию от имени всех связанных субаккаунтов.
   * **Если используете субаккаунт:**
     * MCC должен **поделиться ID ссылки** с субаккаунтом.
     * Субаккаунт должен **также импортировать** `first_open`**конверсию** напрямую.

   Для получения дополнительной информации об аккаунтах Google Ads MCC смотрите: <Anchor target="_blank" href="/marketers/ru/docs/recording-multiple-agency-mcc-google-ads-accounts#mcc">MCC</Anchor>.
2. **Проверьте удаленные** `first_open`**конверсии**  
   На странице <Anchor target="_blank" href="https://ads.google.com/aw/conversions">Сводка конверсий</Anchor> проверьте, было ли удалено `first_open` событие конверсии. Если удалено, свяжитесь с **поддержкой Google** для получения помощи.
3. **Подтвердите идентификатор ссылки**  
   Убедитесь, что идентификатор ссылки в AppsFlyer совпадает с идентификатором ссылки в Google Ads.

</Accordion>

<div id="why-dont-i-see-inapp-events-in-the-google-ads-dashboard" />

<Accordion title="Почему я не вижу событий в приложении на дэшборде Google Ads?">

Используйте этот контрольный список, чтобы убедиться, что ваши события в приложении правильно настроены и синхронизированы между AppsFlyer и Google Ads.

#### Контрольный список для быстрого исправления

Следуйте этим шагам, чтобы быстро решить наиболее распространенные проблемы:

1. **Проверьте постбэки событий в AppsFlyer** (для пошаговых инструкций см. <Anchor target="_blank" href="/marketers/ru/docs/google-ads-adwords-integration-setup-for-advertisers#step-3-map-your-inapp-events-recommended">Настройка Google Ads в AppsFlyer.</Anchor>)
   1. Перейдите на вкладку **Интеграция Google Ads** в AppsFlyer.
   2. Убедитесь, что постбэки настроены правильно для каждого события в приложении, которое вы хотите измерить.
   3. В разделе **Для пользователей из** выберите *Все медиаисточники , включая органические,*, чтобы убедиться, что Google Ads получает данные о событиях.
   4. (Необязательно) После первоначальной настройки при необходимости скорректируйте этот выбор для конкретных событий.
2. **Запустите тестовое событие в приложении**
   1. Запустите ваше приложение.
   2. Для приложений iOS убедитесь, что сбор IDFA включен, разрешив приложению отслеживать.
   3. Выполните сопоставленные события в приложении вручную (например, покупка или регистрация).
3. **Импортируйте события в Google Ads**
   1. В Google Ads нажмите **Инструменты конверсии**.
   2. Проверьте **Сводку действий по конверсии**.
   3. Импортируйте соответствующие события в приложении. Для получения дополнительной информации см. <Anchor target="_blank" href="/marketers/ru/docs/google-ads-adwords-integration-setup-for-advertisers">Импортировать конверсии вашего приложения</Anchor>.

      > 📘 **Примечание**
      >
      > Конверсии могут появляться до 6 часов после выполнения события.


#### Все еще не работает?

Если вы изменили идентификатор события партнера в Google Ads (например, если он помечен как `CUSTOM`) и изменили соответствующее название события в AppsFlyer, вам нужно будет повторно импортировать события в Google Ads.

</Accordion>

<div id="can-i-stop-google-cost-sync" />

<Accordion title="Можно ли прекратить синхронизацию данных о расходах с Google?">

Чтобы прекратить синхронизацию данных о расходах с Google:

1. Перейдите на страницу <Anchor target="_blank" href="https://myaccount.google.com/permissions">разрешений аккаунта Google</Anchor>.
2. Нажмите кнопку Удалить рядом со строкой AppsFlyer Google Cost (Затраты AppsFlyer в Google).  
   ![remove_appsflyer_cost.png](https://files.readme.io/56840e708c98875c8db176c642dd324150a76aef9697fcc2756f524b2a6c0a16-33743128661137.png)

</Accordion>

<div id="do-i-need-to-create-and-then-import-session_start" />

<Accordion title="Нужно ли создавать, а затем импортировать событие session_start?">

Это зависит от типа вашей кампании. Если вы запускаете кампанию по повторному вовлечению пользователей, рекомендуется создать и импортировать событие `session_start`session\_startsession\_start – это позволит получать количественные показатели вовлечения пользователей.

Для кампаний по привлечению новых пользователей это необязательно.

</Accordion>

<div id="can-i-send-uninstall-information-to-google-ads" />

<Accordion title="Можно ли отправить информацию об удалении приложения в Google Ads?">

Да.  
**Чтобы отправлять в Google события удаления:**

1. Отметьте событие af\_uninstall как индивидуально настраиваемое событие в окне настроек Google Ads.
2. Импортируйте эту конверсию в Google.
3. Google подтверждает события, если они получены в период действия окна атрибуции Google (с момента интеракции с рекламой в течение 30-90 дней). События, полученные Google по истечении срока действия окна атрибуции, не регистрируются в Google.

</Accordion>

<div id="what-google-ads-data-does-appsflyer-display" />

<Accordion title="Какие данные Google Ads отображаются в AppsFlyer?">

Вы можете просматривать данные на следующих уровнях: кампания, канал, группа объявлений и регион.

</Accordion>

<div id="do-i-need-to-configure-anything-to-create-audience-lists-in-google-ads-based-on-appsflyer-data" />

<Accordion title="Нужны ли какие-либо настройки для создания в Google Ads списков аудиторий на основе данных AppsFlyer?">

Нет. В API Google эта информация уже задана и основана на ваших настройках внутренних событий приложения.

</Accordion>

<div id="im-running-an-app-campaign-why-cant-i-see-data-or-conversion-events-in-the-appsflyer-or-google-ads-dashboard" />

<Accordion title="Я провожу кампанию для своего приложения, почему данные и события конверсии не отображаются ни в AppsFlyer, ни на дэшборде Google Ads?">

Скорее всего вы еще не выполнили импорт событий. Подробное описание процедуры импорта событий см. <Anchor target="_blank" href="/marketers/ru/docs/google-ads-adwords-integration-setup-for-advertisers#step-4-measure-your-app-conversions-mandatory">здесь</Anchor>.

</Accordion>

<div id="what-do-i-do-if-there-are-multiple-accounts" />

<Accordion title="Что делать, если у меня есть несколько учётных записей?">

В AppsFlyer можно использовать несколько учётных записей Google Ads. AppsFlyer работает только с одним Link ID. Поэтому в Google Ads должен быть создан только один Link ID, который можно использовать для нескольких учётных записей. Для получения дополнительной информации нажмите <Anchor target="_blank" href="https://support.google.com/google-ads/answer/3030657?hl=ru&sjid=54492764837147850-EU">здесь</Anchor>.

</Accordion>

<div id="what-happens-with-link-ids-created-at-mcc-level-vs-account-level" />

<Accordion title="Что происходит с Link ID, созданными на уровне MCC и на уровне учетной записи?">

AppsFlyer поддерживает Link ID, созданные и на уровне MCC, и на уровне учётной записи. Чтобы убедиться что ваша учётная запись была правильно структурирована, рекомендуем связаться с вашим представителем Google Ads. Для получения дополнительной информации нажмите <Anchor target="_blank" href="/marketers/ru/docs/recording-multiple-agency-mcc-google-ads-accounts">здесь</Anchor>.

</Accordion>

<div id="what-is-parallel-tracking" />

<Accordion title="Что такое «параллельное отслеживание»?">

Функция параллельного отслеживания в Google Ads позволяет быстрее загружать вашу целевую страницу, что снижает количество потерянных посещений. В результате растёт количество конверсий и повышается эффективность рекламы. При параллельном отслеживании пользователи направляются на конечный URL-адрес прямо из вашего объявления ещё до их направления на ссылки атрибуции, а учёт нажатий происходит в фоновом режиме.

Подробное описание параллельного отслеживания см. <Anchor target="_blank" href="https://support.google.com/google-ads/answer/7544674?hl=ru">здесь</Anchor>.

#### Что необходимо?

Чтобы параллельное отслеживание работало как положено, конечный URL должен совпадать с тем, что указан в URL кампании, и быть помещен в <Anchor target="_blank" href="https://support.google.com/google-ads/answer/6305348?hl=ru">параметре ValueTrack `{lpurl}` от Google</Anchor>.

Это делается с помощью:

* одноплатформенной ссылки атрибуции (не рекомендуется);
  * в URL должен быть использован параметр af\_r.
* <Anchor target="_blank" href="/marketers/ru/docs/understand-onelink-short-vs-long-urls">длинной ссылки OneLink</Anchor> (рекомендуется);
  * добавьте следующие параметры в URL кампании:
    * af\_android\_url;
    * af\_ios\_url;
    * af\_web\_dp.
  * параметр af\_dp не должен использоваться.
  * добавьте конечный URL (URL назначения) в параметр ValueTrack Google. <Anchor target="_blank" href="https://support.google.com/google-ads/answer/6305348?hl=ru#urlinsertion&zippy=%2Ctracking-template-only">Подробнее</Anchor>

Например:

```
https://subdomain.onelink.me/template_id?pid=xxx&af_ios_url={lpurl}
&af_android_url={lpurl}&af_web_dp={lpurl}
```

Примечание: Для просмотра всех поддерживаемых параметров см. [эту статью.](https://support.google.com/google-ads/answer/6305348?hl=en&sjid=12409212435602417786-AP#zippy=%2Cset-up-or-edit-a-tracking-template-with-valuetrack-parameters-at-the-campaign-level%2Cset-up-or-edit-a-tracking-template-with-valuetrack-parameters-at-the-ad-group-level%2Cfinal-url-tracking-template-or-custom-parameter)

О том, как настроить в Google рекламные веб-кампании с параллельным отслеживанием, читайте здесь.

</Accordion>

<div id="how-do-you-configure-a-campaign-with-android-or-ios-configuration" />

<Accordion title="Как настраиваются кампании для Android и iOS">

> 🚧 **Важно!**
>
> AppsFlyer поддерживает все мобильные кампании, включенные в Google Ads.
>
> Google – это SRN (Self Reporting Network – сеть с самостоятельной атрибуцией). Для получения дополнительной информации о том, как работает поток атрибуции для этих сетей, кликните <Anchor target="_blank" href="/marketers/ru/docs/self-reporting-networks-srns">здесь</Anchor>.
>
> AppsFlyer может отображать любую информацию о кампаниях, предоставленную Google. Тип кампании (Поиск, Видео, Отображение и Повторное вовлечение) и связанную с ней информацию предоставляет Google. Рекомендуется настраивать кампании приложений. Для получения рекомендаций по другим типам кампаний следует обратиться к представителю Google. Дополнительные сведения об этих кампаниях см. <Anchor target="_blank" href="https://developers.google.com/app-conversion-tracking/api/request-response-specs?hl=ru">здесь</Anchor>.

<div id="android-configuration-for-google-ads" />

<Accordion title="Настройки Android для Google Ads">

Атрибуция для Android-приложений возможна при условии, что это приложение поддерживает GAID (Идентификатор рекламы Google), который должен передаваться в AppsFlyer через наш SDK.

#### Настройка регистрации конверсий (установок)

Подробное описание настройки регистрации конверсий см. <Anchor target="_blank" href="/marketers/ru/docs/google-ads-adwords-integration-setup-for-advertisers#step-2-set-up-google-ads-on-appsflyer-mandatory">здесь</Anchor>.

<span id="inapp_events"></span>Google Ads – Настройки Android-приложений – Отправка внутренних событий приложения

Для лучшего измерения успеха своих кампаний по продвижению мобильных приложений в Google, вы можете отправлять внутренние события приложения в свою учётную запись Google Ads из своей учётной записи AppsFlyer.

#### Создание конверсии (внутренние события приложения)

Подробное описание измерения конверсий для приложения см. <Anchor target="_blank" href="/marketers/ru/docs/google-ads-adwords-integration-setup-for-advertisers#step-4-measure-your-app-conversions-mandatory">здесь</Anchor>.

</Accordion>

<div id="ios-configuration-for-google-ads" />

<Accordion title="Настройки iOS для Google Ads">

#### Google Ads – Настройки для iOS-приложений: кампании для приложения

Кампании для приложений позволяют продвигать ваше iOS-приложение в Google Search, YouTube и оторбражать его в одном месте.

Как правило, Google не может самостоятельно атрибутировать установки приложений для устройств iOS, полученные в результате поисковых кампаний, поскольку нажатия поступают из мобильных веб-источников, что не позволяет Google извлекать из устройств идентификаторы IDFA и выполнять сопоставление идентификаторов.

Однако **Google Ads может атрибутировать поиск iOS в ходе кампаний для приложений** по объявлениям, которые размещаются в **приложении Google Search**.

#### Настройка регистрации конверсий (установок)

Подробное описание настройки регистрации конверсий см. <Anchor target="_blank" href="/marketers/ru/docs/google-ads-adwords-integration-setup-for-advertisers#step-2-set-up-google-ads-on-appsflyer-mandatory">здесь</Anchor>.

#### Google Ads – Настройки для iOS-приложений – Отправка внутренних событий приложений

Для лучшего измерения успеха своих кампаний по продвижению мобильных приложений в Google, вы можете отправлять внутренние события приложения в свою учётную запись Google Ads из своей учётной записи AppsFlyer.

#### Создание конверсии (внутренние события приложения)

Подробное описание измерения конверсий для приложения см. <Anchor target="_blank" href="/marketers/ru/docs/google-ads-adwords-integration-setup-for-advertisers#step-4-measure-your-app-conversions-mandatory">здесь</Anchor>.

</Accordion>

</Accordion>

<div id="for-how-long-do-you-keep-google-ads--userlevel-data" />

<Accordion title="Сколько времени хранятся данные Google Ads пользовательского уровня?">

Google Ads требует от поставщиков атрибуции удалять свои данные уровня пользователей через 6 месяцев после установки. Это означает, что события этих пользователей, которые произошли через 6 месяцев после установки приложения, считаются органическими.

Агрегированные данные за прошлое время не изменяются.

Это относится ко всем каналам Google Ads.

</Accordion>

## Расхождения в данных с Google Ads

Иногда возможны расхождения между дэшбордами Google Ads и AppsFlyer.

Мы работаем в тесном контакте с Google Ads, чтобы свести к минимуму такие расхождения, тем не менее рекламодатели должны знать о том, с чем они связаны (см. ниже).

#### Для iOS и Android

| **Причина** | **Google реклама** | **AppsFlyer:** |
| --- | --- | --- |
| **Моделируемые конверсии и конверсии ICM** | Google Ads показывает моделируемые установки, сгенерированные внутренним моделированием Google, и не показывает установки, основанные на ICM. | AppsFlyer показывает моделируемые установки, сгенерированные Google ICM (вероятностные заявки), и не показывает внутренние моделируемые установки Google. |
| **Вспомогательные установки (ассисты) (также многоканальная атрибуция)** | Поскольку Google Ads – это сеть SRN, все установки, связанные с Google Ads, атрибутируются в пределах заданного окна атрибуции. | AppsFlyer атрибутирует только по последнему клику на пути пользователя и рассматривает взаимодействия, произошедшие до него, как <Anchor target="_blank" href="/marketers/ru/docs/measure-assisted-installs">вспомогательные</Anchor>. |
| **Время регистрации установки** | Google Ads атрибутирует конверсию по времени клика. | AppsFlyer атрибутирует конверсию по времени запуска приложения (событие открытия приложения). |
| **Часовые пояса** | Меняются в зависимости от местонахождения. | Меняются в зависимости от местонахождения. |
| **Окно атрибуции** | 30 дней. | При интеграции с Google по умолчанию устанавливается окно 30 дней (можно изменить). |
| **Конверсии по просмотрам** | Конверсии по просмотрам отображаются только в столбце **Все конверсии** , а не в столбце **Конверсии** , если только в Google Ads не указано иное. | AppsFlyer отображает общее количество установок, атрибуцию установок по кликам и по просмотрам. |
| **Повторные установки** | Google Ads отображает повторные установки как конверсию session\_start. | AppsFlyer атрибутирует и отображает повторные установки (повторную атрибуцию) как часть данных по ретаргетингу. |
| **Внутренние события приложений** | Google Ads атрибутирует внутреннее событие приложения по времени нажатия. | На дэшборде AppsFlyer внутренние события приложения атрибутируются в зависимости от времени установки. В отчетах по сырым данным AppsFlyer атрибутирует внутренние события приложения в зависимости от времени события. |
| **Правила валидации** | Google получает от AppsFlyer всю информацию независимо от правил проверки. | AppsFlyer может исключить некоторые установки исходя из своих правил проверки. |
| **Затраты – каналы кампаний Google Ads** | Google сообщает о затратах на все каналы в рамках данной кампании – YouTube, отображение, поиск. | AppsFlyer получает от Google данные о затратах на все каналы кампании, но атрибутирует только конверсии из YouTube и каналов отображения в кампании для iOS-приложений. В результате общий показатель CPI в AppsFlyer выше. |
| **Установки SKAN** | Начиная с версии 10 API Google Ads и выше, дэшборд Google Ads не различает установки с did\_win=TRUE и did\_win=NULL. Различие отражается только в сырых данных. | Начиная с версии 10 API Google Ads и выше, AppsFlyer отображает только установки из постбэков с параметром did\_win=TRUE. В результате число установок в AppsFlyer может быть ниже. |
| **События first\_open** | Google Ads получают события из Firebase, где DMA реализован правильно, и как следствие заявляются события с согласованием DMA. | Google Ads получают те же события также от AppsFlyer, где DMA реализован неверно, что приводит к тому, что все события сообщаются как не согласованные с DMA, и Google не может на них претендовать.<ul><li>Чтобы проверить, правильно ли реализован DMA <Anchor target="_blank" href="/marketers/ru/docs/raw-data-export-page#download-report">скачайте отчет о сырых данных</Anchor> и обратите внимание на поля, указанные в <Anchor target="_blank" href="/marketers/ru/docs/bulletin-dma-support-in-raw-data-reports">этом бюллетене</Anchor>.</li><li>См. [Раздел для разработчиков](https://dev.appsflyer.com/hc/docs/send-consent-for-dma-compliance), чтобы узнать, как реализовать DMA в SDK</li></ul> |
| **События ретаргетинга** | Google Ads может заявить о повторном взаимодействии с `ad_type=ClickToDownload` в ответе. | AppsFlyer считает `ad_type=ClickToDownload` событием конверсии UA, а не повторным вовлечением. В результате число повторных вовлечений в AppsFlyer может быть ниже. |

> 📘 **Примечания**
>
> * В то время как в Google Ads все установки в рамках ретаргетинговой кампании отображаются в одном месте, на обзорном дэшборде AppsFlyer в представлении UA отображаются новые установки, в представлении ретаргетинга – повторные атрибуции, а в объединенном представлении – оба типа.
> * Сравнивая данные в дэшборде Google Ads с данными в AppsFlyer, убедитесь, что данные в дэшборде Google Ads – это данные, импортированные из сервиса аналитики сторонних приложений (AppsFlyer). Данные, импортированные из Firebase или Google Play, имеют другую структуру, поэтому их невозможно полностью сопоставить с данными AppsFlyer. Сведения о том, как импортировать данные из AppsFlyer в дэшборд Google Ads, см. <Anchor target="_blank" href="/marketers/ru/docs/google-ads-adwords-integration-setup-for-advertisers#step-4-measure-your-app-conversions-mandatory">здесь</Anchor>.
> * Чтобы сравнить события установки (first\_open в Google Ads), нужно детально проанализировать события установки в отчёте о конверсиях в Google Ads. В Google Ads могут отображаться все конверсии (например, установки, покупки, подписки), поэтому необходимо выбирать из всех событий конверсии только события установки.

> 📄 **См. также**
>
> * Для получения информации, связанной с iOS 14, см. раздел <Anchor target="_blank" href="/marketers/ru/docs/get-skan-postback-data-from-google-ads">Совместимость Google Ads SKAdNetwork с AppsFlyer</Anchor>.

<div data-zendesk-anchors="google-ads-faq=%D0%B2%D0%BE%D0%BF%D1%80%D0%BE%D1%81%D1%8B-%D0%B8-%D0%BE%D1%82%D0%B2%D0%B5%D1%82%D1%8B-%D0%BF%D0%BE-google-ads h_01HA1SM7D91QPG17WH752FBAFT=%D0%B2%D0%BE%D0%BF%D1%80%D0%BE%D1%81%D1%8B-%D0%B8-%D0%BE%D1%82%D0%B2%D0%B5%D1%82%D1%8B-%D0%BF%D0%BE-google-ads h_01HA1SM7D9JWBEPNE0E8FE665E=why-am-i-not-seeing-clicks-from-google-ads h_01HA1SM7DAW984PPRGHXA5BYSX=why-am-i-not-seeing-first_open-conversions-on-google-ads why-don%E2%80%99t-i-see-installs-from-google-ads=why-don-t-i-see-installs-from-google-ads h_01K5DZBDMS0D2S5XYDC22WQ19H=why-don-t-i-see-installs-from-google-ads quick-fix=%D0%B1%D1%8B%D1%81%D1%82%D1%80%D0%BE%D0%B5-%D1%80%D0%B5%D1%88%D0%B5%D0%BD%D0%B8%D0%B5 h_01K5DZBDMSBDKAFHVVPYD6YKRK=%D0%B1%D1%8B%D1%81%D1%82%D1%80%D0%BE%D0%B5-%D1%80%D0%B5%D1%88%D0%B5%D0%BD%D0%B8%D0%B5 still-not-working=%D0%B2%D1%81%D0%B5-%D0%B5%D1%89%D0%B5-%D0%BD%D0%B5-%D1%80%D0%B0%D0%B1%D0%BE%D1%82%D0%B0%D0%B5%D1%82 h_01K5DZBDMSVTE6M2J235ST85DE=%D0%B2%D1%81%D0%B5-%D0%B5%D1%89%D0%B5-%D0%BD%D0%B5-%D1%80%D0%B0%D0%B1%D0%BE%D1%82%D0%B0%D0%B5%D1%82 h_01K7NT8FVC3K3861WN9VKRZ2HB=why-dont-i-see-inapp-events-in-the-google-ads-dashboard quick-fix-checklist=%D0%BA%D0%BE%D0%BD%D1%82%D1%80%D0%BE%D0%BB%D1%8C%D0%BD%D1%8B%D0%B9-%D1%81%D0%BF%D0%B8%D1%81%D0%BE%D0%BA-%D0%B4%D0%BB%D1%8F-%D0%B1%D1%8B%D1%81%D1%82%D1%80%D0%BE%D0%B3%D0%BE-%D0%B8%D1%81%D0%BF%D1%80%D0%B0%D0%B2%D0%BB%D0%B5%D0%BD%D0%B8%D1%8F h_01K7NT8FVC1T557GPG7ZCYX33J=%D0%BA%D0%BE%D0%BD%D1%82%D1%80%D0%BE%D0%BB%D1%8C%D0%BD%D1%8B%D0%B9-%D1%81%D0%BF%D0%B8%D1%81%D0%BE%D0%BA-%D0%B4%D0%BB%D1%8F-%D0%B1%D1%8B%D1%81%D1%82%D1%80%D0%BE%D0%B3%D0%BE-%D0%B8%D1%81%D0%BF%D1%80%D0%B0%D0%B2%D0%BB%D0%B5%D0%BD%D0%B8%D1%8F h_01K7PAH7VDS7NGW6R6HERGXK9H=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%87%D0%B0%D0%BD%D0%B8%D0%B5 still-not-working::77f3165b=%D0%B2%D1%81%D0%B5-%D0%B5%D1%89%D0%B5-%D0%BD%D0%B5-%D1%80%D0%B0%D0%B1%D0%BE%D1%82%D0%B0%D0%B5%D1%82-1 h_01K7NT8FVCD4DNFKP3DS75ZKR0=%D0%B2%D1%81%D0%B5-%D0%B5%D1%89%D0%B5-%D0%BD%D0%B5-%D1%80%D0%B0%D0%B1%D0%BE%D1%82%D0%B0%D0%B5%D1%82-1 h_01HA1SM7DACQDVGWGKV5MZ63D6=can-i-stop-google-cost-sync h_01HA1SM7DA415FQP3MFC09AE3Y=do-i-need-to-create-and-then-import-session_start h_01HA1SM7DAEKGVPDTX77RJ9Y37=can-i-send-uninstall-information-to-google-ads h_01HA1SM7DAKKVZ82WF6RVEDHE9=what-google-ads-data-does-appsflyer-display h_01HA1SM7DANYQ0DAY54CH4HPV4=do-i-need-to-configure-anything-to-create-audience-lists-in-google-ads-based-on-appsflyer-data h_01HA1SM7DA3XF8NBGYGZ0XTB69=im-running-an-app-campaign-why-cant-i-see-data-or-conversion-events-in-the-appsflyer-or-google-ads-dashboard h_01HA1SM7DAY7JNTFSG86A1QGKC=what-do-i-do-if-there-are-multiple-accounts h_01HA1SM7DAYSVMENT91T2BE26Z=what-happens-with-link-ids-created-at-mcc-level-vs-account-level h_01HA1SM7DAK186BRZN970PKPRM=what-is-parallel-tracking additional-information=%D1%87%D1%82%D0%BE-%D0%BD%D0%B5%D0%BE%D0%B1%D1%85%D0%BE%D0%B4%D0%B8%D0%BC%D0%BE h_01HA1SM7DAMNG8X22VNWMKBJ8R=%D1%87%D1%82%D0%BE-%D0%BD%D0%B5%D0%BE%D0%B1%D1%85%D0%BE%D0%B4%D0%B8%D0%BC%D0%BE h_01HA1SM7DBNAS6DP8G9D8KFHPW=how-do-you-configure-a-campaign-with-android-or-ios-configuration h_01HA1SM7DB16T3RGBVGT5Z9REW=%D0%B2%D0%B0%D0%B6%D0%BD%D0%BE h_01HA1SM7DBC38CY8AN3EPMMJFW=android-configuration-for-google-ads creating-conversion-recording-installs=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-%D1%80%D0%B5%D0%B3%D0%B8%D1%81%D1%82%D1%80%D0%B0%D1%86%D0%B8%D0%B8-%D0%BA%D0%BE%D0%BD%D0%B2%D0%B5%D1%80%D1%81%D0%B8%D0%B9-%D1%83%D1%81%D1%82%D0%B0%D0%BD%D0%BE%D0%B2%D0%BE%D0%BA h_01HA1SM7DBF9KDRNEV25KJHGHN=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-%D1%80%D0%B5%D0%B3%D0%B8%D1%81%D1%82%D1%80%D0%B0%D1%86%D0%B8%D0%B8-%D0%BA%D0%BE%D0%BD%D0%B2%D0%B5%D1%80%D1%81%D0%B8%D0%B9-%D1%83%D1%81%D1%82%D0%B0%D0%BD%D0%BE%D0%B2%D0%BE%D0%BA create-a-conversion-inapp-events=%D1%81%D0%BE%D0%B7%D0%B4%D0%B0%D0%BD%D0%B8%D0%B5-%D0%BA%D0%BE%D0%BD%D0%B2%D0%B5%D1%80%D1%81%D0%B8%D0%B8-%D0%B2%D0%BD%D1%83%D1%82%D1%80%D0%B5%D0%BD%D0%BD%D0%B8%D0%B5-%D1%81%D0%BE%D0%B1%D1%8B%D1%82%D0%B8%D1%8F-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D1%8F h_01HA1SM7DBDQVNDQ5GG7X2PJ8K=%D1%81%D0%BE%D0%B7%D0%B4%D0%B0%D0%BD%D0%B8%D0%B5-%D0%BA%D0%BE%D0%BD%D0%B2%D0%B5%D1%80%D1%81%D0%B8%D0%B8-%D0%B2%D0%BD%D1%83%D1%82%D1%80%D0%B5%D0%BD%D0%BD%D0%B8%D0%B5-%D1%81%D0%BE%D0%B1%D1%8B%D1%82%D0%B8%D1%8F-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D1%8F h_01HA1SM7DBKKQ9R8MQMQT9GRXV=ios-configuration-for-google-ads google-ads-ios-configuration-app-campaigns=google-ads--%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B8-%D0%B4%D0%BB%D1%8F-ios-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D0%B9-%D0%BA%D0%B0%D0%BC%D0%BF%D0%B0%D0%BD%D0%B8%D0%B8-%D0%B4%D0%BB%D1%8F-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D1%8F h_01HA1SM7DBNSDFCJA5BP59MMQ2=google-ads--%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B8-%D0%B4%D0%BB%D1%8F-ios-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D0%B9-%D0%BA%D0%B0%D0%BC%D0%BF%D0%B0%D0%BD%D0%B8%D0%B8-%D0%B4%D0%BB%D1%8F-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D1%8F creating-conversion-recording-installs::6a56eb4b=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-%D1%80%D0%B5%D0%B3%D0%B8%D1%81%D1%82%D1%80%D0%B0%D1%86%D0%B8%D0%B8-%D0%BA%D0%BE%D0%BD%D0%B2%D0%B5%D1%80%D1%81%D0%B8%D0%B9-%D1%83%D1%81%D1%82%D0%B0%D0%BD%D0%BE%D0%B2%D0%BE%D0%BA-1 h_01HA1SM7DBXCT0NS4W50D4ZGEK=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-%D1%80%D0%B5%D0%B3%D0%B8%D1%81%D1%82%D1%80%D0%B0%D1%86%D0%B8%D0%B8-%D0%BA%D0%BE%D0%BD%D0%B2%D0%B5%D1%80%D1%81%D0%B8%D0%B9-%D1%83%D1%81%D1%82%D0%B0%D0%BD%D0%BE%D0%B2%D0%BE%D0%BA-1 google-ads-ios-configuration-sending-inapp-events=google-ads--%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B8-%D0%B4%D0%BB%D1%8F-ios-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D0%B9--%D0%BE%D1%82%D0%BF%D1%80%D0%B0%D0%B2%D0%BA%D0%B0-%D0%B2%D0%BD%D1%83%D1%82%D1%80%D0%B5%D0%BD%D0%BD%D0%B8%D1%85-%D1%81%D0%BE%D0%B1%D1%8B%D1%82%D0%B8%D0%B9-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D0%B9 h_01HA1SM7DBEV9CJTAB5YHRJHYK=google-ads--%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B8-%D0%B4%D0%BB%D1%8F-ios-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D0%B9--%D0%BE%D1%82%D0%BF%D1%80%D0%B0%D0%B2%D0%BA%D0%B0-%D0%B2%D0%BD%D1%83%D1%82%D1%80%D0%B5%D0%BD%D0%BD%D0%B8%D1%85-%D1%81%D0%BE%D0%B1%D1%8B%D1%82%D0%B8%D0%B9-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D0%B9 creating-a-conversion-inapp-events=%D1%81%D0%BE%D0%B7%D0%B4%D0%B0%D0%BD%D0%B8%D0%B5-%D0%BA%D0%BE%D0%BD%D0%B2%D0%B5%D1%80%D1%81%D0%B8%D0%B8-%D0%B2%D0%BD%D1%83%D1%82%D1%80%D0%B5%D0%BD%D0%BD%D0%B8%D0%B5-%D1%81%D0%BE%D0%B1%D1%8B%D1%82%D0%B8%D1%8F-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D1%8F-1 h_01HA1SM7DBCQYSJ3R67F0856QK=%D1%81%D0%BE%D0%B7%D0%B4%D0%B0%D0%BD%D0%B8%D0%B5-%D0%BA%D0%BE%D0%BD%D0%B2%D0%B5%D1%80%D1%81%D0%B8%D0%B8-%D0%B2%D0%BD%D1%83%D1%82%D1%80%D0%B5%D0%BD%D0%BD%D0%B8%D0%B5-%D1%81%D0%BE%D0%B1%D1%8B%D1%82%D0%B8%D1%8F-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D1%8F-1 for-how-long-do-you-keep-google-ads%E2%80%99-userlevel-data=for-how-long-do-you-keep-google-ads--userlevel-data h_01HA1SM7DBFAAV7C4ENA34B7JP=for-how-long-do-you-keep-google-ads--userlevel-data google-ads-discrepancies=%D1%80%D0%B0%D1%81%D1%85%D0%BE%D0%B6%D0%B4%D0%B5%D0%BD%D0%B8%D1%8F-%D0%B2-%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D1%85-%D1%81-google-ads h_01HA1SM7DBA7KK1DXFCE2G0QTP=%D1%80%D0%B0%D1%81%D1%85%D0%BE%D0%B6%D0%B4%D0%B5%D0%BD%D0%B8%D1%8F-%D0%B2-%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D1%85-%D1%81-google-ads both-ios-and-android=%D0%B4%D0%BB%D1%8F-ios-%D0%B8-android h_01HA1SM7DB18BTDKK5BK4949HX=%D0%B4%D0%BB%D1%8F-ios-%D0%B8-android h_01HA1SM7DBSTAREA36YWRRRG82=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%87%D0%B0%D0%BD%D0%B8%D1%8F h_01HDP2XBSEJVQ5G0MD0V5R05CM=%D1%81%D0%BC-%D1%82%D0%B0%D0%BA%D0%B6%D0%B5" />
