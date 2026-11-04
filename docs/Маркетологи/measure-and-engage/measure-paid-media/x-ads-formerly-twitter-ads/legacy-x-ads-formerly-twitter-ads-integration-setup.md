---
title: '[Legacy] Настройка интеграции X Ads (ранее Twitter Ads)'
deprecated: true
metadata:
  keywords:
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
  created_at: '2025-06-22T11:41:06Z'
  edited_at: '2026-09-23T00:15:42Z'
  id: 36433415114769
  locale: ru
  section: X Ads (formerly Twitter Ads)
  section_id: 6551370375569
  url: https://support.appsflyer.com/hc/ru/articles/36433415114769
---
> **Краткий обзор:** Интеграция аккаунта X Ads с AppsFlyer для отображения данных об атрибуции по всем кампаниям X Ads.

<div id="connecting-your-x-ads-account-to-appsflyer" />

## Подключение аккаунта X Ads к AppsFlyer

<Accordion title="Посмотреть">

<Embed title="[Legacy] Настройка интеграции X Ads (ранее Twitter Ads)" typeOfEmbed="iframe" url="https://fast.wistia.com/embed/iframe/a65pnqoyxw" providerUrl="https://fast.wistia.com" />

</Accordion>

<Accordion title="Прочитать">

<div id="before-you-begin" />

> 📘 **Прежде чем начать**
>
> Убедитесь, что в ваш аккаунт X Ads <Anchor target="_blank" href="https://business.twitter.com/en/help/account-setup/billing-basics.html">добавлен способ оплаты</Anchor>. В противном случае вы не сможете активировать партнерскую интеграцию в AppsFlyer.

1. Войдите в свой аккаунт X Ads на сайте <Anchor target="_blank" href="https://ads.twitter.com">ads.twitter.com</Anchor>  
   Если вы не были автоматически перенаправлены на страницу рекламы, нажмите кнопку Ads в левом верхнем углу.
