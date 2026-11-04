---
title: Configurar a atribuição web da AppsFlyer
metadata:
  keywords:
    - Web Attribution
    - Web Attribution SDK
    - Marketers
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - Web Attribution
  created_at: '2026-02-05T08:47:53Z'
  edited_at: '2026-08-18T00:23:17Z'
  id: 43541863890961
  locale: pt
  section: AppsFlyer Web Attribution
  section_id: 43560690387729
  url: https://support.appsflyer.com/hc/pt/articles/43541863890961
---
> **Em resumo:** Configure as definições de atribuição web para controlar como a AppsFlyer atribui visitas ao site, conversões e atividade do usuário às campanhas de marketing. As definições incluem janelas de atribuição, eventos de aquisição de usuários, regras de reengajamento e exclusões de domínio.

<div id="overview" />

## Escritórios

As definições de atribuição web definem como a AppsFlyer mede e atribui a atividade do usuário no seu site. Estas definições determinam:

* Quais eventos se qualificam como aquisição de usuários.
* Por quanto tempo atribuir eventos subsequentes às fontes de marketing.
* Quando considerar os usuários como recorrentes (reengajamento) ou readquiridos.
* Quais domínios excluir da atribuição.

<div id="who-should-configure-these-settings" />

### Quem deve configurar estas definições

As equipes de marketing e os gerentes de growth normalmente configuram essas definições com base nos objetivos de negócios. As equipes técnicas podem se envolver na integração do SDK e na configuração do domínio.

<div id="accessing-web-attribution-settings" />

### Acesso às definições de atribuição web

Para acessar as definições de atribuição do seu aplicativo web:

1. Na AppsFlyer, acesse **My Apps**
2. Selecione seu aplicativo web na lista
3. Acesse **App Settings** > **Attribution**

<div id="quick-reference" />

## Referência rápida

| Configuração | Padrão | Opções | Editável | O que controla |
| --- | --- | --- | --- | --- |
| Nome da aplicação | Entrada do usuário | 1–100 caracteres | Yes | Nome de exibição na AppsFlyer |
| URL completa (domínio principal) | Entrada do usuário | 1–500 caracteres | Sem | Identificador do aplicativo e domínio primário excluído |
| Web SDK ID | Gerado automaticamente | 1–550 caracteres | Sem | Identificador do SDK para coleta de eventos |
| Currency | Selecionado pelo usuário | Códigos ISO | Yes | Relatórios de receita e ROI |
| Fuso horário | Selecionado pelo usuário | Zonas IANA | Com limitação | Carimbos de data/hora do relatório |
| Evento de aquisição de usuários | Primeira visita | Nome do evento | Yes | Quando um usuário é considerado adquirido |
| Janela de lookback (UA) | 30 dias | 1 hora–90 dias | Yes | Até quando encontrar um touchpoint de UA |
| Janela de reengajamento | 30 dias | 1 hora–90 dias | Yes | Por quanto tempo o retargeting recebe crédito |
| Janela de inatividade (reengajamento) | Desativado | 0–30 dias | Yes | Inatividade mínima para retargeting |
| Janela de atribuição | Lifetime | Opções predefinidas | Yes | Por quanto tempo os eventos são atribuídos à UA |
| Janela de inatividade (reaquisição) | 90 dias | 1–180 dias | Yes | Quando os usuários são considerados churned |
| Evento de re-aquisição | Visita | Nome do evento | Yes | O que traz os usuários churned de volta |
| Domínios excluídos | Apenas primário | Até 100 | Yes | Domínios ignorados para atribuição |

**Restrição:**  
A janela de inatividade de reengajamento deve ser **menor ou igual à** janela de inatividade de reaquisição. Caso contrário, os usuários poderão ser readquiridos antes de se qualificarem para retargeting.

<div id="basic-settings" />

## **Configurações básicas**

As configurações básicas do aplicativo web são:

* Nome da aplicação
* URL completa
* Web SDK ID
* Currency
* Fuso horário

Para mais informações, consulte <Anchor target="_blank" href="/marketers/pt/docs/adding-an-app-to-appsflyer#web">Adicionar um aplicativo ao AppsFlyer</Anchor>.

<div id="user-acquisition-settings" />

## Configurações de aquisição de usuários

