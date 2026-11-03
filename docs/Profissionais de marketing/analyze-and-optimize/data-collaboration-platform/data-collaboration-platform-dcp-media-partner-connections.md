---
title: Conexões com parceiros de mídia da plataforma de colaboração de dados (DCP)
metadata:
  keywords:
    - Marketers
    - Audience Activation
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-yael-sharabi
    - Marketers
    - Audience Activation
  created_at: '2026-04-12T14:19:36Z'
  edited_at: '2026-08-19T00:07:05Z'
  id: 45669216166417
  locale: pt
  section: Data Collaboration Platform
  section_id: 26230608274065
  url: https://support.appsflyer.com/hc/pt/articles/45669216166417
---
## De relance

Conecte suas audiências a parceiros de mídia para ativar suas campanhas personalizadas e alcançar o máximo de resultados.

## Sobre as conexões de parceiros

As conexões com parceiros da <Anchor target="_blank" href="/marketers/pt/docs/data-collaboration-platform-dcp-guide">Data Collaboration Platform (DCP)</Anchor> permitem que você conecte com segurança suas audiências do DCP a parceiros de mídia compatíveis, para que você possa ativar campanhas personalizadas nas plataformas deles. Depois que um parceiro é conectado a uma audiência, a DCP entrega a audiência com base no fluxo de atualização e ativação configurado, usando os dados de fonte disponíveis mais recentes e as <Anchor target="_blank" href="/marketers/pt/docs/data-collaboration-platform-dcp-create-and-manage-sources#permissões-de-compartilhamento">permissões</Anchor>.

> 📘 **Atenção**
>
> * A audiência é entregue para ativação como uma lista de identificadores de usuário. Cada entrega representa uma captura completa da audiência no momento da exportação.
> * As atualizações de audiência não são contínuas nem em tempo real. Em vez disso, elas são acionadas de acordo com a política definida, que se baseia em uma cadência e verifica se os dados de fonte foram atualizados. Cada atualização gera e envia a lista de audiências para os destinos selecionados.

## Conexões de parceiros compatíveis

Esta seção lista as conexões com parceiros de mídia compatíveis com a DCP, junto com os requisitos de configuração de cada parceiro, permissões, tipos de campanha compatíveis e quaisquer requisitos adicionais ou limitações.

<div id="google-ads" />

<Accordion title="Google Ads">

**Plataforma do parceiro de mídia:**  
Google Ads

**Nome do parceiro de mídia na DCP:**  
Google Ads

**Requisitos para configuração da conexão e permissões da conta do parceiro de mídia:**

* Conta Google ativa.
* Acesso do usuário: acesso padrão ou de administrador à conta do Google Ads
* Customer Match: deve estar habilitado e aprovado
* Autorização do parceiro: conta aprovada para trabalhar com o parceiro (via representante do Google)
* Link do parceiro: conexão de backend criada pelo Google

**Como funciona**

Um usuário padrão/admin deve habilitar a integração durante a configuração.   
Depois disso, a DCP faz upload das audiências automaticamente por meio do link do parceiro.

**Recursos oficiais:**  
<Anchor target="_blank" href="https://support.google.com/google-ads/answer/10589050">Ajuda do Customer Match do Google Ads</Anchor>

**Tipos de campanha compatíveis:**

* **Pesquisa**  
  Use listas do Customer Match nos modos Observação ou Segmentação para ajustar lances ou refinar a segmentação para consultas de pesquisa.
* **Display**  
  Segmente ou exclua audiências diretamente na Google Display Network usando listas do Customer Match.
* **Vídeo (YouTube)**  
  Use audiências para segmentação de anúncios no YouTube (in-stream, in-feed, Shorts).
* **Shopping**  
  Aplique audiências no modo Observação para otimizar lances para usuários em campanhas do Shopping.
* **Performance Max (PMax)**  
  Use listas do Customer Match como sinais de audiência para orientar a automação do Google (não é segmentação rígida).
* **Demand Gen**  
  Use listas do Customer Match para segmentação direta de audiências no YouTube, Discover e Gmail.
