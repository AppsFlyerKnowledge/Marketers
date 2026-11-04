---
title: Google Ads (AdWords)—custo e receita publicitária
metadata:
  keywords:
    - Advertisers
    - Marketers
    - ROI360
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-michael-talapov
    - Marketers
    - ROI360
  created_at: '2022-01-20T10:01:42Z'
  edited_at: '2026-08-22T00:28:01Z'
  id: 4417309205521
  locale: pt
  section: Google Ads
  section_id: 6551205645457
  url: https://support.appsflyer.com/hc/pt/articles/4417309205521
---
> **At a glance:** Ative os dados de custo e de receita de anúncios do Google Ads no AppsFlyer.

<div id="cost-clicks-and-impressions" />

## Custo, cliques e impressões

A integração de custos fornece os seguintes dados agregados:

* Dados de custo para suas campanhas, conjuntos de anúncios, geolocalização/países e níveis de canal. Consulte a <Anchor target="_blank" href="/marketers/pt/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api">tabela de integração de custos da ad network</Anchor> para obter detalhes completos sobre as dimensões, métricas e recursos compatíveis.**Observação:** os dados de custo exigem uma assinatura <Anchor target="_blank" href="/marketers/pt/docs/roi360-cost-aggregation-overview?query=xpend">ROI360</Anchor> .
* Dados sobre cliques, impressões e dados enriquecidos (palavras-chave, nomes de campanha e nomes de conjunto de anúncios).

> 📘 **Note**
>
> * Contas MCC são compatíveis.
> * Certifique-se de que a configuração da sua campanha no Google Ads seja para um aplicativo iOS ou Android; não para ambos. Se a campanha for para ambos os aplicativos, a AppsFlyer não poderá detalhar o custo por aplicativo e exibirá o custo combinado para ambos os aplicativos.
> * Os dados de custos, cliques e impressões atualmente não estão disponíveis para campanhas de pré-cadastro devido a limitações na API do Google Ads.

Para exibir os dados de custos, cliques e impressões do Google Ads dentro do painel da AppsFlyer, conecte-se através de sua página de configuração no Google Ads. Ao realizar a conexão, a AppsFlyer começa a consultar os valores de custo, cliques e impressões do Google Ads para todas as suas campanhas existentes.

Leia mais sobre como <Anchor target="_blank" href="/marketers/pt/docs/google-ads-adwords-integration-setup-for-advertisers#step-2-set-up-google-ads-on-appsflyer-mandatory">configurar o custo no Google Ads</Anchor>.

Leia mais sobre como o Google define cliques e visualizações.

Leia mais sobre as <Anchor target="_blank" href="https://support.google.com/google-ads/answer/6163740">limitações do Google Ads</Anchor>.

**Após a configuração, os dados devem ser enviados dentro de algumas horas**.

> 👍 **Tip**
>
> Os usuários podem confirmar se estão conectados com a conta correta do Google Ads verificando o endereço de e-mail que aparece no canto superior direito do painel do Google Ads.
>
> Se a conta do Google Ads for uma subconta de uma conta MCC, a ID do canto superior direito será da MCC e a ID da subconta aparecerá no canto superior esquerdo.
>
> Se não for a conta correta, saia da conta e faça login novamente usando o endereço de e-mail para uma conta do Google diferente.

<div id="cost-data-sync-status" />

### Status de sincronização dos dados de custo

<Anchor target="_blank" href="/marketers/pt/docs/set-up-roi360-cost-api-to-measure-cost-data#cost-api-status">Visualize o status da API de custo</Anchor> e a última vez que a AppsFlyer conseguiu extrair dados de custo correspondentes no painel de status de integração de custo (e receita de publicitária) ou no painel individual da ad network. 

O Google Adwords permite sincronizar várias contas para extração de dados de custo. Para cada conta sincronizada, a AppsFlyer exibe o status da integração de custo e a última vez que a AppsFlyer extraiu dados de custo correspondentes.

<div id="stopping-google-cost-sync" />

### Como interromper a sincronização de custo do Google

**Para parar de sincronizar o custo do Google, exclua a conexão da conta do Google:**

* <Anchor target="_blank" href="/marketers/pt/docs/set-up-roi360-cost-api-to-measure-cost-data#deleting-connected-accounts-in-the-cost-tab">Vá para a guia custo, na coluna ações, passe o mouse sobre uma conta, clique em Excluir conexão.</Anchor> Depois de excluída, a AppsFlyer deixa de receber o custo. Deletar a conexão não afeta os dados históricos.

<div id="recording-ad-revenue-with-google-ads" />

## Como gravar a receita publicitária com o Google Ads

A integração de receita do Google Ads (AdWords) foi descontinuada no dia 30 de novembro de 2020. Para dados de receita de anúncios, os clientes do Google AdWords precisam migrar para o <Anchor target="_blank" href="/marketers/pt/docs/google-admob-ad-revenue-attribution-configuration">Google AdMob</Anchor>.

