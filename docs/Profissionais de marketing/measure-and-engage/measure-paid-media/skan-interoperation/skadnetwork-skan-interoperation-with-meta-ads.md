---
title: Interoperabilidade do SKAdNetwork (SKAN) com anúncios do Meta
metadata:
  keywords:
    - Facebook
    - Advertisers
    - Marketers
    - SKAN
    - SKAdNetwork
    - SKAdNetwork (SKAN)
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - SKAdNetwork (SKAN)
  created_at: '2021-01-17T10:08:28Z'
  edited_at: '2026-09-16T00:29:21Z'
  id: 360017095198
  locale: pt
  section: SKAN interoperation
  section_id: 6552115163153
  url: https://support.appsflyer.com/hc/pt/articles/360017095198
---
> **Visão geral:** A interoperabilidade permite que os anúncios do Meta partilhem dados SKAN descodificados com a AppsFlyer e que a AppsFlyer partilhe os seus dados de medição CV (mapeamento) com os anúncios do Meta.

<Embed title="Interoperabilidade do SKAdNetwork (SKAN) com anúncios do Meta" typeOfEmbed="iframe" url="https://fast.wistia.com/embed/iframe/15jnbml3h7" providerUrl="https://fast.wistia.com" />

<div id="skan-interoperability-appsflyer---meta-ads" />

## Interoperabilidade do SKAN: AppsFlyer &lt;-> Anúncios Meta

Se trabalha com múltiplos parceiros de redes publicitárias, é melhor configurá-los na AppsFlyer. Desta forma, as métricas de desempenho do SKAN, enriquecidas com outras métricas como o custo, ficam disponíveis através da plataforma AppsFlyer.

<div id="scope-of-skan-interoperability-with-meta-ads" />

#### Âmbito da interoperabilidade do SKAN com anúncios Meta

A interoperação com anúncios do Meta permite o seguinte:

* A AppsFlyer e os anúncios do Meta partilham o esquema de valor de conversão (CV) do SKAN, permitindo que ambos forneçam métricas de desempenho.
* A AppsFlyer suporta todos os objetivos de campanha dos anúncios do Meta, permitindo a otimização das campanhas:
  * Instalação de aplicações móveis (MAI)
  * Engajamento de aplicações móveis (MAE)
  * Otimização de valor (VO)
* Após ativar a integração do SKAN, ocorre o seguinte:
  * O SDK do Facebook deixa de atualizar o CV do SKAN (*interruptor de desligamento*).
  * O SDK da AppsFlyer atualiza o CV.
  * Os anúncios do Meta partilham dados de postback do SKAN para inclusão no painel do SKAN e nos relatórios agregados.

Outras considerações:

* Se não ativar a integração de parceiros do SKAN, no painel do SKAN, as instalações oriundas dos anúncios do Meta serão contabilizadas como instalações orgânicas.
* No contexto de atribuição da AppsFlyer (painel de visão geral):
  * As instalações de usuários com consentimento obtidas através dos anúncios do Meta são atribuídas corretamente.
  * Os usuários sem consentimento são atribuídos como orgânicos.
* <Anchor target="_blank" href="/marketers/pt/docs/self-reporting-networks-srns#ios-145-srn-attribution">Implicações do iOS 14.5 nos relatórios de SRNs</Anchor>
* Nossa integração do MMP com o Meta Ads sempre implementa o sinalizador *Advertiser Tracking Enabled*. (Essas informações são fornecidas de acordo com a lista de fevereiro de 2021 de diretrizes do iOS 14 para aplicativos do Meta Ads).

<div id="considerations" />

#### Considerações

