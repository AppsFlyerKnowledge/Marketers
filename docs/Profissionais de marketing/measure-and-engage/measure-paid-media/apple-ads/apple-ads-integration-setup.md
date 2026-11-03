---
title: Configuração da integração do Apple Ads (Search Ads)
metadata:
  keywords:
    - cost
    - Advertisers
    - apple search ads
    - asa
    - apple ads
    - apple search advanced
    - apple search ads campaign group
    - apple keywords
    - apple searchads
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
  created_at: '2016-08-31T09:04:38Z'
  edited_at: '2026-10-29T01:21:01Z'
  id: 213747963
  locale: pt
  section: Apple Ads
  section_id: 6551310453393
  url: https://support.appsflyer.com/hc/pt/articles/213747963
---
> **At a glance:** O Apple Ads, um parceiro de Self-Reporting Network (SRN) da AppsFlyer, ajuda os usuários a encontrar seu aplicativo na loja de aplicativos usando palavras-chave.

<Image alt="medium_originaljpeg_apple_ads_logo_blk_highres_720 (1) (1).jpg" src="https://files.readme.io/f89d1a5ec1a1de2ec2dfdec7465465fc2be73e0cf41ddd6be8b2e3f62de3c9e8-47598828154001.jpg" width="719px" />

A relevância do seu aplicativo na busca na app store determina se o seu anúncio será o anúncio mostrado. A resposta do usuário a um anúncio é um sinal de relevância do anúncio. O Apple Ads usa as respostas dos usuários como um sinal para decidir quais anúncios exibir com mais frequência.

> 📘 **Note**
>
> * A AppsFlyer oferece suporte à atribuição mobile baseada em cliques do Apple Ads, retargeting de usuários e dados de custo via API (com uma assinatura ROI360).
> * A partir de 27 de março de 2025, a AppsFlyer também oferece suporte à atribuição mobile baseada em impressões do Apple Search Ads.
> * A partir de 1º de setembro de 2026, o Apple Ads adicionará um timestamp exato a todas as reivindicações de atribuição do iOS.

## Configure a integração com o Apple Ads

<Accordion title="Iniciar">

**Pré-requisito**

* A versão mais recente do iOS SDK da AppsFlyer

**Configurando o Apple Search Ads na AppsFlyer:**

A configuração é feita na página **Integrações ativas**, mas para encontrar novos parceiros você deve primeiro ir ao <Anchor target="_blank" href="/marketers/pt/docs/partner-integrations">Marketplace de parceiros</Anchor>. Complete a configuração utilizando as abas relevantes, conforme descrito abaixo.

> 📘 **Note**
>
> Antes de configurar uma integração, certifique-se de entrar em contato com o parceiro e abrir uma conta com ele.

</Accordion>

<Accordion title="Aba Integração">

O Apple Search Ads, uma SRN, se integra à AppsFlyer por meio da API. Assim, não há configurações de postback. Conclua as próximas etapas de acordo com seus objetivos de atribuição.

<table><thead><tr><th>Secção </th><th>Atenção</th></tr></thead><tbody><tr><td>Ativação da integração</td><td><p><strong>Para ativar a integração:</strong></p><ol><li> <strong>Para ativar:</strong> na AppsFlyer, no menu lateral, selecione <strong>Colaborar</strong> &gt; <strong>Partner Marketplace</strong>.</li><li>Selecione o aplicativo correspondente. </li><li>Na aba <strong>Integração</strong>, selecione o aplicativo e clique em <strong>Ativar parceiro</strong>.</li><li>Na <strong>primeira visita</strong> aqui, você precisará ativar a opção <em><strong>Ativar parceiro</strong></em> para habilitar a configuração dos parâmetros de integração. <strong>Observação:</strong> Essa opção deve permanecer habilitada <a href="./partner-activation-deactivation" target="_blank">(ativada)</a> enquanto você trabalhar com o parceiro.</li><li>Complete a configuração utilizando as abas relevantes, conforme descrito abaixo.</li></ol><p><strong>Para ativar ou editar a integração:</strong></p><p><strong>Para editar</strong>: na AppsFlyer, no menu lateral, selecione <strong>Colaborar</strong> &gt; <strong>Integrações Ativas</strong>.</p></td></tr><tr><td>Atribuição de instalação por click-through</td><td><ol><li><p>Defina o tempo máximo entre um clique e uma instalação. Isso permite que a AppsFlyer atribua instalações (primeiras aberturas) que ocorram dentro da janela de lookback ao Apple Ads.</p><ul><li> <strong>Intervalo:</strong> 1–30 dias</li><li> <strong>Padrão:</strong> 30 dias</li></ul><p>Intervalo: 1–30 dias<br/><br/>Para mais informações sobre janelas de lookback, veja nossa <a href="./set-up-lookback-windows" target="_blank">explicação sobre janelas de lookback</a>.</p></li></ol><ol><li> <strong>Mensuração de campanhas de pré-registro (pré-venda)</strong><br/>Se você executar campanhas de pré-registro para aplicativos iOS, defina a janela de lookback da campanha de pré-registro. <br/>Esse cursor determina a janela de lookback usada para atribuir instalações a campanhas de pré-registro.<br/>A janela de lookback de pré-registro permite a atribuição de instalações que acontecem quando aplicativos pré-registrados (em pré-venda) são lançados, vinculando-as ao engajamento original com o anúncio. <ul><li> <strong>Intervalo:</strong> 1–90 dias</li><li> <strong>Padrão:</strong>  90 dias</li></ul></li></ol></td></tr><tr><td>Atribuição de instalação de view-through</td><td><ol><li><p><span><strong>Defina a janela de lookback view-through da instalação</strong></span><br/>Defina o tempo máximo entre a visualização do anúncio e a instalação. A AppsFlyer atribui instalações (primeiras aberturas) que ocorrem dentro desta janela ao Apple Ads. Defina o tempo máximo entre uma visualização e uma instalação. O slider da janela de lookback de view-through permite somente horas (máx: 24h, padrão: 24h) </p><ul><li> <strong>Intervalo:</strong> 1–24 horas</li><li> <strong>Padrão:</strong>  24 horas</li></ul><p>Intervalo: 1–30 dias<br/><br/>Para mais informações sobre janelas de lookback, veja nossa <a href="./set-up-lookback-windows" target="_blank">explicação sobre janelas de lookback</a>.</p></li><li> <strong>Mensuração de campanha de pré-registro (pré-venda)</strong><br/>Se você executar campanhas de pré-registro para aplicativos iOS, defina a janela de lookback da campanha de pré-registro.<br/>Esse cursor determina a janela de lookback usada para atribuir instalações a campanhas de pré-registro.<br/>A janela de lookback de pré-registro permite a atribuição de instalações que acontecem quando aplicativos pré-registrados (em pré-venda) são lançados, vinculando-as ao engajamento original com o anúncio.<ul><li> <strong>Intervalo:</strong> 1–61 dias</li><li> <strong>Padrão:</strong> 61 dias</li></ul></li></ol></td></tr><tr><td rowspan="2">Reinstalações </td><td><p><strong>Atribuição de reinstalação</strong></p><p>Se a <strong>atribuição de reinstalação estiver</strong> ativada, a AppsFlyer poderá atribuir reinstalações ao Apple Ads.</p><p>As configurações da janela de lookback de atribuição de reinstalação são definidas de acordo com as configurações de atribuição de instalações.</p><p>Se o usuário estiver dentro da <a href="./set-up-re-attribution-window" target="_blank">janela de reatribuição</a> (definida no momento da instalação original), a instalação será atribuída ao Apple Ads como uma reinstalação.</p><p>A reinstalação pode ser vista na visualização de retargeting do dashboard de Visão Geral.</p><p>O campo de dados brutos de <strong>reinstalação</strong> da storeé definido como verdadeiro (true). </p><p>Atualmente, o retargeting do Apple Ads não é compatível com reengajamentos.</p></td></tr><tr><td><p><strong>Janela de inatividade</strong></p><p>Defina o <a href="./set-retargeting-inactivity-window" target="_blank">limite de inatividade</a> do usuário (em dias) para controlar o impacto das campanhas de retargeting. </p></td></tr><tr><td>Postbacks</td><td>No momento, a integração do Apple Ads não é compatível com postbacks.  </td></tr></tbody></table>

