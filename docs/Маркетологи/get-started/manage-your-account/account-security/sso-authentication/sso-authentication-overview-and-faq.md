---
title: Аутентификация SSO — обзор и вопросы и ответы
metadata:
  keywords:
    - Marketers
    - Platform essentials
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-negri
    - Marketers
    - Platform essentials
  created_at: '2024-08-11T07:54:46Z'
  edited_at: '2026-08-19T00:16:28Z'
  id: 27434547337617
  locale: ru
  section: SSO authentication
  section_id: 20162151531793
  url: https://support.appsflyer.com/hc/ru/articles/27434547337617
---
> **Кратко:** Узнайте об аутентификации с единым входом (SSO) и о процессе входа в AppsFlyer через вашего поставщика идентификационных данных (IdP) с помощью SSO. Найдите ответы на часто задаваемые вопросы о входе через SSO.

<div id="what-is-sso-authentication" />

## Что такое технология единого входа (SSO)?

SSO — это метод аутентификации, который позволяет пользователям получать доступ к нескольким независимым приложениям, системам или платформам, войдя в систему один раз через сервис поставщика идентификационных данных (например, Okta, Azure AD или OneLogin). Добавление AppsFlyer в ваш сервис IdP позволяет пользователям входить в AppsFlyer непосредственно через вашего поставщика идентификационных данных с помощью технологии единого входа (SSO). Это позволяет вашим пользователям автоматически входить в систему с более **безопасной аутентификацией** и использовать только один набор учетных данных.

<div id="how-does-sso-authentication-work" />

## Как работает технология единого входа (SSO)?

Платформа AppsFlyer поддерживает верификацию посредством SSO с использованием протокола SAML2.0. Внедрив сертификат аутентификации AppsFlyer в ваш сервис поставщика идентификационных данных SAML 2.0, ваш поставщик идентификационных данных генерирует токен с аутентифицированными данными пользователя. Тот же процесс выполняется со стороны вашего IdP в отношении AppsFlyer — его токен внедряется в AppsFlyer.

<div id="the-appsflyer-service-provider-authentication-certificate" />

## Сертификат аутентификации AppsFlyer (поставщика услуг)

AppsFlyer предоставляет сертификат шифрования для шифрования данных и подписи запроса SSO. Вы можете выбрать, какой сертификат использовать:

* **Сертификат, подписанный AppsFlyer:** Сертификат AppsFlyer, созданный на основе <Anchor target="_blank" href="https://hq1.appsflyer.com/auth/sso-metadata">URL-адреса метаданных AppsFlyer</Anchor>
* **Сертификат, подписанный CA:** Сертификат AppsFlyer, **подписанный Amazon**.

<div id="note" />

> 📘 **Примечание**
>
> AppsFlyer не поддерживает отрицательные серийные номера сертификата.

<div id="troubleshooting-and-faq" />

## Устранение неполадок и часто задаваемые вопросы

<div id="can-users-log-in-using-both-sso-and-2fa-methods" />

<Accordion title="Могут ли пользователи авторизоваться как с помощью SSO, так и с помощью 2FA?">

Одновременно можно использовать только один безопасный метод входа: SSO или 2FA.

* **Чтобы активировать метод 2FA, когда активен SSO:** сначала деактивируйте SSO, затем активируйте 2FA
* **Чтобы активировать SSO, когда активен 2FA:** сначала деактивируйте 2FA, затем активируйте SSO

</Accordion>

<div id="why-cant-some-users-connect-using-sso" />

<Accordion title="Почему некоторые пользователи не могут подключиться с помощью технологии единого входа?">

Убедитесь, что все адреса электронной почты пользователей настроены в обеих системах— в вашем сервисе поставщика идентификационных данных и на платформе AppsFlyer. Если причина не в этом, обратитесь к своему менеджеру по работе с клиентами, чтобы узнать причину и способы устранения проблемы. Тем временем ваш менеджер по работе с клиентами может временно отключить параметр **Принудительный вход через SSO**, чтобы пользователи могли входить в систему с помощью электронной почты и пароля.

</Accordion>

<div id="do-i-need-a-test-environment-to-test-setup-before-pushing-to-production" />

<Accordion title="Нужна ли тестовая среда для тестирования настройки перед установкой конфигурации?">

Тестовая среда не требуется. Следуйте инструкциям в шаге 3, чтобы протестировать вход через SSO — либо со стороны IdP, либо со стороны поставщика услуг (AppsFlyer).

</Accordion>

<div id="what-should-i-do-before-the-appsflyer-certificate-expires" />

