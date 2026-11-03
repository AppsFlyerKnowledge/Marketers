---
title: "Руководство по настройке X Ads (ранее Twitter Ads)\_— частые вопросы и расхождения"
metadata:
  keywords:
    - Advertisers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
  created_at: '2021-11-09T09:34:59Z'
  edited_at: '2026-09-17T00:30:27Z'
  id: 4410464352017
  locale: ru
  section: X Ads (formerly Twitter Ads)
  section_id: 6551370375569
  url: https://support.appsflyer.com/hc/ru/articles/4410464352017
---
> **Краткий обзор**. Ответы на популярные вопросы о Х Ads и разбор расхождений.

## Х Ads: часто задаваемые вопросы и расхождения

<div id="who-can-perform-the-twitter-setup-on-appsflyer" />

<Accordion title="Кто может выполнить настройки в AppsFlyer?">

Пользователь, который дает разрешение на интеграцию между AppsFlyer и Twitter, должен иметь доступ к аккаунту администратора в Twitter.

</Accordion>

<div id="what-happens-if-no-twitter-accounts-are-selected-for-attributing-on-appsflyer" />

<Accordion title="Что произойдет, если в AppsFlyer не выбрать для атрибуции ни одной учетной записи в Twitter?">

Все события будут атрибутированы кампаниям в выбранном аккаунте. Если аккаунты не выбраны, внутренние события приложения и атрибуции не отсылаются в Twitter, даже если сопоставленные внутренние события приложения отображаются в окне настроек для Twitter.

</Accordion>

<div id="do-the-account-owner-and-the-team-members-see-the-same-twitter-data" />

<Accordion title="Видят ли владелец аккаунта и участники команды одни и те же данные X Ads?">

Нет. Владелец учетной записи видит все учетные записи, связанные с Twitter. Члены команды видят только свои учетные записи, связанные с Twitter.

</Accordion>

<div id="how-do-i-disconnect-twitter-from-appsflyer" />

<Accordion title="Как отключить AppsFlyer от X Ads?">

Вы можете отключить AppsFlyer от вашей учетной записи Twitter. Инструкции ниже предполагают, что вы вошли в вашу учетную запись Twitter через браузер настольного компьютера или ноутбука.

1. Войдите в Twitter.
2. В меню слева выберите **More** (Дополнительно) > **Settings and Privacy** (Настройки и конфиденциальность).
3. Перейдите в раздел **Security and account access** (Безопасность и доступ к аккаунту) > **Apps and sessions** (Приложения и сеансы) > **Connected apps** (Подключенные приложения).
4. Выберите AppsFlyer.
5. Нажмите **Revoke Access** (Отозвать доступ).

Теперь вы можете вернуться в свой аккаунт AppsFlyer и при желании <Anchor target="_blank" href="/marketers/ru/docs/x-ads-formerly-twitter-ads-integration-setup">подключить другой аккаунт Twitter</Anchor>.

</Accordion>

<div id="is-it-possible-to-attribute-installs-to-multiple-twitter-accounts" />

<Accordion title="Можно ли атрибутировать установки для нескольких аккаунтов X Ads?">

Да, но для этого нужно выполнить некоторые действия в X Ads. Но сначала необходимы некоторые пояснения:

С аккаунтом AppsFlyer можно связать **только одно имя пользователя Twitter**. При связывании этого имени пользователя в настройках Twitter на дэшборде AppsFlyer появляется аккаунт X Ads.

Если у кого-либо из членов вашей команды также есть аккаунт X Ads, то имя пользователя Twitter этого члена команды будет отличаться от вашего, и они не смогут связать его с AppsFlyer. Это обусловлено тем, что **с аккаунтом AppsFlyer уже связано ваше имя пользователя Twitter**. Чтобы аккаунт X Ads другого члена команды также отображался в AppsFlyer, этот член команды должен **предоставить вашему имени пользователя Twitter доступ к соответствующему аккаунту X Ads на правах администратора**.

