---
title: >-
  Boletim: Ação necessária—Obtenha dados brutos dos anúncios do Meta com o
  Referenciador da instalação do Google
metadata:
  keywords:
    - Advertisers
    - Marketers
    - Mobile Attribution
table_of_contents: false
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
  created_at: '2021-10-21T07:02:51Z'
  edited_at: '2026-08-18T00:18:34Z'
  id: 4409322107537
  locale: pt
  section: Bulletins
  section_id: 6551161473041
  url: https://support.appsflyer.com/hc/pt/articles/4409322107537
---

<Table>
  <tbody>
    <tr>
      <td>
        **Novidades**
      </td>
      <td>
        Obtenha dados brutos da campanha do Meta ads de anúncios direcionados para a Google Play Store usando o referenciador da instalação.
      </td>
    </tr>
    <tr>
      <td>
        **O que vai mudar?**

        **![Information_icon.png](https://files.readme.io/cc1ff74668360a2be64ec90db8f771d751b0a95847ecaee582c2e31c60e310cf-20445036062993.png)**
      </td>
      <td>
        A partir de 29 de outubro de 2021, os dados de atribuição no nível do usuário (dados brutos) trazidos pelo Meta ads **após** essa data serão restritos. O Meta ads disponibiliza esses dados para MMPs como a AppsFlyer, mas não para anunciantes.

        No entanto, se o anúncio direcionar os usuários para a Google Play Store, os campos de atribuição estarão disponíveis para os anunciantes no Referenciador da instalação do Google, que deve ser <Anchor target="_blank" href="/marketers/pt/docs/basic-sdk-integration-guide#attribute-apps-published-on-google-play">integrado ao seu aplicativo.</Anchor> Os campos fornecidos pelo referenciador preenchem os relatórios de dados brutos da AppsFlyer disponíveis para você e permitem que a AppsFlyer atribua usuários que não têm um ID de anúncios (habilitado para LATs).

        O uso do mecanismo de referência requer o SDK V5.4+ da AppsFlyer

        **Observação:** os dados do referenciador têm prioridade sobre os dados fornecidos pela API e não são restritos.

        Os dados no referenciador são criptografados pelo Meta ads e são descriptografados usando uma chave disponível em sua conta de desenvolvedor de anúncios do Meta. Você deve nos fornecer a chave de descriptografia descrita na linha de ações necessárias.

        **Campos de atribuição de campanha disponíveis por meio do referenciador:**

        * ID do anúncio
        * Nome do anúncio
        * ID do conjunto de anúncios
        * Nome do conjunto de anúncios
        * ID da campanha
        * Nome da campanha
        * ID da conta
        * Canal
        * Tipo de anúncio (esse campo ainda não está disponível)

        **Observação**:

        * Nenhum outro campo está disponível por meio do referenciador.
        * Essa solução se aplica à atribuição de cliques e não à atribuição de exibição.
        * Os dados de referência não são aplicáveis a campanhas de reengajamento, pois os usuários não passam pela loja.

        **Quando a AppsFlyer implementará essa mudança?**

        * A partir de 29 de outubro de 2021:
          * Restrições do Meta ads para dados de click-through (em outras palavras, dados brutos de atribuição) são implementadas.
          * Os anunciantes podem atualizar a chave de descriptografia do referenciador na AppsFlyer.
        * A partir de 3 de novembro de 2021:
          * A AppsFlyer preenche dados brutos e atributos usando dados fornecidos pelo mecanismo de referência.
      </td>
    </tr>
    <tr>
      <td>
        **Resumo da disponibilidade de dados**
      </td>
      <td>
        <table><tbody><tr><th rowspan="2">Como é atribuído</th><th rowspan="2">Fonte de dados de atribuição</th><th colspan="2">Dados disponíveis para anunciantes </th><th>Observações</th></tr><tr><th>Dados brutos</th><th>Dados agregados</th><th> </th></tr><tr><td>Cliques</td><td>Referenciador (aplicável a aplicativos Android baixados da Google Play Store)</td><td>Disponíveis</td><td>Disponíveis</td><td><ul><li>Dados de atribuição de usuários LAT disponíveis.</li><li>O referenciador tem prioridade sobre os dados MMP se ambos estiverem disponíveis.</li><li>Não se aplica a campanhas de reengajamento.</li></ul></td></tr><tr><td>Cliques</td><td>API MMP</td><td>Restrito\*</td><td>Disponíveis</td><td> </td></tr><tr><td>Exibição (view-through)</td><td>API MMP</td><td>Restrito\*</td><td>Disponíveis</td><td>Mecanismo de referência não compatível.</td></tr><tr><td colspan="5"><p><strong>Observação:</strong> quando a disponibilidade de dados é restrita:</p><ul><li><ul><li>Os postbacks de eventos de instalação e in-app são enviados apenas para as ad networks restritivas. Parceiros terceirizados, como parceiros de análise, não recebem postbacks para atribuição restrita. </li><li>Postbacks não atribuídos (sem campos de atribuição) são enviados para ad networks que foram configuradas para receber todos os eventos (incluindo orgânicos e não atribuídos). Isso inclui Meta campaign management partners.</li></ul></li></ul></td></tr></tbody></table>
      </td>
    </tr>
    <tr>
      <td>
        **Ação necessária**
      </td>
      <td>
        **Para obter sua chave de descriptografia do Meta ads:**

        [As informações a seguir são baseadas nas informações fornecidas a nós pelo Facebook]

        1. Faça o login no portal do desenvolvedor do Meta.
        2. Navegue até **Meus aplicativos** no canto superior direito.
        3. Selecione o aplicativo para o qual você gostaria de acessar sua chave de descriptografia.
        4. Navegue até **Configurações** > **Básico** no lado esquerdo da página.

           [![FBUIforKey.png](https://files.readme.io/253be6d4cd2a75cc2c038c5b14ed3df067612c46bea174475adba3d196f25789-30354101891985.png)](https://files.readme.io/253be6d4cd2a75cc2c038c5b14ed3df067612c46bea174475adba3d196f25789-30354101891985.png)
        5. Vá até a seção **Android** e você verá sua chave de descriptografia chamada **Chave de descriptografia do referenciador da instalação** abaixo do campo **Nomes do pacote**. **Observação**: essa é a mesma seção na qual você configurou o nome do pacote e a Google Play Store.

        **Para ativar o mecanismo de referência na AppsFlyer.**

        1. [Obrigatório] Verifique se o SDK da AppsFlyer V5.4+ é a versão utilizada em seu aplicativo. Não utilize versões anteriores.
        2. Siga um dos procedimentos abaixo:
           1. [Em breve] Defina a chave de descriptografia via API.
           2. Para definir a chave de descriptografia por meio da interface do usuário:
              1. Na AppsFlyer, vá para **Configuração** > **Integrações ativas**.
              2. Selecione Meta ads.  

                 ![meta-ads-install-referrer-decryption-key.png](https://files.readme.io/adf6caa8d7cee493695eb8fb7db1b61c60e6a1cef0273e615c43a05ad8a9485d-13963525463825.png)
           3. Na aba **Integração**, cole a chave em **Instalar** chave de descriptografia **do referenciador**.
           4. Clique em **Salvar integração.**
      </td>
    </tr>
    <tr>
      <td>
        **Atualizar a chave de descriptografia via API**
      </td>
      <td>
        **[Em breve]**

        Faremos uma API que atualiza a chave de descriptografia.
      </td>
    </tr>
    <tr>
      <td>
        **Disponibilidade de dados brutos daqui para frente**
      </td>
      <td>
        * Se os dados de atribuição forem obtidos por meio do mecanismo de referência, os dados serão irrestritos e estarão disponíveis por meio dos relatórios de dados brutos.
        * Se os dados de atribuição forem obtidos por meio da API, os dados brutos dos usuários trazidos pelo Meta ads serão atribuídos ao canal de mídia *restrito*
        * Essa mudança não tem impacto nos dados brutos dos usuários trazidos antes da mudança. Em outras palavras antes de 29 de outubro de 2021, 08:00 UTC.
      </td>
    </tr>
    <tr>
      <td>
        **O que se mantém igual**
      </td>
      <td>
        A AppsFlyer continua a receber dados do Meta ads no nível do dispositivo, o que significa que nossas habilidades de atribuição e geração de relatórios (incluindo atribuição multi-touch, LTV, ROI, chort, relatórios de retenção, proteção contra fraudes, Audiences e outros serviços) permanecem inalteradas. Veja <Anchor target="_blank" href="/marketers/pt/docs/aggregated-and-analytics-reporting-overview">ferramentas de relatórios agregados e analytics</Anchor>.

        **Observação**: se você nos fornecer a chave de descriptografia, podemos atribuir usuários que não têm um ID de anúncio (habilitado para LAT). Isso melhora a precisão da atribuição.
      </td>
    </tr>
    <tr>
      <td>
        **Mudanças na atribuição**
      </td>
      <td>
        Deferred deep linking via GCD está disponível para aplicativos Android usando o mecanismo do Referenciador de Instalação do Google. Não está disponível para aplicativos iOS.
      </td>
    </tr>
    <tr>
      <td>
        **Perguntas frequentes**
      </td>
      <td>
        * **A chave de descriptografia do referenciador de instalação precisa ser atualizada?**  
          Depois de enviada, a chave de descriptografia não precisa ser atualizada.
        * **Quando posso ver os dados no nível do usuário nos relatórios de dados brutos?**  
          Os dados no nível do usuário são exibidos nos relatórios de dados brutos assim que uma chave de descriptografia do referenciador de instalação válida é enviada e uma instalação é atribuída aos anúncios do Meta.
        * **Os dados de atribuição no nível do usuário estão disponíveis para instalações que ocorreram entre 29 de outubro de 2021 e 3 de novembro de 2021?**  
          Infelizmente, esses dados não estão disponíveis.
      </td>
    </tr>
  </tbody>
</Table>
