---
title: '[Устарело] Скрипт атрибуции целевой страницы для мобильных устройств'
deprecated: true
metadata:
  keywords:
    - Landing Page
    - Facebook
    - Adwords
    - Advertisers
    - Agencies
    - GCLID
    - Developers
    - Marketers
    - Smart Banners and Scripts
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-asaf-mashiah
    - Marketers
    - Agencies
    - Smart Banners and Scripts
  created_at: '2020-12-16T17:28:55Z'
  edited_at: '2026-09-02T00:33:52Z'
  id: 360016643258
  locale: ru
  section: Web-to-app attribution
  section_id: 6551240476177
  url: https://support.appsflyer.com/hc/ru/articles/360016643258
---
> **Краткий обзор.** Этот скрипт устарел с 17 декабря 2020 г. и заменен <Anchor target="_blank" href="/marketers/ru/docs/onelink-smart-script-overview">смарт-скриптом OneLink</Anchor>. Эта версия продолжает работать, но не будет обновляться или изменяться. Скрипт генерирует URL-адреса, встроенные в кнопку на вашем мобильном веб-сайте, и перенаправляет посетителей к загрузке вашего приложения. URL-адреса также поддерживают атрибуцию установок и диплинкинг.

![5648_Sunset_and_deprecation-01.png](https://files.readme.io/f2a154145e26577b698d00c4c3719be3eea7298576e6883bd47e6fb42897c71a-360015062398.png)

**<Anchor target="_blank" href="/marketers/ru/docs/onelink-smart-script-overview">Переход на смарт-скрипт OneLink</Anchor>**

Целевые страницы широко используются цифровыми маркетологами. Они позволяют маркетологам собирать информацию о потенциальных клиентах для ремаркетинга, даже если эти пользователи сначала не совершают конверсии.

Однако для привлечения мобильных пользователей использование целевой страницы имеет свои плюсы и минусы.

#### Плюсы:

* Лиды, которые в конечном итоге установят приложение, должны активнее вовлекаться с приложением.
* Более сложные сервисы (например, финансовые услуги) требуют дополнительных объяснений для конверсии лидов, чему способствуют целевые страницы.

#### Недостатки:

* Более длинная воронка уменьшает конечное количество конвертированных лидов.
* Атрибутировать технически сложнее.

## Сложности мобильной атрибуции на целевых страницах

* **Разные медиа-источники требуют разных методов** для заполнения сценария целевой страницы правильными данными атрибуции.
* **Модель атрибуции по последнему клику может привести к потере правильных данных атрибуции**, если на целевой странице есть собственные ссылки атрибуции.
* **Прямые посетители веб-сайта считаются органическими**, если на целевой странице нет собственных ссылок атрибуции.
* **Посетители с настольных компьютеров учитываются как органические**, если на целевой странице не предусмотрен метод регистрации их конверсий в мобильных пользователей.

## Решение

Чтобы решить указанные проблемы с атрибуцией целевой страницы, вам необходимо реализовать на целевой странице поток javascript. Мы предлагаем пример реализации скрипта, который вы можете использовать. Обязательно настройте скрипт в соответствии со своими требованиями.

В некоторых случаях вам также необходимо внести некоторые коррективы в кампании.

Приведенные ниже сценарии охватывают требования ко всем возможным случаям использования медиа-источников.

## Сценарии целевой страницы

Следуйте приведенным ниже инструкциям **для всех медиа-источников**, отправляющих лидов на ваши целевые страницы.

<div id="facebook-ads-crossplatform-attribution" />

<Accordion title="Meta ads: кроссплатформенная атрибуция">

#### Описание:

Meta-ads — это SRN (сеть с самостоятельной атрибуцией) и не использует внешние ссылки атрибуции.

При первом запуске приложения AppsFlyer запрашивает в Meta ads, взаимодействовал ли пользователь ранее (в течение последних 28 дней) с объявлением рекламодателя в приложении Facebook. Если да, Meta ads выполняет атрибуцию самостоятельно.

Meta ads также подразумевает кроссплатформенность, а это означает, что пользователь может взаимодействовать с кампаниями любого типа, мобильными и другими, на любой платформе, и при этом Meta ads выполняет атрибуцию самостоятельно.

#### Вывод:

Лид с доступным идентификатором устройства, попавший из приложения Facebook на целевую страницу, правильно атрибутируется к Meta ads. Это происходит независимо от нового клика, зарегистрированного на целевой странице.  
Однако если пользователи решат не предоставлять идентификатор своего устройства, как это ожидается с пользователями iOS 14 в 2021 году, кроссплатформенная атрибуция Meta Ads может перестать работать.

**Когда предоставление идентификатора устройства станет необязательным, используйте [метод других SRN](/docs/deprecated-mobile-landing-page-attribution-script#other-srns-add-parameter) для Meta ads.**

* Новые пользователи, которые предоставят свой идентификатор устройства, будут правильно атрибутированы к Meta ads.
* Новые пользователи, которые не предоставят свой идентификатор устройства, будут атрибутированы к «Facebook\_LP».

#### Инструкции

1. В своем аккаунте Meta ads создайте **кампанию с целью «Трафик» или «Конверсии» с включенной мобильной атрибуцией**, отправляя лидов на целевую страницу.
2. Кнопка загрузки целевой страницы на Android — прямая ссылка на Google Play.
3. Кнопка загрузки целевой страницы iOS — прямая ссылка на iTunes (ИЛИ ссылка атрибуции **без идентификатора устройства**).

#### Что делает скрипт

Скрипт целевой страницы не вносит изменений. Скрипт предназначен для обнаружения пользователя, пришедшего из приложения Facebook. Если это так, скрипт ничего не делает. На целевой странице остаются прямые ссылки на магазины приложений в том виде, в каком они есть. Это предотвращает запись еще одного клика, что может повлиять на CTR.

В скрипте найдите метод ***isFacebook()***, чтобы узнать больше о том, что делает скрипт, когда пользователь приходит из приложения Facebook.

</Accordion>

<div id="google-ads-gclid-offline-conversion-upload" />

<Accordion title="Google Ads: GCLID + загрузка конверсий в автономном режиме">

#### Описание:

Обычный процесс атрибуции установок в кампаниях Google Ads требует перенаправления лидов по кликам на URL страницы магазина приложения.

Поэтому при перенаправлении лидов из Google Ads на целевую страницу используйте посредника, чтобы связать установку с мобильного устройства и первоначальный клик в кампании Google Ads не для мобильных устройств.

#### Вывод:

Решение для Google Ads состоит из двух частей.

Первая часть — это **атрибуция в AppsFlyer** мобильных пользователей, которые переходят на целевую страницу из Google и устанавливают приложение оттуда. Для этого необходимо пометить URL-адреса кликов из Google, идентифицировать их на целевой странице и создать динамическую ссылку OneLink с данными из URL-адреса.

Вторая часть — **уведомление Google Ads** об этих мобильных установках с помощью метода загрузки конверсий Google в автономном режиме.

> 📘 **Примечание**
>
> Это решение GCLID официально не поддерживается и не рекомендуется компанией Google.
> В случае, если Google прекратит использование параметра GCLID, мы изменим скрипт в соответствии с изменениями.
> Мы рекомендуем следить за этой статьей, нажав кнопку ***Подписаться*** в заголовке статьи, чтобы получать информацию об обновлении статьи или прикрепленного скрипта.

#### Инструкции

Часть 1. Атрибуция к Google Ads в AppsFlyer

На панели управления Google **включите автоматическую пометку** (<Anchor target="_blank" href="https://support.google.com/analytics/answer/1033981?hl=en">вот как это сделать</Anchor>).

Если автоматическая пометка включена, **URL-адрес целевой страницы содержит параметр *GCLID***.

Пример URL-адреса: `http://www.yoursite.com/yourlandingpage?gclid={USER_GCLID}`

На вашей целевой странице —

1. Активируйте функцию Javascript ***generateUrl***
2. Функция (см. ниже) ищет параметр ***GCLID*** и создает длинный URL-адрес OneLink, содержащий его значение в параметре af\_sub1 (можно использовать любой из <Anchor target="_blank" href="/marketers/ru/docs/about-link-structure-and-parameters#what-are-subscriber-parameters-good-for">параметров подписчика</Anchor> af\_sub1 – af\_sub5).
3. Кнопка загрузки на целевой странице использует сгенерированный URL-адрес OneLink.  
   Пример URL-адреса OneLink: `https://yourapp.onelink.me/abcd?pid=google_lp&c={CAMPAIGN_NAME}&af_sub1={USER_PARSED_GCLID}`
4. Новые мобильные пользователи атрибутируются к медиа-источнику **google\_lp** и кампании CAMPAIGN\_NAME (опционально).
5. В медиа-источник постбэки не отправляются.

На данный момент об установках сообщается в AppsFlyer в медиа-источнике ***google\_lp*** с использованием GCLID, но не в Google Ads.

Часть 2. Загрузка установок в Google в виде офлайн-конверсий

**Этот шаг необходим только в том случае, если вы хотите, чтобы конверсии записывались на платформе Google Ads.**

Для пользователей, атрибутированных к google\_lp, в сырых данных AppsFlyer теперь отображается значение GCLID в столбце **af\_sub1**. GCLID необходим для загрузки офлайн-конверсий в Google Ads, более подробную информацию об этом процессе можно найти <Anchor target="_blank" href="https://support.google.com/adwords/answer/7014069">здесь</Anchor>).

Конверсии можно загрузить вручную или через API Adwords (подробнее об этом API <Anchor target="_blank" href="https://developers.google.com/adwords/api/docs/guides/conversion-tracking#importing_conversions">можно узнать здесь</Anchor>).

Можно экспортировать CSV с этой информацией из вашего аккаунта AppsFlyer или получать эти данные через Push API в режиме реального времени при каждой установке.

> 👍 **Совет**
>
> Вы также можете видеть ключевые слова, которые искали пользователи, в сырых данных AppsFlyer, аналогично тому, как при получении GCLID:
>
> 1. Для записи ключевых слов вы должны включить параметр <Anchor target="_blank" href="https://support.google.com/google-ads/answer/2375447">keyword ValueTrack</Anchor> в конечный URL-адрес от Google Ads на целевую страницу
>    Пример URL-адреса: `http://www.yoursite.com/yourlandingpage?gclid={USER_GCLID}&keyword={USER_KEYWORD}`
> 2. Функция Javascript (см. ниже) ищет параметр ***keyword***
> 3. Значение добавляется к сгенерированному URL-адресу OneLink в параметре af\_keywords
>    Пример URL-адреса OneLink: `https://yourapp.onelink.me/abcd?pid=google_lp&c={CAMPAIGN_NAME}&af_sub1={USER_PARSED_GCLID}&af_keywords={USER_PARSED_KEYWORD}`
>
> Приведенная ниже функция JS уже содержит код для анализа параметра ключевого слова.

#### Что делает скрипт

Google Ads содержит параметр gclid. Скрипт ищет этот параметр в URL-адресе целевой страницы. Если находит, то создает ссылку OneLink, отражающую, что пользователь пришел из Google Ads. Затем скрипт помещает OneLink в качестве ссылки в кнопке загрузки на целевой странице.

В скрипте найдите **gclidValue**, чтобы узнать, как скрипт обнаруживает пользователей, приходящих из Google Ads, и соответствующим образом создает OneLink.

</Accordion>

<div id="other-srns-add-parameter" />

<Accordion title="Другие SRN: добавить параметр">

#### Описание:

Другие <Anchor target="_blank" href="/marketers/ru/docs/self-reporting-networks-srns#srn-интегрированные-с-appsflyer">SRN</Anchor>, например Snapchat или Twitter, не являются кроссплатформенными, как Meta ads, и для того, чтобы атрибутировать к ним пользователей мобильных устройств, потребуется немного потрудиться.

Ваши кампании с другими SRN приводят ваших пользователей на целевую страницу, и вам выставляют счета в соответствии с количеством переходов по ссылкам, что не связано с количеством мобильных пользователей.

#### Вывод:

При определении URL-адреса целевой страницы для кампании в SRN (кроме Meta Ads и Google Ads) добавьте к URL-адресу параметр идентификатора партнера (Partner ID), в котором указана исходная SRN.  
На целевой странице запускается код JavaScript (см. ниже), который анализирует этот параметр и создает URL-адрес OneLink со значением Partner ID. Когда пользователи мобильных устройств нажимают на эту ссылку OneLink и устанавливают приложение, они атрибутируются к указанному медиа-источнику.

#### Инструкции

В вашем аккаунте SRN:

1. Создайте немобильную кампанию
2. При определении URL-адреса целевой страницы добавьте к URL-адресу параметр Partner ID + целевая страница (который не является ссылкой атрибуции AF). Формат: ***&af\_pid=srn\_lp*** (см. пример ниже). (см. приведенные ниже примеры)

На вашей целевой странице —

1. Активируйте функцию Javascript ***generateUrl***
2. Функция ищет параметр ***af\_pid*** и создает URL-адрес OneLink, содержащий его значение в параметре ***pid***
3. Кнопка загрузки на целевой странице использует сгенерированный URL-адрес OneLink.
4. Новые мобильные пользователи атрибутируются к пользовательскому медиа-источнику «Partner ID + landing page» (Идентификатор партнера + целевая страница).
5. В медиа-источник постбэки не отправляются.

Если вы укажете настоящее имя SRN, например twitter\_int, в эту SRN может быть отправлен постбэк. Это может привести к двойным расходам. Альтернативные названия см. в примечании ниже.

Сам скрипт содержит логику, запрещающую использовать эти названия. Найдите в скрипте `var SRNs`. Вы должны увидеть список названий SRN и условие, проверяющее, содержит ли `pidValue` какое-либо из этих названий. Удалите эту логику после завершения тестирования скрипта.

> 📘 **Примечание**
>
> Если вы отправляете пользователей на целевую страницу, мы рекомендуем включить следующий параметр в URL-адрес целевой страницы:
>
> * Для Твиттера используйте «***&af\_pid=twitter\_lp***»
> * Для Snapchat используйте «***&af\_pid=snapchat\_lp***»
> * Для Doubleclick используйте «***&af\_pid=doubleclick\_lp***»
> * Для публикаций в Meta ads (бесплатных) используйте «***&af\_pid=fbpost\_lp***»
> * Для Oath (ранее Yahoo Gemini) используйте «***&af\_pid=oath\_lp***»

#### Что делает скрипт

Скрипт видит параметр af\_pid в URL-адресе целевой страницы и приходит к выводу, что пользователь является пользователем SRN или другой настраиваемой сети. Скрипт соответствующим образом создает ссылку OneLink и устанавливает ее в качестве ссылки в кнопке загрузки на целевой странице.

Чтобы узнать больше о том, что делает скрипт, найдите в скрипте значение **pidValue**.

</Accordion>

<div id="attribution-links-redirect-with-af_r" />

<Accordion title="Ссылки атрибуции: перенаправление с помощью af_r">

#### Описание:

Ссылки атрибуции используются для любого медиа-источника, который не является SRN. Сюда входят тысячи интегрированных партнеров и любые собственные медиа, которые вы хотите указать.

К счастью, решение для атрибуции целевой страницы при использовании ссылок атрибуции AppsFlyer простое (и аналогично решению для Meta ads).

#### Вывод:

ссылка атрибуции перенаправляет лида на целевую страницу и тем самым обеспечивает правильную атрибуцию (если после этого будет установлено мобильное приложение).

Осталось только НЕ препятствовать правильной атрибуции другим последним кликом.

#### Инструкции

1. <Anchor target="_blank" href="/marketers/ru/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#создание-ссылки-onelink">Создайте ссылку атрибуции</Anchor> для медиа-источника.
2. Добавьте в нее <Anchor target="_blank" href="/marketers/ru/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#redirection">параметр целевой страницы</Anchor>, ведущий на целевую страницу.
3. Добавьте `&af_redirect=true` в значение целевой страницы в **любых параметрах перенаправления** (например, af\_r, af\_ios\_url и af\_android\_url) в ссылке атрибуции.  
   Пример: `https://yourapp.onelink.me/abcd?pid=email&c={CAMPAIGN_NAME}&af_r=http://www.yoursite.com/yourlandingpage?af_redirect=true`
4. **Необязательно**: добавьте идентификатор устройства (GAID/IDFA) в ссылку атрибуции, чтобы разрешить атрибуцию путем сопоставления идентификаторов вместо вероятностного моделирования
5. Кнопка загрузки на целевой странице на Android — прямая ссылка на Google Play.
6. Кнопка загрузки на целевой странице на iOS — прямая ссылка на iTunes  

   > 📘 **Примечание**
   >
   > Скрипт и образец HTML предоставляют возможность настроить одну кнопку загрузки, которая подходит как для Android, так и для iOS. Прочитайте комментарии к скрипту, чтобы узнать, как его реализовать.


#### Что делает скрипт

Скрипт ищет параметр **af\_redirect** в URL-адресе целевой страницы. Если находит, то не вносит никаких изменений в кнопки загрузки на целевой странице. Это связано с тем, что параметр af\_redirect указывает, что пользователь попадает на целевую страницу после клика. Таким образом, нет необходимости в дополнительных ссылках атрибуции.

Подробнее о том, как скрипт обрабатывает случаи, когда пользователи попадают на целевую страницу после клика по ссылке атрибуции, см. метод **isAFLink()** в скрипте.

</Accordion>

<div id="links-with-utm-parameters-dynamic-onelink" />

<Accordion title="Ссылки с параметрами utm: динамическая ссылка OneLink">

#### Описание

У вас могут быть источники трафика, которые перенаправляют пользователей на вашу целевую страницу по ссылкам с параметрами UTM.

#### Вывод:

Если исходный URL-адрес НЕ является ссылкой атрибуции AppsFlyer, скрипт ищет в ссылке параметры ***utm\_source*** и ***utm\_campaign***. Если они есть, скрипт подготавливает URL-адрес OneLink, в котором они используются в качестве названия медиа-источника (pid) и названия кампании (c) соответственно.

Обратите внимание, что в ссылках атрибуции AppsFlyer, которые также содержат параметры UTM, используются параметры AppsFlyer, а не параметры UTM.

#### Инструкции

В медиа-источнике:

1. Убедитесь, что в ссылке есть ***utm\_source***.
2. Параметр ***utm\_campaign*** необязателен, но настоятельно рекомендуется.

На вашей целевой странице —

1. Активируйте функцию Javascript ***generateUrl***
2. Функция ищет параметры ***utm\_source и ***utm\_campaign** и создает URL-адрес OneLink, содержащий их значения.
3. Кнопка загрузки на целевой странице использует сгенерированный URL-адрес OneLink.
4. Новые мобильные пользователи атрибутируются к значению ***utm\_source*** в качестве медиа-источника.
5. В медиа-источник постбэки не отправляются.

#### Что делает скрипт

Скрипт ищет параметры UTM в URL-адресе целевой страницы. Если они обнаружены, скрипт преобразует их в параметры OneLink. Таким образом, информация о кампании передается в окончательную атрибуцию.

</Accordion>

<div id="mobile-organic-visitors-onelink-with-pidwebsite" />

<Accordion title="Мобильные органические посетители: OneLink, где pid=website">

#### Описание

Органические мобильные посетители — это, по определению, прямые посетители из неизвестных источников в мобильном интернете. Они редко посещают специальные целевые страницы, но, возможно, подавляющее большинство мобильных установок приходит с веб-сайта рекламодателя.

#### Вывод:

Если с вашего веб-сайта поступает значительное количество органического мобильного трафика, настоятельно рекомендуется записывать данные атрибуции вашего собственного трафика.

#### Инструкции

Для атрибуции органических мобильных посетителей на веб-сайте должны быть кнопки ***загрузки*** или ***установки***, а в них — ссылка атрибуции OneLink. OneLink позволяет диагностировать тип устройства и перенаправлять лидов в соответствующий магазин приложений.

Чтобы узнать, как настраивать и создавать URL-адреса OneLink, перейдите <Anchor target="_blank" href="/marketers/ru/docs/create-a-onelink-template">по этой ссылке.</Anchor>

> 👍 **Совет**
>
> Добавьте «&pid=website» к ссылке атрибуции, чтобы атрибутировать всех этих посетителей к вашему сайту.
> На каждой странице вашего сайта, на которой есть кнопка загрузки/установки со ссылкой атрибуции, добавьте «&c=`{PAGE NAME}`». Это поможет вам найти страницы с самой высокой и самой низкой конверсией на вашем сайте.

#### Что делает скрипт

Исчерпав все остальные опции, скрипт определяет, что пользователь является органическим пользователем, не участвовавшим в какой-либо кампании. Скрипт создает ссылку OneLink, которая отражает это и помещает ее в качестве ссылки в кнопку загрузки на целевой странице.

</Accordion>

<div id="desktop-visitors-telephoneemail-form" />

<Accordion title="Посетители с настольных компьютеров: форма для телефона или электронной почты">

#### Описание

Все описанные выше варианты предполагают, что пользователи используют мобильные устройства при взаимодействии с кампанией и целевой страницей.

Но как насчет пользователей настольных компьютеров?

Пользователи настольных компьютеров могут зайти на вашу целевую страницу или на сайт, а затем «самостоятельно» посетить магазин приложений со своих мобильных устройств и установить мобильное приложение. Без предварительного взаимодействия с мобильными устройствами невозможно атрибутировать этих пользователей, поэтому их относят к «органическим».

#### Вывод:

Отличным решением этой проблемы с атрибуцией является использование **формы «из СМС к скачиванию» на целевой странице** только для пользователей настольных компьютеров. После этого необходимо отправить на мобильное устройство СМС или электронное письмо с URL-адресом OneLink.

#### Инструкции

1. Определите, что посетитель является пользователем настольного компьютера.
2. Когда пользователь вводит в форму свой номер телефона, отправьте ему текстовое сообщение со ссылкой на ваше приложение с коротким URL-адресом OneLink. Вы также можете запросить у него адрес электронной почты, чтобы отправить письмо для загрузки приложения.
3. Использование OneLink здесь имеет решающее значение, поскольку платформа мобильного устройства при отправке сообщения пользователю неизвестна. Функции диагностики и перенаправления OneLink позаботятся об этом за вас.
4. Добавьте «&pid=desktop\_website» к URL-адресу OneLink, чтобы идентифицировать этот источник.
5. Добавьте «&c=`{PAGE NAME}`», чтобы найти страницы с самой высокой и низкой конверсией на вашем сайте для пользователей настольных компьютеров.

#### Что делает скрипт

Скрипт определяет устройство или платформу, на которой находится пользователь. Если это настольный компьютер, скрипт возвращает ссылку на URL-адрес веб-формы и помещает ее в кнопки загрузки. Когда пользователь нажимает кнопку «Загрузить», он отправляется в веб-форму, где заполняет свои данные, чтобы получить SMS или электронное письмо со ссылкой для загрузки приложения.

Вы сами должны создать веб-форму и указать ее URL в скрипте. Чтобы узнать больше, найдите **isMobileDevice()** в скрипте.

</Accordion>

## javascript целевой страницы

Ниже представлена реализация кода javascript, который выполняет полный спектр атрибуции медиа-источников и кампаний в сценариях использования целевых страниц. **Если вы хотите получать дополнительные данные, такие как идентификаторы групп объявлений и отдельных объявлений, вам следует внести в скрипт необходимые корректировки**.

Для вашего удобства вы также можете скачать прилагаемый пример целевой страницы.

В разделе кода вы найдете инструкции по его адаптации к потребностям вашей целевой страницы.

<div id="the-script" />

<Accordion title="Скрипт">

Перед реализацией скрипта учтите следующее:

* Скрипт приведен только в качестве примера. Он охватывает общую целевую страницу и поток атрибуции. Адаптируйте скрипт в соответствии со своими требованиями.
* Скрипт ищет определенные параметры в URL-адресе целевой страницы, такие как медиа-источник, кампания, ключевые слова и т. д. Если вы хотите добавить дополнительные параметры, такие как идентификатор сайта и группы объявлений, вам необходимо соответствующим образом изменить скрипт. Если вы хотите добавить дополнительные параметры, такие как идентификатор сайта и группы объявлений, вам необходимо соответствующим образом изменить скрипт.

```javascript
// Возвращает значение параметра, присутствующего в URL-адресе страницы, или ' ', если он не существует.
function getParameterFromURL(name, url) {
  if (!url) url = window.location.href;
  name = name.replace(/[\[\]]/g, '\\$&');
  var regex = new RegExp('[?&]' + name + '(=([^&#]*)|&|#|$)'),
    results = regex.exec(url);
  if (!results) return null;
  if (!results[2]) return '';
  return decodeURIComponent(results[2].replace(/\+/g, ' '));
}

function isMobileDevice() {
  return (typeof window.orientation !== "undefined") || (navigator.userAgent.indexOf('IEMobile') !== -1);
}

function getMobileOperatingSystem() {
  var userAgent = navigator.userAgent || navigator.vendor || window.opera;
  if (userAgent) {
    if (/android/i.test(userAgent)) {
      return "Android";
    }

    // iOS detection from: http://stackoverflow.com/a/9039885/177710
    if (/iPad|iPhone|iPod/.test(userAgent) && !window.MSStream) {
      return "iOS";
    }
  }
  return "unknown";
}

function isAFLink() {
  return getParameterFromURL('af_redirect');
}

// Note - when device ID sharing becomes optional stop calling this method (or always return false)
function isFacebook() {
  if (document.referrer && document.referrer != "") {
    return document.referrer.toLowerCase().includes('facebook');
  } else {
    return false;
  }
}

// generateUrl returns the URL to use behind the iOS and Android "Download" buttons on a landing page, based on the source of the page visitor.
// По умолчанию эти кнопки должны вести на страницы приложений в iTunes и Google Play.
// Если эти ссылки нужно оставить без изменений, generateUrl возвращает ' '.
// В противном случае generateUrl возвращает URL-адрес, который будет использоваться для ОБЕИХ кнопок (в этом случае также можно использовать одну кнопку для загрузки приложения).
// Параметры: isDebug — если true, для каждого из кейсов выводятся оповещения, в противном случае — нет.  	 
function generateUrl(isDebug) {
  var oneLinkURL = 'https://yourapp.onelink.me/abcd';   // **** Replace with your own basic OneLink URL ****
  var webFormURL = 'https://yoursite.com/webform.html'; // **** Replace with your own web form URL for getting the user's email or SMS ****
  var finalURL = "";
  var partnerIDParam = '?pid=';

  var campaignValue;
  if (getParameterFromURL('c')) {
    campaignValue = getParameterFromURL('c');
  } else if (getParameterFromURL('utm_campaign')) {
    campaignValue = getParameterFromURL('utm_campaign');
  } else if (document.getElementsByTagName('title')[0]) {
    campaignValue = document.getElementsByTagName('title')[0].innerText;
  } else {
    campaignValue = 'unknown';
  }
  var campaignParam = '&c=';
  var gclidParam = '&af_sub1=';
  var gclidValue = getParameterFromURL('gclid');
  var kwParam = '&af_keywords=';
  var pidValue;
  var kwValue = getParameterFromURL('keyword');

  if (getParameterFromURL('af_pid')) {
    pidValue = getParameterFromURL('af_pid');
  } else if (getParameterFromURL('utm_source')) {
    pidValue = getParameterFromURL('utm_source');
  }

  // Prevent the use of real SRN names. Удалите эту часть после завершения тестирования скрипта.
    var SRNs = [
    'twitter_int',
    'facebook_int',
    'snapchat_int',
    'doubleclick_int',
    'yahoogemini_int',
    'yahoojapan_int',
  ];

  if (SRNs.includes(pidValue)) {
  	alert("DO NOT USE NAMES OF SRNS IN af_pid or utm_source - use the names listed in Other SRNs: Add Parameter section in the landing page article\nhttps://support.appsflyer.com/hc/en-us/articles/360000677217#other-srns-add-parameter");
    return;
  }

  // Desktop user
  if (!isMobileDevice()) {
    return webFormURL;
  }

  // User was redirected using af_r parameter on an AppsFlyer attribution link
  if (isAFLink()) {
    if (isDebug) {
      alert("This user comes from AppsFlyer by redirection and is ready to be attributed. \nKeep direct app store links.");
    }
    return; // in this case, the original store links in the install buttons stay the same

    /*
    If you want one install button in the landing page that serves both iOS and Android, uncomment the code below
    The code identifies the operating system and returns the relevant direct link to Google Play or iTunes

    if (getMobileOperatingSystem() === 'Android') {
      return 'direct link to Google Play';
    } 

    if (getMobileOperatingSystem() === 'iOS') {
      return 'direct link to iTunes';
    }
    */
  }

  // Google Ads
  if (gclidValue) {
    partnerIDParam += 'google_lp';
    campaignParam += campaignValue;
    gclidParam += gclidValue
    if (!kwValue) {
      finalURL = oneLinkURL + partnerIDParam + campaignParam + gclidParam;
      if (isDebug) {
        alert("This user comes from Google AdWords\n " + finalURL);
      }
      return finalURL;

    } else { // Google Ads with KW
      kwParam += kwValue;
      finalURL = oneLinkURL + partnerIDParam + campaignParam + gclidParam + kwParam;
      if (isDebug) {
        alert("This user comes from Google AdWords - there is a keyword associated with the ad\n " + finalURL);
      }
      return finalURL;
    }

  // Other SRNs and custom networks  
  } else if (pidValue) {
    campaignParam += campaignValue;
    partnerIDParam += pidValue;
    finalURL = oneLinkURL + partnerIDParam + campaignParam;
    if (isDebug) {
      alert("This user comes the SRN or custom network " + pidValue + "\n" + finalURL);
    }
    return finalURL;
  } else if (isFacebook()) {
    if (isDebug) {
      alert("This user comes from a paid Facebook ad - don't do anything. \nKeep direct app store links.");
    }
    return ' ';

  } else { // organic mobile user
    campaignParam += campaignValue;
    partnerIDParam += 'website'; //**** Replace value if you wish organic users to be attributed to another media source than 'website' ****
    finalURL = oneLinkURL + partnerIDParam + campaignParam;
    if (isDebug) {
      alert("This user comes from an unknown mobile source.\n The user would be attributed to media source 'website' and to the campaign " + campaignParam + "\n" + finalURL);
    }
    return finalURL;
  }
}
```

</Accordion>

<div id="html-sample-for-landing-page" />

<Accordion title="Пример HTML для целевой страницы">

```html Markup
<html>
<head>
  <title>Landing Page</title>
</head>
<body>
  <h1>Landing Page</h1>
  <!-- By default, the install buttons should have direct links to the stores -->
  <div>
    <a id="andrd_link" href="https://play.google.com/store/apps/details?id=com.appsflyer.sampleapp"><img src="/images/andrd.png"alt=""></a>
  </div>
  <div>
    <a id="ios_link" href="https://itunes.apple.com/us/app/id3********"><img src="/images/ios.png" alt=""></a>
  </div>
  <!-- If you want one button to serve both Android and iOS, use the code below instead
  <a id="store_link" href=""><img src="download.png" alt=""></a>
  -->
  <script type="text/javascript" src="/landing-page-test.js"></script>
  <script type="text/javascript">
    window.onload = function () {
      var url = generateUrl(true);

      // onelink is generated
      if (url) {
        document.getElementById('andrd_link').setAttribute('href', url);
        document.getElementById('ios_link').setAttribute('href', url);
      }

      //otherwise, if onelink is not generated it means that the user is redirected
      // and the store links in the buttons stay the same

      /* for the one button solution for both Android and iOS, use the code below instead

      document.getElementById('store_link').setAttribute('href', url);

      */

    };
  </script>
</body>

</html>
```

</Accordion>

> 👍 **Совет**
>
> Вы можете реализовать фрагмент javascript с помощью Диспетчера тегов Google. Диспетчер тегов Google позволяет вам контролировать, когда и где следует использовать javascript для целевой страницы.

### Инструкции

1. Активируйте скрипт ***generateUrl*** при загрузке любой страницы вашего сайта, на которую посетители могут перейти напрямую и на которой есть кнопки ***Скачать*** для вашего мобильного приложения.  

   > 🚧 **Важно!**
   >
   > **По умолчанию кнопки *Скачать* должны направлять на страницы приложений в iTunes и Google Play**. Если эти ссылки сохранены без изменений (например, посетитель перешел по ссылке атрибуции AF или Meta ads), ***generateUrl*** возвращает ' '. В противном случае возвращается URL-адрес, который будет использоваться обеими кнопками «Скачать» (в этом случае можно также использовать одну кнопку ***Скачать*** для обеих версий приложения с помощью OneLink).

2. Замените значение параметра ***oneLinkURL*** собственным базовым URL-адресом OneLink в том же формате, что и заполнитель `https://yourapp.onelink.me/abcd`.  
   ОБЯЗАТЕЛЬНО, чтобы атрибутировать посетителей из всех SRN (кроме платной рекламы в Meta Ads) и органических посетителей с мобильных устройств.
3. Замените значение параметра ***webFormURL*** ссылкой на собственную веб-форму. Веб-форма должна получать электронную почту или номер телефона пользователя и отправлять на мобильное устройство пользователя сообщение с URL-адресом OneLink для загрузки приложения.  
   ОБЯЗАТЕЛЬНО, чтобы атрибутировать посетителей с настольных компьютеров.
4. Замените значение параметра ***partnerIDParam***, если вы хотите, чтобы органические мобильные пользователи атрибутировались к другому медиа-источнику, а не к веб-сайту.
5. По умолчанию при клике по кнопке ***Скачать*** пользователи атрибутируются к веб-странице, на которой они находятся, если только в URL-адресе целевой страницы не указано другое название кампании (`&c={CAMPAIGN_NAME}`). Чтобы изменить это, замените значение параметра ***campaignParam***.  
   Необязательно для ВСЕХ сценариев, кроме платной рекламы в Meta ads.

## Просмотр результатов

[![dashboard_landing_page_results.png](https://files.readme.io/29d7b6b096687a1f106efa4dcfc65ab1f550976516c87c3ffafde29f852855bb-360001342158.png)](https://files.readme.io/29d7b6b096687a1f106efa4dcfc65ab1f550976516c87c3ffafde29f852855bb-360001342158.png)

Как и в любом медиа-источнике, результаты целевой страницы можно просматривать на дэшборде приложения, в сырых данных или с помощью API AppsFlyer.

Если ваша воронка мобильного маркетинга всегда ведет на целевую страницу, эти медиа-источники представляют собой следующее:

| **Источник** | **Описание** |
| --- | --- |
| **органический** | Пользователи, которые не заходили на целевую страницу или не взаимодействовали с ней. А также пользователи, которые все же взаимодействовали, но не были атрибутированы по разным причинам, например, по истечении окна атрибуции до запуска приложения. |
| **Веб-сайт** | Органические мобильные пользователи, посетившие вашу целевую страницу/веб-сайт и затем установившие приложение. |
| **Meta реклама** | Пользователи из платной рекламы в Meta |
| **fbpost\_lp** | Пользователи из вирусных бесплатных постов в Meta |
| **google\_lp** | Пользователи из Google Ads |
| **[SRN]\_lp** | Пользователи из других SRN, например. Пользователи из других SRN, например Twitter (twitter\_lp), Snapchat (snapchat\_lp), Doubleclick (doubleclick\_lp) или Oath (oath\_lp) |
| **Идентификатор интегрированного партнера** | Пользователи, перешедшие по объявлению интегрированного партнера, в котором используется ссылка атрибуции AppsFlyer. Например, inmobi\_int, tapjoy\_int |
| **Настольный ПК** | Пользователи настольных компьютеров, заполнившие веб-форму и совершившие установку после клика по SMS или по электронному письму, отправленному на их мобильные устройства |
| **Другие источники** | Пользователи из собственных медиа-источников, использующих ссылки атрибуции AppsFlyer. Например, email, sms, blog\_post и др. |

## Решение OneLink для целевой страницы

OneLink™ — это уникальная ссылка атрибуции AppsFlyer, которая используется для обнаружения и перенаправления устройств, а также для диплинкинга.

Решение <Anchor target="_blank" href="/marketers/ru/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#social-app-landing-page">Целевая страница для приложений соцсетей</Anchor> требует, чтобы рекламодатель имел базовый URL-адрес OneLink. Пользователи, которые нажимают на рекламу в приложениях социальных сетей, затем перенаправляются на целевую страницу, созданную AppsFlyer. Оттуда они могут быть перенаправлены по диплинкам или перейти к установке приложения.

AppsFlyer предоставляет различные шаблоны целевых страниц для приложений социальных сетей. Расположение элементов в шаблонах фиксировано, но сами элементы можно настраивать, в том числе изображение или цвет фона, заголовки, тексты, иллюстрации, кнопки, тэги и др.

Если вы еще не внедрили OneLink для своего приложения:

1. Настройте <Anchor target="_blank" href="/marketers/ru/docs/create-a-onelink-template#создание-шаблонов-onelink">шаблон OneLink</Anchor>.
2. Создайте <Anchor target="_blank" href="/marketers/ru/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#создание-ссылки-onelink">URL-адрес OneLink</Anchor> на основе шаблона.
3. В скрипте замените https://yourapp.onelink.me/abcd на свой URL-адрес OneLink.

<div data-zendesk-anchors="the-upsides=%D0%BF%D0%BB%D1%8E%D1%81%D1%8B the-downsides=%D0%BD%D0%B5%D0%B4%D0%BE%D1%81%D1%82%D0%B0%D1%82%D0%BA%D0%B8 the-challenges-of-mobile-attribution-on-landing-pages=%D1%81%D0%BB%D0%BE%D0%B6%D0%BD%D0%BE%D1%81%D1%82%D0%B8-%D0%BC%D0%BE%D0%B1%D0%B8%D0%BB%D1%8C%D0%BD%D0%BE%D0%B9-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8-%D0%BD%D0%B0-%D1%86%D0%B5%D0%BB%D0%B5%D0%B2%D1%8B%D1%85-%D1%81%D1%82%D1%80%D0%B0%D0%BD%D0%B8%D1%86%D0%B0%D1%85 the-solution=%D1%80%D0%B5%D1%88%D0%B5%D0%BD%D0%B8%D0%B5 landing-page-scenarios=%D1%81%D1%86%D0%B5%D0%BD%D0%B0%D1%80%D0%B8%D0%B8-%D1%86%D0%B5%D0%BB%D0%B5%D0%B2%D0%BE%D0%B9-%D1%81%D1%82%D1%80%D0%B0%D0%BD%D0%B8%D1%86%D1%8B description=%D0%BE%D0%BF%D0%B8%D1%81%D0%B0%D0%BD%D0%B8%D0%B5 conclusion=%D0%B2%D1%8B%D0%B2%D0%BE%D0%B4 instructions=%D0%B8%D0%BD%D1%81%D1%82%D1%80%D1%83%D0%BA%D1%86%D0%B8%D0%B8 what-the-script-does=%D1%87%D1%82%D0%BE-%D0%B4%D0%B5%D0%BB%D0%B0%D0%B5%D1%82-%D1%81%D0%BA%D1%80%D0%B8%D0%BF%D1%82 description::7888dd9d=%D0%BE%D0%BF%D0%B8%D1%81%D0%B0%D0%BD%D0%B8%D0%B5-1 conclusion::11bed45=%D0%B2%D1%8B%D0%B2%D0%BE%D0%B4-1 instructions::5aa3290f=%D0%B8%D0%BD%D1%81%D1%82%D1%80%D1%83%D0%BA%D1%86%D0%B8%D0%B8-1 what-the-script-does::2a675257=%D1%87%D1%82%D0%BE-%D0%B4%D0%B5%D0%BB%D0%B0%D0%B5%D1%82-%D1%81%D0%BA%D1%80%D0%B8%D0%BF%D1%82-1 description::650e3f28=%D0%BE%D0%BF%D0%B8%D1%81%D0%B0%D0%BD%D0%B8%D0%B5-2 conclusion::a982e4bd=%D0%B2%D1%8B%D0%B2%D0%BE%D0%B4-2 instructions::afffc83f=%D0%B8%D0%BD%D1%81%D1%82%D1%80%D1%83%D0%BA%D1%86%D0%B8%D0%B8-2 what-the-script-does::3fd4ce35=%D1%87%D1%82%D0%BE-%D0%B4%D0%B5%D0%BB%D0%B0%D0%B5%D1%82-%D1%81%D0%BA%D1%80%D0%B8%D0%BF%D1%82-2 description::9c3fcdaa=%D0%BE%D0%BF%D0%B8%D1%81%D0%B0%D0%BD%D0%B8%D0%B5-3 conclusion::bf993a93=%D0%B2%D1%8B%D0%B2%D0%BE%D0%B4-3 instructions::350b4cb1=%D0%B8%D0%BD%D1%81%D1%82%D1%80%D1%83%D0%BA%D1%86%D0%B8%D0%B8-3 what-the-script-does::3dda504d=%D1%87%D1%82%D0%BE-%D0%B4%D0%B5%D0%BB%D0%B0%D0%B5%D1%82-%D1%81%D0%BA%D1%80%D0%B8%D0%BF%D1%82-3 description::5150e1b5=%D0%BE%D0%BF%D0%B8%D1%81%D0%B0%D0%BD%D0%B8%D0%B5-4 conclusion::d51c1aec=%D0%B2%D1%8B%D0%B2%D0%BE%D0%B4-4 instructions::e083609=%D0%B8%D0%BD%D1%81%D1%82%D1%80%D1%83%D0%BA%D1%86%D0%B8%D0%B8-4 what-the-script-does::85ffec6c=%D1%87%D1%82%D0%BE-%D0%B4%D0%B5%D0%BB%D0%B0%D0%B5%D1%82-%D1%81%D0%BA%D1%80%D0%B8%D0%BF%D1%82-4 description::f5a2038b=%D0%BE%D0%BF%D0%B8%D1%81%D0%B0%D0%BD%D0%B8%D0%B5-5 conclusion::4593a93c=%D0%B2%D1%8B%D0%B2%D0%BE%D0%B4-5 instructions::2e4dd2ee=%D0%B8%D0%BD%D1%81%D1%82%D1%80%D1%83%D0%BA%D1%86%D0%B8%D0%B8-5 what-the-script-does::d6370587=%D1%87%D1%82%D0%BE-%D0%B4%D0%B5%D0%BB%D0%B0%D0%B5%D1%82-%D1%81%D0%BA%D1%80%D0%B8%D0%BF%D1%82-5 description::e20640cf=%D0%BE%D0%BF%D0%B8%D1%81%D0%B0%D0%BD%D0%B8%D0%B5-6 conclusion::c818491=%D0%B2%D1%8B%D0%B2%D0%BE%D0%B4-6 instructions::ba61ae3e=%D0%B8%D0%BD%D1%81%D1%82%D1%80%D1%83%D0%BA%D1%86%D0%B8%D0%B8-6 what-the-script-does::3668d917=%D1%87%D1%82%D0%BE-%D0%B4%D0%B5%D0%BB%D0%B0%D0%B5%D1%82-%D1%81%D0%BA%D1%80%D0%B8%D0%BF%D1%82-6 landing-page-javascript=javascript-%D1%86%D0%B5%D0%BB%D0%B5%D0%B2%D0%BE%D0%B9-%D1%81%D1%82%D1%80%D0%B0%D0%BD%D0%B8%D1%86%D1%8B instructions::10da52a9=%D0%B8%D0%BD%D1%81%D1%82%D1%80%D1%83%D0%BA%D1%86%D0%B8%D0%B8-7 viewing-the-results=%D0%BF%D1%80%D0%BE%D1%81%D0%BC%D0%BE%D1%82%D1%80-%D1%80%D0%B5%D0%B7%D1%83%D0%BB%D1%8C%D1%82%D0%B0%D1%82%D0%BE%D0%B2 onelink-for-landing-page-solution=%D1%80%D0%B5%D1%88%D0%B5%D0%BD%D0%B8%D0%B5-onelink-%D0%B4%D0%BB%D1%8F-%D1%86%D0%B5%D0%BB%D0%B5%D0%B2%D0%BE%D0%B9-%D1%81%D1%82%D1%80%D0%B0%D0%BD%D0%B8%D1%86%D1%8B" />