* **Campanhas de Aplicativo**   
  As campanhas de aplicativo para instalação (ACi) usam audiências carregadas apenas como sinais de otimização, enquanto as campanhas de reengajamento (ACe) oferecem suporte à segmentação determinística e são o principal método de ativação de audiências.

#### Diretrizes para campanhas de aplicativo (ACi & ACe)

As campanhas de aplicativo do Google (antes conhecidas como Universal App Campaign - UAC) se comportam de forma diferente de outros tipos de campanha ao usar audiências do Customer Match:

**Campanhas de Aplicativo para Instalações (ACi)**

Criadas para adquirir novos usuários em escala.  
As audiências do Customer Match **não podem ser usadas para segmentação direta.**  
As audiências carregadas são usadas **apenas como sinais** para melhorar o machine learning e a otimização do Google.  
A ativação é **totalmente automatizada pela IA do Google**, sem controle sobre a inclusão/exclusão de audiências.  
Exige histórico suficiente da conta (por exemplo, dados de conversão e gastos) para ser elegível.

**Campanhas de Aplicativo para Engajamento (ACe)**

Criadas para **reengajar usuários existentes.**  
As audiências do Customer Match oferecem suporte à **segmentação determinística.**  
Os anunciantes podem:

* Fazer segmentação de segmentos específicos de usuários (por exemplo, usuários inativos, compradores)
* Executar campanhas de ciclo de vida (upsell, cross-sell, retenção)

As listas de audiência do DCP são usadas como critérios principais de segmentação, de forma semelhante a outras plataformas.

> 📘 **Notas**
>
> * Use ACi quando seu objetivo for escala e aquisição de usuários (audiências = apenas sinais).
> * Use ACe quando seu objetivo for reengajamento e segmentação precisa de audiências (audiências = segmentação direta).

**Expiração da conexão:**

* As conexões geralmente são persistentes e não expiram automaticamente
* A reautenticação pode ser necessária se os tokens OAuth forem revogados, as permissões da conta mudarem, as configurações de senha/segurança forem atualizadas ou a autorização de parceiros do Google mudar

**Atualização das audiências:**

* As associações do Customer Match expiram após 540 dias, a menos que sejam atualizadas
* Validação operacional recomendada: a cada 60–90 dias
* Atualização recomendada das audiências: diária para campanhas de performance/ciclo de vida; no mínimo a cada 7 dias
* As audiências críticas não devem ficar desatualizadas por mais de 7 dias

**Requisitos/limitações adicionais:**

* As listas do Customer Match exigem no mínimo 1.000 usuários ativos correspondentes antes de poderem ser usadas para veicular anúncios.
* Consentimento da UE (DMA): você deve acrescentar que, para usuários no Espaço Econômico Europeu (EEE), é estritamente obrigatório transmitir sinais de consentimento explícito concedido (ad\_user\_data e ad\_personalization) para usar o Customer Match. Se o consentimento for negado ou estiver ausente, o usuário não será processado.

</Accordion>

<div id="dv360" />

<Accordion title="DV360">

**Plataforma do parceiro de mídia:**  
Google DV360 (Display & Video 360)

**Nome do parceiro de mídia no DCP:**  
DV360

**Requisitos de configuração da conexão e permissões da conta do parceiro de mídia:**

* Conta DV360 ativa
* Acesso do usuário: acesso em nível de parceiro ou de anunciante com permissões suficientes
* Ingestão de audiências ativada: a conta deve permitir uploads de audiências próprias de 1st-party
* Autorização do parceiro: conta aprovada para trabalhar com o parceiro (via representante do Google)
* Link do parceiro: conexão de backend criada pelo Google

**Como funciona**

As permissões de acesso apropriadas do DV360 são necessárias para habilitar a integração durante a configuração.  
Depois disso, o DCP faz upload das audiências automaticamente por meio do link do parceiro.

**Recursos oficiais:**  
<Anchor target="_blank" href="https://support.google.com/displayvideo/answer/9134175?hl=en">Ajuda sobre audiências do Display & Video 360</Anchor>

**Tipos de campanha compatíveis:**

