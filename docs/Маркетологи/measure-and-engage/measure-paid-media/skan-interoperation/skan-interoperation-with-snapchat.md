---
title: Взаимодействие SKAN и Snapchat
metadata:
  keywords:
    - Advertisers
    - Marketers
    - SKAdNetwork (SKAN)
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - SKAdNetwork (SKAN)
  created_at: '2021-02-10T20:20:51Z'
  edited_at: '2026-08-18T00:32:15Z'
  id: 360017604077
  locale: ru
  section: SKAN interoperation
  section_id: 6552115163153
  url: https://support.appsflyer.com/hc/ru/articles/360017604077
---
> Краткий обзор. Взаимодействие со SKAN позволяет Snapchat обмениваться постбэками SKAN с AppsFlyer, а AppsFlyer — передавать в Snapchat сопоставление измерений значений конверсии./strong>

## Взаимодействие SKAN: AppsFlyer &lt;-> Snapchat

Если вы работаете с несколькими партнерами – рекламными сетями, лучше всего настроить интеграцию SKAN в AppsFlyer. В результате метрики эффективности SKAN, дополненные другими метриками, например данными о затратах, будут доступны на платформе AppsFlyer. 

**Возможности взаимодействия SKAN и Snapchat**

Такое взаимодействие позволяет AppsFlyer и Snapchat обмениваться картой значений конверсии SKAN, что позволяет им предоставлять вам метрики эффективности. Если вы включите интеграцию с партнером Snapchat в AppsFlyer, то AppsFlyer предоставит Snapchat события для оптимизации.

**Рекомендации по рекламе в Snapchat с целью установки приложений**

При настройке в Snapchat кампаний по установке приложений для iOS 14 обратите внимание на следующие рекомендации по Snapchat:

*С 18 февраля 2021 года SKAdNetwork доступен в Snapchat Ads Manager для всех рекламодателей. Мы рекомендуем настроить приложения и начать их тестирование, чтобы не прерывать в Snapchat измерения и масштабирования кампаний по привлечению приложений для iOS 14. В будущем SKAdNetwork станет обязательным требованием для доступа в Snapchat к ставкам на основе целей для кампаний iOS.*

