---
title: Интеграция Bloomreach с AppsFlyer
metadata:
  keywords:
    - marketers
    - OneLink
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-asaf-mashiah
    - Marketers
    - OneLink
  created_at: '2026-03-29T13:30:32Z'
  edited_at: '2026-10-19T14:30:55Z'
  id: 45235709425553
  locale: ru
  section: Email service providers
  section_id: 6551247620881
  url: https://support.appsflyer.com/hc/ru/articles/45235709425553
---
> **Кратко:** Настройте интеграцию с Bloomreach, чтобы включить бесшовный диплинкинг из email-кампаний, измерять трафик как в Bloomreach, так и в AppsFlyer, а также создавать пользовательский опыт, который стимулирует конверсию.

<Image alt="Bloomreach + AppsFlyer.png" src="https://files.readme.io/842523ac61d5f702a451b361d435e794f8dedad0f54eecffdf27f596c2cab262-45298084947473.png" width="645px" />

## Об интеграции

Bloomreach — это платформа автоматизации email-маркетинга и поставщик услуг электронной почты (ESP), которая помогает брендам создавать персонализированный опыт по всем каналам.

Интеграция между AppsFlyer и Bloomreach обеспечивает плавный диплинкинг из email-кампаний, поддерживает точное измерение трафика как в Bloomreach, так и в AppsFlyer, а также помогает создавать бесшовный пользовательский опыт, который стимулирует конверсию.

## Настройка интеграции

Для настройки интеграции требуются действия как в AppsFlyer, так и в Bloomreach. Чтобы настроить интеграцию, выполните следующие действия:

<div id="step-1-in-appsflyer-create-and-configure-onelink" />

<Accordion title="Шаг 1. В AppsFlyer создайте и настройте OneLink">

Сначала настройте OneLink в AppsFlyer и убедитесь, что необходимые настройки хостинга и домена выполнены.

#### Когда приложение установлено

Определите поведение перенаправления для пользователей, у которых ваше приложение уже установлено.

**Чтобы настроить поведение при перенаправлении:**

1. <Anchor target="_blank" href="/marketers/ru/docs/create-a-onelink-template#создание-шаблонов-onelink">Создайте шаблон OneLink</Anchor> и настройте Universal Links/App Links. Этот шаблон будет использоваться позже для создания ссылок OneLink для ваших email-кампаний.
2. Если у вас уже есть существующий настроенный шаблон OneLink, который активирует ссылки Universal Links/App Links, вы можете использовать его.

#### Хостинг и SSL

* Ссылки OneLink защищены SSL и размещаются в AppsFlyer.
* Файл AASA и файлы App Links также размещаются в AppsFlyer.

См. <Anchor target="_blank" href="/marketers/ru/docs/set-up-your-esp-integration-with-appsflyer#настройка-приложения-для-поддержки-диплинкинга">дополнительную информацию и инструкции.</Anchor>

#### Определение домена приложения

Пример: для iOS определите связанный домен следующим образом:

```text
applinks:<your-onelink-subdomain>.onelink.me
```

См. <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_ios_init_setup#procedures-for-ios-universal-links">дополнительную информацию и инструкции.</Anchor>

</Accordion>

<div id="step-2-in-bloomreach-define-a-universal-link-domain" />

<Accordion title="Шаг 2. В Bloomreach определите домен универсальных ссылок">

Затем определите в Bloomreach домен универсальных ссылок, чтобы ссылки поддерживали диплинкинг и при этом их можно было измерять.

Домены, определенные в Bloomreach, не оборачиваются в CDN-ссылку для отслеживания кликов при использовании в email-кампании, что обеспечивает диплинкинг.

Чтобы включить измерение через веб- и мобильные SDK Bloomreach, к исходной ссылке Universal Link автоматически добавляется дополнительный параметр.

См. <Anchor target="_blank" href="https://documentation.bloomreach.com/engagement/docs/universal-link">дополнительную информацию и инструкции.</Anchor>

<Image alt="2026-03-31_09-28-18.png" src="https://files.readme.io/4058ab59e2622f26327d9a4a62fa8afdc5965210acba9d9c5bb7a62d53a05503-45298084948753.png" width="73.36%" />

