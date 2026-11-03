---
title: Настройка кампании на Reddit
metadata:
  keywords:
    - integrated partner
    - Advertisers
    - Agencies
    - reddit
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
    - Agencies
  created_at: '2020-07-09T09:50:46Z'
  edited_at: '2026-09-11T00:24:46Z'
  id: 360011016138
  locale: ru
  section: Ad network configuration guides (R-Z)
  section_id: 6552025468305
  url: https://support.appsflyer.com/hc/ru/articles/360011016138
---
> **Краткий обзор.** Рекламная сеть Reddit, интегрированный партнер AppsFlyer, имеет 430 миллионов активных пользователей в месяц, которых невозможно найти больше нигде.

## Настройка Reddit

**Необходимые условия.** Перед настройкой интеграции необходимо <Anchor target="_blank" href="/marketers/ru/docs/partner-integrations#contact-details">связаться с партнером</Anchor> и открыть у него аккаунт.

**Чтобы активировать интеграцию:**

1. **Чтобы активировать:** В AppsFlyer в боковом меню выберите**Сотрудничество**> **Маркетплейс партнеров**.  
   **Чтобы изменить**: В боковом меню AppsFlyer выберите **Сотрудничество** > **Активные интеграции**.
2. Выберите соответствующее приложение.
3. На вкладке **Интеграция** выберите приложение для интеграции и нажмите **Активировать партнера**.
4. При **первом посещении** здесь нужно включить переключатель ***Активировать партнера***, чтобы настроить параметры интеграции. Этот переключатель **обязательно** должен быть включен все время, пока вы работаете с партнером.  
    Дополнительная информация по активации партнеров: нажмите <Anchor target="_blank" href="/marketers/ru/docs/partner-activation-deactivation">здесь</Anchor>.
5. Завершите настройку, используя соответствующие вкладки, как описано ниже. Подробное описание заголовка окна настройки параметров партнера см. <Anchor target="_blank" href="/marketers/ru/docs/set-up-an-integrated-partner#about-the-integrated-partner-page">здесь</Anchor>.

<div id="integration-tab" />

<Accordion title="Вкладка «Интеграция»">

На вкладке ***Интеграция*** есть несколько разделов:

#### Активация партнеров

Чтобы включить конфигурацию, <Anchor target="_blank" href="/marketers/ru/docs/partner-activation-deactivation#активировать-интеграцию-партнера">активируйте партнера</Anchor>.

#### Расширенные настройки конфиденциальности

**Только для приложений iOS. Когда <Anchor target="_blank" href="/marketers/ru/docs/set-up-an-integrated-partner#b-advanced-privacy">Расширенная конфиденциальность (для iOS 14.5+ и выше)</Anchor>** включена, вы можете контролировать, какие данные передаются в Reddit через постбэки и отчеты.

#### Идентификатор транзакции

**Только для приложений iOS. Когда переключатель <Anchor target="_blank" href="/marketers/ru/docs/skadnetwork-skan-solution-guide#sending-postbacks-to-integrated-partners">Предоставлять идентификатор транзакции SKAN</Anchor>** включен, вы разрешаете AppsFlyer передавать в Reddit идентификаторы транзакций для постбэков SKAdNetwork. Таким образом, Reddit может расшифровать ваши значения конверсии SKAdNetwork.

#### Общие настройки

**Активируйте атрибуцию по просмотрам**

