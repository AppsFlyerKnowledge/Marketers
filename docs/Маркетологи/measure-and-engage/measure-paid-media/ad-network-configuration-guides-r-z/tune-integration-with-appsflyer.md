---
title: Интеграция TUNE с AppsFlyer
metadata:
  keywords:
    - Advertisers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2021-08-25T08:58:17Z'
  edited_at: '2026-08-31T00:26:34Z'
  id: 4406153487505
  locale: ru
  section: Ad network configuration guides (R-Z)
  section_id: 6552025468305
  url: https://support.appsflyer.com/hc/ru/articles/4406153487505
---
> **Краткий обзор:** TUNE — это партнерская маркетинговая платформа и интегрированный партнер AppsFlyer.  
> Интегрируйтесь с TUNE, чтобы измерять входящий трафик и включить диплинкинг в приложение.

<Image align="center" alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/hasoffers.png" width="79px" />

<div id="setting-up-tune-integration" />

## Настройка интеграции TUNE

Интеграция AppsFlyer с TUNE поддерживает атрибуцию по кликам.

**Необходимые условия:** Перед настройкой интеграции обязательно свяжитесь с партнёром и откройте у него аккаунт.

**См. инструкции по настройке интеграции:**

1. **Чтобы активировать:** В AppsFlyer в боковом меню выберите **Сотрудничество**> **Маркетплейс партнеров**.
2. Выберите соответствующее приложение.
3. Найдите Tune и выберите **Integrate**.
4. На вкладке **Интеграция** выберите приложение для интеграции и нажмите **Активировать партнера**.  
    Держите его включенным, пока работаете с Tune.
5. При необходимости настройте остальные вкладки, описанные ниже.

| Настройка | Замечания |
| --- | --- |
| **Интеграция** | При необходимости настройте дополнительные параметры <Anchor target="_blank" href="/marketers/ru/docs/set-up-an-integrated-partner">интеграции</Anchor>.<br /><br />Поле Custom\_TUNE\_tracking\_domain используется для формирования вашего уникального URL-адреса конечной точки. Например, если вы введете "**greatapp**", URL-адрес конечной точки будет таким:  <br />https://greatapp.go2cloud.org/aff_Isr?<br /><br />Используйте одно и то же имя для пользовательского домена отслеживания событий в приложении. |
| **Ссылка атрибуции** | Создавайте <Anchor target="_blank" href="/marketers/ru/docs/set-up-an-integrated-partner#attribution-link-tab">ссылки атрибуции.</Anchor> |
| **затраты;** | Получайте <Anchor target="_blank" href="/marketers/ru/docs/set-up-an-integrated-partner#cost-tab">данные о расходах</Anchor>. |
| **Дата и время** | Недоступно для этого партнера |
| **Разрешения** | При необходимости задайте <Anchor target="_blank" href="/marketers/ru/docs/set-up-an-integrated-partner#permissions-tab">разрешения</Anchor> для рекламной сети. |

**Для активации или изменения интеграции:**

В AppsFlyer перейдите на вкладку **Сотрудничество> Интеграции партнеров > Активировать интеграции**, найдите партнера и внесите изменения.

<div id="enabling-deep-linking-into-your-app" />

## Включение диплинкинга в ваше приложение

Используйте <Anchor target="_blank" href="/marketers/ru/docs/brand-onelink-with-your-domain">брендированные ссылки OneLink</Anchor>, созданные в AppsFlyer, для измерения кликов в TUNE. Следующий процесс позволяет направлять пользователей с помощью диплинкинга на определенную страницу в приложении.

<div id="prerequisite" />

### Необходимое условие

Проверьте версии мобильного SDK AppsFlyer:

* iOS: V4.9.0 or later
* Android: V4.9.0 or later

<div id="step-1-configure-links-for-your-campaigns" />

### Шаг 1. Настройка ссылок для ваших кампаний

* Создайте <Anchor target="_blank" href="/marketers/ru/docs/create-a-onelink-template#создание-шаблонов-onelink">шаблон OneLink</Anchor> для ваших email-кампаний.
* <Anchor target="_blank" href="/marketers/ru/docs/brand-onelink-with-your-domain">Создайте брендированную ссылку.</Anchor>  
  Если будет предложено добавить CNAME в ваш домен, используйте `yourdomain.esplinks.appsflyer.com` вместо URL-адреса, предложенного на странице создания брендированной ссылки.  
  **Пример:**
  * **Поддомен:** `click.example.com`
  * **CNAME:** `example.appsflyer.com`

    <Image align="center" alt="branded-link-esp-new-en_us.png" src="https://files.readme.io/a7433ac0e3b343195bac9b4be49d22c18534ec1c145189198c5ec467fea510bb-21323417936145.png" />

    Обратите внимание: при нажатии **Verify** для проверки брендированного домена отображается сообщение об ошибке, связанное с CNAME AppsFlyer.

    <Image align="center" alt="branded-link-esp-cname-fail-message.png" src="https://files.readme.io/94f159a089152437111fc6e4308464bc48512ee18f5e249460006bfda05252c2-21323447961105.png" />

    Игнорируйте это сообщение и измените CNAME, как указано выше.