As configurações de aquisição de usuários (UA) determinam como o AppsFlyer identifica quando um usuário é adquirido pela primeira vez e como atribuir essa aquisição às fontes de marketing.

<div id="user-acquisition-event" />

<Accordion title="Evento de aquisição de usuários">

O evento que aciona a aquisição de usuários. Esta é uma ação de negócios importante que define quando você considera que um usuário foi realmente "adquirido".

<div id="why-customize" />

#### Por que personalizar

A **primeira visita** padrão geralmente representa um sinal fraco do valor do usuário. Um usuário pode clicar em um anúncio acidentalmente ou sair imediatamente. Ao personalizar essa configuração, você garante que o valor de longo prazo (LTV) seja atribuído à fonte de marketing que impulsionou uma ação significativa, e não apenas um clique por curiosidade.

**Padrão:** primeira visita (o usuário é adquirido na primeira visita ao site)

<div id="common-alternatives-by-industry" />

#### Alternativas comuns por vertical

| **indústria** | **Evento de UA recomendado** |
| --- | --- |
| Bancos/Finanças | registration ou first\_time\_deposit |
| E-commerce | sign\_up ou first\_purchase |
| Delivery | first\_order |
| SaaS/Assinatura | subscription\_start |
| Gaming | sign\_up ou tutorial\_complete ou first\_purchase |

<div id="how-it-works" />

#### Como funciona

Se definido como **primeira visita**:

* Os usuários são adquiridos imediatamente na primeira visita ao site.
* A atribuição começa na primeira visita.

Se definido como **um evento personalizado** (por exemplo, sign\_up):

* Os usuários entram em um **"período de pré-aquisição"** desde a primeira visita até realizarem o evento.
* Durante a pré-aquisição, os eventos são atribuídos ao último touchpoint não orgânico dentro da janela de lookback (atribuição de último toque).
* Quando o evento de UA personalizado ocorre, uma **conversão de aquisição de usuários** é criada e a atribuição de longo prazo começa.

<div id="example-scenario-ua-event--sign_up" />

#### Exemplo de cenário (evento de UA = sign\_up):

* **Dia 0:** O usuário visita o site por um anúncio do Facebook → O período de pré-aquisição começa
* **Dia 2:** O usuário visita o site por um anúncio do Google → O crédito muda para o Google (último toque)
* **Dia 3:** O usuário se cadastra → A aquisição de usuários é atribuída ao anúncio do Google

**Dia 10:** O usuário faz uma compra → A compra é atribuída ao Google para mensuração de LTV

</Accordion>

<div id="lookback-window-user-acquisition" />

<Accordion title="Janela de lookback (aquisição de usuários)">

Até quanto tempo atrás a AppsFlyer procura o touchpoint de marketing que impulsionou a aquisição de usuários.

Essa janela controla por quanto tempo a AppsFlyer "se lembra" de um touchpoint de marketing. Se um usuário visita o site por um anúncio, mas só conclui o evento de UA mais tarde, essa configuração determina se o anúncio ainda recebe o crédito.

**Padrão:** 30 dias

**Intervalo:** de 1 hora a 90 dias

<div id="how-it-works-1" />

#### Como funciona

Quando um usuário realiza o evento de UA (por exemplo, sign\_up), a AppsFlyer busca dentro dessa janela o touchpoint não orgânico mais recente e atribui a aquisição a essa fonte de marketing.

<div id="example-1-30-day-lookback" />

#### Exemplo 1 (lookback de 30 dias):

* **Dia 0:** O usuário clica em um anúncio do Facebook e visita o site
* **Dia 25:** O usuário retorna diretamente e conclui o evento sign\_up
* **Resultado:** A aquisição de usuários é atribuída ao Facebook (dentro da janela de lookback de 30 dias)

<div id="example-2-window-expired" />

#### Exemplo 2 (janela expirada):

* **Dia 0:** O usuário clica em um anúncio do Facebook e visita o site
* **Dia 40:** o usuário retorna diretamente e conclui o evento sign\_up

**Resultado:** a aquisição de usuários é marcada como orgânica (fora da janela de lookback de 30 dias)

</Accordion>

<div id="re-engagement-settings" />

## Configurações de reengajamento

