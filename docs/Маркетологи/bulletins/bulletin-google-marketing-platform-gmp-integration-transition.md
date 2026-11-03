---
title: 'Бюллетень: Перенос интеграции с Google Платформой для маркетинга (GMP)'
metadata:
  keywords:
    - Agencies
    - Marketers
    - Mobile Attribution
table_of_contents: false
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
    - Agencies
  created_at: '2023-12-18T11:43:04Z'
  edited_at: '2026-10-19T14:39:22Z'
  id: 21035061438737
  locale: ru
  section: Bulletins
  section_id: 6551161473041
  url: https://support.appsflyer.com/hc/ru/articles/21035061438737
---

<Table>
  <tbody>
    <tr>
      <td>
        **Что нового?**
      </td>
      <td>
        В рамках подготовки к вступлению в силу <Anchor target="_blank" href="https://commission.europa.eu/strategy-and-policy/priorities-2019-2024/europe-fit-digital-age/digital-markets-act-ensuring-fair-and-open-digital-markets_en">Закона о цифровом маркетинге</Anchor> (DMA) компания Google обновляет <Anchor target="_blank" href="https://www.google.com/about/company/user-consent-policy/?sjid=15416941068016224808-NA">политику согласия пользователей в ЕС</Anchor>. AppsFlyer вносит необходимые изменения, чтобы поддержать требования политики Google.

        В настоящее время доступны следующие интеграции Google Платформы для маркетинга (GMP):

        * [Устаревшая] CM360 (DoubleClick) `doubleclick_int`
        * <Anchor target="_blank" href="/marketers/ru/docs/google-marketing-platform-display-video-360-dv360-integration">DV360 (новая интеграция)</Anchor> `dv360_int`

        С июля 2024 года устаревшая интеграция doubleclick\_int находится в режиме предстоящего снятия с поддержки и скоро будет снята с поддержки (конечная дата будет объявлена). Если вы используете эту интеграцию, вам нужно будет перейти на новую интеграцию DV360, чтобы продолжать проводить кампании и измерять их с помощью GMP.
      </td>
    </tr>
    <tr>
      <td>
        **Необходимое действие**
      </td>
      <td>
        Как можно скорее перейдите на новую интеграцию DV360 `dv360_int`.
      </td>
    </tr>
    <tr>
      <td>
        **Шаги, которые необходимо предпринять**
      </td>
      <td>
        Убедитесь, что настроены обе платформы, GMP и AppsFlyer:

        **Настройка в GMP**

        1. Войдите в свой аккаунт CM360 или DV360.   
           **Примечание.** Выполнение этих шагов в CM360 отменяет необходимость их выполнения в DV360.
        2. Создайте или повторно используйте ссылку атрибуции партнера (Link ID), используя <Anchor target="_blank" href="https://support.google.com/displayvideo/answer/10956727">эти инструкции</Anchor>.

        **Настройка в AppsFlyer**

        1. Завершите интеграцию DV360 в AppsFlyer, используя <Anchor target="_blank" href="/marketers/ru/docs/google-marketing-platform-display-video-360-dv360-integration#integration-procedures">эти инструкции</Anchor>.   
           **Примечание.** Чтобы сохранить единообразие данных, убедитесь, что конфигурация аналогична старой интеграции (окна атрибуции, постбэки по событиям в приложении и т. д.).
        2. **Протестируйте новую интеграцию:**   
           Подождите около дня, чтобы подтвердить новые данные интеграции. Вы можете затем отключить устаревшую интеграцию.
      </td>
    </tr>
    <tr>
      <td>
        **Что вы должны знать**
      </td>
      <td>

      </td>
    </tr>
    <tr>
      <td>

      </td>
      <td>
        <table><thead><tr><th><strong>Соображения</strong></th><th>Доступные опции</th></tr></thead><tbody><tr><td colspan="2"><span id="media-source-pid"></span><strong>PID медиа-источника</strong></td></tr><tr><td><span id="after-completing-the-migration-the-dv360-media-source-pid-changes-from-doubleclick_int-to-dv360_int"></span>После завершения миграции PID медиа-источника DV360 меняется с <kbd>doubleclick_int</kbd> на <kbd>dv360_int</kbd>.</td><td>Если вы извлекаете сырые данные из AppsFlyer в бизнес-аналитику или любой сторонний аналитический инструмент, обратите внимание на изменение названия медиа-источника.</td></tr><tr><td colspan="2"><span id="outofstore-apps"></span><strong>Внемагазинные приложения</strong></td></tr><tr><td><span id="apps-from-unofficial-app-stores-arent-supported-in-the-dv360-integration-the-integration-relies-on-a-link-id-which-is-generated-for-apps-obtained-through-official-app-stores"></span>Приложения из неофициальных магазинов приложений не поддерживаются в интеграции DV360. Интеграция зависит от идентификатора ссылки, который генерируется для приложений, полученных через официальные магазины приложений.</td><td>Если ваше приложение загружено из источников вне официальных магазинов приложений, свяжитесь с вашим CSM или hello@appsflyer.com.</td></tr><tr><td colspan="2"><span id="attribution-data-duplication"></span><strong>Распределение данных атрибуции</strong></td></tr><tr><td colspan="2"><span id="while-both-integrations-are-active-in-appsflyer-data-duplication-is-expected-inapp-events-for-installsreengagements-attributed-to-the-legacy-integration-remain-credited-accordingly"></span>Когда обе интеграции активны и претендуют на атрибуцию установок, атрибуция случайным образом распределяется между ними, одна из них является основным источником, а другая выступает в качестве участника. Это гарантирует, что данные не дублируются. Например, если DV360 отвечает за 100 установок, вы можете увидеть 70 установок от устаревшей интеграции и 30 от DV360, или 80 установок от DV360 и 20 установок от устаревшей интеграции.</td></tr><tr><td colspan="2"><span id="inapp-events-for-installsreengagements-attributed-to-the-legacy-integration-remain-credited-accordingly"></span>События в приложении, связанные с установками / повторными вовлечениями, атрибутированные к старой интеграции, учитываются соответственно.</td></tr><tr><td colspan="2"><span id="reengagement-reengagement-attribution-is-supported-in-the-dv360-integration"></span><p><strong>повторное вовлечение</strong></p><p>Атрибуция повторного вовлечения поддерживается в интеграции DV360.</p></td></tr></tbody></table>

        **Несоответствия в полях**

        Из-за различий между доступными полями данных в устаревших и обновленных API вы можете увидеть различия в некоторых полях AppsFlyer, как показано ниже:

        | **Поле AppsFlyer** | **Унаследованное поле (doubleclick\_int)** | **Поле DV360 (dv360\_int)** |
        | --- | --- | --- |
        | Название кампании | placement\_id | line\_item\_name |
        | Идентификатор кампании | placement\_id | line\_item\_id |
        | Название набора объявлений | Страница экспорта данных: часовой пояс, выбранный приложением. | Н/Д (нет поддержки) |
        | идентификатор рекламы | Страница экспорта данных: часовой пояс, выбранный приложением. | Н/Д (нет поддержки) |
        | Имя рекламы | creative\_id | Н/Д (нет поддержки) |
        | идентификатор адсета | creative\_id | creative\_id |
      </td>
    </tr>
  </tbody>
</Table>

<div data-zendesk-anchors="while-both-integrations-are-active-in-appsflyer-data-duplication-is-expected%0Ainapp-events-for-installsreengagements-attributed-to-the-legacy-integration-remain-credited-accordingly=while-both-integrations-are-active-in-appsflyer-data-duplication-is-expected-inapp-events-for-installsreengagements-attributed-to-the-legacy-integration-remain-credited-accordingly reengagement%0Areengagement-attribution-is-supported-in-the-dv360-integration=reengagement-reengagement-attribution-is-supported-in-the-dv360-integration" />
