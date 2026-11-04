---
title: Configure o Smart Script para converter visitantes da web
metadata:
  keywords:
    - OneLink
    - Advertisers
    - Developers
    - Marketers
    - Smart Banners and Scripts
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-asaf-mashiah
    - Marketers
    - Smart Banners and Scripts
  created_at: '2021-12-13T09:57:23Z'
  edited_at: '2026-10-09T00:16:23Z'
  id: 4413588932241
  locale: pt
  section: Web-to-app attribution
  section_id: 6551240476177
  url: https://support.appsflyer.com/hc/pt/articles/4413588932241
---
> **Visão geral:** acesse o OneLink e configure o Smart Script para converter e atribuir visitantes do seu site mobile em usuários do aplicativo mobile, independentemente do canal de onde eles vieram.

![7901_Smart_Script_flow_1920x1080_2__1_.png](https://files.readme.io/5181971c27e89974a86afeb83f48eb5c127b64765334bc3b5644ed47adb974e8-30193884510225.png)

<div id="setup" />

## Configuração

No OneLink, existem duas versões do Smart Script:

**OneLink Smart Script V2 (recomendada)**: Se você estiver configurando o Smart Script pela primeira vez, essa é a versão recomendada. Ela pode ser gerada na interface do usuário da AppsFlyer sem a assistência de um desenvolvedor. Se, por algum motivo, for necessária ajuda técnica, esse trabalho será relativamente fácil. Ela também pode ser configurada usando o Google Tag Manager. <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_smart_script_v2">Veja as instruções para desenvolvedores</Anchor>

<Anchor target="_blank" href="/marketers/pt/docs/legacy-onelink-smart-script-v1-setup">**OneLink Smart Script V1 (legada)**</Anchor>: Se você já tiver o Smart Script configurado, use a documentação dessa versão para manter e editar esse script. **Observação**: embora não seja obrigatório, considere migrar para a V2 para obter atribuições de view-through **usando o Smart Script.**

<div id="set-up-onelink-smart-script" />

### Configurar o Smart Script

Para configurar o Smart Script, você pode:

* Incorporar o script ao seu site.
* Usar o Google Tag Manager.

<div id="scope-of-work" />

#### Escopo do trabalho

**Quem está envolvido**

* **Anunciante**:
  * Decide o que a URL de saída deve conter com base nos [argumentos](/docs/set-up-smart-script-to-convert-web-visitors#arguments) no script que processa a URL de entrada. Esse processo determina os dados de atribuição e deep linking que são anexados à URL de saída, seja através da manipulação da URL de entrada ou de determinados valores forçados.
  * Gera o Smart Script na interface do usuário da AppsFlyer.
  * Certifica-se de que todas as campanhas que levam ao site mobile tenham URLs de entrada com parâmetros que funcionem para o script.
  * <Anchor target="_blank" href="https://appsflyersdk.github.io/appsflyer-onelink-smart-script/examples/test_page.html">Testa o Smart Script</Anchor>.
* **Desenvolvedor da web**:
  * Verifica se o script é executado no site/páginas mobile nas quais você quer que ele funcione.
  * Usa o valor resultante conforme necessário: por exemplo, para colocá-lo como um link em um CTA no seu site.
  * Pode criar QR codes usando o script.
  * Pode adicionar manualmente argumentos avançados ao script.

**Pré-requisitos**

* Uma conta da AppsFlyer com pelo menos um aplicativo.
* Um <Anchor target="_blank" href="/marketers/pt/docs/create-a-onelink-template#como-criar-templates-do-onelink">template do OneLink</Anchor> que serve como o valor do [parâmetro OneLinkURL](/docs/set-up-smart-script-to-convert-web-visitors#arguments).

<div id="how-to-create-a-onelink-smart-script" />

<Accordion title="Como criar um Smart Script no OneLink">

**Para criar um Smart Script:**

1. Na AppsFlyer, no menu lateral, vá para **Engajar** > **Web-to-app** > **Smart Banners**.
2. ***Para novos usuários***
   1. *Clique em *Começar*.*
   2. *Siga os passos de 4 em diante.*
3. Clique no **botão + Novo Smart Script** na parte superior da página.
4. Siga as instruções na tela para nomear seu Smart Script.
5. Selecione um template do OneLink como base para seu script. O template contém as configurações básicas de redirecionamento.
6. Mapeie os parâmetros que a URL de saída deve conter. Esses parâmetros se baseiam nos parâmetros da URL de entrada. **Atenção**: O parâmetro fonte de mídia (pid) é obrigatório.
   1. Selecione o parâmetro/dimensão de saída a ser mapeado.  
      Muitas vezes, esse é um nome de parâmetro da AppsFlyer que não pode ser alterado. Mas, em alguns casos, você precisa inserir um novo nome para o parâmetro.
   2. Configure em qual valor o parâmetro de saída deve se basear:
      * Parâmetros de URL de entrada: liste um ou mais parâmetros de URL de entrada possíveis que você deseja substituir pelo parâmetro da URL de saída. Os valores dos parâmetros da URL de entrada serão os valores do parâmetro da URL de saída.
        * Exemplo: any\_param\_name, utm\_param\_name. Se utm\_param\_name for encontrado na URL de entrada, seu valor será usado como o valor do parâmetro da URL de saída selecionado.
        * O Smart Script analisa a lista de parâmetros da esquerda para a direita e mapeia a primeira correspondência para o parâmetro da URL de saída.
        * Os desenvolvedores se referem a essa lista de parâmetros como chaves (keys).
      * Valor padrão: digite o valor padrão desejado para o parâmetro de saída para casos em que um parâmetro de URL de entrada não for encontrado ou caso você não liste nenhum parâmetro de URL de entrada.
        * Exemplo: para o parâmetro de saída, se o parâmetro de URL de entrada listar any\_paramname, utm\_paramname, quando nenhum dos parâmetros da lista for encontrado, o valor padrão será usado como o valor do parâmetro de saída.
      * Substituir valores: configure um ou mais valores da URL de entrada ao lado dos valores da URL de saída que você deseja substituir.
        * Exemplo: para o parâmetro da campanha, se o valor na URL recebida for campaign\_name, o valor na URL de saída poderá ser alterado para new\_campaign\_name.
   3. [Opcional] Clique em **+ Novo parâmetro** para mapear parâmetros adicionais. Veja todos os [argumentos adicionais](/docs/set-up-smart-script-to-convert-web-visitors#arguments) (configurações de parâmetros) que você pode usar.
7. [Opcional] Ative **Fonte de mídia para instalações de pesquisa orgânica**, na seção **mapeamento de referrer** da **web**, para definir automaticamente a fonte de mídia do tráfego de pesquisa orgânica quando ela ainda não tiver sido resolvida pela seção de mapeamento de parâmetros de URL. [Saiba mais](#seo-referrer-mapping)
8. Selecione como implementar o Smart Script no seu site:
   * **Incorporar o script ao seu site.**
   * **Usar o Google Tag Manager.**
9. Clique em **Testar** para testar o script na <Anchor target="_blank" href="https://appsflyersdk.github.io/appsflyer-onelink-smart-script/examples/test_page.html">página de teste do Smart Script</Anchor>. Certifique-se de que a URL de saída correta seja gerada.
10. Clique
    1. Clique em **Salvar** para salvar suas alterações
    2. Clique em **Salvar e gerar** para salvar e gerar o script
       1. Clique em **Baixar script**.
11. Se você optou por incorporar o script em seu site: envie o script para o desenvolvedor da web para implementação e explique o que deve ser feito com a URL de saída gerada. Por exemplo, você pode colocá-la em um botão de CTA em seu site mobile ou em um QR code em seu site desktop. <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/onelink-smart-script-v2web-to-app-url-generator#embed-the-script-in-your-website">Instruções para desenvolvedores</Anchor>
12. Se você optou por usar o Google Tag Manager:
    1. No Google Tag Manager, crie uma nova tag, nomeie-a, clique em **Tag configuration**, e selecione **Custom HTML**.
    2. Na caixa HTML, cole o código Smart Script gerado.
    3. Clique em **Triggering**, crie um novo trigger, nomeie-o e escolha uma **Configuração de trigger** (por exemplo, todos os page views). <Anchor target="_blank" href="https://support.google.com/tagmanager/answer/7679319?hl=en&ref_topic=7679108">Veja a documentação do GTM para saber mais</Anchor>
    4. Clique em **Save**
    5. Explique ao seu desenvolvedor web o que deve ser feito com a URL de saída gerada. Por exemplo, você pode colocá-la em um botão de CTA em seu site mobile ou em um QR code em seu site desktop. <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/onelink-smart-script-v2web-to-app-url-generator#use-google-tag-manager">Instruções para desenvolvedores</Anchor>
13. Os scripts salvos podem ser visualizados no [menu suspenso](/docs/set-up-smart-script-to-convert-web-visitors#how-to-edit-or-delete-a-script).

<div id="important" />

> 🚧 **Importante!**
>
> Toda vez que você atualiza o script, ele precisa ser implementado novamente

</Accordion>

<div id="how-to-edit-or-delete-a-script" />

<Accordion title="Como editar ou excluir um script">

**Para editar ou excluir um script:**

1. Clique na seta <Image alt="Down_arrow.jpg" src="https://files.readme.io/a82023665721be681f985548857c4c329f626435780bb1bff7a3821b32b69078-42045468433041.jpg" width="28px" /> ao lado do nome do Smart Script.  
   Aqui, você pode ver todos os seus scripts salvos  

   <Image alt="Script_steps.jpg" src="https://files.readme.io/824c042dc23acaa14b360ce8cd792cfc2e85ee3c9c95e3fa694f96badfeb1fc2-42045468432657.jpg" width="1732px" />
2. Clique no ícone de lápis ao lado do script que você quer editar
   1. Siga as etapas listadas em [como criar um Smart Script](/docs/set-up-smart-script-to-convert-web-visitors#configurar-o-smart-script)
3. Clique no ícone de lixeira para excluir o Smart Script

<div id="important-1" />

> 🚧 **Importante!**
>
> Toda vez que você atualiza o script, ele precisa ser implementado novamente

</Accordion>

<div id="how-to-duplicate-a-script" />

<Accordion title="Como duplicar um script">

**Para duplicar um script:**

1. Vá para o Smart Script que você deseja duplicar
2. Clique no botão de duplicar <Image alt="SmartScript_duplicate.jpg" src="https://files.readme.io/ec05ea217331b588dc7033984287d46b61a37e41510546b67a0046ea281e0979-42045454920721.jpg" width="21px" /> no banner superior
3. Siga as etapas listadas em [como criar um Smart Script](/docs/set-up-smart-script-to-convert-web-visitors#configurar-o-smart-script)

</Accordion>

<div id="argument-structure" />

<Accordion title="Estrutura do argumento">

O Smart Script do OneLink usa argumentos para gerar uma URL de saída que se baseia nos parâmetros da URL de entrada e nos argumentos definidos no script. O argumento afParameters tem uma estrutura composta por vários outros argumentos (parâmetros) utilizados para a atribuição e o deep linking, sendo que cada um contém uma estrutura (conhecida pelos desenvolvedores como objeto de configuração) que possui chaves (keys), valores de sobreposição (override values) e um valor padrão, conforme descrito na tabela a seguir.

| Argumento | Descrição | Exemplo |
| --- | --- | --- |
| Parâmetros de URL de entrada (ou keys) | <ul><li>Lista de strings</li><li>Lista de parâmetros possíveis na URL de entrada que o script procura, cujo valor é colocado como o valor na URL de saída.</li><li>O script pesquisa da esquerda para a direita e para na primeira correspondência.</li></ul> | <ul><li>Exemplo: ['in\_channel', 'utm\_channel']</li><li>Para o parâmetro do canal no script, o script pesquisa o link de entrada para in\_channel e usa o valor como o valor para o canal.</li></ul> |
| Valor padrão | <ul><li>String</li><li>Defina qual será o valor de "fallback".</li><li>Se um parâmetro não for encontrado em sua lista de keys, defaultValue é usado na URL de saída.</li><li>Você pode forçar um valor padrão ao passar uma lista de keys vazias.</li></ul> | Exemplo: ['web\_video']<br /><br />Para o parâmetro do canal no script, se não o parâmetro in\_channel não for encontrado, web\_video é usado como o valor do canal. |
| Substituir valores | <ul><li>Dicionário \{string: string\}</li><li>Caso você queira alterar valores no link de saída, liste os valores na URL de entrada, junto com os que você deseja que sejam substituídos.</li><li>O script substitui os valores dos parâmetros da URL de entrada pelos valores configurados.</li></ul> | Exemplo: \{'video': 'video\_new'\}<br /><br />Para o parâmetro do canal no script, sempre que o valor de entrada for "video", o script o altera para "video\_new" no link de saída. |

</Accordion>

<div id="arguments" />

<Accordion title="Argumentos (parâmetros e valores)">

O Smart Script usa argumentos para gerar uma URL de saída com base nos parâmetros da URL de entrada e nos argumentos definidos no script.

<div id="arguments-parameters-and-values-to-implement-the-smart-script" />

#### Argumentos (parâmetros e valores) para implementar o Smart Script

<table><thead><tr><th colspan="2">Argumento</th><th>Observações</th><th>Registre suas respostas (para que você ou o desenvolvedor as utilize)</th></tr></thead><tbody><tr><td colspan="2">oneLinkURL (obrigatório)</td><td><ul><li>Forneça o domínio do template do OneLink + ID do template. <strong>Atenção:</strong> essa não é uma URL de link personalizada do OneLink!</li><li>Exemplo: <strong>suamarca.onelink.me/A1b2</strong> </li><li>Exemplo de branded domain: <strong>clique.suamarca.com/A1b2</strong> </li></ul></td><td> </td></tr><tr><td rowspan="9"><p>afParameters</p><p>(obrigatório)</p></td><td><p>mediaSource</p><p>(obrigatório)</p></td><td><ul><li>Objeto de configuração para canal de mídia.</li><li>Exemplo:<ul><li>Keys: ['incoming_mediasource'' 'utm_source']</li><li>Valor padrão: ['any_source']</li><li>Substituir valores: `{twitter: 'twitter_int', orig_src: 'new_src',  seo:'false'}</li></ul></li></ul></td><td><p>Keys:</p><p>Valor padrão:</p><p>Substituir valores:</p></td></tr><tr><td>campaign</td><td><ul><li>Objeto de configuração para campanha.</li><li>Exemplo:<ul><li>Keys: ['incoming_campaign', 'utm_campaign']</li><li>Valor padrão: ['any_campaign_name']</li><li>Valores de substituição: {campaign_name: 'new_campaign_name'}</li></ul></li></ul></td><td><p>Keys:</p><p>Valor padrão:</p><p>Valores de substituição:</p></td></tr><tr><td>channel</td><td><ul><li>Objeto de configuração para canal.</li><li>Exemplo:<ul><li>Keys: ['incoming_channel', 'utm_channel']</li><li>Valor padrão: ['any_video']</li><li>Valores de substituição: {video: 'new_video'}</li></ul></li></ul></td><td><p>Keys:</p><p>Valor padrão:</p><p>Valores de substituição:</p></td></tr><tr><td>ad</td><td><ul><li>Objeto de configuração para anúncio.</li><li>Exemplo:<ul><li>Keys: ['incoming_ad', 'utm_ad']</li><li>Valor padrão: ['any_ad_name']</li><li>Valores de substituição: {ad_name: 'new_ad_name'}</li></ul></li></ul></td><td><p>Keys:</p><p>Valor padrão:</p><p>Valores de substituição:</p></td></tr><tr><td>adSet</td><td><ul><li>Objeto de configuração para conjunto de anúncios.</li><li>Exemplo:<ul><li>Keys: ['incoming_adset', 'utm_adset']</li><li>Valor padrão: ['any_ad_name']</li><li>Valores de substituição: {adset_name: 'new_adset_name'}</li></ul></li></ul></td><td><p>Keys:</p><p>Valor padrão:</p><p>Valores de substituição:</p></td></tr><tr><td>deepLinkValue</td><td><ul><li>Objeto de configuração para <strong>deep_link_value</strong>.</li><li>Exemplo:<ul><li>Keys: ['product_id', 'page_name']</li><li>Valor padrão: 'new_offers_page'.</li><li>Valores de substituição: {twenty_percent_off: 'thirty_percent_off'}</li></ul></li></ul></td><td><p>Keys:</p><p>Valor padrão:</p><p>Valores de substituição:</p></td></tr><tr><td>afSub1-5</td><td>Objeto de configuração para <strong>af_sub[1-5]</strong>.</td><td><p>Keys:</p><p>Valor padrão:</p><p>Valores de substituição:</p></td></tr><tr><td>googleClickIdKey</td><td>Informe como o parâmetro que leva o <a href="https://support.google.com/google-ads/answer/9744275?hl=en" target="_blank">GCLID</a> será chamado.<br/><strong>Atenção</strong>! <span>Para exibir relatórios de dados brutos na AppsFlyer, o parâmetro deve ser um <strong>af_sub[1-5]</strong>.</span> </td><td> </td></tr><tr><td> <span>Outros parâmetros de consulta (personalizados)</span><br/> </td><td><ul><li>Liste quaisquer outros parâmetros que você queira incluir na URL de saída do OneLink para atribuição ou deep linking, junto com seus objetos de configuração.</li><li>O nome do parâmetro personalizado é listado pelo desenvolvedor como um paramKey no objeto de configuração.<span></span> </li><li>Exemplo:<ul><li>paramKey: 'deep_link_sub1'</li><li>Keys: ['page_id']</li><li>Valor padrão: 'page1'</li><li>Substituir valores: {page12: 'new_page12'}`</li></ul></li></ul></td><td><p>Param key:</p><p>Keys:</p><p>Valor padrão:</p><p>Valores de substituição:</p></td></tr></tbody></table>

</Accordion>

<div id="advanced-arguments" />

<Accordion title="Argumentos avançados">

A tabela a seguir descreve os argumentos que os profissionais de marketing ou desenvolvedores podem implementar no Smart Script.

<div id="advanced-arguments-parameters-and-values-to-implement-in-the-smart-script" />

#### Argumentos avançados (parâmetros e valores) para implementar no Smart Script

<table><thead><tr><th colspan="2">Argumento</th><th>Observações</th><th>Registre suas respostas (para que você ou o desenvolvedor as utilize)</th></tr></thead><tbody><tr><td colspan="2"> <br/>referrerSkipList</td><td><ul><li><span>Lista das strings no HTTP referrer para um clique específico (por exemplo, Twitter ou Facebook) que, se encontradas, fazem com que o Smart Script retorne <code>null</code>. Isso pode ser útil para SRNs como o X Ads e Meta ads, para os quais os cliques já são relatados.</span></li><li>A implementação desse argumento faz com que o script NÃO gere uma URL do OneLink.</li></ul></td><td> </td></tr><tr><td colspan="2">urlSkipList</td><td><ul><li>Lista de strings da URL para um determinado clique (por exemplo af_r) que, se identificadas, fazem com que o Smart Script retorne <code>null</code>. Isso pode ser útil se você usar um link de atribuição da AppsFlyer com af_r para redirecionar os usuários para seu site mobile e não quiser que os dados do clique original sejam perdidos.</li><li>A implementação desse argumento faz com que o script NÃO gere uma URL do OneLink.</li></ul></td><td> </td></tr><tr><td colspan="2">SEO</td><td><ul><li>Quando essa opção está ativada e o canal de mídia não é resolvido na seção de <strong>mapeamento de parâmetros de URL</strong>, verificaremos se os usuários chegaram por meio de um mecanismo de busca com base na URL de referência web e definiremos o canal de mídia de acordo. (disponível a partir da versão 2.10.3)</li></ul></td><td> </td></tr></tbody></table>

</Accordion>

<div id="use-cases" />

## Casos de uso

As seções a seguir trazem alguns casos de uso do Smart Script para cenários típicos de campanhas/canais de mídia.

<div id="utm-parameters" />

<Accordion title="Parâmetros UTM">

**Para configurar o script para os parâmetros UTM**:

1. Faça uma lista de parâmetros UTM na URL de entrada (por exemplo: **utm\_source** e **utm\_campaign**) e compare-os com os parâmetros da URL de saída (por exemplo: **media\_source** e **campaign**).
2. Forneça-os na [lista de argumentos](/docs/set-up-smart-script-to-convert-web-visitors#arguments) para o seu desenvolvedor da web.

**Resultado:** os valores nos parâmetros de entrada (**utm\_source** e **utm\_campaign**) são usados para preencher os valores dos parâmetros (**media\_source** e **campaign**) no link de saída.

</Accordion>

<div id="google-ads-gclid" />

<Accordion title="Google Ads GCLID">

O processo usual para a atribuição de instalações de campanhas do Google Ads (que carregam um parâmetro GCLID) requer que os usuários que clicam no seu anúncio sejam redirecionados para a URL da página da loja de aplicativos.

Nesse caso, como você está redirecionando leads do Google Ads para um destino/página da web, o script pega o parâmetro GCLID da URL da campanha de instalação do Google Ads e o coloca na URL de saída. A partir da versão 2.9.0 do Smart Script, os parâmetros GCLID, WBRAID e GBRAID, quando disponíveis, são encaminhados automaticamente "no estado em que se encontram" nas URLs de saída geradas pelo Smart Script.

Você também pode mapear Click IDs para outros parâmetros de saída (**af\_sub[1-5]**) para disponibilizá-los nos relatórios de dados brutos da AppsFlyer.

**Atenção!**

* Isso se aplica às campanhas de instalação. Para campanhas de pesquisa não-ACI (ou seja, campanhas de reengajamento), o Google pode ser atribuído como canal de mídia, apesat do output do Smart Script.
* Se um GCLID for encontrado, o script procurará a palavra-chave do parâmetro de entrada. Se encontrada, ele coloca o valor da palavra-chave na URL de saída como o valor de af\_keywords.

**Pré-requisito**: no dashboard do Google, você deve <Anchor target="_blank" href="https://support.google.com/analytics/answer/1033981?hl=en">ativar o auto-tagging</Anchor>.   
Com o auto-tagging ativado, a URL contém o *parâmetro GCLID*.

**Para configurar o script para mapear o GCLID do Google Ads para outros parâmetros**:

1. Selecione um parâmetro na URL de saída para conter o GCLID.  
   Recomendação: selecione **af\_sub[1-5]**, para que os dados sejam exibidos nos relatórios de dados brutos da AppsFlyer.
2. Forneça esse item na [lista de argumentos](/docs/set-up-smart-script-to-convert-web-visitors#arguments) para o desenvolvedor da web. Como resultado, o GCLID será o valor do parâmetro **af\_sub[1-5]** na URL de saída.

**Para notificar o Google Ads sobre essas instalações:**

**Recomendado:** Configure a <Anchor target="_blank" href="/marketers/pt/docs/google-ads-adwords-create-web-based-campaigns">integração web do Google</Anchor>. Esta integração oferece suporte a postbacks automáticos para instalações.

**Se você não tiver a integração:**

1. Obtenha os dados do GCLID no parâmetro **af\_sub[1-5]** via CSV ou Push API em tempo real para cada instalação.
2. Faça o upload dos dados de GCLID para o Google <Anchor target="_blank" href="https://support.google.com/adwords/answer/7014069">manualmente</Anchor> ou via <Anchor target="_blank" href="https://developers.google.com/google-ads/api/docs/start">Google Ads API</Anchor>.

<div id="note" />

> 📘 **Atenção**
>
> Essa solução GCLID não é oficialmente recomendada pelo Google. Caso o Google desative o parâmetro GCLID, alteraremos o script para que ele aceite as mudanças. Siga as instruções deste artigo, clicando no botão **seguir** no topo da página para ser informado quando houver uma atualização no artigo ou script.

</Accordion>

<div id="facebook-click-id" />

<Accordion title="Facebook FBCLID">

O Meta Ads possui click IDs, chamados de FBCLID. A partir da versão 2.8.1 do Smart Script, quando disponível, o FBCLID será encaminhado automaticamente "no estado em que se encontra" nas URLs de saída geradas pelo Smart Script. Você também pode mapear Click IDs para outros parâmetros de saída para disponibilizá-los nos relatórios de dados brutos da AppsFlyer.

**Para configurar o script para mapear o FBCLID para outros parâmetros:**

1. Selecione um parâmetro na URL de saída que conterá o FBCLID.   
   Recomendação: selecione **af\_sub[1-5]**, para que os dados sejam exibidos nos relatórios de dados brutos da AppsFlyer.
2. Forneça esse item na [lista de argumentos](/docs/set-up-smart-script-to-convert-web-visitors#arguments) para o desenvolvedor da web. O resultado será que, na URL de saída, o FBCLID será o valor do parâmetro **af\_sub[1-5]** .

</Accordion>

<div id="tiktok-ttclid-x-twclid-and-snapsccid" />

<Accordion title="TikTok (ttclid), X (twclid) e Snap (ScCid)">

A atribuição de instalações para campanhas de anúncios do TikTok, X (antigo Twitter) e Snap depende de parâmetros de Click ID específicos de cada rede, que são anexados aos cliques em anúncios e usados para associar instalações e eventos pós-instalação ao anúncio de origem.

Quando o tráfego é redirecionado primeiro para uma página web ou landing page, o Click ID deve ser preservado e encaminhado para garantir a atribuição correta. Nesse caso, o Smart Script captura o parâmetro de Click ID recebido e o anexa à URL de saída que ele gera.

O Click ID será capturado na instalação e usado em eventos futuros associados à instalação.

A partir da versão 2.10.0 do Smart Script, os seguintes parâmetros de Click ID, quando disponíveis, são encaminhados automaticamente nas URLs de saída geradas pelo Smart Script:

* TikTok: ttclid
* X (antigo Twitter): twclid
* Snap: ScCid

Você também pode mapear esses Click IDs para outros parâmetros de saída, como af\_sub1-af\_sub5, para disponibilizá-los nos relatórios de dados brutos da AppsFlyer.

Consulte os seguintes artigos sobre integração web:

* <Anchor target="_blank" href="/marketers/pt/docs/tiktok-for-business-create-web-based-campaigns">TikTok</Anchor>
* <Anchor target="_blank" href="/marketers/pt/docs/snapchat-create-web-based-campaigns">Snap</Anchor>

</Accordion>

<div id="srns-owned-media-and-other-media-source-links" />

<Accordion title="Links de SRNs, mídias próprias e de outros canais de mídia">

<Anchor target="_blank" href="/marketers/pt/docs/self-reporting-networks-srns#srns-integradas-à-appsflyer">SRNs</Anchor> como o Snapchat ou X Ads funcionam de maneira diferente do Google Ads ou de uma cross-platform como o Meta Ads. Nas SRNs, as campanhas levam seus usuários à página web/landing page e você é cobrado de acordo com os clicking leads, sem nenhuma relação com qualquer usuário mobile derivado.

Para SRNs, a configuração do script é a mesma dos links de mídias próprias ou outros canais de mídia que você possa usar.

**Para configurar o script**:

1. Faça uma lista dos canais de mídia e dos nomes dos parâmetros de campanha que estão nos links de entrada.
2. Forneça-os na [lista de argumentos](/docs/set-up-smart-script-to-convert-web-visitors#arguments) para o desenvolvedor da web.  
   O tipo de SRN/canal de mídia corresponde ao valor do canal de mídia na URL de entrada. O script localiza esse valor e o usa como o **media\_source** na URL de saída do OneLink, por trás do botão de download na página da web/landing page. Se você quiser mudar o **media\_source** de saída, forneça o valor de entrada do canal de mídia e o valor override de media\_source na [lista de argumentos](/docs/set-up-smart-script-to-convert-web-visitors#arguments) enviada ao desenvolvedor da web.

**Resultado:** para essas SRNs/canais de mídia, os valores no canal da mídia e nos parâmetros da campanha no link de entrada são usados para preencher os valores para os parâmetros **media\_source** e **campaign**  no link de saída.

<div id="example" />

> 📄 **Exemplo**
>
> **URL de entrada (incoming)**: https://hotel.me/incoming_mediasource=twitter&incoming_campaign=big_social
>
> **URL de saída (outgoing)**: https://hotel.onelink.me/Ac4G?pid=twitter&c=big_social

</Accordion>

<div id="appsflyer-attribution-links" />

<Accordion title="Links de atribuição da AppsFlyer">

Os links de atribuição da AppsFlyer podem ser usados quando o canal de mídia é uma click ad network. Ao configurar esse tipo de link na AppsFlyer, você tem a opção de adicionar um parâmetro de **Redirection URL path (af\_r)** com um URL path específico para seu site mobile para a atribuição web campaign-to-app. Atenção: se o Script criar uma URL de saída do OneLink, alguns dados do clique original podem ser perdidos.

**Ação:** use o argumento **urlSkipList** para listar o parâmetro **af\_r**.

**Resultado**: quando o Smart Script encontra o parâmetro **af\_r** no link de entrada, o Smart Script não produz uma URL de saída. Assim, o desenvolvedor deve decidir qual link colocar como URL de saída e implementá-lo.

<div id="example-1" />

> 📄 **Exemplo**
>
> **URL de entrada (incoming)**: https://app.appsflyer.com/id123456789?pid=click_ad_network_int&c=orlando&af_r=hotel.me
>
> **URL de saída (outgoing)**: sem URL de saída.

</Accordion>

<div id="web-referrer-mapping" />

<Accordion title="Mapeamento de web referrer">

O mapeamento de web referrer mostra a partir de qual página os usuários chegaram ao seu site (por exemplo, resultados de pesquisa orgânica), enriquecendo os dados disponíveis para a análise de instalações e reengajamentos no seu fluxo web-to-app do Smart Script.

Você pode configurar o Smart Script para coletar essas informações da sua landing page ou campo [`Referrer`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Referer) no cabeçalho HTTP do site. Esse campo contém a URL base da página na qual os usuários clicaram antes de serem direcionados para a sua página na web.

**Para configurar o script e ativar a coleta de web referrer**

1. Abra a página do **Smart Script**
2. Em **mapeamento de web referrer**, selecione a chave do parâmetro da URL de saída para o valor do web referrer:
   * af\_channel – o parâmetro está disponível nos dashboards e dados brutos
   * af\_sub1-5 – o parâmetro está disponível nos dados brutos nas colunas **af\_sub1-5** e na coluna **da URL original** .
   * Parâmetro personalizado - é composto pelo nome e valor do parâmetro. O parâmetro é exibido nos dados brutos e na coluna da **URL original**.

Para saber mais sobre a atribuição de pesquisa orgânica para reengajamentos usando Universal Links e App Links, clique <Anchor target="_blank" href="/marketers/pt/docs/set-up-organic-search-seo-and-organic-ai-answers-aeo-re-engagement-attribution">aqui</Anchor>.

</Accordion>

<div id="seo-referrer-mapping" />

<Accordion title="Mapeamento de SEO referrer">

Você pode ativar a opção **"Fonte de mídia para instalações de pesquisa orgânica"** para definir automaticamente a fonte de mídia do tráfego de pesquisa orgânica quando ela ainda não tiver sido resolvida pela seção de **mapeamento de parâmetros de URL**.

* Se o web referrer do usuário corresponder a um mecanismo de busca compatível (por exemplo, google.com ou bing.com), a fonte de mídia será definida como o canal correspondente (por exemplo, google\_organic\_seo).
* Se não houver correspondência, o **valor padrão** configurado no mapeamento de parâmetros de URL será usado.

</Accordion>

<div id="desktop" />

<Accordion title="Desktop">

A maioria dos casos de uso nesse artigo são de usuários provenientes de dispositivos mobile. Portanto, quando direcionados do site mobile para uma loja de aplicativos, eles podem baixar seu aplicativo imediatamente.

No entanto, os usuários de desktop não devem ser enviados imediatamente para uma loja de aplicativos, pois seu dispositivo (desktop ou laptop) não é compatível com downloads de aplicativos mobile.

**Para configurar o script para usuários de desktop**:

* Em seu <Anchor target="_blank" href="/marketers/pt/docs/create-a-onelink-template#como-criar-templates-do-onelink">template do OneLink</Anchor>, defina uma URL de destino para **"quando o usuário clicar no link no desktop"**. A URL deve redirecionar para uma página na web/landing page específica. A landing page pode conter um formulário web onde os usuários preenchem seus dados para receber um SMS ou um e-mail com um link para baixar o aplicativo. Você deve criar formulário e fornecer a URL correspondente no script.

**Resultado:** o script detecta o dispositivo ou a plataforma em que o usuário está. Se for desktop, o script gera uma URL de saída do OneLink que redireciona o usuário para sua página web/landing page.

Consulte também <Anchor target="_blank" href="/marketers/pt/docs/qr-to-app-conversion">Conversão de desktop-to-app</Anchor>.

</Accordion>

<div id="qr-codes" />

<Accordion title="QR codes">

O Smart Script exibe um QR code na sua página web ao invés de um botão com um link por trás dele. 

**Para exibir um QR code:**

1. Lembre-se de usar o Smart Script 2.6+ ao configurar seu Smart Script.
2. Peça ao seu desenvolvedor para seguir <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/onelink-smart-script-v2web-to-app-url-generator#create-a-qr-code-with-the-smart-script-result">as instruções</Anchor> para criar um QR code com o resultado do Smart Script.
3. [Prática recomendada] Diga ao desenvolvedor para:
   * <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_smart_script_v2#create-a-qr-code-with-the-smart-script-result">Personalizar o QR code</Anchor> adicionando o logotipo do aplicativo no centro do código e personalizando a cor.
   * Mostrar o QR code quando os usuários estiverem no desktop e exibir o botão com o link quando os usuários estiverem no mobile.

**Resultado:** o script exibe um QR code em vez de um botão com uma URL por trás dele.

<div id="example-2" />

> 📄 **Exemplo**
>
> **URL de entrada (incoming)**:
>
> https://hotel.me/qr_code.html?incmp=gogo&inmedia=email
>
> **URL de saída (outgoing)**:
>
> https://hotel.onelink.me/LtRd/?af_js_web=true&af_ss_ver=2_1_0&pid=email&c=gogo
>
> **QR code de saída (outgoing)**:
>
> <Image alt="" src="https://files.readme.io/2f06149c901d8a97c2a544b8196e9afecbe3b3748ed8419a39c2dc5e3afa61ba-42045454923153.png" width="48.07%" />

</Accordion>

<div id="impressions" />

<Accordion title="Impressões">

O Smart Script do OneLink pode ser usado para contar impressões no seu site. Para isso, o desenvolvedor precisa chamar a função de impressão. As instalações são atribuídas às impressões por meio da <Anchor target="_blank" href="/marketers/pt/docs/measure-view-through-engagements">atribuição de view-through</Anchor>.

**Atenção**:

* A contagem de impressões se soma à URL normal produzida pelo Smart Script, que conta os cliques. O Smart Script pode ser usado para contar cliques, impressões, ou ambos.
* A atribuição de view-through via Smart Script só funciona em dispositivos mobile, não em desktops.

**Para atribuir novas instalações a essas impressões (que são atribuição de view-through):**

1. Certifique-se de usar o Smart Script 2.3+ quando você configurar seu Smart Script.
2. Peça ao seu desenvolvedor para <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/onelink-smart-script-v2web-to-app-url-generator#fire-an-impression">chamar a função de impressão</Anchor> no Smart Script.
3. Certifique-se <Anchor target="_blank" href="/marketers/pt/docs/measure-view-through-engagements">de que a  atribuição de view-through está habilitada</Anchor>.

<div id="important-2" />

> 🚧 **Importante!**
>
> Desde 1 de fevereiro de 2023 (versão estável do Chrome 110), o Google fez algumas alterações para <Anchor target="_blank" href="https://developer.chrome.com/en/docs/privacy-sandbox/user-agent/">reduzir os dados de User-Agent</Anchor>. Para obter <Anchor target="_blank" href="https://www.appsflyer.com/glossary/view-through-attribution/">atribuições de view-through</Anchor> corretamente usando o OneLink Smart Script, você deve usar a versão 2.3 ou versões mais recentes.

</Accordion>

<div id="additional-information" />

## Informações adicionais

<div id="faq" />

<Accordion title="Perguntas frequentes">

<div id="will-the-incoming-url-for-onelink-link-generation-work-if-the-user-browses-to-a-different-page-on-the-website" />

#### **A URL de entrada para a geração de links do OneLink funciona se o usuário navegar para uma página diferente no site?**

Sim. Os parâmetros de URL de entrada são armazenados durante a sessão de navegação e aplicados aos parâmetros de saída do link do OneLink gerado pelo Smart Script. Para mais informações de implementação, <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_smart_script_v2#preserve-incoming-url-parameters-across-pages">consulte nosso developer hub</Anchor>.

<div id="why-do-i-get-an-error-when-implementing-smart-script-via-google-tag-manager" />

#### **Por que recebo uma mensagem de erro ao implementar o Smart Script por meio do Google Tag Manager?**

Às vezes, quando você gera o Smart Script na AppsFlyer e tenta inseri-lo no Google Tag Manager (GTM), um erro de "JavaScript muito longo" é exibido. Se isso ocorrer, exclua a tag GTM e crie uma nova.

<div id="can-i-add-parameters-that-are-not-listed" />

#### **Posso adicionar parâmetros que não estão listados?**

Sim. Na página do OneLink Smart Script, clique em + **Novo parâmetro** para mapear parâmetros adicionais.

* Novos parâmetros podem ser parâmetros personalizados ou parâmetros reservados da AppsFlyer que não estão listados no menu suspenso.
  * Veja todos os [argumentos adicionais](/docs/set-up-smart-script-to-convert-web-visitors#arguments) (configurações de parâmetros) que você pode usar.
* Use a opção personalizada no menu suspenso e seu parâmetro no campo **Parâmetros de URL de saída**.

Por exemplo, para adicionar is\_retargeting como um parâmetro, o parâmetro personalizado seria selecionado no campo **mapping for** e, em seguida, nosso parâmetro is\_retargeting no campo **Outgoing URL parameters**.

![Smart_Script_Custom.jpg](https://files.readme.io/5a09d18b01ece93bbb47667b676039c98742ebc3b88c5235ad92c7e44d5316b9-small-42045454926609.jpg)

<div id="adset-and-other-parameters-are-not-showing-in-the-dropdown" />

#### **Adset e outros parâmetros não estão aparecendo no menu suspenso**

Recomendamos desativar todos os bloqueadores de anúncios que você possui em seu navegador ao criar ou adicionar novos parâmetros. Às vezes, os bloqueadores de anúncios removem uma opção se ela contiver a palavra "Anúncio" ou "Ad".

<div id="what-browsers-does-smart-script-work-on" />

#### **Em quais navegadores o Smart Script funciona?**

O Smart Script usa Javascript e deve funcionar em todos os navegadores.

</Accordion>

<div id="specs-and-limitations" />

<Accordion title="Especificações e limitações">

| **Especificação** | **Considerações** |
| --- | --- |
| Esquema URI | Mesmo que um esquema URI seja configurado no template do OneLink para abrir o aplicativo para usuários existentes, no caso de links criados usando o Smart Script, o parâmetro af\_dp com o esquema URI deve ser adicionado pelo desenvolvedor como um <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/onelink-smart-script-v2web-to-app-url-generator#set-additional-custom-parameters">parâmetro personalizado</Anchor>. |
| **na URL de entrada (incoming)**| O Smart Script encontra problemas ao processar URLs recebidas que incluem uma hashtag ('#') antes dos parâmetros de consulta (indicados por '?'). Nesses casos, o Smart Script reverte para os valores padrão. |

</Accordion>

<div data-zendesk-anchors="setup=configura%C3%A7%C3%A3o h_01H95PGMNWR12KQ2P0KT8BBGEC=configura%C3%A7%C3%A3o set-up-onelink-smart-script=configurar-o-smart-script h_01H95PGMNW6N63XQ1EQSQSHHB2=configurar-o-smart-script scope-of-work=escopo-do-trabalho h_01H95PGMNWPBRHSZBPMKNJ2PS6=escopo-do-trabalho h_01H95PGMNWWYRRNVNTK31XYRN3=how-to-create-a-onelink-smart-script h_01H95PGMNW5HA4FWBFW7AR89AV=importante h_01H95PGMNXZAES8DPJ1B4E1QV8=how-to-edit-or-delete-a-script h_01H95PGMNX5ZT7DPV2WBG0CTKB=importante-1 h_01H95PGMNXNT9C07B0YTS1KK82=how-to-duplicate-a-script h_01H95PGMNXWJ9V5JW9JEAHF81S=argument-structure h_01H95PGMNXR2HTV1EF07QVQB6W=arguments arguments-parameters-and-values-to-implement-the-smart-script::d4f6bf94=argumentos-par%C3%A2metros-e-valores-para-implementar-o-smart-script h_01H95PGMNXPMCM73XT3GTDVAXJ=argumentos-par%C3%A2metros-e-valores-para-implementar-o-smart-script h_01H95PGMNX4B8W84DHJR9T4CR2=advanced-arguments arguments-parameters-and-values-to-implement-the-smart-script=argumentos-avan%C3%A7ados-par%C3%A2metros-e-valores-para-implementar-no-smart-script h_01H95PGMNXCAHTTJATG75Y3TRN=argumentos-avan%C3%A7ados-par%C3%A2metros-e-valores-para-implementar-no-smart-script use-cases=casos-de-uso h_01H95PGMNXBPFFNE44YGGECBPR=casos-de-uso h_01H95PGMNX3W95JW47YQGSEYQ6=utm-parameters h_01H95PGMNXGZZEMZ6PMAB4XFQQ=google-ads-gclid h_01H95PGMNXZT08G8RTMMG6BQCJ=aten%C3%A7%C3%A3o h_01H95PGMNXHJXGB2QXH0YTB6Z0=facebook-click-id h_01KD5EZQFF23MYGXGJF1CF6VPT=tiktok-ttclid-x-twclid-and-snapsccid h_01H95PGMNXBKXFG9M169WG89TK=srns-owned-media-and-other-media-source-links h_01H95PGMNXZPB6CT3ZKJ2KMQ1J=exemplo h_01H95PGMNX8Q0BASSESVD06MXE=appsflyer-attribution-links h_01H95PGMNX741EJGPF9G2DS67N=exemplo-1 h_01HAS199KS0C0V3G41WGXTK4PF=web-referrer-mapping h_01M1BK4M22YAQ6YX4RZXRKZF7C=seo-referrer-mapping h_01H95PGMNY0P2354ZFVC92TMVC=desktop h_01H95PGMNYDSFP6GJDWC9AE0J2=qr-codes h_01H95PGMNYGJ9BJ86YCP7FYH6G=exemplo-2 h_01H95PGMNYZBGZWNFESDTE9GY9=impressions h_01H95PGMNYX1FDT1KK9PQAMX5N=importante-2 additional-information=informa%C3%A7%C3%B5es-adicionais h_01H95PGMNYB6A8VKEAH8Z8TDPE=informa%C3%A7%C3%B5es-adicionais h_01H95PGMNYKQ8TNM3KKK9EXANV=faq will-the-incoming-url-for-onelink-link-generation-work-if-the-user-browses-to-a-different-page-on-the-website=a-url-de-entrada-para-a-gera%C3%A7%C3%A3o-de-links-do-onelink-funciona-se-o-usu%C3%A1rio-navegar-para-uma-p%C3%A1gina-diferente-no-site h_01H95PGMNYM5X2K9J0WZW6PZ8A=a-url-de-entrada-para-a-gera%C3%A7%C3%A3o-de-links-do-onelink-funciona-se-o-usu%C3%A1rio-navegar-para-uma-p%C3%A1gina-diferente-no-site why-do-i-get-an-error-when-implemeting-smart-script-via-google-tag-manager=por-que-recebo-uma-mensagem-de-erro-ao-implementar-o-smart-script-por-meio-do-google-tag-manager h_01H95PGMNYSQX6BJCN56D4XZZF=por-que-recebo-uma-mensagem-de-erro-ao-implementar-o-smart-script-por-meio-do-google-tag-manager can-i-add-parameters-that-are-not-listed=posso-adicionar-par%C3%A2metros-que-n%C3%A3o-est%C3%A3o-listados h_01H95PGMNY2AVJ0CYDAM62Q9PA=posso-adicionar-par%C3%A2metros-que-n%C3%A3o-est%C3%A3o-listados adset-and-other-parameters-are-not-showing-in-the-dropdown=adset-e-outros-par%C3%A2metros-n%C3%A3o-est%C3%A3o-aparecendo-no-menu-suspenso h_01H95PGMNY97BY6BCPPMYHBF0Q=adset-e-outros-par%C3%A2metros-n%C3%A3o-est%C3%A3o-aparecendo-no-menu-suspenso what-browsers-does-smart-script-work-on=em-quais-navegadores-o-smart-script-funciona h_01H95PGMNY5AV0DTX51X0DJMTK=em-quais-navegadores-o-smart-script-funciona h_01H95PGMNY4W9X51KV6GM4BSPG=specs-and-limitations" />
