---
title: '[бета] Взаимодействие SKAN с Amazon'
metadata:
  keywords:
    - Marketers
    - Beta feature
    - SKAdNetwork (SKAN)
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - SKAdNetwork (SKAN)
  created_at: '2024-08-15T09:36:46Z'
  edited_at: '2026-09-10T00:31:10Z'
  id: 27548444974353
  locale: ru
  section: SKAN interoperation
  section_id: 6552115163153
  url: https://support.appsflyer.com/hc/ru/articles/27548444974353
---
<span class="af-tag af-tag--beta-feature">Beta feature</span>

> **Краткий обзор:** Взаимодействие со SKAN позволяет Amazon обмениваться постбэками SKAN с AppsFlyer, а AppsFlyer — передавать Amazon сопоставление измерения значений конверсии.

> 📘 **Примечание**
>
> Чтобы принять участие в этом закрытом бета-тестировании, сообщите об этом своему представителю Amazon.

## Взаимодействие SKAN: AppsFlyer &lt;-> Amazon

Если вы работаете с несколькими партнерами — рекламными сетями, рекомендуется настроить все в AppsFlyer. Таким образом, метрики эффективности SKAN, дополненные другими показателями, такими как стоимость, доступны на платформе AppsFlyer.

### Объем взаимодействия SKAN с Amazon

Взаимодействие позволяет AppsFlyer и Amazon обмениваться сопоставлением значений конверсии SKAN (настроенным в AppsFlyer). Это позволяет обеим сторонам предоставлять метрики эффективности. См. <Anchor target="_blank" href="/marketers/ru/docs/skan-integrated-partners-list">список полей обогащения</Anchor>, поддерживаемых Amazon.

### Рекомендации по рекламе установки приложений в Amazon DSP

Программа Amazon DSP iOS Alpha позволяет пользователям AppsFlyer запускать кампании по загрузке приложений iOS, используя платформу Amazon и Apple SKAdNetwork для измерения эффективности с соблюдением конфиденциальности. Эта программа предназначена для рекламодателей, которые хотят эффективно привлекать и вовлекать пользователей приложений iOS. Для настройки:

**Требования**

* Убедитесь, что <Anchor target="_blank" href="/marketers/ru/docs/sdk-integration-overview">SDK AppsFlyer</Anchor> обновлен.
* Настройте SKAdNetwork в AppsFlyer
  * Интегрируйте SDK AppsFlyer в ваше приложение.
  * Настройте схему значений конверсии SKAdNetwork в Conversion Studio AppsFlyer.
  * Убедитесь, что SKAdNetwork включена и схема конверсии настроена правильно.
* Примите Условия и положения Amazon для рекламодателей

  * **Клиенты Managed Service:** ваш представитель Amazon поможет вам принять соглашение Advertiser Audience Agreement.
  * **Клиенты самообслуживания:**
    * Войдите в свой аккаунт Amazon Ads.
    * Перейдите в Amazon DSP > Менеджер кампаний >Менеджер событий > вкладку Конверсии.
    * Если появится запрос, примите условия, чтобы продолжить.

  **Шаги ознакомления**
* Зарегистрируйте свое приложение в Amazon Ads
  * **Клиенты Managed Service:** сообщите своему представителю Amazon идентификатор iTunes App и название вашего приложения.
  * **Клиенты самообслуживания:**
    * Войдите в advertising.amazon.com.
    * Перейдите в Amazon DSP > Campaign Manager > Events Manager > вкладка Apps.
    * Нажмите **Add App**, выберите **AppsFlyer** в качестве партнера по мобильным измерениям и укажите следующие сведения:
      * Платформа: iOS
      * Название приложения: название вашего приложения
      * iTunes App ID: указан в URL-адресе приложения в магазине приложений Apple (например, 123456789).
  * Включите **измерение SKAdNetwork** и сохраните.
  * Проверьте вкладку Conversions, чтобы убедиться, что Amazon распознает вашу схему конверсий. Если какие-либо события отсутствуют, обратитесь к вашему представителю Amazon.

**Следующие шаги**

* Клиенты с управляемым обслуживанием: уведомите своего представителя Amazon после завершения онбординга.
* Клиенты самообслуживания: следуйте руководству Amazon по настройке кампании, чтобы начать создавать кампании

**Ключевые функции программы**

* Тип кампании: кампании по привлечению пользователей для приложений iOS.
* Платформа измерения: SKAdNetwork 2.0–4.0.
* Рекламная среда: реклама в приложении на ресурсах Amazon и в отдельных сторонних рекламных биржах.
* Отчетность: инсайты по кампаниям в реальном времени через AppsFlyer.

### Активация взаимодействия

Взаимодействие осуществляется с помощью настроек на дэшбордах AppsFlyer и Amazon. Функциональная совместимость и изменения в самом приложении не требуются.

**Чтобы активировать взаимодействие AppsFlyer SKAN с** **Amazon:**

