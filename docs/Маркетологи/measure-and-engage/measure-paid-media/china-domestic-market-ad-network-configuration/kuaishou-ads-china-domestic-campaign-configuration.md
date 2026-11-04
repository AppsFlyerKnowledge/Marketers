---
title: Настройка кампании Kuaishou Ads (внутренний рынок Китая)
metadata:
  keywords:
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2019-06-05T06:07:11Z'
  edited_at: '2026-09-17T00:26:18Z'
  id: 360001748437
  locale: ru
  section: China domestic market ad network configuration
  section_id: 6552066355601
  url: https://support.appsflyer.com/hc/ru/articles/360001748437
---
> **Кратко:** Kuaishou — интегрированный партнер AppsFlyer по рекламной сети.

<div id="setting-up-kuaishou" />

## Настройка Kuaishou

**Необходимые условия.** Перед настройкой интеграции необходимо <Anchor target="_blank" href="/marketers/ru/docs/partner-integrations#contact-details">связаться с партнером</Anchor> и открыть у него аккаунт.

**Чтобы активировать интеграцию:**

1. **Чтобы активировать:** В AppsFlyer в боковом меню выберите**Сотрудничество**> **Маркетплейс партнеров**.  
   **Чтобы изменить**: В боковом меню AppsFlyer выберите **Сотрудничество** > **Активные интеграции**.
2. Выберите соответствующее приложение.
3. На вкладке **Интеграция** выберите приложение для интеграции и нажмите **Активировать партнера**.
4. При **первом посещении** здесь нужно включить переключатель ***Активировать партнера***, чтобы настроить параметры интеграции.   
   **Важно:** переключатель **должен оставаться включенным (активным), пока вы работаете с партнером**. <Anchor target="_blank" href="/marketers/ru/docs/partner-activation-deactivation">Узнать больше</Anchor>
5. Завершите настройку, используя соответствующие вкладки, как описано ниже.

В окне настроек Kuaishou есть 3 активные вкладки: «Интеграция», «Ссылка атрибуции» и «Разрешения». Чтобы ознакомиться с настройками этих вкладок, нажмите на названия пунктов ниже.

<div id="integration-tab" />

<Accordion title="Вкладка «Интеграция»">

<div id="activate-partner" />

### Activate Partner (Активировать партнера)

При **первом посещении** вам нужно будет включить переключатель ниже. При **первом посещении** вам нужно будет включить переключатель ***Активировать партнера***, чтобы включить настройку параметров на вкладке интеграции. Кнопка ДОЛЖНА оставаться в положении «Включено», пока вы работаете с этим партнером.  
Дополнительная информация по активации партнеров доступна <Anchor target="_blank" href="/marketers/ru/docs/partner-activation-deactivation">здесь</Anchor>.

<div id="default-postbacks" />

### Постбэки по умолчанию