</Accordion>

<Accordion title="Aba de custo">

A integração de custos fornece os seguintes dados agregados:

* Dados de custo para suas campanhas, conjuntos de anúncios, geos/países e palavras-chave. Consulte a <Anchor target="_blank" href="/marketers/pt/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api">tabela de integração de custos da ad network</Anchor> para obter detalhes completos sobre as dimensões, métricas e recursos compatíveis.Atenção: **os dados de custo requerem uma assinatura do ROI360.**
* Dados sobre cliques, impressões e dados enriquecidos — palavras-chave, nomes de campanha e conjuntos de anúncios.

> 📘 **Note**
>
> * Há suporte para o uso de várias contas do Apple Ads. Em outras palavras, se você executa campanhas para o mesmo aplicativo usando diferentes contas do Apple Ads, a AppsFlyer pode receber esses dados de todas as contas.
> * Vários usuários na mesma conta do Apple Ads podem conectar, cada um, sua própria integração de custos do Apple Ads. A AppsFlyer mantém cada integração de custos separada. Quando outro usuário da sua conta Apple cria uma nova integração de custos com a Apple, sua conexão permanece como está e não é substituída. Cada integração de custos extrai dados de custo com base nas permissões do usuário com sessão iniciada no Apple Ads.
> * Os dados de custo para "grupos de campanha" não são suportados pela API de relatórios do Apple Ads; portanto, os dados de "grupo de campanha" não estão disponíveis na AppsFlyer.
> * Para iniciar sessão com a Apple, você precisa das permissões **Campaign Group Manage** do Apple Ads (Account Read Only ou Account Read and Write).
> * Quando você inicia sessão com a Apple, a autorização de grupos de campanha do Apple Ads não é cumulativa. Isso significa que, quando você integra um novo aplicativo, a autorização para os grupos de campanha selecionados em aplicativos anteriores é revogada, a menos que eles sejam selecionados novamente.
> * Quando você faz o login na Apple, você não pode usar um login federado.

**Para habilitar dados de custo, cliques, impressões e dados enriquecidos:**

* Siga <Anchor target="_blank" href="/marketers/pt/docs/set-up-roi360-cost-api-to-measure-cost-data#enable-cost-api">essas instruções de integração</Anchor>

<Anchor target="_blank" href="/marketers/pt/docs/set-up-roi360-cost-api-to-measure-cost-data#cost-api-status">Veja o status da sua API de custo</Anchor> e a última vez que a AppsFlyer conseguiu extrair dados de custo correspondentes no dashboard de status da integração de custo (e receita de anúncios) ou no dashboard individual da ad network.

</Accordion>

<Accordion title="Aba permissões">

<Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#permissions-tab">Definindo permissões de ad network e agência.</Anchor>

</Accordion>

## Configurar agências e parceiros de marketing do Apple Ads

<Accordion title="Princípios">

**Apple Search Ads: Parceiro de marketing vs. agência**

Anunciantes e agências podem optar por trabalhar com Parceiros de marketing do Apple Ads para gerar relatórios e otimizar campanhas no Apple Ads.

As diferenças entre agências e parceiros de marketing estão descritas na tabela abaixo.

#### Agência vs. parceiro de marketing

|  | Agência | Parceiro de marketing |
| --- | --- | --- |
| A AppsFlyer envia postbacks | Não | Sim |
| Tecnologia | Executa campanhas em seu nome | Ter uma solução de tecnologia de valor agregado para otimizar campanhas |

#### Configurando agências e parceiros de marketing

