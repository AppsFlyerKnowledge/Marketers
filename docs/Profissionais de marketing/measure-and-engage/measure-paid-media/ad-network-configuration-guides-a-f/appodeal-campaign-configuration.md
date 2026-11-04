---
title: Configuração de campanha Appodeal
metadata:
  keywords:
    - ad revenue
    - cost
    - Advertisers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2019-12-17T19:36:02Z'
  edited_at: '2026-08-19T00:24:14Z'
  id: 360004404977
  locale: pt
  section: Ad network configuration guides (A-F)
  section_id: 6551990971793
  url: https://support.appsflyer.com/hc/pt/articles/360004404977
---
> **Em resumo:** a Appodeal, parceira integrada da AppsFlyer, oferece aos proprietários de aplicativos atribuição de cliques e uma solução completa de monetização de anúncios. A receita de anúncios é reportada com granularidade em nível de usuário.

<div id="setting-up-appodeal-integration" />

## Como configurar a integração da Appodeal

![](https://cdn.appsflyer.com/marketplace/static/logo/appodeal.png)

A integração da AppsFlyer com a Appodeal oferece suporte à atribuição de cliques e à <Anchor target="_blank" href="/marketers/pt/docs/roi360-guide-ad-revenue-attribution#ad-revenue-raw-data">atribuição da receita de anúncios no nível do usuário.</Anchor>

**Pré-requisito:** antes de configurar a integração, certifique-se de [entrar em contato com o parceiro](#) e abrir uma conta com ele. Antes de criar uma integração, certifique-se de <Anchor target="_blank" href="/marketers/pt/docs/partner-integrations#contact-details">entrar em contato com o parceiro</Anchor> e abrir uma conta com ele.

**Para ativar a integração:**

1. Na aba **Integração**, habilite **Ativar parceiro**.  
   **Para editar**: **Na AppsFlyer, vá para o menu lateral e selecione** Colaborar **>** **Integrações ativas**.
2. Selecione o aplicativo correspondente.
3. Na aba **Integração** selecione **Ativar parceiro**.
4. No **Primeira visita** Aqui, você precisará ativar **Ativar parceiro** para habilitar a configuração dos parâmetros de integração. O botão deve permanecer ativado enquanto você trabalhar com o Medialyzer. Saiba mais sobre <Anchor target="_blank" href="/marketers/pt/docs/partner-activation-deactivation">a ativação de parceiros</Anchor>.
5. Complete a configuração utilizando as abas relevantes, conforme descrito abaixo:

<div id="integration" />

<Accordion title="integração">

Configure esta seção se a Appodeal fornecer serviços de publicidade de ad network.

**Para ativar a integração**:

1. Ative **Ativar parceiro.**
2. Clique em **Salvar Integração**.

</Accordion>

<div id="attribution-link" />

<Accordion title="Link de atribuição">

Gere links de atribuição de cliques (para uso pela Appodeal) nesta aba. <Anchor target="_blank" href="/marketers/pt/docs/about-link-structure-and-parameters">Saiba mais sobre a estrutura do link e os parâmetros</Anchor>.

**Para gerar um link de atribuição**:

1. Selecione um parâmetro na lista suspensa Nome do parâmetro e defina um valor.
2. Clique em **Adicionar parâmetro** e repita a etapa anterior para adicionar mais parâmetros.
3. Defina a duração da **janela de lookback de cliques.**
4. Copie o link de atribuição de cliques e envie-o para a ad network.  
   Observação: a AppsFlyer não salva links.

**Link de atribuição e janela de lookback**

| Tipo de link de atribuição | Ativação do link | Janela de lookback |
| --- | --- | --- |
| CLIQUE | Um usuário clica em um anúncio veiculado pela ad network | **A janela de lookback de cliques** é predefinida; é o **tempo máximo permitido entre o clique e a instalação**.<br /><br />Exemplo: uma instalação (primeira abertura) feita após o clique—mas antes do vencimento da janela de lookback—é atribuída à Appodeal.<br /><br />**Nome do parâmetro**: `af_click_lookback`  <br />**Valor padrão**: 7 dias  <br />**Intervalo:** 1 a 23 horas ou 1 a 30 dias |

**Parâmetros típicos do link**

| Parâmetro | Nome do parâmetro | A descrição |
| --- | --- | --- |
| Campaign | C | Nome da campanha |
| Conjunto de anúncios | af\_adset | Use para diferenciar conjuntos de anúncios. |
| Ad name | af\_ad | Use para diferenciar entre criativos dentro do conjunto de anúncios. |
| ID do site | af\_siteid  <br />af\_subsiteid | Use para atribuir instalações a publishers específicos.<br /><br />**Boa prática!** Se houver vários publishers,<ul><li>Limite o número de IDs de site em uso</li><li>Use o parâmetro de ID de subsite para evitar <Anchor target="_blank" href="/marketers/pt/docs/measure-exceeded-dimensions-and-cardinality-limits#exceeded_siteid_limit">exceder o limite de ID de site</Anchor></li></ul> |
| Parâmetros do assinante | af\_sub1, af\_sub2, af\_sub3, af\_sub4 e af\_sub5 | Use para inserir valores.<ul><li>Os parâmetros são analisados e incluídos no relatório de dados brutos.</li><li>Use-os para agregar ou filtrar dados</li></ul> |

</Accordion>

<div id="cost" />

<Accordion title="Custo (3)">

A Appodeal envia dados de custo de CPI pelo link de atribuição.

</Accordion>

<div id="ad-revenue" />

<Accordion title="Ad revenue">

* A Appodeal oferece mediação de receita de anúncios com <Anchor target="_blank" href="/marketers/pt/docs/roi360-guide-ad-revenue-attribution#ad-revenue-raw-data">granularidade no nível do usuário</Anchor>
* Saiba mais sobre a <Anchor target="_blank" href="/marketers/pt/docs/roi360-guide-ad-revenue-attribution">atribuição de receita de anúncios da AppsFlyer</Anchor>

**Para ativar a API de receita publicitária**:

* Siga <Anchor target="_blank" href="/marketers/pt/docs/roi360-guide-ad-revenue-attribution#connect-to-ad-revenue-integrated-partners">estas instruções de integração.</Anchor>

</Accordion>

<div id="permissions" />

<Accordion title="Authorization: Bearer">

Nenhuma permissão precisa ser definida para a Appodeal.

</Accordion>

<div data-zendesk-anchors="setting-up-appodeal-integration=como-configurar-a-integra%C3%A7%C3%A3o-da-appodeal h_01HKW9BK4ZAR4Q22Z9WBVFPPT7=como-configurar-a-integra%C3%A7%C3%A3o-da-appodeal h_01HKW9BK4ZDFDX9X7P2HW4QR1P=integration h_01HKW9BK4ZM4JMQKT4Y8ZC050V=attribution-link h_01HKW9BK4ZV8DWSZQ55332NQWY=cost h_01HKW9BK4ZS3GYMZ6E9T64PPGC=ad-revenue h_01HKW9BK4ZJ1F1Z099NJHRZRNE=permissions" />
