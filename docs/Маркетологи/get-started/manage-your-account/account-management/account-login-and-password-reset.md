---
title: Вход в систему и сброс пароля
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
  created_at: '2025-03-03T09:04:23Z'
  edited_at: '2026-08-28T00:15:15Z'
  id: 33114514624273
  locale: ru
  section: Account management
  section_id: 6551191075473
  url: https://support.appsflyer.com/hc/ru/articles/33114514624273
---
> **Кратко:** войдите в AppsFlyer, добавьте несколько аккаунтов и сбросьте пароли пользователей.

<div id="log-in-instructions" />

## Инструкции по входу

Инструкции по входу для новых и действующих пользователей. Здесь описано, как создать новый аккаунт, пригласить нового пользователя или войти в систему как существующий пользователь.

**Примечание**: инструкции по созданию пользователя см. <Anchor target="_blank" href="/marketers/ru/docs/user-management#creating-users">здесь</Anchor>.


<div id="logging-in-for-the-first-time" />

<Accordion title="Первый вход в систему">

Если вы только что зарегистрировались или вас только что пригласили в AppsFlyer, вы получите электронное письмо со ссылкой для активации.

Чтобы войти в AppsFlyer:

1. Откройте письмо с активацией от AppsFlyer
2. **Для первого пользователя аккаунта**:
   1. Нажмите ссылку активации в тексте письма  
      **Примечание**: пользователь, созданный при открытии аккаунта, является "владельцем аккаунта" и по умолчанию получает <Anchor target="_blank" href="/marketers/ru/docs/user-management#владелец-аккаунта">роль администратора.</Anchor>
3. **Для пользователей, входящих по приглашению**:
   1. Скопируйте код подтверждения из текста письма
   2. Нажмите кнопку **страница входа в AppsFlyer** в тексте письма
   3. Введите код  
      **Примечание:**  Коды подтверждения действительны 15 минут. Если срок действия кода подтверждения истек, нажмите **Resend Code**, чтобы получить новый
4. Создание пароля

</Accordion>

<div id="existing-users" />

<Accordion title="Существующие пользователи">

Существующие пользователи могут войти в AppsFlyer через <Anchor target="_blank" href="https://hq1.appsflyer.com/auth/login">основную страницу входа</Anchor>.

Войти в AppsFlyer можно с помощью:

* Учетные данные (имя пользователя и пароль)
* Вход через Google
* <Anchor target="_blank" href="/marketers/ru/docs/sso-authentication">Единый вход</Anchor>

**Примечание**: если администратор настроил для вашего аккаунта <Anchor target="_blank" href="/marketers/ru/docs/implementing-and-using-2fa-login">двухфакторную аутентификацию (2FA)</Anchor>, вам будет предложено подтвердить вход в систему с помощью другого метода аутентификации.

</Accordion>

<div id="twofactor-authentication-2fa" />

<Accordion title="Двухфакторная авторизация (2FA)">

Если 2FA включена в настройках управления безопасностью, она будет активирована после первого входа в систему.

