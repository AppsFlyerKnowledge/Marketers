---
title: '[WIP] Об атрибуции органического поиска и органических ответов ИИ'
deprecated: false
hidden: false
metadata:
  keywords:
    - Marketers
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - Marketers
  created_at: '2026-11-01T17:06:19Z'
  edited_at: '2026-11-02T13:55:21Z'
  id: 52556274395537
  locale: ru
  section: Attribution concepts
  section_id: 6551394235409
  url: https://support.appsflyer.com/hc/ru/articles/52556274395537
---
> **At a glance:** Используйте атрибуцию органического поиска (SEO) и органических ответов ИИ (AEO), чтобы увидеть, какие поисковые системы и системы ответов ИИ приводят неоплаченный трафик на ваш сайт и в приложение. Атрибутируйте им веб-конверсии, установки приложений и повторные вовлечения.

<div id="about-seo-and-aeo-attribution" />

## Об атрибуции SEO и AEO

Пользователь выполняет поиск в Google или задает вопрос ChatGPT, а затем кликает по результату, который ведет на ваш сайт. AppsFlyer атрибутирует поисковой системе или системе ответов ИИ визиты и конверсии на вашем сайте, установки приложения и открытия приложения.

<div id="supported-user-journeys" />

## Поддерживаемые пути пользователя

Каждый путь начинается, когда пользователь выполняет поиск в поддерживаемой поисковой системе или задает вопрос поддерживаемой системе ответов ИИ. Если ответ содержит неоплачиваемую ссылку и пользователь кликает по ней, далее следует один из трех путей:

| Путь | Что измеряет AppsFlyer | Требуемая реализация |
| --- | --- | --- |
| Пользователь попадает на ваш сайт | Веб-посещения и веб-конверсии, например регистрации и покупки | SDK AppsFlyer для веб-атрибуции или server-to-server (S2S) интеграция |
| Пользователь попадает на ваш сайт, а затем нажимает кнопку загрузки, которая ведет в магазин приложений | установки приложения | Мобильный SDK AppsFlyer и Smart Script версии 2.10.3 или выше, с включенной опцией **Media source for organic search installs** |
| Пользователь попадает на ваш сайт и сразу переходит в уже установленное приложение | Повторные вовлечения в приложении (открытия приложения) | SDK AppsFlyer для Android и iOS версии 6.12.1 или выше, а также Android App Links и iOS Universal Links |

<div id="use-case-1-web-measurement" />

## Кейс 1: веб-измерение

Атрибутируйте посещения сайта и конверсии поисковой системе или AI answer engine, откуда пришел пользователь.

**Необходимые условия:**

* SDK AppsFlyer для веб-атрибуции или server-to-server (S2S) интеграция. Узнать больше: <Anchor target="_blank" href="/marketers/ru/docs/web-performance-measurement-overview">Web Performance Measurement — обзор</Anchor>.

**Как это работает:**

1. Пользователь кликает по неплатному результату поиска или ссылке в AI-ответе и попадает на ваш сайт.
2. SDK веб-атрибуции или S2S-интеграция считывает веб-реферер — поле, которое показывает, откуда пришел пользователь. AppsFlyer атрибутирует веб-посещение соответствующему SEO- или AEO-медиаисточнику.
3. Если позже пользователь выполняет значимое действие, например регистрируется или совершает покупку, AppsFlyer атрибутирует событие этой поисковой системе или AI answer engine.

<Image align="center" alt="Google Chrome 2026-11-01 19.17.00.png" src="https://files.readme.io/1188ff2a1b87b4ae825c6a2e2d1d67d7663cd526b1a3cfce7107265886d457a1-52589945729553.png" width="2266px" />

Узнать больше об <Anchor target="_blank" href="/marketers/ru/docs/about-traffic-source-resolution#шаг-2-определение-медиаисточников">определении источника трафика</Anchor>.

<div id="use-case-2-app-install-measurement" />

## Кейс 2: измерение установок приложения

Атрибутируйте установки приложения поисковой системе или AI answer engine, которая направила пользователя на ваш сайт.

**Необходимые условия:**

* Мобильный SDK AppsFlyer
* AppsFlyer Smart Script версии 2.10.3 или выше, с включенной опцией **Media source for organic search installs**

