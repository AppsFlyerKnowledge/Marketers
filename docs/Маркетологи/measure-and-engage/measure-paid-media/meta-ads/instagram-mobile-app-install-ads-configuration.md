---
title: Настройка рекламных объявлений для установки мобильного приложения в Instagram
metadata:
  keywords:
    - Facebook
    - Instagram
    - install ads
    - integrated partner
    - Advertisers
    - Developers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
  created_at: '2015-09-09T01:10:44Z'
  edited_at: '2026-08-18T00:31:16Z'
  id: 207034066
  locale: ru
  section: Meta ads
  section_id: 6551109855761
  url: https://support.appsflyer.com/hc/ru/articles/207034066
---
> **Краткий обзор:** Добавьте события установки мобильного приложения Instagram в свой рекламный аккаунт Meta.

<Image align="center" alt="instagram_logo.jpg" src="https://files.readme.io/55ab80e2b1ba9d164d978116f3aaaacb9fe7e4571f71e0130a40e1ded16679db-360000492725.jpg" width="101px" />

<div id="setting-up-instagram" />

## Настройка Instagram

Настройки для Instagram указаны в разделе Meta ads в разделе «Активные интеграции AppsFlyer» .

Документацию по Meta можно найти <Anchor target="_blank" href="https://developers.facebook.com/docs/marketing-api/guides/instagramads/">здесь</Anchor> и <Anchor target="_blank" href="https://www.facebook.com/business/help/1634705703469129">здесь</Anchor> .

1. Свяжите свой аккаунт Instagram с Meta Business Manager.  

   <Image align="center" alt="link-inst-with_fb-account.png" src="https://files.readme.io/c6c7fe17274f0b9af008c4452b4b7ea2233cc5bca8773307fef6afaeb7d06015-11212956311441.png" />
2. После добавления в Business Manager назначьте рекламный аккаунт своему аккаунту Instagram  

   <Image align="center" alt="assign-inst-ad-to-fb.png" src="https://files.readme.io/658dc57d0056a2217a9f0f5c785b87e24c297158b75c5815eddb64930d00ea17-11213052873745.png" width="550px" />
3. Настройте Meta ads в разделе «Конфигурация активных интеграций», добавив идентификатор приложения Facebook.
4. Если у вас нет идентификатора приложения Facebook, создайте его <Anchor target="_blank" href="https://developers.facebook.com/apps">здесь</Anchor> .  
   <Image align="center" alt="facebook_app_id.png" src="https://files.readme.io/2e497e1e00c22d0006aebd540b24c47ba4f2907ee9de061dc04ab50bbbe2cc67-14069602144273.png" />

<div id="instagram-landing-page-for-deep-linking" />

## Целевая страница Instagram для диплинкинга

В настоящий момент <Anchor target="_blank" href="/marketers/ru/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#social-app-landing-page">Instagram поддерживает диплинкинг на приложения iOS через Universal Links</Anchor> для татических объявлений (не из каталога). Универсальные ссылки iOS и App Links Android работают только в кампаниях, где в качестве назначения выбрано **Приложение**.

Если вам необходимо использовать настраиваемые ссылки с диплинкингом в Instagram в кампаниях, где нельзя выбрать **Приложение**не может быть выбрано, или например, если вы настраиваете кампанию на узнаваемость в Meta, поскольку в этой кампании нельзя выбрать **Приложение** в качестве целевого адреса, iOS Universal Links и Android App Links не поддерживаются. Вы можете <Anchor target="_blank" href="/marketers/ru/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#social-app-landing-page">настроить целевую страницу Instagram</Anchor> . Это позволяет использовать OneLink вместе с Universal Links в Instagram для дип-линкинга пользователей и улучшения их пользовательского опыта.

Для динамических объявлений можно использовать iOS Universal Links, Android App Links и URI-схемы, как описано  <Anchor target="_blank" href="/marketers/ru/docs/meta-ads-faq#can-onelink-links-be-used-for-app-opening-and-deep-linking-in-facebook-dynamic-product-ads">здесь.</Anchor>

<div data-zendesk-anchors="setting-up-instagram=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-instagram instagram-landing-page-for-deep-linking=%D1%86%D0%B5%D0%BB%D0%B5%D0%B2%D0%B0%D1%8F-%D1%81%D1%82%D1%80%D0%B0%D0%BD%D0%B8%D1%86%D0%B0-instagram-%D0%B4%D0%BB%D1%8F-%D0%B4%D0%B8%D0%BF%D0%BB%D0%B8%D0%BD%D0%BA%D0%B8%D0%BD%D0%B3%D0%B0" />
