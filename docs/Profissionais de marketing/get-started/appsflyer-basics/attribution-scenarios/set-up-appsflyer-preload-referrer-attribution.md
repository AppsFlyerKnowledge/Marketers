---
title: Atribuição de preload referrer da AppsFlyer
metadata:
  keywords:
    - Advertisers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-alina-koifman
    - Marketers
    - Mobile Attribution
  created_at: '2022-03-02T09:54:10Z'
  edited_at: '2026-09-16T00:09:45Z'
  id: 4543811207313
  locale: pt
  section: Attribution scenarios
  section_id: 6551328497041
  url: https://support.appsflyer.com/hc/pt/articles/4543811207313
---
> **Resumo:** a AppsFlyer usa o preload referrer para atribuir instalações a campanhas de preload, nas quais os profissionais de marketing entram em contato com fabricantes de equipamentos originais (OEMs), operadoras móveis e parceiros de descoberta de aplicativos para fazer a pré-instalação seu aplicativo na fábrica ou no momento em que o dispositivo é ligado pela primeira vez pelo usuário.

<div id="overview" />

## Visão geral

Em campanhas de preload, OEMs, operadoras de celular e parceiros de descoberta de aplicativos fazem a pré-instalação de aplicativos nos dispositivos, antes que eles cheguem a um usuário. Isso pode ser feito pelo OEM na fábrica ou pelos fornecedores na primeira ativação do dispositivo.

As campanhas de preload permitem que os anunciantes alcancem uma audiência ampla sem executar campanhas online.

A atribuição do preload referrer (1 de 3 <Anchor target="_blank" href="/marketers/pt/docs/appsflyer-attribution-model#preload-campaigns">métodos de atribuição de preload</Anchor>) fornece aos profissionais de marketing um mecanismo preciso e protegido para mensurar a performance de campanhas de preload. Esse método traz resultados de atribuição determinísticos e, simultaneamente, garante que a privacidade do usuário dique protegida, pois a atribuição é realizada por meio da correspondência do referrer com um referrer gerado de forma independente do dispositivo e dos identificadores de usuário.

A solução oferece:

* Suporte transparente com atualizações e redownloads de aplicativos.
* Visibilidade e recursos de mensuração entre a primeira ativação do dispositivo e a primeira inicialização do app. Isso permite que você veja quantos dispositivos foram ativados com o app pré-instalado por um parceiro específico e, posteriormente, que você veja quando o app foi iniciado pela primeira vez.

<div id="partners-supporting-preload-referrer-campaigns" />

## Parceiros que oferecem suporte para campanhas de preload referrer

As informações neste artigo são relevantes para anunciantes que estão integrados com os parceiros especificados na tabela abaixo:

<table><thead><tr><th rowspan="2">Parceiro</th><th rowspan="2">PID</th><th colspan="2">Opções de campanha de preload referrer <a href="./set-up-appsflyer-preload-referrer-attribution#opções-de-preload-referrer"><span>Saiba mais.</span> </a> </th></tr><tr><th>Pré-carga</th><th>Click-to-download</th></tr></thead><tbody><tr><td><a href="#preload-referrer-da-samsung">Samsung</a></td><td>samsung_int</td><td><span>✓</span></td><td> </td></tr><tr><td>Digital Turbine On Device</td><td>digitalturbine_int</td><td><span>✓</span></td><td>Em breve</td></tr><tr><td>Aura from Unity</td><td>aura_int</td><td><span>✓</span></td><td>Em breve</td></tr><tr><td>Appnext</td><td>appnext_int</td><td><span>✓</span></td><td>Em breve</td></tr><tr><td>Glance<br/> </td><td>glance_int</td><td><span>✓</span></td><td><span>✓</span></td></tr></tbody></table>

<div id="preload-referrer-options" />

## Opções de preload referrer

Os referrers podem ser usados para atribuir instalações por preload ou por click-to-download. Vjea a tabela a seguir para mais detalhes.

A AppsFlyer dá a maior prioridade à atribuição de preload. Isso significa que, se um usuário interagir com outras campanhas antes de abrir o aplicativo pela primeira vez, a atribuição será concedida à campanha de preload. Outros engajamentos são considerados como instalações assistidas. **Atenção:** você pode habilitar uma prioridade equitativa para engajamentos de preload. Assim, os engajamentos de preload recebem a mesma prioridade de atribuição que os cliques determinísticos para toda a janela de lookback de preload. Portanto, a atribuição à campanha de preload não pode ser substituída por outro engajamento com um anúncio.

| Opção de referrer | Descrição | Tipo de correspondência de dados brutos de instalações de UA |
| --- | --- | --- |
| Pré-carga | <ul><li>O aplicativo é pré-instalado na fábrica ou na primeira vez que o dispositivo é ativado. Ou então, um assistente sugere que os usuários façam o download do aplicativo quando o dispositivo é ativado pela primeira vez.</li><li>Um evento de preload, equivalente a um clique, é relatado à AppsFlyer quando o dispositivo é ligado pela primeira vez.</li><li>A atribuição ocorre quando o usuário abre o app pela primeira vez.</li><li>O evento de preload tem a prioridade de atribuição mais alta (a não ser que a prioridade equitativa esteja ativada).</li></ul> | `preload_rfr` |
| Click-to-download | <ul><li>A instalação do aplicativo ocorre posteriormente no ciclo de vida do dispositivo, por meio de notificações push, lojas alternativas de parceiros, etc.</li><li>Quando o usuário interage com um anúncio ou com uma mensagem push, o app é baixado e instalado automaticamente no dispositivo sem redirecionar para uma loja de aplicativos.</li><li>A atribuição é feita usando as regras de último clique da AppsFlyer.</li></ul> | `af_referrer` |