Включите, если вы хотите атрибутировать установки по просмотрам с Reddit. На вкладке [***Ссылка атрибуции***](/docs/reddit-campaign-configuration#attribution-link-tab) имеется слайдер окна атрибуции по просмотрам.

**Обмен данными расширенного сопоставления**

Включите этот параметр, чтобы передавать в Reddit поля расширенного сопоставления, такие как хешированный email, хешированный номер телефона, хешированное имя и хешированная фамилия, если эти поля включены в информацию о событии, отправляемую в AppsFlyer. Более подробную информацию см. здесь: <Anchor target="_blank" href="/marketers/ru/docs/advanced-matching-data-sharing">Обмен данными с расширенным сопоставлением</Anchor>.

#### Постбэки по умолчанию

Отправляйте автоматические постбэки в Reddit после установок пользователей. Выберите, следует ли отправлять постбэки для установок, атрибутированных к:

* Только Reddit
* Все источники, включая органические

#### Настройки внутренних событий приложения

В этом разделе вы можете настроить отправляемые в Reddit постбэки о внутренних событиях в приложении.

**Для настройки постбэков по внутренним событиям приложения:**

1. Активируйте ***Постбэки о внутренних событиях***.
2. Чтобы добавить в список событие, определенное в SDK, нажмите ***Добавить событие***.
3. Заполните следующие данные:

| Имя параметра | Описание |
| --- | --- |
| **Имя события в SDK** | Имя события, полученное AppsFlyer из SDK или из межсерверного события.  <br />**Совет**: Если в списке нет нужного вам события, активируйте его на устройстве с неорганической установкой, и повторите поиск. |
| **Идентификатор события партнера** | Уникальное название или идентификатор каждого события, как определено на стороне Reddit. Выберите наиболее подходящее предопределенное событие для события SDK:<ul><li>rdt\_install</li><li>rdt\_signup</li><li>rdt\_app\_launch</li><li>rdt\_search</li><li>rdt\_view\_content</li><li>rdt\_add\_payment\_info</li><li>rdt\_add\_to\_cart</li><li>rdt\_purchase</li><li>rdt\_completed\_tutorial</li><li>rdt\_level\_achieved</li><li>rdt\_spend\_credits</li><li>rdt\_ad\_click</li><li>rdt\_ad\_view</li><li>rdt\_add\_to\_wishlist</li><li>rdt\_unlock\_achievement</li><li>rdt\_login</li><li>rdt\_rate</li><li>rdt\_checkout</li><li>rdt\_start\_trial</li><li>rdt\_subscribe</li><li>rdt\_onboard\_started</li><li>rdt\_onboard\_completed</li><li>rdt\_first\_time\_purchase</li></ul> |
| **Вариант отправки** | Выберите, следует ли отправлять события от:<ul><li>Только Reddit</li><li>Все источники, включая органические</li></ul> |
| **Отправить данные о событии** | <ul><li>**Нет значений и нет дохода:** отправляется только само событие без значения.</li><li>**Значения, нет дохода:** отправляются все параметры, кроме значения дохода.</li><li>**Значения и доход**: отправляются все параметры события, включая значение дохода (если оно есть в событии).</li></ul> |

4. Нажмите кнопку ***Сохранить***.

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Вкладка «Ссылка атрибуции»">

Сгенерируйте и сохраните ссылки атрибуции и отправьте их партнеру, чтобы атрибутировать определенные кампании, группы объявлений и отдельные объявления — как для кампаний по привлечению пользователей, так и для ретаргетинговых кампаний. Вы можете использовать либо ссылку для конкретной платформы, либо OneLink.  
<Anchor target="_blank" href="/marketers/ru/docs/about-link-structure-and-parameters">Подробнее о структуре и параметрах ссылок атрибуции</Anchor>.

**Чтобы создать ссылку атрибуции,** следуйте <Anchor target="_blank" href="/marketers/ru/docs/set-up-an-integrated-partner#attribution-link-tab">этой инструкции</Anchor>.

</Accordion>

<div id="cost-tab" />

<Accordion title="Вкладка «Стоимость»">

AppsFlyer получает информацию о затратах через API. Подробную информацию о поддерживаемых параметрах, метриках и функциях см. в <Anchor target="_blank" href="/marketers/ru/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api">таблице интеграции затрат рекламной сети</Anchor>. **Примечание**: Для получения данных о затратах требуется подписка ROI360.

**Чтобы включить API данных о затратах**:

* Следуйте <Anchor target="_blank" href="/marketers/ru/docs/set-up-roi360-cost-api-to-measure-cost-data#enable-cost-api">этим инструкциям по интеграции</Anchor>.

<Anchor target="_blank" href="/marketers/ru/docs/set-up-roi360-cost-api-to-measure-cost-data#статус-api-затрат">Просмотрите статус вашего API данных о затратах</Anchor> и время, когда AppsFlyer получил соответствующие данные о затратах в последний раз, либо на дэшборде статуса интеграции затрат (и доходов от рекламы), либо на дэшборде отдельной рекламной сети. .

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Вкладка «Доходы от рекламы»">

Reddit не поддерживает данные о доходах от рекламы.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Вкладка Permissions (Разрешения)">

В этой вкладке вы можете выбрать разрешения, которые хотите предоставить Reddit. Обратите внимание, что, даже если атрибуция для Reddit отключена, вкладка разрешений остается активной и вы можете предоставить Reddit разрешение на управление.

#### Разрешения для рекламной сети

В этой вкладке вы можете выбрать разрешения, которые хотите предоставить Reddit. Обратите внимание, что, даже если атрибуция для Reddit отключена, вкладка разрешений остается активной и вы можете предоставить Reddit разрешение на управление.

Эти переключатели позволяют предоставить рекламной сети право самостоятельно выполнять настройки для вашего приложения:

* <span id="01EDKYCTJGZCQ05BQ5JXR6457Y"></span>***<span id="01EDKYCTJHNYT3SRD6Q40YJKR1"></span>Разрешение настраивать интеграцию***: разрешить партнеру управлять настройками на вкладке интеграции (за исключением постбэков по внутренним событиям приложений).
* <span id="01EDKYCTJHVW0E6TD5ARMFEQQC"></span>***Разрешить настройку постбэков по внутренним событиям приложения***: разрешить партнеру настраивать постбэки по внутренним событиям и отображать эти настройки на вкладке интеграции.
* <span id="01EDKYCTJH6C06V91M50CXNSZS"></span>***Разрешить доступ к своему отчету об удержании***: доступ предоставляется только к собственным данным партнера.
* <span id="01EDKYCTJHY2JXJHQRQM6S1T7H"></span>***Разрешить доступ к своим сводным данным о лояльных пользователях***: доступ предоставляется только к собственным данным партнера.
* <span id="01EDKYCTJHF1W3FPJCSSEKJ4GZ"></span>***Разрешить доступ к агрегированным данным о внутренних событиях приложения***: партнер получает доступ только к собственным данным о внутренних событиях.
* <span id="01EDKYCTJHVN8E1QPY3BSMC3WD"></span>***Разрешить доступ к агрегированным данным о доходе***: партнер получает доступ к данным только по атрибутированным ему доходам.
* <span id="01EDKYCTJHX0T89JNPJKY71WVW"></span>***Разрешить импорт расходов:*** разрешите партнеру отправлять данные о расходах на рекламу в виде файлов только для этого приложения.
* <span id="01EDKYCTJHWKWYJS7ZFCJ8558V"></span>***Разрешить доступ к дэшборду Protect360***: партнер получает доступ только к собственным данным Protect360, при условии что эта функция активирована для рекламодателя.

См. дополнительные сведения о предоставлении <Anchor target="_blank" href="/marketers/ru/docs/set-up-an-integrated-partner#permissions-tab">разрешений рекламной сети</Anchor>.

</Accordion>

## Ограничения сырых данных

Начиная с 30 августа 2025 г.:

Следующие ограничения применяются к атрибуции по просмотрам:

* Медиаисточник (reddit\_int) – доступен.
* Для времени атрибуции касания указывается только дата (дд/мм/гггг).
* Сведения о кампании: указывается как ограничено
* Клики и показы: не включаются в отчёты о сырых данных.

Следующие ограничения применяются к атрибуции по кликам:

* Медиаисточник (reddit\_int) – доступен.
* Для времени атрибуции касания указывается только дата (дд/мм/гггг).
* Детали кампании – доступны.
* Клики и показы: не включаются в отчёты о сырых данных.

**Напоминание:** Данные, полученные о кампании на Reddit, подпадают под действие <Anchor target="_blank" href="https://protect.checkpoint.com/v2/___https:/business.reddithelp.com/s/article/Reddit-Business-Tool-Terms___.YzJ1OnJlZGRpdDpjOmc6OGFlZGI3Y2U5MDg3ZTgxNzYxYzdjMzEzYzgwZjI3ZDI6NjowMDg5Ojg1MmViZDg4YWY2ZTg4NThjMDE2NjhkYTk2ZjZkYmZlYWI1NGY3MGEwNDk0MmE0ODQ0NTI3ZDM0ZWYwOWVlMmI6cDpUOk4#:%7E:text=These%20Reddit%20Business%20Tool%20Terms,advertising%20purposes%20or%20to%20otherwise">Reddit Business Tool Terms</Anchor> и включают, среди прочих ограничений, запрет на использование данных Reddit для создания профилей любых пользователей.

<div data-zendesk-anchors="setting-up-reddit=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-reddit 01EDKYCH117BTY81G0Z2NF181F=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-reddit 01EDKYCH11YM04HDJTAWP4XHWH=integration-tab activate-partners=%D0%B0%D0%BA%D1%82%D0%B8%D0%B2%D0%B0%D1%86%D0%B8%D1%8F-%D0%BF%D0%B0%D1%80%D1%82%D0%BD%D0%B5%D1%80%D0%BE%D0%B2 01EDKYCH11E2X1VSSG2HKKP6VS=%D0%B0%D0%BA%D1%82%D0%B8%D0%B2%D0%B0%D1%86%D0%B8%D1%8F-%D0%BF%D0%B0%D1%80%D1%82%D0%BD%D0%B5%D1%80%D0%BE%D0%B2 advanced-privacy=%D1%80%D0%B0%D1%81%D1%88%D0%B8%D1%80%D0%B5%D0%BD%D0%BD%D1%8B%D0%B5-%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B8-%D0%BA%D0%BE%D0%BD%D1%84%D0%B8%D0%B4%D0%B5%D0%BD%D1%86%D0%B8%D0%B0%D0%BB%D1%8C%D0%BD%D0%BE%D1%81%D1%82%D0%B8 h_01HJRZF42CYME3EZ37470339CF=%D1%80%D0%B0%D1%81%D1%88%D0%B8%D1%80%D0%B5%D0%BD%D0%BD%D1%8B%D0%B5-%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B8-%D0%BA%D0%BE%D0%BD%D1%84%D0%B8%D0%B4%D0%B5%D0%BD%D1%86%D0%B8%D0%B0%D0%BB%D1%8C%D0%BD%D0%BE%D1%81%D1%82%D0%B8 transaction-id=%D0%B8%D0%B4%D0%B5%D0%BD%D1%82%D0%B8%D1%84%D0%B8%D0%BA%D0%B0%D1%82%D0%BE%D1%80-%D1%82%D1%80%D0%B0%D0%BD%D0%B7%D0%B0%D0%BA%D1%86%D0%B8%D0%B8 h_01HJRZF42CN7VT8SKNX5E638R0=%D0%B8%D0%B4%D0%B5%D0%BD%D1%82%D0%B8%D1%84%D0%B8%D0%BA%D0%B0%D1%82%D0%BE%D1%80-%D1%82%D1%80%D0%B0%D0%BD%D0%B7%D0%B0%D0%BA%D1%86%D0%B8%D0%B8 general-settings=%D0%BE%D0%B1%D1%89%D0%B8%D0%B5-%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B8 01EDKYCH11WFJ09XBND6RQT0XA=%D0%BE%D0%B1%D1%89%D0%B8%D0%B5-%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B8 default-postbacks=%D0%BF%D0%BE%D1%81%D1%82%D0%B1%D1%8D%D0%BA%D0%B8-%D0%BF%D0%BE-%D1%83%D0%BC%D0%BE%D0%BB%D1%87%D0%B0%D0%BD%D0%B8%D1%8E 01EDKYCH11KZT2BN64AGETTMD6=%D0%BF%D0%BE%D1%81%D1%82%D0%B1%D1%8D%D0%BA%D0%B8-%D0%BF%D0%BE-%D1%83%D0%BC%D0%BE%D0%BB%D1%87%D0%B0%D0%BD%D0%B8%D1%8E inapp-events-settings=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B8-%D0%B2%D0%BD%D1%83%D1%82%D1%80%D0%B5%D0%BD%D0%BD%D0%B8%D1%85-%D1%81%D0%BE%D0%B1%D1%8B%D1%82%D0%B8%D0%B9-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D1%8F 01EDKYCH11QAYSV2GMYD4R6DJJ=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B8-%D0%B2%D0%BD%D1%83%D1%82%D1%80%D0%B5%D0%BD%D0%BD%D0%B8%D1%85-%D1%81%D0%BE%D0%B1%D1%8B%D1%82%D0%B8%D0%B9-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D1%8F h_01HJRZF42DHDDHPCE4NYA7QKV2=attribution-link-tab h_01HJRZF42DYG18DTKSV4G8NHV4=cost-tab 01EDKYCH124QTAFK6VQ3ARHCTM=ad-revenue-tab 01EDKYCH12RY4P6DY3QSWG1A18=permissions-tab ad-network-permissions=%D1%80%D0%B0%D0%B7%D1%80%D0%B5%D1%88%D0%B5%D0%BD%D0%B8%D1%8F-%D0%B4%D0%BB%D1%8F-%D1%80%D0%B5%D0%BA%D0%BB%D0%B0%D0%BC%D0%BD%D0%BE%D0%B9-%D1%81%D0%B5%D1%82%D0%B8 01EDKYCH12FXE1WASY5YQF80CV=%D1%80%D0%B0%D0%B7%D1%80%D0%B5%D1%88%D0%B5%D0%BD%D0%B8%D1%8F-%D0%B4%D0%BB%D1%8F-%D1%80%D0%B5%D0%BA%D0%BB%D0%B0%D0%BC%D0%BD%D0%BE%D0%B9-%D1%81%D0%B5%D1%82%D0%B8 raw-data-restrictions=%D0%BE%D0%B3%D1%80%D0%B0%D0%BD%D0%B8%D1%87%D0%B5%D0%BD%D0%B8%D1%8F-%D1%81%D1%8B%D1%80%D1%8B%D1%85-%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D1%85 01JAQ0TCR54Q03RQWPNT5PJGPN=%D0%BE%D0%B3%D1%80%D0%B0%D0%BD%D0%B8%D1%87%D0%B5%D0%BD%D0%B8%D1%8F-%D1%81%D1%8B%D1%80%D1%8B%D1%85-%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D1%85" />