* **Display** – Usado para segmentação direta de audiências e exclusões
* **Vídeo (YouTube & vídeo programático)** – Usado para segmentação direta de audiências no YouTube e no inventário de vídeo
* **Áudio** – Usado para segmentação em inventário de áudio digital
* **Nativo** – Usado para segmentação de audiências em posicionamentos nativos
* **Connected TV (CTV)** – Usado para segmentação em inventário de streaming e TV
* **Campanhas de aplicativo:** o DV360 oferece suporte a estratégias de instalação do aplicativo e reengajamento, mas em um modelo programático baseado em itens de linha. Ele não replica as Campanhas de Aplicativo do Google Ads, e as audiências do Customer Match são usadas diretamente para segmentação/exclusão, em vez de servirem como principais sinais de otimização ou para segmentação determinística de usuários do aplicativo.

**Expiração da conexão:**

* A conexão permanece ativa, a menos que seja revogada ou que as permissões sejam alteradas (espelha o comportamento do Google Ads)
* As associações de audiência seguem as políticas do Google Customer Match, incluindo a janela de expiração de 540 dias

**Atualização das audiências:**

* Validação operacional recomendada: a cada 60–90 dias
* Atualização recomendada das audiências: preferência diária; máximo de 7 dias entre atualizações para campanhas ativas

**Requisitos adicionais / limitações:**

* As listas do Customer Match exigem no mínimo 1.000 usuários ativos e correspondentes antes de poderem ser usadas para veicular anúncios.
* Consentimento da UE (DMA): você deve adicionar que, para usuários no Espaço Econômico Europeu (EEE), é estritamente obrigatório transmitir sinais explícitos de consentimento concedido (ad\_user\_data e ad\_personalization) para usar o Customer Match. Se o consentimento for negado ou estiver ausente, o usuário não será processado.

</Accordion>

<div id="meta-ads" />

<Accordion title="Meta Ads">

**Plataforma do parceiro de mídia:**  
Meta Ads Manager (Facebook / Instagram)

**Nome do parceiro de mídia no DCP:**  
Meta Ads

**Requisitos de configuração da conexão e permissões da conta do parceiro de mídia:**

* Conta pessoal válida da Meta (Facebook)
* Business Manager criado e vinculado à sua conta pessoal
* Pelo menos uma Página do Facebook
* Conta de anúncios pertencente ao Business Manager ou compartilhada com ele
* **Acesso do usuário:**
  * Acesso de administrador ao Business Manager
  * Acesso de administrador ou anunciante à conta de anúncios

Você deve ser o proprietário da conta de anúncios ou ter permissões de administrador/anunciante em uma conta de anúncios conectada a um Business Manager. Essas permissões são necessárias para gerenciar anúncios e audiências e são essenciais para as integrações do DCP.

**Requisitos importantes:**

* O usuário da Meta usado para conectar o DCP deve:
  * Aceitar os Termos & Condições dos anúncios da Meta
  * Aceitar os Termos de Serviço de audiências personalizadas

O mesmo usuário que autentica a conexão do DCP deve ter aceitado estes termos; caso contrário, a conexão falhará.

**Como funciona**

Você precisa ter as permissões necessárias durante a configuração para conectar o DCP.  

Depois que a configuração for concluída:

* O DCP pode fazer upload e atualizar as audiências automaticamente.

**Recursos oficiais:**  
<Anchor target="_blank" href="https://www.facebook.com/business/help/1143109949216644/">Ajuda do Meta Business</Anchor>

**Tipos de campanha compatíveis:**

As audiências personalizadas criadas no DCP podem ser ativadas nos seguintes tipos de campanha da Meta:

* **Reconhecimento (Reconhecimento da marca / Alcance)** – usado para segmentação ampla de audiências
* **Tráfego** – usado para impulsionar os usuários para um destino (por exemplo, site ou aplicativo)
* **Engajamento** – usado para otimizar interações (por exemplo, engajamento com publicações, visualizações de vídeo)
* **Leads** – usado para campanhas de geração de leads
* **Promoção de aplicativo** – usado para instalações de aplicativo e reengajamento
* **Vendas (Conversões)** – usado para impulsionar compras ou outros eventos de conversão

As audiências do DCP (Custom Audiences) podem ser usadas para segmentação direta em todos os tipos de campanha da Meta, com suporte a casos de uso de funil completo, do reconhecimento à conversão.

