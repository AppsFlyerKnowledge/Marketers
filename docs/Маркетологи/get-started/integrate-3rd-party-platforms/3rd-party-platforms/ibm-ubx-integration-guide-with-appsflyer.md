---
title: Руководство по интеграции IBM UBX с AppsFlyer
metadata:
  keywords:
    - Analytics
    - IBM
    - UBX
    - integrated partner
    - Advertisers
    - Ad Networks
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
    - Ad Networks
  created_at: '2016-07-03T09:06:26Z'
  edited_at: '2026-08-28T00:10:37Z'
  id: 210093266
  locale: ru
  section: 3rd-party platforms
  section_id: 6551199962257
  url: https://support.appsflyer.com/hc/ru/articles/210093266
---
> **Кратко:** IBM UBX (универсальный обмен поведенческими данными), интегрированный партнер AppsFlyer, — это функция IBM Marketing Cloud и других решений IBM Commerce, которая позволяет маркетологам контролировать интеграцию всех данных о клиентах с помощью удобной консоли. Эта возможность открытого обмена данными обеспечивает контекстное представление о покупательском поведении клиентов по всем каналам, устройствам и взаимодействиям, чтобы маркетологи могли быстро разрабатывать и запускать эффективные кампании, мгновенно предоставляя значимый опыт и повышая ROI.

<div id="important" />

> 🚧 **Важно!**
>
> <Anchor target="_blank" href="/marketers/ru/docs/about-raw-data-identifier-restrictions#ограничения-медиа-источников">Некоторые медиа-источники</Anchor> ограничивают передачу данных третьим лицам. Поэтому постбэки для ограниченных событий не будут отправляться этому партнёру, независимо от настроек отправки постбэков.

<div id="setting-up-ibm" />

## Настройка IBM

**Необходимые условия.** Перед настройкой интеграции необходимо <Anchor target="_blank" href="/marketers/ru/docs/partner-integrations#contact-details">связаться с партнером</Anchor> и открыть у него аккаунт.

**Чтобы активировать интеграцию:**

1. **Чтобы активировать:** В AppsFlyer в боковом меню выберите**Сотрудничество** > **Маркетплейс партнеров**.  
   **Чтобы изменить**: В боковом меню AppsFlyer выберите **Сотрудничество** > **Активные интеграции**.
2. Выберите соответствующее приложение.
3. Нажмите **Настроить интеграцию**.
4. При **первом заходе** сюда включите **Активацию партнера**, чтобы настройка параметров на вкладке интеграции стала возможной. Переключатель должен оставаться во включенном положении все время, которое вы работаете с Medialyzer. Подробнее об <Anchor target="_blank" href="/marketers/ru/docs/partner-activation-deactivation">активации партнеров</Anchor>.
5. Завершите настройку, используя соответствующие вкладки, как описано ниже.

В окне настройки IBM используется только вкладка **Интеграция**.

Подробное описание заголовка окна настройки параметров партнера см. <Anchor target="_blank" href="/marketers/ru/docs/set-up-an-integrated-partner#about-the-integrated-partner-page">здесь</Anchor>.

<div id="integration-tab" />

<Accordion title="Вкладка «Интеграция»">

На вкладке «Интеграция» есть несколько разделов, которые описаны ниже.

<div id="activate-partner" />

### Активация партнера

При **первом посещении** вам нужно будет включить переключатель ниже. При **первом посещении** вам нужно будет включить переключатель ***Активировать партнера***, чтобы включить настройку параметров на вкладке интеграции. Этот переключатель должен быть активирован все время, пока вы работаете с этим партнером.  
Дополнительная информация по активации партнеров доступна <Anchor target="_blank" href="/marketers/ru/docs/partner-activation-deactivation">здесь</Anchor>.

<div id="general-settings" />

### Общие настройки

**Ключ авторизации**

IBM подключается к AppsFlyer с помощью уникального ключа авторизации. Если у вас ещё нет этого ключа, для продолжения интеграции вы должны получить его в IBM или выполнить следующие шаги.

<Image align="center" alt="IBM_msc_new_2.png" src="https://files.readme.io/d6dddd7232ba7ecba2ed5bd944f98669902689fc0953afc558fbc6586be8b5cf-360002219269.png" />

<div id="obtaining-the-authorization-key" />