![mceclip2.png](https://files.readme.io/dbb58af826e66fda7a501fdb23bf5f0ded2415e295969472e04c958d3190310e-50899821656721.png)

<div id="in-app-events-settings" />

### In-App Events Settings (Настройки внутренних событий приложения)

В этом разделе можно сопоставить события AppsFlyer с событиями Kuaishou с помощью постбэков.

![mceclip0.png](https://files.readme.io/74a4c9e81ac69f65079f5e214de90dc8725f8aedaf59c7ee4d9a3d947a853a0b-50899821661713.png)

1. Установите переключатель "Постбэки внутренних событий приложения" в положение "Включено"
2. Чтобы добавить в список событие, определенное в SDK, нажмите **Добавить событие**.
3. Введите следующие параметры:

| Имя параметра | Описание |
| --- | --- |
| **Имя события в SDK** | Имя события, полученное AppsFlyer из SDK, интегрированного в приложение, или из межсерверного события.  <br />**Совет**. Если в списке нет нужного вам события, убедитесь, что оно активировано на устройстве с неорганической установкой, и повторите поиск. |
| **Идентификатор события партнера** | Уникальное имя или идентификатор каждого события, определенные на стороне iQIYI Ads.  <br />Получите соответствующий идентификатор события в iQIYI Ads и введите его в текстовое поле. |
| **Отправка данных о доходе** | **Флажок не установлен** — AppsFlyer отправляет партнеру все параметры насыщенного события в приложении, за исключением параметра дохода, который содержится в параметре **af\_revenue**.  <br />**Флажок установлен** — AppsFlyer отправляет все параметры, включая значение дохода (если оно есть в событии). |

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Вкладка «Ссылки атрибуции»">

Формируйте и сохраняйте ссылки атрибуции и отправляйте их партнеру, чтобы атрибутировать определенные кампании, группы объявлений и отдельные объявления — как для кампаний по привлечению пользователей, так и для ретаргетинговых кампаний. Вы можете использовать либо ссылку для конкретной платформы, либо <Anchor target="_blank" href="/marketers/ru/docs/onelink-guide">OneLink</Anchor>.  
<Anchor target="_blank" href="/marketers/ru/docs/about-link-structure-and-parameters">Подробнее о структуре и параметрах ссылок атрибуции</Anchor>.

**Чтобы создать ссылку атрибуции,** следуйте <Anchor target="_blank" href="/marketers/ru/docs/set-up-an-integrated-partner#attribution-link-tab">этой инструкции</Anchor>.

</Accordion>

<div id="cost-tab" />

<Accordion title="Вкладка «Стоимость»">

Данные о расходах не поддерживаются при интеграции с этим партнёром.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Вкладка «Доходы от рекламы»">

Доход от рекламы не поддерживается при интеграции с этим партнёром.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Вкладка Permissions (Разрешения)">

На этой вкладке можно выбрать разрешения для Kuaishou в зависимости от того, в каком качестве выступает партнер: как рекламная сеть, как агентство или как оба варианта сразу. Обратите внимание: даже если атрибуция отключена для Kuaishou, вкладка разрешений остается активной, и вы можете предоставить Kuaishou контроль.

![rtb_house-permissions-new.png](https://files.readme.io/645bdfcbb23d0ee5121a6261d5b17ca11a86209bcad2cfd9354e57c8ae281e83-50899852754449.png)

<div id="ad-network-permissions" />

### Полномочия для рекламной сети

Эти переключатели позволяют предоставить рекламной сети право самостоятельно выполнять настройки для вашего приложения:

* ***Разрешить настройку интеграции*** — разрешить партнеру настраивать вкладку интеграции (за исключением постбэков по событиям в приложении)
* ***Разрешить настройку постбэков по внутренним событиям приложения*** — разрешить партнеру настраивать постбэки по внутренним событиям и отображать эти настройки на вкладке интеграции.
* ***Разрешить доступ к своему отчету об удержании*** — доступ предоставляется только к собственным данным партнера.
* ***Разрешить доступ к панели управления Protect360*** — доступ предоставляется только к собственным данным Protect360 этого партнера, при условии что эта функция активирована для рекламодателя.

См. дополнительные сведения о предоставлении <Anchor target="_blank" href="/marketers/ru/docs/set-up-an-integrated-partner#permissions-tab">разрешений рекламной сети</Anchor>.

</Accordion>

<div data-zendesk-anchors="setting-up-kuaishou=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-kuaishou h_01HKW6VK4HFZYAY2XC7Y6QGXD4=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-kuaishou h_01HKW6VK4HMKVSRH9PXH6ASDGJ=integration-tab activate-partner=activate-partner-%D0%B0%D0%BA%D1%82%D0%B8%D0%B2%D0%B8%D1%80%D0%BE%D0%B2%D0%B0%D1%82%D1%8C-%D0%BF%D0%B0%D1%80%D1%82%D0%BD%D0%B5%D1%80%D0%B0 h_01HKW6VK4HWBBP9W3BMTC8KQBJ=activate-partner-%D0%B0%D0%BA%D1%82%D0%B8%D0%B2%D0%B8%D1%80%D0%BE%D0%B2%D0%B0%D1%82%D1%8C-%D0%BF%D0%B0%D1%80%D1%82%D0%BD%D0%B5%D1%80%D0%B0 default-postbacks=%D0%BF%D0%BE%D1%81%D1%82%D0%B1%D1%8D%D0%BA%D0%B8-%D0%BF%D0%BE-%D1%83%D0%BC%D0%BE%D0%BB%D1%87%D0%B0%D0%BD%D0%B8%D1%8E h_01HKW6VK4H4SQP4Q5QXC683R38=%D0%BF%D0%BE%D1%81%D1%82%D0%B1%D1%8D%D0%BA%D0%B8-%D0%BF%D0%BE-%D1%83%D0%BC%D0%BE%D0%BB%D1%87%D0%B0%D0%BD%D0%B8%D1%8E inapp-events-settings=in-app-events-settings-%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B8-%D0%B2%D0%BD%D1%83%D1%82%D1%80%D0%B5%D0%BD%D0%BD%D0%B8%D1%85-%D1%81%D0%BE%D0%B1%D1%8B%D1%82%D0%B8%D0%B9-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D1%8F h_01HKW6VK4HW50X9Z2WJ5X9RP90=in-app-events-settings-%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B8-%D0%B2%D0%BD%D1%83%D1%82%D1%80%D0%B5%D0%BD%D0%BD%D0%B8%D1%85-%D1%81%D0%BE%D0%B1%D1%8B%D1%82%D0%B8%D0%B9-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D1%8F h_01HKW6VK4HKFCXKQNN0RY16B10=attribution-link-tab h_01HKW6VK4JSK4JFC0XD2JM7JJ6=cost-tab h_01HKW6VK4JSCS6M01R6SF1V9YB=ad-revenue-tab h_01HKW6VK4JEEBKB2G0H3WFRB8W=permissions-tab ad-network-permissions=%D0%BF%D0%BE%D0%BB%D0%BD%D0%BE%D0%BC%D0%BE%D1%87%D0%B8%D1%8F-%D0%B4%D0%BB%D1%8F-%D1%80%D0%B5%D0%BA%D0%BB%D0%B0%D0%BC%D0%BD%D0%BE%D0%B9-%D1%81%D0%B5%D1%82%D0%B8 h_01HKW6VK4JY5YG805PZQ7EG1VM=%D0%BF%D0%BE%D0%BB%D0%BD%D0%BE%D0%BC%D0%BE%D1%87%D0%B8%D1%8F-%D0%B4%D0%BB%D1%8F-%D1%80%D0%B5%D0%BA%D0%BB%D0%B0%D0%BC%D0%BD%D0%BE%D0%B9-%D1%81%D0%B5%D1%82%D0%B8" />