**Expiração da conexão:**

* As conexões geralmente são de longa duração, mas podem ser interrompidas devido a: redefinições de senha, alterações em MFA/segurança, permissões revogadas, alterações de propriedade no Business Manager ou análises de políticas da Meta

**Atualização das audiências:**

* Validação operacional recomendada: a cada 60–90 dias
* Atualização de audiências recomendada: diária para campanhas de conversão/ciclo de vida; a cada 3–7 dias é aceitável para campanhas de reconhecimento

</Accordion>

<div id="tiktok" />

<Accordion title="Tiktok">

**Plataforma do parceiro de mídia:**  
TikTok Ads Manager

**Nome do parceiro de mídia no DCP:**  
TikTok

**Requisitos de configuração da conexão e de permissões da conta do parceiro de mídia:**

Conta do Gestor de Anúncios TikTok.  
Conta de anunciante aprovada e ativa.  
Acesso de administrador ao anunciante.  

Conta ativa de anúncios do TikTok (Gestor de Anúncios)

* **Acesso à conta de anúncios:**
  * Acesso de administrador ou operador à conta de anúncios do TikTok
* **Permissões de audiência:**
  * Capacidade de criar e gerenciar Audiências Personalizadas
* **Autorização do parceiro:**
* O parceiro (DCP) deve receber acesso pelo TikTok Business Center ou pelo Gestor de Anúncios

**Como funciona**

Um administrador ou usuário padrão é necessário durante a configuração para autorizar e conectar o DCP.  

Após a conclusão da configuração:

* O DCP pode fazer upload e atualizar audiências automaticamente
* A ativação de audiência acontece diretamente em anúncios do TikTok usando essas audiências carregadas

**Recursos oficiais:**  
<Anchor target="_blank" href="https://ads.tiktok.com/help/article/invite-partners-into-tiktok-business-center?lang=en">Ajuda sobre acesso de parceiros no TikTok Business Center</Anchor>

**Tipos de campanha compatíveis:**

As audiências personalizadas criadas no DCP podem ser ativadas nos seguintes tipos de campanha do TikTok:

* **Alcance** – Usado para maximizar a exposição da audiência
* **Tráfego** – Usado para impulsionar usuários para um site ou uma página de destino
* **Visualizações de vídeo** – Usado para maximizar o engajamento com o vídeo
* **Geração de leads** – Usado para coletar leads diretamente no TikTok
* **Promoção de aplicativo** – Usado para instalações de aplicativo e reengajamento
* **Conversões (Conversões no site)** – Usado para impulsionar ações como compras ou cadastros

As audiências do DCP (Audiências Personalizadas) podem ser usadas para segmentação direta em todos os tipos de campanha do TikTok, com suporte a casos de uso de funil completo, do reconhecimento à conversão.

**Expiração da conexão:**

* A autorização OAuth/da empresa pode expirar ou ser revogada devido a alterações de permissões ou de administrador

**Atualidade das audiências:**

* Validação recomendada de token e permissões: trimestral
* Atualização recomendada de audiências: diária (preferencial); no máximo 7 dias para audiências ativas

**Requisitos adicionais / limitações:**

* Tamanho mínimo da audiência: uma Audiência Personalizada exige um mínimo rigoroso de 1.000 usuários correspondentes no total antes de poder ser aplicada a um grupo de anúncios

</Accordion>

<div id="pinterest" />

<Accordion title="Pinterest">

**Plataforma do parceiro de mídia:**  
Gerenciador de Anúncios do Pinterest

**Nome do parceiro de mídia no DCP:**  
Pinterest

**Requisitos de configuração da conexão e de permissões da conta do parceiro de mídia:**

* Conta comercial ativa do Pinterest  
  Conta do Gerenciador de Anúncios vinculada à empresa
* **Acesso do usuário:**
  * Acesso de administrador ou analista (com permissões de audiência) à conta de anúncios
* **Permissões de audiência:**
  * Capacidade de criar e gerenciar Listas de Clientes (audiências)
* **Acesso do parceiro:**
  * O parceiro (DCP) deve receber acesso à conta de anúncios por meio do Business Manager

