---
title: Configuração da campanha do Petal Ads Global (anteriormente HUAWEI Ads global)
metadata:
  keywords:
    - integrated partner
    - Advertisers
    - Agencies
    - huawei
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
    - Agencies
  created_at: '2020-06-28T08:40:00Z'
  edited_at: '2026-09-10T00:25:10Z'
  id: 360010605858
  locale: pt
  section: Ad network configuration guides (G-Q)
  section_id: 6552006535953
  url: https://support.appsflyer.com/hc/pt/articles/360010605858
---
> **Em resumo:** Petal Ads Global, um parceiro integrado da AppsFlyer, é um serviço de apresentação pago, fornecido pela Huawei para parceiros de todo o ecossistema. Ele tem como objetivo ajudar os parceiros a estabelecer uma ponte de comunicação com os usuários de dispositivos Huawei, para que possam fornecer informações valiosas e serviços de qualidade aos usuários. O Petal Ads Global oferece espaços para exibição de anúncios populares, como anúncios nativos, anúncios em vídeo recompensado, anúncios de banner e anúncios intersticiais, para mais de 570 milhões de usuários de dispositivos Huawei em todo o mundo.

<Image align="center" alt="huaweiadsglobal.png" src="https://files.readme.io/12f1351923768c1afc1ba0f16b267388a8c9b1ae7fc2d6d36b5d1d01381f1bbc-14151449726353.png" width="18.53%" />

<div id="petal-ads-global-introduction" />

## Introdução ao Petal Ads Global

O Petal Ads Global está integrado a vários aplicativos de terceiros e aplicativos da Huawei, como HUAWEI Browser, HUAWEI Video, HUAWEI Assistant, HUAWEI Reader e HUAWEI Music, que são subpublishers da rede de display do Petal Ads Global. Além disso, os posicionamentos padrão de anúncio da AppGallery e o App Gallery Search Ads também oferecem suporte à atribuição da AppsFlyer.

<div id="setting-up-petal-ads-global" />

## Configurar o Petal Ads Global

O Petal Ads Global exige o uso do **OAID** para atribuição. Consulte <Anchor target="_blank" href="/marketers/pt/docs/android-oaid-implementation-in-the-sdk">**nosso guia Implementação de OAID no Android no SDK**</Anchor> para obter o OAID em dispositivos HUAWEI. Além disso, o Petal Ads Global recomenda fortemente a **atribuição de referenciador da HUAWEI App Gallery** para os aplicativos na loja. Para habilitar a atribuição de referenciador da Huawei, atualize o SDK do Android para 6.14.0 ou superior.

| Fonte de tráfego | Valor do canal | Métodos de atribuição | Atenção |
| --- | --- | --- | --- |
| Anúncios de display | huaweiadsglobal | Correspondência de ID (OAID ou GAID), Modelo probabilístico, Referrer da Huawei | Clique <Anchor target="_blank" href="/marketers/pt/docs/android-oaid-implementation-in-the-sdk">aqui</Anchor> para consultar o guia de implementação do OAID no SDK do Android. A atribuição de referenciador da Huawei requer o SDK do Android 6.14.0 |
| AppGallery | huaweiappgalleryglobal | Correspondência de ID (OAID ou GAID), Referrer da Huawei | A atribuição de referenciador da Huawei requer o SDK do Android 6.14.0 |
| Petal Search | valor em branco | Correspondência de ID (OAID ou GAID), modelo probabilístico | Clique <Anchor target="_blank" href="/marketers/pt/docs/android-oaid-implementation-in-the-sdk">aqui</Anchor> para verificar o guia de implementação do OAID no SDK do Android |

<div id="setting-up-the-petal-ads-global-integration" />

### Configuração da integração do Petal Ads Global

