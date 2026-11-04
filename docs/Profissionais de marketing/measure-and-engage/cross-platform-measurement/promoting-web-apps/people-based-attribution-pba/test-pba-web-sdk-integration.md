---
title: Testar a integração do Web SDK do PBA
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
  edited_at: '2026-08-18T00:24:03Z'
  id: 360012729178
  locale: pt
  section: People Based Attribution (PBA)
  section_id: 43560588808721
  url: https://support.appsflyer.com/hc/pt/articles/360012729178
---
> **Visão geral:** Teste a integração do plug-in PBA do Web SDK.

<div id="test-pba-web-events" />

## Testar eventos da web do PBA

**Princípios de uso da página de teste**

O Web SDK envia eventos da web para o PBA, que são disponibilizados por meio de painéis do PBA e relatórios de dados brutos, após o processamento diário. Para habilitar um processo de teste eficiente, você envia eventos de teste sem esperar pelo processamento diário. Os eventos de teste são:

* Analisados e validados no recebimento.
* Disponibilizados para você na interface do usuário. Isso inclui erros de processamento. Se existirem, envie eventos corrigidos novamente para garantir que sejam processados corretamente.
* São processados como qualquer outro evento durante o processamento diário. Isso significa que eles são adicionados aos painéis e dados brutos.

<div id="web-sdk-integration-test-page" />

#### Página de teste de integração do Web SDK