| Шаг | Действие | Подробности |
| --- | --- | --- |
| <span id="1"></span>1 | Минимальные требования для Приложения | <ul><li>Интегрируйте новейший SDK AppsFlyer в свое приложение.</li></ul> |
| <span id="2"></span>2 | Обзор настроек SKAN | Настройте и включите решение <Anchor target="_blank" href="/marketers/ru/docs/skadnetwork-skan-solution-guide">SKAN от AppsFlyer.</Anchor><br /><br />**Чтобы просмотреть настройки SKAN**:<ol><li>В AppsFlyer перейдите в **Настройки** > **SKAN Conversion Studio**.</li><li>Откройте опции (⋮) и убедитесь, что **измерение SKAN** включено.<br />![skan-settings.png](https://files.readme.io/5a5b9b8b8a809336055340a14e49dacc16c5c0e95cda62c6dfb2ca9a11618d71-27548444964497.png)</li><li>Выберите предпочтительный режим измерения.<br />Узнайте больше о <Anchor target="_blank" href="/marketers/ru/docs/skan-conversion-studio">SKAN Conversion Studio</Anchor>.</li><li>Запишите точные названия событий. Они потребуются вам на следующем шаге.</li></ol> |
| <span id="3"></span>3 | Сопоставление событий в приложении | Просмотрите и, при необходимости, внесите изменения в сопоставления событий в приложении Amazon. **Чтобы Amazon мог получить схему и завершить интеграцию, необходимо сопоставить с Amazon хотя бы одно событие в приложении**.<br /><br />**Чтобы просмотреть и настроить сопоставления событий в приложении**:<ol><li>В AppsFlyer перейдите в раздел **Настройки** > **Активные интеграции**.</li><li>Найдите и выберите **Amazon Ads**.</li><li>В разделе **In-app events postback** (Постбэки внутренних событий):<ol><li>[Обязательно] Включите **постбэки внутренних событий приложения**, если они еще не включены.</li><li>Убедитесь, что события в приложении, которые вы настроили в <Anchor target="_blank" href="/marketers/ru/docs/skan-conversion-studio">SKAN conversion studio</Anchor>, сопоставлены с названиями событий Amazon или с событиями в вашей <Anchor target="_blank" href="/marketers/ru/docs/skan-cv-decode-map-your-cv-to-events">пользовательской карте конверсии</Anchor>.<br />**Примечание:** сопоставьте `af_skad_revenue` с названием события Amazon `OFF_AMAZON_purchases`</li></ol></li><li>Нажмите **Сохранить интеграцию**.</li></ol> |

> 📄 **См. также**
>
> * <Anchor target="_blank" href="/marketers/ru/docs/skadnetwork-skan-solution-guide">Руководство по решению AppsFlyer SKAN</Anchor>

<div data-zendesk-anchors="01JEBXBFKGN066TY78WKH0VEXC=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%87%D0%B0%D0%BD%D0%B8%D0%B5 skan-interoperability-appsflyer-tiktok=%D0%B2%D0%B7%D0%B0%D0%B8%D0%BC%D0%BE%D0%B4%D0%B5%D0%B9%D1%81%D1%82%D0%B2%D0%B8%D0%B5-skan-appsflyer---amazon h_01HDNYZ0CT1MGCRSSP3MXTJK5V=%D0%B2%D0%B7%D0%B0%D0%B8%D0%BC%D0%BE%D0%B4%D0%B5%D0%B9%D1%81%D1%82%D0%B2%D0%B8%D0%B5-skan-appsflyer---amazon scope-of-skan-interoperability-with-tiktok=%D0%BE%D0%B1%D1%8A%D0%B5%D0%BC-%D0%B2%D0%B7%D0%B0%D0%B8%D0%BC%D0%BE%D0%B4%D0%B5%D0%B9%D1%81%D1%82%D0%B2%D0%B8%D1%8F-skan-%D1%81-amazon h_01HDNYZ0CT5NZHDHDBDSCFG911=%D0%BE%D0%B1%D1%8A%D0%B5%D0%BC-%D0%B2%D0%B7%D0%B0%D0%B8%D0%BC%D0%BE%D0%B4%D0%B5%D0%B9%D1%81%D1%82%D0%B2%D0%B8%D1%8F-skan-%D1%81-amazon tiktok-for-business-guidance=%D1%80%D0%B5%D0%BA%D0%BE%D0%BC%D0%B5%D0%BD%D0%B4%D0%B0%D1%86%D0%B8%D0%B8-%D0%BF%D0%BE-%D1%80%D0%B5%D0%BA%D0%BB%D0%B0%D0%BC%D0%B5-%D1%83%D1%81%D1%82%D0%B0%D0%BD%D0%BE%D0%B2%D0%BA%D0%B8-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D0%B9-%D0%B2-amazon-dsp 01HR1TPFCSXRGYC610AR7KMTS5=%D1%80%D0%B5%D0%BA%D0%BE%D0%BC%D0%B5%D0%BD%D0%B4%D0%B0%D1%86%D0%B8%D0%B8-%D0%BF%D0%BE-%D1%80%D0%B5%D0%BA%D0%BB%D0%B0%D0%BC%D0%B5-%D1%83%D1%81%D1%82%D0%B0%D0%BD%D0%BE%D0%B2%D0%BA%D0%B8-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D0%B9-%D0%B2-amazon-dsp enabling-interoperation=%D0%B0%D0%BA%D1%82%D0%B8%D0%B2%D0%B0%D1%86%D0%B8%D1%8F-%D0%B2%D0%B7%D0%B0%D0%B8%D0%BC%D0%BE%D0%B4%D0%B5%D0%B9%D1%81%D1%82%D0%B2%D0%B8%D1%8F h_01HDNYZ0CTJGY3GPC9F907NEPT=%D0%B0%D0%BA%D1%82%D0%B8%D0%B2%D0%B0%D1%86%D0%B8%D1%8F-%D0%B2%D0%B7%D0%B0%D0%B8%D0%BC%D0%BE%D0%B4%D0%B5%D0%B9%D1%81%D1%82%D0%B2%D0%B8%D1%8F h_01HDNZ1BW5EBP0JCX84MTYPQ6K=%D1%81%D0%BC-%D1%82%D0%B0%D0%BA%D0%B6%D0%B5" />
