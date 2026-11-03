---
title: Configuração da integração do Yahoo
metadata:
  keywords:
    - Advertisers
    - yahoo
    - gemini
    - Oath
    - verizon media
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2016-08-25T13:09:48Z'
  edited_at: '2026-09-10T00:26:10Z'
  id: 212067546
  locale: pt
  section: Ad network configuration guides (R-Z)
  section_id: 6552025468305
  url: https://support.appsflyer.com/hc/pt/articles/212067546
---
> **Em resumo:** o Yahoo, um parceiro integrado de ad network da AppsFlyer, oferece anúncios de pesquisa e anúncios nativos em uma única plataforma de publicidade. Além da atribuição mobile baseada em cliques, o Yahoo oferece custo e atribuição de view-through, que podem ser registrados na AppsFlyer.

## Configurando o Yahoo

**Pré-requisito:** antes de configurar a integração, certifique-se de [entrar em contato com o parceiro](#) e abrir uma conta com ele. Antes de criar uma integração, certifique-se de <Anchor target="_blank" href="/marketers/pt/docs/partner-integrations#contact-details">entrar em contato com o parceiro</Anchor> e abrir uma conta com ele.

**Para ativar a integração:**

1. Na aba **Integração**, habilite **Ativar parceiro**.  
   **Para editar**: **Na AppsFlyer, vá para o menu lateral e selecione** Colaborar **>** **Integrações ativas**.
2. Selecione o aplicativo correspondente.
3. Na aba **Integração**, selecione o aplicativo e clique em **Ativar parceiro**.
4. Na **primeira visita** aqui, você precisará ativar a opção ***Ativar parceiro*** para habilitar a configuração dos parâmetros de integração. A opção **deve** permanecer ativada enquanto você trabalhar com o parceiro.  
      
   Para obter mais detalhes sobre a ativação do parceiro, clique <Anchor target="_blank" href="/marketers/pt/docs/partner-activation-deactivation">aqui</Anchor>.
5. Complete a configuração utilizando as abas relevantes, conforme descrito abaixo. Para obter uma descrição detalhada do header da Janela de Configuração de Parceiros, clique <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#about-the-integrated-partner-page">aqui</Anchor>.

> 👍 **Dica**
>
> A etapa <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#d-general-settings">Configurações gerais</Anchor> na aba integração é **obrigatória**. Todas as outras etapas são descritivas ou **opcionais**.

<div id="integration-tab" />

<Accordion title="Aba Integração">

### Configuração do anunciante

A aba Integração está dividida em diferentes seções, conforme descrito abaixo.

### Ativar parceiro

Na **primeira visita** aqui, você precisará ativar o toggle ***Ativar parceiro*** para habilitar a configuração dos parâmetros da aba de integração. O botão DEVE estar ATIVADO enquanto você trabalhar com o parceiro.

Para obter mais detalhes sobre a ativação do parceiro, clique <Anchor target="_blank" href="/marketers/pt/docs/partner-activation-deactivation">aqui</Anchor>.

### Configurações gerais

Siga estas etapas para as configurações gerais do Yahoo.

### Atribuição de click-through

Essa barra deslizante permite que você defina o **tempo máximo do clique até a instalação**. Somente as instalações (primeiras aberturas) que acontecerem dentro da janela de lookback podem ser atribuídas ao Yahoo.

Você pode personalizar esse valor para 1 a 23 horas ou 1 a 30 dias. Recomendamos definir a janela de lookback de click-through como 7 dias, para alinhar com o Yahoo.

Mais detalhes sobre a <Anchor target="_blank" href="/marketers/pt/docs/set-up-lookback-windows">janela de lookback de clique aqui</Anchor>.

**Habilitar a atribuição de view-through**

Ative essa opção se quiser atribuir instalações por view-through do Yahoo. O cursor de lookback de view-through está disponível na aba do link de atribuição (conforme descrito abaixo).

Você pode personalizar esse valor para 1 a 23 horas ou 1 a 7 dias. Recomendamos definir a janela de lookback de view-through para 1 dia, para alinhar com o Yahoo.

### Configuração da agência

Antes de começar o trabalho com o Yahoo, o anunciante deve ativar a integração do lado dele; caso contrário, as conversões não poderão ser atribuídas a você.

Para sua conta do Yahoo, insira o ID da sua conta do Yahoo. Para o Yahoo DSP, insira o ID do anunciante.

**Nota:**

* Caso o anunciante e a agência promovam o aplicativo no Yahoo, eles precisarão trabalhar com contas separadas do Yahoo.
* A agência pode usar apenas uma conta no Yahoo.

Para encontrar o ID da sua conta, faça login no dashboard do Yahoo, clique no ícone de engrenagem para abrir o menu ***Settings*** e selecione ***Billing***:

![gemini-account-number.png](https://files.readme.io/77f464c6dadefc54acb3a84d97ab0d0751610b253d2da90523bc117f1f26683c-50705625726865.png)

As janelas de lookback de click-through e view-through estão no modo somente leitura e devem ser configuradas pelo anunciante.

### Configurações de eventos in-app

Nesta seção, você pode mapear seus eventos da AppsFlyer com o Yahoo por meio de postbacks.

1. Insira o ID da Dot tag fornecido pelo Yahoo.  
   Para encontrá-lo no dashboard do Yahoo, clique no ícone de engrenagem para abrir o menu **Configurações** e selecione **Ver código da Dot tag**. Copie o código do dashboard:

   [![yahoo-dot-tag.png](https://files.readme.io/6ceaea7447d1c3a81451dac3aa7c3c3063a5cf2c0051b4dfad6cf7aeba40ab24-small-50705593680401.png)](https://files.readme.io/6ceaea7447d1c3a81451dac3aa7c3c3063a5cf2c0051b4dfad6cf7aeba40ab24-small-50705593680401.png)
2. Ative postbacks de eventos in-app
3. Selecione a opção de envio para todos os eventos definidos pelo SDK.  
   **- Somente eventos atribuídos a esse parceiro** **apenas** para eventos de usuários atribuídos a esse parceiro.  
    **- Eventos atribuídos a qualquer parceiro ou eventos orgânicos** para que toda a base de usuários esteja disponível para ser relatada ao parceiro.
4. Clique em **Add Event** (Adicionar Evento) para adicionar um evento do SDK à lista
5. Complete os seguintes parâmetros:

| Nome do parâmetro | A descrição |
| --- | --- |
| **SDK Event Name (Nome do evento do SDK)** | O nome do evento, conforme recebido pela AppsFlyer, seja do SDK integrado no seu aplicativo ou de eventos de servidor para servidor.  <br />**Dica** - não está encontrando o evento desejado na lista? Certifique-se de ativar o evento em um dispositivo com uma instalação não orgânica e verifique novamente. |
| **Partner Event Identifier (identificador de evento do parceiro)** | O nome exclusivo ou o ID de cada evento, conforme definido no lado do Yahoo.  <br />Obtenha o ID do evento correspondente do Yahoo e defina-o no campo de texto. |
| **Send Revenue (Enviar receita)** | **Quando desmarcado** - todos os parâmetros de evento in-app avançado são enviados para o parceiro, exceto o parâmetro de receita, que está contido no parâmetro **af\_revenue**.  <br />**Quando marcado** - todos os parâmetros, incluindo o valor da receita (caso exista no evento), são enviados. |

**Nota:**

Para agências, a ***opção de envio*** e a lista de eventos disponíveis para mapeamento dependem das permissões concedidas à agência pelo anunciante.

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Separador de Links de Atribuição">

Esta guia não se aplica ao Yahoo.

> 📘 **Nota**
>
> Para todas as SRNs, como Meta ads, Apple Search Ads, Adwords, Snapchat etc., esta guia não é funcional, pois elas não usam links de atribuição externa.

</Accordion>

<div id="cost-tab" />

<Accordion title="Aba de Custos">

### Ativando e testando a integração de custo do Yahoo

A integração de custos fornece os seguintes dados agregados:

* Dados de custo para suas campanhas, conjuntos de anúncios, anúncios e geos/países. Consulte a <Anchor target="_blank" href="/marketers/pt/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api">tabela de integração de custos da ad network</Anchor> para obter detalhes completos sobre as dimensões, métricas e recursos compatíveis.  
  **Atenção:** os dados de custo requerem uma assinatura <Anchor target="_blank" href="/marketers/pt/docs/roi360-cost-aggregation-overview?query=xpend">ROI360</Anchor>.
* Dados sobre cliques, impressões e dados enriquecidos (palavras-chave, nomes de campanha e nomes de conjunto de anúncios).

**Para ativar a Cost API**:

* Siga <Anchor target="_blank" href="/marketers/pt/docs/set-up-roi360-cost-api-to-measure-cost-data#enable-cost-api">estas instruções de integração</Anchor>.

<Anchor target="_blank" href="/marketers/pt/docs/set-up-roi360-cost-api-to-measure-cost-data#cost-api-status">Veja o status da API de custo</Anchor> e a última vez que a AppsFlyer conseguiu extrair os dados de custo correspondentes no dashboard de status da integração de custo (e receita de anúncios) ou no dashboard individual da ad network.

> ❗️ **Aviso**
>
> Depois de definir o custo do Yahoo, não altere o nome de nenhuma campanha em execução, conjunto de anúncios ou anúncio individual, pois isso pode causar discrepâncias graves ou dados de custo ausentes.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Receita de anúncios">

A receita de anúncios não é compatível com esse parceiro.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Aba permissões">

Nesta aba, você pode selecionar as permissões para conceder ao Yahoo. Observe que, mesmo que a atribuição esteja desativada para o Yahoo, a aba de permissões está ativa e você pode conceder controle ao Yahoo.

Use essas chaves seletoras para conceder permissões à rede de anúncios para gerenciar sua própria configuração do aplicativo:

* ***Permitir a configuração da integração*** – permite que o parceiro configure a aba de integração (exceto postbacks de evento in-app)
* *Permitir a configuração de postbacks de evento in-app* – permite que o parceiro configure o mapeamento de postbacks de evento in-app para si mesmo na guia de integração
* ***Permitir o acesso ao relatório de retenção*** – somente aos próprios dados de retenção do parceiro
* ***Permitir acesso aos dados agregados de usuário fiéis*** — apenas aos dados de usuários fieis do parceiro
* ***Permitir acesso aos dados agregados de eventos in-app** —* apenas aos dados de eventos in-app próprios do parceiro
* ***Permitir acesso aos seus dados agregados de receita*** - apenas aos dados de receita atribuídos ao parceiro
* ***Permitir o acesso ao painel Protect360*** – somente aos próprios dados do Protect360 do parceiro e desde que o recurso esteja ativado para o anunciante

Saiba mais sobre a concessão de <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#permissions-tab">permissões de ad networks</Anchor>.

</Accordion>

## Marcação de eventos como conversões no Yahoo

Você pode marcar como conversões os eventos que a AppsFlyer envia ao Yahoo por meio de postbacks de eventos in-app:

![yahoo-conversion-rules.png](https://files.readme.io/17a3fdd1619d4e4d0bfcca35e4fd51e7f270ce7446f9e70fb6f7787291e2e022-50705625729297.png)

## Relatório bruto do Yahoo

A AppsFlyer recebe os seguintes parâmetros do Yahoo e os mapeia para os seguintes campos nos relatórios brutos.

| Parâmetros do Yahoo | Parâmetros do relatório bruto da AppsFlyer |
| --- | --- |
| ID criativa | ID do anúncio |
| Nome do criativo | As ad |
| ID do grupo de anúncios | Adset ID |
| Nome do grupo de anúncios | Conjunto de anúncios |
| ID da campanha | ID da campanha |
| Nome da campanha | Campaign |
| ID do site | ID do site |

## Limitações

* Quando você ativa a atribuição pela primeira vez, pode levar até 4 horas para que isso seja refletido na interface do usuário do Yahoo.

## Compatibilidade SKAdNetwork

A interoperabilidade do SKAdNetwork com o Yahoo está disponível.

<div data-zendesk-anchors="setting-up-yahoo=configurando-o-yahoo h_01HJR1D3NZJPKDK3DJ7DT3VZ44=configurando-o-yahoo h_01HJR1D3P0RS08SJZJYF2487MM=dica h_01HJR1D3P0TMSSJBKDG130RV2E=integration-tab advertiser-configuration=configura%C3%A7%C3%A3o-do-anunciante h_01HJR1D3P05WQGP8SFZ5H5AD6A=configura%C3%A7%C3%A3o-do-anunciante activate-partner=ativar-parceiro h_01HJR1D3P0WC1W6H8MKHKR9MX9=ativar-parceiro general-settings=configura%C3%A7%C3%B5es-gerais h_01HJR1D3P0C5TNMHRGWG8JR2TQ=configura%C3%A7%C3%B5es-gerais clickthrough-attribution=atribui%C3%A7%C3%A3o-de-click-through h_01HJR1D3P0V155S0QFVP2RDPP8=atribui%C3%A7%C3%A3o-de-click-through agency-configuration=configura%C3%A7%C3%A3o-da-ag%C3%AAncia h_01HJR1D3P02HSHKFR45HRQWGCE=configura%C3%A7%C3%A3o-da-ag%C3%AAncia inapp-events-settings=configura%C3%A7%C3%B5es-de-eventos-in-app h_01HJR1D3P0PAT8B60P5313GMQQ=configura%C3%A7%C3%B5es-de-eventos-in-app h_01HJR1D3P0G9P4FQ5QZWXD9PW8=attribution-link-tab h_01HJR1D3P03WM14AYT4TKXVX0X=nota h_01HJR1D3P0YHSB6QDQJ77WFR45=cost-tab enabling-and-testing-yahoo-cost-integration=ativando-e-testando-a-integra%C3%A7%C3%A3o-de-custo-do-yahoo h_01HJR1D3P10YRNVR68AAJNMY6K=ativando-e-testando-a-integra%C3%A7%C3%A3o-de-custo-do-yahoo h_01HJR1D3P10EF6X40X3YPKRTF0=aviso h_01HJR1D3P18KB4AXKN31ZKCHRC=ad-revenue-tab h_01HJR1D3P10GR6AZ7MNS0Q7NWZ=permissions-tab marking-events-as-conversions-in-yahoo=marca%C3%A7%C3%A3o-de-eventos-como-convers%C3%B5es-no-yahoo h_01HJR1D3P1D817ABQ7D92KJ1QK=marca%C3%A7%C3%A3o-de-eventos-como-convers%C3%B5es-no-yahoo yahoo-raw-report=relat%C3%B3rio-bruto-do-yahoo h_01HJR1D3P19SM0JFZ7Q2XND911=relat%C3%B3rio-bruto-do-yahoo limitations=limita%C3%A7%C3%B5es h_01HJR1D3P1YAJJMCC6TX2NSCTG=limita%C3%A7%C3%B5es skadnetwork-support=compatibilidade-skadnetwork h_01HJR1D3P1HBBBCVMRGZ96DC1E=compatibilidade-skadnetwork" />