**Pré-requisito:** antes de configurar a integração, certifique-se de [entrar em contato com o parceiro](#) e abrir uma conta com ele. Antes de criar uma integração, certifique-se de <Anchor target="_blank" href="/marketers/pt/docs/partner-integrations#contact-details">entrar em contato com o parceiro</Anchor> e abrir uma conta com ele.

**Para ativar a integração:**

1. **Para ativar:** na AppsFlyer, no menu lateral, selecione **Colaborar** > **Partner Marketplace**.  
   Para editar: vá para **colaborar** > **integrações ativas**.
2. Selecione o aplicativo correspondente.
3. Na aba **Integração**, selecione o aplicativo e clique em **Ativar parceiro**.
4. Na aba **Integração**, selecione o aplicativo e ative a opção **Ativar parceiro**.  
    **Atenção:** **o toggle deve permanecer ligado ([ativado](#)) enquanto você trabalhar com o parceiro. [Saiba mais sobre a ativação de parceiros](#).**
5. Complete a configuração utilizando as abas relevantes, conforme descrito abaixo. Para obter uma descrição detalhada do cabeçalho da janela de configuração do parceiro, clique <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#about-the-integrated-partner-page">aqui</Anchor>.

<div id="integration-tab" />

<Accordion title="Aba Integração">

A guia **Integração** é dividida em diferentes seções:

<div id="activate-partner" />

#### Ativar parceiro

Para habilitar a configuração, <Anchor target="_blank" href="/marketers/pt/docs/partner-activation-deactivation#ativar-uma-integração-de-parceiro">ative o parceiro</Anchor>.

Esta alternância deve permanecer ativada enquanto você trabalhar com o parceiro.

<div id="general-settings" />

#### Configurações gerais

**Ative a atribuição de view-through**

Para atribuir instalações view-through do Petal Ads Global, ative esta alternância. O controle deslizante da janela de lookback de view-through está disponível na guia **Link de atribuição**.

<div id="default-postbacks" />

#### Postbacks padrão

Envie postbacks automáticos para o Petal Ads Global após instalações de usuários atribuídos somente ao Petal Ads Global. Saiba mais sobre <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#default-postbacks">postbacks padrão</Anchor>.

<div id="in-app-events-settings" />

#### Configurações de eventos in-app

Configure os postbacks de eventos in-app enviados ao Petal Ads Global.

**Para configurar os postbacks de eventos na aplicação:**

1. Ative **Postbacks de eventos in-app**.
2. Configure a <Anchor target="_blank" href="/marketers/pt/docs/in-app-event-postback-configuration#janela-de-postback-de-eventos-in-app">**janela de postback de eventos in-app**</Anchor>.
3. Para adicionar um evento SDK à lista, clique em **Adicionar evento**.
4. Selecione os seguintes parâmetros para cada evento:

| Nome do parâmetro | A descrição |
| --- | --- |
| **Nome do evento do SDK** | O nome do evento, conforme recebido pelo AppsFlyer ou do SDK ou de eventos de servidor para servidor.  <br />**Dica**: Se você não vir o evento desejado na lista, ative esse evento em um dispositivo com uma instalação não orgânica e verifique novamente. |
| **Identificador de evento do parceiro** | Insira o nome exclusivo ou ID de cada evento conforme definido no Petal Ads Global. Selecione o evento predefinido mais adequado entre 68 opções para seu evento SDK, por exemplo:<ul><li>`browse` (navegação)</li><li>`collection` (adição aos favoritos)</li><li>`addToCart` (adição ao carrinho de compras)</li><li>`preOrder` (realização do pedido)</li><li>`register` (cadastro)</li><li>`retain` (retenção no dia seguinte)</li><li>`paid` (pagamento realizado)</li><li>`custom` (evento do tipo personalizado)</li></ul> |
| **Opção de envio** | Os postbacks podem ser enviados somente para os eventos realizados por usuários atribuídos ao Petal Ads Global. |
| **Enviar dados do evento** | <ul><li>**Sem valores & sem receita:** envie apenas o evento em si, sem o valor do evento.</li><li>**Valores & sem receita:** Envie todos os parâmetros, com exceção do valor da receita.</li><li>**Valores & receita**: Envie todos os parâmetros do evento, incluindo o valor da receita (se existir no evento).</li></ul> |

5. Clique em **Salvar Integração**.

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Separador de Links de Atribuição">

Crie e salve links de atribuição e envie-os ao parceiro para atribuição de campanhas específicas, conjuntos de anúncios ou anúncios únicos - tanto para UA como para campanhas de retargeting. Você pode usar um link de plataforma única ou um OneLink.  
<Anchor target="_blank" href="/marketers/pt/docs/about-link-structure-and-parameters">Saiba mais sobre a estrutura de links de atribuição e parâmetros</Anchor>.

**Para gerar um link de atribuição,** siga <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#attribution-link-tab">estas instruções</Anchor>.  
Ao gerar o link de atribuição, selecione os parâmetros da lista abaixo e mapeie-os para o nome dos parâmetros globais do Petal Ads detalhado na tabela.

**Parâmetros de link de atribuição**

| Parâmetro | Nome do parâmetro | Macro do Petal Ads Global | A descrição |
| --- | --- | --- | --- |
| Campaign | c  <br />af\_c\_id | \_\_CID\_\_ | Adicione para comparar diferentes campanhas em execução no Petal Ads Global. |
| Conjunto de anúncios | af\_adset  <br />af\_adset\_id | \_\_ADSETID\_\_ | Use para diferenciar conjuntos de anúncios. |
| As ad | af\_ad  <br />af\_ad\_id | \_\_ADID\_\_ | Use para diferenciar os criativos dentro do conjunto de anúncios. |
| ID do site e do subsite | af\_siteid  <br />af\_subsiteid | \_\_SITEID\_\_ | Use para atribuir instalações a publishers específicos.<br /><br />**Boa prática!** Se houver vários publishers,<ul><li>Limite o número de IDs de site em uso.</li><li>Use o parâmetro de ID do subsite para evitar <Anchor target="_blank" href="/marketers/pt/docs/measure-exceeded-dimensions-and-cardinality-limits#exceeded_siteid_limit">exceder o limite de ID do site</Anchor>.</li></ul> |
| Canal | af\_canal | \_\_CHANNEL\_\_ | Use para diferenciar os posicionamentos de anúncios.<br /><br />huaweiadsglobal<br /><br />huaweiappgalleryglobal<br /><br />Se o valor estiver em branco, então será huawei search ads. |
| Parâmetros do assinante | af\_sub1, af\_sub2, af\_sub3, af\_sub4 e af\_sub5 |  | Use para inserir valores adicionais úteis.<ul><li>Os parâmetros são analisados e incluídos no relatório de dados brutos.</li><li>Use-os para realizar a agregação ou a filtragem de dados.</li></ul> |
| Tipo de anúncio | af\_ad\_type | \_\_APP\_STATUS\_\_ | usado para distinguir se o aplicativo já foi ativado antes.<ul><li>se a campanha for usada para segmentação de usuários que instalaram, mas nunca abriram, o parâmetro será</li></ul>af\_ad\_type=installed<ul><li>se a campanha for usada para segmentação de usuários que nunca instalaram o aplicativo, o parâmetro será</li></ul>af\_ad\_type=notinstalled |

</Accordion>

<div id="cost-tab" />

<Accordion title="Aba de Custos">

Os dados de custos não são compatíveis com esse parceiro.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Receita de anúncios">

Os dados de receita de anúncios não são suportados por este parceiro.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Aba permissões">

Nesta aba, você pode selecionar as permissões para conceder ao Petal Ads Global. Observe que, mesmo que a atribuição esteja desativada para o Petal Ads Global, a aba de permissões fica ativa e você pode conceder controle ao Petal Ads Global.

<Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#permissions-tab">Saiba como conceder permissões ao Petal Ads Global.</Anchor>

</Accordion>

<div id="configuring-campaigns-on-petal-ads-global" />

## Configurando campanhas no Petal Ads Global

**Para configurar a atribuição do AppsFlyer no Petal Ads Global, clique** [**aqui**](https://developer.huawei.com/consumer/en/doc/distribution/promotion/appsflyer-0000001122291488) **para saber mais no Huawei Support Center.**

1. <span id="EN-US_TOPIC_0000001122291488__li7712141055015"></span><span id="EN-US_TOPIC_0000001122291488__en-us_topic_0000001122291488_ol75772831710"></span>Obtenha as URLs de rastreamento de impressões e cliques no AppsFlyer.
2. Associe o AppsFlyer ao Petal Ads Global.
3. Defina o postback de dados no AppsFlyer.
4. Crie uma conversão no Petal Ads Global.
5. Teste a conversão no Petal Ads Global.
6. Crie uma tarefa de anúncio no Petal Ads Global.
7. [Visualize os dados de conversão](https://developer.huawei.com/consumer/en/doc/distribution/promotion/tracking-shu-0000001139892541) no Petal Ads Global.

<div id="data-discrepancies" />

## Discrepâncias de dados

**Observação：** No dashboard do Petal Ads Global, os dados de conversão (por exemplo, instalações/ativações) têm 2 fontes de dados: uma é o AppsFlyer e a outra é o HMS. Quando quiser comparar os dados, como instalações, entre o AppsFlyer e o dashboard do Petal Ads Global, selecione "Activations" em vez de "Activations(HMS)" no dashboard da Huawei.

<Image align="center" alt="" src="https://files.readme.io/fd2878d20c78ebc87d8536225882c8613396178b920c570677edc668dabb810e-360015414918.png" />

<div id="data-reporting-on-petal-ads-global-and-faqs-of-data-discrepancy" />

#### Relatórios de dados no Petal Ads Global e FAQs sobre discrepância de dados

| Métrico | Fonte de dados | Perguntas frequentes | A descrição |
| --- | --- | --- | --- |
| Impressions | Huawei | Impressões da Huawei &lt; impressões do AF | O AppsFlyer registra todas as impressões que a Huawei envia ao AF, enquanto o Petal Ads Global faz algum processamento de dados antes de exibir as impressões no dashboard do Petal Ads Global. |
| Cliques | Huawei | Cliques da Huawei &lt; cliques do AF | O AppsFlyer registra todos os cliques que a Huawei envia ao AF, enquanto o Petal Ads Global faz algum processamento de dados antes de exibir os cliques no Petal Ads Global. |
| Downloads | Huawei | n/d | O AF não tem essa métrica. |
| Ativações | As ativações são do AppsFlyer; Activations HMS é da Huawei | Ativações da Huawei > instalações do AF | As ativações da Huawei são as instalações do AF. A discrepância de dados é resultado de diferentes lógicas de relatórios de dados. <br /><br />Por exemplo, um usuário fez o download do aplicativo na AppGallery em 24 de dezembro e abriu o aplicativo pela primeira vez em 25 de dezembro. Nesse caso, o AF registrará a instalação em 25 de dezembro, enquanto o Petal Ads Global registrará essa ativação em 24 de dezembro. |
| Retenção do Day2 e outros eventos in-app | Para os que não são HMS, as fontes de dados são o AppsFlyer. | Huawei > AF | A discrepância de dados é resultado de diferentes lógicas de relatórios de dados. <br /><br />Seguindo o exemplo acima, o usuário se registrou no aplicativo em 26 de dezembro; o dashboard Overview do AF exibirá os dados de registro em 25 de dezembro, a mesma data da instalação. Enquanto isso, o dashboard de promoções do Petal Ads Global exibirá o registro em 24 de dezembro, a mesma data do download. |

<div data-zendesk-anchors="huawei-ads-introduction=introdu%C3%A7%C3%A3o-ao-petal-ads-global h_01HJQZWW4SH5E9C3VXYM6NNPBA=introdu%C3%A7%C3%A3o-ao-petal-ads-global setting-up-huawei-ads=configurar-o-petal-ads-global h_01HJQZWW4SQ3CDC1TP9NZGQHH5=configurar-o-petal-ads-global setting-up-the-petal-ads-global-integration=configura%C3%A7%C3%A3o-da-integra%C3%A7%C3%A3o-do-petal-ads-global h_01HJRA1NPKF36ZV8AB3PKGWMXS=configura%C3%A7%C3%A3o-da-integra%C3%A7%C3%A3o-do-petal-ads-global h_01HJQZWW4SPFQAKKPJCZ38YNV4=integration-tab activate-partner=ativar-parceiro h_01HJQZWW4TR0XVYFYWPGAQ2FMX=ativar-parceiro general-settings=configura%C3%A7%C3%B5es-gerais h_01HJQZWW4T9QYECWJKFN8SV5D5=configura%C3%A7%C3%B5es-gerais default-postbacks=postbacks-padr%C3%A3o h_01HJQZWW4T62ZJSH1RBGJSC8MY=postbacks-padr%C3%A3o inapp-events-settings=configura%C3%A7%C3%B5es-de-eventos-in-app h_01HJQZWW4T44X5H42KAR432VN7=configura%C3%A7%C3%B5es-de-eventos-in-app h_01HJQZWW4T7TEZ27VRFPFY7DKA=attribution-link-tab h_01HJQZWW4TGDKCV8Q7B80Y5ZWG=cost-tab h_01HJQZWW4T384J7GVEEJ2EQZ0N=ad-revenue-tab h_01HJQZWW4T2P0NZ51TSF8VDEBP=permissions-tab configuring-campaigns-on-huawei-ads-global=configurando-campanhas-no-petal-ads-global h_01HJQZWW4TEX7SDZSG03AK51H9=configurando-campanhas-no-petal-ads-global data-discrepancies=discrep%C3%A2ncias-de-dados h_01HJQZWW4VNTKP5R4KYWX80P5P=discrep%C3%A2ncias-de-dados data-reporting-on-huawei-ads-and-faqs-of-data-discrepancy=relat%C3%B3rios-de-dados-no-petal-ads-global-e-faqs-sobre-discrep%C3%A2ncia-de-dados h_01HJQZWW4VZV1R32TMGGEVNCVA=relat%C3%B3rios-de-dados-no-petal-ads-global-e-faqs-sobre-discrep%C3%A2ncia-de-dados" />