**Como funciona**

É necessário um administrador ou um usuário (com acesso suficiente) durante a configuração para conectar o DCP e conceder permissões.  

Após a conclusão da configuração:

* O DCP pode fazer upload e atualizar audiências automaticamente

**Recursos oficiais:**  
<Anchor target="_blank" href="https://help.pinterest.com/en/business/article/audience-targeting">Ajuda do Pinterest sobre segmentação de audiência</Anchor>

**Tipos de campanha compatíveis:**

As audiências de Lista de Clientes criadas no DCP podem ser ativadas nos seguintes tipos de campanha do Pinterest:

* **Reconhecimento** – Usado para maximizar o alcance e a visibilidade da marca
* **Consideração (Tráfego / Engajamento / Visualizações de vídeo)** – Usado para impulsionar cliques, engajamento ou visualizações de vídeo
* **Conversões** – Usado para impulsionar ações como compras, cadastros ou outros eventos de conversão
* **Vendas por catálogo (anúncios de compras)** – Usado para promover produtos de um catálogo e impulsionar compras

As audiências do DCP (listas de clientes) podem ser usadas para segmentação direta em todos os tipos de campanha do Pinterest, oferecendo suporte a casos de uso de funil completo, do reconhecimento à conversão, incluindo campanhas de shopping/catálogo.

**Expiração da conexão:**

* Os tokens OAuth e as permissões dos parceiros podem expirar ou ser revogados, dependendo de alterações na empresa/conta

**Atualidade das audiências:**

* Validação operacional de reconexão recomendada: a cada 60–90 dias
* Atualização recomendada das audiências: a cada 1–7 dias, dependendo do tipo de campanha

</Accordion>

<div id="the-trade-desk" />

<Accordion title="The Trade Desk">

**Plataforma do parceiro de mídia:**  
The Trade Desk (TTD)

**Nome do parceiro de mídia no DCP:**  
The Trade Desk

**Requisitos de configuração da conexão e permissões da conta do parceiro de mídia:**

* Conta ativa na The Trade Desk (TTD)
* **Acesso do usuário:**
  * Acesso de nível Admin ou Trader à conta
* **Permissões de audiências:**
  * Capacidade de criar e gerenciar audiências de first-party (segmentos de dados)
* **Compartilhamento de dados ativado:**
  * A conta deve permitir o onboarding de dados/ingestão de audiências de parceiros externos (como DCPs)
* **Autorização do parceiro:**
  * O parceiro (DCP) deve ser aprovado e vinculado como provedor de dados na TTD
* **Credenciais de API (obrigatórias)** Necessárias para upload e ativação de audiências via API:
  * Gere na seção “First Party Data Credentials” no TTD (ou solicite ao administrador da sua conta TTD):
    * ID do anunciante
    * Chave secreta do anunciante

**Como funciona**

Um usuário Admin ou Trader é necessário durante a configuração para:

* Ativar a integração
* Gerar credenciais de API
* Aprovar o compartilhamento de dados dos parceiros

Após a conclusão da configuração:

* A DCP faz upload de audiências por meio de credenciais de API + configuração do parceiro
* As audiências estão disponíveis como segmentos de dados party na TTD

**Recursos oficiais:**  
<Anchor target="_blank" href="https://www.thetradedesk.com/">Plataforma The Trade Desk</Anchor>

**Tipos de campanha compatíveis:**

As audiências first-party criadas na DCP podem ser ativadas nos seguintes tipos de campanha da TTD:

* **Display** – Usado para segmentação direta de audiências em inventário web e in-app
* **Vídeo (Vídeo online & CTV)** – Usado para segmentação em inventário de vídeo programático e TV conectada
* **Áudio** – Usado para segmentação em plataformas de áudio digital/streaming
* **Nativo** – Usado para segmentação de audiências em formatos de anúncios nativos

As audiências da DCP no The Trade Desk são usadas para segmentação direta em todos os tipos de campanha, incluindo Display, Vídeo (CTV & OLV), Áudio e Nativo, permitindo a ativação determinística de audiências em todos os canais.

**Expiração da conexão:**

