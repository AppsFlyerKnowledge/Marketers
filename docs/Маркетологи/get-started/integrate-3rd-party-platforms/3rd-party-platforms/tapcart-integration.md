---
title: Интеграция Tapcart
metadata:
  keywords:
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2021-11-24T09:21:54Z'
  edited_at: '2026-08-18T00:12:44Z'
  id: 4411720533905
  locale: ru
  section: 3rd-party platforms
  section_id: 6551199962257
  url: https://support.appsflyer.com/hc/ru/articles/4411720533905
---
> **Краткий обзор:** Используйте Tapcart, чтобы пользоваться всеми преимуществами AppsFlyer для своего приложения.

<div id="introduction" />

## Введение

Благодаря Tapcart вам будет удобнее отправлять свои данные в AppsFlyer и использовать его возможности. Если при разработке приложения вы используете Tapcart, SDK от AppsFlyer реализуется в приложении по умолчанию. После того как вы записали свои данные через Tapcart, данные, включая органические и неорганические установки, отображаются в AppsFlyer.

<div id="integrating-tapcart-with-appsflyer" />

## Интеграция Tapcart с AppsFlyer

SDK от AppsFlyer позволяет вам измерять установки, удаления, рефералы, взаимодействия пользователей с push-уведомлениями, выполнять перенаправления по диплинкам, обрабатывать сценарии конфиденциальности пользователей и многое другое.

Подробнее о том, как как интегрировать Tapcart с AppsFlyer, см. <Anchor target="_blank" href="https://tapcart.com/integrations/appsflyer">на сайте Tapcart</Anchor>.

<div id="default-in-app-events-configured-in-the-appsflyer-sdk" />

## Настройки внутренних событий приложения по умолчанию в SDK от AppsFlyer

После того как Tapcart интегрировал SDK AppsFlyer в ваше приложение, следующие внутренние события приложения будут регистрироваться при каждом выполнении их пользователем:

* Выполнение регистрации
* вход в систему;
* поиск;
* просмотр контента;
* просмотр списка;
* добавление в избранное;
* добавление в корзину;
* начало оформления заказа;
* покупка;
* завершенная покупка;
* удаление из корзины;
* первая покупка.

<div id="enable-deep-linking-with-appsflyer" />

## Активация диплинкинга с AppsFlyer

**Чтобы активировать диплинкинг с AppsFlyer, вам нужно предоставить Tapcart следующие параметры:**

1. **Ключ разработчика:** Этот уникальный идентификатор и токен аутентификации используется для настройки SDK, шифрования его сообщений и аутентификации аккаунта клиента или вызова программы в API.  
   Приложения в одном аккаунте обычно имеют один и тот же ключ разработчика. Подробнее о <Anchor target="_blank" href="/marketers/ru/docs/app-settings#sdk-authentication-dev-key">ключе разработчика</Anchor>.
2. **Идентификатор шаблона OneLink**: Это идентификатор для шаблона OneLink, используемый для генерации ваших URL-адресов OneLink. Подробнее о <Anchor target="_blank" href="/marketers/ru/docs/create-a-onelink-template#создание-шаблонов-onelink">создании шаблона OneLink</Anchor>.  
   **Чтобы получить идентификатор для конкретного шаблона:**  
   1. В AppsFlyer перейдите в раздел **Опыт и диплинкинг** > **Пользовательские ссылки OneLink**.
   2. В меню **шаблона OneLink** выберите необходимый шаблон.
   3. Скопируйте идентификатор, отображаемый справа.  
       <Image align="center" alt="OneLink-template-id.png" src="https://files.readme.io/bb9524b5aecacba00c7f4801f7c854567119c032fa99a6d39122079e3f7956d1-small-4631542470673.png" />
3. **URL-адрес OneLink:** конкретный URL-адрес OneLink, сгенерированный в AppsFlyer для конкретной кампании. Подробнее о <Anchor target="_blank" href="/marketers/ru/docs/onelink-guide">том, как сгенерировать ваш OneLink</Anchor>.

<div data-zendesk-anchors="introduction=%D0%B2%D0%B2%D0%B5%D0%B4%D0%B5%D0%BD%D0%B8%D0%B5 h_01JQ6D9NCM8K3E6GS12V2CR1CH=%D0%B2%D0%B2%D0%B5%D0%B4%D0%B5%D0%BD%D0%B8%D0%B5 integrating-tapcart-with-appsflyer=%D0%B8%D0%BD%D1%82%D0%B5%D0%B3%D1%80%D0%B0%D1%86%D0%B8%D1%8F-tapcart-%D1%81-appsflyer h_01JQ6D9NCM95VJB19G2F7SDRG1=%D0%B8%D0%BD%D1%82%D0%B5%D0%B3%D1%80%D0%B0%D1%86%D0%B8%D1%8F-tapcart-%D1%81-appsflyer default-inapp-events-configured-in-the-appsflyer-sdk=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B8-%D0%B2%D0%BD%D1%83%D1%82%D1%80%D0%B5%D0%BD%D0%BD%D0%B8%D1%85-%D1%81%D0%BE%D0%B1%D1%8B%D1%82%D0%B8%D0%B9-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D1%8F-%D0%BF%D0%BE-%D1%83%D0%BC%D0%BE%D0%BB%D1%87%D0%B0%D0%BD%D0%B8%D1%8E-%D0%B2-sdk-%D0%BE%D1%82-appsflyer h_01JQ6D9NCMYBNJ6WJ09R1EHXH4=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B8-%D0%B2%D0%BD%D1%83%D1%82%D1%80%D0%B5%D0%BD%D0%BD%D0%B8%D1%85-%D1%81%D0%BE%D0%B1%D1%8B%D1%82%D0%B8%D0%B9-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D1%8F-%D0%BF%D0%BE-%D1%83%D0%BC%D0%BE%D0%BB%D1%87%D0%B0%D0%BD%D0%B8%D1%8E-%D0%B2-sdk-%D0%BE%D1%82-appsflyer enable-deep-linking-with-appsflyer=%D0%B0%D0%BA%D1%82%D0%B8%D0%B2%D0%B0%D1%86%D0%B8%D1%8F-%D0%B4%D0%B8%D0%BF%D0%BB%D0%B8%D0%BD%D0%BA%D0%B8%D0%BD%D0%B3%D0%B0-%D1%81-appsflyer h_01JQ6D9NCMC97JQ759B44M9TDJ=%D0%B0%D0%BA%D1%82%D0%B8%D0%B2%D0%B0%D1%86%D0%B8%D1%8F-%D0%B4%D0%B8%D0%BF%D0%BB%D0%B8%D0%BD%D0%BA%D0%B8%D0%BD%D0%B3%D0%B0-%D1%81-appsflyer" />
