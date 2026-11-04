---
title: Атрибуция предварительной загрузки при помощи Google Play Auto Install
metadata:
  keywords:
    - Advertisers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-alina-koifman
    - Marketers
    - Mobile Attribution
  created_at: '2021-07-25T11:31:06Z'
  edited_at: '2026-08-18T00:10:26Z'
  id: 4404557237649
  locale: ru
  section: Attribution scenarios
  section_id: 6551328497041
  url: https://support.appsflyer.com/hc/ru/articles/4404557237649
---
> **Краткий обзор.** AppsFlyer использует функцию Google Play Auto Install (PAI) для атрибуции установок кампаниям предварительной загрузки, в рамках которых маркетологи заключают контракты с операторами мобильной связи и партнерами по обнаружению приложений для предварительной загрузки их приложений в момент первого включения устройства пользователем. **Примечание:** Этот метод атрибуции отличается от <Anchor target="_blank" href="/marketers/ru/docs/appsflyer-factory-preinstall-using-manifest-android">атрибуции предварительной установки APK</Anchor>.

<div id="pai-preload-attribution" />

## Атрибуция предварительной загрузки PAI

В кампаниях предварительной загрузки производители оригинальных устройств (OEM), операторы мобильной связи и партнеры по обнаружению приложений предварительно загружают приложения на устройства, которые скачиваются при первой активации устройства.

Кампании предварительной загрузки позволяют рекламодателям охватить потенциально большую аудиторию без проведения онлайн-кампаний.

Google Play Auto Install (PAI) (1 из 3 методов атрибуции предварительной загрузки) предоставляет маркетологам точный и сохраняющий конфиденциальность механизм для оценки эффективности кампаний предварительной загрузки. Этот метод обеспечивает маркетологам детерминированные результаты атрибуции и одновременно гарантирует сохранение конфиденциальности пользователей, поскольку атрибуция осуществляется посредством сопоставления реферера с реферером Google Play, сгенерированным независимо от идентификаторов устройства и пользователя.

AppsFlyer отдает наивысший приоритет атрибуции предварительной загрузки. Это означает, что если до того, как пользователь впервые откроет приложение, он вовлекался в другие кампании, атрибуция все равно присваивается кампании предварительной загрузки. Взаимодействия с другими кампаниями считаются дополнительными источниками рекламы.

<div id="note" />

> 📘 **Примечание:**
>
> Настройка Preload Equal Attribution Priority не применяется к Google PAI.

<div id="flow" />

### Сценарий

1. Новое устройство активируется в первый раз, и на него автоматически устанавливаются предварительно заданные приложения из Google Play в соответствии с правилами, установленными партнером по предварительной загрузке.
2. Пользователь впервые запускает предварительно загруженное приложение.
3. AppsFlyer SDK запрашивает API реферера Google Play.
4. AppsFlyer выполняет атрибуцию на основе полученных данных.

