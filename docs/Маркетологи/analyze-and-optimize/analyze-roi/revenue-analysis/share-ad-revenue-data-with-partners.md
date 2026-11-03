---
title: Делитесь данными о рекламной выручке с партнёрами
metadata:
  keywords:
    - Premium
    - Marketers
    - ROI360
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-michael-talapov
    - Marketers
    - ROI360
  created_at: '2024-04-11T11:04:45Z'
  edited_at: '2026-09-17T00:01:59Z'
  id: 24100803679761
  locale: ru
  section: Revenue analysis
  section_id: 6551069075089
  url: https://support.appsflyer.com/hc/ru/articles/24100803679761
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **Краткий обзор:** Разрешите партнерам получать от сетей медиации информацию о доходе от рекламы, чтобы они могли оптимизировать свои UA-кампании (привлечение пользователей). **Примечание**: Требуется расширенная подписка ROI360.

## О совместном использовании данных о доходах от рекламы с партнёрами

Вы можете разрешить рекламным сетям, ответственным за привлечение пользователей, получать данные о доходах от рекламы от сетей-посредников. Партнёры использовать эту информацию для оптимизации своих UA-кампаний.

Партнёры могут получать данные о доходах от рекламы через:

* [Алгоритм действий](#ua-signals-for-ad-networks)
* [Постбэки по рекламному доходу для рекламных сетей](#ad-revenue-event-postbacks-for-ad-networks)

В следующей таблице приведено сравнение 2 решений по обмену данными о доходах от рекламы. 

| Решение для обмена данными о доходах от рекламы | Актуальность данных | Применение | Необходимый тип интеграции | Необходимый тип подписки |
| --- | --- | --- | --- | --- |
| UA-сигналы | Ежедневно | Точные и полные данные, обычно используются для оптимизации D3 и D7. | <ul><li>Уровень показов или устройства</li><li>Если настроены оба, отправляются данные на уровне устройства</li></ul> | Расширенный ROI360 |
| Постбэки | В реальном времени | Свежие данные, обычно используются для оптимизации D0 и D1. | На уровне показов | Расширенный ROI360 |

## Процедуры

<div id="ua-signals-for-ad-networks" />

<Accordion title="Сигналы UA для рекламных сетей">

Возможно, вы захотите работать с рекламными сетями, которые могут получать сигналы UA. Это означает, что рекламные сети, отвечающие за привлечение пользователей, могут получать от сетей-медиаторов данные о доходах от рекламы и использовать их для оптимизации UA-кампаний своих клиентов.

Чтобы отправлять UA-сигналы в рекламную сеть:

1. В AppsFlyer в боковом меню выберите **Сотрудничество** > **Интеграции партнеров** > **Активные интеграции**.
2. Выберите интегрированного партнёра.
3. Перейдите на вкладку **Интеграция**.
4. Проверьте, чтобы переключатель **Активировать партнёра** был включён. Если он отключён, данные не передаются.
5. Перейдите на вкладку **Разрешения**.
6. Включите **разрешения рекламной сети**.
7. Включите **доступ к сырым данным о доходах от рекламы (UA-сигналы)**.
8. В разделе **Вариант отправки** выберите, отправлять ли данные о доходе от рекламы только от этого партнера (**Только этот партнер**) или данные о доходе от рекламы из всех медиаисточников (**Все медиаисточники, включая органический**). **Примечание**: если выбран параметр **Все медиаисточники, включая органический**, данные для других партнеров не содержат данных атрибуции.
9. Нажмите **Сохранить настройки**.
10. Свяжитесь с рекламной сетью:
    1. уведомите их о том, что вы предоставили необходимые разрешения;
    2. сообщите им, что для получения отчёта необходимо следовать <Anchor target="_blank" href="/partners/ru/docs/ad-revenue-signals-for-ua-ad-networks#enable-the-ad-revenue-report">инструкции</Anchor>.

**Список партнёров-посредников, которые могут посылать сигналы UA рекламным сетям:**

* Applovin Max
* Google AdMob
* Appodeal
* Chartboost
* Fyber
* Tapdaq
* Topon
* Unity
* Посредник Unity LevelPlay (ранее ironSource)
* Admost
* Tradplusad
* Яндекс
* Пользовательский посредник

</Accordion>

<div id="ad-revenue-event-postbacks-for-ad-networks" />

<Accordion title="Постбэки по событиям рекламного дохода для рекламных сетей">

Вы можете настроить постбэки по событиям рекламного дохода для рекламных сетей. Это означает, что рекламные сети, отвечающие за привлечение пользователей, могут получать от сетей-посредников данные о доходах от рекламы в реальном времени и использовать их для оптимизации UA-кампаний своих клиентов. 

> 🚧 **Важно!**
>
> * Постбэки событий дохода от рекламы в рекламные сети работают только с <Anchor target="_blank" href="/marketers/ru/docs/roi360-guide-ad-revenue-attribution#integration-types-for-ad-revenue-attribution">типами интеграции</Anchor> дохода от рекламы Impression-level via SDK и Impression-level (via SDK) with device-level (via server-to-server (S2S) API). Это означает, что ваш разработчик должен интегрировать <Anchor target="_blank" href="/marketers/ru/docs/integrate-the-roi360-ad-revenue-sdk-api">API SDK от AppsFlyer для рекламного дохода</Anchor>.
> * Хотя вы можете отправлять постбэки по доходам от рекламы конкретным партнерам, перед началом интеграции рекомендуем проверить, как партнеры используют эти данные.

**Для настройки постбэков по событиям дохода от рекламы**:

1. Найдите и выберите своего партнера либо <Anchor target="_blank" href="/marketers/ru/docs/partner-integrations#manage-existing-integrations">в маркетплейсе</Anchor> либо на странице **Сотрудничество** > **Интеграции партнеров** > **Активные** **интеграции** .
2. На вкладке **Интеграция** прокрутите вниз и включите **постбэки по внутренним событиям приложения**.
3. Выберите событие AppsFlyer af\_ad\_revenue. **Примечание**: для некоторых интеграций с рекламными сетями есть возможность выбрать все события. Не используйте этот вариант, так в этом случае исключается событие af\_ad\_revenue.
4. Сопоставьте его с событием рекламной сети следующим образом:

| Рекламная сеть | Событие, с которым следует сопоставить af\_ad\_revenue | Снимок экрана |
| --- | --- | --- |
| Google реклама | ad\_impression | <Image alt="Сопоставление события ad_impression в Google Ads" src="https://files.readme.io/883dd04563027d722e7e8e76a50f813c8a955db827cbb92e94cdc650ab7b234d-50421403523601.png" width="238px" /> |
| Unity Ads | ad\_revenue | [![](https://files.readme.io/17edda24e3de024b1aaf10c1ca4c83da48b024f60aeeeaf9421502e88feb9a80-24100803652369.png)](https://files.readme.io/17edda24e3de024b1aaf10c1ca4c83da48b024f60aeeeaf9421502e88feb9a80-24100803652369.png) |
| Moloco | Сопоставление не требуется |  |
| Mintegral | Сопоставление не требуется |  |
| Smadex | Сопоставление не требуется |  |
| Mistplay | Сопоставление не требуется |  |
| Meta Ads | fb\_mobile\_purchase, для приложений iOS  <br />или  <br />Adimpression, для приложений Android  <br /><Anchor target="_blank" href="/marketers/ru/docs/meta-ads-in-app-event-mapping#сопоставление-данных-о-доходах-от-рекламы-для-оптимизации-кампании">Руководство по сопоставлению событий в приложении в Meta Ads</Anchor>. | [<Image alt="revenue-mapping-meta2.jpg" src="https://files.readme.io/9ec143cbcb622dec2aa0081812e41c0c7586b3583f4da7e57d71dffcb2d68a79-29375912802193.jpg" width="230px" />](https://files.readme.io/9ec143cbcb622dec2aa0081812e41c0c7586b3583f4da7e57d71dffcb2d68a79-29375912802193.jpg) |
| TikTok for Business – расширенная SRN | ImpressionLevelAdRevenue | [![](https://files.readme.io/8beed93895ac3e9d52049bea06b89388e8f32ca12d404c3461a3dcc493aed26f-24100803659665.png)](https://files.readme.io/8beed93895ac3e9d52049bea06b89388e8f32ca12d404c3461a3dcc493aed26f-24100803659665.png) |
| Aura от Unity | ad\_revenue | [![](https://files.readme.io/17edda24e3de024b1aaf10c1ca4c83da48b024f60aeeeaf9421502e88feb9a80-24100803652369.png)](https://files.readme.io/17edda24e3de024b1aaf10c1ca4c83da48b024f60aeeeaf9421502e88feb9a80-24100803652369.png) |
| Digital Turbine | ad\_revenue | [![](https://files.readme.io/17edda24e3de024b1aaf10c1ca4c83da48b024f60aeeeaf9421502e88feb9a80-24100803652369.png)](https://files.readme.io/17edda24e3de024b1aaf10c1ca4c83da48b024f60aeeeaf9421502e88feb9a80-24100803652369.png) |
| SingleTap от Digital Turbine | ad\_revenue | [![](https://files.readme.io/17edda24e3de024b1aaf10c1ca4c83da48b024f60aeeeaf9421502e88feb9a80-24100803652369.png)](https://files.readme.io/17edda24e3de024b1aaf10c1ca4c83da48b024f60aeeeaf9421502e88feb9a80-24100803652369.png) |
| Persona.ly RTB | ad-revenue | [![](https://files.readme.io/bc924575f7cc5f4c7fafe3683ae51dcbf3240b9bc4cf22f9d6916cef7a9877f9-24658308681873.png)](https://files.readme.io/bc924575f7cc5f4c7fafe3683ae51dcbf3240b9bc4cf22f9d6916cef7a9877f9-24658308681873.png) |
| Bigo | ad\_watch | [![](https://files.readme.io/cd3015a60f623ac1d7c563c2b541dfe487006b7babf9b51050f209b70c4a41a4-24658241206929.png)](https://files.readme.io/cd3015a60f623ac1d7c563c2b541dfe487006b7babf9b51050f209b70c4a41a4-24658241206929.png) |
| Appier | Сопоставление не требуется |  |
| Bidease | Сопоставление не требуется |  |
| MAF | Сопоставление не требуется |  |

5. Выберите для события вариант отправки **для пользователя из**:
   * **Только этот партнер**: Отправляйте постбэки только в том случае, если событие атрибутировано этому партнеру, то есть пользователь, выполнивший его, пришел от этого партнера.
   * **Все медиаисточники, включая органический трафик**: Отправляйте постбэки для событий, атрибутированных любому партнеру, а также для органических событий, то есть если пользователь, выполнивший его, пришел из любого медиаисточника. **Примечание**: Если выбран параметр «Все медиа-источники, включая органический», постбэки для других партнёров не содержат данных атрибуции.
6. Нажмите **Сохранить интеграцию**.

**Список партнёров-посредников, которые могут отправлять события о рекламной выручке на уровне показов в рекламные сети:**

* Applovin Max
* Google AdMob
* Appodeal
* Chartboost
* Fyber
* Tapdaq
* Topon
* Unity
* Посредник Unity LevelPlay (ранее ironSource)
* Admost
* Tradplusad
* Яндекс
* Пользовательский посредник

</Accordion>

## Дополнительные сведения

<div id="list-of-ua-ad-networks-that-can-receive-ua-signals-and-postbacks" />

<Accordion title="Список рекламных сетей, которые могут принимать сигналы и постбэки UA">

В следующей таблице перечислены рекламные сети, которые могут получать сигналы о доходах от рекламы UA и постбэки от сетей-посредников.

<table><colgroup><col/><col/><col/></colgroup><thead><tr><th rowspan="2">Рекламная сеть (партнёр)</th><th colspan="2">Поддерживает</th></tr><tr><th>UA-сигналы</th><th>Постбэки</th></tr></thead><tbody><tr><td>RZR (ранее Aarki)</td><td>-</td><td><span>✓</span></td></tr><tr><td>AdAction</td><td><span>✓</span></td><td>-</td></tr><tr><td>Adaction3</td><td>-</td><td><span>✓</span></td></tr><tr><td>Adamobi</td><td><span>✓</span></td><td>-</td></tr><tr><td>Adikteev (Trademob)</td><td><span>✓</span></td><td>-</td></tr><tr><td>Adjoe</td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td>Adonco</td><td><span>✓</span></td><td>-</td></tr><tr><td>Adshow</td><td><span>✓</span></td><td>-</td></tr><tr><td>Almedia GmbH</td><td>-</td><td><span>✓</span></td></tr><tr><td>Appgrowth</td><td>-</td><td><span>✓</span></td></tr><tr><td>Appier</td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td>Apprainbow</td><td><span>✓</span></td><td>-</td></tr><tr><td>Aura от Unity</td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td>Avow OEM</td><td> </td><td><span>✓</span></td></tr><tr><td>ayeT-Studios</td><td>-</td><td><span>✓</span></td></tr><tr><td>Betop</td><td><span>✓</span></td><td>-</td></tr><tr><td>Bidswave</td><td><span>✓</span></td><td>-</td></tr><tr><td>Bidease</td><td>-</td><td><span>✓</span></td></tr><tr><td>Bigo</td><td>-</td><td><span>✓</span></td></tr><tr><td>Brandscale</td><td><span>✓</span></td><td>-</td></tr><tr><td>Buzzvil</td><td>-</td><td><span>✓</span></td></tr><tr><td>Chameleostudios</td><td><span>✓</span></td><td>-</td></tr><tr><td>Chartboost</td><td><span>✓</span></td><td>-</td></tr><tr><td>Churney</td><td>-</td><td><span>✓</span></td></tr><tr><td>Datawave</td><td><span>✓</span></td><td>-</td></tr><tr><td>Digital Turbine</td><td>-</td><td><span>✓</span></td></tr><tr><td>DLab</td><td><span>✓</span></td><td>-</td></tr><tr><td>Ecomonline</td><td><span>✓</span></td><td>-</td></tr><tr><td>Etusdigital</td><td><span>✓</span></td><td>-</td></tr><tr><td>Exmox</td><td>-</td><td><span>✓</span></td></tr><tr><td>Fluent</td><td><span>✓</span></td><td>-</td></tr><tr><td>Foregon</td><td><span>✓</span></td><td>-</td></tr><tr><td>GNA Company</td><td><span>✓</span></td><td>-</td></tr><tr><td>Google реклама</td><td> </td><td><span>✓</span></td></tr><tr><td>Greedygame</td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td>Happimobi</td><td><span>✓</span></td><td>-</td></tr><tr><td>Гибридные</td><td><span>✓</span></td><td>-</td></tr><tr><td>Inflecto</td><td><span>✓</span></td><td>-</td></tr><tr><td>Irismedia</td><td><span>✓</span></td><td>-</td></tr><tr><td>Kashkick</td><td>-</td><td><span>✓</span></td></tr><tr><td>Kwai ads</td><td>-</td><td><span>✓</span></td></tr><tr><td>Lacuna</td><td>-</td><td><span>✓</span></td></tr><tr><td>Lambadapp</td><td><span>✓</span></td><td>-</td></tr><tr><td>Leadidadmonster</td><td><span>✓</span></td><td>-</td></tr><tr><td>Lifestreet</td><td><span>✓</span></td><td>-</td></tr><tr><td>Liftoff</td><td><span>✓</span></td><td>-</td></tr><tr><td>MAF</td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td>Melodong</td><td><span>✓</span></td><td>-</td></tr><tr><td>Meta Ads</td><td><span>-</span></td><td><span>✓</span></td></tr><tr><td>Miniclip</td><td>-</td><td><span>✓</span></td></tr><tr><td>Mintegral</td><td>-</td><td><span>✓</span></td></tr><tr><td>Mistplay</td><td><span>-</span></td><td><span>✓</span></td></tr><tr><td>Mobrand</td><td><span>✓</span></td><td>-</td></tr><tr><td>Moloco</td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td>Motive</td><td><span>✓</span></td><td>-</td></tr><tr><td>Mpnd</td><td><span>✓</span></td><td>-</td></tr><tr><td>Msla</td><td><span>✓</span></td><td>-</td></tr><tr><td>Muvmobile</td><td><span>✓</span></td><td>-</td></tr><tr><td>NewsBreak</td><td>-</td><td><span>✓</span></td></tr><tr><td>Nexamob</td><td><span>✓</span></td><td>-</td></tr><tr><td>Nftdroper</td><td><span>✓</span></td><td>-</td></tr><tr><td>Nsofmedia</td><td><span>✓</span></td><td>-</td></tr><tr><td>Performadlive</td><td><span>✓</span></td><td>-</td></tr><tr><td>Persona.ly RTB</td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td>Pitatroas</td><td><span>✓</span></td><td>-</td></tr><tr><td>Playgap</td><td>-</td><td><span>✓</span></td></tr><tr><td>Rebornads</td><td><span>✓</span></td><td>-</td></tr><tr><td>Remerge</td><td><span>✓</span></td><td>-</td></tr><tr><td>RTBhouse</td><td><span>✓</span></td><td>-</td></tr><tr><td>Runfuns</td><td><span>✓</span></td><td>-</td></tr><tr><td>SayGames LTD</td><td>-</td><td><span>✓</span></td></tr><tr><td>Scmobi</td><td><span>✓</span></td><td>-</td></tr><tr><td>Shalltry</td><td><span>✓</span></td><td>-</td></tr><tr><td>Shareit</td><td><span>✓</span></td><td>-</td></tr><tr><td>SingleTap от Digital Turbine</td><td>-</td><td><span>✓</span></td></tr><tr><td>Smadex</td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td>Surgex</td><td>-</td><td><span>✓</span></td></tr><tr><td>Tapjoy</td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td>Targetmedia</td><td><span>✓</span></td><td>-</td></tr><tr><td>TaurusX</td><td>-</td><td><span>✓</span></td></tr><tr><td>Thepurpleline</td><td><span>✓</span></td><td>-</td></tr><tr><td>TikTok для бизнеса</td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td>Trade Desk</td><td> </td><td><span>✓</span></td></tr><tr><td>Transsion</td><td>-</td><td><span>✓</span></td></tr><tr><td>Truemoney</td><td><span>✓</span></td><td>-</td></tr><tr><td>Tyrads</td><td>-</td><td><span>✓</span></td></tr><tr><td>Unity Ads</td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td>Unity CTV</td><td><span>✓</span></td><td><span>✓</span></td></tr><tr><td>Vivo Global </td><td> </td><td><span>✓</span></td></tr><tr><td>Voodoo</td><td>-</td><td><span>✓</span></td></tr><tr><td>Vungle</td><td><span>✓</span></td><td>-</td></tr><tr><td>VYBS</td><td>-</td><td><span>✓</span></td></tr><tr><td>Яндекс</td><td><span>✓</span></td><td>-</td></tr><tr><td>Yeahmobi</td><td><span>✓</span></td><td>-</td></tr><tr><td>YouAppi</td><td>-</td><td><span>✓</span></td></tr><tr><td>Xiaomi Global</td><td>-</td><td><span>✓</span></td></tr><tr><td>YSO Сеть</td><td>-</td><td><span>✓</span></td></tr><tr><td>Z2A Digital</td><td><span>✓</span></td><td>-</td></tr><tr><td>Zoyo</td><td><span>✓</span></td><td>-</td></tr></tbody></table>

</Accordion>

<div id="traits-and-limitations" />

<Accordion title="Характеристики и ограничения">

| Специфика | Описание |
| --- | --- |
| Типы конверсий | Сигналы UA и постбэки рекламной выручки поддерживают данные по всем типам конверсий: установки, повторные атрибуции, повторные вовлечения и переустановки. |
| Разрешения на постбэки для агентства | Агентства не могут настраивать постбэки по доходам от рекламы |

</Accordion>

<div data-zendesk-anchors="about-sharing-ad-revenue-data-with-ua-partners=%D0%BE-%D1%81%D0%BE%D0%B2%D0%BC%D0%B5%D1%81%D1%82%D0%BD%D0%BE%D0%BC-%D0%B8%D1%81%D0%BF%D0%BE%D0%BB%D1%8C%D0%B7%D0%BE%D0%B2%D0%B0%D0%BD%D0%B8%D0%B8-%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D1%85-%D0%BE-%D0%B4%D0%BE%D1%85%D0%BE%D0%B4%D0%B0%D1%85-%D0%BE%D1%82-%D1%80%D0%B5%D0%BA%D0%BB%D0%B0%D0%BC%D1%8B-%D1%81-%D0%BF%D0%B0%D1%80%D1%82%D0%BD%D1%91%D1%80%D0%B0%D0%BC%D0%B8 h_01HV6CW4SAF23TT5XZF1SGPVQH=%D0%BE-%D1%81%D0%BE%D0%B2%D0%BC%D0%B5%D1%81%D1%82%D0%BD%D0%BE%D0%BC-%D0%B8%D1%81%D0%BF%D0%BE%D0%BB%D1%8C%D0%B7%D0%BE%D0%B2%D0%B0%D0%BD%D0%B8%D0%B8-%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D1%85-%D0%BE-%D0%B4%D0%BE%D1%85%D0%BE%D0%B4%D0%B0%D1%85-%D0%BE%D1%82-%D1%80%D0%B5%D0%BA%D0%BB%D0%B0%D0%BC%D1%8B-%D1%81-%D0%BF%D0%B0%D1%80%D1%82%D0%BD%D1%91%D1%80%D0%B0%D0%BC%D0%B8 procedures=%D0%BF%D1%80%D0%BE%D1%86%D0%B5%D0%B4%D1%83%D1%80%D1%8B h_01HVEEMGMEWDKAXVNHR8C0AHPQ=%D0%BF%D1%80%D0%BE%D1%86%D0%B5%D0%B4%D1%83%D1%80%D1%8B 01H8V10BKM7MMM63JHGCF2DYMC=ua-signals-for-ad-networks 01H8V10BKMED8J73G22CFVH6GJ=ad-revenue-event-postbacks-for-ad-networks h_01HFAAC1J9KQ6ZNSCRSRKE9GA3=%D0%B2%D0%B0%D0%B6%D0%BD%D0%BE additional-information=%D0%B4%D0%BE%D0%BF%D0%BE%D0%BB%D0%BD%D0%B8%D1%82%D0%B5%D0%BB%D1%8C%D0%BD%D1%8B%D0%B5-%D1%81%D0%B2%D0%B5%D0%B4%D0%B5%D0%BD%D0%B8%D1%8F h_01HVE6AREZBPH751WFW70Q7X66=%D0%B4%D0%BE%D0%BF%D0%BE%D0%BB%D0%BD%D0%B8%D1%82%D0%B5%D0%BB%D1%8C%D0%BD%D1%8B%D0%B5-%D1%81%D0%B2%D0%B5%D0%B4%D0%B5%D0%BD%D0%B8%D1%8F h_01HVE6AREZBCAJPVYSF43JWNJZ=list-of-ua-ad-networks-that-can-receive-ua-signals-and-postbacks h_01HTM0KJA8TB44TSV5N2151N4N=traits-and-limitations" />