*Завершите интеграцию SKAdNetwork на дэшборде AppsFlyer MMP и завершите настройку сопоставления значений конверсии перед запуском групп объявлений SKAdNetwork в Snapchat Ads Manager. Руководство по настройке SKAdNetwork в Snapchat можно найти [здесь](https://businesshelp.snapchat.com/s/article/skadnetwork).*

**Требования к реализации**

Рассмотрите следующие моменты в Snapchat:

* Сконфигурируйте идентификатор [Snap App ID](https://businesshelp.snapchat.com/en-US/a/snap-app-id) для каждого приложения, которое вы рекламируете в Snapchat.
* Подпишитесь на использование рекламных наборов Snapchat для измерения SKAN.
* Для одного приложения вы можете одновременно использовать не более 10 групп объявлений, включенных в атрибуцию SKAN.

### Включение взаимодействия AppsFlyer SKAN и Snapchat

Взаимодействие осуществляется с помощью настроек на дэшбордах AppsFlyer и Snapchat. В самом приложении взаимодействие не требуется. Однако вам необходимо использовать самую последнюю версию SDK AppsFlyer.

<Table>
  <thead>
    <tr>
      <th>
        Шаг
      </th>
      <th>
        Действие
      </th>
      <th>
        Подробности
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        1
      </td>
      <td>
        Требования к приложению
      </td>
      <td>
        * Интегрируйте в приложение самую последнюю версию <Anchor target="_blank" href="/marketers/ru/docs/sdk-integration-overview">SDK</Anchor> AppsFlyer.
      </td>
    </tr>
    <tr>
      <td>
        2
      </td>
      <td>
        Обзор настроек SKAN
      </td>
      <td>
        Настройте и включите решение <Anchor target="_blank" href="/marketers/ru/docs/skadnetwork-skan-solution-guide">SKAN от AppsFlyer.</Anchor>

        **Для просмотра настроек SKAN**:

        1. В AppsFlyer перейдите в раздел **Настройки**  > **SKAN Conversion Studio**.
        2. Откройте дополнительные параметры (⋮) и убедитесь, что **измерение SKAN** включено.  

           ![skan-settings.png](https://files.readme.io/5a5b9b8b8a809336055340a14e49dacc16c5c0e95cda62c6dfb2ca9a11618d71-27548444964497.png)
        3. Выберите предпочтительный режим измерения.  
           Подробнее о <Anchor target="_blank" href="/marketers/ru/docs/skan-conversion-studio">SKAN Conversion Studio</Anchor>.
        4. Запишите точные названия событий. Они потребуются вам на следующем шаге.
      </td>
    </tr>
    <tr>
      <td>
        3
      </td>
      <td>
        Сопоставление внутренних событий приложения
      </td>
      <td>
        Просмотрите и, при необходимости, внесите изменения в сопоставления внутренних событий Snapchat.

        **Чтобы просмотреть и настроить сопоставление внутренних событий приложения**:

        1. В AppsFlyer перейдите в раздел **Настройки** > **Активные интеграции**.
        2. Найдите и выберите **Snapchat**.
        3. На вкладке **Интеграция**: если переключатель **Активировать партнера** не включен, включите его.
        4. Проверьте и, при необходимости, замените идентификатор приложения Snap, отображаемый в AppsFlyer, на идентификатор приложения, который отображается на <Anchor target="_blank" href="https://businesshelp.snapchat.com/s/article/snap-app-id?language=en_US">панели управления Snapchat</Anchor>.
        5. Если **Постбэки по внутренним событиям приложения** еще не активированы, активируйте их.  

           [<Image alt="mceclip0.png" src="https://files.readme.io/9df3455b102ff280e8b0fae4bfc006fa87f8830d74064eb955fc829d06708165-23458868914577.png" width="432px" />](https://files.readme.io/9df3455b102ff280e8b0fae4bfc006fa87f8830d74064eb955fc829d06708165-23458868914577.png)

           Убедитесь, что внутренние события приложения и **имена событий SDK**, заданные вами в измерениях SKAN, сопоставлены с **идентификаторами событий партнера,** т. е. с именами событий Snapchat. Необходимо сопоставить выбранные в данный момент события типа измерения SKAN или события в <Anchor target="_blank" href="/marketers/ru/docs/skan-cv-decode-map-your-cv-to-events">настраиваемой карте конверсий</Anchor>. **Примечание**! Тип измерения по умолчанию — доход.

           #### Руководство по сопоставлению внутренних событий приложения

        | Тип измерения | Требования к сопоставлению |
        | --- | --- |
        | Настраиваемые | Сопоставьте внутренние события приложения, заданные в разделе «Настраиваемые», с соответствующими событиями Snap.<br /><br />Чтобы передавать данные о доходах с помощью постбэков, задайте для параметра Отправка данных о доходе значение **Значения и доход**.<br /><br />![SendValueandRevenue.png](https://files.readme.io/412c60db2b09d80a989b7546a6819aa1b030732e0ce004b323dc09db1015c238-11331054047377.png)<br /><br />*af\_skad\_revenue* используется для общего дохода и сопоставляется с событием дохода Snap.<br /><br />**Примечание**! Можно сопоставить более одного события с событием дохода Snap. |
        | Доход | Сопоставьте af\_skad\_revenue с событием покупки PURCHASE |
        | Конверсия | Сопоставьте события конверсии 1–6 с соответствующими событиями Snapchat. |
        | Вовлеченность | Сопоставьте установленное событие вовлечения с соответствующим событием Snapchat. |

        6. Нажмите **Сохранить интеграцию**.
      </td>
    </tr>
    <tr>
      <td>
        4
      </td>
      <td>
        Разрешите Snapchat делиться постбэками с AppsFlyer
      </td>
      <td>
        1. Перейдите на панель управления Snapchat.
        2. В разделе **Please share postbacks with this MMP** (Поделиться постбэками с этим MMP) выберите AppsFlyer.

           [<Image alt="SnapchatSelectAppsFlyer.png" src="https://files.readme.io/e142c4bf54019e8587722af4c5cf5aa95ca49a76948f66e3fb584b003aaacdd6-360017154717.png" width="268px" />](https://files.readme.io/e142c4bf54019e8587722af4c5cf5aa95ca49a76948f66e3fb584b003aaacdd6-360017154717.png)
        3. Нажмите **Update** (Обновить).
      </td>
    </tr>
  </tbody>
</Table>

## Дополнительные сведения

<div id="discrepancies-guide" />

<Accordion title="Руководство по несоответствиям">

| Расхождения | Подробности |
| --- | --- |
| Фильтры дэшборда | **Причина несоответствия**<ul><li>AppsFlyer: Дэшборд SKAN содержит установки, относящиеся к полученным постбэкам iOS.</li><li>Snapchat: По умолчанию панель управления и отчет Snapchat включают как установки SKAN, так и традиционно атрибутированные установки (IDFA). Отфильтруйте отчет Snapchat, чтобы получить только установки SKAN.</li></ul>**Решение**<br /><br />Настройте фильтры панели управления Snapchat так, чтобы отображались только установки SKAN, как показано на следующем снимке.<br /><br />[![SnapchatFilter.png](https://files.readme.io/6e067557aabe899df48454aaf4b7be7f466da55e41b7cd3c68db802e48df7d07-360019782137.png)](https://files.readme.io/6e067557aabe899df48454aaf4b7be7f466da55e41b7cd3c68db802e48df7d07-360019782137.png) |
| Разница в датах установки | **Причина несоответствия**<br /><br />Между датами установки AppsFlyer и Snapchat могут быть следующие различия:<ul><li>AppsFlyer: Получает дату установки по следующей формуле: Время прибытия постбэка - 24 часа - окно измерения (по умолчанию 24 часа). Таким образом, по умолчанию корректировка составляет 48 часов. Время UTC. <Anchor target="_blank" href="/marketers/ru/docs/about-data-freshness-and-timezone-support#skan">Актуальность данных SKAN</Anchor></li><li>Snapchat: Как правило, в качестве даты установки используется время прибытия постбэка iOS без корректировки.</li></ul>**Решение**<br /><br />Учитывайте вышесказанное при сравнении результатов. |

</Accordion>

> 📄 **См. также**
>
> * <Anchor target="_blank" href="/marketers/ru/docs/skadnetwork-skan-solution-guide">Руководство по решению AppsFlyer SKAN</Anchor>

<div data-zendesk-anchors="skan-interoperability-appsflyer-snapchat=%D0%B2%D0%B7%D0%B0%D0%B8%D0%BC%D0%BE%D0%B4%D0%B5%D0%B9%D1%81%D1%82%D0%B2%D0%B8%D0%B5-skan-appsflyer---snapchat h_01HDNZ3SP97C331D45AP1F8CM7=%D0%B2%D0%B7%D0%B0%D0%B8%D0%BC%D0%BE%D0%B4%D0%B5%D0%B9%D1%81%D1%82%D0%B2%D0%B8%D0%B5-skan-appsflyer---snapchat enabling-appsflyer-skan-interoperation-with-snapchat=%D0%B2%D0%BA%D0%BB%D1%8E%D1%87%D0%B5%D0%BD%D0%B8%D0%B5-%D0%B2%D0%B7%D0%B0%D0%B8%D0%BC%D0%BE%D0%B4%D0%B5%D0%B9%D1%81%D1%82%D0%B2%D0%B8%D1%8F-appsflyer-skan-%D0%B8-snapchat h_01HDNZ3SP9FZ3AXCNG185DJQY1=%D0%B2%D0%BA%D0%BB%D1%8E%D1%87%D0%B5%D0%BD%D0%B8%D0%B5-%D0%B2%D0%B7%D0%B0%D0%B8%D0%BC%D0%BE%D0%B4%D0%B5%D0%B9%D1%81%D1%82%D0%B2%D0%B8%D1%8F-appsflyer-skan-%D0%B8-snapchat inapp-event-mapping-guide=%D1%80%D1%83%D0%BA%D0%BE%D0%B2%D0%BE%D0%B4%D1%81%D1%82%D0%B2%D0%BE-%D0%BF%D0%BE-%D1%81%D0%BE%D0%BF%D0%BE%D1%81%D1%82%D0%B0%D0%B2%D0%BB%D0%B5%D0%BD%D0%B8%D1%8E-%D0%B2%D0%BD%D1%83%D1%82%D1%80%D0%B5%D0%BD%D0%BD%D0%B8%D1%85-%D1%81%D0%BE%D0%B1%D1%8B%D1%82%D0%B8%D0%B9-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D1%8F h_01HDNZ3SPA742313RAJPYSEHWV=%D1%80%D1%83%D0%BA%D0%BE%D0%B2%D0%BE%D0%B4%D1%81%D1%82%D0%B2%D0%BE-%D0%BF%D0%BE-%D1%81%D0%BE%D0%BF%D0%BE%D1%81%D1%82%D0%B0%D0%B2%D0%BB%D0%B5%D0%BD%D0%B8%D1%8E-%D0%B2%D0%BD%D1%83%D1%82%D1%80%D0%B5%D0%BD%D0%BD%D0%B8%D1%85-%D1%81%D0%BE%D0%B1%D1%8B%D1%82%D0%B8%D0%B9-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D1%8F additional-information=%D0%B4%D0%BE%D0%BF%D0%BE%D0%BB%D0%BD%D0%B8%D1%82%D0%B5%D0%BB%D1%8C%D0%BD%D1%8B%D0%B5-%D1%81%D0%B2%D0%B5%D0%B4%D0%B5%D0%BD%D0%B8%D1%8F h_01HDNZ3SPASN8P9G5YYQGRFC8F=%D0%B4%D0%BE%D0%BF%D0%BE%D0%BB%D0%BD%D0%B8%D1%82%D0%B5%D0%BB%D1%8C%D0%BD%D1%8B%D0%B5-%D1%81%D0%B2%D0%B5%D0%B4%D0%B5%D0%BD%D0%B8%D1%8F h_01HDNZ3SPA99XHVBPXVWB5MN86=discrepancies-guide h_01HDNZ1BW5EBP0JCX84MTYPQ6K=%D1%81%D0%BC-%D1%82%D0%B0%D0%BA%D0%B6%D0%B5" />