Use a lista de verificação abaixo para garantir que você conclua todas as etapas do processo de configuração. As instruções detalhadas para cada tipo de parceiro são fornecidas nas seções a seguir.

#### Checklist das etapas de configuração

| Configurado por | Integração com uma agência | Integração com um parceiro de marketing |
| --- | --- | --- |
| AppsFlyer | <ol><li>Na AppsFlyer, na aba de integração do Apple Ads, ative **Ativar parceiro.**</li><li>Selecione a agência; na aba Permissões da agência, ative **Permissão da agência.**</li></ol> | <ol><li>Na aba de integração do Apple Ads, ative **Ativar parceiro.**</li><li>No dashboard do Apple Ads, obtenha o **Campaign Group ID.** do parceiro de marketing.</li><li>Na aba de integração do parceiro de marketing:<ol><li>Habilite **Ativar parceiro.**</li><li>Configure o grupo da campanha.</li><li>Configure o postback de eventos in-app.</li></ol></li></ol> |
| Agência | Na aba de integração do Apple Ads, configure **Grupo de campanha do Apple Ads.** | <ol><li>Na aba de integração do Apple Ads, ative **Ativar parceiro.**</li><li>No dashboard do Apple Ads, obtenha o **Campaign Group ID.** do parceiro de marketing.</li><li>Na aba de integração do parceiro de marketing:<ol><li>Habilite **Ativar parceiro.**</li><li>Configure o grupo da campanha.</li><li>Configure o postback de eventos in-app.</li></ol></li></ol> |

</Accordion>

<Accordion title="Configuração de parceiro de marketing">

**Para configurar um parceiro de marketing:**

1. Se necessário, ative **a integração do Apple Search Ads:**
   1. No AppsFlyer, vá para **Configuração**> **Parceiros de integração ativos** > **Apple Ads**.
   2. Habilite **Ativar parceiro.**
   3. Clique em **Salvar.**