> 📄 **Например**
>
> Ниже приведен пример необернутой универсальной ссылки с добавленными параметрами отслеживания Bloomreach:
>
> ```text
> https://engmntqa.onelink.me/LtRd?pid=ESP_Bloomreach&c=esp-campaign&is_retargeting=true&utm_source=bloomreach&utm_medium=email&utm_campaign=Test-severla-link-yossi-26-10&xnpe_cmp=.eJwzPNrmPEXT6ZZjVKC-flJ-SqV-SWJSTqp-CYRdpF-SQrxItHEslJuSWaafmMWTsWTZufIm9r61XAs2AABFBChI.jF6UMukHXiw5lw
> ```

</Accordion>

<div id="step-3-in-bloomreach-implement-mobile-and-web-sdks" />

<Accordion title="Шаг 3: В Bloomreach внедрите мобильные и веб-SDK">

Наконец, реализуйте соответствующие SDK Bloomreach, чтобы измерение кликов корректно работало в мобильных приложениях и в веб-среде.

#### https://support.appsflyer.com/hc/article_attachments/360016192917

Реализуйте <Anchor target="_blank" href="https://documentation.bloomreach.com/engagement/docs/mobile-sdks">мобильный SDK</Anchor> Bloomreach для iOS и убедитесь, что измерение универсальных ссылок настроено правильно. SDK Bloomreach поддерживает измерение универсальных ссылок, чтобы фиксировать взаимодействия пользователей, инициированные через email-кампании.

См. дополнительную информацию и инструкции по <Anchor target="_blank" href="https://documentation.bloomreach.com/engagement/docs/ios-sdk-universal-links#track-universal-links">Universal Links</Anchor> и <Anchor target="_blank" href="https://documentation.bloomreach.com/engagement/docs/mobile-sdks">мобильным SDK.</Anchor>

#### Android;

Реализуйте <Anchor target="_blank" href="https://documentation.bloomreach.com/engagement/docs/mobile-sdks">мобильный SDK</Anchor> Bloomreach для Android и настройте App Links аналогично универсальным ссылкам iOS, чтобы обеспечить согласованность атрибуции кликов и измерения.

См. дополнительную информацию и инструкции по <Anchor target="_blank" href="https://documentation.bloomreach.com/engagement/docs/android-sdk-app-links#track-android-app-links">Android App Links</Anchor> и <Anchor target="_blank" href="https://documentation.bloomreach.com/engagement/docs/mobile-sdks">мобильным SDK.</Anchor>

#### Веб

Реализуйте <Anchor target="_blank" href="https://Mobile%20SDKs">веб-SDK JavaScript</Anchor> Bloomreach, чтобы клики по универсальным ссылкам также измерялись на вашем сайте. Измерение кликов по универсальным ссылкам на вашем сайте будет работать без дополнительной настройки.

См. <Anchor target="_blank" href="https://documentation.bloomreach.com/engagement/docs/js-sdk">дополнительную информацию и инструкции.</Anchor>

</Accordion>

<div id="step-4-test-the-integration-by-sending-a-test-email" />

<Accordion title="Шаг 4: Протестируйте интеграцию">

После завершения настройки отправьте тестовое электронное письмо, чтобы проверить интеграцию и убедиться, что диплинкинг и измерение кликов работают как ожидается.

1. **Вставьте ссылку OneLink в тестовое электронное письмо и отправьте его себе.**

   С помощью редактора электронной почты в вашем ESP добавьте ссылку OneLink в тестовое электронное письмо и отправьте его себе. Убедитесь, что используется домен, настроенный на шаге 2, и что ссылка не обернута.
2. **Проверьте структуру ссылки.**

   Откройте тестовое электронное письмо и убедитесь, что OneLink не обернут Bloomreach. Кроме того, проверьте, что к ссылке добавлен параметр `xnpe_cmp`.
3. **Проверьте измерение кликов и поведение OneLink.**

   Со своего мобильного устройства откройте электронное письмо и нажмите на ссылку. Убедитесь, что:

   * Если приложение установлено, оно открывается и выполняется диплинкинг к ожидаемому контенту в приложении.
   * Клик отображается в дэшборде аналитики Bloomreach.

После завершения всех валидаций настройка интеграции будет завершена.

> 📘 **Примечание**
>
> Если клики не отображаются на платформе Bloomreach, обратитесь в службу поддержки Bloomreach.

</Accordion>

