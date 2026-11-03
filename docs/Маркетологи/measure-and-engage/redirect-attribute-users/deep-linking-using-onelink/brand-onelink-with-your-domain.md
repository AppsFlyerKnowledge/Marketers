---
title: Добавьте название своего бренда в ссылки OneLink
metadata:
  keywords:
    - Marketers
    - cname
    - OneLink
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-asaf-mashiah
    - Marketers
    - OneLink
  created_at: '2019-08-26T09:00:09Z'
  edited_at: '2026-09-01T00:34:34Z'
  id: 360002329137
  locale: ru
  section: Deep linking using OneLink
  section_id: 6551203111057
  url: https://support.appsflyer.com/hc/ru/articles/360002329137
---
> **At a glance:** **Краткий обзор:** Рекламодатели, использующие ссылки OneLink, могут указывать в них свой домен, чтобы повысить эффективность кампаний и узнаваемость бренда. чтобы повысить эффективность кампаний и узнаваемость бренда.

![Branded_1__3_.jpg](https://files.readme.io/20d0a59aa3e896960c9a0faaacad51a58e314073368452e07a7507e0770ca817-30192959736465.png)

## Брендированные домены

* Брендированные домены позволяют указывать в ссылках атрибуции название бренда и домен. Например, как на предыдущей схеме.
  * Ссылка OneLink: abcdef.onelink.me
  * Бренд: abcdef.com
  * Поддомен: Например, приложение
  * Если создать брендированный домен с указанием полного домена, ссылка атрибуции будет выглядеть следующим образом: click.abcdef.com.
* Кампании с брендированными доменами более эффективны по следующим причинам.
  * Доверие: Позволяют использовать узнаваемость бренда, придерживаться фирменного стиля, устранить препятствия на пути пользователя и повысить кликабельность (CTR).
  * Позволяют использовать брендинг в диплинках.
  * Просты в реализации и работают аналогично ссылкам OneLink.
  * Повышают узнаваемость бренда: Ссылки кампаний с названием бренда эффективнее общих ссылок.
  * Предотвращают попадание рассылок в спам из-за несовпадения ссылки с электронной почтой отправителя.
  * Брендированные домены включены в платные <Anchor target="_blank" href="/marketers/ru/docs/account-management-plans-payments-and-billing">тарифные планы</Anchor> AppsFlyer.

### Принципы реализации

Для создания брендированного домена полный домен, определенный в системе доменных имен (DNS), связывается с поддоменом OneLink (пункт назначения AppsFlyer CNAME). Для этого используются стандартные параметры в DNS, а в AppsFlyer настраивается брендированный домен. Кроме того, для поддержки брендированных доменов потребуется внести небольшие изменения в приложение.

Вам потребуется помощь администратора DNS (как правило, это кто-то из вашего ИТ-отдела или специалист поставщика услуг хостинга DNS) и разработчика приложения.

С одним поддоменом OneLink может быть связано несколько полных доменов. Это значит, что один и тот же поддомен OneLink может использоваться несколькими брендами.

### Настройка брендированных доменов

Чтобы настроить брендированный домен, выполните следующие действия.

|  | Ответственность | Действие | Замечания |
| --- | --- | --- | --- |
| 1 | Маркетолог при поддержке администратора DNS | [Настройка брендированной ссылки в AppsFlyer](/docs/brand-onelink-with-your-domain#set-up-a-branded-domain-in-appsflyer) | Администратор DNS (как правило, это кто-то из вашего ИТ-отдела или специалист поставщика услуг хостинга DNS) определяет полный домен (хост) и настраивает запись CNAME, как описано в процедуре. |
| 2 | Разработчик | [Настройка брендированных доменов в приложении](/docs/brand-onelink-with-your-domain#set-up-branded-domains-in-the-app) | Вносит незначительные изменения в код приложения. |
| 3 | Маркетолог | [Применение и тестирование брендированных доменов](/docs/brand-onelink-with-your-domain#using-and-testing-branded-domains) |  |
| При необходимости | Маркетолог | [Изменение и удаление брендированных доменов](/docs/brand-onelink-with-your-domain#editing-and-deleting-branded-domains) |  |

### Процедура

<div id="set-up-a-branded-domain-in-appsflyer" />

<Accordion title="Настройка брендированного домена в AppsFlyer">

Настройка брендированных доменов предполагает связывание полного домена, заданного в вашей записи DNS, с поддоменом OneLink в AppsFlyer, как показано на следующей схеме.

**Брендированный домен, указывающий на серверы AppsFlyer**

![Позволяют использовать брендинг в диплинках.](https://files.readme.io/43bcdbe50ec58af434f404f0216f90ad345b7b1e034cb7d7c80e3c3c4307c1d2-30192946333713.png)

**Прежде чем начать:**

* Выберите полное доменное имя, например app.abcdef.com, где  
  abcdef.com - это ваш бренд. Поддомен (например, app) также можно настроить.
* Попросите администратора DNS создать полный домен (хост).
* Попросите администратора DNS установить запись CNAME, чтобы полный  
  домен (Brand domain) указывал на определенный URL (он же хост AppsFlyer).  
  Это показано на схеме (выше): брендированный домен указывает на серверы AppsFlyer.

**Чтобы сопоставить ваш полный домен с поддоменом OneLink**:

1. В AppsFlyer перейдите в **Вовлечение** > **Брендовые домены**.
2. Нажмите **+ New Branded Domain** (Новый брендированный домен).
3. В поле **Brand Domain** (Домен бренда) введите полный домен, как в записи DNS. Например, click.abcdef.com **Не ставьте точку после домена.**
4. Выберите поддомен OneLink из открывшегося списка. Если список не  
   отображения, вам нужно создать шаблон OneLink, который обеспечит  
   поддомен по умолчанию.
5. Нажмите **Далее**.
6. Задайте запись CNAME:
   * Если ваш домен правильно указан на AppsFlyer CNAME,  
     в месте назначения появится сообщение "AppsFlyer CNAME was found" (запись AppsFlyer CNAME найдена).
   * Если запись CNAME не найдена, скопируйте пункт назначения AppsFlyer CNAME ниже и отправьте вашему админу DNS. Попросите его проверить, что полный домен указывает на пункт назначения CNAME. Администратор DNS должен привязать ваш полный домен к месту назначения AppsFlyer CNAME. Иначе брендированный домен будет создан, но он не будет работать.

     > 📘 **Note**
     >
     > **Примечание**
     >
     > Запись CNAME должна быть сопоставлена в течение 7 дней, начиная с даты создания брендового домена и заканчивая датой, указанной в подтверждении.  
     > Если запись CNAME не будет сопоставлена к указанной дате, вы должны  
     > [продлить 7-дневный период](#продление-7-дневного-периода-для-сопоставления-записи-cname).

7. Нажмите **Готово**. Теперь вы можете создавать новые ссылки на основе шаблона OneLink с брендированным доменом.

   > 📘 **Note**
   >
   > **Примечание**
   >
   > * Если вы уже создали ссылки на основе шаблона OneLink без брендированного домена, они все равно будут работать.
   > * Новый брендированный домен начинает работать в течение 24 часов.


#### Продление 7-дневного периода для сопоставления записи CNAME

Новый брендированный домен не будет работать, если запись CNAME вашего полного домена не будет сопоставлена с AppsFlyer в течение 7 дней после создания брендированного домена.

> 📘 **Note**
>
> **Примечание**
>
> Если запись была сопоставлена после истечения 7-дневного периода, вам все равно нужно продлить 7-дневный период, чтобы новый брендированный домен заработал.

**Чтобы продлить 7-дневный период:**

1. В AppsFlyer в боковом меню выберите **Engage** > **Branded Domains**.
2. Перейдите на брендовый домен, который еще не сопоставлен с AppsFlyer, на что указывает значок предупреждения (![alert.png](https://files.readme.io/7df53739ca5c629ec0bda789563f59717da9699986222705228f57e0d947c8de-30192946335761.png)).
3. Нажмите на значок обновления (<Image alt="refresh.png" src="https://files.readme.io/052b47c423612c1b0549f37ed6394373d37f28331e09f4c709601a7e5473bf2b-30192959741585.png" width="18px" />), чтобы продлить 7-дневный период.

> 📘 **Note**
>
> **Примечание**
>
> Вы можете удалить брендированный домен, нажав на значок Delete (<Image alt="delete-subdomain.png" src="https://files.readme.io/0029cc63db331d998182d46a63f9da9856de9b2351abd5b2d87fb2b47ae853c2-30192959748241.png" width="16px" />), если решите не продлевать 7-дневный период. Удалять можно только брендированные домены, которые еще не сопоставлены с AppsFlyer.

#### Пользовательский SSL-сертификат (необязательно)

SSL, управляемый AppsFlyer, является вариантом по умолчанию и рекомендован большинству клиентов; он не требует дополнительных действий, поскольку AppsFlyer автоматически выпускает и продлевает сертификаты. Если у вас есть особые требования к безопасности или соответствию нормативным требованиям, вы можете использовать собственный центр сертификации SSL (пользовательский SSL-сертификат) вместо SSL, управляемого AppsFlyer. Если вы выбираете этот вариант, вы несете ответственность за выпуск, загрузку, обслуживание и продление сертификата. Если срок действия сертификата истекает и он не продлевается вовремя, работа сервиса может быть нарушена.

**Чтобы использовать пользовательский SSL-сертификат:**

1. [Создайте брндовый домен](/docs/brand-onelink-with-your-domain#настройка-брендированных-доменов).
2. В AppsFlyer перейдите в **Вовлечение** > **Брендовые домены**, наведите курсор на нужный домен и выберите значок «Пользовательский SSL-сертификат».

   <Image alt="SSL certificate icon Newest minimal.png" src="https://files.readme.io/8b22a41fd755a3f36e8eaf4a869b107661894d81504bbfb44e1fc728b9b06751-45231876708497.png" width="1044px" />
3. Заполните форму с данными сертификата.

   <Image alt="fill in form to generate CSR file.png" src="https://files.readme.io/4327a4da0cbcc6243c9bbdbec21fe4f91d7fe701ccbffca99e629a5eadd248e8-45231876709649.png" width="722px" />
4. Нажмите **Загрузить CSR**, чтобы загрузить копию только что заполненной формы. <Image alt="Download CSR file.png" src="https://files.readme.io/9a560d19e38593fbc379efc6bdb1e636e1fa34f894dca4b46a23be30019127dd-45231892701585.png" width="254px" />
5. Предоставьте только что загруженный CSR-файл выбранному вами центру сертификации SSL.
6. После того как вам предоставят новый SSL-сертификат, загрузите его обратно в AppsFlyer.

<Image alt="Upload new SSL certificate to AF.png" src="https://files.readme.io/b22525d9f653c3897f39f02a7beded3ad5c42d74a5487458f2ed720a20351e03-45231892701969.png" width="811px" />

> 📘 **Note**
>
> **Примечание**
>
> Сертификаты SSL истекают. Вы несете ответственность за продление сертификата и загрузку его обновленной версии в AppsFlyer до истечения срока действия текущего.

</Accordion>

<div id="set-up-branded-domains-in-the-app" />

<Accordion title="Настройка брендированных доменов в приложении">

* Используйте следующие версии SDK:
  * Android: 4.10.1 и выше
  * iOS: 4.10.1 и выше
  * Чтобы отслеживать приглашения пользователей по рекомендациям («Пригласите друга»), требуется SDK версии 5.2.0 и выше (как для iOS, так и для Android)

**Примечания по реализации поддержки брендированных доменов в SDK**

* Если диплинкинг выполняется с использованием брендированных доменов, SDK AppsFlyer не может получить данные о конверсиях по установкам и диплинкингу.
* Чтобы решить эту проблему, разработчик использует `setOneLinkCustomDomain` и `oneLinkCustomDomains` SDK API для Android и iOS соответственно.
* Этот API отправляет запрос на брендированный домен, получает домен OneLink, которому он сопоставлен, после чего завершает создание ссылки OneLink.

<Tabs>
<Tab title="Android;">

Обязательно обновите в манифесте <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_android_init_setup#adding-app-link-intent-filter-to-main-activity">intent-filter</Anchor>, указав домен своего бренда в качестве значения атрибута android:host.

Используйте этот API до инициализации SDK в <Anchor target="_blank" href="https://developer.android.com/reference/android/app/Application">глобальном классе Application в Android.</Anchor>

**Пример**

```java
public class AFApplication extends Application {

    @Override
    public void onCreate() {
    super.onCreate();

      // Set branded link domain. Don't include https:// as part of the domain. 
      AppsFlyerLib.getInstance().setOneLinkCustomDomain("promotion.greatapp.com");
      AppsFlyerLib.getInstance().init(AF_DEV_KEY, conversionListener, this);
      AppsFlyerLib.getInstance().start(this, AF_DEV_KEY);

    }
}
```

Если у вас несколько брендированных доменов, передайте их все в API, чтобы всегда получать данные о конверсиях и иметь возможность использовать диплинки.

**Пример**

```java
AppsFlyerLib.getInstance().setOneLinkCustomDomain("promotion.greatapp.com", 
                                                        "click.greatapp.com", 
                                                        "deals.greatapp.com");
```

</Tab>

<Tab title="https://files.readme.io/f28d0aac1797ee18fdc6083d9ea6d5d2f87d37a894a6c27ab0ea9b6ca51c53a1-49839256665233.png">

**Чтобы связать домены с универсальными ссылками iOS:**

* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_ios_init_setup#enabling-associated-domains">Настройте</Anchor> **домен/поддомен OneLink** как связанный домен в Xcode.
* Настройте **брендированный домен** в Xcode как <Anchor target="_blank" href="https://developer.apple.com/documentation/security/password_autofill/setting_up_an_app_s_associated_domains">связанный домен</Anchor>.
* Установите брендированную ссылку, чтобы получить данные о конверсии. Чтобы получить инструкции, щелкните соответствующий язык программирования ниже.

<Tabs>
<Tab title="Objective C">

Используйте API в AppDelegate.m внутри метода didFinishLaunchingWithOptions:

```objectivec
- (BOOL)application:(UIApplication *)application didFinishLaunchingWithOptions:(NSDictionary *)launchOptions {
    /** ИНИЦИАЛИЗАЦИЯ AppsFlyer **/
    [AppsFlyerLib shared].appsFlyerDevKey = @"SED_DEV_KEY";
    [AppsFlyerLib shared].appleAppID = @"123456789";
    [AppsFlyerLib shared].oneLinkCustomDomains = @[@"promotion.greatapp.com"];
    //...
    //...
  }
```

Если у вас несколько брендированных доменов, передайте их все в API, чтобы всегда получать данные о конверсиях и иметь возможность использовать диплинки.

**Пример**

```objectivec
[AppsFlyerLib shared].oneLinkCustomDomains = @[@"promotion.greatapp.com", @"click.greatapp.com"];
```

</Tab>

<Tab title="Swift">

Этот API должен использоваться в AppDelegate.swift внутри метода didFinishLaunchingWithOptions:

```swift
   func application(_ application: UIApplication, didFinishLaunchingWithOptions 
        launchOptions: [UIApplicationLaunchOptionsKey: Any]?) -> Bool {
          AppsFlyerLib.shared().appsFlyerDevKey = "6CQi4Be6Zs9oNLsCusPbUL"
          AppsFlyerLib.shared().appleAppID = "340954504"
          AppsFlyerLib.shared().oneLinkCustomDomains = ["example.com"]
          //...
          //...
   }
```

Если у вас несколько брендированных доменов, их можно передать в API как массив строк. Так, независимо от того, какая именно брендированная ссылка используется, вы всегда будете получать данные о конверсиях и сможете использовать диплинки.

**Пример**

```objectivec
AppsFlyerLib.shared().oneLinkCustomDomains = ["promotion.greatapp.com", "click.greatapp.com"]
```

</Tab>
</Tabs>

</Tab>
</Tabs>

</Accordion>

<div id="using-and-testing-branded-domains" />

<Accordion title="Применение и тестирование брендированных доменов">

**Необходимые условия**:

Перед использованием и тестированием брендированных доменов, выполните шаги [соответствующего процесса](/docs/brand-onelink-with-your-domain#set-up-branded-domains-in-the-app).

**Чтобы создать и протестировать брендированные домены:**

1. <Anchor target="_blank" href="/marketers/ru/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#создание-ссылки-onelink">Создайте ссылку OneLink</Anchor> с помощью шаблона OneLink, сопоставленного брендированному домену.
2. Скопируйте настраиваемую ссылку атрибуции в текстовый редактор.
3. Настраиваемая ссылка атрибуции состоит из поддомена OneLink, идентификатора OneLink и идентификатора настраиваемой ссылки. Замените поддомен OneLink полным доменом брендированного домена. Пример:

| Настраиваемая ссылка атрибуции | Брендированный домен |
| --- | --- |
| **abcdef.onelink.me**/A1bc/dc1234ef | **click.abcdef.com**/A1bc/dc1234ef |

4. Используйте брендированную ссылку <Anchor target="_blank" href="/marketers/ru/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#testing">для тестирования установок и диплинкинга</Anchor>.
5. Если в рамках тестирования вы используете отчеты с сырыми данными, в поле Original URL (Исходный URL-адрес) будут указаны брендированные ссылки.

</Accordion>

<div id="editing-verifying-and-deleting-branded-domains" />

<Accordion title="Редактирование, проверка и удаление брендированных доменов">

#### **Редактирование сопоставления брендированных доменов**

Вы можете изменить сопоставление существующего полного домена другому поддомену OneLink. Задавать CNAME не требуется.

1. В AppsFlyer в боковом меню выберите **Engage** > **Branded Domains**.
2. Перейдите к брендированному домену, который вы хотите изменить.
3. Щелкните значок Edit (<Image alt="edit-subdomain.png" src="https://files.readme.io/ffe3da7d1c065a806a44c607bcf1231e06bf7e7478ca50187e57cb5ab876ae72-30192959751185.png" width="17px" />).
4. Выберите новый поддомен OneLink.
5. Нажмите **Далее.** Задавать CNAME не требуется.
6. Нажмите **Готово**.

> 🚧 **Important**
>
> **Предупреждение**
>
> При изменении брендированного домена в активных кампаниях ссылки могут начать работать по-другому или перестать работать.

#### **Проверка сопоставления брендированных доменов**

После изменения поддомена OneLink, сопоставленного с вашим брендированным доменом, проверьте, правильно ли сопоставлен брендированный домен:

1. В AppsFlyer в боковом меню выберите **Engage** > **Branded Domains**.
2. Перейдите к брендированному домену, который вы хотите проверить.
3. Щелкните значок Verify (<Image alt="verify-2.png" src="https://files.readme.io/4ac94a535e9101b3e727351f67df8917c0870d6ede8ec963de8c5528893b8e2b-30192946342929.png" width="17px" />).

> 📘 **Note**
>
> **Примечание**
>
> Если проверка не удалась из-за того, что запись CNAME еще не сопоставлена, вы можете сделать это с течение 7 дней, до даты, указанной в диалоге о неудачной проверке.
> Если запись CNAME не будет сопоставлена к указанной дате, вам придется продлить 7-дневный период.

#### **Запись CNAME домена больше не указывает на AppsFlyer**

Изменение вашей записи CNAME, чтобы она больше не указывала на AppsFlyer, приведет к удалению брендированного домена из AppsFlyer.

#### **Чтобы удалить сопоставление брендированного домена:**

Для удаления брендированного домена обратитесь к своему CSM AppsFlyer или напишите на электронный адрес [hello@appsflyer.com](mailto:hello@appsflyer.com").

</Accordion>

## Поиск и устранение неполадок, особенности и ограничения

<div id="troubleshooting" />

<Accordion title="Устранение неполадок">

| Симптом | Причина/решение |
| --- | --- |
| Брендированный домен не удается сопоставить шаблону OneLink | <ul><li>**Недопустимое доменное имя:** При сопоставлении брендированного домена шаблону OneLink AppsFlyer пытается проверить, что брендированная ссылка имеет действительное доменное имя. Допустимое доменное имя имеет формат click.abcdef.com.</li><li>**Брендированный домен уже сопоставлен**: Полный домен может быть сопоставлен только один раз.</li></ul> |
| При использовании брендированного домена не выполняется переход в приложение в рамках диплинкинга | <ul><li>[Проверьте работоспособность брендированного домена.](#проверка-сопоставления-брендированных-доменов)</li><li>**Проверьте CNAME**: Убедитесь, что запись CNAME указывает на AppsFlyer с вашего брендированного домена.</li><li>**Проверьте настройки диплинкинга для шаблона OneLink**: Возможно, проблема в настройках диплинкинга OneLink. Убедитесь, что диплинкинг настроен с помощью OneLink.</li><li>**Изменено сопоставление OneLink**: Вы можете отредактировать брендированный домен и сопоставить его с другой ссылкой OneLink. Если у вновь сопоставленной ссылки OneLink настройки диплинкинга другие или отсутствуют, диплинкинг может не работать.</li></ul> |
| По брендированным доменам нет установок | <ul><li>**Проверьте настройки шаблона OneLink**: Убедитесь, что поддомен OneLink, используемый для сопоставления с брендированным доменом, связан с правильными приложениями.</li><li>**Поддомен OneLink изменился:** если вы сопоставили брендированный домен с шаблоном OneLink, и поддомен OneLink изменился, это может повлиять на атрибуцию.</li><li>**Обеспечьте реализацию:** API setOneLinkCustomDomain в приложении.</li></ul> |
| По брендированным доменам не регистрируются повторные вовлечения | Убедитесь, что заданы и активны следующие настройки:<ul><li><Anchor target="_blank" href="/marketers/ru/docs/onelink-guide#настройка-onelink">Диплинкинг с помощью OneLink</Anchor>.</li><li>Приложение использует специальный [SDK API setOneLinkCustomDomain](/docs/brand-onelink-with-your-domain#set-up-a-branded-domain-in-appsflyer).</li><li><Anchor target="_blank" href="/marketers/ru/docs/retargeting-attribution-guide#retargeting-settings">В настройках приложения включен ретаргетинг</Anchor>.</li></ul> |
| Во время настройки брендированного домена появляется сообщение **Domain doesn't exist** (Домен не существует) | <ol><li>Обратитесь к администратору DNS с просьбой выяснить, почему так происходит.</li><li>Дождитесь от администратора DNS подтверждения, что домен зарегистрирован.</li><li>Нажмите **Reverify** (Перепроверить).</li></ol> |
| Во время настройки брендированного домена появляется сообщение **AppsFlyer CNAME not found** (Запись CNAME AppsFlyer не найдена) | <ol><li>Попросите администратора DNS настроить запись CNAME, чтобы полный домен (домен бренда) указывал на заданный URL-адрес (хост AppsFlyer). Это показано на схеме в данном разделе: брендированная ссылка указывает на серверы AppsFlyer.</li><li>Дождитесь от администратора DNS подтверждения, что запись CNAME активна.</li></ol> |
| Сообщение о **блокировке** при загрузке страницы брендированного домена | Брендированные домены не включают шаблон или какие-либо параметры. При использовании брендированного домена необходимо добавить шаблон или параметры в конец URL-адреса домена.<br /><br />Например, если «click.abcdef.com» – это ваш брендированный домен, использование просто «**click.abcdef.com**» приведет к появлению сообщения о том, **что вы были заблокированы**.<br /><br />Вы должны добавить параметры или шаблоны в конец. Например, click.abcdef.com **/A1bc/dc1234ef** |
| Ошибка **err\_cert\_authority\_invalid** при загрузке страницы брендированного домена | Данная ошибка указывает на то, что в фирменном домене отсутствует действующий сертификат HTTPS, поскольку центр сертификации не распознан. Поскольку AppsFlyer сертифицирует ваши фирменные домены с помощью Let's Encrypt, ошибка, скорее всего, связана с тем, что Let's Encrypt не признан действительным центром сертификации (CA) в соответствии с DNS-записями CAA (Авторизация центра сертификации) вашего домена.<br /><br />**Решение**<br />Выполните следующие действия:<ol><li>Определите, признает ли ваш домен Let's Encrypt в качестве CA, используя сервисы, подобные <Anchor target="_blank" href="https://www.entrust.com/resources/certificate-solutions/tools/caa-lookup">этому</Anchor>.</li><li>Попросите системных администраторов обновить записи CAA вашего домена, чтобы включить Let's Encrypt в качестве авторизованного центра сертификации.</li></ol> |

</Accordion>

<div id="traits-and-limitations" />

<Accordion title="Характеристики и ограничения">

| Специфика | Да ✓ / Нет **x** | Замечания |
| --- | --- | --- |
| Доступ пользователей аккаунта | ✓ |  |
| Доступ рекламной сети | **X** |  |
| Доступ агентства | **X** | Агентства не могут создавать брендированные домены (или ссылки OneLink). |
| Прозрачность агентства | **X** |  |
| Валюта приложения | Н/Д |  |
| Часовой пояс конкретного приложения | Н/Д |  |
| Доступность брендовых доменов | Н/Д | Брендовые домены доступны только в рамках соответствующих платных тарифов. Если срок действия вашего тарифного плана истекает или он отменяется, доступ к брендовым доменам удаляется, а существующие ссылки, использующие ваши брендовые домены, перестают работать. |
| Ограничение по количеству символов | Н/Д | При вводе доменного имени точка («.») не может быть последним символом. |
| Актуальность данных | Н/Д |  |
| Исторические данные | ✓ |  |
| HTTP | **X** | Протокол HTTP не поддерживается брендированными ссылками. Необходимо использовать протокол HTTPS. |
| Неорганические данные | ✓ |  |
| Органические данные | ✓ |  |
| Ограничение предоставления данных | ✓ | Сертификаты SSL/HTTP для брендированных доменов создаются в AppsFlyer с помощью <Anchor target="_blank" href="https://letsencrypt.org/">Let's Encrypt</Anchor> с ограничением до 50 новых сертификатов в неделю на домен. |
| Ограничения на размер | Н/Д |  |
| Продление действия сертификата SSL/HTTP | ✓ | Ваши брендированные сертификаты домена SSL/HTTP, управляемые AppsFlyer, автоматически продлеваются без каких-либо действий с вашей стороны. |

</Accordion>

<div data-zendesk-anchors="branded-domains=%D0%B1%D1%80%D0%B5%D0%BD%D0%B4%D0%B8%D1%80%D0%BE%D0%B2%D0%B0%D0%BD%D0%BD%D1%8B%D0%B5-%D0%B4%D0%BE%D0%BC%D0%B5%D0%BD%D1%8B h_01HFM51V4PE53FQAED68V8Q834=%D0%B1%D1%80%D0%B5%D0%BD%D0%B4%D0%B8%D1%80%D0%BE%D0%B2%D0%B0%D0%BD%D0%BD%D1%8B%D0%B5-%D0%B4%D0%BE%D0%BC%D0%B5%D0%BD%D1%8B principles-of-implementation=%D0%BF%D1%80%D0%B8%D0%BD%D1%86%D0%B8%D0%BF%D1%8B-%D1%80%D0%B5%D0%B0%D0%BB%D0%B8%D0%B7%D0%B0%D1%86%D0%B8%D0%B8 h_01HFM51V4PPJXMCSV5ZVDPT49M=%D0%BF%D1%80%D0%B8%D0%BD%D1%86%D0%B8%D0%BF%D1%8B-%D1%80%D0%B5%D0%B0%D0%BB%D0%B8%D0%B7%D0%B0%D1%86%D0%B8%D0%B8 setting-up-branded-domains=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-%D0%B1%D1%80%D0%B5%D0%BD%D0%B4%D0%B8%D1%80%D0%BE%D0%B2%D0%B0%D0%BD%D0%BD%D1%8B%D1%85-%D0%B4%D0%BE%D0%BC%D0%B5%D0%BD%D0%BE%D0%B2 h_01HFM51V4PH58ZA4ZXHP5J6K2W=%D0%BD%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-%D0%B1%D1%80%D0%B5%D0%BD%D0%B4%D0%B8%D1%80%D0%BE%D0%B2%D0%B0%D0%BD%D0%BD%D1%8B%D1%85-%D0%B4%D0%BE%D0%BC%D0%B5%D0%BD%D0%BE%D0%B2 procedures=%D0%BF%D1%80%D0%BE%D1%86%D0%B5%D0%B4%D1%83%D1%80%D0%B0 h_01HFM51V4PWWX7TBCHFMPR3QVB=%D0%BF%D1%80%D0%BE%D1%86%D0%B5%D0%B4%D1%83%D1%80%D0%B0 h_01HQ5CWGQNRBXQ6QQDADV7XCQP=set-up-a-branded-domain-in-appsflyer renew-the-day=%D0%BF%D1%80%D0%BE%D0%B4%D0%BB%D0%B5%D0%BD%D0%B8%D0%B5-7-%D0%B4%D0%BD%D0%B5%D0%B2%D0%BD%D0%BE%D0%B3%D0%BE-%D0%BF%D0%B5%D1%80%D0%B8%D0%BE%D0%B4%D0%B0-%D0%B4%D0%BB%D1%8F-%D1%81%D0%BE%D0%BF%D0%BE%D1%81%D1%82%D0%B0%D0%B2%D0%BB%D0%B5%D0%BD%D0%B8%D1%8F-%D0%B7%D0%B0%D0%BF%D0%B8%D1%81%D0%B8-cname h_01HQ5CWGQNQJJ1CXDKTGZ8N9ZE=%D0%BF%D1%80%D0%BE%D0%B4%D0%BB%D0%B5%D0%BD%D0%B8%D0%B5-7-%D0%B4%D0%BD%D0%B5%D0%B2%D0%BD%D0%BE%D0%B3%D0%BE-%D0%BF%D0%B5%D1%80%D0%B8%D0%BE%D0%B4%D0%B0-%D0%B4%D0%BB%D1%8F-%D1%81%D0%BE%D0%BF%D0%BE%D1%81%D1%82%D0%B0%D0%B2%D0%BB%D0%B5%D0%BD%D0%B8%D1%8F-%D0%B7%D0%B0%D0%BF%D0%B8%D1%81%D0%B8-cname custom-ssl-certificate=%D0%BF%D0%BE%D0%BB%D1%8C%D0%B7%D0%BE%D0%B2%D0%B0%D1%82%D0%B5%D0%BB%D1%8C%D1%81%D0%BA%D0%B8%D0%B9-ssl-%D1%81%D0%B5%D1%80%D1%82%D0%B8%D1%84%D0%B8%D0%BA%D0%B0%D1%82-%D0%BD%D0%B5%D0%BE%D0%B1%D1%8F%D0%B7%D0%B0%D1%82%D0%B5%D0%BB%D1%8C%D0%BD%D0%BE h_01KM0E8VHARA2JRAR2H37QM91Y=%D0%BF%D0%BE%D0%BB%D1%8C%D0%B7%D0%BE%D0%B2%D0%B0%D1%82%D0%B5%D0%BB%D1%8C%D1%81%D0%BA%D0%B8%D0%B9-ssl-%D1%81%D0%B5%D1%80%D1%82%D0%B8%D1%84%D0%B8%D0%BA%D0%B0%D1%82-%D0%BD%D0%B5%D0%BE%D0%B1%D1%8F%D0%B7%D0%B0%D1%82%D0%B5%D0%BB%D1%8C%D0%BD%D0%BE h_01HFM51V4PP0NQHVHTKB86250R=set-up-branded-domains-in-the-app h_01HFM51V4PN0FPEDNAF0Q1QS8P=using-and-testing-branded-domains h_01HQ5CWGQPZ6MEFA6MDTHYHCSA=editing-verifying-and-deleting-branded-domains edit-a-branded-domain-mapping=%D1%80%D0%B5%D0%B4%D0%B0%D0%BA%D1%82%D0%B8%D1%80%D0%BE%D0%B2%D0%B0%D0%BD%D0%B8%D0%B5-%D1%81%D0%BE%D0%BF%D0%BE%D1%81%D1%82%D0%B0%D0%B2%D0%BB%D0%B5%D0%BD%D0%B8%D1%8F-%D0%B1%D1%80%D0%B5%D0%BD%D0%B4%D0%B8%D1%80%D0%BE%D0%B2%D0%B0%D0%BD%D0%BD%D1%8B%D1%85-%D0%B4%D0%BE%D0%BC%D0%B5%D0%BD%D0%BE%D0%B2 h_01HQ5FJZD6QMNFA45Z2C7CA3ST=%D1%80%D0%B5%D0%B4%D0%B0%D0%BA%D1%82%D0%B8%D1%80%D0%BE%D0%B2%D0%B0%D0%BD%D0%B8%D0%B5-%D1%81%D0%BE%D0%BF%D0%BE%D1%81%D1%82%D0%B0%D0%B2%D0%BB%D0%B5%D0%BD%D0%B8%D1%8F-%D0%B1%D1%80%D0%B5%D0%BD%D0%B4%D0%B8%D1%80%D0%BE%D0%B2%D0%B0%D0%BD%D0%BD%D1%8B%D1%85-%D0%B4%D0%BE%D0%BC%D0%B5%D0%BD%D0%BE%D0%B2 verify-a-branded-domain-mapping=%D0%BF%D1%80%D0%BE%D0%B2%D0%B5%D1%80%D0%BA%D0%B0-%D1%81%D0%BE%D0%BF%D0%BE%D1%81%D1%82%D0%B0%D0%B2%D0%BB%D0%B5%D0%BD%D0%B8%D1%8F-%D0%B1%D1%80%D0%B5%D0%BD%D0%B4%D0%B8%D1%80%D0%BE%D0%B2%D0%B0%D0%BD%D0%BD%D1%8B%D1%85-%D0%B4%D0%BE%D0%BC%D0%B5%D0%BD%D0%BE%D0%B2 h_01HQ5FK5XJNZ1EABJA66RMYBCN=%D0%BF%D1%80%D0%BE%D0%B2%D0%B5%D1%80%D0%BA%D0%B0-%D1%81%D0%BE%D0%BF%D0%BE%D1%81%D1%82%D0%B0%D0%B2%D0%BB%D0%B5%D0%BD%D0%B8%D1%8F-%D0%B1%D1%80%D0%B5%D0%BD%D0%B4%D0%B8%D1%80%D0%BE%D0%B2%D0%B0%D0%BD%D0%BD%D1%8B%D1%85-%D0%B4%D0%BE%D0%BC%D0%B5%D0%BD%D0%BE%D0%B2 domain-cname-record-no-longer-pointing-to-appsflyer=%D0%B7%D0%B0%D0%BF%D0%B8%D1%81%D1%8C-cname-%D0%B4%D0%BE%D0%BC%D0%B5%D0%BD%D0%B0-%D0%B1%D0%BE%D0%BB%D1%8C%D1%88%D0%B5-%D0%BD%D0%B5-%D1%83%D0%BA%D0%B0%D0%B7%D1%8B%D0%B2%D0%B0%D0%B5%D1%82-%D0%BD%D0%B0-appsflyer h_01JSHFECXS00M6BXH8168ZWJE5=%D0%B7%D0%B0%D0%BF%D0%B8%D1%81%D1%8C-cname-%D0%B4%D0%BE%D0%BC%D0%B5%D0%BD%D0%B0-%D0%B1%D0%BE%D0%BB%D1%8C%D1%88%D0%B5-%D0%BD%D0%B5-%D1%83%D0%BA%D0%B0%D0%B7%D1%8B%D0%B2%D0%B0%D0%B5%D1%82-%D0%BD%D0%B0-appsflyer delete-a-branded-domain-mapping=%D1%87%D1%82%D0%BE%D0%B1%D1%8B-%D1%83%D0%B4%D0%B0%D0%BB%D0%B8%D1%82%D1%8C-%D1%81%D0%BE%D0%BF%D0%BE%D1%81%D1%82%D0%B0%D0%B2%D0%BB%D0%B5%D0%BD%D0%B8%D0%B5-%D0%B1%D1%80%D0%B5%D0%BD%D0%B4%D0%B8%D1%80%D0%BE%D0%B2%D0%B0%D0%BD%D0%BD%D0%BE%D0%B3%D0%BE-%D0%B4%D0%BE%D0%BC%D0%B5%D0%BD%D0%B0 h_01JSHF5RMXXFJTXC246KKAQBSS=%D1%87%D1%82%D0%BE%D0%B1%D1%8B-%D1%83%D0%B4%D0%B0%D0%BB%D0%B8%D1%82%D1%8C-%D1%81%D0%BE%D0%BF%D0%BE%D1%81%D1%82%D0%B0%D0%B2%D0%BB%D0%B5%D0%BD%D0%B8%D0%B5-%D0%B1%D1%80%D0%B5%D0%BD%D0%B4%D0%B8%D1%80%D0%BE%D0%B2%D0%B0%D0%BD%D0%BD%D0%BE%D0%B3%D0%BE-%D0%B4%D0%BE%D0%BC%D0%B5%D0%BD%D0%B0 troubleshooting-traits-and-limitations=%D0%BF%D0%BE%D0%B8%D1%81%D0%BA-%D0%B8-%D1%83%D1%81%D1%82%D1%80%D0%B0%D0%BD%D0%B5%D0%BD%D0%B8%D0%B5-%D0%BD%D0%B5%D0%BF%D0%BE%D0%BB%D0%B0%D0%B4%D0%BE%D0%BA-%D0%BE%D1%81%D0%BE%D0%B1%D0%B5%D0%BD%D0%BD%D0%BE%D1%81%D1%82%D0%B8-%D0%B8-%D0%BE%D0%B3%D1%80%D0%B0%D0%BD%D0%B8%D1%87%D0%B5%D0%BD%D0%B8%D1%8F h_01HFM51V4PH4YM13DVXENRWF2E=%D0%BF%D0%BE%D0%B8%D1%81%D0%BA-%D0%B8-%D1%83%D1%81%D1%82%D1%80%D0%B0%D0%BD%D0%B5%D0%BD%D0%B8%D0%B5-%D0%BD%D0%B5%D0%BF%D0%BE%D0%BB%D0%B0%D0%B4%D0%BE%D0%BA-%D0%BE%D1%81%D0%BE%D0%B1%D0%B5%D0%BD%D0%BD%D0%BE%D1%81%D1%82%D0%B8-%D0%B8-%D0%BE%D0%B3%D1%80%D0%B0%D0%BD%D0%B8%D1%87%D0%B5%D0%BD%D0%B8%D1%8F h_01HFM51V4PJNHZTD97X75WPN98=troubleshooting h_01HFM51V4QQ2TZQMJ2ATNDG91F=traits-and-limitations" />