<Accordion title="Что мне нужно сделать до истечения срока действия сертификата AppsFlyer?">

AppsFlyer через платформу предупредит вас о том, что срок действия вашего сертификата SSO AppsFlyer истекает. Выполните следующие действия, чтобы внедрить новый сертификат AppsFlyer:

1. [Создайте новый файл сертификата с обновленным ключом шифрования](#how-to-create-the-appsflyer-certificate-file).
2. Перейдите к своему поставщику идентификационных данных и внедрите новый сертификат AppsFlyer.
3. После внедрения вернитесь в раздел **Единый вход (SSO)**, нажмите **Подтвердить внедрение сертификата** и подтвердите, что вы обновили актуальный сертификат AppsFlyer.

</Accordion>

<div id="how-can-i-unselect-the-force-sso-login-option" />

<Accordion title="Принудительный вход через SSO отключен, как я могу его включить?">

После выбора параметра **Принудительный вход через SSO** и сохранения конфигурации этот параметр становится недоступным. Чтобы снова включить **Принудительный вход через SSO**, вам потребуется заново выполнить настройку на <Anchor target="_blank" href="/marketers/ru/docs/set-up-sso-authentication-with-your-identity-provider-idp#step-2-complete-the-configuration-at-appsflyer">шаге 2</Anchor> процесса SSO с самого начала.

<div id="note-1" />

> 📘 **Примечание**
>
> Рекомендуется оставить выбранным параметр **Принудительный вход через SSO**, чтобы обеспечить более безопасный вход в систему. Это означает, что пользователи, пытающиеся войти в систему, аутентифицируются поставщиком идентификационных данных и не могут войти в систему только при помощи своего имени пользователя и пароля.

</Accordion>

<div id="is-it-required-to-use-the-appsflyer-certificate-in-my-idp" />

<Accordion title="Обязательно ли использовать сертификат AppsFlyer в моем IdP?">

Внедрение сертификата AppsFlyer в ваш IdP **настоятельно рекомендуется**, но не является обязательным. Для некоторых поставщиков идентификационных данных, таких как Google Workspace и Microsoft Entra ID, по умолчанию не требуется сертификат поставщика услуг.

</Accordion>

<div id="what-happens-when-i-deactivate-sso-and-how-do-i-do-it" />

<Accordion title="Что происходит при отключении SSO и как это сделать?">

При отключении аутентификации через SSO пользователи смогут входить в систему другими способами, например с помощью имени пользователя и пароля AppsFlyer, а также с помощью метода <Anchor target="_blank" href="/marketers/ru/docs/implementing-and-using-2fa-login">2FA</Anchor>.

1. На верхней панели откройте меню аккаунта (выпадающее меню адреса электронной почты администратора) > **Центр безопасности**.
2. В разделе **Повышенная безопасность входа в систему**выберите **Настройка способа входа в систему**.
3. В разделе **Единый вход (SSO)** выключите переключатель **Единый вход**.

</Accordion>

<div id="can-i-have-negative-serial-numbers-in-the-certificate" />

<Accordion title="Можно ли использовать отрицательные серийные номера в сертификате?">

№ № AppsFlyer не поддерживает отрицательные серийные номера сертификата.

</Accordion>

<div data-zendesk-anchors="what-is-sso=%D1%87%D1%82%D0%BE-%D1%82%D0%B0%D0%BA%D0%BE%D0%B5-%D1%82%D0%B5%D1%85%D0%BD%D0%BE%D0%BB%D0%BE%D0%B3%D0%B8%D1%8F-%D0%B5%D0%B4%D0%B8%D0%BD%D0%BE%D0%B3%D0%BE-%D0%B2%D1%85%D0%BE%D0%B4%D0%B0-sso h_01J5QR4DE5EBSVWHXXENZTRPWQ=%D1%87%D1%82%D0%BE-%D1%82%D0%B0%D0%BA%D0%BE%D0%B5-%D1%82%D0%B5%D1%85%D0%BD%D0%BE%D0%BB%D0%BE%D0%B3%D0%B8%D1%8F-%D0%B5%D0%B4%D0%B8%D0%BD%D0%BE%D0%B3%D0%BE-%D0%B2%D1%85%D0%BE%D0%B4%D0%B0-sso how-does-sso-authentication-work=%D0%BA%D0%B0%D0%BA-%D1%80%D0%B0%D0%B1%D0%BE%D1%82%D0%B0%D0%B5%D1%82-%D1%82%D0%B5%D1%85%D0%BD%D0%BE%D0%BB%D0%BE%D0%B3%D0%B8%D1%8F-%D0%B5%D0%B4%D0%B8%D0%BD%D0%BE%D0%B3%D0%BE-%D0%B2%D1%85%D0%BE%D0%B4%D0%B0-sso h_01HCHG901WVRX1MKNB0KF02PSJ=%D0%BA%D0%B0%D0%BA-%D1%80%D0%B0%D0%B1%D0%BE%D1%82%D0%B0%D0%B5%D1%82-%D1%82%D0%B5%D1%85%D0%BD%D0%BE%D0%BB%D0%BE%D0%B3%D0%B8%D1%8F-%D0%B5%D0%B4%D0%B8%D0%BD%D0%BE%D0%B3%D0%BE-%D0%B2%D1%85%D0%BE%D0%B4%D0%B0-sso the-authentication-certificate=%D1%81%D0%B5%D1%80%D1%82%D0%B8%D1%84%D0%B8%D0%BA%D0%B0%D1%82-%D0%B0%D1%83%D1%82%D0%B5%D0%BD%D1%82%D0%B8%D1%84%D0%B8%D0%BA%D0%B0%D1%86%D0%B8%D0%B8-appsflyer-%D0%BF%D0%BE%D1%81%D1%82%D0%B0%D0%B2%D1%89%D0%B8%D0%BA%D0%B0-%D1%83%D1%81%D0%BB%D1%83%D0%B3 h_01HCHG901WG05TP2NJBJRDRWPN=%D1%81%D0%B5%D1%80%D1%82%D0%B8%D1%84%D0%B8%D0%BA%D0%B0%D1%82-%D0%B0%D1%83%D1%82%D0%B5%D0%BD%D1%82%D0%B8%D1%84%D0%B8%D0%BA%D0%B0%D1%86%D0%B8%D0%B8-appsflyer-%D0%BF%D0%BE%D1%81%D1%82%D0%B0%D0%B2%D1%89%D0%B8%D0%BA%D0%B0-%D1%83%D1%81%D0%BB%D1%83%D0%B3 h_01JJH8DC3AHNC6GST0S41X8MFV=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%87%D0%B0%D0%BD%D0%B8%D0%B5 faq=%D1%83%D1%81%D1%82%D1%80%D0%B0%D0%BD%D0%B5%D0%BD%D0%B8%D0%B5-%D0%BD%D0%B5%D0%BF%D0%BE%D0%BB%D0%B0%D0%B4%D0%BE%D0%BA-%D0%B8-%D1%87%D0%B0%D1%81%D1%82%D0%BE-%D0%B7%D0%B0%D0%B4%D0%B0%D0%B2%D0%B0%D0%B5%D0%BC%D1%8B%D0%B5-%D0%B2%D0%BE%D0%BF%D1%80%D0%BE%D1%81%D1%8B h_01HCHG901XSAQ7HSGM0ZVT7B70=%D1%83%D1%81%D1%82%D1%80%D0%B0%D0%BD%D0%B5%D0%BD%D0%B8%D0%B5-%D0%BD%D0%B5%D0%BF%D0%BE%D0%BB%D0%B0%D0%B4%D0%BE%D0%BA-%D0%B8-%D1%87%D0%B0%D1%81%D1%82%D0%BE-%D0%B7%D0%B0%D0%B4%D0%B0%D0%B2%D0%B0%D0%B5%D0%BC%D1%8B%D0%B5-%D0%B2%D0%BE%D0%BF%D1%80%D0%BE%D1%81%D1%8B h_01HCHG901XJ77NQFVX01YZPGT2=can-users-log-in-using-both-sso-and-2fa-methods h_01HCHG901XH0ED40MK2YM1NGRP=why-cant-some-users-connect-using-sso h_01HCHG901X942E0WCBC00KRFSE=do-i-need-a-test-environment-to-test-setup-before-pushing-to-production h_01HCHG901XNNT8GA3TSP5XJC3B=what-should-i-do-before-the-appsflyer-certificate-expires h_01HCHG901XSKPTTRECJPNA09XR=how-can-i-unselect-the-force-sso-login-option h_01HCHG901XPKMP7HSJ04PY9KHW=%D0%BF%D1%80%D0%B8%D0%BC%D0%B5%D1%87%D0%B0%D0%BD%D0%B8%D0%B5-1 h_01HYDBV18S924FNRCBSPR56CTR=is-it-required-to-use-the-appsflyer-certificate-in-my-idp h_01J5QRR54JNC5YNZHQ463KS7BS=what-happens-when-i-deactivate-sso-and-how-do-i-do-it h_01JJH8F3VFTQA1AANNNS85YBF8=can-i-have-negative-serial-numbers-in-the-certificate" />
