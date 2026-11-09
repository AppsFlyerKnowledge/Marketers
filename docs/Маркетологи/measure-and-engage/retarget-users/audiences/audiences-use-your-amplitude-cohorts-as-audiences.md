---
title: Аудитории — используйте когорты Amplitude как аудитории
metadata:
  keywords:
    - Audiences
    - Premium
    - Marketers
    - Audience Segmentation
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-neama-benhabib
    - Marketers
    - Audience Segmentation
  created_at: '2022-02-23T14:27:13Z'
  edited_at: '2026-08-18T00:37:08Z'
  id: 4470658876817
  locale: ru
  section: Audiences
  section_id: 6551336428945
  url: https://support.appsflyer.com/hc/ru/articles/4470658876817
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **Вкратце:** Используйте собственные данные, синхронизируя когорты Amplitude с AppsFlyer в качестве импортированных аудиторий.

<div id="about-the-amplitude-integration" />

## О интеграции с Amplitude

Интеграция **AppsFlyer Audiences-Amplitude** позволяет вам синхронизировать определенные вами в Amplitude когорты напрямую с AppsFlyer в виде <Anchor target="_blank" href="/marketers/ru/docs/audiences-import-audience-segments-from-internal-systems">импортированных аудиторий</Anchor>. AppsFlyer может служить центром для связи и поддержки этих сегментов аудитории с Партнерами, анализа показателей кампаний и объединения ваших данных Amplitude и AppsFlyer для полного их использования.

Когорты Amplitude можно синхронизировать с AppsFlyer либо однократно, либо в запланированном режиме с ежедневными или ежечасными обновлениями.

<div id="setting-up-the-integration" />

## Настройка интеграции

Настройте интеграцию Audiences-Amplitude из платформы Amplitude.

<div id="define-appsflyer-data-destinations" />

### Определение мест назначения данных AppsFlyer

**Следуйте этим шагам в Amplitude, чтобы определить места назначения данных AppsFlyer.** **Учтите, что вам нужно определить отдельное место назначения данных для каждого Приложения, для которого вы импортируете аудитории AppsFlyer.**

1. В разделе **Назначения данных** в Amplitude выберите плитку **AppsFlyer**.
2. В разделе **Назначения когорт** выберите **AppsFlyer.**
3. Введите следующую информацию в диалоговом окне **Подключение к AppsFlyer**.

   **Важно!** Если в вашей учетной записи Amplitude уже созданы места назначения данных AppsFlyer, диалоговое окно будет представлять собой прокручиваемый список, в котором отображены все существующие места назначения. Чтобы создать новое место назначения, прокрутите список до конца и нажмите **Добавить другой пункт назначения**.

   <Image align="center" alt="" src="https://files.readme.io/ba47fc9a411bd55d84ad34ccd5c1d74fecb1648f8f7aed3ae713965bef616ae8-33375708375441.png" />

   

