---
title: Длинные URL-адреса OneLink
metadata:
  keywords:
    - Marketers
    - parameters
    - QR-to-App
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-asaf-mashiah
    - Marketers
    - QR-to-App
  created_at: '2021-01-26T09:39:19Z'
  edited_at: '2026-08-19T00:33:56Z'
  id: 360017132597
  locale: ru
  section: Deep linking using OneLink
  section_id: 6551203111057
  url: https://support.appsflyer.com/hc/ru/articles/360017132597
---
> Срок действия не истекает, то есть нет ограничения по времени жизни (TTL).

## **Настраиваемые ссылки OneLink:**

* Работайте со всеми маркетинговыми медиаканалами, чтобы перенаправлять пользователей по одному из следующих назначений: 
  * Правильный URL-адрес/магазин приложений.
  * Откройте приложение, а затем перенаправьте пользователей по диплинку на определенное действие в приложении.
* Может поддерживать персонализацию бренда. Это означает, что URL-адрес содержит ваш <Anchor target="_blank" href="/marketers/ru/docs/brand-onelink-with-your-domain">домен бренда</Anchor>вместо субдомена OneLink.
* Это могут быть как короткие, так и длинные URL-адреса:
  * Короткие URL-адреса создаются в AppsFlyer (либо <Anchor target="_blank" href="/marketers/ru/docs/onelink-guide">в пользовательском интерфейсе</Anchor>, либо через <Anchor target="_blank" href="/marketers/ru/docs/use-onelink-api-to-create-links-in-large-scale-campaigns">API</Anchor> или <Anchor target="_blank" href="/marketers/ru/docs/user-invite-attribution">SDK</Anchor>).
  * Длинные URL-адреса:
    * могут быть созданы в пользовательском интерфейсе AppsFlyer или вне AppsFlyer.
    * Содержат любые параметры, которые вам нужны.
    * Можно использовать для генерации большого количества пользовательских ссылок OneLink , применяя собственные простые формулы в электронной таблице. **Примечание**: Ссылки, созданные в электронной таблице , не видны (и не могут быть отредактированы) в любом пользовательском интерфейсе AppsFlyer.
      * Ссылки, созданные в электронной таблице , не видны (и не могут быть отредактированы) в любом пользовательском интерфейсе AppsFlyer.
      * Этот метод работы с электронной таблицей отличается от <Anchor target="_blank" href="/marketers/ru/docs/perform-onelink-bulk-actions-via-csv">выполнения массовых действий OneLink через CSV</Anchor>, при котором создаются короткие URL-адреса оптом.
    * Срок действия не истекает, то есть нет ограничения по времени жизни (TTL).  
      **Краткий обзор.**
    * Длинные URL-адреса прозрачны, то есть все параметры ссылки видны аудитории и потенциально могут быть использованы для манипуляций.
    * Длинные URL-адреса могут не помещаться в браузерах, SMS и других местах с ограничением символов URL.

### Длинные URL-адреса OneLink

* Обновление параметров в коротком URL-адресе OneLink в дэшборде AppsFlyer не меняет идентификатор ID короткой ссылки, поэтому нет необходимости заменять или повторно распространять URL-адрес или связанные с ним QR-коды, даже если они уже используются.
* AppsFlyer автоматически применяет обновленные параметры для атрибуции и отчетности, благодаря чему QR-код остается функциональным и автоматически отражает изменения.

## Процедура

**Чтобы создать длинный URL-адрес OneLink вне пользовательского интерфейса AppsFlyer:**

1. Создайте <Anchor target="_blank" href="/marketers/ru/docs/create-a-onelink-template#создание-шаблонов-onelink">шаблон OneLink</Anchor>.
2. Запишите базовый URL-адрес OneLink, то есть домен шаблона OneLink + идентификатор шаблона.  
   Пример: 
   * Домен шаблона OneLink: `yourbrand.onelink.me`
   * Идентификатор шаблона: `1a6f`
   * Базовый URL-адрес OneLink: `yourbrand.onelink.me/1a6f`
   * Пример брендированного домена: `yourbrand.com/1a6f`
3. Добавьте `?` к URL-адресу, а затем любые параметры, которые вы хотите добавить.
   * См. <Anchor target="_blank" href="/marketers/ru/docs/about-link-structure-and-parameters">список параметров AppsFlyer</Anchor>.
   * Чтобы добавить более одного параметра, используйте `&`.  
     Пример: `yourbrand.onelink.me/1a6f?pid=email&c=freestuff`

**Чтобы получить длинные URL-адреса для пользовательских ссылок OneLink, которые вы создаете в пользовательском интерфейсе AppsFlyer:**

1. В AppsFlyer перейдите к **пользовательским ссылкам OneLink**.  
   Отобразится список OneLinks.  
   [![](https://files.readme.io/53bd68c390389e48eb55802418c601e7523ab7d816d21c1ae672ed55d7ade365-360016243798.jpg)](https://files.readme.io/53bd68c390389e48eb55802418c601e7523ab7d816d21c1ae672ed55d7ade365-360016243798.jpg)
2. Перейдите к ссылке, для которой вам нужен длинный URL-адрес, и в столбце **Действия** нажмите **Получить URL**.  
   Отображается длинный URL-адрес.

<div data-zendesk-anchors="onelink-long-urls=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%B0%D0%B8%D0%B2%D0%B0%D0%B5%D0%BC%D1%8B%D0%B5-%D1%81%D1%81%D1%8B%D0%BB%D0%BA%D0%B8-onelink 01JBXQENR6QHQ1HXQQQ5NBBMKN=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%B0%D0%B8%D0%B2%D0%B0%D0%B5%D0%BC%D1%8B%D0%B5-%D1%81%D1%81%D1%8B%D0%BB%D0%BA%D0%B8-onelink advantages-of-a-short-onelink-url-compared-to-a-long-url=%D0%B4%D0%BB%D0%B8%D0%BD%D0%BD%D1%8B%D0%B5-url-%D0%B0%D0%B4%D1%80%D0%B5%D1%81%D0%B0-onelink h_01JGXTFWS509NW0ESM1CZZ1KZM=%D0%B4%D0%BB%D0%B8%D0%BD%D0%BD%D1%8B%D0%B5-url-%D0%B0%D0%B4%D1%80%D0%B5%D1%81%D0%B0-onelink procedures=%D0%BF%D1%80%D0%BE%D1%86%D0%B5%D0%B4%D1%83%D1%80%D0%B0 h_01JBXQTQ3DXPTP9BY06QKXN3NP=%D0%BF%D1%80%D0%BE%D1%86%D0%B5%D0%B4%D1%83%D1%80%D0%B0" />