**Как это работает:**

1. Пользователь кликает по неплатному результату поиска или ссылке в AI-ответе и попадает на ваш сайт.
2. На странице отображается кнопка загрузки со Smart Script. У пользователя не установлено ваше приложение, поэтому кнопка направляет его в магазин приложений.
3. Smart Script создает ссылку атрибуции AppsFlyer. Ее медиаисточник (`pid`) определяется на основе веб-реферера, то есть страницы, с которой пришел пользователь. Например, пользователь приходит с google.com, и у визита нет признаков платного трафика (`pid`, параметры UTM, `gclid`, `gbraid` или `wbraid`). Тогда Smart Script может задать `pid=google_organic_seo`.
4. Пользователь устанавливает приложение и открывает его в первый раз. AppsFlyer может атрибутировать установку этому клику и засчитать ее поисковой системе или AI-системе ответов, которая направила пользователя на ваш сайт.

<Image align="center" alt="Google Chrome 2026-11-01 19.18.06.png" src="https://files.readme.io/3e6db22edfc5f8a22fd32c0167d1d0868a65097aaf9b6967f5c1162b40ebb85f-52589954515089.png" width="2250px" />

Узнайте больше о <Anchor target="_blank" href="/marketers/ru/docs/set-up-smart-script-to-convert-web-visitors#seo-referrer-mapping">настройке Smart Scripts для конвертации посетителей сайта</Anchor>.

<div id="use-case-3-app-re-engagement-measurement" />

## Кейс 3: измерение повторного вовлечения в приложение

Атрибутируйте открытия приложения пользователями, у которых ваше приложение уже установлено.

**Необходимые условия:**

* AppsFlyer SDK для Android и iOS версии 6.12.1 или выше
* Контент сайта сопоставлен с контентом приложения с помощью Android App Links и iOS Universal Links

**Как это работает:**

1. Пользователь кликает по неоплачиваемому результату поиска или ссылке в AI-ответе.
2. Контент вашего сайта сопоставлен с вашим приложением, и у пользователя установлено приложение. Ссылка сразу открывает приложение на соответствующем контенте.
3. Приложение открывается через диплинк. Веб-реферер, то есть страница, с которой пришел пользователь, отправляется в AppsFlyer. AppsFlyer использует его, чтобы атрибутировать открытие приложения соответствующей поисковой системе или AI-сервису ответов.

<Image align="center" alt="Google Chrome 2026-11-01 19.18.53.png" src="https://files.readme.io/36363bbe8d74921f5c286b600f7e25daa91746fd8f2d217cf74c84ae43d4b528-52589954523025.png" width="2227px" />

Узнайте больше о <Anchor target="_blank" href="/marketers/ru/docs/set-up-organic-search-seo-and-organic-ai-answers-aeo-re-engagement-attribution">настройке атрибуции повторного вовлечения для органического поиска (SEO) и органических ответов ИИ (AEO)</Anchor>.

<div id="data-availability" />

## Доступность данных

SEO- и AEO-трафик отображается в AppsFlyer следующим образом:

* **Дэшборды и отчеты:** поисковые системы отображаются как `<search engine>_organic_seo`, например `google_organic_seo`. AI-сервисы ответов отображаются как `<AI engine>_organic_aeo`, например `chatgpt_organic_aeo`.
* **Отчеты о сырых данных:** поле `channel` имеет значение `seo` для трафика из поисковых систем и `aeo` для трафика из AI-сервисов ответов.

<div id="supported-search-engines-and-ai-answer-engines" />

## Поддерживаемые поисковые системы и AI-сервисы ответов

AppsFlyer атрибутирует трафик от следующих систем.

**Поисковые системы:** Google, Bing, Yahoo, Ask, DuckDuckGo, Yandex, Naver, Daum, Baidu, Ecosia, Coccoc, Sogou и Yahoo Япония.

**ИИ-системы ответов:** ChatGPT, Claude, Perplexity, Manus, Copilot, Gemini, Grok и DeepSeek.

<div id="faq" />

## Часто задаваемые вопросы

<div id="is-there-an-additional-fee-for-seo-and-aeo-attribution" />

### Взимается ли дополнительная плата за атрибуцию SEO и AEO?

