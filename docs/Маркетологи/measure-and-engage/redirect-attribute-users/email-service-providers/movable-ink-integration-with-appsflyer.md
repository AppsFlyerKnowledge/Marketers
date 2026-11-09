---
title: Интеграция Movable Ink с AppsFlyer
metadata:
  keywords:
    - Marketers
    - OneLink
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-asaf-mashiah
    - Marketers
    - OneLink
  created_at: '2024-09-05T11:55:13Z'
  edited_at: '2026-09-02T00:33:19Z'
  id: 28109258392977
  locale: ru
  section: Email service providers
  section_id: 6551247620881
  url: https://support.appsflyer.com/hc/ru/articles/28109258392977
---
> **Кратко:** Настройте интеграцию с Movable Ink, чтобы создавать уникальные пути пользователя на базе ИИ в ваших маркетинговых кампаниях и контенте в приложении.

## ![53374 изображение базы знаний Movable Ink.png](https://files.readme.io/0f1a5d3d6b60cccdb8be113c9fd4f3603c7c3ed0ad8573a153709391d29b2c3b-28624891792401.png)

<div id="about-the-integration" />

## Об интеграции

Movable Ink — партнер по оптимизации динамического контента, который предоставляет персонализированный опыт клиента в различных каналах, таких как электронная почта, push-уведомления и СМС. Интеграция AppsFlyer и Movable Ink позволяет создавать уникально персонализированные пути на базе ИИ в маркетинговых кампаниях и контенте в приложении.

<div id="set-up-the-integration" />

## Настройка интеграции

**Требования**

* Для кампаний по электронной почте необходимо настроить интеграцию с вашим поставщиком услуг электронной почты (ESP).  
  Список ESP, поддерживаемых AppsFlyer, доступен <Anchor target="_blank" href="/marketers/ru/docs/email-service-provider-esp-integration-guide">здесь.</Anchor>
* Интеграция фрагмента кода AppsFlyer <Anchor target="_blank" href="https://github.com/AppsFlyerSDK/appsflyer-urlresolver-client">URL Resolver</Anchor> в ваши мобильные приложения (он отвечает за разрешение обернутой ссылки Movable Ink).
* OneLink настроен и поддерживает Universal Links/App Links. <Anchor target="_blank" href="/marketers/ru/docs/create-a-onelink-template#создание-шаблонов-onelink">Узнать больше</Anchor>

**См. инструкции по настройке интеграции:**

1. **В Movable Ink:** Войдите в свою учетную запись Movable Ink (если вам нужна помощь, обратитесь к своему представителю Movable Ink или в их команду по работе с клиентами).
2. Создайте контент в **Студии** и завершите настройку кампании.
3. Получите ссылку Movable Ink для использования в кампании по электронной почте:
   * * Перейдите на страницу **Завершить экспорт &** .
     * Нажмите на три точки («…») Щелкните по трем точкам («…») в разделе **Copy Creative Tag** и выберите **Copy Link URL**.   
       **Примечание:** Завершите настройку кампании перед копированием URL-адреса ссылки.
     * Скопируйте URL из атрибута HREF скопированной ссылки (выделен на изображении) и сохраните его для дальнейшего использования. Она будет использоваться как значение диплинкинга в итоговой ссылке.   
       <Image align="center" alt="Изображение Movableink с выделением.png" src="https://files.readme.io/a2ccca4d6053e1448094dd83478610693b13a7f04a77aaaff7d12305533e8fbe-28405439389201.png" width="1130px" />
4. **В AppsFlyer:** перейдите к нужному <Anchor target="_blank" href="/marketers/ru/docs/create-a-onelink-template">шаблону OneLink</Anchor>, который будет использоваться для кампании, и получите следующие данные, необходимые для интеграции:
   * * **Домен OneLink:** Поддомен для генерации OneLink в AppsFlyer.
     * **Template ID:** Идентификатор ID используемого шаблона или шаблона, созданного для кампании.
     * **PID**: Уникальный идентификатор медиаисточника.  
       Рекомендуемое значение — название ESP.
5. Составьте свою ссылку, используя приведенную ниже структуру ссылки. 

   **Структура ссылки:**

   `https://{{onelink.domain}}/{{template_id}}?pid={{pid_value}}&c={{link_name}}&deep_link_value={{mi_link_from_creative_tag}}`

   **Пример:**

   Ниже приведен пример того, как выглядит ссылка после добавления обязательных параметров из таблицы ниже.

   https://link.movableink.com/oskuw854?pid=BRAZE&deep_link_value=https://www.movable-ink-2563.com/p/cp/ee0e28529389f573/c?url=https%3A%2F%2Fwww.movable-ink-2563.com%2Fp%2Frp%2F9011ea048ec4bf03%2Furl&url_sig=D4QtmtC8vqJhU7

   

