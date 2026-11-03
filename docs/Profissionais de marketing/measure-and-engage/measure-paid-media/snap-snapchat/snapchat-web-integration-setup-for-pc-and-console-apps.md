---
title: Configuração da integração do Snapchat—web para aplicativos de PC e console
metadata:
  keywords:
    - Marketers
    - PC & Console Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roi-tamir
    - Marketers
    - PC & Console Attribution
  created_at: '2025-11-28T12:53:35Z'
  edited_at: '2026-09-16T00:30:23Z'
  id: 41396370612497
  locale: pt
  section: Snap (Snapchat)
  section_id: 6551316540945
  url: https://support.appsflyer.com/hc/pt/articles/41396370612497
---
> **Visão geral:** Aprenda como integrar o Snapchat Ads web a aplicativos de PC e console com a AppsFlyer e configurar campanhas no Snapchat Ads web.

> ❗️ **Atenção**
>
> Essa integração está disponível apenas para aplicativos de PC e console como Steam, Epic ou Native PC. Para apps mobile, consulte a <Anchor target="_blank" href="/marketers/pt/docs/tiktok-for-business-advanced-srn-integration-setup">página de configuração da integração do Snapchat Ads</Anchor> .

## Escritórios

Este artigo contém informações e um passo a passo sobre como configurar e usar o Snapchat Ads web para aplicativos de PC e console com a AppsFlyer.

### Pré-requisito

Antes de ativar a integração do Snapchat Ads web, certifique-se de que você tenha uma conta comercial no <Anchor target="_blank" href="https://businesshelp.snapchat.com/s/topic/0TO8b000000KfssGAC/ads-manager?language=en_US">Snapchat Ads Manager.</Anchor>

## Ativando o parceiro na AppsFlyer

**Para ativar a integração do parceiro:**

1. Na AppsFlyer, no menu lateral, abra **Colaborar** > **Integrações de parceiros > Marketplace** aba.
2. Pesquise por **Snapchat Ads web** (`snapweb_int`).
3. Clique **Integrate**. Você será direcionado para a página de configuração.
4. Na aba **Integração** , habilite **Ativar parceiro**. O botão deve permanecer <Anchor target="_blank" href="/marketers/pt/docs/partner-activation-deactivation">ativado</Anchor> enquanto você trabalhar com o parceiro.
5. Conclua a configuração usando as abas relevantes, conforme descrito na próxima seção.

## Configurando o Snapchat Ads web na AppsFlyer

Nesta parte da configuração, você também pode configurar postbacks para o Snapchat Ads web por meio da API de eventos do Snapchat. A integração do Snapchat Ads web (`snapweb_int`) usa uma ferramenta de Events API fornecida pelo Snapchat Ads, permitindo que os anunciantes enviem dados dos seus **aplicativos de PC e console** diretamente para os servidores do Snapchat. Esses dados podem incluir ações do usuário como compras, cadastros e outros tipos de conversões realizadas em plataformas fora do ecossistema mobile (sites ou aplicativos). Os dados são usados pelo Snapchat Ads para otimizar a segmentação de anúncios, mensurar a performance dos anúncios e criar audiências personalizadas para retargeting.

A integração com o Snapchat Ads web oferece suporte apenas ao envio de postbacks de instalações e eventos in-app.

<div id="integration-tab" />

<Accordion title="Aba Integração">

A aba **Integração** inclui várias seções, conforme descrito abaixo.

**Ativar parceiro**

Para configurar a integração, você deve primeiro habilitar o botão **Ativar parceiro** .

**Configurações gerais**

