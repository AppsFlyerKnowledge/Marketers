---
title: Рекомендуемые события для приложений онлайн-образования
metadata:
  keywords:
    - Advertisers
    - Developers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-guy-sarfatty
    - Marketers
    - Mobile Attribution
  created_at: '2021-04-28T12:35:57Z'
  edited_at: '2026-08-28T00:13:23Z'
  id: 360019794378
  locale: ru
  section: In-app events
  section_id: 6551285343761
  url: https://support.appsflyer.com/hc/ru/articles/360019794378
---
> **Краткий обзор:** Измеряйте качество пользователей на всех этапах их пути, регистрируя эти рекомендуемые события внутри вашего приложения онлайн-образования.

<div id="-online-education" />

## <Image alt="education.png" src="https://files.readme.io/fb036c8f3b0cb4cc06a5284c26089bbb361273ab628bc5b740692bc49e7a2c40-20659493109393.png" width="100px" /> Онлайн-образование

Приложения для онлайн-обучения позволяют пользователям учиться удаленно. Мы рекомендуем регистрировать следующие типичные события: регистрация, прохождение заданий и курсов, получение сертификатов.

Регистрация событий поможет вам определить:

* Какие курсы самые востребованные, как можно настроить таргетинг.
* Для каких пользователей настраивать ретаргетинг и напоминания о необходимости выполнить оставшиеся задания курса.
* Какие курсы и сертификаты пользуются самым большим спросом.

<div id="important" />

> 🚧 **Важно!**
>
> * Обязательно прочитайте <Anchor target="_blank" href="/marketers/ru/docs/in-app-events-overview#настройка-событий-в-приложении">инструкции</Anchor> для маркетологов по реализации внутренних событий приложения.
> * Чтобы оптимизировать процесс внедрения, воспользуйтесь <Anchor target="_blank" href="http://evgen.appsflyer.com/?vertical=online_education">генератором внутренних событий</Anchor>. Этот инструмент содержит все типичные внутренние события приложения, описанные в этой статье, и позволяет изменять их в соответствии с потребностями бизнеса. Когда файл будет готов, предоставьте его разработчику.
> * По каждому рекомендуемому в этой статье событию доступны <Anchor target="_blank" href="http://evgen.appsflyer.com/?vertical=online_education&view=code">примеры кода</Anchor> для разработчиков iOS, Android и Unity.
> * Подробные инструкции для разработчиков доступны в <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/in-app-events-sdk#understanding-event-structure-definitions">**хабе AppsFlyer для разработчиков**</Anchor>.
>
> Дополнительные сведения о регистрации внутренних событий см. в <Anchor target="_blank" href="/marketers/ru/docs/in-app-events-overview">Руководстве по внутренним событиям приложения</Anchor>.

