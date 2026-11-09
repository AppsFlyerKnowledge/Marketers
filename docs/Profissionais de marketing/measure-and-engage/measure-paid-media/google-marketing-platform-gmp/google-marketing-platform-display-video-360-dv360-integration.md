---
title: >-
  Plataforma de Marketing do Google - Integração de Display & Video 360
  (DV360)
metadata:
  keywords:
    - Advertisers
    - Agencies
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
    - Agencies
  created_at: '2021-02-02T17:40:13Z'
  edited_at: '2026-09-10T12:29:09Z'
  id: 360017595598
  locale: pt
  section: Google Marketing Platform (GMP)
  section_id: 6551212604305
  url: https://support.appsflyer.com/hc/pt/articles/360017595598
---
> **Visão geral:** Google Marketing Platform - Display & Video 360 (GMP-DV360) é um parceiro da rede de auto-relato (SRN) da AppsFlyer que combina publicidade e análise. A integração GMP-DV360 (dv360\_int) combina publicidade e análise para melhorar as conexões com os clientes, revelar insights e melhorar os resultados de marketing.

<div id="important" />

> 🚧 **Importante!**
>
> Veja o novo boletim sobre nosso <Anchor target="_blank" href="/marketers/pt/docs/bulletin-supporting-the-new-google-eu-consent-policy">suporte para a nova política de consentimento do Google na UE</Anchor>.

<Image align="center" alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/doubleclick.png" width="121px" />

<div id="overview" />

## Visão geral

A integração GMP-DV360 utiliza o ID do link para a mensuração da conversão. Você pode trabalhar diretamente com o GMP-DV360, através de uma agência, ou ambos, utilizando as seguintes integrações:

* [DV360 para anunciantes](#configuração-do-gmp-dv360-para-anunciantes): Preencher uma vez-obrigatório
* [DV360 para agências](#configuração-do-gmp-dv360-para-agências): Opcional por agência

<div id="note" />

> 📘 **Observação**
>
> Lembre-se do seguinte:
>
> * A integração do GMP-DV360 foi concebida para substituir a  integraçãolegada do GMP DV360/CM (doubleclick\_int), que será descontinuada até ao final do segundo trimestre de 2024.
> * Para utilizar a API, contacte o seu gerente de conta GMP-DV360.

A tabela abaixo descreve as soluções de integração GMP:

| Solução GMP | Descrição | Ação necessária para a integração |
| --- | --- | --- |
| DV360 | Integrar o DV360 com a AppsFlyer para medir a atribuição do dv360\_int | Concluir a [integração do anunciante](#configuração-do-gmp-dv360-para-anunciantes) |
| CM360 & DV360 | Comprar tráfego DV360 via CM360, medido como atribuição dv360\_int na AppsFlyer. | Concluir a [integração do anunciante](#configuração-do-gmp-dv360-para-anunciantes) |
| CM360 + fonte de mídia externa que não seja DV360* | Comprar tráfego de fontes de mídia externa e medir conversões de aplicativos móveis originadas desse tráfego em CM360. | <Anchor target="_blank" href="/marketers/pt/docs/gmp-use-case-of-traffic-measurement-from-3rd-parties-in-cmp360">Medir o tráfego externo utilizando o CM360</Anchor> |

<div id="data-sharing-between-appsflyer-and-gmp---dv360" />

### Compartilhamento de dados entre a AppsFlyer e o GMP - DV360

**Dados fornecidos pela AppsFlyer:** A AppsFlyer envia postbacks para o GMP-DV360 relacionados a conversões e eventos in-app.

**Dados fornecidos à AppsFlyer:** Quando o GMP-DV360 solicita uma conversão, ele fornece à AppsFlyer os parâmetros da fonte de mídia. Estes parâmetros preenchem relatórios analíticos e de dados brutos. A tabela abaixo mostra os parâmetros de mapeamento para o GMP-DV360 e a AppsFlyer.

| GMP | A AppsFlyer |
| --- | --- |
| `Tipo de interação` | `tipo_de_toque_atribuído` |
| `timestamp` | `attributed_touch_time` |
| `line_item_id` | `id_da_campanha` |
| `line_item_name` | `campaign_name` |
| `creative_id` | `id_anúncio` |
| `product_type` | `af_canal` |
| `external_customer_id` | `network_account_id` |
| `id_do_site` | `af_siteid` |
| `insertion_order_id` | `af_sub4` |

<div id="setting-up-gmp-dv360-for-advertisers" />

## Configuração do GMP-DV360 para anunciantes

**Pré-requisitos**

Antes de configurar a integração, certifique-se de que:

* <Anchor target="_blank" href="/marketers/pt/docs/partner-integrations#contact-details">Entrar em contato com o parceiro</Anchor> e abrir uma conta com ele.
* <Anchor target="_blank" href="https://support.google.com/displayvideo/answer/10956727">Obter o ID do link GMP-DV360</Anchor>.

  <div id="note-1" />

  > 📘 **Nota**
  >
  > O ID do link do DV360 deve atender ao seguinte:
  >
  > * Ele deve conter números e letras.
  > * Ele deve ter mais de 20 caracteres.
  > * Android e iOS devem usar IDs de link diferentes.


**Para configurar uma nova integração:**  
  
**Pré-requisito:** uma conta com o parceiro. Antes de criar uma integração, certifique-se de <Anchor target="_blank" href="/marketers/pt/docs/partner-integrations#contact-details">entrar em contato com o parceiro</Anchor> e abrir uma conta com ele.

1. Na aba **Integração**, habilite **Ativar parceiro**.  
   **Para editar**: **Na AppsFlyer, vá para o menu lateral e selecione** Colaborar **>** **Integrações ativas**.
2. Selecione o aplicativo correspondente.
3. Na aba **Integração**, selecione o aplicativo e clique em **Ativar parceiro**.
4. Na **primeira visita** aqui, você precisará ativar a opção ***Ativar parceiro*** para habilitar a configuração dos parâmetros de integração. A opção **deve** permanecer ativada enquanto você trabalhar com o parceiro.  
      
   Para obter mais detalhes sobre a ativação do parceiro, clique <Anchor target="_blank" href="/marketers/pt/docs/partner-activation-deactivation">aqui</Anchor>.
5. Complete a configuração utilizando as abas relevantes, conforme descrito abaixo. Para obter uma descrição detalhada do header da Janela de Configuração de Parceiros, clique <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#about-the-integrated-partner-page">aqui</Anchor>.

<div id="integration-tab" />

<Accordion title="Aba de integração">

Quando a AppsFlyer consulta o GMP-DV360, eles retornam os parâmetros listados em sua resposta. Estes são mapeados para os parâmetros e dados brutos da AppsFlyer, conforme detalhado na tabela que se segue.

| GMP - parâmetro antigo | GMP-DV360 parâmetro | Parâmetro da AppsFlyer | Parâmetro do URL |
| --- | --- | --- | --- |
| ID de posicionamento | Nome do item da linha | Nome da campanha | C |
| ID de posicionamento | ID do item de linha | ID da campanha | af\_c\_id |
| ID do site | ID do site | ID do site | af\_siteid |
| ID criativa | ID criativa | ID do anúncio | af\_ad\_id |

<span id="activate-partner::e4f2f638"></span>A aba **Integração** inclui várias seções, conforme descrito abaixo.

<div id="activate-partner" />

#### Ativar parceiro

Para configurar a integração, você deve primeiro habilitar o botão **Ativar parceiro** . Saiba mais sobre como <Anchor target="_blank" href="/marketers/pt/docs/partner-activation-deactivation#ativar-uma-integração-de-parceiro">ativar e desativar integrações de parceiros</Anchor>.

<div id="general-settings" />

#### Configurações gerais

**ID do link:** Insira o ID do link mencionado nos pré-requisitos.

**Usuários fora da UE:** Decida se você deseja ou não ativar a opção <Anchor target="_blank" href="/marketers/pt/docs/support-google-eu-consent-policy#do-i-have-control-over-consent-data-for-nonue-users">**Usuários fora da UE**</Anchor>.

<Image align="center" alt="non eu usrs.png" src="https://files.readme.io/fb141c0bd8885facd6574f3e73c5ec8ae8beb596de7fdf3dd8aed9d4e82686dd-22352319155985.png" width="536px" />

<div id="install-attribution" />

#### Atribuição de instalação

Defina as diferentes janelas de atribuição para atribuir novas instalações (primeiras inicializações) de usuários que visualizaram ou clicaram no seu anúncio. Isto significa o tempo máximo entre o clique/visualização e a instalação. Apenas as instalações dentro da janela de lookback podem ser atribuídas à Google Marketing Platform - Display & Video 360 (DV360).

1. Defina a **janela de lookback de clique de instalação** para 1 a 23 horas ou 1 a 30 dias.
2. [Opcional] Ative a **atribuição de exibição de instalação** e defina a janela de lookback para 1 a 23 horas ou 1 a 30 dias.

<div id="re-engagement-attribution" />

#### Atribuição de reengajamento

Defina as diferentes janelas de atribuição para atribuir reengajamentos de usuários existentes que visualizaram ou clicaram no seu anúncio. Observe que apenas os reengajamentos dentro da janela de lookback podem ser atribuídas ao GMP-DV360.

1. Defina a **janela de reengajamento de clique de instalação** para 1 a 23 horas ou 1 a 30 dias.
2. [Opcional] Ative a **atribuição** **de visualização de reengajamento** e defina a janela de lookback para 1 a 23 horas ou 1 a 7 dias.

<div id="note-2" />

> 📘 **Nota**
>
> A reatribuição não é compatível com campanhas do DV360

Saiba mais sobre <Anchor target="_blank" href="/marketers/pt/docs/retargeting-attribution-guide#reengagement-rules-and-windows">regras e janelas</Anchor> de reengajamento.

<div id="re-engagement-window" />

#### Janela de reengajamento

Defina a janela de tempo, durante a qual os eventos do aplicativo são atribuídos principalmente à conversão de reengajamento. <Anchor target="_blank" href="/marketers/pt/docs/retargeting-attribution-guide#setup-reengagement-window">Saiba mais</Anchor>.

* Defina a **janela de reengajamento** como 1-23 horas, 1-90 dias ou **Vitalício**.

<div id="ignore-active-users-for-retargeting" />

#### Ignorar usuário ativo para retargeting

Defina um período de tempo para <Anchor target="_blank" href="/marketers/pt/docs/set-retargeting-inactivity-window#período-de-inatividade">ignorar reengajamentos e reatribuições</Anchor> de usuários que inicializaram o seu aplicativo. Isto significa que a sua atividade durante o período da janela não é registada na AppsFlyer.

<div id="note-3" />

> 📘 **Observação**
>
> **São registradas** as conversões de reengajamento e reatribuição de usuários que estavam **inativos** no período de tempo definido.

1. Ative a opção **Ignorar usuários ativos para retargeting**.
2. Configure a janela de inatividade.

<div id="in-app-event-postbacks" />

#### Postback de eventos in-app

Configure o mapeamento de eventos in-app com eventos do GMP-DV360, enviados via postbacks:

1. Ative **Postbacks de eventos in-app.**
2. Clique em **Adicionar evento** para adicionar um SDK ou evento de servidor para servidor à lista. A tabela a seguir descreve os campos a serem preenchidos:

| Nome do parâmetro | Descrição |
| --- | --- |
| **Evento AppsFlyer** | O nome do evento, conforme recebido do SDK integrado no aplicativo ou de eventos de servidor para servidor.<br />**Dica**: não encontrou o evento que está procurando?<ul><li>Certifique-se de ativar o evento em um dispositivo com uma instalação não orgânica e verifique novamente.</li><li>Digite-o em **Evento AppsFlyer**, depois clique em **Criar personalizado**. Leia mais sobre o <Anchor target="_blank" href="/marketers/pt/docs/in-app-event-postback-configuration#eventos-personalizados">mapeamento de eventos personalizados</Anchor>.</li></ul> |
| **mapeado para evento do parceiro** | O nome exclusivo ou ID de cada evento, conforme definido pelo parceiro. As configurações de mapeamento possíveis são:<ul><li>**Caixa suspensa:** selecione o evento predefinido mais adequado.</li></ul>**Observação:**<ul><li>A melhor prática é selecionar um evento padrão da lista. No entanto, para vários eventos PERSONALIZADOS, é melhor especificá-los de forma única, como PERSONALIZADO\_1 e PERSONALIZADO\_2. Isto ajudará a distinguir entre eventos no DV360/CM360.</li><li>Os eventos da AppsFlyer (como `af_purchase`, etc.) são sempre enviados com as variáveis `u`, por exemplo, `u24=`. Isto ajuda-o a identificá-los na CM360, mesmo quando enviados como personalizados.</li><li>O CM360 permite um máximo de 10 eventos no total, que podem ser eventos personalizados ou padrão.</li></ul> |
| **para usuários de** | Selecione a opção de envio para o evento:<ul><li>**Apenas este parceiro** (predefinição): Envie postbacks somente quando esse evento for atribuído ao GMP-DV360.</li><li>**Todas as fontes de mídia, incluindo orgânicas**: Envie postbacks para eventos atribuídos a qualquer parceiro, assim como eventos orgânicos.</li></ul> |
| **incluindo** | <ul><li>**Sem valores e sem receitas** (padrão): Envie somente o evento em si, sem o valor do evento.</li><li>**Com valores e sem receita**: envie todos os parâmetros, com **exceção** do valor da receita.</li><li>**Valores e receita**: envie todos os parâmetros do evento, **incluindo** o valor da receita (se existir no evento).</li></ul> |

3. [Opcional] Clique no ícone **Adicionar condição**<Image alt="conditional-iae-postbacks-icon.png" src="https://files.readme.io/575c9ab0dd82a125319591072b17604a7f9d1b71fff6baff4124d99edc1a7fc7-16570673855121.png" width="30px" /> para <Anchor target="_blank" href="/marketers/pt/docs/in-app-event-postback-configuration#postbacks-condicionais-de-eventos-in-app">definir condições</Anchor> para um evento.
4. Clique em **Salvar integração.**
5. [Opcional] Após salvar a integração, enquanto permanece na página de configuração, você pode integrar mais aplicativos com o GMP-DV360:
   1. Do canto superior esquerdo, abaixo do nome do parceiro, clique no nome do aplicativo para abrir a lista de apps.
   2. Selecione um aplicativo diferente a partir da lista suspensa.
   3. Repita as  etapas de integração  para o aplicativo selecionado.

<div id="note-4" />

> 📘 **Observação**
>
> Somente para aplicativos iOS: Seu controle sobre os dados compartilhados com o parceiro por meio de postbacks e <Anchor target="_blank" href="/marketers/pt/docs/about-raw-data-identifier-restrictions">relatórios</Anchor> depende do **status** [da Privacidade Avançada (para iOS 14.5+ em diante)](#advanced-privacy).

<div id="u-parameter-mapping" />

#### Mapeamento do parâmetro U

A AppsFlyer aceita o envio de parâmetros adicionais (parâmetros u), limitados a u26. Os parâmetros U são pré-mapeados e fixados pela AppsFlyer. Considere o seguinte:

* Como esses parâmetros são pré-mapeados, nenhum parâmetro U personalizado adicional pode ser configurado.
* Se faltarem dados para um parâmetro U específico, a AppsFlyer não os enviará. Por exemplo, se os dados da operadora estiverem ausentes, a AppsFlyer não enviará o U5.

| Parâmetro U | Nome | Valor de exemplo |
| --- | --- | --- |
| u1= | id do dispositivo af | 1540995037437-2811776739500410055 |
| u2= | id de usuário cliente | eaf8a5f2.1836.4686 |
| u3= | **Android**:  <br />ID de publicidade  <br />**iOS**: idfa | 9d9d03ab-f211-4e17-994e-d0afdf23ac01 |
| u4= | wifi | verdadeiro |
| u5= | operadora | Jio%204G |
| u6= | código do país | IN |
| u7= | Região | HR |
| u8= | cidade | Gurgaon |
| u9= | tipo do dispositivo | motorola::Moto G (4) |
| u10= | versão do so | 7 |
| u11= | versão do sdk | v4.8.18 |
| u12= | versão do aplicativo | 3.31.1 |
| u13= | carimbo de data/hora da instalação | 1540995041 |
| u14= | hora do clique | 1546441586 |
| u15= | hora da impressão | 1546441586 |
| u16= | nome da campanha* | Appinstall\_campaign |
| u17= | ID da campanha | 12345ABC |
| u18= | nome do conjunto de anúncios* | Appinstall\_adset |
| u19= | ID do conjunto de anúncios | 12345ABC |
| u20= | ad name* | Appinstall\_ad |
| u21= | ID do anúncio | 1234567ABCDE |
| u22= | site id | site\_id\_123456 |
| u23= | event time | 2019-01-04 12:56:35.707 |
| u24= | Nome do evento | af\_compra |
| u25= | Valor do evento | `{"af_price":459,"af_content_id":"77147","af_revenue":4.59,"af_currency":"EUR"}` |
| u26= | símbolos monetários | EUR |

* Se a AppsFlyer não receber esse nome de parâmetro na resposta do GMP-DV360, ela preenche o campo com o ID correspondente. Por exemplo, o nome do Adset mostrará o ID do Adset, que é `12345ABC`.

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Aba do link de atribuição">

É possível **usar os links de atribuição da AppsFlyer com o DV360 somente para gravação de impressões e cliques.** Esses links não são usados para atribuição e qualquer informação adicional contida neles não é analisada ou usada para qualquer finalidade.

Se você deseja medir o número de cliques de DV360 na AppsFlyer, deve adicionar uma URL de atribuição da AppsFlyer no seu painel DV360. Ao fazer isso, certifique-se de que o nome da campanha na URL de atribuição é **idêntico** à ID de posicionamento no GMP (se possível) para que a AppsFlyer possa recuperar e anexar os dados de cliques nas campanhas corretas.

<div id="important-1" />

> 🚧 **Importante!**
>
> O uso de links de atribuição para o **DV360** não é obrigatório.
>
> **Limitação:** Links de atribuição do DV360 que incluem o parâmetro `af_prt` atualmente **não são compatíveis com contas de agência**.

Se você quiser contar os **cliques** na AppsFlyer, use este link:

```http
https://app.appsflyer.com/ADD-APP-ID?pid=dv360_int&af_siteid=${UNIVERSAL_SITE_ID}
&af_ad_id=${CREATIVE_ID}&c=${PLACEMENT_ID}&af_c_id=${PLACEMENT_ID}
```

Se você quiser contar as **impressões** na AppsFlyer, use este link:

```http
https://impression.appsflyer.com/ADD-APP-ID?pid=dv360_int&af_siteid=%24{UNIVERSAL_SITE_ID}
&af_ad_id=${CREATIVE_ID}&c=${PLACEMENT_ID}&af_c_id=${PLACEMENT_ID}
```

</Accordion>

<div id="cost-tab-for-cost-clicks-and-impressions" />

<Accordion title="Aba Custo (para custo, cliques e impressões)">

Custo, cliques e impressões são compatíveis com esta integração por meio do ROI360.

Os clientes do ROI360 podem criar e editar integrações de custo na **aba Custo** e em **Configurações de custo**. Veja <Anchor target="_blank" href="/marketers/pt/docs/set-up-roi360-cost-api-to-measure-cost-data#enabling-cost-api">como ativar a integração de custo</Anchor>.

A partir de 7 de setembro de 2026, cliques e impressões não serão mais reportados por meio da atribuição. Para continuar recebendo essas métricas, configure a integração SRN/custo do DV360.

<div id="note-5" />

> 📘 **Anunciante**
>
> Cliques e impressões desta integração são reportados em:
>
> * Painéis
> * Relatórios de custo de ETL (somente para clientes ROI360)
> * APIs agregadas da AppsFlyer
>
> Dependendo de quando a ativação da integração com o DV360 ocorrer, poderá haver uma discrepância temporária em cada um dos itens acima:
>
> * Ativação em ou antes de 6 de setembro: cliques e impressões são relatados duas vezes durante esse período, uma vez pela atribuição da AppsFlyer e uma vez pela API do DV360; portanto, é esperada uma discrepância temporária.
> * Ativação até 12 de setembro: é esperada uma discrepância em algumas datas devido ao preenchimento automático retroativo dos últimos 7 dias do DV360.
> * Ativação após 12 de setembro: não é esperada nenhuma discrepância.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Aba receita de anúncios">

As receitas de anúncios não são compatíveis com esta integração.

</Accordion>

<div id="setting-up-gmp-dv360-for-agencies" />

## Configuração do GMP-DV360 para agências

As agências podem efetuar campanhas com o GMP-DV360 em seu nome.

<div id="agency-setup" />

#### Configuração da agência

| Procedimento realizado por | Procedimento |
| --- | --- |
| AppsFlyer | <ol><li>Verifique se concluiu a integração GMP-DV360 do anunciante.</li><li>Na AppsFlyer, vá para o menu lateral e selecione **Colaborar** > **Integrações ativas**.</li><li>Selecione uma agência.</li><li>Vá para a aba **Permissões** e habilite **Permissões de agência.**</li><li>[Opcional] Na aba**Integração**, ative **o postback de eventos in-app**. Isto faz com que a agência possa ativar ou desativar os postbacks.</li></ol> |
| Agência | <ol><li>Na AppsFlyer, vá para o menu lateral e selecione **Colaborar** > **Integrações ativas**.</li><li>Selecione **Google Marketing Platform - Integração de Display & Video 360 (DV360).**</li><li>Acesse a aba de **Integração**.<br />O status de integração com o GMP é exibido. [![mceclip2.png](https://files.readme.io/153226084274c9e2bf0c5cfdca65f7d36076a2020c605e21177c8c71613b69f6-360017196637.png)](https://files.readme.io/153226084274c9e2bf0c5cfdca65f7d36076a2020c605e21177c8c71613b69f6-360017196637.png)</li><li>Verifique se a opção **Ativar parceiro** está habilitada. Se não for este o caso, o anunciante deve completar [a integração do GMP-DV360 do anunciante.](#configuração-do-gmp-dv360-para-anunciantes)</li><li>Verifique se as restantes definições, como as janelas de lookback e o mapeamento de eventos in-app, estão corretas. Se necessário, peça para o anunciante realizar alterações.</li><li>Insira um ou mais **IDs de anunciante DBM**. O ID está disponível no seu <Anchor target="_blank" href="https://support.google.com/displayvideo/answer/3423704?hl=en&ref_topic=9133452">painel de controle GMP.</Anchor></li><li>Clique em **Salvar**.</li></ol> |

<div id="gmp-dv360-discrepancies" />

## Discrepâncias GMP-DV360

Veja as possíveis razões para as discrepâncias e como minimizá-las:

| Causa | Descrição | Dica da AppsFlyer |
| --- | --- | --- |
| Janela de atribuição de exibição | A exibição na janela de atribuição do GMP-DV360 é de 14 dias. Já a janela padrão da AppsFlyer é de 1 dia. | Para reduzir a discrepância, defina a janela de view-through na AppsFlyer como a janela máxima de 7 dias. |
| Mapeamento incorreto | Mapeamento entre a AppsFlyer e o GMP-DV360 não está correto. | <ul><li>Verifique o ID do link</li><li>Verifique se os eventos in-app estão corretamente mapeados</li></ul> |

<div id="see-also" />

> 📄 **Consulte também**
>
> * <Anchor target="_blank" href="/marketers/pt/docs/set-up-roi360-cost-api-to-measure-cost-data">Configure a ROI360 cost API para mensurar dados de custo</Anchor>
> * <Anchor target="_blank" href="/marketers/pt/docs/retargeting-attribution-guide">Aba Permissões</Anchor>
> * <Anchor target="_blank" href="/marketers/pt/docs/in-app-event-postback-configuration">**PERSONALIZADO**: Ao selecionar essa opção, a AppsFlyer envia o evento como ele aparece no campo de **evento da AppsFlyer**.</Anchor>

<div data-zendesk-anchors="h_01HMEH8VW3PYCZ6GC4T5BYBS3V=importante overview=vis%C3%A3o-geral 01H8E4ZJNRMXY183TQCPW15ZQB=vis%C3%A3o-geral 01H8DYEV7JPV80T3YAJQQHBA6C=observa%C3%A7%C3%A3o data-sharing-between-appsflyer-and-gmp=compartilhamento-de-dados-entre-a-appsflyer-e-o-gmp---dv360 h_01HQ0QJJRMYP3E6B5FVA0V6861=compartilhamento-de-dados-entre-a-appsflyer-e-o-gmp---dv360 advertiser-gmp-integration=configura%C3%A7%C3%A3o-do-gmp-dv360-para-anunciantes 01H8DYEV7KYNB2FJG7N1CTEE86=configura%C3%A7%C3%A3o-do-gmp-dv360-para-anunciantes h_01KC714WNQWGCM1C1MC8S2PZXH=nota h_01HPYMRJ1WVVKCHKKEA6WD0XZP=integration-tab 01H8VVCC8G0KR4AA2HD9S8QBKD=ativar-parceiro general-settings=configura%C3%A7%C3%B5es-gerais 01H8VVCC8GSDPSNN0AJPVZPR8P=configura%C3%A7%C3%B5es-gerais install-attribution=atribui%C3%A7%C3%A3o-de-instala%C3%A7%C3%A3o 01H8VVCC8GK8VFPBEPAMVHCAWM=atribui%C3%A7%C3%A3o-de-instala%C3%A7%C3%A3o reengagement-attribution=atribui%C3%A7%C3%A3o-de-reengajamento 01H8VVCC8HHG5290PYF0BT29QA=atribui%C3%A7%C3%A3o-de-reengajamento h_01K4AFW71RG9YE5EJE1FQCN4SE=nota-1 reengagement-window=janela-de-reengajamento h_01HQ06JCJZD6AMFR2B6GTMSM9S=janela-de-reengajamento ignore-active-users-for-retargeting=ignorar-usu%C3%A1rio-ativo-para-retargeting h_01HNWSTJZPFQVQ5C8M0JA1J0T5=ignorar-usu%C3%A1rio-ativo-para-retargeting h_01HMXNJVHK9C3FT8E04RE0TH99=observa%C3%A7%C3%A3o-1 inapp-event-postbacks=postback-de-eventos-in-app 01H8VVCC8HHZRFQ2T1X478YZMP=postback-de-eventos-in-app 01H8VVCC8HDMTY1P2SG31HD61K=observa%C3%A7%C3%A3o-2 parameter-mapping=mapeamento-do-par%C3%A2metro-u h_01HBBJQZSTT1HFENXNACMHFC18=mapeamento-do-par%C3%A2metro-u 01H8VVCC8H53ZRMDBNK1436NAX=attribution-link-tab h_01HBBJQZSW45X3SM92H4FS94HM=importante-1 01H8VVCC8H74GDVCNAXT0741MG=cost-tab-for-cost-clicks-and-impressions h_01_dv360_cutover_discrepancy=anunciante 01H8VVCC8H90ANM70QAHKTQQ1S=ad-revenue-tab setting-up-gmp-dv360-for-agencies=configura%C3%A7%C3%A3o-do-gmp-dv360-para-ag%C3%AAncias 01H8VVCC8HVNNQ9PJS4ZQCVDNS=configura%C3%A7%C3%A3o-do-gmp-dv360-para-ag%C3%AAncias agency-setup=configura%C3%A7%C3%A3o-da-ag%C3%AAncia 01H8DYEV7MNFFY9ESFF2S3ETEB=configura%C3%A7%C3%A3o-da-ag%C3%AAncia gmp-discrepancies=discrep%C3%A2ncias-gmp-dv360 01H8DYEV7MTPJMY12AVHX45YFF=discrep%C3%A2ncias-gmp-dv360 h_01KYS9JJ9RSTDPHRZWW47DN438=consulte-tamb%C3%A9m" />