As configurações de reengajamento controlam como a AppsFlyer atribui a atividade quando usuários adquiridos retornam ao seu site por meio de campanhas de retargeting.

<div id="reengagement-window-item" />

<Accordion title="Janela de reengajamento">

Por quanto tempo, após uma conversão de reengajamento, a AppsFlyer continua a atribuir eventos a esse touchpoint de marketing.

Essa configuração determina por quanto tempo as campanhas de retargeting recebem crédito pela atividade do usuário. Ela equilibra a atribuição de crédito aos esforços de retargeting, ao mesmo tempo que continua atribuindo o LTV de longo prazo à fonte de aquisição original.

**Padrão:** 30 dias

**Intervalo:** de 1 hora a 90 dias

<div id="how-it-works-2" />

#### Como funciona

Quando um usuário adquirido retorna por uma fonte não orgânica (por exemplo, um anúncio de retargeting) e atende aos critérios de reengajamento, uma **conversão de retargeting** é criada. Os eventos dentro desta janela recebem **atribuição dupla**:

1. **Atribuição primária** → Campanha de retargeting
   * Objetivo: dar crédito à campanha de retargeting
2. **Atribuição secundária** → Fonte de UA original
   * Objetivo: dar suporte à visualização de UA que mensura o valor total do ciclo de vida do usuário (LTV) até a aquisição original

<div id="example-within-window" />

#### Exemplo (dentro da janela):

* **Dia 0:** usuário adquirido por meio de um anúncio do Facebook
* **Dia 50:** o usuário clica em uma campanha de retargeting por e-mail e retorna (conversão de retargeting criada)
* **Dia 60:** Usuário faz uma compra de US$100 (10 dias após o retargeting)
* **Resultado - atribuição dupla:**
  * **Primária (visualização de retargeting):** Campanha de e-mail recebe crédito pela compra de US$100
  * **Secundária (visualização de UA):** o anúncio do Facebook também é rastreado para US$100 no LTV do usuário
* **Relatórios:**
  * Visualização unificada: mostra a compra atribuída ao e-mail
  * Visualização de retargeting: mostra a compra atribuída ao e-mail
  * Visualização de UA: mostra a compra atribuída ao Facebook

</Accordion>

<div id="inactivity-window-for-reengagement" />

<Accordion title="Janela de inatividade para reengajamento">

O período mínimo de inatividade do usuário necessário para que um touchpoint não orgânico possa criar uma conversão de reengajamento (retargeting).

Evite creditar campanhas de retargeting quando os usuários já estiverem engajados ativamente com seu site. Isso otimiza o orçamento de retargeting ao garantir que as campanhas segmentem usuários realmente inativos.

**Padrão:** Desativado

**Intervalo:** 0 (desativado) a 30 dias

<div id="how-it-works-3" />

#### Como funciona

**Quando desativado:**

* Cada touchpoint não orgânico de um usuário adquirido cria uma conversão de retargeting

**Quando ativado (por exemplo, 7 dias):**

* Só cria uma conversão de retargeting se o usuário estiver inativo há pelo menos 7 dias
* Se o usuário esteve ativo recentemente, a visita será atribuída à fonte de UA original

**Restrição:**

* Não pode exceder a janela de inatividade (re-aquisição)

<div id="example-7-day-inactivity-window" />

#### Exemplo (janela de inatividade de 7 dias):

* **Dia 0:** Usuário adquirido por meio de um anúncio do Facebook
* **Dia 3:** Usuário visita de forma orgânica
* **Dia 5:** Usuário clica em um anúncio de retargeting → **Nenhuma conversão de retargeting** (apenas 2 dias de inatividade)
* **Dia 15:** Usuário clica em um anúncio de retargeting → **Conversão de retargeting criada** (12 dias de inatividade)

</Accordion>

<div id="re-acquisition-settings" />

## Configurações de reaquisição

As configurações de reaquisição determinam quando usuários inativos são considerados "churned" e como trazê-los de volta como usuários readquiridos.

<div id="inactivity-window-reacquisition" />

<Accordion title="Janela de inatividade (reaquisição)">

O período de inatividade total após o qual um usuário é marcado como "churned". Usuários "churned" podem ser readquiridos, gerando uma nova conversão de aquisição de usuários.