<div id="step-2-set-up-the-attribution-link" />

### Шаг 2. Настройте ссылку атрибуции

1. Перейдите на вкладку Attribution link и скопируйте только параметры ссылки в разделе **Click attribution link** , как показано ниже.[![](https://files.readme.io/51bb21c2fe4bd82965f30909fe5ed4ae6c5b906972789b143755982ea8b73f6e-4406164987537.png)](https://files.readme.io/51bb21c2fe4bd82965f30909fe5ed4ae6c5b906972789b143755982ea8b73f6e-4406164987537.png)
2. Добавьте скопированные параметры в вашу брендированную ссылку.

   <div id="example" />

   > 📄 **Пример:**
   >
   > <Image align="center" alt="TUNE-link-example2-en_us.png" src="https://files.readme.io/58f38eb0bb724b66d0c958454651e0950a54f6fd990220f2ac24f93ca89ba344-small-4410086650769.png" />

3. Чтобы завершить настройку, перейдите к <Anchor target="_blank" href="https://support.tune.com/hc/en-us/articles/1500008336641-Managing-Mobile-Offers-with-Appsflyer">руководству Managing Mobile Offers with AppsFlyer</Anchor> в центре помощи TUNE, прокрутите страницу вниз до раздела Universal Links via OneLink и следуйте инструкциям.

<div data-zendesk-anchors="setting-up-tune-integration=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-%D0%B8%D0%BD%D1%82%D0%B5%D0%B3%D1%80%D0%B0%D1%86%D0%B8%D0%B8-tune h_01HJZRGVZ1VQF4N93THDRT5YCJ=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-%D0%B8%D0%BD%D1%82%D0%B5%D0%B3%D1%80%D0%B0%D1%86%D0%B8%D0%B8-tune enabling-deep-linking-into-your-app=%D0%B2%D0%BA%D0%BB%D1%8E%D1%87%D0%B5%D0%BD%D0%B8%D0%B5-%D0%B4%D0%B8%D0%BF%D0%BB%D0%B8%D0%BD%D0%BA%D0%B8%D0%BD%D0%B3%D0%B0-%D0%B2-%D0%B2%D0%B0%D1%88%D0%B5-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D0%B5 h_01HJZRGVZ1KJ80ZA1THKFZ535P=%D0%B2%D0%BA%D0%BB%D1%8E%D1%87%D0%B5%D0%BD%D0%B8%D0%B5-%D0%B4%D0%B8%D0%BF%D0%BB%D0%B8%D0%BD%D0%BA%D0%B8%D0%BD%D0%B3%D0%B0-%D0%B2-%D0%B2%D0%B0%D1%88%D0%B5-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D0%B5 prerequisite=%D0%BD%D0%B5%D0%BE%D0%B1%D1%85%D0%BE%D0%B4%D0%B8%D0%BC%D0%BE%D0%B5-%D1%83%D1%81%D0%BB%D0%BE%D0%B2%D0%B8%D0%B5 h_01HJZRGVZ1ZC9G7M72V2HW4XDS=%D0%BD%D0%B5%D0%BE%D0%B1%D1%85%D0%BE%D0%B4%D0%B8%D0%BC%D0%BE%D0%B5-%D1%83%D1%81%D0%BB%D0%BE%D0%B2%D0%B8%D0%B5 step-1-configure-links-for-your-campaigns=%D1%88%D0%B0%D0%B3-1-%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-%D1%81%D1%81%D1%8B%D0%BB%D0%BE%D0%BA-%D0%B4%D0%BB%D1%8F-%D0%B2%D0%B0%D1%88%D0%B8%D1%85-%D0%BA%D0%B0%D0%BC%D0%BF%D0%B0%D0%BD%D0%B8%D0%B9 h_01HJZRGVZ1GPR3NQQAXRBXV09Z=%D1%88%D0%B0%D0%B3-1-%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-%D1%81%D1%81%D1%8B%D0%BB%D0%BE%D0%BA-%D0%B4%D0%BB%D1%8F-%D0%B2%D0%B0%D1%88%D0%B8%D1%85-%D0%BA%D0%B0%D0%BC%D0%BF%D0%B0%D0%BD%D0%B8%D0%B9 step-2-set-up-the-attribution-link=%D1%88%D0%B0%D0%B3-2-%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D1%82%D0%B5-%D1%81%D1%81%D1%8B%D0%BB%D0%BA%D1%83-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8 h_01HJZRGVZ2F83PHABEWJXMMJ22=%D1%88%D0%B0%D0%B3-2-%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D1%82%D0%B5-%D1%81%D1%81%D1%8B%D0%BB%D0%BA%D1%83-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8 h_01HJZRGVZ2435CGWY4FZ5FKKHV=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%80" />