[Чтобы сбросить 2FA пользователя, см. здесь](/docs/account-login-and-password-reset#resetting-twofactor-authentication-2fa).

</Accordion>

<div id="password-login-or-2fa-reset" />

## Сброс пароля, логина или 2FA

Сброс пароля для существующих пользователей и пользователей, которые не завершили первоначальную регистрацию или процесс принятия приглашения.

<div id="existing-users-and-invited-users-who-have-not-activated-yet" />

<Accordion title="Существующие и приглашенные пользователи, которые еще не активировали аккаунт">

Чтобы сбросить пароль:

1. На <Anchor target="_blank" href="https://hq1.appsflyer.com/auth/login">главной странице входа</Anchor> в AppsFlyer нажмите **Забыли пароль?**.
2. На вашу электронную почту будет отправлен одноразовый код подтверждения
3. Скопируйте код подтверждения из текста электронного письма
4. В тексте письма нажмите кнопку **Страница входа в AppsFlyer**.
5. Введите код.  
   **Примечание:** код подтверждения действителен в течение 15 минут.  
   Если срок действия кода истёк, нажмите **Отправить код повторно**, чтобы получить новый.
6. Создайте новый пароль

</Accordion>

<div id="users-who-have-not-completed-the-initial-registration" />

<Accordion title="Пользователи, которые не завершили первоначальную регистрацию">

При регистрации в AppsFlyer на вашу электронную почту было отправлено приглашение. Ссылка для активации в письме действительна в течение 7 дней. Чтобы завершить регистрацию, выполните следующие действия:

1. Откройте электронное письмо
2. В тексте письма нажмите кнопку активации **Страница регистрации в AppsFlyer**.  
   **Примечание:** пользователю, созданному при открытии аккаунта, – «владельцу аккаунта» – по умолчанию назначается <Anchor target="_blank" href="/marketers/ru/docs/user-management#владелец-аккаунта">роль администратора</Anchor>.
   1. Если срок действия ссылки истек, выполните регистрацию заново с самого начала
3. Создание пароля

</Accordion>

<div id="resetting-twofactor-authentication-2fa" />

<Accordion title="Сброс двухфакторной аутентификации (2FA) пользователя">

Если в аккаунте используется двухфакторная аутентификация, в некоторых случаях может потребоваться сбросить ее настройки для пользователя. Для этого:

1. На вкладке **Пользователи** нажмите кнопку **Действия** <Image alt="actions_icon.png" src="https://files.readme.io/24ad987d1e77d9dfa8559a370733a7b62a6d86954ec1d552eac9c406445ed927-16162502616593.png" width="25px" /> в крайнем правом углу строки пользователя.
2. В меню выберите **Сбросить 2FA**.

**Примечание:** Администратор может сбросить 2FA любого другого пользователя, кроме себя. Чтобы сбросить 2FA для владельца аккаунта, обратитесь в службу поддержки AppsFlyer.

</Accordion>

<div data-zendesk-anchors="log-in-instructions=%D0%B8%D0%BD%D1%81%D1%82%D1%80%D1%83%D0%BA%D1%86%D0%B8%D0%B8-%D0%BF%D0%BE-%D0%B2%D1%85%D0%BE%D0%B4%D1%83 h_01JNDM4M03F0T16ZHY2V1BSRQH=%D0%B8%D0%BD%D1%81%D1%82%D1%80%D1%83%D0%BA%D1%86%D0%B8%D0%B8-%D0%BF%D0%BE-%D0%B2%D1%85%D0%BE%D0%B4%D1%83 h_01JNDJFMRHCS20TABKNSHQ2MMW=logging-in-for-the-first-time h_01JNDM9HN8K396432TQ5MEVYCZ=existing-users h_01JNDS7ZT2TMX5315587CHBDY5=twofactor-authentication-2fa password-login-or-2fa-reset=%D1%81%D0%B1%D1%80%D0%BE%D1%81-%D0%BF%D0%B0%D1%80%D0%BE%D0%BB%D1%8F-%D0%BB%D0%BE%D0%B3%D0%B8%D0%BD%D0%B0-%D0%B8%D0%BB%D0%B8-2fa h_01JNDSMFB1YAWA340BAEYFXRES=%D1%81%D0%B1%D1%80%D0%BE%D1%81-%D0%BF%D0%B0%D1%80%D0%BE%D0%BB%D1%8F-%D0%BB%D0%BE%D0%B3%D0%B8%D0%BD%D0%B0-%D0%B8%D0%BB%D0%B8-2fa h_01JNDSJPQ4GNV0PD16GE7G9FY6=existing-users-and-invited-users-who-have-not-activated-yet h_01JNDTHN2B6VCH38ER68D3RNFS=users-who-have-not-completed-the-initial-registration h_01H9Q9007R72FAH89XW58MWCXT=resetting-twofactor-authentication-2fa" />