<Accordion title="Perguntas frequentes">

**P.** Por que não consigo ver meus dados de custo?

**R.** Existem vários motivos possíveis pelos quais você não consegue ver os dados:

* Ao fazer login, é importante verificar se está sendo usada a conta correta do Google.Se você fizer login usando uma conta errada do Google, não é obtido ou exibido nenhum custo. Em tal situação, você deve remover o aplicativo das permissões de aplicativos do Google e fazer login com a conta correta. Para fazer isso, siga as etapas abaixo:
  1. Clique na seguinte URL: <Anchor target="_blank" href="https://myaccount.google.com/permissions">https://myaccount.google.com/permissions</Anchor>
  2. Remova o custo da AppsFlyer no Google e faça login novamente.
* Em alguns casos, a integração de custos da agência é ativada mas não extrai os custos porque o usuário da agência que fez o login não tem acesso ao ID correto do cliente do Google Ads. Isso faz com que o anunciante veja dados de custo incompletos.

  Certifique-se de que o usuário da agência que fizer login na aba Custo tenha acesso ao ID do cliente do Google Ads, configurado na aba Integração.

  <Image alt="" src="https://files.readme.io/2d17b3dad78e02c76253f30db0c15c18eb837b531becabc07ccad274258c2c61-49938966132753.png" width="457px" />
* Usar espaços ou caracteres especiais em pesquisa do iOS ou campanhas de página inicial do Android pode causar problemas de correspondência dos dados de custo com os dados de cliques e levar à falta de relatórios de custo.
* Quando uma agência desativa uma integração de custos após a coleta dos custos, mas o anunciante ainda tem uma integração de custos ativa, os dados são associados ao anunciante somente a partir do dia em que a agência desativa a integração.

**P.** Onde estão meus dados de cliques baseados em localização?

**R.** Em alguns casos, a Appsflyer recebe dados parciais de cliques por localidade do Google. Quando isso ocorre, a Appsflyer completa as informações de cliques faltantes a partir de outras fontes do Google, as quais não têm os dados de localidade. Portanto, ao realizar o agrupamento por localidade, o número total de cliques de campanhas do Google pode não corresponder ao mesmo número com outra dimensão de agrupamento.

</Accordion>

<Accordion title="Características e limitações">

| Caraterística | Observações |
| --- | --- |
| Campanhas inativas e ativas | A integração do Google é compatível com relatórios de custos para **campanhas inativas**, nos seguintes casos:<ul><li>Campanhas de apps para instalações (tipo de campanha ACI)</li><li>Campanhas de aplicativos para engajamentos (tipo de campanha ACE)</li><li>Campanhas inativas são campanhas para as quais nenhuma instalação ou conversão foi registrada na AppsFlyer.</li></ul>Para essas campanhas de aplicativo, a AppsFlyer detalha os dados de custo por canal, alinhados aos dados de atribuição. Por exemplo, ACI\_Display, ACI\_Youtube, ACI\_Search.<br /><br />Para campanhas que não são ACI nem ACE, a AppsFlyer informa os custos apenas para **campanhas ativas**, o que significa que pelo menos uma conversão ou instalação é registrada na AppsFlyer. Os custos são relatados para a janela de 7 dias da conversão/instalação. |
| Campanhas do Performance Max | As campanhas Performance Max não oferecem suporte ao detalhamento dos dados de custo por país/geolocalização. |

</Accordion>

**Veja também**

* Para considerações sobre o iOS 14, consulte <Anchor target="_blank" href="/marketers/pt/docs/get-skan-postback-data-from-google-ads">Interoperabilidade do Google Ads para SKAdNetwork com a AppsFlyer</Anchor>.

<div data-zendesk-anchors="cost-clicks-and-impressions=custo-cliques-e-impress%C3%B5es h_01HDP2SMHJ26S1BCER3KKZ8H14=custo-cliques-e-impress%C3%B5es cost-data-sync-status=status-de-sincroniza%C3%A7%C3%A3o-dos-dados-de-custo h_01HDP2SMHJT8Z6DP7BHC0Y5RRN=status-de-sincroniza%C3%A7%C3%A3o-dos-dados-de-custo stopping-google-cost-sync=como-interromper-a-sincroniza%C3%A7%C3%A3o-de-custo-do-google h_01HDP2SMHJPEDKKZF9SBXW56KG=como-interromper-a-sincroniza%C3%A7%C3%A3o-de-custo-do-google recording-ad-revenue-with-google-ads=como-gravar-a-receita-publicit%C3%A1ria-com-o-google-ads h_01HDP2SMHKC9TSZZZPFFNK8TPH=como-gravar-a-receita-publicit%C3%A1ria-com-o-google-ads" />
