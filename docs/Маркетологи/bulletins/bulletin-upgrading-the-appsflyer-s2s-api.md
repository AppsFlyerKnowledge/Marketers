---
title: 'Бюллетень: обновление API S2S AppsFlyer'
metadata:
  keywords:
    - Marketers
    - Mobile Attribution
table_of_contents: false
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-guy-sarfatty
    - Marketers
    - Mobile Attribution
  created_at: '2023-11-28T16:26:35Z'
  edited_at: '2026-10-19T14:39:25Z'
  id: 20509378973457
  locale: ru
  section: Bulletins
  section_id: 6551161473041
  url: https://support.appsflyer.com/hc/ru/articles/20509378973457
---
| **Что нового?** | Чтобы повысить безопасность при использовании API и сократить фрод, AppsFlyer обновил свой API server-to-server (S2S) для событий в приложении. В будущем текущая конечная точка будет выведена из эксплуатации, поэтому рекомендуем уже сейчас начать планировать переход.<br /><br />AppsFlyer работает над решением для сторонних технологических партнеров, которые отправляют данные от вашего имени. |
| --- | --- |
| **Дата вступления в силу** | 12.12.2023 |
| **Необходимые условия** | Обновить новый API S2S может только администратор. |
| **Необходимое действие** | Обновите следующие поля для отправки S2S-событий в приложении в AppsFlyer:<ol><li>Перейдите к <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/post_s2s_inappevent">API POST S2S in-app event</Anchor>.</li><li>Замените URL-адрес:<br />С <Anchor target="_blank" href="https://api2.appsflyer.com/inappevent">https://api2.appsflyer.com/inappevent</Anchor><br />На <Anchor target="_blank" href="https://api3.appsflyer.com/inappevent">https://api3.appsflyer.com/inappevent</Anchor></li><li>Обновите заголовок Authorization: замените Dev key на <Anchor target="_blank" href="/marketers/ru/docs/managing-appsflyer-tokens">**новый ключ S2S**</Anchor>.</li><li>Если вы отправляете S2S-события в AppsFlyer через интегрированного партнера (например, Segment, Tealium, Amplitude, mParticle, RevenueCat или других), свяжитесь с ним, чтобы узнать, как обновить интеграцию.</li></ol> |
| **Рекомендуемое действие:** | **Перед тем как обновить новый API во всех ваших production-вызовах:**<br /><br />Настоятельно рекомендуем отправить несколько тестовых событий в приложении на новую конечную точку и **убедиться, что ошибки не возвращаются**. |
| **Что вам нужно знать** | Если после обновления нового API у вас есть опасения, что события фрода продолжают отправляться на старую конечную точку, обратитесь к своему CSM или в поддержку AppsFlyer. Обязательно укажите соответствующие идентификаторы приложений.<br /><br />После завершения production-миграции AppsFlyer заблокирует старую конечную точку API для этих приложений, поэтому все фрод-вызовы будут заблокированы. |
| **Кому нужно обновить новый API?** | Только рекламодатели должны обновить новый API S2S для событий в приложении. |
| **Об API S2S** | Узнать больше о <Anchor target="_blank" href="/marketers/ru/docs/managing-appsflyer-tokens">S2S и токенах API</Anchor>. |