Essa configuração define o limite de churn da sua empresa. Ela determina quando um usuário é considerado "perdido" e elegível para ser readquirido, permitindo que campanhas de win-back recebam crédito por trazer de volta usuários "churned".

**Padrão:** 90 dias

**Intervalo:** 1 a 180 dias

<div id="how-it-works-4" />

#### Como funciona

**Quando o usuário é marcado como "churned":**

* O usuário não é mais atribuído à fonte original de UA para novos eventos
* O usuário entra em um estado de "pré-aquisição" (aguardando ser readquirido)
* As janelas de atribuição da aquisição original não se aplicam mais

**Quando o usuário churned retorna:**

* Se o usuário realizar o evento de reaquisição → uma nova conversão de UA será criada
* A campanha de win-back recebe o crédito como a nova fonte de aquisição
* O usuário é tratado como uma aquisição completamente nova do ponto de vista de relatórios

<div id="example-90-day-window" />

#### Exemplo (janela de 90 dias):

* **Dia 0:** usuário adquirido por meio de anúncio do Google
* **Dia 50:** última atividade
* **Dia 140:** usuário churned (90 dias inativo)
* **Dia 145:** usuário clica na campanha de win-back por e-mail

**Dia 146:** usuário realiza o evento de reaquisição → **Nova conversão de UA** atribuída à campanha de e-mail

</Accordion>

<div id="reacquisition-event" />

<Accordion title="Evento de re-aquisição">

O evento que aciona a reaquisição para usuários churned. Somente usuários que sofreram churn podem ser readquiridos.

Muitos eventos de aquisição de usuários são ações únicas (por exemplo, sign\_up, first\_purchase) que não podem acontecer duas vezes. Essa configuração permite definir um evento repetível que sinaliza que um usuário que sofreu churn retornou.

**Padrão:** visit (usuários churned são **readquiridos imediatamente** na primeira visita de retorno)

**Alternativas comuns:** sign\_in ou purchase

<div id="how-it-works-5" />

#### Como funciona

**Se definido como um evento personalizado (por exemplo,** **sign\_in**):

* Usuários que sofreram churn devem realizar o evento específico para serem readquiridos
* O usuário pode visitar várias vezes antes que ocorra a reaquisição
* Definição mais rigorosa de reaquisição "verdadeira".

<div id="example-re-acquisition-event--sign_in" />

#### Exemplo (evento de reaquisição = sign\_in):

* Usuário churned após 90 dias de inatividade
* Usuário clica na campanha de win-back por e-mail e visita → Ainda não foi readquirido
* Um dia depois, o usuário faz login → Conversão de reaquisição criada, atribuída à campanha de e-mail

</Accordion>

<div id="attribution-window" />

## Janela de atribuição

<div id="time-period" />

<Accordion title="Período">

O período máximo após a aquisição de usuários durante o qual a AppsFlyer atribui eventos a essa conversão.

**Padrão:** Para sempre

**Opções disponíveis:** Nenhum, 1 dia, 7 dias, 30 dias, 60 dias, 90 dias, 180 dias, 365 dias, Para sempre (limitado pela retenção de dados)

</Accordion>

<div id="excluded-domains" />

## Domínios excluídos

Domínios excluídos da atribuição. Isso impede que a AppsFlyer atribua visitas ou eventos quando os usuários navegam entre domínios especificados e seu site.

**Propósito:**

1. **Evita a autoatribuição:** Exclua seus próprios domínios
2. **Exclui fluxos de terceiros:** Exclua gateways de pagamento e provedores de autenticação

<div id="domain-types" />

<Accordion title="Tipos de domínio">

<div id="primary-required-automatic" />

#### PRIMÁRIO (obrigatório, automático)

* O domínio principal do seu site (definido durante a criação do aplicativo)
* Adicionado automaticamente e não pode ser removido
* Exatamente um domínio primário por aplicativo web
* **Exclusão automática de subdomínios:** O domínio primário exclui automaticamente todos os seus subdomínios
  * Exemplo: example.com exclui automaticamente shop.example.com, blog.example.com etc.
* **Impacto da exclusão:** Sem autoatribuição

<div id="internal-optional" />

#### INTERNO (opcional)