№ Это включено в вашу подписку. Органические конверсии учитываются в вашем пакете так же, как и неорганические конверсии.

<div id="can-i-customize-the-seo-or-aeo-media-source-name" />

### Можно ли настроить имя медиаисточника SEO или AEO?

№ AppsFlyer задает имя медиаисточника.

<div id="does-appsflyer-attribute-an-install-when-the-user-taps-an-install-button-shown-in-the-search-results" />

### Атрибутирует ли AppsFlyer установку, когда пользователь нажимает кнопку установки в результатах поиска?

№ В этом сценарии AppsFlyer не может собрать информацию, необходимую для Атрибуции.

<div id="is-keyword-search-term-or-prompt-data-available" />

### Доступны ли данные по ключевому слову, поисковому запросу или запросу prompt?

№ Веб-реферер не включает эту информацию.

<div id="see-also" />

## См.также

* <Anchor target="_blank" href="/marketers/ru/docs/about-traffic-source-resolution">[Бета] Об определении источника трафика</Anchor>
* <Anchor target="_blank" href="/marketers/ru/docs/set-up-smart-script-to-convert-web-visitors">Настройте Smart Script для конверсии посетителей сайта</Anchor>
* <Anchor target="_blank" href="/marketers/ru/docs/set-up-organic-search-seo-and-organic-ai-answers-aeo-re-engagement-attribution">Настройка атрибуции повторного вовлечения для органического поиска (SEO) и органических ответов ИИ (AEO)</Anchor>
* <Anchor target="_blank" href="/marketers/ru/docs/appsflyer-attribution-model">Модель атрибуции AppsFlyer</Anchor>