* As credenciais de API normalmente têm longa duração até serem rotacionadas ou revogadas manualmente
* Rotação recomendada de credenciais: a cada 6–12 meses, de acordo com a política de segurança

**Atualização das audiências:**

* Atualização recomendada das audiências: diária ou semanal, dependendo do caso de uso de ativação e da volatilidade do segmento

</Accordion>

## Criar uma conexão com parceiros

Você pode configurar conexões com parceiros como parte do fluxo do criador de audiências ou separadamente.

<div id="setup-as-part-of-the-audiencebuilder-flow" />

<Accordion title="Configuração como parte do fluxo do criador de audiências">

<span id="h_01HZHF5BWHBE7W8VNM3QFB7K58"></span>**Para criar uma conexão com parceiro de mídia como parte do fluxo do criador de audiências:**

Siga as instruções detalhadas <Anchor target="_blank" href="/marketers/pt/docs/data-collaboration-platform-dcp-build-and-activate-audiences#step-3-connect-and-export">aqui</Anchor>.

</Accordion>

<div id="separate-setup" />

<Accordion title="Configuração separada">

<span id="h_01HZHF5BWH7P8HCWS9SG1JQ2BT"></span>**Para criar uma conexão fora do fluxo do criador de audiências:**

1. Na AppsFlyer, no menu lateral, vá para **Colaborar** > **Data Clean Room.**
2. No menu no canto superior direito, clique em **Gerenciar conexões**.
3. Clique em **Nova conexão**. Se você já tiver conexões de nuvem existentes na sua conta, verá todas elas em **Parceiro**.
4. Na caixa de diálogo **Nova conexão com parceiros de mídia**, selecione o parceiro de mídia correspondente.

   <Image alt="Nova conexão do parceiro de mídia.png" src="https://files.readme.io/1c50a570d4eb495c3d77ee8e572b14a577e39adad65e41fe20eb3b014cce8989-46196842129425.png" width="91.09%" />
5. Insira um nome para a conexão.
6. Faça login na conta do parceiro de mídia com suas credenciais e siga as instruções para conceder acesso à AppsFlyer.
7. Clique em **Selecionar ID da conta** e selecione a conta correspondente para a conexão.
8. Clique em **Guardar**. A nova conexão é adicionada à lista de parceiros.

</Accordion>

<div data-zendesk-anchors="at-a-glance=de-relance h_01KNS1JFT1R7K6MCWJRGA2EAAY=de-relance about-partner-connections=sobre-as-conex%C3%B5es-de-parceiros h_01KNS1JFT1C788JKA9ZH657TE0=sobre-as-conex%C3%B5es-de-parceiros h_01KP0WCJVS71MZ5XEXRHRWXX2Q=aten%C3%A7%C3%A3o media-partner-connections=conex%C3%B5es-de-parceiros-compat%C3%ADveis h_01KNS1JFT1CT1AC1C6PAZAM779=conex%C3%B5es-de-parceiros-compat%C3%ADveis h_01KNS1JFT1RE8MA525AJ99D9DS=google-ads app-campaigns-aci-ace-guidelines=diretrizes-para-campanhas-de-aplicativo-aci--ace h_01KQC3Y84E1GT5VJB463N42SFT=diretrizes-para-campanhas-de-aplicativo-aci--ace h_01KQC759QZPWJ7MWGPK7TJ06HW=notas h_01KNS1JFT1VESJCKHV4S11EKST=dv360 h_01KNS1JFT1P3ZR6EG6YR0M1F98=meta-ads h_01KNS1JFT1GTXJ4PMV5QKSDEX9=tiktok h_01KNS1JFT18VRXFHBYPRTS2MS6=pinterest h_01KNS1JFT2GJMKYNGR6ZRMWN25=the-trade-desk create-a-partner-connection=criar-uma-conex%C3%A3o-com-parceiros h_01KP115WC2QNT7MAS73HZSHQJT=criar-uma-conex%C3%A3o-com-parceiros h_01KP11SX0VMYNRCY9C7GKQPYGB=setup-as-part-of-the-audiencebuilder-flow h_01KP11SX0VCAQM5MEGV3RKG086=separate-setup" />
