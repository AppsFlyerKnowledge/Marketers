---
title: >-
  Платформа для совместной работы с данными (DCP) – настройка управления
  совместной работы
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
  created_at: '2025-01-27T09:58:46Z'
  edited_at: '2026-08-18T00:06:45Z'
  id: 32147174933905
  locale: ru
  section: Collaboration measurement
  section_id: 38034865098641
  url: https://support.appsflyer.com/hc/ru/articles/32147174933905
---
**Краткий обзор:** Узнайте, как настроить DCP для выполнения атрибуции на уровне SKU на основе источников конверсии, вовлеченности и сопоставления кампаний.

<div id="overview" />

## Обзор

После <Anchor target="_blank" href="/marketers/ru/docs/data-collaboration-platform-dcp-prepare-collaboration-measurement">подготовки данных о конверсиях, вовлечённости и сопоставлении кампаний</Anchor> вы можете настроить DCP для их использования в измерении и атрибуции:

1. [**Определите тип кампании**](#выберите-тип-кампании-на-площадке-вне-площадке-или-оба-варианта) – Выберите на платформе, вне платформы или комбинированно. Это определяет, как DCP обрабатывает ваши данные и устанавливает необходимые задачи конфигурации.
2. [**Назначьте задачи**](#назначить-задачу-конфигурации) – Владелец назначает каждую задачу конфигурации партнеру, имеющему доступ к соответствующим данным.
3. [**Настройте задачи**](#внутренние-и-внешние-измерения-кампаний) – Партнеры настраивают конверсии, вовлеченность и сопоставление кампаний. Это включает в себя настройку кампаний на площадке и вне площадки, чтобы все данные были связаны, сопоставлены и готовы к атрибуции.
4. <Anchor target="_blank" href="/marketers/ru/docs/data-collaboration-platform-dcp-run-and-manage-measurement">**Запустите и управляйте измерениями**</Anchor> - Запускайте измерения в реальном времени или ретроспективно, дублируйте их, повторно запускайте или изменяйте их объем.

<div id="start-the-measurement-setup" />

## Начните настройку измерения

Чтобы начать настройку измерения, выполните следующие шаги:

1. В AppsFlyer в боковом меню выберите **Сотрудничество** > **Data Clean Room**.
2. На странице **Платформа совместной работы с данными** выберите сотрудничество, которое вы хотите настроить.
3. На странице Совместной работы выполните **один** из следующих шагов:
   * Если это первая настройка измерения в вашем сотрудничестве, нажмите **Настроить измерение.** Отображается страница **Создать измерение**.
   * Если у вас уже есть набор измерений в вашем сотрудничестве, нажмите знак плюса в панели выбора измерений. Отображается страница **Создать измерение**.

[![start-measurement.png](https://files.readme.io/c87bae214a48e807c085d192fd1b2132559a23a0954ea4fedae57b8d18372cae-44433074460305.png)](https://files.readme.io/c87bae214a48e807c085d192fd1b2132559a23a0954ea4fedae57b8d18372cae-44433074460305.png)

<div id="select-campaign-type-on-site-off-site-or-both" />

## Выберите тип кампании: на площадке, вне площадке или оба варианта

Поскольку кампании «на площадке» и «вне площадки» различаются местом конверсии и способом атрибуции, владелец совместной работы должен указать тип кампании до настройки измерения сотрудничества. Более подробную информацию см. здесь: <Anchor target="_blank" href="/marketers/ru/docs/data-collaboration-platform-dcp-collaboration-measurement-overview#on-site-vs-off-site-campaign-measurement">Измерение кампаний «на площадке» и «вне площадки»</Anchor>.

Чтобы выбрать тип кампании, выполните следующие шаги:

1. [Начните настройку измерений](#начните-настройку-измерения).
2. На странице **Создать измерение** выберите  <Image alt="on-site icon.png" src="https://files.readme.io/c9ff0bb1e2c31527ee38a9403a6180e3ecd4c3ad105935fb59ed14c2474f6039-32148924980113.png" width="3.27%" /> **На площадке, <Image alt="off-site icon.png" src="https://files.readme.io/6de5841985237de221c74d427ad06f719572000aafe8077c7cef64e53ee8caf5-32156666763921.png" width="3.3%" /> Вне площадки**, или оба варианта. Перейдите к **одному** из следующих вариантов.
   * [Настроить кампанию на месте](#внутренние-и-внешние-измерения-кампаний),
   * [Настроить кампанию вне места](#configure-offsite-campaign-measurement),
   * [Настроить комбинированную кампанию на месте и вне места](#configure-combined-onsite-and-offsite-campaign-measurement).

<div id="assign-configuration-task" />

## Назначить задачу конфигурации

Страница настроек измерения включает пять ключевых задач: конверсии, вовлечённость, сопоставление кампаний, медиа-партнёры и конфигурация окна ретроспективы.

Владелец аккаунта DCP может назначать задачи партнерам, чтобы обеспечить конфиденциальность данных и отразить разделение обязанностей. Например, один партнер может обрабатывать данные о вовлеченности, в то время как другой обрабатывает конверсии. Партнеры имеют доступ только к назначенным задачам.

<div id="assign-a-configuration-task-to-a-collaborator" />

<Accordion title="Назначьте задачу по конфигурации партнеру">

Чтобы назначить любую из вышеуказанных задач, выполните следующие шаги:

1. [Открыть настройки измерения](#начните-настройку-измерения).
2. В каждой из четырех задач из списка **Исполнитель**, выберите участника, который будет выполнять задачу.
   * **Задача по конверсиям:** Назначьте партнеру, чья платформа обрабатывает конверсии.
   * **Задача по кампаниям:** Назначьте партнеру, чья платформа обрабатывает конверсии.
   * **Задача по вовлеченности:** Назначьте эту задачу тому участнику, на стороне которого происходит вовлечённость пользователей.
   * **Задача медиапартнеров:** Назначьте эту задачу тому участнику, чей аккаунт медиа-партнёра используется для кампаний вне площадки
   * **Задача окна ретроспективы** – Автоматически назначается владельцу сотрудничества. При желании вы можете назначить другого участника.

</Accordion>

<div id="remove-the-configuration-task-assignment-from-a-collaborator" />

<Accordion title="Удалите назначение задачи конфигурации у партнера">

В некоторых случаях может потребоваться отозвать назначение задачи конфигурации у партнера. Когда владелец сотрудничества удаляет назначение, происходит следующее:

* Партнер немедленно теряет доступ к не назначенной задаче.
* Любая конфигурация, ранее предоставленная участником для этой задачи, удаляется.
* Измерение сотрудничества прекращается.

Чтобы удалить назначение задачи конфигурации, выполните следующие шаги:

1. Перейдите к измерению сотрудничества, смотрите Открыть настройки измерения.
2. На соответствующем шаге конфигурации в списке **Назначенный** удалите назначенного партнера.

</Accordion>

<div id="configure-on-site-and-off-site-campaign-measurement" />

## Внутренние и внешние измерения кампаний

Настройте установку измерения кампании в настройках измерения. Используйте приведённые ниже шаги в зависимости от того, является ли ваше измерение «на площадке», «вне площадки» или комбинированным (на площадке и вне площадки).

<div id="configure-onsite-campaign-measurement::4f9b35af" />

<Accordion title="Настройте измерение кампании на месте">

Чтобы настроить <Anchor target="_blank" href="/marketers/ru/docs/data-collaboration-platform-dcp-collaboration-measurement-overview#on-site-campaigns">кампанию на площадке</Anchor>, выполните следующие шаги:

1. [Начните настройку измерений](#начните-настройку-измерения).
2. <Anchor target="_blank" href="/marketers/ru/docs/set-up-the-campaigns-task">Настройте задачу кампаний</Anchor>
3. <Anchor target="_blank" href="/marketers/ru/docs/set-up-the-conversions-task">Настройте задачу конверсий</Anchor>
4. <Anchor target="_blank" href="/marketers/ru/docs/set-up-the-engagements-task">Настройте задачу вовлеченности</Anchor>
5. <Anchor target="_blank" href="/marketers/ru/docs/set-up-the-lookback-windows-task">Настройте задачу окна ретроспективы</Anchor>

</Accordion>

<div id="configure-offsite-campaign-measurement" />

<Accordion title="Настройте измерение кампаний вне площадки">

Чтобы настроить <Anchor target="_blank" href="/marketers/ru/docs/data-collaboration-platform-dcp-collaboration-measurement-overview#off-site-campaigns">кампанию вне площадки</Anchor>, выполните следующие шаги:

1. [Начните настройку измерений](#начните-настройку-измерения).
2. <Anchor target="_blank" href="/marketers/ru/docs/set-up-the-campaigns-task">Настройте задачу кампаний</Anchor>
3. <Anchor target="_blank" href="/marketers/ru/docs/set-up-the-conversions-task">Настройте задачу конверсий</Anchor>
4. <Anchor target="_blank" href="/marketers/ru/docs/set-up-the-media-partners-task">Настройте задачу по медиапартнерам</Anchor>
5. <Anchor target="_blank" href="/marketers/ru/docs/set-up-the-lookback-windows-task">Настройте задачу окна ретроспективы</Anchor>

</Accordion>

<div id="configure-combined-onsite-and-offsite-campaign-measurement" />

<Accordion title="Настройте комбинированное измерение кампаний на площадке и вне его">

Чтобы настроить <Anchor target="_blank" href="/marketers/ru/docs/data-collaboration-platform-dcp-collaboration-measurement-overview#on-site-and-off-site-campaigns">комбинированную кампанию на площадке и вне ее</Anchor>, выполните следующие шаги:

1. [Начните настройку измерений](#начните-настройку-измерения).
2. <Anchor target="_blank" href="/marketers/ru/docs/set-up-the-campaigns-task">Настройте задачу кампаний</Anchor>
3. <Anchor target="_blank" href="/marketers/ru/docs/set-up-the-conversions-task">Настройте задачу конверсий</Anchor>
4. <Anchor target="_blank" href="/marketers/ru/docs/set-up-the-engagements-task">Настройте задачу вовлеченности</Anchor>
5. <Anchor target="_blank" href="/marketers/ru/docs/set-up-the-media-partners-task">Настройте задачу по медиапартнерам</Anchor>
6. <Anchor target="_blank" href="/marketers/ru/docs/set-up-the-lookback-windows-task">Настройте задачу окна ретроспективы</Anchor>

</Accordion>

<div data-zendesk-anchors="overview=%D0%BE%D0%B1%D0%B7%D0%BE%D1%80 h_01K3EHANCCZ703MMMM5PTEF68B=%D0%BE%D0%B1%D0%B7%D0%BE%D1%80 open-measurement-settings=%D0%BD%D0%B0%D1%87%D0%BD%D0%B8%D1%82%D0%B5-%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D1%83-%D0%B8%D0%B7%D0%BC%D0%B5%D1%80%D0%B5%D0%BD%D0%B8%D1%8F h_01JJKK3CQ8F9Q7VM7MM9AFKNN5=%D0%BD%D0%B0%D1%87%D0%BD%D0%B8%D1%82%D0%B5-%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D1%83-%D0%B8%D0%B7%D0%BC%D0%B5%D1%80%D0%B5%D0%BD%D0%B8%D1%8F select-campaign-type-onsite-offsite-or-both=%D0%B2%D1%8B%D0%B1%D0%B5%D1%80%D0%B8%D1%82%D0%B5-%D1%82%D0%B8%D0%BF-%D0%BA%D0%B0%D0%BC%D0%BF%D0%B0%D0%BD%D0%B8%D0%B8-%D0%BD%D0%B0-%D0%BF%D0%BB%D0%BE%D1%89%D0%B0%D0%B4%D0%BA%D0%B5-%D0%B2%D0%BD%D0%B5-%D0%BF%D0%BB%D0%BE%D1%89%D0%B0%D0%B4%D0%BA%D0%B5-%D0%B8%D0%BB%D0%B8-%D0%BE%D0%B1%D0%B0-%D0%B2%D0%B0%D1%80%D0%B8%D0%B0%D0%BD%D1%82%D0%B0 h_01K3EHANCCW8PQ8NWC6ZHWCMGT=%D0%B2%D1%8B%D0%B1%D0%B5%D1%80%D0%B8%D1%82%D0%B5-%D1%82%D0%B8%D0%BF-%D0%BA%D0%B0%D0%BC%D0%BF%D0%B0%D0%BD%D0%B8%D0%B8-%D0%BD%D0%B0-%D0%BF%D0%BB%D0%BE%D1%89%D0%B0%D0%B4%D0%BA%D0%B5-%D0%B2%D0%BD%D0%B5-%D0%BF%D0%BB%D0%BE%D1%89%D0%B0%D0%B4%D0%BA%D0%B5-%D0%B8%D0%BB%D0%B8-%D0%BE%D0%B1%D0%B0-%D0%B2%D0%B0%D1%80%D0%B8%D0%B0%D0%BD%D1%82%D0%B0 assign-configuration-task=%D0%BD%D0%B0%D0%B7%D0%BD%D0%B0%D1%87%D0%B8%D1%82%D1%8C-%D0%B7%D0%B0%D0%B4%D0%B0%D1%87%D1%83-%D0%BA%D0%BE%D0%BD%D1%84%D0%B8%D0%B3%D1%83%D1%80%D0%B0%D1%86%D0%B8%D0%B8 h_01K3EHANCCW97TV88ECVMQKF2N=%D0%BD%D0%B0%D0%B7%D0%BD%D0%B0%D1%87%D0%B8%D1%82%D1%8C-%D0%B7%D0%B0%D0%B4%D0%B0%D1%87%D1%83-%D0%BA%D0%BE%D0%BD%D1%84%D0%B8%D0%B3%D1%83%D1%80%D0%B0%D1%86%D0%B8%D0%B8 h_01K3EHANCD71R47V88DR61CTMV=assign-a-configuration-task-to-a-collaborator h_01K3EHANCDF1HMTV8X35Q1RHTS=remove-the-configuration-task-assignment-from-a-collaborator configure-onsite-campaign-measurement=%D0%B2%D0%BD%D1%83%D1%82%D1%80%D0%B5%D0%BD%D0%BD%D0%B8%D0%B5-%D0%B8-%D0%B2%D0%BD%D0%B5%D1%88%D0%BD%D0%B8%D0%B5-%D0%B8%D0%B7%D0%BC%D0%B5%D1%80%D0%B5%D0%BD%D0%B8%D1%8F-%D0%BA%D0%B0%D0%BC%D0%BF%D0%B0%D0%BD%D0%B8%D0%B9 h_01K3EHANCD936QN2MKFY5QSDBZ=%D0%B2%D0%BD%D1%83%D1%82%D1%80%D0%B5%D0%BD%D0%BD%D0%B8%D0%B5-%D0%B8-%D0%B2%D0%BD%D0%B5%D1%88%D0%BD%D0%B8%D0%B5-%D0%B8%D0%B7%D0%BC%D0%B5%D1%80%D0%B5%D0%BD%D0%B8%D1%8F-%D0%BA%D0%B0%D0%BC%D0%BF%D0%B0%D0%BD%D0%B8%D0%B9 h_01KJWCMN3XRTS3361N08RT1SD6=configure-onsite-campaign-measurement::4f9b35af h_01KJWCMN3XRXW6A71P5678AHH1=configure-offsite-campaign-measurement h_01KJWCMN3XKD8YJVPQEZ53K819=configure-combined-onsite-and-offsite-campaign-measurement" />