<div data-zendesk-anchors="h_01M6C15DBDG1JVJ11WZ2ZB5A0R=%D0%BE%D0%B1-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D0%B8-seo-%D0%B8-aeo h_01M6C15DBDFD0H52Y2V2X9J89K=%D0%BF%D0%BE%D0%B4%D0%B4%D0%B5%D1%80%D0%B6%D0%B8%D0%B2%D0%B0%D0%B5%D0%BC%D1%8B%D0%B5-%D0%BF%D1%83%D1%82%D0%B8-%D0%BF%D0%BE%D0%BB%D1%8C%D0%B7%D0%BE%D0%B2%D0%B0%D1%82%D0%B5%D0%BB%D1%8F h_01M6C15DBDKJH8NN771ED3ZWVX=%D0%BA%D0%B5%D0%B9%D1%81-1-%D0%B2%D0%B5%D0%B1-%D0%B8%D0%B7%D0%BC%D0%B5%D1%80%D0%B5%D0%BD%D0%B8%D0%B5 h_01M6C15DBDY5Y4KM23NBYN12RH=%D0%BA%D0%B5%D0%B9%D1%81-2-%D0%B8%D0%B7%D0%BC%D0%B5%D1%80%D0%B5%D0%BD%D0%B8%D0%B5-%D1%83%D1%81%D1%82%D0%B0%D0%BD%D0%BE%D0%B2%D0%BE%D0%BA-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D1%8F h_01M6C15DBDK3HC4SD9X9V7BGWD=%D0%BA%D0%B5%D0%B9%D1%81-3-%D0%B8%D0%B7%D0%BC%D0%B5%D1%80%D0%B5%D0%BD%D0%B8%D0%B5-%D0%BF%D0%BE%D0%B2%D1%82%D0%BE%D1%80%D0%BD%D0%BE%D0%B3%D0%BE-%D0%B2%D0%BE%D0%B2%D0%BB%D0%B5%D1%87%D0%B5%D0%BD%D0%B8%D1%8F-%D0%B2-%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D0%B5 h_01M6C15DBDSSBM7JK28KT01EA9=%D0%B4%D0%BE%D1%81%D1%82%D1%83%D0%BF%D0%BD%D0%BE%D1%81%D1%82%D1%8C-%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D1%85 h_01M6C15DBDQSE84ZGBJ7EBHR99=%D0%BF%D0%BE%D0%B4%D0%B4%D0%B5%D1%80%D0%B6%D0%B8%D0%B2%D0%B0%D0%B5%D0%BC%D1%8B%D0%B5-%D0%BF%D0%BE%D0%B8%D1%81%D0%BA%D0%BE%D0%B2%D1%8B%D0%B5-%D1%81%D0%B8%D1%81%D1%82%D0%B5%D0%BC%D1%8B-%D0%B8-ai-%D1%81%D0%B5%D1%80%D0%B2%D0%B8%D1%81%D1%8B-%D0%BE%D1%82%D0%B2%D0%B5%D1%82%D0%BE%D0%B2 h_01M6C15DBDFQ4R4CE8021ANQ8Z=%D1%87%D0%B0%D1%81%D1%82%D0%BE-%D0%B7%D0%B0%D0%B4%D0%B0%D0%B2%D0%B0%D0%B5%D0%BC%D1%8B%D0%B5-%D0%B2%D0%BE%D0%BF%D1%80%D0%BE%D1%81%D1%8B h_01M6C15DBDP74VR7JTPMMDP91H=%D0%B2%D0%B7%D0%B8%D0%BC%D0%B0%D0%B5%D1%82%D1%81%D1%8F-%D0%BB%D0%B8-%D0%B4%D0%BE%D0%BF%D0%BE%D0%BB%D0%BD%D0%B8%D1%82%D0%B5%D0%BB%D1%8C%D0%BD%D0%B0%D1%8F-%D0%BF%D0%BB%D0%B0%D1%82%D0%B0-%D0%B7%D0%B0-%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%86%D0%B8%D1%8E-seo-%D0%B8-aeo h_01M6C15DBDSVC2E5HTRPJ27PM2=%D0%BC%D0%BE%D0%B6%D0%BD%D0%BE-%D0%BB%D0%B8-%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B8%D1%82%D1%8C-%D0%B8%D0%BC%D1%8F-%D0%BC%D0%B5%D0%B4%D0%B8%D0%B0%D0%B8%D1%81%D1%82%D0%BE%D1%87%D0%BD%D0%B8%D0%BA%D0%B0-seo-%D0%B8%D0%BB%D0%B8-aeo h_01M6C15DBD6Q000S8S8VZ2PEK9=%D0%B0%D1%82%D1%80%D0%B8%D0%B1%D1%83%D1%82%D0%B8%D1%80%D1%83%D0%B5%D1%82-%D0%BB%D0%B8-appsflyer-%D1%83%D1%81%D1%82%D0%B0%D0%BD%D0%BE%D0%B2%D0%BA%D1%83-%D0%BA%D0%BE%D0%B3%D0%B4%D0%B0-%D0%BF%D0%BE%D0%BB%D1%8C%D0%B7%D0%BE%D0%B2%D0%B0%D1%82%D0%B5%D0%BB%D1%8C-%D0%BD%D0%B0%D0%B6%D0%B8%D0%BC%D0%B0%D0%B5%D1%82-%D0%BA%D0%BD%D0%BE%D0%BF%D0%BA%D1%83-%D1%83%D1%81%D1%82%D0%B0%D0%BD%D0%BE%D0%B2%D0%BA%D0%B8-%D0%B2-%D1%80%D0%B5%D0%B7%D1%83%D0%BB%D1%8C%D1%82%D0%B0%D1%82%D0%B0%D1%85-%D0%BF%D0%BE%D0%B8%D1%81%D0%BA%D0%B0 h_01M6C15DBDQ2JPM01NX82N110A=%D0%B4%D0%BE%D1%81%D1%82%D1%83%D0%BF%D0%BD%D1%8B-%D0%BB%D0%B8-%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D0%B5-%D0%BF%D0%BE-%D0%BA%D0%BB%D1%8E%D1%87%D0%B5%D0%B2%D0%BE%D0%BC%D1%83-%D1%81%D0%BB%D0%BE%D0%B2%D1%83-%D0%BF%D0%BE%D0%B8%D1%81%D0%BA%D0%BE%D0%B2%D0%BE%D0%BC%D1%83-%D0%B7%D0%B0%D0%BF%D1%80%D0%BE%D1%81%D1%83-%D0%B8%D0%BB%D0%B8-%D0%B7%D0%B0%D0%BF%D1%80%D0%BE%D1%81%D1%83-prompt h_01M6C15DBD6442ATGZVZNZKGJ9=%D1%81%D0%BC%D1%82%D0%B0%D0%BA%D0%B6%D0%B5" />