![PAI-attribution-flow_en-us.png](https://files.readme.io/c7f02a0a6637e9c73e9a39f97e71d5d37d8d2712b458735cd87b4b245ad0fccb-small-4404791877649.png)

<div id="data-availability" />

### Доступность данных

Данные об эффективности предварительной загрузки Google Play Auto Install (PAI) доступны здесь:

* Обзорный дэшборд и сводные отчеты, агрегированные на уровне партнера по предварительной загрузке (медиа-источника) и кампании.
* Отчеты по необработанным данным

Необработанные данные включают в себя следующие поля:

* Media\_source = идентификатор партнера
* Match\_type = preload\_pai
* Campaign\_name = кампания предварительной загрузки `<preloadpartner ID>`

<div id="set-up-google-play-auto-install-pai-preload-attribution" />

### Настройка атрибуции предварительной загрузки при помощи Google Play Auto Install (PAI)

**Чтобы настроить атрибуцию предварительной загрузки PAI:**

1. В AppsFlyer в боковом меню выберите **Сотрудничество** > **Активные интеграции**.
2. Выберите партнера по предварительной загрузке.
3. Активируйте **Атрибуцию предварительной загрузки**.
4. Установите **длительность окна предварительной загрузки**.

   <div id="note-1" />

   > 📘 **Примечание:**
   >
   > Google хранит данные о реферере в течение 90 дней. Установите окно атрибуции PAI на 90 дней или меньше. Хотя в интерфейсе можно указать до 180 дней, данные за период более 90 дней недоступны в Google.

5. Нажмите **Сохранить интеграцию**.
6. Сообщите партнеру по предварительной загрузке, что вы готовы атрибутировать его кампании.

<div id="partners-supporting-google-play-auto-install-pai-preload-campaigns" />

### Партнеры, поддерживающие кампании предварительной загрузки Google Play Auto Install (PAI)

<table><thead><tr><th rowspan="2">Партнер</th><th rowspan="2">pid</th></tr></thead><tbody><tr><td><p>Xiaomi</p></td><td><span>xiaomipai_int</span></td></tr><tr><td><p>Transsion</p></td><td><span>shalltrypai_int</span></td></tr><tr><td><p>Oppo</p></td><td><span>oppopaipreinstall_int</span></td></tr><tr><td><p>Vivo</p></td><td><span>vivootapreload_int</span></td></tr><tr><td><p>TCL</p></td><td><span>tclpai_int</span></td></tr><tr><td><p>Motorola</p></td><td><span>motorola_int</span></td></tr><tr><td><p>MITV</p></td><td><span>mitvpai_int</span></td></tr><tr><td><p>ZTE</p></td><td><span>ztepai_int</span></td></tr><tr><td><p>Lenovotab</p></td><td><span>lenovotabpai4p_int</span></td></tr><tr><td><p>KDDI Pre-Install</p></td><td><span>kddipai_int</span></td></tr></tbody></table>

<div id="note-2" />

> 📘 **Примечание:**
>
> Агентства не могут активировать кампании предварительной загрузки для своих клиентов.

<div id="postbacks-for-preload-partners" />

## Постбэки для партнеров по предварительной загрузке

В рамках интеграции с AppsFlyer партнеры по предварительной загрузке определяют содержимое и конечные точки постбэков, отправляемых им AppsFlyer.

Включенные в постбэк макросы содержат данные, касающиеся пользователя. Поддерживаемые макросы перечислены в следующей таблице:

* **Источник**: Указывает, откуда получены данные:
  * **SDK**: SDK AppsFlyer, встроенный в приложение или межсерверный API.
  * **AppsFlyer**: После обработки AppsFlyer.

| Макрос постбэка для партнеров по предварительной загрузке (имя параметра) | Источник | Описание |
| --- | --- | --- |
| app\_name (название приложения) | SDK (пакет средств разработки ПО) | Имя приложения, заданное рекламодателем |
| код\_страны | AppsFlyer: | Код страны согласно ISO 3166 (alpha-2) Пример: US, CN. |
| время\_установки | SDK (пакет средств разработки ПО) | Метка времени установки |
| язык | SDK (пакет средств разработки ПО) | Язык (местный), сообщается устройством, устанавливается ОС устройства. |
| app\_id (идентификатор приложения) | SDK (пакет средств разработки ПО) | Уникальный идентификатор приложения в AppsFlyer |
| версия\_приложения | SDK (пакет средств разработки ПО) | Версия приложения, установленная разработчиком приложения в коде приложения |
| тип\_устройства | SDK (пакет средств разработки ПО) | Коммерческое название модели устройства. Пример: SM-GM284 или iPhone7 |
| os\_version | SDK (пакет средств разработки ПО) | Версия операционной системы устройства |

<div id="postback-example" />

#### Пример постбэка

```http
http://YourCompanyDomain.com?pid=(preinstall_partner)&app_name=(app-name)&app_id=(app-id)&install_time=(install-unix-ts)
```

<div data-zendesk-anchors="pai-preload-attribution=%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D1%8F-%D0%BF%D1%80%D0%B5%D0%B4%D0%B2%D0%B0%D1%80%D0%B8%D1%82%D0%B5%D0%BB%D1%8C%D0%BD%D0%BE%D0%B9-%D0%B7%D0%B0%D0%B3%D1%80%D1%83%D0%B7%D0%BA%D0%B8-pai h_01HEJG4FHSGJDZ77Y281F7SG4R=%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D1%8F-%D0%BF%D1%80%D0%B5%D0%B4%D0%B2%D0%B0%D1%80%D0%B8%D1%82%D0%B5%D0%BB%D1%8C%D0%BD%D0%BE%D0%B9-%D0%B7%D0%B0%D0%B3%D1%80%D1%83%D0%B7%D0%BA%D0%B8-pai h_01K8XBQ3YKJ8KBMPMAAMBZP25E=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%87%D0%B0%D0%BD%D0%B8%D0%B5 pai-preload-attribution-flow=%D1%81%D1%86%D0%B5%D0%BD%D0%B0%D1%80%D0%B8%D0%B9 h_01HEJG4FHSF8X1TEMMNJBYP71Z=%D1%81%D1%86%D0%B5%D0%BD%D0%B0%D1%80%D0%B8%D0%B9 campaign-performance-data-availability=%D0%B4%D0%BE%D1%81%D1%82%D1%83%D0%BF%D0%BD%D0%BE%D1%81%D1%82%D1%8C-%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D1%85 h_01HEJG4FHSCMPJM5TRNSPNDHVN=%D0%B4%D0%BE%D1%81%D1%82%D1%83%D0%BF%D0%BD%D0%BE%D1%81%D1%82%D1%8C-%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D1%85 run-preload-referrer-campaigns=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8-%D0%BF%D1%80%D0%B5%D0%B4%D0%B2%D0%B0%D1%80%D0%B8%D1%82%D0%B5%D0%BB%D1%8C%D0%BD%D0%BE%D0%B9-%D0%B7%D0%B0%D0%B3%D1%80%D1%83%D0%B7%D0%BA%D0%B8-%D0%BF%D1%80%D0%B8-%D0%BF%D0%BE%D0%BC%D0%BE%D1%89%D0%B8-google-play-auto-install-pai h_01HEJG4FHS7E5JZT2BBYG2BNEK=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8-%D0%BF%D1%80%D0%B5%D0%B4%D0%B2%D0%B0%D1%80%D0%B8%D1%82%D0%B5%D0%BB%D1%8C%D0%BD%D0%BE%D0%B9-%D0%B7%D0%B0%D0%B3%D1%80%D1%83%D0%B7%D0%BA%D0%B8-%D0%BF%D1%80%D0%B8-%D0%BF%D0%BE%D0%BC%D0%BE%D1%89%D0%B8-google-play-auto-install-pai h_01K8XBJ9EJ38ST3KAFF879ZQ1H=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%87%D0%B0%D0%BD%D0%B8%D0%B5-1 partners-supporting-preload-referrer-campaigns=%D0%BF%D0%B0%D1%80%D1%82%D0%BD%D0%B5%D1%80%D1%8B-%D0%BF%D0%BE%D0%B4%D0%B4%D0%B5%D1%80%D0%B6%D0%B8%D0%B2%D0%B0%D1%8E%D1%89%D0%B8%D0%B5-%D0%BA%D0%B0%D0%BC%D0%BF%D0%B0%D0%BD%D0%B8%D0%B8-%D0%BF%D1%80%D0%B5%D0%B4%D0%B2%D0%B0%D1%80%D0%B8%D1%82%D0%B5%D0%BB%D1%8C%D0%BD%D0%BE%D0%B9-%D0%B7%D0%B0%D0%B3%D1%80%D1%83%D0%B7%D0%BA%D0%B8-google-play-auto-install-pai h_01HEJG4FHSNEGR7R9VCSDT9TSZ=%D0%BF%D0%B0%D1%80%D1%82%D0%BD%D0%B5%D1%80%D1%8B-%D0%BF%D0%BE%D0%B4%D0%B4%D0%B5%D1%80%D0%B6%D0%B8%D0%B2%D0%B0%D1%8E%D1%89%D0%B8%D0%B5-%D0%BA%D0%B0%D0%BC%D0%BF%D0%B0%D0%BD%D0%B8%D0%B8-%D0%BF%D1%80%D0%B5%D0%B4%D0%B2%D0%B0%D1%80%D0%B8%D1%82%D0%B5%D0%BB%D1%8C%D0%BD%D0%BE%D0%B9-%D0%B7%D0%B0%D0%B3%D1%80%D1%83%D0%B7%D0%BA%D0%B8-google-play-auto-install-pai h_01K8XBVZJGG59K3XJ8R346X9FH=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%87%D0%B0%D0%BD%D0%B8%D0%B5-2 postbacks-for-preload-partners=%D0%BF%D0%BE%D1%81%D1%82%D0%B1%D1%8D%D0%BA%D0%B8-%D0%B4%D0%BB%D1%8F-%D0%BF%D0%B0%D1%80%D1%82%D0%BD%D0%B5%D1%80%D0%BE%D0%B2-%D0%BF%D0%BE-%D0%BF%D1%80%D0%B5%D0%B4%D0%B2%D0%B0%D1%80%D0%B8%D1%82%D0%B5%D0%BB%D1%8C%D0%BD%D0%BE%D0%B9-%D0%B7%D0%B0%D0%B3%D1%80%D1%83%D0%B7%D0%BA%D0%B5 h_01HEJG4FHSKD7DY6W7W65YBMGN=%D0%BF%D0%BE%D1%81%D1%82%D0%B1%D1%8D%D0%BA%D0%B8-%D0%B4%D0%BB%D1%8F-%D0%BF%D0%B0%D1%80%D1%82%D0%BD%D0%B5%D1%80%D0%BE%D0%B2-%D0%BF%D0%BE-%D0%BF%D1%80%D0%B5%D0%B4%D0%B2%D0%B0%D1%80%D0%B8%D1%82%D0%B5%D0%BB%D1%8C%D0%BD%D0%BE%D0%B9-%D0%B7%D0%B0%D0%B3%D1%80%D1%83%D0%B7%D0%BA%D0%B5 preload-postback-example=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%80-%D0%BF%D0%BE%D1%81%D1%82%D0%B1%D1%8D%D0%BA%D0%B0 h_01HEJG4FHSBFB456Z752HFC8KN=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%80-%D0%BF%D0%BE%D1%81%D1%82%D0%B1%D1%8D%D0%BA%D0%B0" />
