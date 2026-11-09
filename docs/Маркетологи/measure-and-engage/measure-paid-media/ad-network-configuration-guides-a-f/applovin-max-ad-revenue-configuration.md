---
title: Настройка конфигурации дохода от рекламы AppLovin MAX
metadata:
  keywords:
    - Ad Network
    - Advertisers
    - Marketers
    - ROI360
    - Ad Networks
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-michael-talapov
    - Marketers
    - ROI360
    - Ad Networks
  created_at: '2020-01-09T10:53:21Z'
  edited_at: '2026-08-31T00:24:18Z'
  id: 360004707378
  locale: ru
  section: Ad network configuration guides (A-F)
  section_id: 6551990971793
  url: https://support.appsflyer.com/hc/ru/articles/360004707378
---
> **Краткий обзор:** AppLovin MAX, интегрированный партнер AppsFlyer, предоставляет владельцам приложений решения для получения дохода от рекламы.

<Image align="center" alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/applovinmax.png" width="265px" />

<div id="setting-up-applovin-max-integration" />

## Настройка интеграции Applovin MAX

**Необходимые условия.** Перед настройкой интеграции необходимо <Anchor target="_blank" href="/marketers/ru/docs/partner-integrations#contact-details">связаться с партнером</Anchor> и открыть у него аккаунт.

**Чтобы активировать интеграцию:**

1. **Чтобы активировать:** В AppsFlyer в боковом меню выберите**Сотрудничество** > **Маркетплейс партнеров**.  
   **Чтобы изменить**: В боковом меню AppsFlyer выберите **Сотрудничество** > **Активные интеграции**.
2. Выберите соответствующее приложение.
3. Нажмите **Настроить интеграцию**.
4. При **первом заходе** сюда включите **Активацию партнера**, чтобы настройка параметров на вкладке интеграции стала возможной.   
   **Важное примечание:** переключатель **должен оставаться включенным (активным), пока вы работаете с партнером**. <Anchor target="_blank" href="/marketers/ru/docs/partner-activation-deactivation">Узнать больше</Anchor>
5. Завершите настройку, используя соответствующие вкладки, как описано ниже.

<div id="setting-tabs" />

### Вкладки настроек

При необходимости обновите содержимое вкладок настроек: доход от рекламы.

<div id="ad-revenue" />

<Accordion title="Дата и время">

AppLovin MAX обеспечивает медиацию дохода от рекламы с агрегированными данными на уровне устройства.

<div id="note" />

> 📘 **Примечание:**
>
> * Доход от рекламы для платформы Fire OS не отображается в отчетности AppsFlyer.
> * Узнать больше об <Anchor target="_blank" href="/marketers/ru/docs/roi360-guide-ad-revenue-attribution">атрибуции дохода от рекламы</Anchor> (монетизации рекламы).

**Чтобы включить API доходов от рекламы**:

* Следуйте <Anchor target="_blank" href="/marketers/ru/docs/roi360-guide-ad-revenue-attribution#connect-to-ad-revenue-integrated-partners">этим инструкциям по интеграции</Anchor>.

</Accordion>

<div id="best-practice" />

### Практические рекомендации:

Если вы монетизируете с помощью рекламы Meta и используете AppLovin Max, лучше не настраивать прямую интеграцию дохода от рекламы Facebook с AppsFlyer. Так вы будете получать данные на уровне пользователя. Если у вас настроена прямая интеграция дохода от рекламы Facebook, данные будут на агрегированном уровне.

<div data-zendesk-anchors="setting-up-applovin-max-integration=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-%D0%B8%D0%BD%D1%82%D0%B5%D0%B3%D1%80%D0%B0%D1%86%D0%B8%D0%B8-applovin-max 01EZPC55J2HP7DPGR3HADZXRFK=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-%D0%B8%D0%BD%D1%82%D0%B5%D0%B3%D1%80%D0%B0%D1%86%D0%B8%D0%B8-applovin-max setting-tabs=%D0%B2%D0%BA%D0%BB%D0%B0%D0%B4%D0%BA%D0%B8-%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B5%D0%BA 01EV471WS4J9B4374GXA5R5WXM=%D0%B2%D0%BA%D0%BB%D0%B0%D0%B4%D0%BA%D0%B8-%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B5%D0%BA 01EV471WS4S7KE1GHQAJNYR5FR=ad-revenue h_01HFVAPG2CEQMRFN7HZZ2H8J3M=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%87%D0%B0%D0%BD%D0%B8%D0%B5 best-practice=%D0%BF%D1%80%D0%B0%D0%BA%D1%82%D0%B8%D1%87%D0%B5%D1%81%D0%BA%D0%B8%D0%B5-%D1%80%D0%B5%D0%BA%D0%BE%D0%BC%D0%B5%D0%BD%D0%B4%D0%B0%D1%86%D0%B8%D0%B8 01FBGVR4ZAMKSHBMFCPAZVHH6A=%D0%BF%D1%80%D0%B0%D0%BA%D1%82%D0%B8%D1%87%D0%B5%D1%81%D0%BA%D0%B8%D0%B5-%D1%80%D0%B5%D0%BA%D0%BE%D0%BC%D0%B5%D0%BD%D0%B4%D0%B0%D1%86%D0%B8%D0%B8" />