<Table>
  <tbody>
    <tr>
      <td>
        <span id="page-main-view"></span>**Visualização principal da página**

        [<Image alt="TestScreen_us-en.jpg" src="https://files.readme.io/345bb7bfffcb7756c0a61d05daadd8a355df5a7b7a07adaeeef203a64adc79bf-360011199758.jpg" width="338px" />](https://files.readme.io/345bb7bfffcb7756c0a61d05daadd8a355df5a7b7a07adaeeef203a64adc79bf-360011199758.jpg)

        * Os eventos mais recentes aparecem primeiro.
        * **Cache de eventos**:
          * Contém até 100 eventos
          * Eventos mais antigos são excluídos para dar lugar a eventos mais recentes
          * Os eventos armazenados em cache são excluídos após 24 horas
        * **Controles de página**:
          * **Indicador de taxa de atualização**: A página é atualizada automaticamente a cada 5 segundos.
          * Limpar tudo: Limpa eventos do cache permanentemente. **Atenção!** O cache é comum a sites que compartilham a mesma chave do desenvolvedor web. Assim, se outro desenvolvedor estiver usando a página de teste, ele também será limpo para eles.
          * **Pausar/iniciar**: Pausa a atualização automática. Novos eventos não são exibidos até que você clique em Iniciar.

        **Colunas da tabela de eventos**

        | Campo | Descrição |
        | --- | --- |
        | Hora (UTC) | Hora do evento |
        | Tipo de evento | Os tipos de evento são os seguintes:<br /><br />* Eventos enviados por você:<br />  * `EVENT`<br />  * `Definir ID de usuário cliente`<br />  * `pageLoad`: Enviado pelo Web SDK sempre que uma página é carregada/atualizada em seu site |
        | Conteúdo do evento | O payload, conforme registrado pelo PBA. |
        | Comentários | * **Válido**: O PBA recebeu e gravou o evento. Não é necessária nenhuma ação adicional.<br />* **Inválido**: Lista de erros que requerem ação corretiva. O formato da mensagem de erro é:  <br />  Nome do campo de evento: descrição do erro<br />* Passe o mouse sobre as mensagens de erro para ver os detalhes:  <br /><br />  ![PBAWebSDKTestingErrorMessagesPopup_en-us.png](https://files.readme.io/0e050e60dbf9f1289880b5d58c4885d4be66392265986eaf4b2f76876697e429-360011317358.png) |
      </td>
    </tr>
    <tr>
      <td>
        **Visualização detalhada**[![mceclip0.png](https://files.readme.io/893f2654c8a3d4f9e8bce43728c65723d9fe1583825b2ae8c2276afc33612511-360011199738.png)](https://files.readme.io/893f2654c8a3d4f9e8bce43728c65723d9fe1583825b2ae8c2276afc33612511-360011199738.png)

        Clique em uma linha de evento para exibir seu conteúdo após o processamento. Ver <Anchor target="_blank" href="/marketers/pt/docs/pba-web-sdk-integration-guide#web-sdk-event-parameters">Parâmetros de evento do Web SDK</Anchor> Para informações adicionais
      </td>
    </tr>
  </tbody>
</Table>

<div id="procedures" />

## Procedimentos

Conclua os procedimentos a seguir.

<div id="enable-test-mode" />

<Accordion title="Habilitar o modo de teste">

**Pré-requisitos**

Antes de testar, <Anchor target="_blank" href="/marketers/pt/docs/pba-web-sdk-integration-guide#installation-and-integration">o Web SDK deve ser implementado em seu site</Anchor> ou em um site de teste.

**Limitação do navegador**

Se o modo de teste estiver ativado em um determinado navegador, independentemente da guia; O navegador só pode ser usado para se conectar ao site especificado e não a qualquer outro site. Use um navegador diferente, por exemplo, Safari em vez do Chrome, para se conectar da mesma máquina a um site diferente.

**Para habilitar o modo de teste:**

1. **Verifique se o SDK está carregado:**
   1. Na AppsFlyer, no menu superior, selecione **Meus aplicativos** > **Exibir agrupamentos de marca.**
   2. Selecione o **Teste de integração do Web SDK requerido.** A página de integração é aberta. A chave do desenvolvedor web é exibida.  

      [![pba_web_sdk_integration_test_web_dev_key_en-us.png](https://files.readme.io/48c37f28d833c0b864fee0a3f417bbd946a385f329ed0e906e20596aeef79b71-360011130257.png)](https://files.readme.io/48c37f28d833c0b864fee0a3f417bbd946a385f329ed0e906e20596aeef79b71-360011130257.png)
   3. Em uma nova aba do navegador, vá para seu site (que tem o Web SDK instalado).
   4. Clique com o botão direito do mouse e selecione inspecionar para abrir as ferramentas de desenvolvedor do navegador.
   5. Ir para a aba **Console**.
   6. No console, digite:  

      ```javascript
      window.AF_SDK.initPluginsConfig.pba.webAppId
      ```

      O webAppID é exibido.

      [![testing_pba_integration_webappid_check_en-us.png](https://files.readme.io/030f867d82d122f2f493d20f65793ded7739ebb32d92ee15e0668aceded02a58-360011059197.png)](https://files.readme.io/030f867d82d122f2f493d20f65793ded7739ebb32d92ee15e0668aceded02a58-360011059197.png)
   7. Verifique se o webAppID é idêntico à chave do desenvolvedor web na página **Teste de integração do Web SDK** .
2. **Habilitar o modo de teste**:
   1. Na aba do navegador do site, vá para a aba **Console**.
   2. Insira:

      ```javascript
      window.AF_SDK.PLUGINS.PBA.turnOnDevMode()
      ```

      A função retorna`undefined`.

      [![testing_pba_integration_turnondevmode.png](https://files.readme.io/b26f180876556e90bce8512f310ca3acff97b7ca040b0dcf98362d9076c81e5b-360011059137.png)](https://files.readme.io/b26f180876556e90bce8512f310ca3acff97b7ca040b0dcf98362d9076c81e5b-360011059137.png)
3. **Verifique se o modo de teste está habilitado:**
   * Em **Console**, digite:  

     ```javascript
     window.AF_SDK.PLUGINS.PBA.isDevModeOn()
     ```

     O valor de retorno é `true`. Isso indica que o modo de teste está ativo.   
     [![PBATestingWebSDKIntegrationIsDevModeOn_en-us.png](https://files.readme.io/4b5d8f3c3ef31148c9f3cd4021d83404810382fd654defa86d733c0377ffd968-360011482797.png)](https://files.readme.io/4b5d8f3c3ef31148c9f3cd4021d83404810382fd654defa86d733c0377ffd968-360011482797.png)

</Accordion>

<div id="send-test-events" />

<Accordion title="Enviar eventos de teste">

* No modo de teste, os eventos enviados são exibidos na página de integração de teste
* Atenção! Os eventos de teste são processados e, posteriormente, serão incluídos nos relatórios do PBA. Para evitar a distorção de relatórios, preencha `eventRevenue` com valores baixos (pequenos). Se nenhum valor for enviado, o PBA o preencherá com 0.

Envie eventos de exemplo de cada um dos tipos descritos.

| Etapa | Ação<br /><br />(Digite comandos) | Página de integração de teste do Web SDK<br /><br />(Resultado esperado) |
| --- | --- | --- |
| 1 | Abra uma nova aba no navegador e vá para qualquer página do seu site. | O PBA registra um `'pageLoad'` sempre que seu site abrir/atualizar:<br /><br />[![PBATestingWebSDKPageLoadEvent_en-us.png](https://files.readme.io/25ae1b2efbfea897caeb5da94d683b3465c9068245acbedb976959cb8fd3cc77-360011369638.png)](https://files.readme.io/25ae1b2efbfea897caeb5da94d683b3465c9068245acbedb976959cb8fd3cc77-360011369638.png) |
| 2 | Faça login/registre-se em seu site como usuário <Anchor target="_blank" href="/marketers/pt/docs/pba-web-sdk-integration-guide#setting-customer-user-id-after-signup">para disparar um evento setCustomerUserId</Anchor>. | [![mceclip3.png](https://files.readme.io/7fb5276c5d24b1c6128aaee60684e9f2941e1686eeef4dcf4df4a91c86c9ebb6-360011199558.png)](https://files.readme.io/7fb5276c5d24b1c6128aaee60684e9f2941e1686eeef4dcf4df4a91c86c9ebb6-360011199558.png) |
| 3 | <Anchor target="_blank" href="/marketers/pt/docs/pba-web-sdk-integration-guide#recording-event-scenarios">Comece a enviar eventos da web</Anchor> para verificar se o PBA os processa corretamente.<br /><br />**Observação:**<br /><br />Se não for especificado, `eventRevenue` e `eventRevenueCurrency` são preenchidos com valores padrão:<ul><li>`eventRevenueCurrency: "USD"`</li><li>`eventRevenue: 0`</li></ul>[![PBAWebSDKTestEventEVENT_en-us.png](https://files.readme.io/208c42edaa132b69279a5a99232763e2e9da1be950dd3dec3b5636d650e540c8-360011317918.png)](https://files.readme.io/208c42edaa132b69279a5a99232763e2e9da1be950dd3dec3b5636d650e540c8-360011317918.png)<br /><br />Ver <Anchor target="_blank" href="/marketers/pt/docs/pba-web-sdk-integration-guide#web-sdk-event-parameters">Parâmetros de evento do Web SDK para obter informações adicionais.</Anchor> | [![mceclip5.png](https://files.readme.io/51f3c824c253bc825d22c672393adc002c365a2084d71ce6183e412b76e9d3eb-360011199578.png)](https://files.readme.io/51f3c824c253bc825d22c672393adc002c365a2084d71ce6183e412b76e9d3eb-360011199578.png) |

</Accordion>

<div id="troubleshooting" />

## Solução de problemas

<div id="events-do-not-display-in-the-test-page" />

<Accordion title="Os eventos não são exibidos na página de teste">

1. Nas ferramentas de desenvolvedor do navegador, vá para a aba **Rede**.
2. No campo de filtro, digite "websdk".
3. Com base no código de resposta HTTP, proceda da seguinte forma:
   * 200: Entre em contato com o suporte técnico da AppsFlyer.
   * 400: Verifique se todos os parâmetros estão incluídos em " ".

</Accordion>

<div data-zendesk-anchors="test-pba-web-events=testar-eventos-da-web-do-pba h_01HKW32BE04AKHFMY853211C1A=testar-eventos-da-web-do-pba web-sdk-integration-test-page=p%C3%A1gina-de-teste-de-integra%C3%A7%C3%A3o-do-web-sdk h_01HKW32BE0Z2ZKTBHSCSWVT04N=p%C3%A1gina-de-teste-de-integra%C3%A7%C3%A3o-do-web-sdk procedures=procedimentos h_01HKW32BE0VA0X9ZX4Z26EY6CZ=procedimentos h_01HKW32BE08Z9CCMBPK4Z0854C=enable-test-mode h_01HKW32BE0E4A1W221FKY97EZB=send-test-events troubleshooting=solu%C3%A7%C3%A3o-de-problemas h_01HKW32BE1HFV0NM64QMASBCCT=solu%C3%A7%C3%A3o-de-problemas h_01HKW32BE1QHV0W6ZDYHG94RQA=events-do-not-display-in-the-test-page" />
