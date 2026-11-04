---
title: Тестирование интеграции веб-SDK PBA
metadata:
  keywords:
    - Developers
    - PBA
    - Marketers
    - Cross-Platform Measurement
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - Cross-Platform Measurement
  created_at: '2020-09-01T19:09:41Z'
  edited_at: '2026-08-18T00:24:22Z'
  id: 360012729178
  locale: ru
  section: People Based Attribution (PBA)
  section_id: 43560588808721
  url: https://support.appsflyer.com/hc/ru/articles/360012729178
---
> **Краткий обзор.** Протестируйте интеграцию плагина веб-SDK PBA.

<div id="test-pba-web-events" />

## Тестирование веб-событий PBA

**Принципы использования страницы тестирования**

Веб-SDK отправляет веб-события в PBA, и они становятся доступны на дэшборде PBA и в отчетах по сырым данным после ежедневной обработки. Для обеспечения эффективного процесса тестирования вы отправляете тестовые события, не дожидаясь ежедневной обработки. Тестовые события:

* Проанализированы и проверены при получении.
* Доступны в пользовательском интерфейсе. Сюда входят и ошибки обработки. Если они есть, отправьте исправленные события еще раз, чтобы убедиться, что они обработаны правильно.
* Обрабатываются как и любые другие события в ходе ежедневной обработки. Это означает, что они добавляются на дэшборды и в сырые данные.

<div id="web-sdk-integration-test-page" />

#### Страница тестирования интеграции веб-SDK