Допустим, в вашей команде работает Женя, которая использует имя пользователя Twitter @jenny. Вас зовут Ниви, ваше имя пользователя — @nivi, и это имя подключено к AppsFlyer. Чтобы аккаунт X Ads Жени появился в учетной записи AppsFlyer, **ей нужно предоставить вашему имени пользователя Twitter доступ к своему аккаунту X Ads на правах администратора**. Женя должна предоставить Ниви доступ к своему аккаунту X Ads, а не наоборот. Когда она это сделает, AppsFlyer увидит имя пользователя @nivi и все рекламные аккаунты, с которыми оно связано, в том числе аккаунт Жени.

1. Женя входит в учетную запись <Anchor target="_blank" href="http://ads.twitter.com/">ads.twitter.com</Anchor>.
2. Она нажимает пункт **Account** (Аккаунт) и выбирает **Edit access to account** (Изменить доступ к аккаунту).

   ![twitter_assign_account2.PNG](https://files.readme.io/cd2aa0b7a700fd0eee8754ac850adb99cc22b1c42d0d94f18d31ca71901ff31f-50903273809937.png)
3. Затем Женя предоставляет @nivi доступ к своему аккаунту X Ads на правах администратора (Account administrator).  

   [![twitter_edit_access_to_account.png](https://support.appsflyer.com/hc/article_attachments/49929519902993)](https://support.appsflyer.com/hc/article_attachments/49929523995665)
4. Дженни входит в аккаунт AppsFlyer и переходит в раздел Active Integrations >> X Ads
5. На этом этапе она видит в списке и свой аккаунт X Ads.
6. Теперь она видит свой аккаунт X Ads и может настроить интеграцию. Администратор аккаунта может видеть все подключенные аккаунты X Ads.

   Что видит Женя:

   ![jennys_ads_account.png](https://files.readme.io/73e3ca9be6090bfd47acb675e4faa634721d9aa75f5ebb8cf736fd56dd9e336b-50903273813137.png)

   Что видит администратор учетной записи:

   ![jennys_ads_account__1_.png](https://files.readme.io/d744c0e2de60011a0395a407607ec90f4fac04f76787b430cf1a74eda2342e66-50903273813649.png)

</Accordion>

<div id="any-special-instructions-for-agencies" />

<Accordion title="Нет ли каких-либо особых указаний для агентств?">

Есть.Есть.Когда агентство создает в Twitter новую кампанию, название кампании должно начинаться с имени агентства с символом подчеркивания (например: "AgencyName\_Campaign1").

> 📘 **Примечание**
>
> Чтобы установить связь между AppsFlyer и Twitter, рекламодатель ДОЛЖЕН выполнить настройки для Twitter, которые позволят агентствам использовать трафик в Twitter.

Подробные инструкции см. <Anchor target="_blank" href="/partners/ru/docs/about-agency-accounts#конфигурации-srn">здесь</Anchor>.

</Accordion>

<div id="do-you-make-twitters-raw-data-available-to-agencies" />

<Accordion title="Доступны ли агентствам сырые данные X Ads?">

Мы не предоставляем агентствам сырым данные Twitter, поскольку в их условиях обслуживания агентства рассматриваются как третьи стороны.

</Accordion>

<div id="im-clicking-save-close-but-twitters-configuration-is-not-saved-help" />

<Accordion title="Я нажимаю кнопку «Сохранить и закрыть», однако настройки для Twitter не сохраняются! Помогите!">

Если раньше приложение было связано с другим поставщиком атрибуции, который использовался для атрибуции установок из Twitter, при выполнении настроек для Twitter на панели управления AppsFlyer могут возникнуть описанные ниже ошибки:

**Error:  The app is associated with a different attribution provider. Please associate it with AppsFlyer.**

Кроме того, может произойти такая ошибка:  

[![](https://support.appsflyer.com/hc/article_attachments/49929523996561)](https://support.appsflyer.com/hc/article_attachments/49929523996561)

**Ошибка: При сохранении настроек для Twitter произошла ошибка. Некоторые аккаунты не удалось обновить: ХХ Несколько одинаковых идентификаторов поставщика (аppid, conversionType) для события appid2872.)**

Если выбор аккаунта не сохраняется, это может быть связано с тем, что аккаунт в Twitter, о котором идет речь, ранее был привязан в Twitter к другому поставщику. Для решения проблемы сделайте следующее:

* Обратитесь в X Ads с просьбой удалить со своей стороны другого поставщика
* Выберите имя активного аккаунта.
* Нажмите кнопку **Save and Close** (Сохранить и закрыть).
* Если проблема все еще не решена, вам придется попросить своего предыдущего поставщика измерений удалить из Twitter старые теги, связанные с вашим аккаунтом.

</Accordion>

<div id="how-can-i-set-up-retargeting-campaigns-with-twitter" />

<Accordion title="Как настроить ретаргетинговые кампании в X Ads?">

Подробные сведения о настройке ретаргетинговых кампаний в Twitter см. здесь.

</Accordion>

<div id="does-retargeting-affect-inapp-events-sending-to-twitter" />

<Accordion title="Влияет ли ретаргетинг на события в приложении, отправляемые в X Ads?">

Да. Если ретаргетинг активирован, AppsFlyer не отправляет по запросу Twitter постбэки событий af\_app\_opened.  
Обратите внимание, что при ретаргетинге постбэки событий af\_app\_opened не отправляются, даже если в окне настроек для Twitter можно выбрать такую возможность.

</Accordion>

<div id="how-can-i-stop-measuring-twitter-attributions" />

<Accordion title="Как прекратить измерение атрибуции X Ads?">

Чтобы отключить интеграцию с Twitter, снимите флажки для всех аккаунтов и нажмите кнопку **Сохранить и закрыть**.

</Accordion>

<div id="can-an-agency-measure-twitter-attributions-for-advertisers" />

<Accordion title="Может ли агентство измерять атрибуцию в Twitter от имени рекламодателей?">

Да!  
Чтобы установить подключение между AppsFlyer и Twitter, рекламодатель ДОЛЖЕН открыть дэшборд AppsFlyer и выбрать на странице партнера Twitter активный аккаунт. Флажок требуется установить хотя бы для одного аккаунта Twitter.  
Затем агентству необходимо установить подключение со своим аккаунтом Twitter непосредственно со своего дэшборда.

</Accordion>

<div id="can-an-agency-configure-inapp-events-for-twitter" />

<Accordion title="Может ли агентство выполнять для Twitter настройку внутренних событий приложения?">

Агентства не могут выполнять для Twitter настройку внутренних событий приложения. Так же как и настройки для Meta Ads, они должны выполняться рекламодателем.

</Accordion>

<div id="for-how-long-do-you-keep-twitter-s-userlevel-data" />

<Accordion title="Сколько времени вы храните пользовательские данные X Ads?">

Twitter требует от поставщиков атрибуции удалять свои данные уровня пользователей через 3 месяца после установки. Это означает, что события этих пользователей, которые произошли через 3 месяца после установки приложения, считаются органическими.

Агрегированные данные за прошлое время не изменяются.

</Accordion>

<div id="why-do-i-see-duplicated-cost-data" />

<Accordion title="Почему мои данные о затратах дублируются?">

Когда вы настраиваете кампанию в Twitter, вы можете добавить в кампанию несколько приложений. Когда Twitter сообщает о затратах, общие данные о затратах кампании отображаются в AppsFlyer под каждым приложением, но не делятся по приложениям.

Например, если вы запускаете одну кампанию, стоимость которой для приложений и Android и iOS составляет 1000 долларов, на дэшборде AppsFlyer отображаются затраты 1000 долларов и под приложением Android, и под приложением iOS. Затраты не разделяются на 500 долларов для каждого приложения.

Чтобы избежать дублирования данных о затратах, рекомендуется определять только одно приложение для каждой позиции / кампании.

</Accordion>

<div id="im-trying-to-link-my-twitter-account-with-appsflyer-but-i-get-an-error-message" />

<Accordion title="Я пытаюсь привязать мой аккаунт Twitter к AppsFlyer, но получаю сообщение об ошибке">

Чтобы получать данные атрибуции от AppsFlyer, ваш аккаунт Twitter должен быть активным рекламным аккаунтом.

**Чтобы решить эту проблему:**

1. Выйдите из Twitter.
2. В AppsFlyer в боковом меню выберите **Collaborate > Partner Integrations >** **Active Integrations.**
3. Найдите X Ads и выберите его. Откроется окно настройки партнера.
4. На вкладке **Integration** (Интеграция) нажмите **Activate partner** (Активировать партнера).
5. Нажмите **Login with X Ads**,  
   откроется окно входа в X Ads.
6. Войдите с данными вашего аккаунта X Ads.

</Accordion>

## Расхождения между X Ads и AppsFlyer

Хотя мы тесно сотрудничаем с X Ads, между дэшбордом X Ads и дэшбордом/отчетами AppsFlyer могут возникать расхождения.

Ниже приведены наиболее распространенные причины таких расхождений, о которых должны знать производители рекламы.

| Причина | Twitter | в AppsFlyer: |
| --- | --- | --- |
| **Окно атрибуции** | Twitter позволяет своим пользователям настраивать окно атрибуции и поддерживает оба вида атрибуции: по кликам и по просмотрам. По умолчанию для атрибуции по кликам установлено значение 14 дней, а для атрибуции по просмотрам — 1 день. | Если вы не настроили окно ретроспективной атрибуции AppsFlyer для X Ads с такими же значениями, как в X Ads, могут возникать расхождения. |
| **Атрибуция многоканальных источников** | Атрибуция X Ads функционирует, как указано выше, независимо от других источников. | AppsFlyer использует атрибуцию по последнему клику (подробные сведения об атрибуции в AppsFlyer см. <Anchor target="_blank" href="/marketers/ru/docs/appsflyer-attribution-model">здесь</Anchor>). |
| **Различия часового пояса** | Часовой пояс Twitter определяется часовым поясом, выбранным в приложении рекламодателя. | По умолчанию AppsFlyer использует часовой пояс GMT/UTC±00:00, однако рекламодатель может установить любой часовой пояс. |
| **Различия во времени установки** | X Ads показывает установки по времени клика (которое называется «время вовлечения»). | AppsFlyer отображает время первого запуска приложения. |
| **Типы атрибуции** | Атрибуция в X Ads основана на собственном учете кликов и показов. | В AppsFlyer атрибуция по кликам считается более приоритетной по сравнению с атрибуцией по просмотрам. Если в Twitter считаются показы, а AppsFlyer учитывает дополнительные клики в окне атрибуции по кликам, то клики от других источников атрибутируются на панели управления AppsFlyer. В Twitter показы атрибутируются и отображаются на панели управления. |
| **Настройки общего доступа к данным Twitter** | Twitter разрешает своим пользователям НЕ <Anchor target="_blank" href="https://twitter.com/settings/account/personalization">передавать свои персональные данные третьим лицам</Anchor>. К этим данным относится и реклама, с которой они взаимодействуют.<br /><br />Статистика на дэшборде X Ads отражает все вовлечения, включая пользователей, которые отказались делиться данными. | AppsFlyer отображает сводные данные этих пользователей Twitter, но не показывает необработанные данные на уровне отдельного пользователя (<Anchor target="_blank" href="/marketers/ru/docs/x-ads-formerly-twitter-ads-setup-guide-overview#конфиденциальность-пользователей-xads">подробная информация</Anchor>). |
| **Логика повторного вовлечения в X Ads** | Twitter подсчитывает количество уникальных пользователей. Если в рамках одной кампании пользователь вовлекается повторно более одного раза, Twitter засчитывает это как одну конверсию. | AppsFlyer подсчитывает количество повторных вовлечений, поэтому в подобном случае засчитывает такие повторные вовлечения как несколько конверсий. |

> 📘 **Примечание**
>
> В результате применения <Anchor target="_blank" href="/marketers/ru/docs/implement-validation-rules-to-prevent-fraud">Правил проверки AppsFlyer</Anchor> данные на панелях управления могут отличаться, поскольку некоторые установки, которые отображаются в Twitter, не отображаются на панели управления AppsFlyer.

<div data-zendesk-anchors="twitter-ads-faq-and-discrepancies=%D1%85-ads-%D1%87%D0%B0%D1%81%D1%82%D0%BE-%D0%B7%D0%B0%D0%B4%D0%B0%D0%B2%D0%B0%D0%B5%D0%BC%D1%8B%D0%B5-%D0%B2%D0%BE%D0%BF%D1%80%D0%BE%D1%81%D1%8B-%D0%B8-%D1%80%D0%B0%D1%81%D1%85%D0%BE%D0%B6%D0%B4%D0%B5%D0%BD%D0%B8%D1%8F h_01HE7S15F9YR28FBA1TYCE3N0X=%D1%85-ads-%D1%87%D0%B0%D1%81%D1%82%D0%BE-%D0%B7%D0%B0%D0%B4%D0%B0%D0%B2%D0%B0%D0%B5%D0%BC%D1%8B%D0%B5-%D0%B2%D0%BE%D0%BF%D1%80%D0%BE%D1%81%D1%8B-%D0%B8-%D1%80%D0%B0%D1%81%D1%85%D0%BE%D0%B6%D0%B4%D0%B5%D0%BD%D0%B8%D1%8F h_01HE7S15F9NSQJSP268B0WF0JP=who-can-perform-the-twitter-setup-on-appsflyer h_01HE7S15F9PFZ8CATJC5YWC6QP=what-happens-if-no-twitter-accounts-are-selected-for-attributing-on-appsflyer h_01HE7S15F989Y94YFJ7TGK7QN5=do-the-account-owner-and-the-team-members-see-the-same-twitter-data h_01HE7S15F9GNWTK2N50GAHN52Q=how-do-i-disconnect-twitter-from-appsflyer h_01HE7S15F9CE4F29R97EVCG791=is-it-possible-to-attribute-installs-to-multiple-twitter-accounts h_01HE7S15F9G4M44CB2Q1KQMJPJ=any-special-instructions-for-agencies h_01HE7S15F9VG8XMJE7YSNN245P=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%87%D0%B0%D0%BD%D0%B8%D0%B5 h_01HE7S15F9A7BBAW8BNN6H4AKQ=do-you-make-twitters-raw-data-available-to-agencies h_01HE7S15F9MM26SGKMAPGDH9F8=im-clicking-save-close-but-twitters-configuration-is-not-saved-help h_01HE7S15F923NKTTCS3Z1C40B5=how-can-i-set-up-retargeting-campaigns-with-twitter h_01HE7S15F931EWS48QVCQYPBCH=does-retargeting-affect-inapp-events-sending-to-twitter h_01HE7S15F98VN1TS99751S34C5=how-can-i-stop-measuring-twitter-attributions h_01HE7S15F9MEKBKAQ3NA76TFKY=can-an-agency-measure-twitter-attributions-for-advertisers h_01HE7S15F921V3T885F39VSPCQ=can-an-agency-configure-inapp-events-for-twitter for-how-long-do-you-keep-twitter%E2%80%99s-userlevel-data=for-how-long-do-you-keep-twitter-s-userlevel-data h_01HE7S15F90RXSWJ7HV3GSJB65=for-how-long-do-you-keep-twitter-s-userlevel-data h_01HE7S15F9B39KV628NSD29P6P=why-do-i-see-duplicated-cost-data h_01HE7S15F9N3CCJEMAD2QB38F9=im-trying-to-link-my-twitter-account-with-appsflyer-but-i-get-an-error-message discrepancies-between-twitter-and-appsflyer=%D1%80%D0%B0%D1%81%D1%85%D0%BE%D0%B6%D0%B4%D0%B5%D0%BD%D0%B8%D1%8F-%D0%BC%D0%B5%D0%B6%D0%B4%D1%83-x-ads-%D0%B8-appsflyer h_01HE7S15F9YWCY883DP9TEGQXK=%D1%80%D0%B0%D1%81%D1%85%D0%BE%D0%B6%D0%B4%D0%B5%D0%BD%D0%B8%D1%8F-%D0%BC%D0%B5%D0%B6%D0%B4%D1%83-x-ads-%D0%B8-appsflyer h_01HE7S15FAPS2696J3KQG3P3ME=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%87%D0%B0%D0%BD%D0%B8%D0%B5-1" />
