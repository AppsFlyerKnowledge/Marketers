---
title: Настройте задачу  Окна ретроспективного анализа
metadata:
  keywords:
    - Marketers
    - Data Clean Room
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-yael-sharabi
    - Marketers
    - Data Clean Room
  created_at: '2025-08-18T11:38:51Z'
  edited_at: '2026-08-27T00:05:44Z'
  id: 38191154658193
  locale: ru
  section: Set up the measurement data tasks
  section_id: 38035061674769
  url: https://support.appsflyer.com/hc/ru/articles/38191154658193
---
## Настройка Окон ретроспективного анализа

> **Кратко:** Задайте окна атрибуции для кампаний на сайте и вне сайта, чтобы определить, за какой период вовлеченность пользователей может быть сопоставлена с конверсиями.

Окна атрибуции определяют максимальный период времени между вовлеченностью пользователя (кликом или просмотром) и итоговой конверсией для целей атрибуции. Для каждого сотрудничества можно задать пользовательскую длительность окна атрибуции. Медиапартнеры, такие как Google Ads или Meta Ads, обычно применяют разные правила для настройки этих окон. В этой статье объясняется, как настроить окна атрибуции как для участников сотрудничества, так и для Google и Meta.

## Требования

Прежде чем участник совместной работы, который не является ее владельцем, сможет настроить задачу «Окна атрибуции», владелец должен сначала назначить ее этому участнику. Более подробную информацию см. здесь: Назначение задач настройки.

## Откройте задачу «Окна ретроспективного анализа»

В задаче «Окна атрибуции» на странице **Настройки измерения** настраиваются окна атрибуции для <Anchor target="_blank" href="/marketers/ru/docs/data-collaboration-platform-dcp-collaboration-measurement-overview#on-site-vs-off-site-campaign-measurement">кампаний на сайте и вне сайта</Anchor>.

Чтобы открыть задачу «Окна ретроспективного анализа», выполните следующие шаги:

1. В AppsFlyer в боковом меню выберите **Сотрудничество** > **Data Clean Room**.
2. На странице **Платформа совместной работы с данными** выберите сотрудничество, которое вы хотите настроить.
3. В нижней части страницы совместной работы нажмите **Настроить измерение**
   * Если ссылка неактивна, настройте <Anchor target="_blank" href="/marketers/ru/docs/data-collaboration-platform-dcp-create-and-manage-sources">источники данных</Anchor> и <Anchor target="_blank" href="/marketers/ru/docs/data-collaboration-platform-dcp-build-and-activate-audiences">аудитории</Anchor> для совместной работы.
4. На странице **Настройки измерения** нажмите панель **Окна ретроспективного анализа**, чтобы открыть диалоговое окно **Окна ретроспективного анализа**.

   > 📘 **Примечание**
   >
   > Если панель **Окна ретроспективного анализа** неактивна, попросите владельца панели совместной работы назначить вам задачу Окна ретроспективного анализа.


## Настройте окно ретроспективного анализа для совместной работы

Чтобы настроить окно ретроспективного анализа для совместной работы, выполните следующие шаги:

1. Если вы настраиваете <Anchor target="_blank" href="/marketers/ru/docs/data-collaboration-platform-dcp-collaboration-measurement-overview#on-site-and-off-site-campaigns">комбинированную кампанию на сайте и за его пределами</Anchor> в диалоговом окне **Окна ретроспективного анализа** , разверните панель <Image alt="AppsFlyer.png" src="https://files.readme.io/2536fe45ebde303e110c7b90cb3b2a95fc28672a5fa095efff485cdebbd466df-38392816916369.png" width="2.61%" />**Атрибуция CMN**. В противном случае перейдите к следующему шагу.
2. На ползунках **Окно атрибуции по кликам** или **Окно атрибуции по показам** перетащите указатель, чтобы выбрать длительность окна в днях.
3. Нажмите **Сохранить**.

## Настройка окна атрибуции Meta Ads

Если вы запускаете кампанию вне сайта с Meta Ads, задача «Окна атрибуции» будет включать настройки специально для Meta Ads. Можно отдельно настроить окна атрибуции по кликам и по просмотрам в соответствии с предустановленной длительностью окон в Meta Ads.

1. На панели **Lookback windows** разверните панель <Image alt="Meta.png" src="https://files.readme.io/4023aa4c9446f22aa46063ab349fc038d974638aeefcbb3288e04663896ec788-38392832989585.png" width="3.22%" /> **Meta Ads**.
2. Выберите окна атрибуции **Click-through** и **View-through** из следующих вариантов:
   * **1 день**
   * **7 дней**
   * **28 дней**

## Окно атрибуции Google Ads

Если у вас запущена внешняя кампания в Google Ads, задача Lookback windows будет содержать ссылку на платформу Google Ads.

1. В диалоговом окне **Lookback windows** прокрутите до панели <Image alt="Google-ads.png" src="https://files.readme.io/afa0e2cd15ea4214eba625da397dccd04118b564450c59993fd0e668c31f023b-38392832994321.png" width="2.86%" /> **Google Ads**.
2. Нажмите значок **стрелки**, чтобы открыть соответствующую страницу настроек действия-конверсии на платформе Google Ads.
3. При необходимости обновите настройки окна атрибуции в Google Ads.