> 📘 **Вкладка «Затраты»**
>
> * AppsFlyer размещает и защищает все соответствующие файлы OneLink и association, включая файлы AASA и App Link.
> * Чтобы измерение ссылок работало, SDK Bloomreach для iOS, Android и JavaScript должны быть реализованы корректно.
> * Universal Links и App Links должны оставаться без обёртки, а параметры Bloomreach должны добавляться автоматически.
> * Эта интеграция обеспечивает точную атрибуцию кликов из email в приложение и из email в веб, а также измерение вовлеченности по разным каналам.

<div data-zendesk-anchors="about-the-integration=%D0%BE%D0%B1-%D0%B8%D0%BD%D1%82%D0%B5%D0%B3%D1%80%D0%B0%D1%86%D0%B8%D0%B8 h_01KMWVJR5AQRY8YRAD6ZV6H1VV=%D0%BE%D0%B1-%D0%B8%D0%BD%D1%82%D0%B5%D0%B3%D1%80%D0%B0%D1%86%D0%B8%D0%B8 set-up-the-integration=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-%D0%B8%D0%BD%D1%82%D0%B5%D0%B3%D1%80%D0%B0%D1%86%D0%B8%D0%B8 h_01KMWVJR5ACS7Q1GKP1GGGBRYK=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-%D0%B8%D0%BD%D1%82%D0%B5%D0%B3%D1%80%D0%B0%D1%86%D0%B8%D0%B8 h_01KMWVJR5ABTK766X4G0B9J92E=step-1-in-appsflyer-create-and-configure-onelink when-your-app-is-installed=%D0%BA%D0%BE%D0%B3%D0%B4%D0%B0-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D0%B5-%D1%83%D1%81%D1%82%D0%B0%D0%BD%D0%BE%D0%B2%D0%BB%D0%B5%D0%BD%D0%BE h_01KMWVJR5AY8WRV4Y6GTWHDE5D=%D0%BA%D0%BE%D0%B3%D0%B4%D0%B0-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D0%B5-%D1%83%D1%81%D1%82%D0%B0%D0%BD%D0%BE%D0%B2%D0%BB%D0%B5%D0%BD%D0%BE hosting-and-ssl=%D1%85%D0%BE%D1%81%D1%82%D0%B8%D0%BD%D0%B3-%D0%B8-ssl h_01KMWVJR5A40099PC91YW2QR1D=%D1%85%D0%BE%D1%81%D1%82%D0%B8%D0%BD%D0%B3-%D0%B8-ssl app-domain-definition=%D0%BE%D0%BF%D1%80%D0%B5%D0%B4%D0%B5%D0%BB%D0%B5%D0%BD%D0%B8%D0%B5-%D0%B4%D0%BE%D0%BC%D0%B5%D0%BD%D0%B0-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D1%8F h_01KMWVJR5A7JV0FHC5W1EP9502=%D0%BE%D0%BF%D1%80%D0%B5%D0%B4%D0%B5%D0%BB%D0%B5%D0%BD%D0%B8%D0%B5-%D0%B4%D0%BE%D0%BC%D0%B5%D0%BD%D0%B0-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D1%8F h_01KMWVJR5A57Y1ZPAYBC5321DX=step-2-in-bloomreach-define-a-universal-link-domain h_01KMWVJR5BER86B8YV3H60PGF6=%D0%BD%D0%B0%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%80 h_01KMWVJR5B6K6EG49VJM7JSEK2=step-3-in-bloomreach-implement-mobile-and-web-sdks ios=httpssupportappsflyercomhcarticle_attachments360016192917 h_01KMWVJR5B3505FSJSXRC9NQ4A=httpssupportappsflyercomhcarticle_attachments360016192917 h_01KMWVJR5BE703X877C40DZ5MX=android web=%D0%B2%D0%B5%D0%B1 h_01KMWVJR5BVTXS8W2WGTYEGP0D=%D0%B2%D0%B5%D0%B1 h_01KMWVJR5BPA0N2YTK2983DHMT=step-4-test-the-integration-by-sending-a-test-email h_01KMWVJR5B6PHSEK7NA5W8ZGNF=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%87%D0%B0%D0%BD%D0%B8%D0%B5 h_01KN1TCDE27DNPJJ8HRHZ4FPA0=%D0%B2%D0%BA%D0%BB%D0%B0%D0%B4%D0%BA%D0%B0-%D0%B7%D0%B0%D1%82%D1%80%D0%B0%D1%82%D1%8B" />