<div id="view-preload-attribution-data" />

## Ver dados de atribuição de preload

Os dados de performance da campanha de preload/click-to-download estão disponíveis da seguinte forma:

* Os engajamentos contam como cliques em relatórios e dashboards agregados. Eles são agregados no parceiro de preload (fonte de mídia) e nos níveis de campanha.
* **Dados brutos:** Os engajamentos estão disponíveis nos relatórios de cliques disponíveis via Data Locker. Eles são encontrados no campo URL original e podem ser identificados no parâmetro af\_engagement\_type como preload ou click\_to\_download. Para instalações, consulte a tabela na seção anterior para ver como o tipo de correspondência é exibido em dados brutos.

<div id="set-up-preload-referrer-attribution" />

## Configurar a atribuição do preload referrer

**Pré-requisitos:**

* Integre o <Anchor target="_blank" href="/marketers/pt/docs/appsflyer-android-sdk-release-notes">Android SDK 6.10.1+</Anchor> da AppsFlyer.
* Contrato com um parceiro de preload da AppsFlyer.

**Para configurar a atribuição do preload referrer**:

1. No AppsFlyer, no menu lateral, selecione **Colaborar** > **Integrações de parceiros** > **Integrações ativas**.
2. Selecione o parceiro de preload.
3. Na aba **Integração**, ative **a atribuição de preload**.  
   <Image align="center" alt="" src="https://files.readme.io/d2c08125ca318b4bde60b51668692f21b88e292ca1b3f4fef54b77df779815cb-15585078780433.png" width="538px" />
4. Configure a duração da **janela de lookback de preload**. Intervalo: 1-180 dias.
5. [Opcional] Ative a **Prioridade equitativa para atribuição de preload**.  
   Isso dá aos cliques determinísticos a mesma prioridade de atribuição que a atribuição de preload, o que significa que, se um clique determinístico for registrado entre o engajamento do preload referrer e a instalação, o clique receberá a atribuição sob a lógica de atribuição de último toque padrão, em vez de ser substituído pelo preload referrer.
6. Clique em **Salvar integração**.
7. Informe ao parceiro de preload que você está pronto para atribuir suas campanhas.

<div id="samsung-preload-referrer" />

## Preload referrer da Samsung

A integração do preload referrer da Samsung com a AppsFlyer permite que você tenha uma visão detalhada desde o download inicial do app até sua primeira abertura, permitindo uma compreensão mais clara do comportamento do usuário.

<div id="set-up-samsung-preload-referrer-attribution" />

### Configurar a atribuição de preload referrer da Samsung

Para configurar a atribuição de preload referrer da Samsung, consulte as [instruções gerais para preload referrers](#configurar-a-atribuição-do-preload-referrer).

<div id="traits-and-limitations" />

### Características e limitações

As características específicas do preload referrer da Samsung são as seguintes:

| Caraterística | Observações |
| --- | --- |
| Nome da integração | samsung\_int |
| Versão do SDK | v6.16.0 |
| Tipo de correspondência | `preload_rfr` |
| Dashboard de Visão Geral | Dahsboard de Visão Geral Os engajamentos são considerados como cliques em relatórios e dashboards agregados. Eles são agregados no parceiro de preload (fonte de mídia) e nos níveis de campanha. |
| Relatórios de dados brutos | <ul><li>Os engajamentos estão disponíveis nos relatórios de cliques somente por meio do Data Locker.</li><li>Nos relatórios de instalação, os eventos de preload NÃO são encontrados na URL original devido às restrições de privacidade da Samsung.</li><li>Eles podem ser identificados no parâmetro `af_engagement_type` como `preload`.</li></ul> |

<div data-zendesk-anchors="appsflyer-preload-referrer-attribution=vis%C3%A3o-geral h_01HEKAF7K41PH189PSCKBRF070=vis%C3%A3o-geral partners-supporting-preload-referrer-campaigns=parceiros-que-oferecem-suporte-para-campanhas-de-preload-referrer h_01HEKAF7K5CWX2P9TY8M0MTQAM=parceiros-que-oferecem-suporte-para-campanhas-de-preload-referrer preload-referrer-options=op%C3%A7%C3%B5es-de-preload-referrer h_01HEKAF7K4H3HNAMEYM6C58Y29=op%C3%A7%C3%B5es-de-preload-referrer view-preload-attribution-data=ver-dados-de-atribui%C3%A7%C3%A3o-de-preload h_01HEKAF7K4GJDDPHCFTTC75YBS=ver-dados-de-atribui%C3%A7%C3%A3o-de-preload set-up-preload-referrer-attribution=configurar-a-atribui%C3%A7%C3%A3o-do-preload-referrer h_01HEKAF7K41RBRVXC6GF6PCN3Y=configurar-a-atribui%C3%A7%C3%A3o-do-preload-referrer samsung-preload-referrer=preload-referrer-da-samsung h_01JCB6K81QRK2NM983SJBYD9M3=preload-referrer-da-samsung set-up-samsung-preload-referrer-attribution=configurar-a-atribui%C3%A7%C3%A3o-de-preload-referrer-da-samsung h_01M2JCPMNY1ZACWQTDDGZCF2X9=configurar-a-atribui%C3%A7%C3%A3o-de-preload-referrer-da-samsung traits-and-limitation=caracter%C3%ADsticas-e-limita%C3%A7%C3%B5es h_01JDPYAV86PT14C91ZQ2D9XTZ2=caracter%C3%ADsticas-e-limita%C3%A7%C3%B5es" />