* Após a ativação da interoperabilidade, cada vez que alterar as configurações de medição, não precisará repetir o procedimento de integração MMP descrito neste artigo. Isso significa que não precisa de copiar novamente o URL de ligação do MMP.
* Na AppsFlyer, se desativar a medição SKAN, os anúncios Meta não conseguem mais obter o mapeamento de CV.
* SDK da AppsFlyer vs. SDK do Facebook: O SDK do Facebook é adequado apenas para campanhas com anúncios da Meta. Se realizar campanhas com vários parceiros, utilizando o SDK da AppsFlyer poderá visualizar os dados de todos os parceiros.
* Veja a seção sobre [discrepâncias](/docs/skadnetwork-skan-interoperation-with-meta-ads#troubleshooting-discrepancies-and-faq) neste artigo.

<div id="meta-ads-app-install-ads-guidance" />

#### Diretrizes para anúncios de instalação de apps Meta

Ao configurar suas campanhas de instalação de apps para iOS 14 no Meta Ads, considere as seguintes <Anchor target="_blank" href="https://developers.facebook.com/blog/post/2020/10/29/preparing-our-partners-ios-14-latest-guidance-on-skadnetwork/">orientações do Meta Ads</Anchor>:

* É permitido um máximo de 9 campanhas por aplicativo, cada uma com 5 conjuntos de anúncios.
* Você não precisa de uma conta separada para as campanhas no iOS 14. Você pode executar campanhas no iOS 14 a partir de contas existentes.
* Há uma relação entre o método de otimização do Meta Ads e o tipo de mensuração que você seleciona na AppsFlyer da seguinte forma:
  * **Mensuração de receita**: VO e AEO
  * Mensuração de conversão: AEO – Inclui eventos padrão dos anúncios da Meta e eventos de compra. Você deve mapear o evento do aplicativo na AppsFlyer para o evento relevante do Meta Ads.

<div id="interoperation-procedures" />

## Procedimentos de interoperação

Conclua os procedimentos a seguir para ativar a interoperação.

Para atribuição de instalação de apps:

<div id="allow-facebook-to-share-skadnetwork-data-with-appsflyer" />

<Accordion title="Permitir que os anúncios da Meta partilhem dados SKAN com a AppsFlyer">

Permita que os anúncios da Meta partilhem dados SKAN com a AppsFlyer. Caso contrário, não verá instalações SKAN atribuídas aos anúncios da Meta no painel SKAN da AppsFlyer.

Este procedimento precisa de ser realizado uma vez por aplicação.

**Para conceder permissão aos anúncios da Meta para partilhar dados SKAN com a AppsFlyer:**

1. No AppsFlyer, acesse **Colaborar > Integrações de parceiros > Integrações ativas**.
2. Procure e selecione anúncios da Meta.
3. Aceda ao separador **SKAN**.

   ![skan_repprtiing_-_connected_accounts.png](https://files.readme.io/41514c220de398871292c990e448e2bc8ce450a17512649842cdb2bc4fd78846-40032591356817.png)
4. Clique em **fazer login**. A conta que você usa precisa ser de administrador ou anunciante, <Anchor target="_blank" href="https://www.facebook.com/business/help/155909647811305?id=829106167281625">com as seguintes permissões</Anchor>:
   * Permissão para leitura de anúncios. Consulte [para verificar se você tem a permissão de leitura de anúncios](/docs/skadnetwork-skan-interoperation-with-meta-ads#verifying-the-ads_read-permission).
   * Acesso ao ID da app anunciada nas definições do Meta Business Partner.
5. Siga as instruções no interface do utilizador.  
   A Meta gera um <Anchor target="_blank" href="https://developers.facebook.com/docs/facebook-login/guides/access-tokens/get-long-lived/">token de acesso</Anchor> que permite o compartilhamento de dados com a AppsFlyer. Após concluir o processo, será redirecionado para a AppsFlyer.
6. Se esta é a primeira vez que configura esta integração, verifique se o estado da conta apresenta **Aguardando sincronização**.  
   Esta mensagem persiste até recebermos dados dos anúncios Meta.
7. Espere até depois das 02:00 UTC do dia seguinte e verifique se o estado muda para **Dados extraídos com sucesso.**  
   Os dados no painel SKAN são atualizados diariamente até às 08:00 UTC.
8. Leia a secção sobre as [diferenças de medição](/docs/skadnetwork-skan-interoperation-with-meta-ads#measurement-and-timing-differences-between-appsflyer-and-facebook).

</Accordion>

Para atribuição de eventos na app:

<div id="share-cv-schema-with-facebook" />

<Accordion title="Partilhe o esquema CV com os anúncios Meta.">

![SKAdNetwork-Facebook-AppsFlyer_integration__5_.png](https://files.readme.io/f5965dc535a47b3d665a3cf1ae1df564a176ff9be76d5fb4a9f01d80b0e58994-40032652599953.png)

<div id="enabling-appsflyer-skan-interoperation-with-meta-ads" />

#### Ativação da interoperação SKAN da AppsFlyer com anúncios Meta.

<Table>
  <thead>
    <tr>
      <th>
        Passo
      </th>
      <th>
        Ação
      </th>
      <th>
        Detalhes
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td><span id="1"></span>
        1
      </td>
      <td>
        Pré-requisitos da app
      </td>
      <td>
        * Adote o <Anchor target="_blank" href="/marketers/pt/docs/sdk-integration-overview">SDK</Anchor> mais recente da AppsFlyer no seu app.
      </td>
    </tr>
    <tr>
      <td><span id="2"></span>
        2
      </td>
      <td>
        Revisão das definições do SKAN
      </td>
      <td>
        Verifique se a <Anchor target="_blank" href="/marketers/pt/docs/skadnetwork-skan-solution-guide">solução SKAN</Anchor> da AppsFlyer está configurada e ativa. Assim, o SDK da AppsFlyer pode chamar as APIs SKAN e definir o CV.

        **Para ver as definições do SKAN**:

        1. Na AppsFlyer, vá a **Definições** > **SKAN Conversion Studio**.
        2. Clique no ícone ⋮ e verifique se a **mensuração SKAN** está ativa.  
           [![Measurement_mode_on_facebook_ads.png](https://files.readme.io/310ec3b7cb313dfbf00e073ab808231f48a995e7e6a5c482ccd6c997a3714483-40032652602257.png)](https://files.readme.io/310ec3b7cb313dfbf00e073ab808231f48a995e7e6a5c482ccd6c997a3714483-40032652602257.png)
        3. Selecione o modo de medição que prefere.  
           Saiba mais sobre o <Anchor target="_blank" href="/marketers/pt/docs/skan-conversion-studio">SKAN Conversion Studio</Anchor>.
        4. Registe os nomes exatos dos eventos definidos. Vai precisar deles na etapa seguinte. **Nota:** Os nomes são diferenciados por maiúsculas e minúsculas.
      </td>
    </tr>
    <tr>
      <td><span id="in-app-event-mapping"></span>
        3
      </td>
      <td>
        Mapeamento de eventos na app
      </td>
      <td>
        Revise, e se necessário, faça alterações nos mapeamentos de eventos na app.

        **Para ver e definir mapeamentos de eventos na app**:

        1. No AppsFlyer, acesse **Colaborar > Integrações de parceiros > Integrações ativas**.
        2. Selecione **anúncios Meta**.
        3. [Obrigatório] No separador **Integração**, ative os **Postbacks de eventos na app**.
           * Deve mapear o tipo de medição SKAN atualmente escolhido. O tipo de medição predefinido é a receita.  
             ![in-app_events_fb_en-us.png](https://files.readme.io/98e2c8048444331c5d24343e683605e8388ee93bbfcb70aa5e8dad183c995859-40032591364241.png)
           * Confirme se os eventos in-app que definiu na medição SKAN (**evento da AppsFlyer**) estão associados aos identificadores de eventos do Meta Ads (**associados ao evento do parceiro**). Se você não mapear os eventos, o Meta Ads não poderá ser otimizado e contabilizará somente as instalações.

             <div id="h_01H8XRMVR5GY77K7GJ4TXGWEHS" />

             > 📘 **Nota**
             >
             > Ao adicionar, alterar ou remover um valor de conversão (CV) no SKAN Conversion Studio, certifique-se de que o evento está mapeado nos **postbacks de eventos na aplicação**. Caso contrário, o CV não será atualizado nos anúncios Meta.
             >
             > #### <span id="inapp-event-mapping-guide"></span>Guia de mapeamento de eventos in-app


        | Tipo de medição | Requisito de mapeamento |
        | --- | --- |
        | <span id="custom"></span><Anchor target="_blank" href="/marketers/pt/docs/skan-conversion-studio#custom">Personalizado</Anchor> | Associe os eventos in-app que definiu em Personalizado aos eventos Meta Ads correspondentes.<br /><br />Para reportar receitas por postback, deve definir **Enviar receita** como **Valores e receita**.<br /><br />![SendValueandRevenue.png](https://files.readme.io/412c60db2b09d80a989b7546a6819aa1b030732e0ce004b323dc09db1015c238-11331054047377.png)<br /><br />*af\_skad\_revenue* é utilizado para a receita total e é mapeado para o evento de receita do Meta Ads, habitualmente *fb\_mobile\_purchase.*<br /><br />Nota! Não há problema em mapear mais de um evento para *fb\_mobile\_purchase*. |
        | <span id="revenue"></span>Resultados | Ao reportar receitas por postback para redes de anúncios, certifique-se de que os mapeamentos dos postbacks de eventos in-app incluem os eventos de receita in-app que definiu.<br /><br />*af\_skad\_revenue* é utilizado para a receita total e é mapeado para o evento de receita do Meta Ads, habitualmente *fb\_mobile\_purchase.*<br /><br />Nota! Não há problema em mapear mais de um evento para *fb\_mobile\_purchase*. |
        | <span id="conversion"></span>Conversão | Mapeie entre 1 a 6 eventos de conversão para os eventos de Meta Ads correspondentes. |

        4. Clique em **Guardar integração**.
        5. Desça até **Configuração SKAN** e clique no **URL de conexão MMP** para copiá-lo. Na próxima secção, indicaremos onde colar o URL no Meta.

           ![meta_ads_skan_configuration_mmp_url.png](https://files.readme.io/341918a757014d51a240898d157a6576b50cb269ad3bd0a574e4e6aef9d504ef-40032652607377.png)
      </td>
    </tr>
    <tr>
      <td><span id="4"></span>
        4
      </td>
      <td>
        Conecte a AppsFlyer aos Meta Ads
      </td>
      <td>
        1. Nos Meta Ads, abra o gestor de eventos e vá ao separador **Definições**.

           [<Image alt="FacebookSkadNetworkSetup.jpg" src="https://files.readme.io/8720d8f951915091df74bbe1b1154a1c5af80a547f81bb70bf66ac74f5ff6e54-40032652609297.jpg" width="503px" />](https://files.readme.io/8720d8f951915091df74bbe1b1154a1c5af80a547f81bb70bf66ac74f5ff6e54-40032652609297.jpg)
        2. Nas definições, clique em **Configurar eventos**.

           [<Image alt="mceclip0.jpg" src="https://files.readme.io/208040fdd63fcd80ddc2cac6d0f49ff6b78f5f788f85a5022f5e3c747f268ef9-40032591379217.jpg" width="503px" />](https://files.readme.io/208040fdd63fcd80ddc2cac6d0f49ff6b78f5f788f85a5022f5e3c747f268ef9-40032591379217.jpg)
        3. No Events Manager, selecione **Importar do aplicativo do parceiro**. **Etapa 1**:

           [<Image alt="mceclip1.png" src="https://files.readme.io/61d55b6fe05055fbc9b8db5a412c6da7d80807abec4b6b31a7b357fb76fcdf34-40032652611729.png" width="503px" />](https://files.readme.io/61d55b6fe05055fbc9b8db5a412c6da7d80807abec4b6b31a7b357fb76fcdf34-40032652611729.png)
        4. Será apresentado um campo para colar o **URL de conexão MMP**.   
           Isso atualiza o Meta com o mapeamento de CV e **instrui o SDK do Facebook na sua aplicação a deixar de configurar o CV**. Se a importação de uma aplicação parceira estiver desativada—[Solucionar problemas](/docs/skadnetwork-skan-interoperation-with-meta-ads#import-from-partner-app-is-disabled).
        5. Siga as instruções na interface do utilizador do Meta Ads. Ocorre uma das seguintes situações:
           1. Conseguiu colar com sucesso o **URL de ligação MMP** na interface do utilizador do Meta Ads. Parabéns! Concluiu a integração. Leia as notas que seguem.
           2. A colagem do **URL de ligação MMP** falha e é exibida uma mensagem de erro na interface do utilizador do Meta Ads. Nesse caso:  
              - Aguarde 24 horas e repita este procedimento.  
              - Se o erro persistir (mais de 24 horas), entre em contacto com o suporte da AppsFlyer.

        Notas

        * É necessário executar este procedimento apenas uma vez. Ou seja, não há necessidade de copiar e colar o URL de ligação após mudar as configurações de medição na AppsFlyer. Por exemplo, se mudar da medição de receitas para a medição de conversões, os anúncios Meta utilizarão o URL existente para obter o esquema atual.
        * Concluir o procedimento permite que os anúncios Meta obtenham o esquema CV da AppsFlyer através de uma estrutura aleatória proprietária. Não há como você configurar isso.
        * Demora até 24 horas para que as configurações de medição atualizadas entrem em vigor nos anúncios Meta.
      </td>
    </tr>
    <tr>
      <td><span id="5"></span>
        5
      </td>
      <td>
        Configuração da campanha iOS 14
      </td>
      <td>
        Nos anúncios Meta, verifique se a configuração da campanha do iOS 14 está ativada.

        Esta configuração encontra-se na página de definições da **Campanha de instalações de novas aplicações**.

        [![FBiOS14.png](https://files.readme.io/3f45a8480affad430adaac46a603bf43b47e8254314226077e5d9f8255ca2e97-40032652616209.png)](https://files.readme.io/3f45a8480affad430adaac46a603bf43b47e8254314226077e5d9f8255ca2e97-40032652616209.png)
      </td>
    </tr>
  </tbody>
</Table>

</Accordion>

<div id="additional-information" />

## Informações adicionais

<div id="turning-off-the-skan-integration" />

<Accordion title="Desativação da integração SKAN">

Ao desativar a integração do Meta Ads, não basta desativar o botão **Ativar parceiro**; você precisa remover separadamente as conexões SKAN para interromper o registro de dados SKAN.

**Para desativar a integração SKAN:**

1. Na AppsFlyer, acesse **Colaborar > Integrações de parceiros > Integrações ativas.**
2. Procure e selecione anúncios da Meta.
3. Aceda ao separador **SKAN**.
4. Clique no ícone de eliminação da conta que deseja remover.

</Accordion>

<div id="measurement-and-timing-differences-between-appsflyer-and-facebook" />

<Accordion title="Diferenças de medição e de tempo entre AppsFlyer e anúncios Meta">

| Item | Detalhes |
| --- | --- |
| Nomes de eventos na aplicação | Até 15 de agosto de 2021, os nomes de eventos no painel usavam os nomes de eventos dos anúncios Meta. De agora em diante, isso já não se aplica. |
| Métricas de utilizadores convertidos no modo de receita | [Descontinuado em 16 de agosto de 2021]<br /><br />~~No modo de receita, a métrica de usuários convertidos (usuários pagantes) não considera o número de usuários que informam a receita por meio de campanhas do Meta Ads devido à convenção de nomenclatura mencionada na seção anterior (nomes de eventos in-app) mencionada na seção anterior (nomes de eventos in-app) mencionada na seção anterior (nomes de eventos in-app)~~ |
| Disponibilidade inicial de dados | Na primeira sincronização de dados após a integração, assim como nas sincronizações posteriores, a AppsFlyer recebe retroativamente os dados do Meta Ads por até 7 dias. |
| Data de instalação | A AppsFlyer e os anúncios Meta diferenciam-se na forma como determinam a data de instalação. Considere:<ul><li>Os postbacks do iOS SKAN não contêm um carimbo de data/hora real de instalação.</li><li>Os anúncios Meta consideram a hora de chegada do postback como hora de instalação, tendo em conta o fuso horário da app ao definir a data.</li><li>A AppsFlyer determina a hora de instalação de acordo com as <Anchor target="_blank" href="/marketers/pt/docs/skan-conversion-studio#activity-window">configurações da janela de atividade</Anchor>. Nem o fuso horário da app nem o fuso horário da conta de anúncios Meta são considerados no cálculo.</li></ul> |
| Relevância dos dados | <ul><li>Recolhemos dados SKAN dos anúncios Meta às 01:00 UTC.</li><li>Os painéis e dados agregados são atualizados 7 horas depois.</li></ul> |

</Accordion>

<div id="verifying-the-ads_read-permission" />

<Accordion title="Verificar a permissão ads_read">

A permissão ads\_read fornece aos clientes de anúncios Meta acesso à API para dados de desempenho dos anúncios, permitindo a sua utilização em painéis personalizados e análise de dados.

**Para confirmar se a sua conta Meta Ads tem a permissão ads\_read:**

1. Acesse sua <Anchor target="_blank" href="https://developers.facebook.com/apps">conta de desenvolvedor do Meta Ads.</Anchor>
2. Selecione um ID do aplicativo do Facebook.
3. Vá para **Casos de uso > Permissões e recursos**.
4. Pesquise por `ads_read`.
5. Confirme se `ads_read` está com o status “pronto para uso”. Se esse for o caso, nenhuma outra ação é necessária.
6. Se `ads_read` não estiver com o status “pronto para uso”, solicite a permissão e envie a solicitação.
7. Depois que a Meta aprovar a solicitação, volte à página de integração do Meta Ads na AppsFlyer e clique em **Conectar**.  
   **Observação:** A Meta renomeou e reorganizou essa seção recentemente. É esperado que você não veja o status de **análise do aplicativo**. O local correto para solicitar permissões é em **Casos de Uso > Permissões e recursos**.

</Accordion>

<div id="troubleshooting-discrepancies-and-faq" />

<Accordion title="Resolução de problemas, discrepâncias e perguntas frequentes">

| Ação | Detalhes |
| --- | --- |
| <span id="not-seeing-skan-inapp-events-from-meta"></span>Não está vendo os eventos in-app da SKAN na Meta? | Se você está vendo as instalações, mas não há eventos in-app das campanhas da SKAN na Meta, esta lista ajudará a identificar o que falta.<br /><br />Observação: se não está vendo as instalações, primeiro consulte a lista de instalações.<br /><br />**<span id="quick-fix-checklist"></span>Lista de soluções rápidas**<br /><br />**1º passo**<ol><li>Confirme o mapeamento de eventos da SKAN na AppsFlyer.</li><li>Acesse **Configurações** > **Conversion Studio da SKAN**.</li><li>Certifique-se de que os eventos in-app que você deseja mensurar estão corretamente mapeados.</li></ol>**Etapa 2:**<ol><li>Verifique o mapeamento de eventos da integração do Meta Ads.</li><li>Na AppsFlyer, acesse **Colaborar > Integrações de parceiros > Integrações ativas** e selecione **Meta Ads**.</li></ol><ul><li>Garanta que os mesmos nomes de eventos (maiúsculas e minúsculas) do SKAN Conversion Studio estejam mapeados em “Postbacks de eventos in-app” para a Meta.</li><li>Se estiver mensurando receitas, verifique se af\_skad\_revenue está incluído e mapeado para fb\_mobile\_purchase.</li></ul>**<span id="still-not-working"></span>Ainda não funcionou?**<br /><br />**>Verificação do volume mínimo de instalação**<ul><li>Você precisa de um número mínimo de instalações por campanha da Meta por dia para exibir os dados pós-instalação da SKAN.</li><li>As instalações abaixo desse número mínimo aparecem com valores de conversão nulos e os dados de eventos não podem ser descodificados.</li></ul>Esse limite não é revelado pela Meta, mas você pode verificar a taxa do valor de conversão nulo no dashboard da SKAN da sua campanha. Se for ~100%, você precisa aumentar o número de instalações. Ajuste os filtros da base de usuários ou aumente as instalações das campanhas. |
| <span id="facebook-cant-connect"></span>Os anúncios Meta não conseguem estabelecer ligação | **Sintoma**<br /><br />Nos anúncios Meta, se receber a mensagem, *não conseguimos estabelecer ligação. Verifique se está a usar o URL correto. Se o problema continuar, contacte a aplicação parceira para obter assistência.*<br /><br />**Ação corretiva**<br /><br />Na AppsFlyer, verifique se ativou o mapeamento de eventos na aplicação e mapeou os seus eventos AppsFlyer para os eventos dos seus anúncios Meta. (Como descrito no mapeamento de eventos na aplicação referido na secção anterior)<br /><br />[Orientações atualizadas em 20 de abril de 2021] |
| <span id="event-priority"></span>Prioridade dos eventos | Pergunta: Como defino a prioridade dos eventos nos anúncios Meta?<br /><br />Resposta: Não é necessário definir prioridades nos anúncios Meta. Esta funcionalidade de prioridade aplica-se a aplicações que usam o SDK do Facebook para definir o CV. No seu caso, é o SDK da AppsFlyer que está a definir o CV. Desconsidere a opção de prioridade nos anúncios Meta. A AppsFlyer mede 6 eventos na conversão sem atribuição de prioridade.<br /><br />[Orientações atualizadas em 20 de abril de 2021] |
| <span id="event-occurrences"></span>Ocorrência de eventos | Pergunta: Porque é que tenho mais ocorrências de eventos mostradas na AppsFlyer do que nos anúncios Meta?<br /><br />Resposta: O Meta Ads contabiliza apenas 0 a 1 ocorrência de evento. Portanto, mesmo que você defina mais ocorrências como parte de um intervalo, as ocorrências adicionais só serão contabilizadas pela AppsFlyer. |
| <span id="import-from-partner-app-is-disabled"></span>A importação de aplicações parceiras está desativada | ![ImportFromPartnerApp.png](https://files.readme.io/c124696c4a8bca7c0d95d812f5390e9672adbfd6fc510a6fa573972f5441cd02-40032591386129.png)<br /><br />**Sintoma**<br /><br />Nos anúncios Meta, se a **importação de aplicações parceiras** estiver desativada, a aplicação nunca enviou um evento para os anúncios Meta através de um SDK MMP.<br /><br />**Ação corretiva**<br /><br />Siga uma das opções abaixo:<ul><li>Comece a enviar eventos para o Meta Ads com o SDK do MMP o mais rápido possível.</li><li>Inicie o envio de eventos para o Meta Ads com o SDK do Facebook ou a App Events API e use um dos outros métodos para configurar o esquema de conversão.</li></ul>Em seguida, após os primeiros eventos serem registrados no Meta Ads, configure a integração com a AppsFlyer.<br /><br />[Orientação atualizada a 25 de abril de 2021] |
| <span id="ranges-cant-overlap-and-must-be-in-consecutive-order"></span>Os intervalos não podem sobrepor-se e devem estar numa ordem consecutiva | **Sintoma**<br /><br />Utiliza o modo de medição personalizado SKAN da AppsFlyer. Ao importar o modelo de medição para os anúncios Meta, aparece a seguinte mensagem: *Os intervalos não podem sobrepor-se e devem estar numa ordem consecutiva.*<br /><br />**Ação corretiva**<br /><br />Os valores de receita no esquema de conversão personalizada devem estar em ordem crescente consecutiva.<br /><br />[Orientação atualizada a 26 de abril de 2021] |
| <span id="sending-events-to-facebook"></span>Envio de eventos para anúncios Meta | **Q**: Faz sentido enviar postbacks de eventos adicionais para eventos não selecionados na opção de medição de CV para anúncios Meta?<br /><br />**R**: Para utilizadores que deram consentimento, envie toda a gama de eventos para maximizar a capacidade de otimização dos anúncios Meta. |
| <span id="map-multiple-events-to-the-same-facebook-event"></span>Mapear vários eventos para um único evento de anúncios Meta | **Q**: Posso mapear vários eventos no aplicativo para um único evento do Meta Ads?<br /><br />**R**: Se mapear vários eventos para um único evento padrão de anúncios Meta, os anúncios Meta não poderão diferenciar entre os eventos. Assim, o Meta Ads otimizará para o único evento que ele reconhece. |
| <span id="no-data-to-pull"></span>Sem dados para extrair | P: **Por que motivo o status de conexão exibe "Sem dados para extrair": Verifique as suas permissões de partilha de dados Meta"?**<br /><br />**R**: Ainda não existem dados da SKAN disponíveis ou é necessário iniciar sessão no Meta Ads como administrador da conta.<br /><br />P: **Recebi a mensagem "Sem dados para extrair": Verifique as suas permissões de partilha de dados Meta". Apesar de visualizar os detalhes do Meta Ads, está tudo em ordem?**<br /><br />**R**: Sim. Embora esta mensagem de erro possa aparecer, está tudo bem e os seus dados serão extraídos. |
| <span id="facebook-data-is-not-in-the-dashboard"></span>Os dados dos anúncios Meta não estão no dashboard | **Sintoma**<br /><br />No separador de integração SKAN, é exibida a mensagem *falha ao extrair dados*.<br /><br />![FacebookSKAdIntegration.png](https://files.readme.io/42538a59d27815b95b71ec136ebc45b8d918eebf6a2235c90fef59c467128fb2-40032591388177.png)<br /><br />**Ação corretiva**<br /><br />Verifique se a conta conectada é de um administrador do Facebook ou de um anunciante do Meta Ads com permissão ads\_read. |
| <span id="there-is-an-error-in-facebook-when-you-try-to-run-ios-14-campaigns"></span>Há um erro nos anúncios Meta ao tentar executar campanhas para iOS 14 | **Sintoma**<br /><br />Todos os pontos seguintes são verdadeiros:<ul><li>Recebe uma mensagem de erro nos anúncios Meta ao tentar executar uma campanha para iOS 14</li><li>Adicionou recentemente uma nova aplicação ou uma aplicação direcionada a crianças na App Store.</li></ul>Isto acontece porque o Meta Ads não reconhece que está a utilizar um SDK que inclui suporte para SKAN. Ou seja, o SDK da AppsFlyer.<br /><br />**Ação corretiva**<ol><li>No AppsFlyer, acesse **Colaborar > Integrações de parceiros > Integrações ativas**.</li><li>Procure e selecione **Anúncios Meta**.</li><li>No separador **Integração**, desative **Ativar parceiro.**</li><li>Clique em **Guardar Integração.**</li><li>Aguarde 15 segundos.</li><li>Reative **Ativar parceiro.**</li><li>Clique em **Guardar Integração.**</li><li>Aguarde até 24 horas para que os anúncios Meta recebam o sinal.</li></ol> |
| <span id="revenue-reported-by-facebook"></span>Receita reportada pelos anúncios Meta | [Atualizado a 12 de julho de 2021]<br /><br />Os anúncios Meta derivam receita do CV utilizando as suas definições SKAN. No entanto, este cálculo não é direto, e o Meta Ads usa algoritmos para determinar a receita.<br /><br />Um sintoma disto é a receita ter valores não arredondados, mesmo que a receita seja medida em dólares inteiros. |
| <span id="retroactive-data-backfill"></span>Preenchimento retroativo de dados | [Atualizado a 23 de dezembro de 2021]<br /><br />Por vezes, não conseguimos conectar-nos aos anúncios Meta para obter os dados, por exemplo, devido a falhas de login. Não se preocupe. Preencheremos as lacunas nos relatórios dos últimos sete dias assim que conseguirmos iniciar sessão novamente. |
| <span id="appsflyer-is-showing-significantly-more-installseventsrevenue-than-facebook"></span>A AppsFlyer está a mostrar significativamente mais instalações/eventos/receitas do que os anúncios Meta. | Em muitos casos, esta discrepância ocorre porque o painel de anúncios Meta exibe apenas instalações ou eventos resultantes de cliques por predefinição, enquanto o painel da AppsFlyer exibe tanto instalações e eventos de cliques como de visualização. |
| <span id="agency-integration"></span>Integração com agências | Se a agência tiver um papel de administrador na conta do anunciante no Meta Ads, ela pode realizar o processo neste artigo para permitir a interoperabilidade da SKAN em nome do anunciante. Os anunciantes não precisam de iniciar sessão nas suas contas de anúncios Meta. O login da agência será indicado na conta do anunciante. |
| <span id="an-updated-cv-doesnt-appear-on-facebook"></span>Um valor de conversão atualizado não aparece no Meta Ads | Ao adicionar, alterar ou remover um valor de conversão (CV) no SKAN Conversion Studio, certifique-se de que o evento está mapeado nos **postbacks de eventos na aplicação**. Caso contrário, o CV não será atualizado nos anúncios Meta. |
| <span id="modeled-data-differences-in-appsflyer-and-facebook-ads-manager"></span>Diferenças dos dados modelados na AppsFlyer e no Meta Ads Manager | A AppsFlyer modela dados agregados que os relatórios básicos do SKAN não conseguem fornecer. <Anchor target="_blank" href="/marketers/pt/docs/skan-modeled-data">Saiba mais</Anchor><br /><br />Quando a AppsFlyer modela dados, os dados modelados por anúncios Meta não são considerados, uma vez que a AppsFlyer depende exclusivamente de dados confirmados e imparciais. Portanto, pode haver discrepâncias nos dados e na granularidade entre os relatórios do Meta ads Manager e os relatórios do AppsFlyer. |

</Accordion>

<div id="see-also" />

> 📄 **Veja também**
>
> * <Anchor target="_blank" href="/marketers/pt/docs/skadnetwork-skan-solution-guide">Guia da solução AppsFlyer SKANetwork</Anchor>

<div data-zendesk-anchors="skan-interoperability-appsflyer-facebook=interoperabilidade-do-skan-appsflyer---an%C3%BAncios-meta h_01H8XRMVR4JK6ZCGPQJE4D3T26=interoperabilidade-do-skan-appsflyer---an%C3%BAncios-meta scope-of-skan-interoperability-with-meta-ads=%C3%A2mbito-da-interoperabilidade-do-skan-com-an%C3%BAncios-meta h_01H8XRMVR4Q7HAJV0B7QB5MDPH=%C3%A2mbito-da-interoperabilidade-do-skan-com-an%C3%BAncios-meta considerations=considera%C3%A7%C3%B5es h_01H8XRMVR43KEGWARYMD45S0VY=considera%C3%A7%C3%B5es facebook-app-install-ads-guidance=diretrizes-para-an%C3%BAncios-de-instala%C3%A7%C3%A3o-de-apps-meta h_01H8XRMVR48NWM47043YWT63HK=diretrizes-para-an%C3%BAncios-de-instala%C3%A7%C3%A3o-de-apps-meta interoperation-procedures=procedimentos-de-interopera%C3%A7%C3%A3o h_01H8XRMVR4NVDZ23572F6KJTA9=procedimentos-de-interopera%C3%A7%C3%A3o h_01H8XRMVR4D07SWXS1TWK42DS3=allow-facebook-to-share-skadnetwork-data-with-appsflyer h_01H8XRMVR5HKXWYB3XN11V48Y0=share-cv-schema-with-facebook enabling-appsflyer-skadnetwork-interoperation-with-facebook=ativa%C3%A7%C3%A3o-da-interopera%C3%A7%C3%A3o-skan-da-appsflyer-com-an%C3%BAncios-meta h_01H8XRMVR56T3X9MJ6KVJF0Z8W=ativa%C3%A7%C3%A3o-da-interopera%C3%A7%C3%A3o-skan-da-appsflyer-com-an%C3%BAncios-meta h_01H8XRMVR5GY77K7GJ4TXGWEHS=nota inapp-event-mapping-guide=guia-de-mapeamento-de-eventos-in-app h_01H8XRMVR5T28Q0E8KP6BZ6CGH=guia-de-mapeamento-de-eventos-in-app additional-information=informa%C3%A7%C3%B5es-adicionais h_01H8XRMVR5WXZ88676PAW9BKC9=informa%C3%A7%C3%B5es-adicionais h_01H8XRMVR5AW2HZD6JFDYJRNFJ=turning-off-the-skan-integration h_01H8XRMVR5HZ2BBP4XXDEFYT34=measurement-and-timing-differences-between-appsflyer-and-facebook h_01H8XRMVR58DFA2SX20ZEKZRC3=verifying-the-ads_read-permission h_01H8XRMVR5Z9H83X0TAYS50CJ9=troubleshooting-discrepancies-and-faq h_01K7P24YAYSPB84PV0ZGBJ0QB0=quick-fix-checklist h_01K7P2811MRTVRC0D6YGVSXY4C=still-not-working h_01HE7SMBXBCEQM7KF2RG3V16KV=veja-tamb%C3%A9m" />
