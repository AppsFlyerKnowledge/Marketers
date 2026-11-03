---
title: Тестирование интеграции tvOS перед публикацией
metadata:
  keywords:
    - Testing
    - tvos
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
  created_at: '2016-07-12T09:49:14Z'
  edited_at: '2026-10-19T14:11:10Z'
  id: 211758923
  locale: ru
  section: iOS platform
  section_id: 6551263106577
  url: https://support.appsflyer.com/hc/ru/articles/211758923
---
> **Кратко:** смоделируйте неорганическую установку на устройстве AppleTV с помощью тестового приложения tvOS.

## Информация о компании

В AppleTV нет браузера. Поэтому вы не можете выполнить тест кликов или установок на устройстве для **неопубликованного** приложения. (Для **опубликованных** приложений вы можете <Anchor target="_blank" href="/marketers/ru/docs/testing-the-sdk-integration-for-marketers#тестирование-с-помощью-ссылок-атрибуции">выполнить тест с использованием ссылок атрибуции</Anchor>).

Чтобы выполнить тест атрибуции для неопубликованных приложений, вы можете использовать **тестовое приложение tvOS.**

### Как работает тестовое приложение tvOS?

Тестовое приложение tvOS позволяет смоделировать клик по ссылке атрибуции на устройстве AppleTV, чтобы затем установить приложение и получить неорганическую атрибуцию.

**Чтобы протестировать атрибуцию с помощью тестового приложения tvOS:**

1. Загрузите проект <Anchor target="_blank" href="https://github.com/AppsFlyerSDK/AppsFlyerFramework">здесь</Anchor>.
2. В Xcode соберите проект для тестового устройства AppleTV.

   На экране появится такое окно:

   ![](https://files.readme.io/7ed3c5e8165e6d27c9d87db8b026c0898536b145def6bfedd0dc5f78c7804669-205289963.png)
3. <Anchor target="_blank" href="/marketers/ru/docs/registering-test-devices">Зарегистрируйте</Anchor> устройство AppleTV как тестовое устройство, используя **IDFA**, который отображается внизу экрана приложения.
4. В тестовом приложении введите AppID так, как он указан на дэшборде вашего приложения.

   Убедитесь, что тестируемое приложение **не установлено** на устройстве. Чтобы получить неорганическую атрибуцию, необходимо смоделировать реальный сценарий, при котором клик по ссылке атрибуции происходит до открытия приложения при **первом** **запуске**.
5. Нажмите кнопку **Click Simulation** и дождитесь ответа.

   Если все данные корректны, отображается следующее сообщение:

   ![](https://files.readme.io/27b8b5acfe9691d3704ae36b04e28ecaa643e1b68eb5e0a6f8be70f657b2c0d3-205275743.png)
6. **Установите** интегрированное приложение на устройство.

   Если интеграция настроена правильно, на дэшборде отобразится неорганическая атрибуция в медиаисточнике **AppsFlyer\_Test**.

   ![](https://files.readme.io/4c6ab66ebd13556bd764d4e93adbb639be208b8955dd1fe1d3dd60ecd5c01a3b-205275823.png)

<div data-zendesk-anchors="overview=%D0%B8%D0%BD%D1%84%D0%BE%D1%80%D0%BC%D0%B0%D1%86%D0%B8%D1%8F-%D0%BE-%D0%BA%D0%BE%D0%BC%D0%BF%D0%B0%D0%BD%D0%B8%D0%B8 how-does-the-tvos-test-app-work=%D0%BA%D0%B0%D0%BA-%D1%80%D0%B0%D0%B1%D0%BE%D1%82%D0%B0%D0%B5%D1%82-%D1%82%D0%B5%D1%81%D1%82%D0%BE%D0%B2%D0%BE%D0%B5-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D0%B5-tvos" />
