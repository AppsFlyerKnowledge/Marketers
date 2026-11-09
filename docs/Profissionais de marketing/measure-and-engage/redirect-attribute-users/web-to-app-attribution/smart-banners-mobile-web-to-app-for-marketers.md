---
title: Smart Banners — web-to-app mobile (para profissionais de marketing)
metadata:
  keywords:
    - Landing Page
    - Advertisers
    - Web Attribution
    - Developers
    - Smart Banner
    - sb
    - Marketers
    - Banner
    - Banners
    - Smart Banners and Scripts
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-asaf-mashiah
    - Marketers
    - Smart Banners and Scripts
  created_at: '2019-01-14T12:33:07Z'
  edited_at: '2026-08-18T00:36:22Z'
  id: 360000764837
  locale: pt
  section: Web-to-app attribution
  section_id: 6551240476177
  url: https://support.appsflyer.com/hc/pt/articles/360000764837
---
> **Visão Geral:** converta os visitantes do seu site em usuários mobile com os Smart Banners.

<Image align="center" alt="" src="https://files.readme.io/2e76dd3d337d7cb8e34af01b34f3a466fa724566058d260f56796bf6eae4b3ff-34734678772881.jpg" />

<div id="note" />

> 📘 **Nota**
>
> O web SDK v1 do Smart Banner da AppsFlyer foi desativado em 8 de novembro de 2023. Para exibir Smart Banners em seu site, você precisa atualizar para a v2. <Anchor target="_blank" href="/marketers/pt/docs/bulletin-deprecation-of-appsflyer-smart-banner-web-sdk-v1">Saiba mais.</Anchor>

## Smart Banners

Smart Banners:

* **São exibidos no site mobile da sua marca** para aumentar as taxas de conversão para usuários de alta intenção.
* Mensuram a qualidade das instalações de aplicativos provenientes de visitantes do site mobile.
* Permitem a atribuição precisa de campanhas web-to-app para TODOS os canais de mídia, incluindo SRNs.
* Os Smart Banners podem atribuir usando <Anchor target="_blank" href="/marketers/pt/docs/appsflyer-attribution-model#tipos-de-atribuição-de-engajamento-do-usuário">atribuição de view-through, atribuição de click-through</Anchor> e contagem de impressões:
  * **Cliques:** um usuário clica nos Smart Banners e segue para a instalação.
  * **Impressões:** quando o banner é carregado (o usuário vê o banner), ele envia um evento de contagem de impressão para a AppsFlyer.

O fluxo funciona da seguinte maneira:

1. Um usuário clica em um anúncio e é direcionado para o site mobile do anunciante.
2. Um Smart Banner é [exibido](/docs/smart-banners-mobile-web-to-app-for-marketers#banner-group-display-logic) no site mobile do anunciante.
3. O usuário clica no Smart Banner e:
   * **Se o aplicativo não estiver instalado**, ele será direcionado para a loja de aplicativos para fazer a instalação.
   * **Se o aplicativo estiver instalado** e Universal Links, App Links e/ou links de esquema URI estiverem configurados, o aplicativo será inicializado diretamente.
4. O usuário é levado ao conteúdo in-app, no contexto da promoção.
5. Ele é atribuído ao canal de mídia que mostrou o anúncio original.

**Quem está envolvido**

* O desenvolvedor do site precisa apenas <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_smart_banner_v2#installation">inserir um trecho de código (code snippet) no HTML do site</Anchor>.
* Para todas as outras ações, apenas a ação do profissional de marketing é necessária.

---

**Pré-requisitos**

* Uma conta da AppsFlyer com pelo menos um aplicativo
* [opcional] Copiar **chave da web (web key)** (essa chave já existe como parte do trecho de código).

---

**Tempo necessário**

Aproximadamente 20 minutos.

---

**Resultado**

* Os visitantes do site que clicam no botão de CTA são enviados para a loja de aplicativos ou página correta na web, de acordo com o dispositivo utilizado.
* Usuários de aplicativos mobile que clicam no botão CTA podem ser enviados ao aplicativo por meio de deep linking.
* Os usuários são atribuídos de acordo com o clique/instalação aos canais de mídia originais ou canais de mídia própria
* A performance do banner pode ser visualizada na página de performance e nos cartões.

---

---

<div id="example" />

> 📄 **Exemplo**
>
> Mark é um profissional de marketing que trabalha para um serviço de delivery bem-sucedido, o "Feed Me".
>
> Ele quer converter os visitantes do site mobile do Feed Me em usuários do app.
>
> Para fazer isso, Mark usa os Smart Banners com seus próprios criativos e textos.
>
> Smart Banners são uma tecnologia do OneLink. Quando os visitantes do site clicam no botão de CTA, ele **os direciona automaticamente para a loja de aplicativos ou landing page apropriada**. Quando usuários mobile existentes clicam no botão de CTA, o aplicativo é aberto.
>
> Em seguida, a AppsFlyer **atribui o clique/instalação ao canal de mídia e à campanha do Mark**.

<div id="important" />

> 🚧 **Importante!**
>
> Use os Smart Banner da AppsFlyer ou o smart app banner do iOS Safari, mas não ambos. O uso de ambos pode causar problemas de exibição em seu site mobile e resultar em discrepâncias de atribuição.

<div id="setup" />

## Configuração

Conclua os procedimentos a seguir para configurar um Smart Banner que:

* Direcione os usuários do seu site mobile, através de um Smart Banner, para a loja de aplicativos ou para a página certa dentro do app com base no dispositivo utilizado.
* Atribua o clique/instalação ao seu canal de mídia própria usando o OneLink.

<div id="1-website-workplace-setup" />

<Accordion title="1. Configuração do workplace do site">

<div id="prepare-your-mobile-site-to-display-smart-banners-for-the-first-time" />

#### Prepare seu site mobile para exibir Smart Banners pela primeira vez

1. Na AppsFlyer, no menu lateral, selecione **engajar** > **web-to-app** > **Smart Banners** > **ir para Smart Banners**.
2. Clique em **começar**. O assistente de configuração guiará você pelas etapas necessárias (a seguir). Para configurar outros workplaces do site, veja abaixo
3. Insira um nome de workplace do site.
4. Clique em **criar**. O workplace do site vai abrir.
5. Copie o **trecho de código (code snippet)** do banner.
6. Implemente o trecho de código em seu site. Essa tarefa é feita apenas uma vez por site.
   * Para adicionar o código ao seu site via Google Tag Manager, Adobe Tag Manager, Shopify, Wix, Squarespace ou WordPress, consulte <Anchor target="_blank" href="/marketers/pt/docs/smart-banners-website-code-implementation-for-marketers">Implementação de código de site aos Smart Banners - para profissionais de marketing</Anchor>.
   * Para adicionar o código por meio de outras plataformas ou fazer alterações no código de acordo com as suas necessidades (incluindo a adição de parâmetros, deep linking, ocultação do banner ou integração do PBA com os Smart Banners), consulte <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_smart_banner_v2">Implementação de código de site aos Smart Banners - para desenvolvedores</Anchor>.
7. [opcional] Copiar **chave da web (web key)** (essa chave já existe como parte do trecho de código). (Essa chave já existe como parte do trecho de código.)
8. Clique em **continuar.**

<div id="to-create-website-workplaces-after-the-first-time" />

#### Para criar workplaces do site após a primeira vez

1. Na AppsFlyer, no menu lateral, vá para **Engajar** > **Web-to-app** > **Smart Banners** > **Studio**.
2. Clique no menu de opções
3. selecione **novo workplace do site**
4. Insira um nome de workplace do site.
5. Clique em **criar**. O workplace do site vai abrir.
6. Copie o **trecho de código (code snippet)** do banner.
7. Implemente o trecho de código em seu site. Essa tarefa é feita apenas uma vez por site.
   * Para adicionar o código ao seu site via Google Tag Manager, Adobe Tag Manager, Shopify, Wix, Squarespace ou WordPress, consulte <Anchor target="_blank" href="/marketers/pt/docs/smart-banners-website-code-implementation-for-marketers">Implementação de código de site aos Smart Banners - para profissionais de marketing</Anchor>.
   * Para adicionar o código por meio de outras plataformas ou fazer alterações no código de acordo com as suas necessidades (incluindo a adição de parâmetros, deep linking, ocultação do banner ou integração do PBA com os Smart Banners), consulte <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_smart_banner_v2">Implementação de código de site aos Smart Banners - para desenvolvedores</Anchor>.
8. [opcional] Copiar **chave da web (web key)** (essa chave já existe como parte do trecho de código). (Essa chave já existe como parte do trecho de código.)
9. Clique em **continuar.**

</Accordion>

<div id="2-banner-group-setup" />

<Accordion title="2. Configuração de grupos de banners">

Os grupos de banners contêm um ou mais banners. Aqui você pode:

* Selecionar o template do OneLink usado pelo grupo de banners, que contém os aplicativos mobile para os quais os visitantes do site serão redirecionados.
* Definir um esquema específico de deep linking
* Definir suas regras de segmentação, cronograma, comportamento e detalhes de atribuição usados por todos os banners do grupo de banners.
* Definir quais páginas ativam os banners do grupo de banners quando acessadas.

**Para configurar ou duplicar um grupo de banners:**

1. Na AppsFlyer, no menu lateral, vá para **Engajar** > **Web-to-app** > **Smart Banners**.
2. **Para configurar um grupo de banners pela primeira vez**
   1. <span class="af-ol-a"></span>No lado esquerdo, clique em **adicionar grupo de banners**.
   2. Siga o 5º passo e os passos seguintes.
3. **Para configurar grupos de banners adicionais**
   1. <span class="af-ol-a"></span>Acesse a aba **Studio**.
   2. Clique em **+ Novo.**
   3. Siga o 5º passo e os passos seguintes.
4. **Para duplicar um grupo de banners**
   1. <span class="af-ol-a"></span>Clique no ícone **duplicar** ao lado do ícone de deletar.
5. Insira um **nome exclusivo para o grupo de banners**. O nome deve representar um tema comum geral entre os banners definidos para o grupo de banners em questão (por exemplo, o aplicativo anunciado).
6. Selecione o template do OneLink para o grupo de banners.
7. [opcional] Defina um **esquema URI** para o grupo de banners como um fallback para usuários de Universal Links e de Android App Links. Isso raramente é necessário, pois, como padrão, o valor é retirado do template do OneLink. Só faça essa configuração para o grupo de banners caso seja necessário um valor diferente do que o definido no template.
8. <span id="attributed-sources"></span>Configure as **fontes atribuídas** primárias e de fallback a serem atribuídas com novas instalações vindas desse grupo de banners.   
    **Aviso sobre o reencaminhamento do click ID:** FBCLID, GCLID, WBRAID e GBRAID são automaticamente reencaminhados para a URL de saída se estiverem disponíveis na URL de entrada. Para os click IDs do Google, se o parâmetro "keyword" também for encontrado, ele coloca o valor da palavra-chave (keyword) na URL de saída como o valor de af\_keywords.

   Use a tabela a seguir para escolher a melhor opção para o link personalizado.

<div id="param-table" />

| Opção | Quando selecionar | Comentários |
| --- | --- | --- |
| **Usar parâmetros UTM** | Selecione quando a maioria dos visitantes não-orgânicos chegam ao site mobile a partir de canais com parâmetros UTM. | ◦ Nome do canal de mídia (pid) = UTM\_Source   <br />◦ Campanha (c) = UTM\_campaign  <br />◦ Se os parâmetros UTM\_source ou UTM\_Campaign estiverem ausentes, os nomes estáticos serão usados como fallback. |
| **Usar parâmetros do link de atribuição recebido** | Selecione quando a maioria dos visitantes não-orgânicos chegam ao site mobile a partir de cliques em ad networks que usam links de atribuição da AppsFlyer. | ◦ Todos os parâmetros disponíveis do link de atribuição de entrada da AppsFlyer são adicionados ao link do Smart Banner.<br /><br />◦ Se existir um parâmetro no link de atribuição de entrada da AppsFlyer e no Smart Banner, o parâmetro de entrada prevalece no link personalizado final. |
| **Adicionar outro parâmetro de atribuição** | Se desejar, adicione dados adicionais de atribuição relacionados ao site. Isso permite a análise granular de cada instalação. | Por exemplo, para sites de eCommerce, crie links personalizados idênticos para cada tipo de categoria de produto, que diferem por valores af\_adset (por exemplo: "af\_adset=fruit") |
| **Usar parâmetros de atribuição padrão** | ◦ Selecione quando: ▪ A maioria dos visitantes do site mobile é orgânica.   ▪ Visitantes não-orgânicos não chegam ao site a partir de cliques em ad networks ou de fontes com parâmetros UTM. ◦ Você pode personalizar os valores dos parâmetros. | **Importante:** recomendamos que você selecione a UTM ou os parâmetros de link de atribuição de entrada, pois os parâmetros de atribuição padrão do Smart Banner são usados no link personalizado como fallback, caso o canal de mídia, a campanha ou os nomes dos canais não estejam disponíveis. |

9. [Recomendado] Defina o parâmetro de atribuição padrão **Nome do canal** para atribuir todas as instalações provenientes do Smart Banner para o canal especificado. Isso permite que você agregue informações de várias fontes de mídia no mesmo canal no **relatório de coorte**, **painel de visão geral**, **relatório de retenção** e mais.
10. <span id="2-banner-group-setup-step10"></span>[Opcional] Ative **Retargeting** se você planeja usar o grupo de banners para registrar reengajamentos realizados por usuários que clicam no banner. Para saber mais sobre Retargeting, consulte o <Anchor target="_blank" href="/marketers/pt/docs/retargeting-attribution-guide">guia de atribuição de Retargeting</Anchor>.

    <div id="important-1" />

    > 🚧 **Importante:**
    >
    > Para que o retargeting funcione, você também precisa:
    >
    > * <Anchor target="_blank" href="/marketers/pt/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#ativar-o-retargeting-para-o-aplicativo">Ativar o retargeting para o aplicativo</Anchor>


    Os usuários existentes que clicam em links sem retargeting (UA) com tecnologia do OneLink também iniciam têm a mesma experiência quando abrem o aplicativo. No entanto, seus reengajamentos são registrados como sessões regulares, o que significa que é impossível mensurar o sucesso da campanha de mídia própria.
11. [Opcional] Ative **ignorar usuários ativos para retargeting** e selecione a janela de inatividade. Assim, o parâmetro af\_inactivity\_window=[número de dias] é adicionado aos seus links do grupo de smart banners e todos os usuários ativos durante esse período são ignorados para retargeting.
12. Configure a janela de reengajamento para determinar o período após o reengajamento, onde os eventos in-app do usuário são atribuídos ao canal de mídia de retargeting.
    * Pode definir o valor em dias (1-90), horas (até 23) ou mesmo vitalício.
    * A janela de reengajamento é adicionada ao link no parâmetro af\_reengagement\_window.
13. <span id="dismissal-behaviour"></span>[Opcional] Configure o **comportamento de rejeição**, ou seja, o tempo mínimo permitido entre a rejeição de um banner feita por um usuário e o momento em que o banner pode ser exibido novamente a esse usuário. Selecione uma das seguintes opções:
    * Por tempo: 1 hora, 1 dia ou 1 semana.
    * Próxima sessão: é a sessão que ocorre em uma guia ou janela diferente, depois que o usuário fecha o banner.
    * Nunca: o banner não é mostrado novamente. **Nota**:
      * Se o usuário limpar o cache do navegador ou visualizar o site no modo de navegação privada, a configuração do comportamento de rejeição será perdida.
      * O comportamento de rejeição é aplicado ao banner que o usuário descarta; outros banners ainda podem ser exibidos.
14. [opcional] Configure o **limite de frequência**.  O limite de frequência determina o número de vezes que cada banner em um grupo de banners é exibido para um único usuário. Você pode escolher a opção **sem limites** (em que os banners sempre são exibidos) ou **limitar a exibição dos banners**.

    Por exemplo, se um grupo de banners consistir em três banners e o limite de frequência for definido como um, cada banner no grupo aparecerá uma vez por usuário. Nesse cenário, após três visitas, o usuário terá visualizado os três banners do grupo. No entanto, a partir da quarta visita, o usuário não verá mais nenhum banner desse grupo. Quando o limite de frequência é definido como dois, cada banner do grupo será exibido duas vezes por usuário, exigindo um total de seis visitas para atingir o limite.
15. [Opcional] Defina em qual **sistema operacional** você deseja mostrar os banners:
    * Todos os sistemas operacionais mobile.
    * Apenas Android ou apenas iOS.
16. [Opcional] **Configure** a ativação do grupo de banners: iniciar imediatamente (padrão) ou definir uma campanha com tempo limitado.
17. [Opcional] Configure em quais **locais** o grupo de banners ficará ativado.
    1. <span class="af-ol-a"></span>Selecione **global** para exibir esse grupo de banners a todos os usuários. Se necessário, exclua visitantes de diferentes regiões, países ou estados.
    2. Selecione a opção **escolher localização específica** para exibir esse grupo de banners para usuários de um ou mais locais específicos.
18. [Opcional] Configure **exibir nas páginas** para definir em quais páginas o grupo de banners pode ser exibido aos visitantes:
    * **[Padrão]** Exibir em todas as páginas do site. **Atenção**: recomendamos que você defina pelo menos um grupo de banners para todas as páginas como fallback.
    * **Mostrar em páginas específicas**: especifique o que a página ou URL deve conter para exibir banners.
      * Você pode escolher:
        * **Página específica**: especifique o host e/ou caminho (path) da página na qual você deseja exibir o banner. Quaisquer consultas (queries) inseridas serão ignoradas. Exemplo: http://www.example.com/path?query
        * **Caminho da URL e query**: Caminho e query da URL: insira o caminho (path) e/ou o query que determina se o banner é exibido ou não. Exemplo: path?query. **Atenção**: Não insira uma URL inteira, como http://www.exemplo.com/path?query. Insira apenas o path e/ou a query.

* Até 15 condições podem ser adicionadas usando e/ou.
* Se houver um conflito entre as condições, o banner não será exibido.

1. Clique em **criar grupo de banners**.
2. [Opcional] Para editar novamente o grupo de banners, passe o mouse sobre  **direcionamento e comportamento** e clique em **editar**.

<div id="example-1" />

> 📄 **Exemplo**
>
> Mark é o profissional de marketing de um serviço de delivery chamado "Feed Me". Ele decide criar uma campanha para a venda de ameixas no aplicativo. Mark decide usar um disparo de SMS, além de ad networks e do Google para a campanha.
>
> Em preparação para a campanha, Mark:
>
> * Opta por usar os parâmetros de atribuição do link de entrada e os parâmetros UTM (com parâmetros padrão como fallback para cliques que não vêm de um link de entrada ou de uma campanha UTM).
> * Fornece à ad network um link de atribuição exclusivo a ser usado na campanha para direcionar os usuários para a página de venda de ameixas no site mobile do Feed Me. O link inclui o parâmetro de URL de redirecionamento (af\_r), com o URL para a página de venda de ameixas: `http://feedme.com/plums_link`.
> * Prepara uma campanha do Google Ads para usuários que visitam páginas na web mobile que contenham "plums\_utm".
> * Para SMS, adiciona parâmetros de atribuição exclusivos para usar no link da campanha, direcionando os usuários à página de venda de ameixas no site mobile do Feed Me. O link inclui o parâmetro pid, com a URL para a página de venda de ameixas: `http://feedme.com/plums_link?pid=sms&c=plums`.
>
> As campanhas começam a ser executadas.
>
> Os usuários:
>
> * Veem o anúncio para a venda de ameixas e clicam no site mobile do Feed Me.
> * Os cliques do Google Ads e todos os outros cliques chegam à landing page do link de entrada e o Smart Banner correspondente é ativado por página.
> * Veem o Smart Banner no site mobile e clicam nele.
> * Chegam ao aplicativo do Feed Me, baixam e instalam.
> * Ao abrir o app, são direcionados para a página com a venda de ameixas.
> * São atribuídos aos canais de mídia corretos que os levaram ao site mobile do Feed Me.

<div id="targeting--behavior" />

#### Direcionamento e comportamento

O dashboard de segmentação e comportamento mostra as configurações definidas para esse grupo de banners. Para editar essas configurações, clique no ícone de edição.

</Accordion>

<div id="3-banner-setup" />

<Accordion title="3. Configuração do banner">

**Para criar um banner em um grupo de banners:**

1. Clique em **Novo banner** para entrar  na página **Editar banners**.
2. Configure o **Nome** do banner.
3. Crie um **Criativo de design**:
   1. <span class="af-ol-a"></span>Clique em **Criativo de design** para configurar o criativo do banner.

      Uma janela para escolher um template de banner aparece.

      <Image align="center" alt="" src="https://files.readme.io/72baea2c6323742beb17761fdf8dc69048ada303db89855db8a60644ead3ad7f-34734678773649.png" />
   2. Passe o mouse sobre **Template de criativo** e clique em **Criar** para acessar a página de configuração de **Montar criativo**.
   3. Personalize todos os elementos do criativo do Smart Banner. Para fazer isso, selecione os elementos por nome ou clique em cada um na imagem de pré-visualização. **Nota:** nem todos os elementos estão disponíveis em todos os templates.
      * Título
      * Descrição
      * Estrelas de classificação
      * Botão de fechar
      * Call to action
      * Logo do aplicativo
      * CONTEXTO
      * Posição do banner
      * Espaçamento do banner (para ajustar o tamanho do banner)
      * Transparência do dispositivo
      * Para imagens, use um dos seguintes tipos de arquivo: jpeg, jpg, png. **Observação**: o formato webp não é compatível.  As recomendações para as imagens são:

| Tipo de template | Tamanho máximo do arquivo de imagem | Proporção da imagem | Altura da imagem | Largura da imagem |
| --- | --- | --- | --- | --- |
| Mínimo | 300 KB | 3:1 (largura x altura) | 70 px | Ajustado para se adequar ao dispositivo |
| Padrão | 300 KB | 3:1 (largura x altura) | 70 px | Ajustado para se adequar ao dispositivo |
| Aprimoradas | 300 KB | 9:4 (largura x altura) | 110 px | Ajustado para se adequar ao dispositivo |
| Múltipla escolha | 300 KB | 9:4 (largura x altura) | 110 px | Ajustado para se adequar ao dispositivo |
| Promocional | 300 KB | 4:5 (largura x altura) | 300 px | Ajustado para se adequar ao dispositivo |
| Sobreposição de múltipla escolha | 300 KB | 9:4 (largura x altura) | 110 px | Ajustado para se adequar ao dispositivo |
| Intersticial | 700 KB | 9:16 (largura x altura) | Ajustado para se adequar ao dispositivo | Ajustado para se adequar ao dispositivo |

   4. Clique em **Revisar** para revisar o criativo do banner e testar sua aparência em diferentes dispositivos. **Atenção**: os banners podem aparecer um pouco diferentes nas campanhas ativas em comparação com as imagens de pré-visualização.
   5. Se forem necessárias alterações, clique em **Voltar ao editor**.
   6. Clique em **Concluído** para voltar à página de configuração do banner.
4. [Opcional] Adicione parâmetros de atribuição personalizados. Por exemplo: `ad_adset` e `af_ad`. **Atenção**: os parâmetros `pid`, `c` e `channel` não podem ser adicionados no nível do banner, pois pertencem ao nível do grupo de banner.
5. Depois de terminar e salvar o novo criativo, o status do banner se torna ativo. Use o botão **Status** para alternar entre os status **Ativo** e **Pausado**.
6. Clique em **Salvar** para salvar seu trabalho ou **Salvar e fechar** para salvar seu trabalho e fechar a página de configuração do banner.

<div id="example-2" />

> 📄 **Exemplo**
>
> Para dicas e truques, consulte a nossa <Anchor target="_blank" href="https://drive.google.com/file/d/1mr6g3uNwlLw6UQ_WgtQZprJMhauw7Xi3/view?usp=sharing">cheat sheet para Smart Banners</Anchor>.

</Accordion>

<div id="4-testing" />

<Accordion title="4. Testes">

Quando o criativo estiver pronto, é hora de testá-lo  **antes** de publicá-lo e ativá-lo para seus usuários.

**Para testar um criativo do Smart Banner:**

**Pré-requisitos:** certifique-se de que o trecho de código do Smart Banner esteja integrado ao seu site.

1. Na página **Testar criativo**, insira o link para sua página web em que o SDK do Smart Banner está integrado (consulte [Smart Banners para desenvolvedores](https://dev.appsflyer.com/hc/docs/dl_smart_banner_v2)).
2. Clique em **Gerar**.
3. Copie o link gerado e envie-o para seu dispositivo de teste ou escaneie o QR code com o dispositivo de teste. **O link ou QR deve redirecionar para o site e exibir um banner com o criativo.**
4. Clique em **Editar criativo** para retornar à configuração do criativo ou clique em **Concluído** para salvá-lo.

</Accordion>

<div id="view-banner-performance" />

## Visualizar a performance do banner

Você pode visualizar e comparar a performance de todos os seus banners na página de performance.

Você pode ter uma visão rápida da performance de banners específicos em seus cartões de performance individuais.

Os dados de performance do banner incluem:

* Impressões
* Fechar banner
* Cliques
* Instalações
* Reatribuições
* Reengajamentos
* Taxa de cliques (CTR). Fórmula: Cliques/impressões x 100
* Taxa de conversão (CVR). Fórmula: Atribuições / Cliques x 100

**Atenção**:

* Os dados se baseiam no fuso horário UTC.
* A atualização dos dados é <Anchor target="_blank" href="/marketers/pt/docs/about-data-freshness-and-timezone-support#continuous-aka-realtime">contínua</Anchor>.
* Os dados são exibidos por banner e template do OneLink. Isso significa que se o seu banner e template do OneLink estiverem configurados para mais de um aplicativo (por exemplo, tanto um aplicativo Android quanto um aplicativo iOS), os dados de performance são exibidos para mais de um aplicativo.
* O CVR pode ser maior do que o esperado, às vezes até acima de 100%, pois as atribuições de exibição e de clique são contadas.

<div id="performance-page" />

<Accordion title="Página de performance">

A página de performance permite que você pode visualize e compare os dados de performance de todos os seus Smart Banners, até os 90 dias anteriores.

**Para ver a página de performance**:

1. Na AppsFlyer, no menu lateral, vá para **Engajar** > **Web-to-app** > **Smart Banners** > **Performance**.
2. Selecione o intervalo de datas para o qual você deseja visualizar a performance. O intervalo de data padrão são os últimos 7 dias.
3. [Opcional] Ative **Mostrar apenas os banners ativos**. Quando ativado, os dados dos banners pausados ou não ativos no momento não são exibidos, mesmo que estivessem ativos durante o intervalo de datas selecionado. Os dados de performance são exibidos para o intervalo de datas selecionado.

</Accordion>

<div id="performance-cards" />

<Accordion title="Cartões de performance">

Você pode visualizar os dados de performance dos últimos 7 dias para qualquer banner.

**Para visualizar a performance do banner**:

1. Na AppsFlyer, no menu lateral, vá para **Engajar** > **Web-to-app** > **Smart Banners** > **Studio**.
2. Selecione o workplace do site e o grupo de banners para o qual você deseja visualizar a performance.
3. Passe o mouse sobre qualquer um dos banners no grupo de banners. Os dados de performance são exibidos para a semana anterior.

</Accordion>

<div id="additional-information" />

## Informações adicionais

<div id="banner-group-display-logic" />

<Accordion title="Lógica de exibição do grupo de banners">

A AppsFlyer leva em consideração o seguinte ao determinar se/qual Smart Banner exibir:

* Existem regras (comportamento de rejeição, limite de frequência, localização, mostrar nas páginas, etc.) definidas para os grupos de banners?
* O usuário final atende às condições da regra e se qualifica para ver um banner?

Se a resposta para ambas as perguntas for sim, a AppsFlyer escolherá um banner que será exibido conforme explicado na tabela a seguir.

| Configuração de grupos de banners | Quais banners são exibidos | Exemplo |
| --- | --- | --- |
| Grupo de banner único | A AppsFlyer divide a exibição de todos os banners ativos em todos os seus grupos de banners entre todos os usuários elegíveis. | • Exemplo 1: existe 1 banner ativo. Ele é exibido para todos os usuários.<br /><br />• Exemplo 2 : existem 2 banners. 50% dos usuários veem o banner 1 e os outros 50% veem o banner 2.<br /><br />• Exemplo 3: existem 3 banners, 1/3 dos usuários elegíveis veem cada banner.<br /><br />• Exemplo 4:  não há banners ativos. Nada é exibido. |
| Diferentes grupos de banners com regras idênticas | A AppsFlyer divide a exibição de todos os banners ativos em todos os seus grupos de banners entre todos os usuários elegíveis. | Existem 2 grupos de banners (A e B), cada um com 3 banners (um total de 6 banners). 1/6 dos usuários elegíveis veem cada banner. |
| Múltiplos grupos de banners com múltiplas regras | A AppsFlyer divide a exibição de todos os banners ativos *do grupo de banners com regras que descrevem e correspondem mais especificamente aos usuários*. Se os grupos de banners tiverem detalhes específicos, mas diferentes, os banners de todos esses grupos serão exibidos. | • Exemplo 1: existem 2 grupos de banner, A e B. O grupo de banner A está configurado para ser exibido no mundo todo e o grupo de banner B está configurado para ser exibido no Japão. O grupo de banner B é mais específico, portanto apenas os banners desse grupo são exibidos para usuários no Japão. Se o grupo não tiver banners ativos, nada será exibido.<br /><br />• Exemplo 2 : existem 2 grupos de banners, A e B. O grupo de banner A está configurado para ser exibido no mundo todo, e o grupo de banner B está configurado para ser exibido em todos os lugares, exceto na Ucrânia. O grupo de banner B é mais específico, portanto, apenas os banners desse grupo são exibidos para usuários no mundo todo (exceto usuários na Ucrânia). Se o grupo B não tiver banners ativos, nada será exibido. O grupo A é exibido na Ucrânia.<br /><br />• Exemplo 3: existem 2 grupos de banner, A e B. O grupo de banner A está configurado para ser exibido no Japão e o grupo de banner B está configurado para ser exibido em abril. Ambos os grupos são igualmente específicos, mas de maneiras diferentes. Portanto, no Japão, em abril, os banners de ambos os grupos de banners são exibidos, pois nenhum grupo tem prioridade sobre o outro. |

</Accordion>

<div id="ab-testing-banner-performance" />

<Accordion title="Teste A/B da performance de banners">

Você pode fazer testes A/B para comparar a performance dos seus banners no dashboard de performance. Para dados adicionais relacionados com a atribuição, recomendamos que você adicione `af_adset`, `af_ad` ou outros parâmetros de atribuição (exceto `pid`, `c`, e `channel`) com um valor único para cada criativo ou grupo de banners. Use esses parâmetros para comparar a performance de cada grupo, analisando os dados nos dashboards e relatórios da AppsFlyer.

</Accordion>

<div id="faq" />

## Perguntas frequentes

<div id="why-does-my-banner-not-display" />

<Accordion title="Por que meu banner não é exibido?">

Isso acontece por conta do limite de frequência definido no grupo do seu banner. O limite de frequência determina quantas vezes o banner pode ser mostrado a um único usuário. Por exemplo, se o limite de frequência estiver definido como três, e um usuário visitar o site quatro vezes, o usuário verá o banner nas primeiras 3 visitas, mas não da quarta em diante. O limite de frequência pode ser desativado. Selecione um valor de limite de frequência ou desative o limite de frequência.

</Accordion>

<div id="can-i-use-my-own-font-for-my-banner" />

<Accordion title="Posso usar minha própria fonte em meu banner?">

Sim. você pode definir sua própria usando as [instruções no developer hub](https://dev.appsflyer.com/hc/docs/dl_smart_banner_v2#control-smart-banner-font).

* Você precisa de um desenvolvedor de site para a implementação.
* A fonte será aplicada a todos os banners no site e a todos os elementos de texto dentro do banner.
* A fonte não pode ser visualizada no editor criativo.
* Após a implementação, [teste seu banner](/docs/smart-banners-mobile-web-to-app-for-marketers#4-testing).
* Se a fonte não for exibida corretamente, salve novamente seu banner no [editor criativo](/docs/smart-banners-mobile-web-to-app-for-marketers#3-banner-setup).

</Accordion>

<div id="can-i-add-parameters-to-the-url-of-my-smart-banners" />

<Accordion title="Posso adicionar parâmetros à URL dos meus Smart Banners?">

Sim, basta invocar as duas funções seguintes no seu smart script:

* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_smart_banner_v2#showbanner">showBanner</Anchor>
* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_smart_banner_v2#updateparams">updateParams</Anchor>

</Accordion>

<div id="do-smart-banners-support-deep-linking" />

<Accordion title="Os Smart Banners são compatíveis com deep linking?">

Sim. Para isso, adicione o parâmetro <Anchor target="_blank" href="/marketers/pt/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#deep-linking-and-deferred-deep-linking">deep\_link\_value</Anchor> de uma das seguintes maneiras:

* Na interface do usuário da AppsFlyer, adicione um parâmetro de atribuição personalizado estático durante a [configuração do banner](/docs/smart-banners-mobile-web-to-app-for-marketers#3-banner-setup).
* Use additionalParams na função [ShowBanner](https://dev.appsflyer.com/hc/docs/dl_smart_banner_v2#showbanner%20target=) para adicionar o parâmetro à URL antes de exibir o banner.
* Use a função <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_smart_banner_v2#updateparams">updateParams</Anchor> para adicionar o parâmetro à URL após a exibição do banner.

Certifique-se de que seu desenvolvedor implemente o comportamento desejado do deep\_link\_value.

</Accordion>

<div id="can-smart-banners-show-different-content-based-on-whether-or-not-users-have-the-app-installed" />

<Accordion title="Os Smart Banners podem mostrar conteúdos diferentes quando o usuário não tem o aplicativo instalado?">

Não. Se você não sabe se os usuários têm o aplicativo instalado, recomendamos que você faça seu call to action de forma que ele se aplique a ambos os casos. Por exemplo: Por exemplo: "vá para o aplicativo" ou "abra o aplicativo."

</Accordion>

<div id="do-original-incoming-url-parameters-remain-available-for-the-smart-banner-url-when-users-navigate-away-from-and-then-return-to-the-banners-landing-page" />

<Accordion title="Os parâmetros originais da URL de entrada permanecem disponíveis para a URL do Smart Banner quando os usuários saem e retornam à landing page?">

Sim. Se a URL de entrada original contiver um parâmetro utm\_source ou pid, a URL original será salva durante a sessão de navegação e os parâmetros serão aplicados à URL do banner de saída.

</Accordion>

<div id="can-i-set-my-banners-to-display-on-my-mobile-site-but-not-on-my-wrapperhybrid-app" />

<Accordion title="Posso configurar meus banners para serem exibidos no meu site mobile, mas não no meu aplicativo wrapper/híbrido?">

Sim. Para fazer isso, na implementação de Smart Banners em um aplicativo wrapper/híbrido e carregar a página do banner a partir do aplicativo (e não de um navegador da web), não use a função [showBanner](https://dev.appsflyer.com/hc/docs/dl_smart_banner_v2#showbanner%20target=), pois isso exibe o banner no aplicativo. Como alternativa, use a função <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_smart_banner_v2#hidebanner">hideBanner</Anchor>.

</Accordion>

<div id="do-smart-banners-support-web-accessibility" />

<Accordion title="Os Smart Banners são compatíveis com acessibilidade na web?">

Queremos garantir que todos os seus usuários, incluindo aqueles com deficiências, possam acessar e se engajar totalmente com os Smart Banners.

Por isso, tentamos tornar a acessibilidade na web compatível com nossos Smart Banners, seguindo as melhores práticas do WCAG 2.1 e fornecendo os atributos HTML relevantes nos elementos do Smart Banner.

No entanto, entender quais são os requisitos de acessibilidade relevantes para seus usuários nos Smart Banners é de sua responsabilidade. Você é o único responsável por garantir que os Smart Banners que você usa sejam acessíveis a todos os usuários de acordo com os requisitos relevantes de acessibilidade na web.

Observe que muitas alterações nos Smart Banners podem afetar sua compatibilidade com a acessibilidade relevante, incluindo, por exemplo, a edição de cores e tamanho dos elementos internos do banner.

</Accordion>

<div id="if-a-smart-banner-is-deleted-from-a-banner-group-will-the-data-associated-with-that-banner-group-also-be-removed" />

<Accordion title="Se um Smart Banner for excluído de um grupo de banners, os dados associados a esse grupo também serão removidos?">

Não. Os dados de atribuição não são excluídos se um Smart Banner for excluído.

</Accordion>

<div id="troubleshooting--traits-and-limitations" />

## Identificação e solução de problemas, características e limitações

| Caraterística | Observações |
| --- | --- |
| Divisão de exibição | A AppsFlyer divide uniformemente a exibição de banners ativos para os usuários. Não é possível selecionar quais banners específicos serão exibidos com maior ou menor frequência. Por exemplo, se houver 2 banners em um grupo, cada um será exibido para 50% dos usuários. Isso não pode ser alterado para uma divisão 70%-30%. |
| Parâmetros personalizados | • Os seguintes caracteres especiais não são permitidos em parâmetros personalizados: ;, *, !, @, #, ?, $, ^, :, &, ~, \`, =, +, ', >, &lt;, / • Se você definir um parâmetro usando um desses caracteres especiais, o parâmetro não será salvo. |
| Mudança de nome | Os nomes dos grupos de banners e nomes dos banners podem ser alterados. Os dados de performance não são afetados. |
| Número de cliques/fechamentos em um botão | Os dados estão disponíveis a partir de 17 de fevereiro de 2026. Os dados são armazenados por 90 dias. |
| Página específica | Quando você configura seu grupo de banners para exibir banners em uma determinada página, a regra do banner se aplica somente ao host/caminho inserido. Se não houver uma correspondência perfeita (por exemplo, se a página do site tiver cadeias de caracteres adicionais não incluídas na configuração da regra), a regra não se aplica. |
| Tablets | • Os Smart Banners são projetados para dispositivos mobile e suas resoluções talvez não sejam otimizadas para tablets com telas grandes. • Navegadores em tablets podem não ser reconhecidos como dispositivos mobile. |
| O banner é exibido ao lado de uma área desocupada | Quando se deparar com esse comportamento, avalie a sua possível causa utilizando os seguintes critérios:<ul><li>Verifique se o trecho de código do SDK não foi implementado mais de uma vez na página da web.</li><li>Certificar-se de que a função <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_smart_banner_v2#showbanner">`showBanner`</Anchor> não foi invocada várias vezes.</li></ul> |

<div data-zendesk-anchors="h_01HB5W700P3GP7JS4PFDF65EWT=nota h_01HB5W700PWY5G45BYNWPKAC52=smart-banners h_01HB5W700QQMYSEFBBXVJ97M0M=exemplo h_01HB5W700QGWTWDXBNB2GAPQ3B=importante setup=configura%C3%A7%C3%A3o h_01HB5W700QVNYJT48VAP9Y7HQS=configura%C3%A7%C3%A3o h_01HB5W700Q7G5E98V0DBN9P5VZ=1-website-workplace-setup prepare-your-mobile-site-to-display-smart-banners-for-the-first-time=prepare-seu-site-mobile-para-exibir-smart-banners-pela-primeira-vez h_01HB5W700QE7MDBSN5GH4E7ABR=prepare-seu-site-mobile-para-exibir-smart-banners-pela-primeira-vez to-create-website-workplaces-after-the-first-time=para-criar-workplaces-do-site-ap%C3%B3s-a-primeira-vez h_01HB5W700Q57WXKFSWXNF22QZ1=para-criar-workplaces-do-site-ap%C3%B3s-a-primeira-vez h_01HB5W700QY1FH2SYX6DM4HDEQ=2-banner-group-setup h_01HDH1BQSXCQV9QCJGZ4VNXGPQ=importante-1 h_01HB5W700QYJ9NR5F4VT59NG2Q=exemplo-1 targeting-behavior=direcionamento-e-comportamento h_01HB5W700QYC48YTJY9B8JT0XM=direcionamento-e-comportamento h_01HB5W700QG54YYQFHGA2J41RY=3-banner-setup h_01HB5W700QD0WKNAP5X6T9E6DQ=exemplo-2 h_01HB5W700QX5J59BBK1AV7VFV6=4-testing view-banner-performance=visualizar-a-performance-do-banner h_01HB5W700Q6WHMVFNSVM2E9JXN=visualizar-a-performance-do-banner h_01HB5W700QEP46WV78KEYD1RT1=performance-page h_01HB5W700QZ705H5EE0PFHB1KY=performance-cards additional-information=informa%C3%A7%C3%B5es-adicionais h_01HB5W700Q9XD8MGEK0B3ZZJS3=informa%C3%A7%C3%B5es-adicionais h_01HB5W700QHW078W3RRCB81AWM=banner-group-display-logic h_01HB5W700QNYT482FR0FRHP2DC=ab-testing-banner-performance faq=perguntas-frequentes h_01HB5W700Q90F1KMASF94EZWEM=perguntas-frequentes h_01HB5W700Q1ZP3RAR94T41SXK2=why-does-my-banner-not-display h_01HB5W700QKBVFQHH9D8WD36R2=can-i-use-my-own-font-for-my-banner h_01HB5W700R2AJC2C1PRT5PTH8G=can-i-add-parameters-to-the-url-of-my-smart-banners h_01HB5W700RAVG10QZDBPXWT14G=do-smart-banners-support-deep-linking h_01HB5W700R12DSA6HF4HVWGW9P=can-smart-banners-show-different-content-based-on-whether-or-not-users-have-the-app-installed h_01HB5W700RT122T2M6NXFPSXDV=do-original-incoming-url-parameters-remain-available-for-the-smart-banner-url-when-users-navigate-away-from-and-then-return-to-the-banners-landing-page h_01HB5W700RH40FGHWVJ9J31R9F=can-i-set-my-banners-to-display-on-my-mobile-site-but-not-on-my-wrapperhybrid-app h_01HB5W700R11SHAKV5W21MXCX8=do-smart-banners-support-web-accessibility h_01JSVH17EH97S8B7EBCD4QHS1Q=if-a-smart-banner-is-deleted-from-a-banner-group-will-the-data-associated-with-that-banner-group-also-be-removed traits-and-limitations=identifica%C3%A7%C3%A3o-e-solu%C3%A7%C3%A3o-de-problemas-caracter%C3%ADsticas-e-limita%C3%A7%C3%B5es h_01HB5W700RXHC22QGXDX4GG1AR=identifica%C3%A7%C3%A3o-e-solu%C3%A7%C3%A3o-de-problemas-caracter%C3%ADsticas-e-limita%C3%A7%C3%B5es" />