| Параметр | Description(Описание) | Пример значения | Примечание | Получить из |
| --- | --- | --- | --- | --- |
| `{{onelink.domain}}` | Ваш домен AppsFlyer | mink.onelink.com |  | UI AppsFlyer |
| `{{template_id}}` | ID шаблона ссылки, настроенного в AppsFlyer | 1a6f |  | UI AppsFlyer |
| `{{pid_value}}` | ID ESP / медиаисточника | Название ESP |  | UI AppsFlyer |
| `{{mi_link_from_creative`<br /><br />`_tag}}` | Ссылка перехода по клику HREF из креативного тега Movable Ink. Доступно на странице Finish & Export (см. изображение на шаге 3.) | https://www.movable-ink-2563<br /><br />.com /p/cp /ee0e28529389f573<br /><br />/curl=https %3A%2 F%2Fwww.<br /><br />movableink2563 .com %2Fp%2<br /><br />Frp%2F9011ea048e c4b f03%2<br /><br />Furl&url \_sig=D4QtmtC8vqJhU7 | Ссылка должна быть закодирована. | Movable Ink |

   <div id="note" />

   > 📘 **Примечание**
   >
   > Если значения `af_android_url`, `af_ios_url` и `af_web_dp` совпадают, можно сократить ссылку, используя вместо них `af_r`. Если есть другой параметр с тем же значением, попросите вашего менеджера по работе с клиентами AppsFlyer активировать функцию дублирования параметров.

6. Используйте новую ссылку в своей кампании.  
   **Примечание:** ссылка HREF Movable Ink, которую вы скопировали и вставили в свою ссылку, должна быть закодирована. Однако **при использовании ссылки в email-кампании через ваш ESP параметры ESP не должны быть закодированы**.

<div id="traits-and-limitations" />

## Спецификации и ограничения

См. дополнительные <Anchor target="_blank" href="/marketers/ru/docs/about-link-structure-and-parameters#особенности-и-ограничения">особенности и ограничения ссылки атрибуции</Anchor>.

<div data-zendesk-anchors="about-the-integration=%D0%BE%D0%B1-%D0%B8%D0%BD%D1%82%D0%B5%D0%B3%D1%80%D0%B0%D1%86%D0%B8%D0%B8 h_01J8HQFV2ZYYN7G1FDA1DH1GV3=%D0%BE%D0%B1-%D0%B8%D0%BD%D1%82%D0%B5%D0%B3%D1%80%D0%B0%D1%86%D0%B8%D0%B8 h_01J8HX53FVT1N4MG2HPE743RTS=%D0%BE%D0%B1-%D0%B8%D0%BD%D1%82%D0%B5%D0%B3%D1%80%D0%B0%D1%86%D0%B8%D0%B8 set-up-the-integration=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-%D0%B8%D0%BD%D1%82%D0%B5%D0%B3%D1%80%D0%B0%D1%86%D0%B8%D0%B8 h_01J710N8QBFHSX9BS6H0NFY918=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-%D0%B8%D0%BD%D1%82%D0%B5%D0%B3%D1%80%D0%B0%D1%86%D0%B8%D0%B8 01J9GSWGHBA01N227MCEV91YMV=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%87%D0%B0%D0%BD%D0%B8%D0%B5 traits-and-limitations=%D1%81%D0%BF%D0%B5%D1%86%D0%B8%D1%84%D0%B8%D0%BA%D0%B0%D1%86%D0%B8%D0%B8-%D0%B8-%D0%BE%D0%B3%D1%80%D0%B0%D0%BD%D0%B8%D1%87%D0%B5%D0%BD%D0%B8%D1%8F h_01J9GAS3T6STFKHD4C6Z6GYFMF=%D1%81%D0%BF%D0%B5%D1%86%D0%B8%D1%84%D0%B8%D0%BA%D0%B0%D1%86%D0%B8%D0%B8-%D0%B8-%D0%BE%D0%B3%D1%80%D0%B0%D0%BD%D0%B8%D1%87%D0%B5%D0%BD%D0%B8%D1%8F" />