| Поле | Описание |
| --- | --- |
| Имя | Введите название для пункта назначения.<br /><br />Если вы будете создавать более одного пункта назначения AppsFlyer в проекте Amplitude (например, если у вас несколько Приложений в проекте), обязательно создайте имя, которое можно будет легко идентифицировать позже. |
| Токен API AppsFlyer V2.0 | **Чтобы получить токен API AppsFlyer, выполните эти шаги в AppsFlyer:**<ol><li>Из верхнего меню, доступ к меню пользователя (адрес электронной почты в правом верхнем углу).</li><li>Выберите **Центр безопасности.**</li><li>В разделе **Токены API AppsFlyer** нажмите **Управление токенами API AppsFlyer.**</li><li>Скопируйте токен **V2.0**.</li></ol> |
| AppsFlyer ID приложения | Введите идентификатор приложения для этого назначения так, как он отображается на дэшборде AppsFlyer:<br /><br />![amplitude_app_id_from_appsflyer_dashboard.png](https://files.readme.io/2e7da9a20f0c4b59e58f51823dd9753ecc36b77e84622821cb3cb65e4f7b2743-33375708378385.png) |
| Платформа | Выберите платформу приложения (iOS или Android). |
| Идентификатор | Инструктируйте AppsFlyer как связать ваши данные Amplitude с данными AppsFlyer, выбрав свойство пользователя Amplitude слева и соответствующий ключ AppsFlyer для сопоставления справа. Выбранный вами ключ AppsFlyer должен быть одним из следующих:<ul><li>**Для аудитории iOS:** идентификатор рекламодателя iOS, идентификатор пользователя Amplitude или идентификатор пользователя клиента AppsFlyer</li><li>**Для аудитории Android:** Идентификатор рекламодателя Google, идентификатор пользователя Amplitude или идентификатор пользователя клиента AppsFlyer</li></ul> |

4. Нажмите **Сохранить**, чтобы сохранить новое назначение AppsFlyer.

<div id="sync-amplitude-cohorts-to-appsflyer-destinations" />

### Синхронизация когорт Amplitude с целями AppsFlyer

**Далее выполните следующие шаги, чтобы синхронизировать любую из ваших когорт Amplitude с вашими целями AppsFlyer:**

1. В разделе **Когорты** платформы Amplitude выберите когорту, для которой вы хотите создать аудиторию AppsFlyer. (Альтернативно, вы можете создать новую когорту.)
2. Перейдите по ссылке: **Нажмите, чтобы просмотреть детали когорты.**
3. На странице **Определение когорты** нажмите кнопку **Синхронизировать с…** .
4. Выберите плитку AppsFlyer, затем нажмите **Далее.**

   Откроется диалоговое окно **Определение назначения и частоты**.

   <Image align="center" alt="amplitude_define_destination_and_cadence_dialog.png" src="https://files.readme.io/e9f726c731e865e6313bf430b1e5506db5a820fc7d3d544747a873cf08139b26-33375708382097.png" />
5. В списке **Выберите цель API для синхронизации** выберите имя соответствующего назначения AppsFlyer.
6. Выберите, хотите ли вы синхронизировать эту когорту с AppsFlyer один раз или по заданному расписанию. (Для запланированных синхронизаций выберите, обновлять ли данные ежедневно или ежечасно.)
7. Нажмите кнопку **Синхронизировать**, чтобы начать процесс синхронизации.

После успешного завершения первой синхронизации новая аудитория для этой когорты будет видна на вкладке «Аудитории» дэшборда «Аудитории».

По умолчанию именем новой аудитории является имя синхронизированной когорты Amplitude, за которым следует буквенно-цифровой идентификатор. Вы можете изменить название аудитории на дэшборде аудиториями, если это необходимо.

<Image align="center" alt="amplitude_imported_audience.png" src="https://files.readme.io/a4f8efc6818d94a68b28ca62ae26215f17bfc7edcfb990855a042a2dee71f8b6-33375708383249.png" />

<div data-zendesk-anchors="overview=%D0%BE-%D0%B8%D0%BD%D1%82%D0%B5%D0%B3%D1%80%D0%B0%D1%86%D0%B8%D0%B8-%D1%81-amplitude h_01HNZP6HDVC5RBMKTCZY81HG4M=%D0%BE-%D0%B8%D0%BD%D1%82%D0%B5%D0%B3%D1%80%D0%B0%D1%86%D0%B8%D0%B8-%D1%81-amplitude setting-up-the-integration=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-%D0%B8%D0%BD%D1%82%D0%B5%D0%B3%D1%80%D0%B0%D1%86%D0%B8%D0%B8 h_01HNZP6HDVZH6Q1KGJE7FXSPMT=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-%D0%B8%D0%BD%D1%82%D0%B5%D0%B3%D1%80%D0%B0%D1%86%D0%B8%D0%B8 define-appsflyer-data-destinations=%D0%BE%D0%BF%D1%80%D0%B5%D0%B4%D0%B5%D0%BB%D0%B5%D0%BD%D0%B8%D0%B5-%D0%BC%D0%B5%D1%81%D1%82-%D0%BD%D0%B0%D0%B7%D0%BD%D0%B0%D1%87%D0%B5%D0%BD%D0%B8%D1%8F-%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D1%85-appsflyer h_01HNZP6HDVV3GSEPARCY1VABX8=%D0%BE%D0%BF%D1%80%D0%B5%D0%B4%D0%B5%D0%BB%D0%B5%D0%BD%D0%B8%D0%B5-%D0%BC%D0%B5%D1%81%D1%82-%D0%BD%D0%B0%D0%B7%D0%BD%D0%B0%D1%87%D0%B5%D0%BD%D0%B8%D1%8F-%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D1%85-appsflyer sync-amplitude-cohorts-to-appsflyer-destinations=%D1%81%D0%B8%D0%BD%D1%85%D1%80%D0%BE%D0%BD%D0%B8%D0%B7%D0%B0%D1%86%D0%B8%D1%8F-%D0%BA%D0%BE%D0%B3%D0%BE%D1%80%D1%82-amplitude-%D1%81-%D1%86%D0%B5%D0%BB%D1%8F%D0%BC%D0%B8-appsflyer h_01HNZP6HDV6EFPCM5FE5XBAS78=%D1%81%D0%B8%D0%BD%D1%85%D1%80%D0%BE%D0%BD%D0%B8%D0%B7%D0%B0%D1%86%D0%B8%D1%8F-%D0%BA%D0%BE%D0%B3%D0%BE%D1%80%D1%82-amplitude-%D1%81-%D1%86%D0%B5%D0%BB%D1%8F%D0%BC%D0%B8-appsflyer" />
