---
title: Integre o Web SDK da AppsFlyer
deprecated: false
hidden: false
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  created_at: '2026-09-15T09:07:44Z'
  edited_at: '2026-09-16T00:39:31Z'
  id: 50896216552337
  locale: pt
  section: Web platform
  section_id: 50896333547281
  url: https://support.appsflyer.com/hc/pt/articles/50896216552337
---
**Resumo:** Instale o Web SDK da AppsFlyer (também conhecido como pixel) no seu site para registrar visitas e eventos de usuários na plataforma e defina um Customer User ID (CUID) para unificar jornadas cross-platform.

## Visão geral

O Web SDK permite que você registre como os visitantes interagem com seu site e envia essa informação para a AppsFlyer. É um módulo plug-in de 40–60 KB que comunica as visitas e ações dos usuários no seu site à plataforma da AppsFlyer.

### Integre o SDK manualmente

 Siga as etapas abaixo para concluir a integração do Web SDK, desde a instalação até a validação e aos controles de privacidade.

1. [Receber suas chaves](#1-receber-suas-chaves). Obtenha o ID do Web SDK (também conhecido como Web Dev Key).
2. [Selecionar um code snippet](#2-selecionar-um-code-snippet). Escolha o snippet que corresponde ao seu tipo de integração e requisitos de segurança.
3. [Implementar o Web SDK](#3-implementar-o-snippet). Implemente o SDK usando um snippet nativo, o Google Tag Manager ou o Adobe Launch Tag Manager.
4. [Verificar se o SDK está funcionando](#4-verificar-se-o-sdk-está-funcionando). Certifique-se de que o SDK está enviando solicitações ao conferir as chamadas de rede nas ferramentas de desenvolvedor do navegador.
5. [Configurar e gravar eventos](#5-configurar-e-gravar-eventos). Defina e envie eventos personalizados no carregamento da página ou em interações do usuário usando o JavaScript nativo ou o Google Tag Manager.
6. [Definir o Customer User ID](#6-definir-o-customer-user-id). Defina um CUID para unificar a atividade da web com outras plataformas.
7. [Gerenciar a privacidade](#7-gerenciar-a-privacidade). Controle a mensuração opt-in ou opt-out e configure a segurança e os filtros de dados (Política de Segurança de Conteúdo e descarte dos parâmetros de consulta).
8. [Referência de cookies do Web SDK](#referência-de-cookies-do-web-sdk). Analise os cookies que o Web SDK configura ou usa, incluindo propósito, duração e alcance.

#### Integre o SDK com um agente de codificação de IA

Em vez de integrar manualmente o SDK web (veja as etapas abaixo), use uma ferramenta de codificação com IA (Cursor, Claude Code, Codex, Copilot) para implementar toda a integração por você. Copie o prompt, substitua os dois placeholders e cole-o na sua ferramenta de codificação com IA.

Essa abordagem simplifica e cobre todas as etapas abaixo, mas você ainda precisa garantir que o SDK funcione corretamente e revisar sua configuração de privacidade depois.

Antes de copiar o prompt, substitua:

* `<WEB_SDK_ID>`: Na AppsFlyer, acesse **Configurações do aplicativo**, selecione seu aplicativo web (o domínio do seu site com o prefixo "website-") e copie o **ID do SDK web** em **Autenticação do SDK**.
* `<PRODUCTION_URL>`: a URL ativa do seu site, usada para verificação pós-implantação.

> 📘 **Note**
>
> A ferramenta de IA cria um plano de eventos com base na sua base de código e aguarda sua aprovação antes de implementá-lo. Revise o plano, confirme que os valores de receita e moeda aparecem apenas em eventos de receita realizada e verifique os resultados usando as etapas de verificação pós-implantação do prompt.

<Accordion title="Prompt de implementação com IA">

```markdown
# **AppsFlyer Web SDK - prompt de implementação com IA**

Copie o prompt abaixo para uma ferramenta de codificação com IA que possa editar seu projeto (Cursor, Claude Code, Codex, Copilot). Antes de copiar, substitua dois placeholders:

  - <WEB_SDK_ID> - na AppsFlyer, acesse Meus aplicativos, selecione seu aplicativo web (seu domínio com o prefixo website-) e copie o ID do SDK web (também chamado de Web Dev Key) em Autenticação do SDK.
  - <PRODUCTION_URL> - a URL do seu site em produção, usada para verificação pós-implantação.

Implemente o AppsFlyer Web SDK (pixel de atribuição web) neste site, incluindo os eventos que importam para minha mensuração de marketing.

Meu ID do SDK web: <WEB_SDK_ID>

Minha URL de produção: <PRODUCTION_URL>

## Etapa 0 - Bloqueio de configuração

Se o ID do SDK web acima estiver ausente ou ainda for um placeholder, responda APENAS com uma solicitação curta pedindo esse dado (na AppsFlyer: Meus aplicativos > o aplicativo com prefixo "website-" > Autenticação do SDK > ID do SDK web) e pare. Não escreva nenhum código até que ele seja fornecido. Se a URL de produção estiver ausente, solicite-a na mesma resposta - ela é necessária para a verificação pós-implantação.

Trabalhe com diffs mínimos: deduza os caminhos dos arquivos a partir do repositório, altere apenas o que essa integração exige e preserve os padrões existentes do projeto.

## Etapa 1 - Analise o site primeiro

Antes de escrever qualquer código, revise a base de código e monte você mesmo o plano de eventos - não me peça para listar os eventos:

1. Identifique o framework (HTML puro, React, Next.js, Vue etc.) e onde o <head> do documento é controlado.

2. Descubra as ações de conversão a partir do código. Procure, em ordem de confiabilidade:

   - Chamadas de analytics existentes: eventos de gtag()/GA4, Segment analytics.track(), fbq('track'), dataLayer.push (incluindo objetos de eCommerce) - elas mostram tanto as ações quanto onde os valores (valor, moeda, ID do pedido) já estão.

   - Lógica de comércio: módulos de checkout/carrinho, páginas/rotas de confirmação do pedido e de agradecimento, retornos de chamada de sucesso de pagamento.

   - Lógica de autenticação: fluxos de cadastro e login, e onde o ID interno do usuário fica disponível no código do cliente.

   - Formulários e CTAs: formulários de leads, inícios de assinatura/teste e downloads.

   - Produtos sem comércio / de ferramentas: se o site não tiver fluxos de compra, carrinho, checkout, cadastro ou login, não invente eventos de comércio nem de autenticação. Identifique as ações reais do produto (por exemplo, gerar, copiar, exportar, download, compartilhar, selecionar modelo, editar parâmetros) e mapeie-as para nomes descritivos de eventos personalizados.

3. Mapeie cada ação descoberta para o nome padrão da AppsFlyer:

   - pedido concluído / "Order Completed" / purchase_success -> af_purchase (com eventRevenue)

   - signup / register / conta criada -> af_complete_registration

   - login / signin -> af_login

   - adicionar ao carrinho / "Produto adicionado" -> af_add_to_cart (af_price, sem eventRevenue)

   - iniciar checkout / "Checkout Started" -> af_initiated_checkout (af_price, sem eventRevenue)

   - visualização de produto ou conteúdo -> af_content_view

   - assinatura iniciada -> af_subscribe; teste grátis iniciado -> af_start_trial

   - busca -> af_search

   Qualquer item sem equivalente padrão mantém um nome personalizado descritivo.

4. Para cada evento, identifique no código a fonte exata de: o valor realmente cobrado (para af_purchase), a moeda, o ID do pedido/transação e o ID do usuário. Reutilize as mesmas fontes de dados que a análise existente usa.

5. Verifique se existe uma plataforma de gerenciamento de consentimento (CMP), como OneTrust ou Didomi. Sinalize também qualquer alternância de consentimento criada internamente ou qualquer preferência de privacidade armazenada pelo site e me pergunte como isso deve controlar a mensuração, em vez de decidir por conta própria.

Atenção: as análises existentes servem apenas como input de descoberta - implemente os eventos da AppsFlyer como chamadas diretas de AF(), sem retransmiti-los via Segment/GA4 com os nomes deles.

Em seguida, mostre o plano de eventos proposto como uma tabela (nome do evento da AppsFlyer, gatilho + arquivo, fonte de receita/af_price, fonte do ID de deduplicação) e aguarde minha aprovação antes de implementar. Sinalize qualquer evento em que você não conseguiu localizar a fonte do valor, em vez de adivinhar.

## Etapa 2 - Instalação do snippet do SDK

Adicione este snippet perto do topo do <head> em todas as páginas, com meu ID do SDK web:

<script>

!function(t,e,n,s,a,c,i,o,p){t.AppsFlyerSdkObject=a,t.AF=t.AF||function(){

(t.AF.q=t.AF.q||[]).push([Date.now()].concat(Array.prototype.slice.call(arguments)))},

t.AF.id=t.AF.id||i,t.AF.plugins={},o=e.createElement(n),p=e.getElementsByTagName(n)[0],o.async=1,

o.src="https://websdk.appsflyer.com?"+(c.length>0?"st="+c.split(",").sort().join(",")+"&":"")+(i.length>0?"af_id="+i:""),

p.parentNode.insertBefore(o,p)}(window,document,"script",0,"AF","pba",{pba: {webAppId: "<WEB_SDK_ID>"}})

</script>

Regras rígidas:

- Use o snippet literalmente. NÃO o reescreva como um componente personalizado nem como um módulo wrapper. SDKs encapsulados podem enviar eventos personalizados, enquanto a visita automática (o evento LOAD do SDK) nunca é disparada - o site então mostra zero visitas e nada pode ser atribuído.

- O SDK deve carregar exatamente UMA vez por carregamento de página. No React/Next.js, proteja contra re-renderizações e montagem dupla (por exemplo, carregue-o no template HTML/document raiz, não dentro de um componente que é montado novamente). Vários carregamentos podem impedir o SDK de funcionar.

- Se o site já carregar o SDK da AppsFlyer por meio de um gerenciador de tags (GTM), NÃO o adicione também no código - um carregador, não dois. Avise-me se você encontrar uma tag existente da AppsFlyer.

- NÃO implemente manualmente um evento de visualização de página nem um evento de visita. O SDK registra visitas automaticamente no carregamento; um evento "page_view" feito manualmente nunca contará como visita.

- A chave de configuração é webAppId (não appId).

- Se o site aplicar uma Content Security Policy rígida com nonces, adicione o nonce à tag do snippet inline E garanta que a política inclua 'strict-dynamic' — o snippet injeta o script do SDK dinamicamente e, sem 'strict-dynamic', uma política somente com nonce o bloqueia.

## Etapa 3 - Implementar eventos

Formato da chamada do evento:

AF('pba', 'event', {

  eventType: 'EVENT',            // sempre a string literal 'EVENT'

  eventName: 'af_purchase',

  eventRevenue: 49.99,           // nível superior - apenas em receita realizada

  eventRevenueCurrency: 'USD',   // nível superior - código ISO de 3 letras; o padrão é USD se omitido

  eventValue: {                  // metadados JSON, máximo de 1000 caracteres

    "af_order_id": "TXN-12345",

    "af_customer_event_id": "evt-abc-001"

  }

});

Regras de evento - siga estas exatamente:

1. Use nomes padrão de evento da AppsFlyer para que os relatórios multiplataforma e os funis fiquem alinhados: af_purchase, af_complete_registration, af_login, af_add_to_cart, af_initiated_checkout, af_content_view, af_subscribe. Se houver um app mobile, use os MESMOS nomes de eventos do SDK mobile. Nunca adicione sufixos de plataforma como "_web".

   Exceção – linhas de compra distintas: se o site vender claramente níveis ou categorias de produtos distintos que precisem de detalhamentos separados no dashboard (por exemplo, dois produtos de assinatura), proponha nomes separados no plano de eventos (af_purchase_<tier>) em vez de um evento genérico e explique o motivo. A segmentação apenas por eventValue não aparece nas visualizações padrão do dashboard. Nunca envie AMBOS: um evento no nível de tier e um evento genérico para a mesma compra — isso duplica os dados.

2. A receita vai SOMENTE no campo eventRevenue de nível superior e SOMENTE em eventos nos quais o dinheiro realmente mudou de mãos (compra concluída, assinatura concluída, reserva confirmada). Valores dentro de eventValue (af_revenue, revenue, price, amount, total) NUNCA são contabilizados como receita - colocar a receita ali é o erro de implementação nº 1 e resulta em $0 de receita em todas as compras.

3. Sempre envie eventRevenueCurrency com eventRevenue quando a moeda não for USD - caso contrário, todos os valores serão registrados em USD.

4. Envie o valor real da transação única como um número simples: sem símbolos de moeda, sem centavos como unidades, sem duplicação entre total do carrinho e item, sem valor vitalício.

5. Para valores monetários que NÃO são receita realizada (valor de add-to-cart, valor de checkout-started, preço visualizado), NÃO defina eventRevenue. Coloque o valor em "af_price" e a moeda em "af_currency" dentro de eventValue. Enviar eventRevenue em af_initiated_checkout e em af_purchase faz a receita ser contabilizada em duplicidade.

6. Nas compras, inclua "af_order_id" (o ID da transação) dentro de eventValue. Se a base de código não tiver um ID de transação real nesse ponto, informe isso no plano de eventos em vez de substituir por um placeholder.

7. Inclua um "af_customer_event_id" exclusivo dentro de eventValue em todo evento de conversão. O mesmo nome de evento nunca deve disparar duas vezes com o mesmo ID — gere-o por ação e se proteja contra re-renderizações de SPA que disparem o handler duas vezes. Isso também elimina duplicações em relação a qualquer fluxo server-side (S2S) que envie as mesmas conversões.

8. Um evento por ação do usuário. Não emita dois nomes para a mesma ação e não retransmita a mesma ação pela AppsFlyer e por uma camada de encaminhamento com nomes diferentes.

9. Para carrinhos com vários itens, adicione um array "af_order_info" dentro de eventValue — um objeto por item com as chaves: sku, revenue (preço por unidade), qty, content_name, content_type, content_category, brand. Em uma compra, o eventRevenue de nível superior continua trazendo o total do pedido.

10. Os eventos devem disparar depois que o snippet do SDK tiver carregado na página. Para conversões que terminam em uma página de confirmação/agradecimento, dispare o evento no carregamento dessa página; para ações dentro da página (cliques em botões em uma SPA), dispare a partir do handler da ação.

11. Payloads enxutos - omita campos irrelevantes:\n\n    - NÃO inclua eventRevenue nem eventRevenueCurrency, a menos que o dinheiro realmente tenha mudado de mãos nesse evento. Nunca envie eventRevenue: 0 nem uma moeda padrão "só por garantia".

    - NÃO inclua eventCategory, eventLabel nem quaisquer campos no estilo de GA/Segment. Eles não fazem parte da API de eventos do SDK web da AppsFlyer.

    - Dentro de eventValue, omita as chaves cujos valores sejam string vazia, null, undefined ou false (a menos que o próprio valor false tenha significado para essa propriedade).

    - Se um parâmetro não for relevante para um evento específico, não o inclua no payload de forma alguma. Prefira um objeto mínimo, apenas com os campos aplicáveis.

    - Colunas vazias de receita/moeda nos relatórios da AppsFlyer não significam que o cliente deve enviar zeros ou valores padrão - deixe esses campos ausentes.

## Etapa 4 - Definir o Customer User ID (CUID)\n\nImediatamente após um usuário fazer login ou se cadastrar (e em carregamentos de página em que o usuário já esteja autenticado), chame:\n\nAF('pba', 'setCustomerUserId', '<o ID interno do usuário, como string>');\n\nRegras:\n\n- Use o MESMO identificador que os apps mobile passam para setCustomerUserId, se existirem apps mobile - é isso que conecta a jornada de um usuário entre web e mobile.

- Use um ID interno opaco. Nunca um endereço de e-mail, número de telefone ou outras PII.

- Chame isso o quanto antes - eventos disparados antes disso não levarão o CUID.

- setCustomerUserId, por si só, não cria um evento reportável. Também dispare af_complete_registration no cadastro e af_login no login, depois que o CUID for definido, para que esses eventos o incluam.

## Etapa 5 - Consentimento (somente se existir uma CMP)\n\nSe o site tiver uma plataforma de gerenciamento de consentimento:\n\n- Inicialize o SDK com a mensuração desativada: {pba: {webAppId: "<WEB_SDK_ID>", measurementStatus: false}}\n\n- Quando o consentimento for concedido: window.AF_SDK.PLUGINS.PBA.enableMeasurement()\n\n- Quando o consentimento for revogado: window.AF_SDK.PLUGINS.PBA.disableMeasurement()\n\nNotas:\n\n- Esses métodos do plugin só existem depois que o script do SDK termina de carregar, diferente de AF(), que é um stub de enfileiramento disponível imediatamente. Leve essa ordem em conta.

- Se a mensuração começar desativada, nenhuma visita será registrada até que o consentimento seja concedido. Deixe esse trade-off explícito antes de implementar isso.

Se não houver CMP, use o snippet simples (a mensuração vem ativada por padrão).

## Etapa 6 - Verificar

### 6a. Verificação local (durante a implementação)\n\nExecute o projeto, controle um navegador (Playwright/Puppeteer ou uma ferramenta de navegador, se você tiver uma) e capture TANTO o payload da solicitação QUANTO o status da resposta HTTP de cada chamada para domínios da AppsFlyer. Verifique:

- A solicitação do carregador do SDK retorna 200 e dispara exatamente uma vez por carregamento de página (navegue entre páginas e renderize novamente componentes para comprovar que não há carregamento duplo).

- Uma solicitação é disparada no carregamento da página com eventType "LOAD" e um afWebUserId preenchido, e sua resposta é 2xx - esta é a visita; sem isso, nada será atribuído.

- Cada conversão implementada produz exatamente uma solicitação de evento, cada uma retornando 2xx, com eventRevenue e eventRevenueCurrency no nível superior nas compras, e com af_customer_event_id presente e exclusivo.

- Depois de um login simulado, as solicitações subsequentes incluem o ID de usuário do cliente.

Uma solicitação capturada NÃO é prova de sucesso. Um evento cuja resposta seja 4xx foi rejeitado e nunca aparecerá nos relatórios. Reporte o código de status de cada evento que você dispara e nunca descreva um evento como verificado sem um.

Se você não conseguir executar um navegador, verifique estaticamente: o snippet tem um único ponto de inserção e não pode ser montado duas vezes; cada manipulador de evento dispara exatamente uma vez por ação; receita e currency são campos de nível superior; setCustomerUserId está acessível em todos os caminhos de entrada autenticados. Diga claramente que não foi possível observar nenhum status de resposta.

### 6b. Verificação pós-implantação no domínio real (obrigatória)

As execuções locais comprovam o caminho do código, não a página de produção. Pipelines de build e processadores de ativos podem remover, adiar ou realocar scripts inline, então verificar o arquivo-fonte não basta. Após a implantação:

- Busque a URL de produção e confirme que o snippet está presente no HTML SERVIDO.

- Carregue a página de produção em um navegador e repita nela todas as verificações de 6a.

- Confirme que o parâmetro de consulta af_id nas solicitações de saída carrega exatamente o ID do SDK web - um ID incorreto ou truncado significa que os eventos são enviados sob um ID que não existe na minha conta e, silenciosamente, não chegarão a lugar nenhum.

- Use um ID de usuário do cliente de QA dedicado (por exemplo, qa_<yyyymmdd>_01) para que a execução possa ser isolada nos dados brutos depois.

Se eu ainda não tiver implantado, diga que 6b ainda está pendente e me dê os comandos e as verificações exatos para executar quando eu fizer isso.

### 6c. Registro de QA

Produza uma tabela da execução de verificação para que as linhas possam ser associadas nos dados brutos da AppsFlyer depois, com uma linha por evento: timestamp em UTC, nome do evento, CUID, af_order_id, af_customer_event_id, status HTTP. Informe o horário de início e de término em UTC de toda a execução, e o horário da implantação em UTC, se você souber.

## Etapa 7 - Leitura dos dados

Inclua no relatório um guia explícito de como confirmar os eventos na AppsFlyer, porque visitas e conversões são tipos de registro diferentes e é fácil confundi-los:

- As visitas são registradas automaticamente e aparecem nos dados em nível de evento como linhas SESSION com nome de evento VAZIO e receita zero - esse é o esquema, não uma falha. Primeiras visitas e revisitas aparecem nos dados em nível de conversão (FIRST_VISIT / REVISIT), não como eventos nomeados. Uma exportação com escopo de sessões nunca pode conter eventos in-app, por mais correta que seja a implementação.

- As conversões implementadas aparecem como linhas separadas, com o nome do evento preenchido (af_purchase, af_login e assim por diante), com receita apenas nas linhas de compra.

- Quaisquer dados extraídos para uma janela de tempo ANTES da implantação não podem conter os novos eventos. Informe o horário UTC da implantação e diga para eu consultar somente depois disso. Ressalte que os campos de tempo de atribuição podem ser muito mais antigos do que o horário do evento e se referem a uma visita anterior, não a esta execução.

- Indique a latência esperada de relatórios e avise para eu não interpretar um relatório vazio dentro dessa janela como uma falha.

- Diga qual é o filtro exato a usar para encontrar a execução de QA de 6c (janela de tempo mais o QA CUID) e como é um resultado saudável.

- Se os eventos retornarem 2xx, mas ainda assim não aparecerem após a janela de latência, diga claramente que isso é um problema do lado da conta (evento não habilitado para o aplicativo web, escopo de relatórios ou acesso aos dados), e não um defeito no código, e liste o que devo verificar na interface do usuário da AppsFlyer.

## Output\n\nQuando terminar, me entregue:\n\n- Uma tabela de todos os eventos implementados: nome, local do gatilho (arquivo), tratamento da receita, ID de deduplicação.

- Onde o snippet foi instalado e como o carregamento único é garantido.

- Onde setCustomerUserId é chamado.

- A tabela de registros de QA da 6c e uma divisão clara entre o que você mesmo verificou (com status de resposta) e o que ainda fica como checklist manual de QA para mim (página a abrir, ação a realizar, solicitação e status esperados).

- O guia da etapa 7 para ler os dados de volta.

- Tudo o que você não conseguiu implementar ou precisa de mim (por exemplo, onde fica o ID do usuário, qual campo do valor da compra é o total final cobrado, qualquer fonte de valor que você tenha se recusado a supor).

Não implemente nada além da integração do SDK web da AppsFlyer descrita aqui.
```

</Accordion>

## 1. Receber suas chaves

**Obtenha o ID do Web SDK (também conhecido como Web Dev Key):**

1. No menu superior na plataforma da AppsFlyer, vá para **Configurações do aplicativo**.
2. No seletor de aplicativos, selecione seu aplicativo web (domínio do site com o prefixo "website-").
3. Em **Autenticação do SDK**, copie o **Web SDK ID**.

**Obtenha a chave do Smart Banner (se necessário):**

1. Na AppsFlyer, no menu lateral, acesse **Engajar**> **Web-to-app** > **Smart Banners**.
2. Copie a chave do Smart Banner necessária.

## 2. Selecionar um code snippet

Escolha o snippet que corresponde ao seu tipo de integração e requisitos de segurança. Duas opções estão disponíveis:

* [Web SDK padrão](#web-sdk-padrão): a integração padrão.
* [Verificação avançada de SDK](#verificação-avançada-de-sdk): uma integração aprimorada que inclui segurança da cadeia de suprimentos para o Web SDK. Use-a para adicionar uma camada extra de segurança contra comprometimento de CDN, sequestro de DNS e ataques intermediários (MiTM).

> ❗️ **Warning**
>
> Se você estiver fazendo a transição do Web SDK padrão para a verificação avançada do SDK, substitua o snippet existente pelo novo. O novo snippet não deve ser adicionado em conjunto com o snippet existente.

### Web SDK padrão

Use este snippet para implementar a integração do Web SDK padrão. Insira-o perto do topo da tag  em todas as páginas onde você deseja que o SDK seja carregado.

<Accordion title="Sem Smart Banners">

```html
<html>
<head>
    <script>
!function(t,e,n,s,a,c,i,o,p){t.AppsFlyerSdkObject=a,t.AF=t.AF||function(){
(t.AF.q=t.AF.q||[]).push([Date.now()].concat(Array.prototype.slice.call(arguments)))},
t.AF.id=t.AF.id||i,t.AF.plugins={},o=e.createElement(n),p=e.getElementsByTagName(n)[0],o.async=1,
o.src="https://websdk.appsflyersdk.com?"+(c.length>0?"st="+c.split(",").sort().join(",")+"&":"")+(i.length>0?"af_id="+i:""),
p.parentNode.insertBefore(o,p)}(window,document,"script",0,"AF","pba",{pba: {webAppId: "WEB_DEV_KEY"}})
    </script>
    <script>
        // Using the fetch API to send the user email to the server
        // and get the unique user id in return	
        window.onload = function () {
            var userEmail = localStorage.getItem('user_email');
            fetch('users/' + userEmail).then(function (res) {
                   res.text().then(function (id) {
                    console.log(id);
                    AF('pba', 'setCustomerUserId', id);
                });
            });
        }  </script> 
     </head> 
     <body> 
        <h1>Thank You for Signing Up!</h1> 
     </body> 
</html>
```

</Accordion>

<Accordion title="Com Smart Banners">

```html
<html>
<head>
    <script>
!function(t,e,n,s,a,c,i,o,p){t.AppsFlyerSdkObject=a,t.AF=t.AF||function(){
(t.AF.q=t.AF.q||[]).push([Date.now()].concat(Array.prototype.slice.call(arguments)))},
t.AF.id=t.AF.id||i,t.AF.plugins={},o=e.createElement(n),p=e.getElementsByTagName(n)[0],o.async=1,
o.src="https://websdk.appsflyersdk.com?"+(c.length>0?"st="+c.split(",").sort().join(",")+"&":"")+(i.length>0?"af_id="+i:""),
p.parentNode.insertBefore(o,p)}(window,document,"script",0,"AF","pba",{pba: {webAppId: "WEB_DEV_KEY"}})
    </script>
    <script>
        function storeUserEmail() {
            var userEmail = document.getElementById('email').value;
            localStorage.setItem('user_email', userEmail);
        }
    </script>
</head>
<body>
    <h1>Cadastre-se</h1>
    <form onsubmit="storeUserEmail()" action="/signup" method="post">
        <div><label>Nome</label><input type="text" name="name" id="name"></div>
        <br/>
        <div><label>E-mail</label><input type="email" name="email" id="email"></div>
        <br/>
        <input type="submit" id="submit">
    </form>
</body>
</html>
```

</Accordion>

### Verificação avançada de SDK

A verificação avançada de SDK adiciona segurança da cadeia de suprimentos ao Web SDK. Ela garante que o código executado nos navegadores dos seus usuários é exatamente o mesmo que a AppsFlyer publicou. O código-fonte do SDK em si é idêntico à integração padrão; apenas os mecanismos de entrega e verificação diferem.

A verificação avançada de SDK:

* Adiciona uma camada extra de segurança contra comprometimento de CDN, sequestro de DNS e ataques intermediários (MiTM).
* Adiciona aproximadamente 250ms ao tempo de carregamento do SDK.

Esse recurso é opcional. A integração padrão permanece totalmente disponível e é o padrão de mercado para analytics pixels de terceiros. A verificação avançada do SDK fornece uma camada adicional de proteção além do padrão.

Se o seu site impõe uma Política de Segurança de Conteúdo (CSP) usando nonce, consulte [Política de Segurança de Conteúdo (CSP)](#política-de-segurança-de-conteúdo-csp) em “Gerenciar privacidade” para acessar a variante nonce-extended do snippet.

<Accordion title="Sem Smart Banners">

```html
<script>
  // Queue — buffers AF() calls until the SDK is ready
  window. AppsFlyerSdkObject = "AF";
  window.AF = window.AF || function() {
    (window.AF.q = window.AF.q || []).push([Date.now()].concat(Array.prototype.slice.call(arguments)));
  };
  // Replace WEB_DEV_KEY with your Web SDK ID
  window.AF.id = window.AF.id || { pba: { webAppId: "WEB_DEV_KEY" } };
  window.AF.plugins = {};

  // Manifest loader config
  window.AF_LOADER_CONFIG = {
    baseUrl: "https://websdk.appsflyersdk.com",
    plugins: ["pba"]
  };

  // Inject manifest loader
  var loaderScript = document.createElement("script");
  loaderScript.src = "https://websdk.appsflyersdk.com/manifestLoader.v1.js";
  loaderScript.integrity = "sha384-Uncl2YwvjFpFz0PwEfl3bL/0JsOQcDFEpwXHzcN0MBavn9vvFEx5pZxADTq8h+CV";
  loaderScript.crossOrigin = "anonymous";
  loaderScript.async = true;
  document.head.appendChild(loaderScript);
</script>
```

</Accordion>

<Accordion title="Com Smart Banners">

```html
<script>
  // Queue — buffers AF() calls until the SDK is ready
  window. AppsFlyerSdkObject = "AF";
  window.AF = window.AF || function() {
    (window.AF.q = window.AF.q || []).push([Date.now()].concat(Array.prototype.slice.call(arguments)));
  };
  // Replace WEB_DEV_KEY with your Web SDK ID
  window.AF.id = window.AF.id || { pba: { webAppId: "WEB_DEV_KEY" }, banners: { key: "YOUR_BANNER_KEY" } };
  window.AF.plugins = {};

  // Manifest loader config
  window.AF_LOADER_CONFIG = {
    baseUrl: "https://websdk.appsflyersdk.com",
    plugins: ["banners", "pba"]
  };

  // Inject manifest loader
  var loaderScript = document.createElement("script");
  loaderScript.src = "https://websdk.appsflyersdk.com/manifestLoader.v1.js";
  loaderScript.integrity = "sha384-Uncl2YwvjFpFz0PwEfl3bL/0JsOQcDFEpwXHzcN0MBavn9vvFEx5pZxADTq8h+CV";
  loaderScript.crossOrigin = "anonymous";
  loaderScript.async = true;
  document.head.appendChild(loaderScript);
</script>
```

</Accordion>

## 3. Implementar o snippet

Implemente o snippet escolhido na Etapa 2 usando um dos seguintes métodos. Certifique-se de que o SDK seja carregado uma vez por cada página.

<Accordion title="Opção A: Adicionar diretamente ao seu site">

Repita os seguintes passos em todas as páginas:

1. No snippet da Etapa 2, substitua `WEB_DEV_KEY` (e, se aplicável, `YOUR_BANNER_KEY`) pelo ID do Web SDK.
2. Cole o snippet perto da parte superior da tag  do site.

</Accordion>

<Accordion title="Opção B: Implementar pelo Google Tag Manager (GTM)">

Certifique-se de que o SDK seja carregado uma vez por cada página e configure-o para carregar assim que a página abrir usando a prioridade do GTM.

1. Abra o Google Tag Manager.
2. Crie uma nova tag para o Web SDK da AppsFlyer.
3. Selecione o tipo de tag **HTML personalizado**.
4. Dê um nome significativo à etiqueta.
5. Cole o snippet da Etapa 2 em **Configuração de tags**.
6. Clique em **Guardar**.
7. Adicione um gatilho:
   * Para todas as páginas:
     1. Clique em **Adicionar gatilho**.
     2. Selecione **Todas as páginas**.
     3. Clique em **Guardar**.
     4. Insira um nome de tag e clique em **Salvar**.
   * Para páginas específicas:
     1. Clique em **Salvar tag**.
     2. Na janela principal do GTM, selecione **Gatilhos**. Clique em **Novo**.
     3. Clique no ícone de caneta.
     4. Escolha o tipo de gatilho **Visualização de página**.
     5. Selecione **Algumas visualizações de página**.
     6. Defina a página e as condições de gatilho conforme necessário.
     7. Clique em **Guardar**.
     8. Associe o gatilho à tag do Web SDK da AppsFlyer.
        1. Na janela principal do **GTM**, selecione **Gatilhos**.
        2. Selecione a etiqueta que criou anteriormente.
        3. No painel de gatilhos, clique no ícone de edição.
        4. Selecione o gatilho da visualização da página que criou anteriormente.
        5. Clique em **Guardar**.

> 📘 **Note**
>
> Os modelos personalizados do GTM não são compatíveis com a Verificação avançada de SDK, porque o ambiente em sandbox não permite definir o atributo integrity necessário para a verificação. Em vez disso, use o tipo de tag **HTML personalizado**.

</Accordion>

<Accordion title="Opção C: Implementar via Adobe Launch Tag Manager">

#### Crie uma propriedade no Adobe Experience Cloud

1. Acesse Adobe Experience Cloud > Inicialização.
2. Em Adobe Experience Cloud Launch, clique em **Ir para Inicialização**.
3. Clique em **Nova propriedade**.
4. Nomeie a propriedade.
5. Em **Plataforma**, selecione **Web**.
6. Insira o domínio do seu site.
7. Clique em **Guardar**.

#### Adicione o snippet à propriedade do Adobe Launch

1. Na página **Propriedade da minha web**, selecione a aba **Regras**.
2. Nomeie a regra. Recomenda-se carregar o Web SDK.
3. Na seção **IF**, em **Eventos**, clique em **Adicionar**.
   * Em **Tipo de evento**, selecione **Core - DOM Ready**.
   * Clique em **Manter alterações**.
4. Na seção **THEN**, em **Ações**, clique em **Adicionar** .
   * Em **Tipo de ação**, selecione **Código personalizado**.
   * Selecione **JavaScript** > **Abrir Editor** e cole o snippet da Etapa 2 (sem linhas extras).
   * Clique em **Manter alterações** para fechar o editor de código.
5. Clique em **Guardar**.

#### Adicione a tag Adobe Launch ao site

1. Na página **Propriedade da minha web**, selecione a aba **Ambientes** .
2. Encontre a linha com o ambiente no qual você deseja publicar (desenvolvimento ou produção).
3. Na coluna **Instalar**, clique no ícone de seleção na linha relevante.
4. Na caixa de diálogo **Instruções de instalação da web**, copie o snippet de código do script e feche a caixa de diálogo.
5. Cole o snippet de código na tag “head” do site.

#### Publicar o ambiente Adobe Launch

1. Na página **Propriedade da minha web**, acesse a aba **Publicação** .
2. Na seção  **Desenvolvimento**, clique em **Adicionar nova biblioteca**.
   * Dê um nome à biblioteca e escolha um ambiente.
   * Em **ALTERAÇÕES DE RECURSO**, clique em **Adicionar um recurso**.
   * Clique em **Regras** > **Carregar Web SDK** > **Mais recentes** > **Selecionar e criar uma nova revisão**.
   * Clique em **Guardar**.
3. Na seção **Desenvolvimento**:
   * Ao lado da biblioteca recém-criada, clique no menu Ação (3 pontos) > selecione **Construir para Desenvolvimento**.
   * Clique no menu de ação novamente > selecione **Enviar para aprovação**.
4. Na seção **Enviado**:
   * Clique no menu de ação > selecione **Construir para Staging**.
   * Clique novamente no menu de ação > selecione **Aprovar para publicação**.
5. Abaixo da seção **Aprovado**:
   * Clique no menu de ação e selecione **Criar e publicar em produção.**

</Accordion>

## 4. Verificar se o SDK está funcionando

Após a instalação, certifique-se de que o SDK está enviando solicitações ao conferir as chamadas de rede nas ferramentas de desenvolvedor do navegador.

[<Image alt="DevTools screenshot" src="https://files.readme.io/a1bb1f22e9d30059830239e7a4d13d7cde106a3363502cb9e8a054d6e8d65dff-43492318562833.png" width="1015px" />](https://files.readme.io/a1bb1f22e9d30059830239e7a4d13d7cde106a3363502cb9e8a054d6e8d65dff-43492318562833.png)

**Para verificar se o SDK está funcionando, siga estes passos:**

1. Abra o site.
2. Abra as ferramentas de desenvolvimento do navegador.
3. Vá para a aba (A) **Rede**.
4. Atualize a página.
5. Filtre por (B) `appsflyer`. Filtre por duas solicitações:
   * **Carregador do SDK**: URL da solicitação começa com `https://websdk.appsflyersdk.com`. Isso confirma que o script do SDK foi carregado corretamente.
   * **Dados de evento**: URL da solicitação começa com `https://wa.appsflyer.com/events`. Isso confirma que o SDK está enviando dados de evento para a AppsFlyer.
6. Selecione a mensagem **eventos** (C): a chamada `wa.appsflyer.com`.
7. Sob os headers, verifique (D):
   * O URL da solicitação começa com `https://wa.appsflyer.com/events?site-id=`.
   * Parâmetro de consulta `site_id` = `WEB_DEV_KEY`.
   * O código de status é 200.
8. Verifique se `site_id` corresponde a `WEB_DEV_KEY` na AppsFlyer > menu superior > **Meus aplicativos**.
9. Certifique-se de que o SDK seja carregado apenas uma vez. O carregamento múltiplo do SDK pode fazer com que ele pare de funcionar.

> 📘 **Note**
>
> Para uma forma visual e em tempo real de confirmar a instalação do seu SDK web e validar se seus eventos são disparados corretamente, use a página de teste do SDK web.

## 5. Configurar e gravar eventos

Depois de inicializar o Web SDK, você deixa de mensurar visitas básicas para capturar ações específicas do usuário. Nessa seção, você aprenderá como configurar e gravar eventos personalizados, como compras ou cadastros, usando **JavaScript nativo** ou **Google Tag Manager**.

<Accordion title="Configurar eventos">

Os eventos são fundamentais para a mensuração da web, representando ações específicas do usuário que geram valor para o seu negócio. Para registrar essas interações, você precisa definir a lógica e os parâmetros para cada evento, garantindo que os parâmetros corretos, como receita e metadados personalizados, sejam enviados para a plataforma da AppsFlyer.

**Exemplo de evento: evento de compra com receita associada**

```javascript
AF('pba', 'event', {eventType: 'EVENT', eventName: 'purchase', eventRevenue: 12, eventValue: {"key1": 123, "key2": "name", "af_customer_event_id": "evt-abc-001"}});
```

<div id="web-sdk-event-parameters-table" />

<Accordion title="Tabela de parâmetros de eventos do Web SDK">

| Nome do parâmetro | Obrigatoriedade | Visão geral |
| --- | --- | --- |
| `eventType` | Sim | Tipo de evento. Formato: string. Sempre preencha esse parâmetro com `EVENT`. Exemplo: `eventType: "EVENT"` |
| `eventName` | Sim | Nome do evento. Formato: string. Exemplo: Compra, Assinatura |
| `eventRevenue` | Retargeting | Receita atribuída a um evento de conversão. Formato: Float |
| `eventRevenueCurrency` | Retargeting | Moeda da receita. Código de moeda ISO 4217 de 3 caracteres. Padrão: USD. Formato: Sequência de caracteres |
| `Valor do evento` | Retargeting | Mapa de parâmetros da descrição de eventos. Use esse parâmetro para enviar eventos in-app avançados como SKU do produto e preço do item. Formato: JSON. Exemplo: `{"sku": "ABC123", "color": "blue", "unit_price": 3.99, "currency": "USD"}` Limite: 3000 caracteres (truncado se excedido). |

</Accordion>

</Accordion>

<Accordion title="Registrar eventos no carregamento da página">

Essa é a abordagem padrão para conversões que terminam com um redirecionamento, como uma página de confirmação ou **agradecimento**.

Você pode implementar esse gatilho com um método de carregamento de janela ao seu **JavaScript nativo** ou com um gatilho de visualização de página no **Google Tag Manager**.

> 🚧 **Important**
>
> Os exemplos de código abaixo são para fins ilustrativos. **Não use o código original**. Adapte-o à estrutura específica do seu site.

<div id="example-record-event-via-af-web-sdk" />

<Accordion title="Exemplo: Gravação de eventos via Web SDK da AppsFlyer">

Essa abordagem é ideal para gravar conversões que ocorrem através de redirecionamentos, como uma página de agradecimento para uma assinatura de newsletter.

**Caso de uso**: Um usuário assina uma newsletter e é redirecionado para uma página de confirmação. Você deve registrar o evento de assinatura assim que a página estiver visível.

**Exemplo de carregamento nativo de página:**

```javascript
window.onload = function(){
  AF('pba', 'event', {eventType: 'EVENT', eventValue: {'category': 'holiday_promotion'}, eventName: 'subscription'});
}
```

**Como funciona**

1. A página carrega o conteúdo necessário.
2. Depois do carregamento completo da janela (`window.onload`), o script chama automaticamente o método `AF()`.
3. O evento de **assinatura**, juntamente com os metadados associados (categoria e rótulo), é enviado diretamente para a AppsFlyer.

</Accordion>

<div id="example-record-event-via-gtm" />

<Accordion title="Exemplo: Gravação de eventos via GTM">

Essa abordagem é usada para registrar conversões bem-sucedidas, como uma assinatura de newsletter, disparando uma tag no carregamento de uma página de agradecimento.

#### 1. Crie uma página de agradecimento

A estrutura de HTML carrega o GTM que, por sua vez, carrega o Web SDK. Ela também mostra como os dados podem ser disponibilizados ao GTM através de funções ou `localStorage`.

```html
<html>\n<head>\n    <script>\n        // Google Tag Manager carrega o SDK web\n        (function(w,d,s,l,i){w[l]=w[l]||[];w[l].push({'gtm.start':\n        new Date().getTime(),event:'gtm.js'});var f=d.getElementsByTagName(s)[0],\n        j=d.createElement(s),dl=l!='dataLayer'?'&l='+l:'';j.async=true;j.src=\n        'https://www.googletagmanager.com/gtm.js?id='+i+dl;f.parentNode.insertBefore(j,f);\n        })(window,document,'script','dataLayer','GTM-XXXX');\n    </script>\n    <script>\n        function getResponseFromServer() {\n            return JSON.stringify({ action: 'subscribe', category: 'site actions', label: userEmail })\n        }\n        localStorage.setItem('data', JSON.stringify({ action: 'subscribe', category: 'site actions', label: 'user@email.com' }));\n    </script>\n</head>\n<body>\n    <h1>Obrigado por se inscrever em nossa newsletter</h1>\n</body>\n</html>
```

#### 2. Configure a tag do GTM

1. Crie uma nova tag no GTM e selecione o tipo de tag **HTML personalizado**.
2. Dê um nome diferente (exemplo: "Evento de assinatura da AppsFlyer").
3. Cole o seguinte script na área de texto HTML:

   ```javascript
   AF('pba', 'event', {eventType: 'EVENT', eventValue: {'category' : 'holiday_promotion'}, eventName: 'subscription'});
   ```
4. Abra **Configurações avançadas** > **Sequenciamento de tags**. Certifique-se de que está configurado para disparar após a tag de inicialização principal do Web SDK.
5. Defina um gatilho para que a tag seja ativada na **visualização de página** da página de agradecimento.

</Accordion>

</Accordion>

<Accordion title="Registrar eventos na interação do usuário">

Use isto para medir ações sem recarregar a página (cliques em botões, downloads, adicionar ao carrinho).

Essas interações costumam ser gerenciadas por meio de um ouvinte de clique a um **elemento HTML nativo** ou através de variáveis do **Google Tag Manager** para identificar e mensurar IDs de elementos específicos ou seletores CSS.

> 🚧 **Important**
>
> Os exemplos de código abaixo são para fins ilustrativos. **Não use o código original**. Adapte-o à estrutura específica do seu site.

<div id="example-record-event-via-af-web-sdk-interaction" />

<Accordion title="Exemplo: Gravação de eventos via Web SDK da AppsFlyer">

Use este método para mensurar ações específicas que os usuários realizam em uma página, como clicar em um botão de **Checkout** ou **Download**.

**Caso de uso**: Você opera um site de eCommerce e deseja capturar um evento de **checkout** no momento em que um usuário clica no botão **Checkout** no carrinho de compras.

**Exemplo de interação de usuário nativo:**

```html
<html>
<head>
    <script>
        window.onload = function () {
            document.getElementById('checkout').addEventListener('click', function () {
                AF('pba', 'event', {eventType: 'EVENT', eventValue: {'category' : 'holiday_promotion'}, eventName: 'checkout'});
            });
        }
    </script>
</head>
<body>
    <h1>Carrinho de compras</h1>
    <button id='checkout'>Checkout</button>
</body>
</html>
```

**Como funciona**

1. Quando a página é carregada, o script anexa um ouvinte de **clique** ao elemento com a ID `checkout`.
2. Quando o usuário clica no botão de checkout, a função de callback é ativada.
3. A função pode recuperar dados relevantes (de `localStorage`, por exemplo) e enviá-los para o método de `AF()`.
4. Em seguida, o SDK envia o evento de **checkout** para a plataforma da AppsFlyer.

</Accordion>

<div id="example-record-event-via-gtm-interaction" />

<Accordion title="Exemplo: Gravação de eventos via GTM">

Esse método captura ações específicas, como clicar em um botão de **checkout**, usando as variáveis e os gatilhos integrados do GTM.

#### 1. Configure uma página de checkout

```html
<html>
<head>
    <script>
        (function(w,d,s,l,i){w[l]=w[l]||[];w[l].push({'gtm.start':
        new Date().getTime(),event:'gtm.js'});var f=d.getElementsByTagName(s)[0],
        j=d.createElement(s),dl=l!='dataLayer'?'&l='+l:'';j.async=true;j.src=
        'https://www.googletagmanager.com/gtm.js?id='+i+dl;f.parentNode.insertBefore(j,f);
        })(window,document,'script','dataLayer','GTM-XXXX');
    </script>
</head>
<body>
    <h1>Carrinho de compras</h1>
    <button id='checkout'>Checkout</button>
</body>
</html>
```

#### 2. Configure variáveis e gatilhos no GTM

1. No GTM, clique em **Variáveis** > **Configurar** e ative **Elementos de clique** na lista de variáveis incorporadas.
2. Crie uma nova variável definida pelo usuário (tipo: **Todos os elementos**).
3. Crie um novo **gatilho**:
   * Tipo de gatilho: **Clique - Todos os elementos**.
   * Esse gatilho dispara em: **Alguns cliques**.
   * Condição: **Elementos de clique** corresponde ao seletor CSS `#checkout`.

#### 3. Crie a tag de interação

1. Crie uma nova tag **HTML personalizado** para a ação do checkout.
2. Cole o script de interação:

   ```html
   <script>
     AF('pba', 'event', {eventType: 'EVENT', eventValue: {'category' : 'holiday_promotion'}, eventName: 'checkout'});
   </script>
   ```
3. Atribua o gatilho "clique do checkout" criado ne etapa anterior.

</Accordion>

</Accordion>

<Accordion title="Práticas recomendadas para a implementação de eventos">

Para garantir a precisão dos dados e um envio bem-sucedido, lembre-se destes requisitos técnicos:

* **Ordem de carregamento**: Verifique se a tag de funções do Web SDK está totalmente carregada antes de fazer chamadas de evento.
* **Formatação de dados:** Não inclua caracteres especiais nos valores de eventos. Exemplo: use valores numéricos para receita em vez de símbolos de moeda (use `10.50` em vez de `$10.50`).
* **Limites de string:** Mantenha suas strings `eventValue` concisas; valores com mais de 3000 caracteres serão truncados.
* **Desduplicação de evento:** Recomendamos enviar `af_customer_event_id` em `eventValue`, com um valor único por evento. Isso é ainda mais importante quando você envia o mesmo evento tanto pelo SDK web quanto pela API Server-to-Server (S2S). A AppsFlyer encaminha esse valor para a ad network, que o usa para desduplicar o evento do lado do servidor que ela recebe da AppsFlyer em relação ao mesmo evento recebido do próprio pixel.
* **Posicionamento da receita:** Preencha `eventRevenue` apenas em eventos em que houve movimentação real de dinheiro, como uma compra ou uma assinatura confirmada. Para eventos que têm um valor monetário, mas não representam receita realizada (por exemplo, adicionar ao carrinho, checkout iniciado ou visualização de conteúdo), use af\_price e af\_currency em eventValue. Enviar `eventRevenue` tanto no checkout quanto na compra faz a receita ser contabilizada em dobro em todos os relatórios.
* **Nomenclatura de evento:** Não adicione sufixos de plataforma, como `_web`, aos nomes dos eventos. A plataforma já é uma dimensão no dashboard e nos dados brutos. Use os mesmos nomes de eventos do seu app mobile para manter os relatórios entre plataformas unificados.

</Accordion>

## 6. Definir o Customer User ID

Após implementar a mensuração de eventos, configure uma identidade para vincular a atividade web com outras plataformas (mobile, PC, CTV). Use `setCustomerUserId` para obter uma visão unificada da jornada do usuário entre as plataformas.

**Regras principais**

* **Consistência:** Use o mesmo valor de CUID das suas implementações de apps mobile (ver `setCustomerUserId` mobile para: <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/integrate-ios-sdk">iOS</Anchor>, <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/integrate-android-sdk#setting-the-customer-user-id">Android</Anchor>, <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/basicintegration#set-customer-user-id">Unity</Anchor>).
* **Tempo**: Você pode enviar o CUID em qualquer fase (após o login ou cadastro, por exemplo). Defina o CUID assim que tiver acesso a ele. Na maioria das vezes, isso significa que é necessário esperar que o usuário se identifique através do login ou do cadastro.
* **Sintaxe**: Envie o valor como uma string (entre aspas). **Exemplo:** `AF('pba', 'setCustomerUserId', '663274')`
* **Privacidade**: Não inclua informações pessoais identificáveis (PII), como endereços de e-mail ou números de telefone.

<Accordion title="Exemplo: Configurando o CUID após o cadastro (nativo)">

O código fornecido nestes exemplos é apenas para referência. Não use este código tal como está. Se você não tiver certeza de como usar este código, consulte o seu desenvolvedor Web.

Pressuposto: O Web SDK é carregado na página antes do evento ser enviado. Não o carregue novamente.

Cenário do usuário:

* Um usuário faz o cadastro no seu site.
* O código do site recolhe os dados do usuário e os envia ao seu servidor.
* O servidor gera um CUID único para o usuário.
* Na página de agradecimento após o cadastro, você consulta o servidor para obter o novo CUID.
* Com a resposta do servidor, você define o CUID da AppsFlyer usando o método `setCustomerUserId()` do Web SDK.

#### Um exemplo de formulário de cadastro

O código abaixo é um formulário de cadastro simples. Quando o formulário é enviado, o endereço de e-mail é armazenado em `localStorage`. Quando o usuário chega à página de agradecimento, o endereço de e-mail é enviado para o servidor que obtém o CUID único para esse e-mail.

```html
<html>
<head>
    <script>
!function(t,e,n,s,a,c,i,o,p){t.AppsFlyerSdkObject=a,t.AF=t.AF||function(){
(t.AF.q=t.AF.q||[]).push([Date.now()].concat(Array.prototype.slice.call(arguments)))},
t.AF.id=t.AF.id||i,t.AF.plugins={},o=e.createElement(n),p=e.getElementsByTagName(n)[0],o.async=1,
o.src="https://websdk.appsflyersdk.com?"+(c.length>0?"st="+c.split(",").sort().join(",")+"&":"")+(i.length>0?"af_id="+i:""),
p.parentNode.insertBefore(o,p)}(window,document,"script",0,"AF","pba",{pba: {webAppId: "WEB_DEV_KEY"}})
    </script>
    <script>
        function storeUserEmail() {
            var userEmail = document.getElementById('email').value;
            localStorage.setItem('user_email', userEmail);
        }
    </script>
</head>
<body>
    <h1>Cadastre-se</h1>
    <form onsubmit="storeUserEmail()" action="/signup" method="post">
        <div><label>Nome</label><input type="text" name="name" id="name"></div>
        <br/>
        <div><label>E-mail</label><input type="email" name="email" id="email"></div>
        <br/>
        <input type="submit" id="submit">
    </form>
</body>
</html>
```

#### Um exemplo de página de agradecimento

O código usa a Fetch API. Ele envia ao servidor o endereço de e-mail inserido pelo usuário. Considerando que o servidor crie um usuário com um CUID único no cadastro, enviar o endereço de e-mail para o servidor retornará um CUID único. O servidor responde com um CUID único, que é enviado com o método`setCustomerUserId`.

```html
<script>
  // Queue — buffers AF() calls until the SDK is ready
  window. AppsFlyerSdkObject = "AF";
  window.AF = window.AF || function() {
    (window.AF.q = window.AF.q || []).push([Date.now()].concat(Array.prototype.slice.call(arguments)));
  };
  // Replace WEB_DEV_KEY with your Web SDK ID
  window.AF.id = window.AF.id || { pba: { webAppId: "WEB_DEV_KEY" }, banners: { key: "YOUR_BANNER_KEY" } };
  window.AF.plugins = {};

  // Inject SDK
  var o = document.createElement("script"),
      p = document.getElementsByTagName("script")[0];
  o.async = 1;
  // Replace WEB_DEV_KEY with your Web SDK ID
  o.src = "https://websdk.appsflyersdk.com?" + "st=pba,banners&af_id=WEB_DEV_KEY";
  p.parentNode.insertBefore(o, p);
  AF('banners', 'showBanner');
</script>
```

</Accordion>

<Accordion title="Exemplo: Configurando o CUID após o cadastro (Google Tag Manager)">

1. Crie uma página de cadastro.

   O exemplo de código abaixo é um formulário de cadastro simples. Quando o formulário é enviado, o endereço de e-mail é armazenado em `localStorage`. Quando o usuário chega à página de agradecimento, o endereço de e-mail é enviado para o servidor que obtém o CUID único para esse e-mail.

   ```html
   <html>
   <head>
       <script>
           (function (w, d, s, l, i) {
               w[l] = w[l] || []; w[l].push({ 'gtm.start': new Date().getTime(), event: 'gtm.js' });
               var f = d.getElementsByTagName(s)[0], j = d.createElement(s),
                   dl = l != 'dataLayer' ? '&l=' + l : ''; j.async = true;
               j.src = 'https://www.googletagmanager.com/gtm.js?id=' + i + dl;
               f.parentNode.insertBefore(j, f);
           })(window, document, 'script', 'dataLayer', 'GTM-5VJ6C7R');
           function storeUserEmail() {
               var userEmail = document.getElementById('email').value;
               localStorage.setItem('user_email', userEmail);
           }
       </script>
   </head>
   <body>
       <h1>Cadastre-se</h1>
       <form onsubmit="storeUserEmail()" action="/signup" method="post">
           <div><label>Nome</label><input type="text" name="name" id="name"></div>
           <br />
           <div><label>E-mail</label><input type="email" name="email" id="email"></div>
           <br />
           <input type="submit" id="submit">
       </form>
   </body>
   </html>
   ```
2. Configure uma página de agradecimento para os usuários que fazem o cadastro. O código abaixo é uma página de agradecimento com um gatilho do GTM que envia o endereço de e-mail fornecido pelo usuário ao servidor no formulário de cadastro. Considerando que o servidor crie um usuário com um CUID único no cadastro, enviar o endereço de e-mail para o servidor retornará um CUID único. O servidor responde com um CUID exclusivo que é enviado usando o método `setCustomerUserId()`.

   ```html
   <script>
       window.onload = function () {
           var userEmail = localStorage.getItem('user_email');
           fetch('users/' + userEmail).then(function (res) {
               res.text().then(function (id) {
                   console.log(id);
                   AF('pba', 'setCustomerUserId', id);
               });
           });
       }
   </script>
   ```
3. Adicione uma nova tag para atribuir assinaturas após o carregamento da página de agradecimento.

   [![Adição de uma nova tag do GTM para o evento de conversão de CUID](https://files.readme.io/c85a3cbc6c9675e4bfa762ff0a9930d58b1e02b13f147342a11b433e1d211b11-360002750309.png)](https://files.readme.io/c85a3cbc6c9675e4bfa762ff0a9930d58b1e02b13f147342a11b433e1d211b11-360002750309.png)
4. Dê um nome diferente à tag e selecione a opção de tipo de tag **HTML personalizado**.

   [![Nomeação da tag e seleção do tipo de tag HTML personalizado no GTM](https://files.readme.io/beab3305bc50c44c291997fa9b77bf4df7dd5dd9207a1bf766c2e1702e314d2c-360016246418.jpg)](https://files.readme.io/beab3305bc50c44c291997fa9b77bf4df7dd5dd9207a1bf766c2e1702e314d2c-360016246418.jpg)

   ```html
   <script>
       var userEmail = localStorage.getItem('user_email');
       fetch('users/' + userEmail).then(function (res) {
           res.text().then(function (id) {
               console.log(id);
               AF('pba', 'setCustomerUserId', id);
           });
       });
   </script>
   ```
5. Abra **Configurações avançadas** e **Sequenciamento de tags** e certifique-se de que está configurado para disparar a conversão após a execução da tag.

   [![Configuração do sequenciamento de tags do GTM para a tag de conversão](https://files.readme.io/67ab225ab5ddfe97da782fe6a0d659b609d930d3cd5e2b4478a19c250968f676-360002902065.png)](https://files.readme.io/67ab225ab5ddfe97da782fe6a0d659b609d930d3cd5e2b4478a19c250968f676-360002902065.png)
6. Defina um gatilho para a tag de conversão para indicar quando deve ser acionada. No exemplo abaixo, ela é acionada no carregamento da página de agradecimento.

   [![Configuração do gatilho do GTM para disparar a tag de conversão ao carregar a página de agradecimento](https://files.readme.io/25fd3944971abc811cbe6192cec8c73bb31b3b3c3715a1b8918a71d7f8bf72b1-360002902185.png)](https://files.readme.io/25fd3944971abc811cbe6192cec8c73bb31b3b3c3715a1b8918a71d7f8bf72b1-360002902185.png)

</Accordion>

## 7. Gerenciar a privacidade

Após implementar a mensuração de eventos, talvez você precise aplicar restrições de segurança e privacidade específicas para atender aos padrões da sua empresa ou região.

<Accordion title="Opt-in ou opt-out do envio de eventos">

Você pode controlar a mensuração de duas maneiras:

#### Definição do estado inicial do SDK (no snippet)

Determina se o SDK envia eventos quando a página da web carrega pela primeira vez ou espera até que você peça para que ele envie os eventos. Essa configuração é definida no snippet da web.

* Envie eventos: `{pba: {webAppId: "...", measurementStatus:true}}`
* Não envie eventos: `{pba: {webAppId: "...", measurementStatus:false}}`

> 📘 **Note**
>
> Se measurementStatus estiver vazio ou NULL, a AppsFlyer considera como se measurementStatus:true.

#### Controle explícito

O controle explícito tem prioridade sobre a configuração de estado inicial e usa cookies first-party:

* Definido no domínio do site.
* Expira após um período definido pelo Web SDK ou conforme determinado pelo navegador.
* Sempre sujeito às configurações de cookies do navegador.

**Comandos**

* Comece a enviar eventos (opt-in): `window.AF_SDK.PLUGINS.PBA.enableMeasurement()`
* Pare de enviar eventos (opt-out): `window.AF_SDK.PLUGINS.PBA.disableMeasurement()`

</Accordion>

<Accordion title="Proteção e filtro de dados">

e o seu site exige protocolos rigorosos de segurança e de privacidade de dados, use os seguintes mecanismos para configurar a maneira como o Web SDK interage com seu ambiente e seus dados.

#### Política de Segurança de Conteúdo (CSP)

Se o seu site exige que o JavaScript seja protegido por uma CSP, o Web SDK é compatível com duas abordagens diferentes, a depender da configuração da sua CSP e do snippet selecionado na Etapa 2.

* **CSP usando self**: Adicione `https://websdk.appsflyersdk.com` à sua lista de permissões `script-src`. Isso funciona tanto para o Web SDK padrão quanto para a verificação avançada do SDK.
* **CSP usando nonce**: Se sua política usar `script-src 'nonce-...'`, use a variante once-extended da derificação avançada do SDK. Esse mecanismo encaminha o nonce para todas as três tags de script exigidas pelo processo de verificação. Substitua `{{CSP_NONCE}}` pelo valor nonce gerado pelo servidor.

A tabela abaixo mostra quais políticas CSP são compatíveis com a variante nonce-extended.

| Política | Funciona? | Observações |
| --- | --- | --- |
| `script-src 'self'` | Retargeting | Origem de CDN externa não permitida; script inline também é bloqueado. |
| `script-src 'self' https://websdk.appsflyersdk.com` | Parcial | Permite carregador e SDK, mas o script de configuração inline ainda está bloqueado. |
| `script-src 'nonce-...' https://websdk.appsflyersdk.com` | Sim | Nonce cobre script inline e carregador; a tag SDK recebe nonce encaminhado pelo carregador. |
| `script-src 'nonce-...' 'strict-dynamic'` | Sim (recomendado) | Nonce cobre script inline e carregador; `strict-dynamic` propaga confiança para a tag SDK inserida dinamicamente. Nenhuma origem de CDN necessária na lista de permissões. |

Compatibilidade com a política CSP

#### Verificação avançada de SDK com snippets de nonce CSP

<div id="nonce-without-smart-banners" />

<Accordion title="Sem Smart Banners">

```html
<script nonce="{{CSP_NONCE}}">
  // Queue — buffers AF() calls until the SDK is ready
  window. AppsFlyerSdkObject = "AF";
  window.AF = window.AF || function() {
    (window.AF.q = window.AF.q || []).push([Date.now()].concat(Array.prototype.slice.call(arguments)));
  };
  // Replace WEB_DEV_KEY with your Web SDK ID
  window.AF.id = window.AF.id || { pba: { webAppId: "WEB_DEV_KEY" } };
  window.AF.plugins = {};

  // Manifest loader config — nonce forwarded to the injected SDK <script> tag
  window.AF_LOADER_CONFIG = {
    baseUrl: "https://websdk.appsflyersdk.com",
    plugins: ["pba"],
    nonce: "{{CSP_NONCE}}"
  };

  // Inject manifest loader
  var loaderScript = document.createElement("script");
  loaderScript.src = "https://websdk.appsflyersdk.com/manifestLoader.v1.js";
  loaderScript.integrity = "sha384-Uncl2YwvjFpFz0PwEfl3bL/0JsOQcDFEpwXHzcN0MBavn9vvFEx5pZxADTq8h+CV";
  loaderScript.crossOrigin = "anonymous";
  loaderScript.nonce = "{{CSP_NONCE}}";
  loaderScript.async = true;
  document.head.appendChild(loaderScript);
</script>
```

</Accordion>

<div id="nonce-with-smart-banners" />

<Accordion title="Com Smart Banners">

```html
<script nonce="{{CSP_NONCE}}">
  // Queue — buffers AF() calls until the SDK is ready
  window. AppsFlyerSdkObject = "AF";
  window.AF = window.AF || function() {
    (window.AF.q = window.AF.q || []).push([Date.now()].concat(Array.prototype.slice.call(arguments)));
  };
  // Replace WEB_DEV_KEY with your Web SDK ID
  window.AF.id = window.AF.id || { pba: { webAppId: "WEB_DEV_KEY" }, banners: { key: "YOUR_BANNER_KEY" } };
  window.AF.plugins = {};

  // Manifest loader config — nonce forwarded to the injected SDK <script> tag
  window.AF_LOADER_CONFIG = {
    baseUrl: "https://websdk.appsflyersdk.com",
    plugins: ["banners", "pba"],
    nonce: "{{CSP_NONCE}}"
  };

  // Inject manifest loader
  var loaderScript = document.createElement("script");
  loaderScript.src = "https://websdk.appsflyersdk.com/manifestLoader.v1.js";
  loaderScript.integrity = "sha384-Uncl2YwvjFpFz0PwEfl3bL/0JsOQcDFEpwXHzcN0MBavn9vvFEx5pZxADTq8h+CV";
  loaderScript.crossOrigin = "anonymous";
  loaderScript.nonce = "{{CSP_NONCE}}";
  loaderScript.async = true;
  document.head.appendChild(loaderScript);
</script>
```

</Accordion>

#### Descartar parâmetros de consulta

Se os parâmetros de consulta de URL contêm informações confidenciais, peça à AppsFlyer para descartá-las (URLs, referrers e `header_referer`).

* Descarregue **todos** os parâmetros de consulta: anexar `af_url=true`
* Descarte os parâmetros **específicos**: use `af_url_mask=param` (separar múltiplos parâmetros com `;`)

Nome do imposto sobre a receita líquida

* Original: `param1=value1&param2=value2&param3=value3&af_url_mask=param2;param3`
* Resultado: `param1=value1&af_url_mask=param2;param3`

</Accordion>

## Referência de cookies do Web SDK

O Web SDK define ou utiliza os seguintes cookies:

| Nome do cookie | Domínio | Duração | Quando usado | Atenção |
| --- | --- | --- | --- | --- |
| afUserid | Domínio do seu site | 395 dias | Non-Accelerated Mobile Pages (páginas não aceleradas para dispositivos mobile) | Identifica um usuário no contexto de eventos de carregamento de páginas da web e navegação. |
| AF\_SYNC | Domínio do seu site | 1 semana | Non-Accelerated Mobile Pages (páginas não aceleradas para dispositivos mobile) | Sinaliza que um identificador de usuário final está definido. É usado para reduzir o tempo de carregamento do site. |
| af\_id | <Anchor target="_blank" href="http://appsflyer.com/">appsflyer.com</Anchor> | 395 dias | Páginas não-AMP quando cookies de terceiros são permitidos | Identifica um usuário no contexto de eventos de inicialização de aplicativo e navegação. |
| af\_id | <Anchor target="_blank" href="http://onelink.me/">onelink.me</Anchor> | 395 dias | Páginas não-AMP quando cookies de terceiros são permitidos | Vincule interações de banner, interações do OneLink, ou ambas, a eventos de inicialização de aplicativos. |
| amp-afUserid | AMP CDN ou domínio do seu site | 1 ano | Páginas AMP (accelerated mobile pages) |  |
| AF\_DEFAULT\_MEASUREMENT\_STATUS | Domínio do seu site | 395 dias | Non-Accelerated Mobile Pages (páginas não aceleradas para dispositivos mobile) | Armazena o estado de consentimento. Impede que o SDK funcione até que o usuário autorize. Não definido por padrão. Usado apenas quando o <Anchor target="_blank" href="/marketers/pt/docs/pba-web-sdk-integration-guide#sending-events-optinoptout">gating de consentimento</Anchor> está configurado. |

<div data-zendesk-anchors="overview=vis%C3%A3o-geral h_01KGJCGCPZDJ446QHW80H9Z4C3=vis%C3%A3o-geral h_01M11M9ZXB0PFFPKVDCGVD0RFT=integre-o-sdk-manualmente ai-prompt=integre-o-sdk-com-um-agente-de-codifica%C3%A7%C3%A3o-de-ia h_01UJZDE8GXD6NCF10EPF91DH=integre-o-sdk-com-um-agente-de-codifica%C3%A7%C3%A3o-de-ia step-1-obtain-your-keys=1-receber-suas-chaves h_01KP11XJV8B56W7FK2KAAFH0NE=1-receber-suas-chaves step-2-select-a-code-snippet=2-selecionar-um-code-snippet h_01KP11XJV8RDV378GMFF0DVZ8V=2-selecionar-um-code-snippet standard=web-sdk-padr%C3%A3o h_01KP11XJV8MN64YV17D1M0T5B9=web-sdk-padr%C3%A3o advanced-sdk-verification=verifica%C3%A7%C3%A3o-avan%C3%A7ada-de-sdk h_01KP11XJV8ZGF4SDXJH6FKX18E=verifica%C3%A7%C3%A3o-avan%C3%A7ada-de-sdk step-3-deploy-the-snippet=3-implementar-o-snippet h_01KP11XJV8JQ5S2BBS18RV2H2R=3-implementar-o-snippet create-a-property-in-adobe-experience-cloud=crie-uma-propriedade-no-adobe-experience-cloud h_01KP11XJV9RWY4TTWACW69YGJH=crie-uma-propriedade-no-adobe-experience-cloud add-the-snippet-to-the-adobe-launch-property=adicione-o-snippet-%C3%A0-propriedade-do-adobe-launch h_01KP11XJV9ZHMP9M85S3KG0V6R=adicione-o-snippet-%C3%A0-propriedade-do-adobe-launch add-the-adobe-launch-tag-to-the-website=adicione-a-tag-adobe-launch-ao-site h_01KP11XJVBV5J9E0HV5DM9HS7B=adicione-a-tag-adobe-launch-ao-site publish-the-adobe-launch-environment=publicar-o-ambiente-adobe-launch h_01KP11XJVB0Y4RCBS9QCFBAKRD=publicar-o-ambiente-adobe-launch 2-make-sure-the-sdk-is-working=4-verificar-se-o-sdk-est%C3%A1-funcionando h_01KGJCGCPZ38XZAY8SXB48YWBD=4-verificar-se-o-sdk-est%C3%A1-funcionando 3-set-and-record-events=5-configurar-e-gravar-eventos h_01KGJCGCPZMPX1FH58MVGM9VQS=5-configurar-e-gravar-eventos h_01KP3CJBZXV66CCP4N0482DG1N=web-sdk-event-parameters-table h_01KP3CJBZXB328CABH2QCRXTHX=example-record-event-via-af-web-sdk h_01KP3CJBZXM3WK0JYB6S8P6SMQ=example-record-event-via-gtm 1-set-up-a-thank-you-page=1-crie-uma-p%C3%A1gina-de-agradecimento h_01KGJCGCPZQDP9KVBSE1Z1GT48=1-crie-uma-p%C3%A1gina-de-agradecimento 2-configure-the-gtm-tag=2-configure-a-tag-do-gtm h_01KGJCGCPZ2YVRY6VYJ0BTC14N=2-configure-a-tag-do-gtm h_01KP3CJBZXD6MPTQ0KCPMTM1Y9=example-record-event-via-af-web-sdk-interaction h_01KP3CJBZX53G1HABG3TKN2X6S=example-record-event-via-gtm-interaction 1-set-up-a-checkout-page=1-configure-uma-p%C3%A1gina-de-checkout h_01KGJCGCQ0858AAJC82Y2G0GNP=1-configure-uma-p%C3%A1gina-de-checkout 2-configure-gtm-variables-and-triggers=2-configure-vari%C3%A1veis-e-gatilhos-no-gtm h_01KGJCGCQ0GGYDQBP9CJNM9AXQ=2-configure-vari%C3%A1veis-e-gatilhos-no-gtm 3-create-the-interaction-tag=3-crie-a-tag-de-intera%C3%A7%C3%A3o h_01KGJCGCQ0EV557QF3CGZ6YB4X=3-crie-a-tag-de-intera%C3%A7%C3%A3o 4-set-customer-user-id=6-definir-o-customer-user-id h_01KGJCGCQ0RNBW7V5T4PXVXQW1=6-definir-o-customer-user-id a-sign-up-form-example=um-exemplo-de-formul%C3%A1rio-de-cadastro h_01KGJCGCQ0M0ESXFMK45PJ3SX9=um-exemplo-de-formul%C3%A1rio-de-cadastro a-thank-you-page-example=um-exemplo-de-p%C3%A1gina-de-agradecimento h_01KGJCGCQ0FMKFKM2SWV2794T5=um-exemplo-de-p%C3%A1gina-de-agradecimento 5-manage-privacy=7-gerenciar-a-privacidade h_01KGJCGCQ01PQWT44ZWE329DWX=7-gerenciar-a-privacidade sdk-initial-state-setting-in-the-snippet=defini%C3%A7%C3%A3o-do-estado-inicial-do-sdk-no-snippet h_01KGJCGCQ0AQM3Y9NNCJF2XP9G=defini%C3%A7%C3%A3o-do-estado-inicial-do-sdk-no-snippet explicit-control=controle-expl%C3%ADcito h_01KGJCGCQ07KKYGN5JZF41A6W7=controle-expl%C3%ADcito content-security-policy-csp=pol%C3%ADtica-de-seguran%C3%A7a-de-conte%C3%BAdo-csp h_01KGJCGCQ0QB7NK6YNZT5XJVJY=pol%C3%ADtica-de-seguran%C3%A7a-de-conte%C3%BAdo-csp advanced-sdk-verification-with-csp-nonce-snippets=verifica%C3%A7%C3%A3o-avan%C3%A7ada-de-sdk-com-snippets-de-nonce-csp h_01KP11XJV88YB2NSBZJTX9K7ZQ=verifica%C3%A7%C3%A3o-avan%C3%A7ada-de-sdk-com-snippets-de-nonce-csp h_01KP3CJBZXQ4D538H0T7N9FZ6Z=nonce-without-smart-banners h_01KP3CJBZX8K3WK6RHQMB029VN=nonce-with-smart-banners discard-query-parameters=descartar-par%C3%A2metros-de-consulta h_01KGJCGCQ010K4RMFMGHD5NDC3=descartar-par%C3%A2metros-de-consulta web-sdk-cookies-reference=refer%C3%AAncia-de-cookies-do-web-sdk h_01KGJCGCQ03A1H7NA5ZGPSGKP3=refer%C3%AAncia-de-cookies-do-web-sdk" />