[![Flowchart_for_recommended_events_online_education_app_user_journey](https://files.readme.io/a913f14a20a52d7d70a96be7601fd264650f790337ceb83b9c53fd0006afc8e1-360020170478.png)](https://files.readme.io/a913f14a20a52d7d70a96be7601fd264650f790337ceb83b9c53fd0006afc8e1-360020170478.png)

<div id="recommended-structures-for-predefined-events" />

## Рекомендуемые структуры для предопределенных событий

В следующем разделе представлен список структур для событий, характерных для вертикали онлайн-обучения. В каждую структуру входят предопределенное название события и рекомендуемые параметры события. Обратите внимание, что внутренние события приложения могут содержать любые параметры событий, отвечающие потребностям вашего бизнеса.

<div id="login-af_login" />

<Accordion title="Вход в систему (af_login)">

**Цель**

Проанализировать метрику удержания зарегистрированных пользователей.

**Триггер**

Каждый успешный вход пользователя в систему.

**Параметры события**

Можно отправлять без каких-либо дополнительных параметров.

</Accordion>

<div id="complete-registration-af_complete_registration" />

<Accordion title="Завершить регистрацию (af_complete_registration)">

**Цель**

Узнать, сколько пользователей установило приложение и зарегистрировалось, какие способы регистрации предпочитают пользователи.

**Триггер**

Пользователь завершает процесс регистрации.

**Параметры события**

| Имя | Описание | Пример значения |
| --- | --- | --- |
| af\_метод\_регистрации | Тип метода регистрации | email, facebook |

</Accordion>

<div id="tutorial-completion-af_tutorial_completion" />

<Accordion title="Завершение обучения (af_tutorial_completion)">

**Цель**

Регистрация этого события поможет вам определить:

* Какие темы могут быть трудны для пользователей.
* Какие туториалы выполняются плохо и требуют доработки.
* Связать общую активность пользователя с такими показателями, как доход и т. д.

**Триггер**

* Если пользователь проходит туториал полностью,
* Если пользователь начинает туториал, но выходит, не пройдя его полностью,

**Параметры события**

| Имя | Описание | Пример значения |
| --- | --- | --- |
| af\_success | Прошел ли пользователь туториал | Да |
| af\_tutorial\_id | Идентификатор задания | 3 |
| af\_content | Название задания | алгебра |

</Accordion>

<div id="purchase-af_purchase" />

<Accordion title="Покупка (af_purchase)">

**Цель**

Регистрация покупок внутри приложения поможет вам:

* Определить LTV пользователей и ROI кампаний по всем рекламным сетям и рекламным агентствам.
* Определить, какие предложения наиболее популярны среди пользователей
* Настроить перекрестные ссылки между кампаниями и приобретенными товарами, чтобы оптимизировать таргетинг

Чтобы зарегистрировать и валидировать это событие, см. в разделе <Anchor target="_blank" href="/marketers/ru/docs/purchase-and-subscription-validation-overview">Валидация покупки и подписки</Anchor>.

**Триггер**

Пользователь попадает на страницу благодарности после успешной покупки.

**Параметры события**

| Имя | Описание | Пример значения |
| --- | --- | --- |
| <Anchor target="_blank" href="/marketers/ru/docs/in-app-events-overview#revenue-events">af\_выручка</Anchor> | Ожидаемый доход от покупки | 250.99 |
| af\_currency | Код валюты | USD (доллар США) |
| af\_content\_id | идентификатор товара | 001, 092 |
| идентификатор\_заказа | Идентификатор заказа | 9277 |
| af\_receipt\_id | Идентификатор чека | 9277 |

</Accordion>

<div id="recommended-structures-for-custom-events" />

## Рекомендуемые структуры для настраиваемых событий

В следующем разделе представлен список структур для событий. В структурах указаны имена настраиваемых событий и рекомендуемые параметры событий. Обратите внимание, что внутренние события приложения могут содержать любые параметры событий, отвечающие потребностям вашего бизнеса.

<div id="complete-exercise-complete_excercise" />

<Accordion title="Выполнение упражнения (complete_excercise)">

**Цель**

Регистрация этого события и его сопоставление с другими данными позволяет узнать больше о пользователях. Например, сколько пользователей начали, но не завершили упражнение.

**Триггер**

Упражнение выполнено пользователем

**Параметры события**

| Имя | Описание | Пример значения |
| --- | --- | --- |
| course\_name | Название курса | алгебра |
| exercise\_name | Название упражнения | 2 |

</Accordion>

<div id="course-completed-course_completed" />

<Accordion title="Полное прохождение курса (course_completed)">

**Цель**

Регистрация этого события и его сопоставление с другими данными позволяет узнать больше о пользователях. Например, сколько пользователей начали, но не завершили курс.

**Триггер**

Курс пройден пользователем.

**Параметры события**

| Имя | Описание | Пример значения |
| --- | --- | --- |
| course\_name | Название курса | алгебра |
| course\_completed | Пройден ли курс | Да |

</Accordion>

<div id="certificate-issued-certificate_issued" />

<Accordion title="Выдача сертификата (certificate_issued)">

**Цель**

Регистрация этого события и его сопоставление с другими данными позволяет узнать больше о пользователях. Например, выяснить, сколько пользователей прошло курс, чтобы настроить для них ретаргетинг с приглашением на следующий курс.

**Триггер**

Выдача сертификата пользователю.

**Параметры события**

| Имя | Описание | Пример значения |
| --- | --- | --- |
| course\_name | Название курса | алгебра |
| certificate\_received | Был ли выдан сертификат | Да |

</Accordion>

<div data-zendesk-anchors="online-education=-%D0%BE%D0%BD%D0%BB%D0%B0%D0%B9%D0%BD-%D0%BE%D0%B1%D1%80%D0%B0%D0%B7%D0%BE%D0%B2%D0%B0%D0%BD%D0%B8%D0%B5 h_01HGTAYQ9V4Z5YEWTNCZPVMVMF=-%D0%BE%D0%BD%D0%BB%D0%B0%D0%B9%D0%BD-%D0%BE%D0%B1%D1%80%D0%B0%D0%B7%D0%BE%D0%B2%D0%B0%D0%BD%D0%B8%D0%B5 h_01HGTAYQ9VJ6GS1XVQPG198C8Z=%D0%B2%D0%B0%D0%B6%D0%BD%D0%BE recommended-structures-for-predefined-events=%D1%80%D0%B5%D0%BA%D0%BE%D0%BC%D0%B5%D0%BD%D0%B4%D1%83%D0%B5%D0%BC%D1%8B%D0%B5-%D1%81%D1%82%D1%80%D1%83%D0%BA%D1%82%D1%83%D1%80%D1%8B-%D0%B4%D0%BB%D1%8F-%D0%BF%D1%80%D0%B5%D0%B4%D0%BE%D0%BF%D1%80%D0%B5%D0%B4%D0%B5%D0%BB%D0%B5%D0%BD%D0%BD%D1%8B%D1%85-%D1%81%D0%BE%D0%B1%D1%8B%D1%82%D0%B8%D0%B9 h_01HGTAYQ9VS0DYFSFNEPDCDVTG=%D1%80%D0%B5%D0%BA%D0%BE%D0%BC%D0%B5%D0%BD%D0%B4%D1%83%D0%B5%D0%BC%D1%8B%D0%B5-%D1%81%D1%82%D1%80%D1%83%D0%BA%D1%82%D1%83%D1%80%D1%8B-%D0%B4%D0%BB%D1%8F-%D0%BF%D1%80%D0%B5%D0%B4%D0%BE%D0%BF%D1%80%D0%B5%D0%B4%D0%B5%D0%BB%D0%B5%D0%BD%D0%BD%D1%8B%D1%85-%D1%81%D0%BE%D0%B1%D1%8B%D1%82%D0%B8%D0%B9 h_01HGTAYQ9VX44FA5HHBT6DGA2R=login-af_login h_01HGTAYQ9VR78MHTJZFVFCKCV4=complete-registration-af_complete_registration h_01HGTAYQ9VE8ZBF1DJ2AAA1HFF=tutorial-completion-af_tutorial_completion h_01HGTAYQ9VSXMR0J1T0KN6WK2G=purchase-af_purchase recommended-structures-for-custom-events=%D1%80%D0%B5%D0%BA%D0%BE%D0%BC%D0%B5%D0%BD%D0%B4%D1%83%D0%B5%D0%BC%D1%8B%D0%B5-%D1%81%D1%82%D1%80%D1%83%D0%BA%D1%82%D1%83%D1%80%D1%8B-%D0%B4%D0%BB%D1%8F-%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%B0%D0%B8%D0%B2%D0%B0%D0%B5%D0%BC%D1%8B%D1%85-%D1%81%D0%BE%D0%B1%D1%8B%D1%82%D0%B8%D0%B9 h_01HGTAYQ9V93HET4AZ7XGE0E3V=%D1%80%D0%B5%D0%BA%D0%BE%D0%BC%D0%B5%D0%BD%D0%B4%D1%83%D0%B5%D0%BC%D1%8B%D0%B5-%D1%81%D1%82%D1%80%D1%83%D0%BA%D1%82%D1%83%D1%80%D1%8B-%D0%B4%D0%BB%D1%8F-%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%B0%D0%B8%D0%B2%D0%B0%D0%B5%D0%BC%D1%8B%D1%85-%D1%81%D0%BE%D0%B1%D1%8B%D1%82%D0%B8%D0%B9 h_01HGTAYQ9VBZZJ5TC1W2S0MK3P=complete-exercise-complete_excercise h_01HGTAYQ9WQJBBEYKDJ8DP9E31=course-completed-course_completed h_01HGTAYQ9WVXX20FNDZWHGDNZ2=certificate-issued-certificate_issued" />