### Получение ключа авторизации

Первый шаг при настройке универсальной конечной точки паблишера событий AppsFlyer — создать пустую конечную точку в интерфейсе UBX.

Для этого войдите в свою учетную запись UBX и перейдите на вкладку **Endpoints**

<Image align="center" alt="" src="https://files.readme.io/8c0833f890c5e2ed2df1c0a8904e1764b341a82f3381c0a1a3fb6effe4f76673-205128323.png" />

Затем нажмите **Зарегистрировать новую конечную точку**.

<Image align="center" alt="" src="https://files.readme.io/23c8d4a88eda765fce1b42f9eb2e74b1325160e6d0602dc65a8ab05488598b9e-205053206.png" />

Затем выберите **AppsFlyer** и нажмите**Далее**.

<Image align="center" alt="IBM_1.png" src="https://files.readme.io/f30b7b27d2ffecf3e562cbe651367306a581d1881325dd141c950b39efac016c-115002600286.png" />

Создайте информативное название для эксперимента, затем нажмите **Далее**

<Image align="center" alt="Pasted_image_at_2017_02_23_02_48_PM.png" src="https://files.readme.io/11a94c4d9f4c9282c230e4cf69f31e0d39f4eb88196313b3cfc103a5bbaba9a4-115002600326.png" />

Кликните на 3 точки справа в только что созданной конечной точкеAppsFlyer и кликните **детали конечной точки**.

<Image align="center" alt="IBM_3.png" src="https://files.readme.io/70edd2e14c6c344188dcc65b65b3a8d92081401dd34909f5a4e0dd6bd137b8df-115002599203.png" />

Скопируйте ключ аутентификации:

<Image align="center" alt="IBM_Endpoint_details.png" src="https://files.readme.io/3706f4dd665d8d2a26de9013b03c0e6575d051f2fa5500033e172312a63f09ea-115002601006.png" />

<div id="default-postbacks" />

### Постбэки по умолчанию

AppsFlyer может отправлять автоматические постбэки об установках пользователей IBM. В этом разделе можно определить отправку этих постбэков.

<Image align="center" alt="Swrve_msc_new_4.png" src="https://files.readme.io/0144ced7a8f0e6eec2a4847971c1d058efde9bdb0efbef961c6451a4c7e81ccf-18274450980753.png" />

Выберите **События, атрибутированные любому партнеру или органическому трафику**, чтобы отправлять в IBM постбэки по всем пользователям, скачавшим приложение, или выберите **Выкл.**.

Нажмите кнопку **Сохранить.**

<div id="in-app-event-settings" />

### Настройки внутренних событий приложения

<Image align="center" alt="" src="https://files.readme.io/c945ee3c04f49076e54c9966389506aea441406e01daa49d737a86da9f5bd2bc-360002219429.png" />

В этом разделе вы можете сопоставить свои события AppsFlyer с IBM с помощью постбэков.

1. Снова введите ключ авторизации.
2. Установите переключатель "Постбэки внутренних событий приложения" в положение "Включено"
3. В поле «Вариант отправки» выберите значение, которое будет использоваться для всех событий, определенных в SDK.  
   **- Только события, атрибутированные этому партнеру**: партнер будет получать сведения о событиях **только** тех пользователей, которые ему атрибутированы.  
    **- События, атрибутированные любому партнеру или органические**: партнер будет получать сведения о событиях всех пользователей, которые есть в вашей базе.
4. Чтобы добавить в список событие, определенное в SDK, нажмите **Добавить событие**.
5. Введите следующие параметры:

| Имя параметра | Description(Описание) |
| --- | --- |
| **Имя события в SDK** | Имя события, полученное AppsFlyer либо из SDK, интегрированного в ваше приложение, либо из межсерверных событий.  <br />**Совет**. Если в списке нет нужного вам события, убедитесь, что оно активировано на устройстве с неорганической установкой, и повторите поиск. |
| **Идентификатор события партнера** | Уникальное имя или идентификатор ID каждого события, определенные на стороне IBM.  <br />Получите соответствующий идентификатор события в IBM и введите его в текстовое поле. |
| **Отправка данных о доходе** | **Если флажок не установлен** — AppsFlyer отправляет партнеру все параметры насыщенного события в приложении, кроме параметра дохода, который содержится в параметре **af\_revenue**.  <br />**Флажок установлен** — AppsFlyer отправляет все параметры, включая значение дохода (если оно есть в событии). |

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Вкладка «Ссылки атрибуции»">

