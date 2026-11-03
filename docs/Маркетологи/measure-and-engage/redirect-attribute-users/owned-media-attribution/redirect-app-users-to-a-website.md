---
title: Перенаправляйте пользователей приложения на веб-сайт
metadata:
  keywords:
    - OneLink
    - Marketers
    - Social-to-App
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-asaf-mashiah
    - Marketers
    - Social-to-App
  created_at: '2022-02-22T11:45:43Z'
  edited_at: '2026-10-19T14:31:29Z'
  id: 4460838224273
  locale: ru
  section: Owned media attribution
  section_id: 6551214397585
  url: https://support.appsflyer.com/hc/ru/articles/4460838224273
---
> **Кратко:** Перенаправляйте пользователей приложения на веб-URL-адрес или страницу в социальных сетях с помощью URL-адреса, созданного в OneLink.

## Перенаправляйте пользователей приложения на веб-URL-адрес

Рекламодатели могут публиковать URL-адреса OneLink, ведущие на внешние веб-страницы или сайты социальных сетей. AppsFlyer измеряет клики по ссылке в приложении, что позволяет определить эффективность рекламы.

**Необходимые условия**: аккаунт AppsFlyer как минимум с одним приложением.

**Чтобы настроить перенаправление из приложения в интернет**:

1. Настройте <Anchor target="_blank" href="/marketers/ru/docs/create-a-onelink-template#создание-шаблонов-onelink">шаблон OneLink</Anchor>.
   * В разделе **When app is installed** убедитесь, что вы не настроили способ открытия приложения (Universal Links, App Links или схема URI).
2. Создайте <Anchor target="_blank" href="/marketers/ru/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#создание-ссылки-onelink">пользовательскую ссылку OneLink</Anchor>.
   * В разделе **When app isn’t installed** убедитесь, что настройки перенаправления указывают на нужный веб-URL-адрес.
   * Не добавляйте параметр `af_dp` со схемой URI.
3. Убедитесь, что домен, на который вы перенаправляете пользователей, добавлен в ваш <Anchor target="_blank" href="/marketers/ru/docs/set-up-your-domain-redirect-allowlist">redirect allowlist</Anchor>.   
   **Примечание:** Чтобы пользователи перенаправлялись только на проверенные и надежные домены, необходимо настроить redirect allowlist.

Чтобы протестировать вашу ссылку:

**Необходимые условия**: мобильное устройство с установленным приложением.

1. Отправьте короткий или длинный URL-адрес на свой телефон и кликните по нему.  
   **Примечание**: Перешлите себе ссылку по электронной почте или по WhatsApp и откройте ее на телефоне. Не копируйте ссылку в заметки на устройствах iOS, или напрямую в мобильный браузер.
2. Вы будете перенаправлены на веб-URL-адрес.

<div data-zendesk-anchors="redirect-app-users-to-a-web-url=%D0%BF%D0%B5%D1%80%D0%B5%D0%BD%D0%B0%D0%BF%D1%80%D0%B0%D0%B2%D0%BB%D1%8F%D0%B9%D1%82%D0%B5-%D0%BF%D0%BE%D0%BB%D1%8C%D0%B7%D0%BE%D0%B2%D0%B0%D1%82%D0%B5%D0%BB%D0%B5%D0%B9-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D1%8F-%D0%BD%D0%B0-%D0%B2%D0%B5%D0%B1-url-%D0%B0%D0%B4%D1%80%D0%B5%D1%81 01JENAXDEE8C81DN0JGPWPZQSY=%D0%BF%D0%B5%D1%80%D0%B5%D0%BD%D0%B0%D0%BF%D1%80%D0%B0%D0%B2%D0%BB%D1%8F%D0%B9%D1%82%D0%B5-%D0%BF%D0%BE%D0%BB%D1%8C%D0%B7%D0%BE%D0%B2%D0%B0%D1%82%D0%B5%D0%BB%D0%B5%D0%B9-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D1%8F-%D0%BD%D0%B0-%D0%B2%D0%B5%D0%B1-url-%D0%B0%D0%B4%D1%80%D0%B5%D1%81" />