<div data-zendesk-anchors="set-lookback-windows=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-%D0%BE%D0%BA%D0%BE%D0%BD-%D1%80%D0%B5%D1%82%D1%80%D0%BE%D1%81%D0%BF%D0%B5%D0%BA%D1%82%D0%B8%D0%B2%D0%BD%D0%BE%D0%B3%D0%BE-%D0%B0%D0%BD%D0%B0%D0%BB%D0%B8%D0%B7%D0%B0 h_01K3G9Q0G79BDATM6T80T6F6TX=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-%D0%BE%D0%BA%D0%BE%D0%BD-%D1%80%D0%B5%D1%82%D1%80%D0%BE%D1%81%D0%BF%D0%B5%D0%BA%D1%82%D0%B8%D0%B2%D0%BD%D0%BE%D0%B3%D0%BE-%D0%B0%D0%BD%D0%B0%D0%BB%D0%B8%D0%B7%D0%B0 prerequisites=%D1%82%D1%80%D0%B5%D0%B1%D0%BE%D0%B2%D0%B0%D0%BD%D0%B8%D1%8F h_01K3G9Q0G7XSM1VS4VF9VCTWD0=%D1%82%D1%80%D0%B5%D0%B1%D0%BE%D0%B2%D0%B0%D0%BD%D0%B8%D1%8F open-the-lookback-windows-task=%D0%BE%D1%82%D0%BA%D1%80%D0%BE%D0%B9%D1%82%D0%B5-%D0%B7%D0%B0%D0%B4%D0%B0%D1%87%D1%83-%D0%BE%D0%BA%D0%BD%D0%B0-%D1%80%D0%B5%D1%82%D1%80%D0%BE%D1%81%D0%BF%D0%B5%D0%BA%D1%82%D0%B8%D0%B2%D0%BD%D0%BE%D0%B3%D0%BE-%D0%B0%D0%BD%D0%B0%D0%BB%D0%B8%D0%B7%D0%B0 h_01K3G9Q0G7FM4MMR6CVWM4ATRA=%D0%BE%D1%82%D0%BA%D1%80%D0%BE%D0%B9%D1%82%D0%B5-%D0%B7%D0%B0%D0%B4%D0%B0%D1%87%D1%83-%D0%BE%D0%BA%D0%BD%D0%B0-%D1%80%D0%B5%D1%82%D1%80%D0%BE%D1%81%D0%BF%D0%B5%D0%BA%D1%82%D0%B8%D0%B2%D0%BD%D0%BE%D0%B3%D0%BE-%D0%B0%D0%BD%D0%B0%D0%BB%D0%B8%D0%B7%D0%B0 h_01K3G9Q0G7DQRCX9FH9Q3N17N3=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%87%D0%B0%D0%BD%D0%B8%D0%B5 set-the-collaboration-lookback-window=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D1%82%D0%B5-%D0%BE%D0%BA%D0%BD%D0%BE-%D1%80%D0%B5%D1%82%D1%80%D0%BE%D1%81%D0%BF%D0%B5%D0%BA%D1%82%D0%B8%D0%B2%D0%BD%D0%BE%D0%B3%D0%BE-%D0%B0%D0%BD%D0%B0%D0%BB%D0%B8%D0%B7%D0%B0-%D0%B4%D0%BB%D1%8F-%D1%81%D0%BE%D0%B2%D0%BC%D0%B5%D1%81%D1%82%D0%BD%D0%BE%D0%B9-%D1%80%D0%B0%D0%B1%D0%BE%D1%82%D1%8B h_01K3G9Q0G7X7FY6C0H4DQYSP3F=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D1%82%D0%B5-%D0%BE%D0%BA%D0%BD%D0%BE-%D1%80%D0%B5%D1%82%D1%80%D0%BE%D1%81%D0%BF%D0%B5%D0%BA%D1%82%D0%B8%D0%B2%D0%BD%D0%BE%D0%B3%D0%BE-%D0%B0%D0%BD%D0%B0%D0%BB%D0%B8%D0%B7%D0%B0-%D0%B4%D0%BB%D1%8F-%D1%81%D0%BE%D0%B2%D0%BC%D0%B5%D1%81%D1%82%D0%BD%D0%BE%D0%B9-%D1%80%D0%B0%D0%B1%D0%BE%D1%82%D1%8B set-the-meta-ads-lookback-window=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-%D0%BE%D0%BA%D0%BD%D0%B0-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8-meta-ads h_01K3G9Q0G71ADFQ9QHBXJBTEAA=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-%D0%BE%D0%BA%D0%BD%D0%B0-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8-meta-ads google-ads-lookback-window=%D0%BE%D0%BA%D0%BD%D0%BE-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8-google-ads h_01K3G9Q0G7HEFS65XA6YD0V6YD=%D0%BE%D0%BA%D0%BD%D0%BE-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8-google-ads" />