* Outros domínios da sua marca não abrangidos pelo domínio primário
* Adicione até 99 domínios adicionais
* Exemplo: Diferentes domínios de nível superior, como example.co.uk, example.in
* **Impacto da exclusão:** Sem autoatribuição

<div id="external-optional" />

#### EXTERNO (opcional)

Existem dois tipos de exclusões de domínio externo:

<div id="external-listed-by-you" />

#### Externo (listado por você)

* Domínios usados diretamente pelo seu site, mas que não fazem parte da sua marca
* Isso inclui gateways de pagamento, sites de processamento de pagamentos e provedores de autenticação
* Adicione até 99 domínios adicionais
* Exemplos: auth0.com, okta.com, facebook.com, google.com
* **Impacto da exclusão:** As visitas são desconsideradas

<div id="external-listed-by-appsflyer" />

#### Externo (listado pela AppsFlyer)

* Domínios automaticamente excluídos pela AppsFlyer:

  **Provedores de pagamento**

  * PayPal (checkout de pagamento)
  * Stripe (checkout de pagamento)
  * Adyen (checkout de pagamento)
  * Klarna (checkout de pagamento)
  * Braintree (gateway de pagamento)
  * Square (checkout de pagamento)
  * Paddle (checkout de pagamento)
  * Mollie (checkout de pagamento)
  * Alipay (checkout de pagamento)
  * Razorpay (checkout de pagamento)
  * Paytm (checkout de pagamento)
  * PayU (checkout de pagamento)
  * Mercado Pago (checkout de pagamento)
  * Yandex Pay (checkout de pagamento)
  * Naver Pay (checkout de pagamento)

  **Login com OAuth e SSO**

  * Google Sign-In (login da conta do Google)
  * Apple ID (login da conta Apple)
  * Microsoft (login da conta Microsoft 365 / Entra)
  * Microsoft Live (login da conta do Outlook/Live)
  * Facebook Login (apenas o domínio de entrada do Facebook)
  * Yandex Login (login da conta do Yandex)
  * Kakao Login (login da conta do Kakao)
  * Naver Login (login da conta do Naver)
  * LINE Login (login da conta do LINE)
  * Weixin Login (entrada OAuth do WeChat)
  * VK Login (login da conta do VK)
  * Daum Login (login da conta do Daum)
* A lista de domínios automáticos não pode ser editada
* **Impacto da exclusão:** as visitas são desconsideradas

</Accordion>

<div id="adding-excluded-domains" />

<Accordion title="Adicionar domínios excluídos">

**Para adicionar domínios:**

1. Acesse as configurações do seu aplicativo web → Atribuição
2. Acesse a seção Domínios excluídos
3. Clique em **Adicionar domínio**
4. Insira o nome do domínio (por exemplo, custom-gateway.com)
5. Selecione um tipo de domínio: Interno ou Externo
6. Clique em **Salvar**.

**Notas Importantes:**