Ссылки атрибуции недоступны для IBM.

</Accordion>

<div id="cost-tab" />

<Accordion title="Вкладка «Стоимость»">

Данные о расходах не поддерживаются при интеграции с этим партнером.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Вкладка «Доходы от рекламы»">

Доход от рекламы не поддерживается при интеграции с этим партнером.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Вкладка Permissions (Разрешения)">

Разрешения недоступны для IBM.

</Accordion>

<div data-zendesk-anchors="h_01H9FK8FS5T9KZ30N87B76QVT5=%D0%B2%D0%B0%D0%B6%D0%BD%D0%BE setting-up-ibm=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-ibm h_01H9FK8FS5QPJYSA7JVY4QNB3S=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-ibm h_01H9FK8FS5J30GZS634NMG62BQ=integration-tab activate-partner=%D0%B0%D0%BA%D1%82%D0%B8%D0%B2%D0%B0%D1%86%D0%B8%D1%8F-%D0%BF%D0%B0%D1%80%D1%82%D0%BD%D0%B5%D1%80%D0%B0 h_01H9FK8FS5SYTBF8A3QX4QGESM=%D0%B0%D0%BA%D1%82%D0%B8%D0%B2%D0%B0%D1%86%D0%B8%D1%8F-%D0%BF%D0%B0%D1%80%D1%82%D0%BD%D0%B5%D1%80%D0%B0 general-settings=%D0%BE%D0%B1%D1%89%D0%B8%D0%B5-%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B8 h_01H9FK8FS5YXRCN83RHG6QBAKS=%D0%BE%D0%B1%D1%89%D0%B8%D0%B5-%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B8 obtaining-the-authorization-key=%D0%BF%D0%BE%D0%BB%D1%83%D1%87%D0%B5%D0%BD%D0%B8%D0%B5-%D0%BA%D0%BB%D1%8E%D1%87%D0%B0-%D0%B0%D0%B2%D1%82%D0%BE%D1%80%D0%B8%D0%B7%D0%B0%D1%86%D0%B8%D0%B8 h_01H9FK8FS5ZVGX5RK7K72SH6K6=%D0%BF%D0%BE%D0%BB%D1%83%D1%87%D0%B5%D0%BD%D0%B8%D0%B5-%D0%BA%D0%BB%D1%8E%D1%87%D0%B0-%D0%B0%D0%B2%D1%82%D0%BE%D1%80%D0%B8%D0%B7%D0%B0%D1%86%D0%B8%D0%B8 default-postbacks=%D0%BF%D0%BE%D1%81%D1%82%D0%B1%D1%8D%D0%BA%D0%B8-%D0%BF%D0%BE-%D1%83%D0%BC%D0%BE%D0%BB%D1%87%D0%B0%D0%BD%D0%B8%D1%8E h_01H9FK8FS5SVF4YQC8AG2V6N8D=%D0%BF%D0%BE%D1%81%D1%82%D0%B1%D1%8D%D0%BA%D0%B8-%D0%BF%D0%BE-%D1%83%D0%BC%D0%BE%D0%BB%D1%87%D0%B0%D0%BD%D0%B8%D1%8E inapp-event-settings=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B8-%D0%B2%D0%BD%D1%83%D1%82%D1%80%D0%B5%D0%BD%D0%BD%D0%B8%D1%85-%D1%81%D0%BE%D0%B1%D1%8B%D1%82%D0%B8%D0%B9-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D1%8F h_01H9FK8FS54N196VQ0XCXJ763Q=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B8-%D0%B2%D0%BD%D1%83%D1%82%D1%80%D0%B5%D0%BD%D0%BD%D0%B8%D1%85-%D1%81%D0%BE%D0%B1%D1%8B%D1%82%D0%B8%D0%B9-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D1%8F h_01H9FK8FS50TB7TZH9JKEH3Y7H=attribution-link-tab h_01H9FK8FS54P1MYVXGR46TXN7D=cost-tab h_01H9FK8FS600SP0MS1T6PTBMH4=ad-revenue-tab h_01H9FK8FS65VMZK13D2BE5DT09=permissions-tab" />