2. **No seu dashboard do Apple Ads,** obtenha o parâmetro Apple Ads Campaign Group ID relacionado ao parceiro de marketing. Use a captura de tela a seguir como um guia para localizar o ID.

   ![ASACGroupID.png](https://files.readme.io/722ab215c9a096628b42caefc6838dfe790d726524839c588d9e01c061620711-21589950935057.png)
3. **No AppsFlyer, configure o parceiro de marketing do Apple Ads:**
   1. Na AppsFlyer, no menu lateral, selecione **Colaboração** > **Integrações ativas**.
   2. Pesquise o ***parceiro de marketing do Apple Search Ads.*  
      A lista de parceiros de marketing é exibida.**
   3. Selecione um parceiro de marketing.
   4. Habilite **Ativar parceiro.**
   5. Insira a **Campaign Group ID** do parceiro, que você obteve na etapa anterior. Insira apenas os dígitos (números).
   6. Clique em **Salvar**.
4. [Opcional] Configurar postbacks de eventos in-app:
   1. Ative **Postback de eventos in-app.**
   2. Clique em **adicionar evento** para adicionar um evento de SDK à lista.
   3. Preencha os seguintes parâmetros:
      1. **Nome do evento do SDK**: O nome do evento, conforme recebido pela AppsFlyer, seja do SDK integrado ao seu aplicativo ou de eventos server-to-server. **Dica:** não está encontrando o evento desejado na lista? Certifique-se de ativar o evento em um dispositivo com uma instalação não orgânica e verifique novamente.
      2. **Send Revenue (Enviar receita)** Escolha uma das seguintes opções: Sem valores e sem receita, Com valores e sem receita, ou Com valores e com receita.
5. Clique em **Salvar integração**.

</Accordion>

<Accordion title="Configuração da agência">

Os anunciantes permitem que as agências executem campanhas em seu nome usando o Apple Search Ads. Tanto anunciantes como agências executam ações de configuração na AppsFlyer, conforme descrito nesta seção.

**Pré-requisitos**

Antes de configurar uma agência na AppsFlyer, tanto a agência quanto o anunciante devem seguir as etapas a seguir na plataforma do Apple Ads:

* **Agência:**
  1. Crie grupos de campanhas separados na conta da agência.
  2. Convide o anunciante como gerente de grupo de campanha ou através da função de Vincular contar para conectar sua conta da App Store Connect.
* Anunciante: **Após receber o convite para vincular contas, o anunciante deve vincular os grupos de campanha à sua conta do App Store Connect.**

Consulte a documentação do Apple Ads sobre <Anchor target="_blank" href="https://searchads.apple.com/help/get-started/0012-link-app-store-connect-accounts">Como vincular a conta do App Store Connect de um cliente a uma conta de agência.</Anchor>

**Grupo de campanha do Apple Search Ads**

* Campanhas de agências e campanhas de anunciantes devem compor grupos separados de campanhas do ID do Apple Search Ads.
* Não use caracteres especiais ou espaços no nome do grupo.
* Quando você faz login com a Apple, a autorização dos grupos de campanha do Apple Ads não é cumulativa. Isso significa que quando você integra um novo aplicativo, a autorização para grupos de campanhas escolhidos para os aplicativos anteriores será revogada, a menos que seja ativado novamente. Você precisará selecionar **Acesso limitado** e cada um dos grupos de campanha relevantes (relacionados aos aplicativos que deseja conectar para o anunciante).

#### **Ações do anunciante**

**Pré-requisito**:

<Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#permissões-da-agência">Conceder permissão a uma agência</Anchor>.

**Para ativar a atribuição do Apple Ads, o anunciante:**

1. Na AppsFlyer, no menu lateral, selecione **Colaboração** > **Integrações ativas**.
2. Selecione **Apple Search Ads.**
3. Acesse a aba **Integração** e habilite a opção **Ativar parceiro**.
4. [Opcional] Se você quiser atribuir usuários que reinstalam o aplicativo durante a janela de reatribuição, ative a **Atribuição de reinstalação.**
5. Clique em **Salvar.**

#### **Ações da agência**

1. **No seu dashboard do Apple Ads,** obtenha o seu Campaign Group ID. Use a captura de tela a seguir como um guia para localizar o ID. Copie apenas os números.

   ![ASACGroupID.png](https://files.readme.io/722ab215c9a096628b42caefc6838dfe790d726524839c588d9e01c061620711-21589950935057.png)
2. Na AppsFlyer, selecione um aplicativo.
3. No menu lateral, selecione **Colaborar** > **Integrações ativas**.
4. Selecione **Apple Search Ads.**
5. Insira o parâmetro **Apple Search Ads Campaign ID**. Atenção! Insira somente dígitos (números)
6. Clique em **Salvar**.

> 📘 **Note**
>
> Quando uma agência trabalha com um parceiro de marketing do Apple Ads, ela deve configurar o mesmo Campaign Group ID tanto na página de configuração do Apple Ads quanto na página de configuração do parceiro de marketing.

### Dados de custo, cliques e impressões

Se você ativar a API de custo, a AppsFlyer receberá dados de custo, cliques e impressões do Apple Ads por meio da API. Consulte a <Anchor target="_blank" href="/marketers/pt/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api">tabela de integração de custos da ad network</Anchor> para obter detalhes completos sobre as dimensões, métricas e recursos compatíveis. **Atenção:** os dados de custo requerem uma assinatura ROI360. Sem o ROI360, apenas os dados de cliques e impressões são recebidos.

**Para ativar a Cost API**:

* Siga <Anchor target="_blank" href="/marketers/pt/docs/set-up-roi360-cost-api-to-measure-cost-data#enable-cost-api">essas instruções de integração</Anchor>. Certifique-se de que, quando for solicitado a fazer login na sua conta do Apple Ads em **Selecionar permissões**, você selecione uma das seguintes opções:
  * **Account Read and Write**
  * **Account Read Only**  
     **Atenção:** Se você escolher Acesso Limitado em um grupo de campanha específico, você pode encontrar alguns erros de dados.

<Anchor target="_blank" href="/marketers/pt/docs/set-up-roi360-cost-api-to-measure-cost-data#cost-api-status">Ver o status da API de custo</Anchor> e a última vez que a AppsFlyer conseguiu extrair dados de custo correspondentes no dashboard de status da integração de custo (e receita de anúncios) ou no dashboard individual da ad network.

> 📘 **Note**
>
> Os dados de custo do Apple Ads não estão disponíveis no dashboard do SKAdNetwork (SKAN) nem na Pull API do SKAN, porque os postbacks do SKAN não incluem dados no nível da campanha. No entanto, os dados de custo estão disponíveis nos relatórios SSOT, que combinam dados de instalação da SKAN com informações de custo obtidas por meio da nossa integração clássica com o Apple Search Ads.

</Accordion>

<Accordion title="Desativar agências e parceiros de marketing">

**Para interromper o registro da atribuição de instalações do Apple Search Ads geradas por agências ou parceiros de marketing:**

1. Na AppsFlyer, no menu lateral, selecione **Colaboração** > **Integrações ativas**.
2. Selecione a agência ou parceiro de marketing conforme o caso.
3. Exclua o conteúdo do **campo Apple Search Ads Campaign Group ID.**
4. Selecione **Apple Search Ads.** Etapa 1:

</Accordion>

## Informações adicionais

<Accordion title="Atribuição do Apple Ads">

O Apple Ads funciona de forma independente da SKAdNetwork e atribui os usuários de forma determinística, independentemente do consentimento do ATT (App Tracking Transparency). Isso significa que, para usuários atribuídos ao Apple Ads, você tem toda a gama de recursos e mensurações fornecida pelo nosso <Anchor target="_blank" href="/marketers/pt/docs/appsflyer-attribution-model">modelo de atribuição de LTV.</Anchor>

A atribuição do Apple Ads não depende do IDFA; a atribuição é feita usando um token do dispositivo (atribuição determinística).

#### Depois de 1 de setembro de 2026

O horário do clique e da impressão está disponível independentemente do status do ATT. A janela de lookback é definida pelo anunciante, e a AppsFlyer aplica as regras de atribuição de último toque ao engajamento.

#### Antes de 1 de setembro de 2026

A disponibilidade do horário do clique e da impressão, bem como a janela de lookback, varia de acordo com o consentimento do ATT:

| **Consentimento à ATT** | **Hora do clique/impressão disponível** | **Janela de lookback de clique/impressão** | **Observações** |
| --- | --- | --- | --- |
| Yes | Sim | Definido pelo anunciante | Regras de atribuição de último toque da AppsFlyer usadas |
| Sem | Não | Cliques: 30 dias (definido pelo Apple Ads), impressões: 24 h | Nenhum tempo de clique ou impressão é fornecido. Prioridade é dada a candidatos determinísticos |

</Accordion>

<Accordion title="Discrepâncias">

A AppsFlyer e o Apple Ads usam lógicas de atribuição diferentes, o que resulta em discrepâncias entre as plataformas. O <Anchor target="_blank" href="/marketers/pt/docs/self-reporting-networks-srns#atribuição">Apple Search Ads</Anchor>, como SRN, reporta novas instalações por API.

**Apple Ads reportando para a AppsFlyer via API**

* As campanhas são agregadas por Geo.
* Os dados abaixo não são relatados: Impressões, toques ou custo de Geos com menos de 100 impressões para uma determinada campanha.
* Ao agrupar por Geo na AppsFlyer, as geolocalizações com dados indisponíveis não são mostradas e o total de dados indisponíveis aparece em N/D.

### Discrepâncias relacionadas ao retargeting

O mecanismo de atribuição de retargeting da AppsFlyer permite que os anunciantes mensurem e analisem suas campanhas de retargeting, além de suas campanhas de aquisição de usuários.

As figuras a seguir mostram como podem ocorrer discrepâncias em relação às campanhas de retargeting (independentemente da configuração dos controles de retargeting) em execução no Apple Ads.

**Retargeting ativado**

 ![ASA R Enabled2.jpg](https://files.readme.io/0d26cc4844aa97adb793a266cb2a51961a1345e71a24eec305fcc16539d86027-31197524086801.jpg) 

**Retargeting desativado**

 ![ASA_R_Disabled.png](https://files.readme.io/425a0e1e802482a00230d7ceaebdcaa7f74523fb6feb75d60168f94b56886201-31197514618001.png) 

### Razões adicionais para discrepâncias

A tabela a seguir mostra os principais motivos para discrepâncias.

| Discrepância | Apple Search Ads | A AppsFlyer |
| --- | --- | --- |
| <span id="differences-related-to-appsflyer-sdk-versions"></span>Diferenças relacionadas às versões do SDK da AppsFlyer | Conta conversões independentemente da versão do SDK da AppsFlyer. | Para AdsServices, a versão 6.1.3+ do SDK é necessária para atribuir corretamente. |
| <span id="limit-ad-tracking-lat-and-att"></span>Limit ad tracking (LAT) e ATT. | Sempre conta a conversão.<br /><br />Se a sua campanha for limitada por idade e gênero, os usuários com LAT serão excluídos.<br /><br />Usuários da Apple com menos de 18 anos sempre são LAT. | As conversões de LAT são atribuídas como orgânicas.<br /><br />Se AdServices for implementado e o iOS 14.3+ estiver instalado, os usuários sem consentimento serão atribuídos corretamente. |
| <span id="counting-users"></span>Contagem de usuários | Conta usuários com base nos downloads | Conta usuários com base na primeira abertura do aplicativo |
| <span id="reinstall-a-user-after-installing-the-app-deletes-it-clicks-on-a-search-ad-then-installs-the-app-again"></span>Reinstalação: depois de instalar o aplicativo, um usuário o exclui, clica em um Search Ad e o instala novamente | Conta como uma conversão (instalação) | <ul><li>Com IDFA: a AppsFlyer identifica a reinstalação e não a conta para fins de UA. Dica! Ative o retargeting e a reinstalação será registrada como uma instalação de retargeting (ou seja, reatribuição)</li><li>Sem IDFA: a AppsFlyer pode depender do IDFV para determinar se esta é uma reinstalação ou uma nova instalação:<ol><li>Se um ou mais outros aplicativos do fornecedor estiverem instalados no dispositivo, a AppsFlyer atribui o Apple Ads como uma reatribuição.</li><li>Caso contrário (se não existir nenhum outro aplicativo), a AppsFlyer atribui a instalação ao Apple Ads.</li></ol></li></ul> |
| <span id="click-lookback-window"></span>Janela de lookback de clique | Janela fixa de 30 dias | Para respostas de AdServices que não têm a hora do clique, a janela de lookback de cliques é de 30 dias. |
| <span id="impression-lookback-window"></span>Janela de lookback de impressão | Janela fixa de 24 horas | Para respostas de AdServices que não têm a hora da impressão, a janela de lookback de impressão é de 24 horas. |
| <span id="preregistration-click-and-impression-lookback-window-discrepancy"></span>Diferença entre as janelas de lookback de clique e impressão de pré-registro |  | Para respostas do AdServices que não têm horário de clique ou de impressão, a janela de lookback de clique ou de impressão é fixa.<ul><li>**Clique**: 90 dias</li><li>**Impressão**: 61 dias</li></ul> |
| <span id="winning-click"></span>Clique vencedor (final) | Sempre atribui a si mesmo se o usuário teve engajamento e fez o download do aplicativo. | Tem visibilidade em múltiplas networks e atribui de acordo com a metodologia do último clique |
| <span id="install-time"></span>Hora da instalação | Hora do download do aplicativo | Primeira abertura do aplicativo |
| <span id="time-zone"></span>Fuso horário | Fuso horário local da loja de aplicativos | Fuso horário UTC ou conforme definido nas configurações da AppsFlyer |
| <span id="conversion-data"></span>Dados de conversão | Pode levar mais de 5 segundos para que a AppsFlyer seja atualizada se o Search Ads for responsável pela instalação | Atribui dentro de 5 segundos no momento em que a Conversion Data API responde. Se nenhum dado for recebido, a resposta é orgânica. |
| <span id="cost-data"></span>Dados de custo | Reporta custo para todas as palavras-chave | Não reporta dados de custo para palavras-chave contendo letras maiúsculas no dashboard de cohort ou na Cohort API. |
| <span id="geo-locations"></span>Geolocalizações | O Apple Search Ads permite que os anunciantes segmentem usuários de acordo com seu país e região. O Apple Search Ads é compatível com um número limitado de [**países**](https://searchads.apple.com/storefronts/). | A AppsFlyer reconhece a localização geográfica exata do usuário com base no endereço de IP e, portanto, informa sobre as geolocalizações não disponíveis no Apple Search Ads.<br /><br />Dica! Os usuários que instalam um app enquanto estão no próprio país da app store têm os mesmos dados geográficos na AppsFlyer e no Apple Search Ads. |
| <span id="missing-conversion-payload-for-gender-and-age-targeted-users"></span>Payload de conversão ausente para usuários segmentados por gênero ou idade (aplica-se a partir de 1 de setembro de 2026) | Pode contabilizar essas conversões nos relatórios do Apple Ads, embora a Apple não forneça uma reivindicação de atribuição para essa coorte. | Grupos de anúncios com segmentação por idade ou gênero retornam um payload de atribuição como false; por isso, esses usuários não são atribuídos ao Apple Ads no AppsFlyer. Isso pode fazer com que o Apple Ads reporte mais conversões do que o AppsFlyer para os grupos de anúncios afetados. |

</Accordion>

<Accordion title="Dicas">

Trabalhar com o Apple Search Ads permite que você colete dados de marketing valiosos, o que pode melhorar seus esforços de aquisição de usuários com todas as fontes de mídia para seus aplicativos iOS.

Dicas para ajudar você a maximizar os benefícios do Apple Search Ads:

| Observação | Detalhes |
| --- | --- |
| <span id="get-keyword-data"></span>Obtenha dados de palavra-chave | O Apple Search Ads compartilha dados de palavras-chave com a AppsFlyer. Você pode ver os dados da palavra-chave nas ferramentas de dados brutos e de análise como Pivot, Retenção e Cohort.<br /><br />**Atenção:**<ul><li>A coleta de dados de palavras-chave pode ter um atraso de 8 a 12 horas e, em alguns casos, pode incluir apenas o ID da palavra-chave, sem o termo correspondente da palavra-chave.</li><li>Para obter os dados de palavras-chave, a opção de "custo" deve estar ativada. Os dados de palavras-chave são fornecidos como parte da [integração de custos](/docs/apple-ads-integration-setup#cost-tab), sem que seja necessário uma assinatura do ROI360.</li></ul>Nos casos em que os dados da palavra-chave estão ausentes na AppsFlyer, isso pode ser causado por:<ul><li>**Tipo de pacote:** os dados de palavra-chave são compartilhados pelo Apple Search Ads com anunciantes que têm o pacote [avançado](https://searchads.apple.com/advanced/) do Apple Search Ads.</li><li>**Tipo de campanha:** você pode configurar diferentes tipos de correspondência de palavras-chave de campanha no Apple Search Ads. Com base no tipo de correspondência, o Apple Search Ads compartilha as palavras-chave da seguinte forma:<ul><li>**Correspondência exata:** As palavras-chave exatas pesquisadas pelo usuário</li><li>**Correspondência ampla:** As palavras-chave que a Apple usou para realizar a pesquisa. Elas são parecidas com os termos de pesquisa reais do usuário.</li><li>**Correspondência de pesquisa:** a Apple **não** compartilha essas palavras-chave com anunciantes.</li></ul></li></ul>**Use apenas campanhas de pesquisa de correspondência exata ou ampla** para receber dados completos de palavras-chave. |
| <span id="compare-the-quality-of-users-based-on-keyword-data"></span>Compare a qualidade dos usuários com base em dados de palavras-chave | Nem todas as palavras-chave são iguais, o que significa que, embora diferentes palavras-chave possam ter o mesmo custo, a qualidade dos usuários atraídos pode ser diferente. Use os relatórios de Retenção ou de <Anchor target="_blank" href="/marketers/pt/docs/pivot-table-user-metrics">Pivot</Anchor> para identificar as palavras-chave que maximizam seu ROI. |
| <span id="analyze-keyword-cost"></span>Analisar custo da palavra-chave | A plataforma contém dados agregados de custo de palavra-chave quando as campanhas de palavra-chave do Apple Ads são configuradas como [correspondência exata ou correspondência ampla](/docs/apple-ads-integration-setup#get-keyword-data). Os dados de custo de palavra-chave têm as seguintes características:<ul><li>O histórico de dados está disponível a partir de 13 de outubro de 2019.</li><li>Dimensões:<ul><li>Data</li><li>Campanha</li><li>Conjunto de anúncios</li></ul></li><li>Ferramentas de análise:<ul><li><Anchor target="_blank" href="/marketers/pt/docs/cohort-and-retention-dashboard">Coorte</Anchor></li><li><Anchor target="_blank" href="/marketers/pt/docs/pivot-table-user-metrics">Pivot</Anchor></li><li><Anchor target="_blank" href="/marketers/pt/docs/master-api-user-acquisition-metrics-via-api">Master API</Anchor></li></ul></li></ul>**Limitações**<ul><li>Use apenas as dimensões observadas para filtrar e agrupar consultas de dados de custo. Por exemplo, não filtre ou agrupe usando Geo.</li></ul>**<span id="h_01M0YZYCC5S0E3HA296KAA0SDZ"></span>Exemplos**<br /><br />**<span id="cohort-example"></span>Exemplo de Cohort**<br /><br />O exemplo a seguir mostra como configurar o Cohort para exibir informações de custo e ROI.<br /><br />**Configuração do Cohort**<br /><br /><Image alt="CohortRequest.png" src="https://files.readme.io/73004ab25cfff029786ec4601e22a0ac4b02a146141787b51bda1a02d5412330-31197524095377.png" width="327px" /><br /><br />**Tabela de resultados de cohort**<br /><br />Na tabela a seguir, o custo total e o ROI do cohort são exibidos<br /><br /><Image alt="CohortTable.png" src="https://files.readme.io/ebceedb82207bdbc7f58daafc0557630ac35a73a11b14d207a7283b93294073d-31197514633233.png" width="429px" /><br /><br />**<span id="pivot-example"></span>Exemplo do Pivot**<br /><br />**Configuração do Pivot**<br /><br /><Image alt="Pivot_define.png" src="https://files.readme.io/29ad177a5ef681f8358968092005d8ba871f3dd06661a8dea6d186318c08a476-31197524107153.png" width="413px" /><br /><br />**Tabela de resultados do Pivot**<br /><br /><Image alt="Pivot.png" src="https://files.readme.io/ef9766de2059d0608e8ae6dc063053f2926ffa296e7eca2e13a1bc4171921d2c-31197524111505.png" width="439px" /> |
| <span id="find-the-best-performing-creative-set"></span>Encontre o conjunto de criativos com a melhor performance | ![creative_sets.png](https://files.readme.io/ef8e38d67121283742dcbd1faef11d94a8ea1c612dc258611e72cbf826d7ef8f-31197524112785.png)<br /><br />Recomendamos que você teste como os leads respondem a diferentes criativos. Os conjuntos de criativos com melhor performance têm taxas de conversão mais altas. Além disso, os melhores conjuntos de criativos convertem usuários com um nível mais alto de engajamento.<br /><br />Isso afeta todos os seus leads de iOS, não apenas os leads do Apple Ads, pois todos eles chegam à página do seu aplicativo na App Store. No entanto, com as instalações do Apple Ads, a AppsFlyer indica o ID do conjunto de criativos no parâmetro <Anchor target="_blank" href="/marketers/pt/docs/raw-data-field-dictionary">raw data</Anchor> **Ad ID**, permitindo que você compare a performance de diferentes conjuntos de criativos. |
| <span id="target-redownloaders"></span>Segmentação de re-downloads | Seus usuários anteriores possivelmente são a melhor audiência para você segmentar usando o Apple Ads.<br /><br />Um usuário que desinstalou seu aplicativo e, como resultado da sua campanha de retargeting do Apple Ads, instala novamente é chamado de Re-Downloader pelo Apple Ads. Se a reinstalação for realizada durante a <Anchor target="_blank" href="/marketers/pt/docs/set-up-re-attribution-window">janela de reatribuição</Anchor>, a AppsFlyer chamará isso de Reatribuição. Em todos os outros casos, ela é tratada como uma nova instalação.<br /><br />![ASACGroupID.png](https://files.readme.io/ebdc380f2abc3e9a3b134cd258d90ae32f75b3ee4d9eadde39adbc728daae523-31197514645265.png) |

</Accordion>

<Accordion title="Log de alterações do Apple Ads">

| Data de início | Atualização/alteração |
| --- | --- |
| <span id="20260901"></span>09-2026-01 | A partir de 1 de setembro de 2026:<ul><li>A API AdServices da Apple adiciona um carimbo de data/hora de engajamento a todas as reivindicações de atribuição do iOS, independentemente do status do ATT. A AppsFlyer usa esse carimbo de data/hora para aplicar a janela de lookback configurada pelo anunciante e as regras de atribuição de último toque a essas reivindicações.</li><li>Para grupos de anúncios com segmentação por idade ou gênero, a Apple retornará um payload de atribuição como false, o que significa que nenhuma mensuração de SRN pode ser aplicada a essa coorte segmentada.</li></ul>Consulte a documentação para desenvolvedores do AdServices da Apple para mais detalhes. |
| <span id="20230207"></span>07/02/2023 | Os parâmetros de atribuição enriquecidos `Campaign name`, `Adset name` e `Keywords` só estão disponíveis quando a aba Custo está ativada, independentemente do seu plano de assinatura.  <br />**Isso significa que para que seus dashboards e relatórios de dados brutos mostrem campaign names, adset names e keywords, você deve ter a aba Custo ativada.** Etapa 1: |
| <span id="20220216"></span>16/02/2022 | As palavras-chave estão disponíveis via Cost API. Você deve ativar a API na página de integração do Apple Search Ads. Atenção! A API está disponível para todos os anunciantes, independentemente do seu plano de assinatura. |
| <span id="20210407"></span>07/04/2021 | Integração do Apple Ads: o Apple Ads funciona independentemente da SKAdNetwork e atribui usuários de forma determinística. Isso significa que, para usuários atribuídos ao Apple Ads, você tem toda a gama de recursos e mensurações fornecida pelo nosso <Anchor target="_blank" href="/marketers/pt/docs/appsflyer-attribution-model">modelo de atribuição de LTV.</Anchor> |
| <span id="20210307"></span>07/03/2021 | O Apple Search Ads está lançando a versão 4.0 da Campaign Management API. A API está relacionada ao custo e a outros dados relativos à campanha. Isso não afeta a atribuição. Estamos no processo de adotar a API atualizada. Nenhuma ação é exigida por você. |
| <span id="20210215"></span>15/02/2021 | A partir desta data, os campos campaign name e adset name podem ser preenchidos se você habilitar a [Cost API](/docs/apple-ads-integration-setup#cost-tab) de custo do Apple Ads. A API está disponível para todos os anunciantes, independentemente do plano de assinatura. |

Atualizações e alterações do Apple Ads

</Accordion>

<Accordion title="Disponibilidade dos parâmetros da campanha do Apple Search Ads">

A tabela abaixo mostra a disponibilidade dos parâmetros de atribuição nos relatórios de dados brutos ou no dashboard.

| Parâmetro do relatório de dados brutos | Disponibilidade |
| --- | --- |
| Campaign name | Para que esse parâmetro esteja disponível, você deve habilitar a [Cost API](/docs/apple-ads-integration-setup#cost-tab) na página de integração do Apple Search Ads. A API está disponível para todos os anunciantes, independentemente de seu plano de assinatura |
| ID da campanha | Sempre disponível |
| Nome do Adset | Para que esse parâmetro esteja disponível, você deve habilitar a [Cost API](/docs/apple-ads-integration-setup#cost-tab) na página de integração do Apple Search Ads. A API está disponível para todos os anunciantes, independentemente de seu plano de assinatura |
| Adset ID | Sempre disponível |
| As ad | Atualmente não disponível |
| ID do anúncio | Esse parâmetro só está disponível quando ambas as condições a seguir são atendidas:<ul><li>Os usuários usam o iOS 15.2 e versões posteriores</li><li>O anúncio usa</li></ul><Anchor target="_blank" href="https://developer.apple.com/app-store/product-page/">Páginas de produtos personalizadas</Anchor> para campanhas associadas a qualquer um dos seguintes posicionamentos de anúncios:<ul><li>`Aba Hoje`</li><li>`Buscando resultados`</li></ul> |
| Palavras-chave | Para que esse parâmetro esteja disponível, você deve habilitar a [Cost API](/docs/apple-ads-integration-setup#cost-tab) na página de integração do Apple Search Ads. A API está disponível para todos os anunciantes, independentemente de seu plano de assinatura |
| ID da palavra-chave | Esse parâmetro está disponível por meio de relatórios de dados brutos. No entanto, ele deve ser explicitamente selecionado em Data Locker, Push API e Export data. No caso da Pull API, adicione `keyword_id` ao parâmetro  `&additional_fields` <Anchor target="_blank" href="/marketers/pt/docs/pull-api-raw-data#additional-fields">da chamada da Pull API</Anchor>. |
| Tipo de correspondência das palavras-chave | Atualmente não disponível |

</Accordion>

<Accordion title="Impacto da Privacidade Avançada Agregada">

A partir do iOS 14, o [ATTrackingManager](https://developer.apple.com/documentation/apptrackingtransparency/attrackingmanager/authorizationstatus/) (ATT) determina a disponibilidade do IDFA, e o Apple Ads controla os dados de atribuição em nível de usuário das instalações trazidas pelo Apple Ads. Assim, a disponibilidade de dados em nível de usuário das instalações geradas pelo Apple Ads não é afetada pela <Anchor target="_blank" href="/marketers/pt/docs/apply-aggregated-advanced-privacy-framework">Privacidade Avançada Agregada</Anchor>.

#### Após 1 de setembro de 2026

| **Consentimento à ATT** | **Hora do clique/impressão disponível** | **Janela de lookback de clique/impressão** | **Observações** | **Disponibilidade de dados** | **IDFA disponível** |
| --- | --- | --- | --- | --- | --- |
| Com consentimento e sem consentimento | Sim | Definido pelo anunciante | Regras de atribuição de último toque da AppsFlyer usadas | Dados de atribuição a nível do usuário | Sim para quem consentiu, não para quem não consentiu |

#### Antes de 1 de setembro de 2026

A disponibilidade do horário de clique/impressão, a janela de lookback e a disponibilidade dos dados variavam de acordo com o consentimento do ATT:

| **Consentimento à ATT** | **Hora do clique/impressão disponível** | **Janela de lookback de clique/impressão** | **Considerações** | **Disponibilidade de dados** | **IDFA disponível** |
| --- | --- | --- | --- | --- | --- |
| Anunciante | Yes | Disponível apenas em <Anchor target="_blank" href="/marketers/pt/docs/about-data-locker-advanced-reports">relatórios avançados</Anchor>. | Regras de atribuição de último toque da AppsFlyer usadas | Dados de atribuição no nível do usuário | Sim |
| Sem consentimento | Sem | Cliques: 30 dias (definido pelo Apple Ads), impressões: 24 horas | Prioridade é dada a candidatos determinísticos | Dados de atribuição a nível de usuário sem a hora do clique/impressão. | Não |

</Accordion>

#### Veja também

* <Anchor target="_blank" href="/marketers/pt/docs/apply-aggregated-advanced-privacy-framework">Estrutura de privacidade avançada agregada</Anchor>
* <Anchor target="_blank" href="/marketers/pt/docs/set-up-lookback-windows">Explicando as janelas de lookback</Anchor>

<div data-zendesk-anchors="set-up-asa-integration=configure-a-integra%C3%A7%C3%A3o-com-o-apple-ads h_01HDPCGMP2CY4B37VM3AT2P114=configure-a-integra%C3%A7%C3%A3o-com-o-apple-ads set-up-agencies-and-asa-marketing-partners=configurar-ag%C3%AAncias-e-parceiros-de-marketing-do-apple-ads h_01HDPCGMP3D96BG496G7H97YWP=configurar-ag%C3%AAncias-e-parceiros-de-marketing-do-apple-ads agency-vs-marketing-partner=ag%C3%AAncia-vs-parceiro-de-marketing h_01HDPCGMP3YGJEA942DF2YC9P1=ag%C3%AAncia-vs-parceiro-de-marketing configuring-agencies-and-marketing-partners=configurando-ag%C3%AAncias-e-parceiros-de-marketing h_01HDPCGMP3NQQ76SC32SEC8TS4=configurando-ag%C3%AAncias-e-parceiros-de-marketing configuration-steps-checklist=checklist-das-etapas-de-configura%C3%A7%C3%A3o h_01HDPCGMP39HE117X4MP25M77W=checklist-das-etapas-de-configura%C3%A7%C3%A3o advertiser-actions=a%C3%A7%C3%B5es-do-anunciante h_01HDPCGMP3S3PHHH3F6KZE3SEV=a%C3%A7%C3%B5es-do-anunciante agency-actions=a%C3%A7%C3%B5es-da-ag%C3%AAncia h_01HDPCGMP3MK61YRMCQA2KA5X2=a%C3%A7%C3%B5es-da-ag%C3%AAncia cost-clicks-and-impressions-data=dados-de-custo-cliques-e-impress%C3%B5es h_01HDPCGMP3AVYYK2X03RF057FN=dados-de-custo-cliques-e-impress%C3%B5es additional-information=informa%C3%A7%C3%B5es-adicionais h_01HDPCGMP3BXVASH2YJ9G8AS2C=informa%C3%A7%C3%B5es-adicionais h_01M0YZYCC477D5MMBC6D5BD3MG=depois-de-1-de-setembro-de-2026 h_01M0YZYCC4RRSRWBDAKN6ECV7N=antes-de-1-de-setembro-de-2026 retargeting-related-discrepancies=discrep%C3%A2ncias-relacionadas-ao-retargeting h_01HDPCGMP4Z9M3QR6QGRR7A8BM=discrep%C3%A2ncias-relacionadas-ao-retargeting additional-reasons-for-discrepancies=raz%C3%B5es-adicionais-para-discrep%C3%A2ncias h_01HDPCGMP4QJ3HYEP7EAYMHRQQ=raz%C3%B5es-adicionais-para-discrep%C3%A2ncias h_01HDPCGMP4MF9FBP4WDRHVZ4BR=cohort-example h_01HDPCGMP4EFMZ4FHZ8WBWW9R2=pivot-example h_01M0YZYCC5H6FBKYNEHZA91BSZ=ap%C3%B3s-1-de-setembro-de-2026 h_01M0YZYCC5QK9A6T9KV2XDSK8P=antes-de-1-de-setembro-de-2026-1 h_01M0YZYCC5V5N4Z3M3327W2XFT=veja-tamb%C3%A9m" />