* As exclusões entram em vigor em até **1 hora**
* As alterações se aplicam **somente de forma prospectiva** (não afetam dados históricos)
* Provedores de pagamento comuns e domínios de entrada OAuth/SSO são excluídos automaticamente. Consulte a lista completa em [Externo (listado pela AppsFlyer)](#externo-listado-pela-appsflyer) (não é necessário adicioná-los manualmente)

</Accordion>

<div id="requirements-and-validation" />

<Accordion title="Requisitos e validação">

<div id="domain-format" />

#### Formato do domínio:

* Somente o nome do domínio (sem protocolos, caminhos ou portas)
* Máximo de 500 caracteres por domínio
* Protocolos (https://) removidos automaticamente, convertidos para minúsculas

<div id="examples" />

#### Exemplos:

* example.com ✅
* shop.example.com ✅ (mas desnecessário se example.com for o domínio principal)
* https://example.com → example.com ✅ (protocolo removido)
* example.com/path ❌ (caminhos não são permitidos)
* example.com:8080 ❌ (portas não são permitidas)

<div id="limits" />

#### Limites:

* Máximo de 100 domínios no total (incluindo 1 PRINCIPAL)

</Accordion>

<div id="migrating-from-people-based-attribution-pba" />

## Migração do People-Based Atribuição (PBA)

<div id="key-differences" />

<Accordion title="Principais diferenças">

| **Aspecto** | **PBA (legado)** | **Nova mensuração da performance web** |
| --- | --- | --- |
| **Nível de configuração** | Nível do agrupamento de marca | Nível do aplicativo web |
| **Evento UA personalizado** | Disponível | Totalmente personalizável |
| **Janelas de tempo** | Controle limitado | Controle total (1h - vitalício) |

</Accordion>

<div id="migration-steps" />

<Accordion title="Etapas da migração">

1. Criar novo aplicativo web
   1. Vá para Meus aplicativos → Adicionar aplicativo → Selecione Website
2. Escolha o ID do SDK web   
   Reutilize a chave de desenvolvimento PBA existente (recomendado) para evitar alterações no código do seu site.
3. Configurar definições   
   Mapeie as definições de PBA para as novas definições de atribuição web
4. Adicionar domínios excluídos   
   Mapeie os domínios excluídos de PBA (pacote da marca) para as novas configurações de atribuição web

**Observação:** Cada chave de desenvolvimento de PBA só pode ser atribuída a UM novo aplicativo web.

</Accordion>

<div data-zendesk-anchors="overview=escrit%C3%B3rios h_01KGPFHN8MKTPX5VYDEV30M9A7=escrit%C3%B3rios who-should-configure-these-settings=quem-deve-configurar-estas-defini%C3%A7%C3%B5es h_01KGPFK1RNA7ZTJRACJ6M97EAB=quem-deve-configurar-estas-defini%C3%A7%C3%B5es accessing-web-attribution-settings=acesso-%C3%A0s-defini%C3%A7%C3%B5es-de-atribui%C3%A7%C3%A3o-web h_01KGPFM0DJDMVDXZC2B6G6DVX5=acesso-%C3%A0s-defini%C3%A7%C3%B5es-de-atribui%C3%A7%C3%A3o-web quick-reference=refer%C3%AAncia-r%C3%A1pida h_01KGPFT1W65R724WCNDPBHY3F6=refer%C3%AAncia-r%C3%A1pida basic-settings=configura%C3%A7%C3%B5es-b%C3%A1sicas h_01KGPGJG092S1TEDB1T9JNBASE=configura%C3%A7%C3%B5es-b%C3%A1sicas user-acquisition-settings=configura%C3%A7%C3%B5es-de-aquisi%C3%A7%C3%A3o-de-usu%C3%A1rios h_01KGPGE592EK59XXVKTTFDGX16=configura%C3%A7%C3%B5es-de-aquisi%C3%A7%C3%A3o-de-usu%C3%A1rios h_01KGPGRTEFA0PJ3DB7MR4W85EB=user-acquisition-event why-customize=por-que-personalizar h_01KGPHMJWF6Z1VV0KH301TYAS5=por-que-personalizar common-alternatives-by-industry=alternativas-comuns-por-vertical h_01KGPHMSEDGJ2E6NSB1ZCR5CCW=alternativas-comuns-por-vertical how-it-works=como-funciona h_01KGPHN5M5GBBMPBYRMYHB9F0E=como-funciona example-scenario-ua-event-sign_up=exemplo-de-cen%C3%A1rio-evento-de-ua--sign_up h_01KGPHQES3SF5AKBNYD8CY3RG8=exemplo-de-cen%C3%A1rio-evento-de-ua--sign_up h_01KGPGRTEFYRAZD7Z9NYDKV907=lookback-window-user-acquisition how-it-works::69b3417c=como-funciona-1 h_01KGPHX2JNAWZ8VJZ25CRWP1ER=como-funciona-1 example-1-30day-lookback=exemplo-1-lookback-de-30-dias h_01KGPHX8JMG7FMRS1MYFYS6JRV=exemplo-1-lookback-de-30-dias example-2-window-expired=exemplo-2-janela-expirada h_01KGPHXT83JHJ6J0APVN7NRJ3E=exemplo-2-janela-expirada reengagement-settings=configura%C3%A7%C3%B5es-de-reengajamento h_01KGPJ1ZMXXJJNCBB52CHY95Z2=configura%C3%A7%C3%B5es-de-reengajamento reengagement-window%C2%A0item=reengagement-window-item h_01KGPJ58N3712E1NZ4E6JVGAY2=reengagement-window-item how-it-works::dafb60ec=como-funciona-2 h_01KGPJFG3X578XCP5X353RRVR1=como-funciona-2 example-within-window=exemplo-dentro-da-janela h_01KGPJG6WSYX2R0VVQYXXWZSMA=exemplo-dentro-da-janela h_01KGPJ58N3QH9RKXTVZXCZ1WGW=inactivity-window-for-reengagement how-it-works::4a4cf0f=como-funciona-3 h_01KGPJK3H2JF7PV1ATQB3TE9AX=como-funciona-3 example-7day-inactivity-window=exemplo-janela-de-inatividade-de-7-dias h_01KGPJKDMY4FRAJSMHE19GGJCA=exemplo-janela-de-inatividade-de-7-dias reacquisition-settings=configura%C3%A7%C3%B5es-de-reaquisi%C3%A7%C3%A3o h_01KGPJMJDX83SBA77A7BSRZ87V=configura%C3%A7%C3%B5es-de-reaquisi%C3%A7%C3%A3o h_01KGPJPC0QXYFD6Q09XF7T3XA9=inactivity-window-reacquisition how-it-works::9c91010b=como-funciona-4 h_01KGPJV8EJR94H1P7GZXMP8HSR=como-funciona-4 example-90day-window=exemplo-janela-de-90-dias h_01KGPJVHCNBZHD9ZXW288CGG9H=exemplo-janela-de-90-dias h_01KGPJPC0QY2726Z583AQ7G5W2=reacquisition-event how-it-works::587eebec=como-funciona-5 h_01KGPJY5PA9907PXBRC2QHNJ6T=como-funciona-5 example-reacquisition-event-sign_in=exemplo-evento-de-reaquisi%C3%A7%C3%A3o--sign_in h_01KGPJYWG31QJ1G5A09QC00AMY=exemplo-evento-de-reaquisi%C3%A7%C3%A3o--sign_in attribution-window=janela-de-atribui%C3%A7%C3%A3o h_01KGPK8H7P5AT59S0GQ9ZK0F01=janela-de-atribui%C3%A7%C3%A3o h_01KGPK1CSV5XGKHX3XVS37QFKS=time-period excluded-domains=dom%C3%ADnios-exclu%C3%ADdos h_01KGPKA56KQRJKRS54HBR50NJN=dom%C3%ADnios-exclu%C3%ADdos h_01KGPKCY1EBCMYDDYS6SZEK1ZR=domain-types primary-required-automatic=prim%C3%A1rio-obrigat%C3%B3rio-autom%C3%A1tico h_01KGPKJQ7M82KW5VE9ESYNNFEQ=prim%C3%A1rio-obrigat%C3%B3rio-autom%C3%A1tico internal-optional=interno-opcional h_01KGPKJV9B2BHDR64JD24VHH1X=interno-opcional external-optional=externo-opcional h_01KGPKJZQYZESHHH3D0NA2WC9F=externo-opcional external-listed-by-you=externo-listado-por-voc%C3%AA h_01KGPKK4THXQ88AXT58GZ2MHHE=externo-listado-por-voc%C3%AA external-listed-by-appsflyer=externo-listado-pela-appsflyer h_01KGPKK96ZAZSKVPBX60FC888X=externo-listado-pela-appsflyer h_01KGPKCY1ETKF1NQ2BP6Z3JH4T=adding-excluded-domains h_01KGPKCY1EE01631ZEYGC6FEJH=requirements-and-validation domain-format=formato-do-dom%C3%ADnio h_01KGPKKXRA59A4RDY4QE1M0Q66=formato-do-dom%C3%ADnio examples=exemplos h_01KGPKM213203KA8CEBHZ9KJP3=exemplos limits=limites h_01KGPKM8AMQ5BA88ZCSTRJ2JV7=limites migrating-from-peoplebased-attribution-pba=migra%C3%A7%C3%A3o-do-people-based-atribui%C3%A7%C3%A3o-pba h_01KGPKPGSF3VSBTQJR6JN80BF4=migra%C3%A7%C3%A3o-do-people-based-atribui%C3%A7%C3%A3o-pba h_01KGPKQPWC1GYYGYYD6PCDWX29=key-differences h_01KGPKQPWD00B08Z76ZYGRP4AT=migration-steps" />