<Table>
  <tbody>
    <tr>
      <td>
        <span id="page-main-view"></span>**Основной вид страницы**

        [<Image alt="TestScreen_us-en.jpg" src="https://files.readme.io/345bb7bfffcb7756c0a61d05daadd8a355df5a7b7a07adaeeef203a64adc79bf-360011199758.jpg" width="338px" />](https://files.readme.io/345bb7bfffcb7756c0a61d05daadd8a355df5a7b7a07adaeeef203a64adc79bf-360011199758.jpg)

        * Сначала отображаются самые последние события.
        * **Кэш событий**:
          * Содержит до 100 событий
          * Старые события удаляются, чтобы освободить место для новых событий.
          * Кэшированные события удаляются через 24 часа.
        * **Элементы управления страницей**:
          * **Индикатор частоты обновления**: Страница автоматически обновляется каждые 5 секунд.
          * **Очистить все**: Очищает кэш событий навсегда. **Внимание!** Кэш является общим для веб-сайтов, использующих один и тот же ключ веб-разработки. Таким образом, если другой разработчик использует страницу тестирования, она будет очищена и для него.
          * **Пауза/старт**: Приостанавливает автоматическое обновление. Новые события не отображаются, пока вы не нажмете «Старт».

        **Столбцы таблицы событий**

        | Поле | Описание |
        | --- | --- |
        | Время (UTC) | Время события |
        | Тип события | Типы событий следующие:<br /><br />* События, отправленные вами:<br />  * `EVENT`<br />  * `Установка Customer User ID`<br />  * `pageLoad`: Отправляется из веб-SDK каждый раз при загрузке/обновлении страницы на вашем сайте. |
        | Содержание события | Полезная нагрузка события, зафиксированная PBA. |
        | Комментарии | * **Действительно**: Событие получено и зарегистрировано в PBA. Никаких дополнительных действий не требуется.<br />* **Недействительно**: Список ошибок, требующих исправления. Формат сообщения об ошибке:  <br />  название поля события: описание ошибки<br />* Наведите курсор на сообщения об ошибках, чтобы увидеть подробности:  <br /><br />  ![PBAWebSDKTestingErrorMessagesPopup_en-us.png](https://files.readme.io/0e050e60dbf9f1289880b5d58c4885d4be66392265986eaf4b2f76876697e429-360011317358.png) |
      </td>
    </tr>
    <tr>
      <td>
        **Детализированный вид**[![mceclip0.png](https://files.readme.io/893f2654c8a3d4f9e8bce43728c65723d9fe1583825b2ae8c2276afc33612511-360011199738.png)](https://files.readme.io/893f2654c8a3d4f9e8bce43728c65723d9fe1583825b2ae8c2276afc33612511-360011199738.png)

        Нажмите на строку события, чтобы показать ее содержимое после обработки. Дополнительную информацию см. <Anchor target="_blank" href="/marketers/ru/docs/pba-web-sdk-integration-guide#web-sdk-event-parameters">в параметрах событий веб-SDK.</Anchor>
      </td>
    </tr>
  </tbody>
</Table>

<div id="procedures" />

## Процедура

Выполните следующие процедуры.

<div id="enable-test-mode" />

<Accordion title="Включите тестовый режим">

**Необходимые условия**

Перед тестированием <Anchor target="_blank" href="/marketers/ru/docs/pba-web-sdk-integration-guide#installation-and-integration">веб-SDK необходимо внедрить на ваш сайт</Anchor> или на тестовый сайт.

**Ограничение браузера**

Если в определенном браузере включен тестовый режим, независимо от вкладки, браузер можно использовать только для подключения к указанному веб-сайту, а не к какому-либо другому веб-сайту. Используйте другой браузер, например Safari вместо Chrome, чтобы подключиться с того же компьютера к другому веб-сайту.

**Чтобы включить тестовый режим:**

1. **Убедитесь, что SDK загружен:**
   1. В AppsFlyer в верхнем меню выберите **Мои приложения** > **Просмотр пакетов брендов**.
   2. Выберите необходимый **Тест интеграции веб-SDK.** Откроется страница интеграции. Отобразится веб-ключ разработчика.  

      [![pba_web_sdk_integration_test_web_dev_key_en-us.png](https://files.readme.io/48c37f28d833c0b864fee0a3f417bbd946a385f329ed0e906e20596aeef79b71-360011130257.png)](https://files.readme.io/48c37f28d833c0b864fee0a3f417bbd946a385f329ed0e906e20596aeef79b71-360011130257.png)
   3. В новой вкладке браузера перейдите на свой сайт (на котором установлен веб-SDK).
   4. Нажмите правой кнопкой мыши и выберите «Проверить», чтобы открыть инструменты разработчика в браузере.
   5. Перейдите на вкладку **Консоль**.
   6. В консоли введите:  

      ```javascript
      window.AF_SDK.initPluginsConfig.pba.webAppId
      ```

      Отобразится webAppID.

      [![testing_pba_integration_webappid_check_en-us.png](https://files.readme.io/030f867d82d122f2f493d20f65793ded7739ebb32d92ee15e0668aceded02a58-360011059197.png)](https://files.readme.io/030f867d82d122f2f493d20f65793ded7739ebb32d92ee15e0668aceded02a58-360011059197.png)
   7. Убедитесь, что webAppID совпадает с веб-ключом разработчика на странице **тестирования интеграции веб-SDK**.
2. **Включите тестовый режим**:
   1. На вкладке браузера веб-сайта перейдите на вкладку **Консоль**.
   2. Введите следующее:

      ```javascript
      window.AF_SDK.PLUGINS.PBA.turnOnDevMode()
      ```

      Функция возвращает `undefined`.

      [![testing_pba_integration_turnondevmode.png](https://files.readme.io/b26f180876556e90bce8512f310ca3acff97b7ca040b0dcf98362d9076c81e5b-360011059137.png)](https://files.readme.io/b26f180876556e90bce8512f310ca3acff97b7ca040b0dcf98362d9076c81e5b-360011059137.png)
3. **Убедитесь, что тестовый режим включен:**
   * На вкладке **Консоль** введите:  

     ```javascript
     window.AF_SDK.PLUGINS.PBA.isDevModeOn()
     ```

     Возвращаемое значение: `true`. Это означает, что тестовый режим активен.   
     [![PBATestingWebSDKIntegrationIsDevModeOn_en-us.png](https://files.readme.io/4b5d8f3c3ef31148c9f3cd4021d83404810382fd654defa86d733c0377ffd968-360011482797.png)](https://files.readme.io/4b5d8f3c3ef31148c9f3cd4021d83404810382fd654defa86d733c0377ffd968-360011482797.png)

</Accordion>

<div id="send-test-events" />

<Accordion title="Отправьте тестовые события">

* В тестовом режиме отправляемые вами события отображаются на странице тестирования интеграции.
* Внимание! Тестовые события обрабатываются и впоследствии включаются в отчеты PBA. Чтобы избежать искажения отчетов, заполните `eventRevenue` низкими (малыми) значениями. Если значение не отправлено, PBA заполняет его как 0.

Отправьте примеры событий каждого из описанных типов.

| Шаг | Действие<br /><br />(Введите команды) | Страница тестирования интеграции веб-SDK<br /><br />(Ожидаемый результат) |
| --- | --- | --- |
| 1 | Откройте новую вкладку в браузере и перейдите на любую страницу вашего сайта. | PBA зарегистрирует событие `'pageLoad'` при открытии/обновлении вашего сайта:<br /><br />[![PBATestingWebSDKPageLoadEvent_en-us.png](https://files.readme.io/25ae1b2efbfea897caeb5da94d683b3465c9068245acbedb976959cb8fd3cc77-360011369638.png)](https://files.readme.io/25ae1b2efbfea897caeb5da94d683b3465c9068245acbedb976959cb8fd3cc77-360011369638.png) |
| 2 | Войдите/зарегистрируйтесь на своем сайте как пользователь, <Anchor target="_blank" href="/marketers/ru/docs/pba-web-sdk-integration-guide#setting-customer-user-id-after-signup">чтобы вызвать событие setCustomerUserId</Anchor>. | [![mceclip3.png](https://files.readme.io/7fb5276c5d24b1c6128aaee60684e9f2941e1686eeef4dcf4df4a91c86c9ebb6-360011199558.png)](https://files.readme.io/7fb5276c5d24b1c6128aaee60684e9f2941e1686eeef4dcf4df4a91c86c9ebb6-360011199558.png) |
| 3 | <Anchor target="_blank" href="/marketers/ru/docs/pba-web-sdk-integration-guide#recording-event-scenarios">Начните отправлять веб-события,</Anchor> чтобы убедиться, что PBA обрабатывает их правильно.<br /><br />**Примечание.**<br /><br />Если не указано иное, `eventRevenue` и `eventRevenueCurrency` заполнены значениями по умолчанию:<ul><li>`eventRevenueCurrency: "USD"`</li><li>`eventRevenue: 0`</li></ul>[![PBAWebSDKTestEventEVENT_en-us.png](https://files.readme.io/208c42edaa132b69279a5a99232763e2e9da1be950dd3dec3b5636d650e540c8-360011317918.png)](https://files.readme.io/208c42edaa132b69279a5a99232763e2e9da1be950dd3dec3b5636d650e540c8-360011317918.png)<br /><br />/docs/pba-web-sdk-integration-guide#web-sdk-event-parameters | [![mceclip5.png](https://files.readme.io/51f3c824c253bc825d22c672393adc002c365a2084d71ce6183e412b76e9d3eb-360011199578.png)](https://files.readme.io/51f3c824c253bc825d22c672393adc002c365a2084d71ce6183e412b76e9d3eb-360011199578.png) |

</Accordion>

<div id="troubleshooting" />

## Устранение неполадок

<div id="events-do-not-display-in-the-test-page" />

<Accordion title="События не отображаются на странице тестирования">

1. В инструментах разработчика в браузере перейдите на вкладку **Сеть**.
2. В поле фильтра введите «websdk».
3. На основе кода ответа HTTP выполните следующие действия:
   * 200: Обратитесь в службу технической поддержки AppsFlyer.
   * 400: Проверьте, что все параметры заключены в кавычки " ".

</Accordion>

<div data-zendesk-anchors="test-pba-web-events=%D1%82%D0%B5%D1%81%D1%82%D0%B8%D1%80%D0%BE%D0%B2%D0%B0%D0%BD%D0%B8%D0%B5-%D0%B2%D0%B5%D0%B1-%D1%81%D0%BE%D0%B1%D1%8B%D1%82%D0%B8%D0%B9-pba h_01HKW32BE04AKHFMY853211C1A=%D1%82%D0%B5%D1%81%D1%82%D0%B8%D1%80%D0%BE%D0%B2%D0%B0%D0%BD%D0%B8%D0%B5-%D0%B2%D0%B5%D0%B1-%D1%81%D0%BE%D0%B1%D1%8B%D1%82%D0%B8%D0%B9-pba web-sdk-integration-test-page=%D1%81%D1%82%D1%80%D0%B0%D0%BD%D0%B8%D1%86%D0%B0-%D1%82%D0%B5%D1%81%D1%82%D0%B8%D1%80%D0%BE%D0%B2%D0%B0%D0%BD%D0%B8%D1%8F-%D0%B8%D0%BD%D1%82%D0%B5%D0%B3%D1%80%D0%B0%D1%86%D0%B8%D0%B8-%D0%B2%D0%B5%D0%B1-sdk h_01HKW32BE0Z2ZKTBHSCSWVT04N=%D1%81%D1%82%D1%80%D0%B0%D0%BD%D0%B8%D1%86%D0%B0-%D1%82%D0%B5%D1%81%D1%82%D0%B8%D1%80%D0%BE%D0%B2%D0%B0%D0%BD%D0%B8%D1%8F-%D0%B8%D0%BD%D1%82%D0%B5%D0%B3%D1%80%D0%B0%D1%86%D0%B8%D0%B8-%D0%B2%D0%B5%D0%B1-sdk procedures=%D0%BF%D1%80%D0%BE%D1%86%D0%B5%D0%B4%D1%83%D1%80%D0%B0 h_01HKW32BE0VA0X9ZX4Z26EY6CZ=%D0%BF%D1%80%D0%BE%D1%86%D0%B5%D0%B4%D1%83%D1%80%D0%B0 h_01HKW32BE08Z9CCMBPK4Z0854C=enable-test-mode h_01HKW32BE0E4A1W221FKY97EZB=send-test-events troubleshooting=%D1%83%D1%81%D1%82%D1%80%D0%B0%D0%BD%D0%B5%D0%BD%D0%B8%D0%B5-%D0%BD%D0%B5%D0%BF%D0%BE%D0%BB%D0%B0%D0%B4%D0%BE%D0%BA h_01HKW32BE1HFV0NM64QMASBCCT=%D1%83%D1%81%D1%82%D1%80%D0%B0%D0%BD%D0%B5%D0%BD%D0%B8%D0%B5-%D0%BD%D0%B5%D0%BF%D0%BE%D0%BB%D0%B0%D0%B4%D0%BE%D0%BA h_01HKW32BE1QHV0W6ZDYHG94RQA=events-do-not-display-in-the-test-page" />