* **ID do pixel:** Insira o ID do pixel. Você pode criá-lo ou recuperá-lo do seu Snapchat Ads Manager seguindo as instruções detalhadas na <Anchor target="_blank" href="https://businesshelp.snapchat.com/s/article/pixel-website-install?language=en_US">documentação oficial do Snapchat Ads</Anchor>[.](https://businesshelp.snapchat.com/s/article/pixel-website-install?language=en_US)
* **Token de acesso:** Insira o token de acesso. Para gerá-lo ou recuperá-lo, siga as instruções [in](https://businesshelp.snapchat.com/s/article/pixel-website-install?language=en_US) a <Anchor target="_blank" href="https://developers.snap.com/api/marketing-api/Conversions-API/GetStarted">documentação oficial do Snapchat Ads</Anchor>[.](https://developers.snap.com/api/marketing-api/Conversions-API/GetStarted)

**Ative a atribuição de view-through**

A AppsFlyer oferece suporte à atribuição de view-through para campanhas do Snapchat Ads web usando modelo probabilístico (PMOD) e uma landing page habilitada para [Smart Script](#create-a-landing-page-with-onelink-smart-script) ou [Smart Banner](#create-a-landing-page-with-onelink-smart-banners). Isso permite que a AppsFlyer atribua instalações de aplicativos que resultam de usuários que visualizaram um anúncio e depois instalaram o aplicativo, mesmo em diferentes plataformas, sem exigir um clique direto.

Quando um usuário clica em um anúncio do Snapchat na web e acessa uma landing page habilitada para [Smart Script](#create-a-landing-page-with-onelink-smart-script) ou [Smart Banner](#create-a-landing-page-with-onelink-smart-banners), a AppsFlyer pode atribuir a instalação do aplicativo posteriormente. Se disponível, o `ScCid` será incluído no postback para o Snapchat para aumentar a fidelidade da atribuição.

**Para ativar a atribuição de view-through:**

1. Na AppsFlyer, no menu lateral, abra **Active Integrations** > **Snapchat Ads web ads**.
2. Na aba **Integração**, vá até a seção **Atribuição de instalação**.
3. Ative a **Atribuição de instalação por view-through**.
4. **[Opcional]** Ative a **Prioridade de atribuição equitativa entre plataformas** e defina sua janela de lookback. Para mais informações, veja o artigo <Anchor target="_blank" href="/marketers/pt/docs/set-up-cross-platform-links-for-multi-device-campaigns#step-3-enable-equal-priority-for-crossplatform-impressions">Ativar prioridade equitativa para impressões entre plataformas</Anchor>.
5. Clique na aba do **link de atribuição**.
6. Vá até **Atribuição de view-through** e defina a **janela de lookback de view-through** desejada (de até 24 horas).
7. Clique em **Salvar integração** para aplicar suas configurações.

**Postbacks padrão**

Os postbacks de instalações são enviados automaticamente apenas para o Snapchat Ads web.

**Aba Permissões**

Configure o mapeamento dos postbacks de eventos in-app enviados para o Snapchat Ads web. Esses eventos podem ser visualizados no [Snapchat Ads Manager](https://businesshelp.snapchat.com/s/topic/0TO8b000000KfssGAC/ads-manager?language=en_US).

1. Ative **Postbacks de eventos in-app.**
2. Para mapear a nova ação de conversão para o evento de postback da AppsFlyer, recupere o ID da ação de conversão: Na página **Resumo** das metas de conversão, clique na ação de conversão que você criou e copie o valor do parâmetro de consulta `ctid=*` do URL da página. A tabela a seguir lista e descreve os campos:

| **Nome do parâmetro** | **A descrição** |
| --- | --- |
| Evento na AppsFlyer | O nome do evento, conforme recebido do SDK integrado no aplicativo ou de eventos de servidor para servidor.<ul><li>Clique em Adicionar item e insira o nome do evento.</li></ul> |
| Mapeado para evento do parceiro | O nome exclusivo ou ID de cada evento, conforme definido pelo parceiro.<ul><li>Selecione na lista o evento de parceiro predefinido mais adequado.</li></ul> |
| para utilizadores de | Somente este parceiro: os postbacks de eventos in-app são enviados apenas para eventos atribuídos a este parceiro. |
| Incluindo | Valores e receita: todos os parâmetros do evento, incluindo o valor da receita (se existir no evento), são enviados no postback. |

3. [Opcional] Clique no ícone **Adicionar condição** para <Anchor target="_blank" href="/marketers/pt/docs/in-app-event-postback-configuration#postbacks-condicionais-de-eventos-in-app">definir condições</Anchor> para um evento. Para mais informações, consulte <Anchor target="_blank" href="/marketers/pt/docs/in-app-event-postback-configuration#postbacks-condicionais-de-eventos-in-app">Postbacks de eventos in-app condicionais</Anchor>.
4. Configure a **janela de postback de evento in-app**. Para mais informações, consulte <Anchor target="_blank" href="/marketers/pt/docs/in-app-event-postback-configuration#janela-de-postback-de-eventos-in-app">janela de postback de evento in-app</Anchor>.
5. Clique em **Salvar integração**.
6. [Opcional] Após salvar a integração, você pode integrar mais aplicativos com o parceiro em questão:
   1. No canto superior esquerdo, abaixo do nome do parceiro, clique no nome do aplicativo para abrir a lista de apps.
   2. Selecione um aplicativo diferente a partir da lista suspensa.
   3. Repita as etapas de integração para o aplicativo selecionado.

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Separador de Links de Atribuição">

A opção de criar um link de atribuição na AppsFlyer não está disponível no momento. Você pode usar uma landing page multiplataforma com SmartScript ou criar um link de atribuição direta para seu aplicativo. Consulte a tabela abaixo.

<Table>
  <thead>
    <tr>
      <th>
        Opção
      </th>
      <th>
        Ações
      </th>
      <th>
        Quem está envolvido
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        Landing page multiplataforma
      </td>
      <td>
        **Recomendado.** Use esta opção quando sua campanha promover um aplicativo disponível em várias plataformas, como Epic e Steam.  
        <Anchor target="_blank" href="/marketers/pt/docs/ctv-pc-and-console-platform-attribution-concepts#landing-page">Saiba mais sobre landing pages multiplataforma</Anchor>  

        <Anchor target="_blank" href="/marketers/pt/docs/cross-platform-landing-pages-with-smart-script">Saiba como configurar uma landing page multiplataforma</Anchor>  
        Certifique-se de que todos os parâmetros de URL relevantes (que depois são capturados pelo Smart Script) sejam anexados à URL do anúncio

        * Certifique-se de que o script pegue o valor `ScCid` da URL de entrada e o adicione ao link gerado. Isso significa que você deve mapear o parâmetro de URL de saída `ScCid` para o parâmetro de entrada `ScCid`.  
          **Observação:** Para exibir o `ScCid` nos relatórios de dados brutos da AppsFlyer, o parâmetro de entrada `ScCid` também deve ser mapeado para um dos parâmetros de saída `af_sub[1–5]`.
        * OPCIONAL. Você pode usar macros de URL dinâmicas do Snapchat em vez de codificar os valores manualmente. Para mais informações, consulte a [documentação oficial do Snapchat](https://businesshelp.snapchat.com/s/article/add-url-macros?language=en_US).
      </td>
      <td>
        `{1>Profissional de marketing (a assistência de um desenvolvedor pode ser necessária) <1}`
      </td>
    </tr>
    <tr>
      <td>
        Link de atribuição direta
      </td>
      <td>
        Se você não usa uma landing page multiplataforma, porque você só tem um aplicativo em uma plataforma, pode criar links de atribuição direta para colocar em anúncios.   
        <Anchor target="_blank" href="/marketers/pt/docs/ctv-pc-and-console-platform-direct-attribution-links">Saiba como criar links de atribuição direta</Anchor>

        Certifique-se de que os parâmetros obrigatórios estejam incluídos em seu link:

        * `media_source`
        * `af_campaign_id`
        * `af_r`

        **Template para usar no link de anúncio web do Snapchat Ads:**

        ```
        https://engagements.appsflyer.com/v1.0/c2s/click/app/{platform}/{app_id}?af_media_source=snapweb_int&af_campaign_id={{campaign.id}}&af_campaign={{campaign.name}}&af_adset={{adSet.name}}&af_adset_id={{adSet.id}}&af_ad={{creative.name}}&af_ad_id={{ad.id}}&af_channel={{site_source_name}}&af_r={encoded landing page and URL params}
        ```

        **Exemplo de link de anúncio web do Snapchat que leva ao Steam:**

        ```
        https://engagements.appsflyer.com/v1.0/c2s/click/app/steam/123456?af_media_source=snapweb_int&af_campaign_id={{campaign.id}}&af_campaign={{campaign.name}}&af_adset={{adSet.name}}&af_adset_id={{adSet.id}}&af_ad={{creative.name}}&af_ad_id={{ad.id}}&af_r=https%3A%2F%2Fstore.steampowered.com%2Fapp%2F440%2FTest_app2%2F%3Futm_term%3Dhello
        ```

        **Observação**: o template inclui alguns parâmetros de URL dinâmicos compatíveis com o Snapchat. Se preferir, você pode substituí-los manualmente por valores reais.
      </td>
      <td>
        Marketer
      </td>
    </tr>
  </tbody>
</Table>

</Accordion>

<div id="cost-tab" />

<Accordion title="Aba de Custos">

O custo não está disponível para o Snapchat Ads para web.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Receita de anúncios">

A receita de anúncios não está disponível no Snapchat Ads web.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Aba permissões">

No momento, as permissões não são concedidas no Snapchat Ads web.

</Accordion>

## Configuração de campanhas no Snapchat Ads web para aplicativos de PC e console

Configure sua campanha no Snapchat Ads Manager. Para obter mais informações, consulte <Anchor target="_blank" href="/marketers/pt/docs/snapchat-create-web-based-campaigns#configurar-a-integração-da-appsflyer-no-snapchat-ads">Configurar a integração da AppsFlyer no Snapchat Ads</Anchor>.

Ao configurar sua nova campanha:

* Selecione **website** como local de conversão.
* Ao nomear seu pixel de conversão do Snapchat, insira o mesmo ID de pixel que você inseriu para `snapweb_int` no *AppsFlyer Partner Marketplace*.
* Ao selecionar o URL do site como destino do seu anúncio, o URL deve ser:
  * Uma web landing page (recomendado quando o seu aplicativo está disponível em mais de uma plataforma)
  * Store URL (recomendado quando o seu aplicativo está disponível em uma única loja ou plataforma.

## Ver os dados de atribuição de web-to-app

Embora os eventos de conversão baseados na web sejam enviados para o Snapchat sob o PID original `snapweb_int`, eles são relatados no dashboard da AppsFlyer e nos relatórios de dados brutos com o PID `snapchat_int`. Isso se aplica tanto a eventos de conversão primários quanto a eventos de assistência de conversão.

Essa visualização unificada permite que você analise a performance das campanhas na web e no aplicativo em um só lugar, incluindo relatórios completos de custos na web e no mobile.

### Ver no dashboard

Todas as atribuições de web-to-app do Snapchat aparecem sob `snapchat_int` nos dashboards de Visão Geral e de Atividade. Isso fornece uma visão única e consolidada dos resultados da campanha em várias plataformas. Use filtros e detalhamentos padrão para comparar o tráfego do aplicativo e da web nos seus dados do Snapchat Ads.

### Ver em dados brutos e relatórios de API

* **Exportações de dados brutos e respostas de API** incluem o PID `snapchat_int` no campo `media_source` para a atividade web do Snapchat. Para verificar os detalhes da configuração da campanha web, consulte o campo `original_url`, que mostra `snapweb_int` como o PID usado durante a criação de campanhas web.
* **Relatórios de postback** mostram `snapweb_int` como o canal de mídia original para o qual o postback foi enviado.

## Especificações e limitações

| Caraterística | Descrição |
| --- | --- |
| Cliques e impressões (limitação temporária) | Cliques e impressões para campanhas com segmentação para aplicativos de PC & Console estão temporariamente indisponíveis no Snapchat SRN. |

<div data-zendesk-anchors="h_01KB58BEK73PMXZXB8RA59YHM2=aten%C3%A7%C3%A3o overview=escrit%C3%B3rios h_01KB58BEK78P4C35JYZXKJFPHW=escrit%C3%B3rios prerequisite=pr%C3%A9-requisito h_01KB58BEK77YP1T2XCHZJ00V7S=pr%C3%A9-requisito activating-partner-in-appsflyer=ativando-o-parceiro-na-appsflyer h_01KB58BEK7A3MJT4C9ZA9ZFGDA=ativando-o-parceiro-na-appsflyer setting-up-snapchat-ads-web-in-appsflyer=configurando-o-snapchat-ads-web-na-appsflyer h_01KB58BEK7CGYB1DZJCG2WMH0Y=configurando-o-snapchat-ads-web-na-appsflyer h_01KB58BEK7SE837F67MKRFY6K2=integration-tab h_01KB58BEK74Q2K3SNCPFQSCJ2B=attribution-link-tab h_01KB58BEK7WAVABV4YBR728FCF=cost-tab h_01KB58BEK7ESEZFARRQ3HB6P8H=ad-revenue-tab h_01KB58BEK7WXEFMSSB0QRE4E6B=permissions-tab setting-up-campaigns-in-snapchat-ads-web-for-pc-and-console-apps=configura%C3%A7%C3%A3o-de-campanhas-no-snapchat-ads-web-para-aplicativos-de-pc-e-console h_01KB58BEK7D8760J2ZWJ9B1K3Y=configura%C3%A7%C3%A3o-de-campanhas-no-snapchat-ads-web-para-aplicativos-de-pc-e-console view-webtoapp-attribution-data=ver-os-dados-de-atribui%C3%A7%C3%A3o-de-web-to-app h_01KB58BEK7M96WYN7YMERH7CWW=ver-os-dados-de-atribui%C3%A7%C3%A3o-de-web-to-app view-in-the-dashboard=ver-no-dashboard h_01KB58BEK70FB5SYQAV938CB5W=ver-no-dashboard view-in-raw-data-and-api-reports=ver-em-dados-brutos-e-relat%C3%B3rios-de-api h_01KB58BEK7YWM10A7RCNV7YDEM=ver-em-dados-brutos-e-relat%C3%B3rios-de-api traits-and-limitations=especifica%C3%A7%C3%B5es-e-limita%C3%A7%C3%B5es h_01KB58BEK7MDZGT7G7RQ9VK9MZ=especifica%C3%A7%C3%B5es-e-limita%C3%A7%C3%B5es" />