2. Когда появится запрос на выбор кампании **Simple (NEW)** (Простая (Новое)) или **Advanced** (Расширенная), выберите **Advanced**.
3. В разделе **Campaign objective** (Цели кампании) выберите **App Installs** (Установки приложения) или **App re-engagements** (Повторное взаимодействие с приложением), затем нажмите **Далее**.

   ![twitter-campaign-objective.png](https://files.readme.io/44e5aca3895fc5aefa22f91542b9c23f9798b246ac8086e97a3994244fc2c5a8-36433415100561.png)
4. Выберите свое приложение, затем нажмите **партнер по мобильным измерениям** .
5. На странице **Conversion tracking** (Отслеживание конверсий) нажмите **Go to AppsFlyer** (Перейти в AppsFlyer). 

   ![twitter-mmp-selection.png](https://files.readme.io/718bc93d2fcf606a8c165aed70364659ba23b74891b22775c5522ee9e4c7901a-36433422307345.png)
6. На экране появится уведомление о том, что вы собираетесь покинуть X Ads и перейти на сайт AppsFlyer. Нажмите кнопку **Go to AppsFlyer** (Перейти в AppsFlyer) и войдите в свой дэшборд.

   <Image alt="twitter-go-to-appsflyer.png" src="https://files.readme.io/bca10eea5032a495fd38c996d0aa4a9f2db8a285211e6cf0860dd6f21bcfa670-36433422307601.png" width="576px" />
7. В AppsFlyer в боковом меню выберите **Сотрудничество** > **Партнерские интеграции > Маркетплейс.**
8. Найдите **X Ads** и выберите его.
9. На вкладке **Интеграция** примите условия X Ads по использованию услуги регистрации конверсий для мобильных приложений (Mobile App Conversion Recording, MACT) и нажмите **Сохранить интеграцию**.
10. Включите **Активировать партнера** и нажмите **Войти через X Ads**.
11. Разрешите AppsFlyer использовать ваш аккаунт X Ads, нажав **Авторизовать приложение**.

    [<Image alt="" src="https://support.appsflyer.com/hc/en-us/article_attachments/4411037924497/Twitter_Ads_6.png" width="476px" />](https://support.appsflyer.com/hc/en-us/article_attachments/4411037924497/Twitter_Ads_6.png)
12. Включите **Активировать партнера** снова, чтобы отобразить настройки вкладки **Интеграция** и включить атрибуцию.  
    **Примечание:** Этот переключатель должен быть активирован все время, пока вы работаете с этим партнёром. Подробнее об <Anchor target="_blank" href="/marketers/ru/docs/partner-activation-deactivation">активации партнеров</Anchor>.
13. Выберите свои аккаунты X Ads, чтобы активировать их, затем нажмите **Сохранить и закрыть**.

    ![twitter_account_name.png](https://files.readme.io/d74e9b3edd08c4ca3396b95ae20e20db99bcbe1a220318403bd6c9d6f9600282-36433415108497.png)

</Accordion>

<div id="x-ads-attribution-setup" />

## Настройка атрибуции X Ads

Подробное описание страницы настроек партнера см. <Anchor target="_blank" href="/marketers/ru/docs/set-up-an-integrated-partner">здесь</Anchor>.

<div id="integration-tab" />

<Accordion title="Вкладка «Интеграция»">

На вкладке **Интеграция** есть несколько разделов, которые описаны ниже. Чтобы задать настройки для партнера, необходимо <Anchor target="_blank" href="/marketers/ru/docs/partner-activation-deactivation">активировать этого партнера</Anchor> при первом посещении вкладки.

<div id="ad-account-connected" />

### Ad Account Connected (Связанный рекламный аккаунт)

Выберите аккаунты, для которых нужно активировать атрибуцию.

![Twitter_msc_new_4.png](https://files.readme.io/8b8ecdfd79bc87d4a65766ce67e48a06524d825e04d5e642eb5e9741069a2f6c-36433422308241.png)

<div id="click-through-attribution" />

### Атрибуция по кликам

На этой шкале можно задать **максимальное время от клика до установки**. К X Ads атрибутируются только те установки (первые запуски), которые произошли в пределах окна атрибуции.

Это значение можно задать в часах (от 1 до 23) или в днях (от 1 до 30). Мы рекомендуем задать для окна атрибуции по кликам значение 14 дней, что соответствует стандартному значению этого параметра в X Ads.

![Twitter_msc_new_6.png](https://files.readme.io/359f6145751f45d38c151572f1ba0c525d232d16ffaee6b68453da0bc1826a69-36433422308369.png)

<div id="view-through-attribution-lookback-window" />

### Окно лукбэк на основе просмотров

На этой шкале можно задать **максимальное время от показа до установки**. К X Ads атрибутируются только те установки (первые запуски), которые произошли в рамках окна атрибуции после показа рекламы, при условии отсутствия других кликов по объявлению, относящихся к этой установке.

Это значение можно задать в часах (от 1 до 23) или в днях (от 1 до 7). Мы рекомендуем установить значение окна атрибуции по просмотрам на 1 день, что соответствует стандартному значению этого параметра в X Ads.

![Twitter_msc_new_7.png](https://files.readme.io/15c9d815b05c03dfdf8578ed5af297c411991ab74accc5539fc1dbca178c3336-36433422308497.png)

<div id="re-engagement-settings" />

### Настройки повторного вовлечения

Для ретаргетинговых кампаний на X Ads AppsFlyer поддерживает **Re-engagement** только измерение. Это взаимодействие с кампанией повторного таргетинга со стороны пользователя, у которого на момент взаимодействия уже было установлено приложение. **В настоящее время измерение повторной атрибуции не поддерживается в X Ads.**

<div id="important" />

> 🚧 **Важно!**
>
> Убедитесь, что для приложения активирован ретаргетинг на странице "App Settings" (Настройки приложения). Для получения подробной информации нажмите <Anchor target="_blank" href="/marketers/ru/docs/app-settings#reengagement-attribution">здесь</Anchor>.

<div id="re-engagement-click-through-lookback-window" />

#### Окно атрибуции повторного вовлечения по кликам

Установите продолжительность **окна атрибуции повторного вовлечения по кликам** — максимальный период времени после клика по объявлению, в течение которого пользователя, на которого нацелен ретаргетинг, можно атрибутировать этому объявлению. Это значение можно задать в часах (до 23) или днях (1–30).

![twitter-reengagement-activate.png](https://files.readme.io/318deeab0432870035a163a7b8a5b8c03be7d683bfc369104c8577674fde0036-36433422309905.png)

<div id="re-engagement-view-through-lookback-window" />

#### Окно атрибуции повторного вовлечения по просмотрам

Чтобы начать атрибуцию показов рекламных объявлений ретаргетинга, активируйте **окно атрибуции повторного вовлечения по просмотрам**.

Установите продолжительность **окна атрибуции повторного вовлечения по просмотрам** — максимальный период времени после показа объявления, в течение которого пользователя, на которого нацелен ретаргетинг, можно атрибутировать этому объявлению. Это значение можно задать в часах (до 23) или днях (1-7):

![twitter-reengagement-view-through.png](https://files.readme.io/4faf93b6d8a8e45043eb9440d8f56a70eba2da51f3a572ea6cd698e072f033c6-36433415112849.png)

<div id="re-engagement-window" />

#### Окно повторного вовлечения

Установите продолжительность **Окно повторного вовлечения** — временной интервал, в течение которого внутренние события приложения пользователя будут атрибутироваться медиа-источнику ретаргетинга. Это значение можно задавать в днях (от 1 до 90), часах (до 23) или даже на весь период использования приложения.

![Twitter-reengagement-window.png](https://files.readme.io/5bc42bd967929a88fd38f8bdd9cc36046a6f0381d1883ab1f26f5c680185a74c-36433415113105.png)

<div id="in-app-event-postback-settings" />

### Настройки постбэков о внутренних событиях приложений

В этом разделе можно настроить отправку партнёру постбэков о своих событиях в AppsFlyer.

[![In-app_event_postbacks_en-us.png](https://files.readme.io/d89725172c53c309b5b58227ce53812e12f9cd4ee7611a6c375970b395122b15-36433415113361.png)](https://files.readme.io/d89725172c53c309b5b58227ce53812e12f9cd4ee7611a6c375970b395122b15-36433415113361.png)

**Чтобы настроить постбэки для внутренних событий приложения:**

1. При необходимости задайте **Partner ID** (Идентификатор партнера).
2. Активируйте **постбэки по внутренним событиям**.
3. Чтобы добавить в список событие, определенное в SDK, или межсерверное событие, нажмите **Add Event** (Добавить событие).
4. Заполните необходимые параметры, как указано в таблице ниже.

| Параметр | Description(Описание) |
| --- | --- |
| **Событие AppsFlyer** | Имя события, полученное AppsFlyer из SDK, интегрированного в приложение, или из межсерверного события.<br />**Совет**: Не нашли здесь нужное событие?<ul><li>Убедитесь, что событие активировано на устройстве с неорганической установкой, и повторите поиск.</li><li>Введите его в поле **Событие AppsFlyer** и нажмите **Добавить другое**. Узнайте больше о <Anchor target="_blank" href="/marketers/ru/docs/in-app-event-postback-configuration#пользовательские-события">сопоставлении пользовательских событий</Anchor>.</li></ul> |
| **сопоставлено с событием партнёра** | Уникальное имя или идентификатор каждого события, определённого на стороне партнёра. Возможные <Anchor target="_blank" href="/marketers/ru/docs/in-app-event-postback-configuration#сопоставление-событий">настройки сопоставления</Anchor>:<ul><li>**Текстовое поле**. Введите в него соответствующий идентификатор события, полученный от партнера.</li><li>**Раскрывающийся список**. Выберите наиболее подходящее предопределенное событие AppsFlyer.</li><li>Переход к маркетплейс: в верхнем меню любой страницы AppsFlyer нажмите **Маркетплейс**.</li></ul> |
| **для пользователей из** | Выберите вариант отправки для события:<br /><br /><br /><br />**Примечание:**<br />Чтобы X Ads получал постбэки, атрибутированные агентствам, вы должны выбрать **Все медиа-источники и органический трафик**. В противном случае X Ads не будет получать такие постбэки.<ul><li>**Только этот партнер**: постбэки отправляются только в том случае, когда событие атрибутируется этому партнеру.</li><li>**Все медиа-источники, включая органические**: отправляйте постбэки для событий, атрибутированных любому партнеру, включая органические.</li></ul> |
| **включая** | <ul><li>**Нет данных (по умолчанию)**: отправляет только само событие без значения.</li><li>**Значения и доход**: отправляет все параметры события, **включая** значение дохода (если оно есть в событии).</li><li>**Значения без дохода**: отправляет все параметры, **кроме** значения дохода.</li></ul> |

5. [Необязательно] Нажмите <Image alt="conditional-iae-postbacks-icon.png" src="https://files.readme.io/575c9ab0dd82a125319591072b17604a7f9d1b71fff6baff4124d99edc1a7fc7-16570673855121.png" width="30px" />, чтобы задать условия отправки партнеру определенных событий в приложении.  
   Подробнее об <Anchor target="_blank" href="/marketers/ru/docs/in-app-event-postback-configuration#условные-постбэки-по-событиям-в-приложении">условных постбэках по внутренним событиям приложения</Anchor>.

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Вкладка «Ссылки атрибуции»">

В X Ads ссылки атрибуции не используются.

<div id="note" />

> 📘 **Примечание**
>
> Эта вкладка неприменима для <Anchor target="_blank" href="/marketers/ru/docs/self-reporting-networks-srns">сетей с самостоятельной атрибуцией (SRN)</Anchor>, таких как Meta Ads, Apple Search Ads, Google Реклама, X Ads и т.д., поскольку в них не используются внешние ссылки атрибуции.

</Accordion>

<div id="cost-tab" />

<Accordion title="Вкладка «Стоимость»">

Интеграция затрат предоставляет следующие агрегированные данные:

* Данные по затратам для кампаний, групп объявлений, объявлений, каналов и регионов/стран. Подробную информацию о поддерживаемых параметрах, метриках и функциях см. в таблице <Anchor target="_blank" href="/marketers/ru/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api">интеграции затрат рекламной сети</Anchor>.  
  **Примечание:** Для получения данных о затратах требуется подписка на <Anchor target="_blank" href="/marketers/ru/docs/roi360-cost-aggregation-overview?query=xpend">ROI360</Anchor>.
* Данные о кликах, показах и расширенные данные (ключевые слова, названия кампаний и группы объявлений).

**Чтобы включить API данных о затратах:**

* Следуйте соответствующему методу в <Anchor target="_blank" href="/marketers/ru/docs/roi360-guide-ad-revenue-attribution#внедрение">руководстве по интеграции выручки от рекламы.</Anchor>

<Anchor target="_blank" href="/marketers/ru/docs/set-up-roi360-cost-api-to-measure-cost-data#статус-api-затрат">Просмотрите статус вашего API данных о затратах</Anchor> и время, когда AppsFlyer получил соответствующие данные о затратах в последний раз, либо на дэшборде статуса интеграции затрат (и доходов от рекламы), либо на дэшборде отдельной рекламной сети.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Вкладка «Доходы от рекламы»">

Доход от рекламы в настоящее время недоступен для X Ads.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Вкладка Permissions (Разрешения)">

На этой вкладке можно выбрать разрешения для X Ads в зависимости от того, в каком качестве выступает партнер: как рекламная сеть, агентство или и то, и другое. Обратите внимание, что, даже если атрибуция для X Ads отключена, вкладка разрешений остается активной и вы можете предоставить X Ads разрешение на управление.

Используйте эти переключатели, чтобы уполномочить рекламную сеть самостоятельно обрабатывать конфигурацию для вашего приложения:

<div id="ad-network-permissions" />

### Разрешения для рекламной сети

* **Разрешение настраивать интеграцию**: разрешить партнеру управлять настройками на вкладке интеграции (за исключением постбэков по внутренним событиям приложений).
* **Разрешение настраивать постбэки по событиям внутри приложения**: разрешить партнеру сопоставлять себе постбэки по внутренним событиям приложений на вкладке интеграции.
* **Предоставление доступа к отчету об удержании пользователей**: партнер получает доступ только к собственным данным об удержании пользователей.
* **Allow access to your aggregate loyal user data** (Разрешить доступ к агрегированным данным о лояльных пользователях): партнер получает доступ только к собственным данным о лояльных пользователях.
* **Allow access to your aggregate in-app event data** (Разрешить доступ к агрегированным данным о внутренних событиях приложения): партнер получает доступ только к собственным данным о внутренних событиях.
* **Предоставление доступа к агрегированным данным о доходе**: партнер получает доступ к данным только по атрибутированным ему доходам.
* **Разрешить доступ к дэшборду Protect360**: партнер получает доступ только к собственным данным Protect360, при условии что эта функция активирована для рекламодателя.

Подробнее о <Anchor target="_blank" href="/marketers/ru/docs/set-up-an-integrated-partner#permissions-tab">предоставлении разрешений рекламной сети</Anchor>.

<div id="agency-permissions" />

### Разрешения агентства

См. подробнее о <Anchor target="_blank" href="/marketers/ru/docs/set-up-an-integrated-partner#разрешения-агентства">предоставлении разрешений для агентства.</Anchor>

</Accordion>

<div id="advanced-x-ads-setup-video" />

## Видео о расширенной настройке XAds

<Accordion title="Посмотреть">

<Embed title="[Legacy] Настройка интеграции X Ads (ранее Twitter Ads)" typeOfEmbed="iframe" url="https://fast.wistia.com/embed/iframe/3ypfld8enr" providerUrl="https://fast.wistia.com" />

</Accordion>

<div id="traits-and-limitations" />

<Accordion title="Спецификации и ограничения">

| Специфика | Замечания |
| --- | --- |
| Атрибуция рекламы в начале ролика не поддерживается | X Ads не поддерживает атрибуцию MMP для кампаний с рекламой в начале ролика. |
| Названия | На дэшборде отображаются идентификаторы вместо названий для **line item names** (названий групп объявлений) и **post names** (названий рекламных объявлений). Это связано с тем, что AppsFlyer получает от X Ads только идентификаторы для этих элементов, а не их названия. |
| затраты; | Для X Ads данные о затратах для кампаний, имеющих только SKAN установки (без «обычных» установок), не доступны агентствам. Интеграция затрат должна быть настроена рекламодателем. А видеть данные может только рекламодатель. |

Спецификации и ограничения

</Accordion>

<div data-zendesk-anchors="connecting-your-twitter-ads-account-to-appsflyer=%D0%BF%D0%BE%D0%B4%D0%BA%D0%BB%D1%8E%D1%87%D0%B5%D0%BD%D0%B8%D0%B5-%D0%B0%D0%BA%D0%BA%D0%B0%D1%83%D0%BD%D1%82%D0%B0-xads-%D0%BA-appsflyer h_01HDJVCRYQESA17XZ83GS81YZ3=%D0%BF%D0%BE%D0%B4%D0%BA%D0%BB%D1%8E%D1%87%D0%B5%D0%BD%D0%B8%D0%B5-%D0%B0%D0%BA%D0%BA%D0%B0%D1%83%D0%BD%D1%82%D0%B0-xads-%D0%BA-appsflyer h_01HDJVBAEZXA0WJ94JYMK84MAX=%D0%BF%D1%80%D0%B5%D0%B6%D0%B4%D0%B5-%D1%87%D0%B5%D0%BC-%D0%BD%D0%B0%D1%87%D0%B0%D1%82%D1%8C twitter-ads-attribution-setup=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8-xads h_01HDJVBAEZ5W3JH1BN7WXJ08P6=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8-xads h_01HDJVBAEZSFKRXAKQJP58N550=integration-tab ad-account-connected=ad-account-connected-%D1%81%D0%B2%D1%8F%D0%B7%D0%B0%D0%BD%D0%BD%D1%8B%D0%B9-%D1%80%D0%B5%D0%BA%D0%BB%D0%B0%D0%BC%D0%BD%D1%8B%D0%B9-%D0%B0%D0%BA%D0%BA%D0%B0%D1%83%D0%BD%D1%82 h_01HDJVBAEZD89BSGHQTPR84HSC=ad-account-connected-%D1%81%D0%B2%D1%8F%D0%B7%D0%B0%D0%BD%D0%BD%D1%8B%D0%B9-%D1%80%D0%B5%D0%BA%D0%BB%D0%B0%D0%BC%D0%BD%D1%8B%D0%B9-%D0%B0%D0%BA%D0%BA%D0%B0%D1%83%D0%BD%D1%82 clickthrough-attribution=%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D1%8F-%D0%BF%D0%BE-%D0%BA%D0%BB%D0%B8%D0%BA%D0%B0%D0%BC h_01HDJVBAEZFJWQ6FD4Q4GSPD76=%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D1%8F-%D0%BF%D0%BE-%D0%BA%D0%BB%D0%B8%D0%BA%D0%B0%D0%BC viewthrough-attribution-lookback-window=%D0%BE%D0%BA%D0%BD%D0%BE-%D0%BB%D1%83%D0%BA%D0%B1%D1%8D%D0%BA-%D0%BD%D0%B0-%D0%BE%D1%81%D0%BD%D0%BE%D0%B2%D0%B5-%D0%BF%D1%80%D0%BE%D1%81%D0%BC%D0%BE%D1%82%D1%80%D0%BE%D0%B2 h_01HDJVBAEZ2H91WBHNSMRQYQ7H=%D0%BE%D0%BA%D0%BD%D0%BE-%D0%BB%D1%83%D0%BA%D0%B1%D1%8D%D0%BA-%D0%BD%D0%B0-%D0%BE%D1%81%D0%BD%D0%BE%D0%B2%D0%B5-%D0%BF%D1%80%D0%BE%D1%81%D0%BC%D0%BE%D1%82%D1%80%D0%BE%D0%B2 reengagement-settings=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B8-%D0%BF%D0%BE%D0%B2%D1%82%D0%BE%D1%80%D0%BD%D0%BE%D0%B3%D0%BE-%D0%B2%D0%BE%D0%B2%D0%BB%D0%B5%D1%87%D0%B5%D0%BD%D0%B8%D1%8F h_01HDJVBAEZZR1W06YH4XJSBKHV=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B8-%D0%BF%D0%BE%D0%B2%D1%82%D0%BE%D1%80%D0%BD%D0%BE%D0%B3%D0%BE-%D0%B2%D0%BE%D0%B2%D0%BB%D0%B5%D1%87%D0%B5%D0%BD%D0%B8%D1%8F h_01JV9YQ7ZHRDD2NA5ENQXJQ31V=%D0%B2%D0%B0%D0%B6%D0%BD%D0%BE reengagement-clickthrough-lookback-window=%D0%BE%D0%BA%D0%BD%D0%BE-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8-%D0%BF%D0%BE%D0%B2%D1%82%D0%BE%D1%80%D0%BD%D0%BE%D0%B3%D0%BE-%D0%B2%D0%BE%D0%B2%D0%BB%D0%B5%D1%87%D0%B5%D0%BD%D0%B8%D1%8F-%D0%BF%D0%BE-%D0%BA%D0%BB%D0%B8%D0%BA%D0%B0%D0%BC h_01HDJVBAEZ59ERYD2WQQYK6T37=%D0%BE%D0%BA%D0%BD%D0%BE-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8-%D0%BF%D0%BE%D0%B2%D1%82%D0%BE%D1%80%D0%BD%D0%BE%D0%B3%D0%BE-%D0%B2%D0%BE%D0%B2%D0%BB%D0%B5%D1%87%D0%B5%D0%BD%D0%B8%D1%8F-%D0%BF%D0%BE-%D0%BA%D0%BB%D0%B8%D0%BA%D0%B0%D0%BC reengagement-viewthrough-lookback-window=%D0%BE%D0%BA%D0%BD%D0%BE-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8-%D0%BF%D0%BE%D0%B2%D1%82%D0%BE%D1%80%D0%BD%D0%BE%D0%B3%D0%BE-%D0%B2%D0%BE%D0%B2%D0%BB%D0%B5%D1%87%D0%B5%D0%BD%D0%B8%D1%8F-%D0%BF%D0%BE-%D0%BF%D1%80%D0%BE%D1%81%D0%BC%D0%BE%D1%82%D1%80%D0%B0%D0%BC h_01HDJVBAEZSCK7430NJ8AMQYVY=%D0%BE%D0%BA%D0%BD%D0%BE-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8-%D0%BF%D0%BE%D0%B2%D1%82%D0%BE%D1%80%D0%BD%D0%BE%D0%B3%D0%BE-%D0%B2%D0%BE%D0%B2%D0%BB%D0%B5%D1%87%D0%B5%D0%BD%D0%B8%D1%8F-%D0%BF%D0%BE-%D0%BF%D1%80%D0%BE%D1%81%D0%BC%D0%BE%D1%82%D1%80%D0%B0%D0%BC reengagement-window=%D0%BE%D0%BA%D0%BD%D0%BE-%D0%BF%D0%BE%D0%B2%D1%82%D0%BE%D1%80%D0%BD%D0%BE%D0%B3%D0%BE-%D0%B2%D0%BE%D0%B2%D0%BB%D0%B5%D1%87%D0%B5%D0%BD%D0%B8%D1%8F h_01HDJVBAEZCMWY5X47FEEFXTBX=%D0%BE%D0%BA%D0%BD%D0%BE-%D0%BF%D0%BE%D0%B2%D1%82%D0%BE%D1%80%D0%BD%D0%BE%D0%B3%D0%BE-%D0%B2%D0%BE%D0%B2%D0%BB%D0%B5%D1%87%D0%B5%D0%BD%D0%B8%D1%8F inapp-event-postback-settings=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B8-%D0%BF%D0%BE%D1%81%D1%82%D0%B1%D1%8D%D0%BA%D0%BE%D0%B2-%D0%BE-%D0%B2%D0%BD%D1%83%D1%82%D1%80%D0%B5%D0%BD%D0%BD%D0%B8%D1%85-%D1%81%D0%BE%D0%B1%D1%8B%D1%82%D0%B8%D1%8F%D1%85-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D0%B9 h_01HDJVBAEZ5ZM9RDXPWTJPPYVA=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B8-%D0%BF%D0%BE%D1%81%D1%82%D0%B1%D1%8D%D0%BA%D0%BE%D0%B2-%D0%BE-%D0%B2%D0%BD%D1%83%D1%82%D1%80%D0%B5%D0%BD%D0%BD%D0%B8%D1%85-%D1%81%D0%BE%D0%B1%D1%8B%D1%82%D0%B8%D1%8F%D1%85-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D0%B9 h_01HDJVBAEZATGM580CNC7BCVTN=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%87%D0%B0%D0%BD%D0%B8%D0%B5 h_01HDJVBAEZR1Q2SVE9MEQ9EXKP=attribution-link-tab h_01HDJVBAEZ7R7BKFAZYXXBGS5Y=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%87%D0%B0%D0%BD%D0%B8%D0%B5 h_01HDJVBAEZYSWN59VNXTDEWX93=cost-tab h_01HDJVBAF0VPBBAEHJPG40HJP8=ad-revenue-tab h_01HDJVBAF0KEVSWJ0EW54AEAWV=permissions-tab ad-network-permissions=%D1%80%D0%B0%D0%B7%D1%80%D0%B5%D1%88%D0%B5%D0%BD%D0%B8%D1%8F-%D0%B4%D0%BB%D1%8F-%D1%80%D0%B5%D0%BA%D0%BB%D0%B0%D0%BC%D0%BD%D0%BE%D0%B9-%D1%81%D0%B5%D1%82%D0%B8 h_01HDJVBAF0BMSCKF6J9NJ019YJ=%D1%80%D0%B0%D0%B7%D1%80%D0%B5%D1%88%D0%B5%D0%BD%D0%B8%D1%8F-%D0%B4%D0%BB%D1%8F-%D1%80%D0%B5%D0%BA%D0%BB%D0%B0%D0%BC%D0%BD%D0%BE%D0%B9-%D1%81%D0%B5%D1%82%D0%B8 agency-permissions=%D1%80%D0%B0%D0%B7%D1%80%D0%B5%D1%88%D0%B5%D0%BD%D0%B8%D1%8F-%D0%B0%D0%B3%D0%B5%D0%BD%D1%82%D1%81%D1%82%D0%B2%D0%B0 h_01HDJVBAF0W3ZE7J93CRE8EBRP=%D1%80%D0%B0%D0%B7%D1%80%D0%B5%D1%88%D0%B5%D0%BD%D0%B8%D1%8F-%D0%B0%D0%B3%D0%B5%D0%BD%D1%82%D1%81%D1%82%D0%B2%D0%B0 advanced-twitter-ads-setup-video=%D0%B2%D0%B8%D0%B4%D0%B5%D0%BE-%D0%BE-%D1%80%D0%B0%D1%81%D1%88%D0%B8%D1%80%D0%B5%D0%BD%D0%BD%D0%BE%D0%B9-%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B5-xads h_01HDJVBAF0SJ93TNQ8WSFVE91P=%D0%B2%D0%B8%D0%B4%D0%B5%D0%BE-%D0%BE-%D1%80%D0%B0%D1%81%D1%88%D0%B8%D1%80%D0%B5%D0%BD%D0%BD%D0%BE%D0%B9-%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B5-xads h_01HGWGG2422VR9PFV88AMEHNT8=traits-and-limitations" />
