---
title: >-
  TikTok for Business—Configuração da integração web para aplicativos de PC e
  console
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
  created_at: '2025-10-31T13:58:16Z'
  edited_at: '2026-09-16T00:30:37Z'
  id: 40500157955601
  locale: pt
  section: TikTok for Business
  section_id: 12192554266385
  url: https://support.appsflyer.com/hc/pt/articles/40500157955601
---
> **Visão geral:** Aprenda como integrar o TikTok Web para aplicativos de PC e console com a AppsFlyer e configurar campanhas no TikTok Web.

> ❗️ **Atenção**
>
> Essa integração está disponível apenas para aplicativos de PC e console como Steam, Epic ou Native PC. Para apps mobile, consulte a página <Anchor target="_blank" href="/marketers/pt/docs/tiktok-for-business-advanced-srn-integration-setup">TikTok ads integration setup</Anchor> .

## Escritórios

Este artigo contém informações e etapas sobre como configurar e usar o TikTok web para aplicativos de PC e console com a AppsFlyer.

### Pré-requisito

Antes de ativar a integração do TikTok web, certifique-se de que você tem uma conta comercial no TikTok Ads Manager.

## Ativando o parceiro na AppsFlyer

**Para ativar a integração do parceiro:**

1. Na AppsFlyer, no menu lateral, abra **Colaborar** > **Integrações de parceiros > Marketplace** aba.
2. Pesquise por **TikTok Web** (`tiktokweb_int`).
3. Clique em **Configurar integração**. Você será direcionado para a página de configuração.
4. Na aba **Integração**, ative **Ativar parceiro**. O botão deve permanecer <Anchor target="_blank" href="/marketers/pt/docs/partner-activation-deactivation">ativado</Anchor> enquanto você trabalhar com o parceiro.
5. Conclua a configuração usando as abas relevantes, conforme descrito na próxima seção.

## Configuração do TikTok web na AppsFlyer

Nesta parte da configuração, você também pode configurar postbacks para o TikTok Web pela API de eventos do TikTok. A integração do TikTok web (tiktokweb\_int) usa uma ferramenta de API de eventos fornecida pelo TikTok ads para que os anunciantes enviem dados de seus **aplicativos de PC e console** diretamente para os servidores do TikTok. Esses dados podem incluir ações do usuário como compras, cadastros e outros tipos de conversões realizadas em plataformas fora do ecossistema mobile (sites ou aplicativos). Os dados são usados pelo TikTok ads para otimizar a segmentação de anúncios, mensurar a performance dos anúncios e criar audiências personalizadas para retargeting.

A integração com o TikTok web oferece suporte apenas ao envio de postbacks de instalação e eventos in-app.

<div id="integration-tab" />

<Accordion title="Aba Integração">

A aba **Integração** inclui várias seções, conforme descrito abaixo.

#### Ativar parceiro

Para configurar a integração, você deve primeiro ativar o **Ativar parceiro** .

#### Configurações gerais

* **ID do pixel:** Insira o ID do pixel. Você pode gerá-lo ou recuperá-lo no seu TikTok Ads Manager seguindo as instruções detalhadas [AQUI](https://business-api.tiktok.com/portal/docs?id=1771100865818625).
* **Token de acesso:** Insira o token de acesso. Para gerá-lo ou recuperá-lo, siga [estas instruções](https://business-api.tiktok.com/portal/docs?id=1771100865818625)
* **Limitar o uso, pelo TikTok ads, das informações pessoais dos usuários (CCPA):** Ative esta opção para garantir compliance com <Anchor target="_blank" href="/marketers/pt/docs/send-opendsr-api-requests">leis de proteção de dados</Anchor>.

  > 📘 **Nota**
  >
  > A conformidade com as normas de privacidade da CCPA limita os dados provenientes de usuários do TikTok ads localizados na Califórnia ou em outros estados sensíveis dos EUA.


#### Ative a atribuição de view-through

A AppsFlyer oferece suporte à atribuição de view-through para campanhas do TikTok web usando modelo probabilístico (PMOD) e uma [Smart Script](https://www.notion.so/TikTok-Web-integration-setup-for-PC-and-console-apps-28fb7b13af5f8084bf59f621577b3bcb?pvs=21) ou [Smart Banner](https://www.notion.so/TikTok-Web-integration-setup-for-PC-and-console-apps-28fb7b13af5f8084bf59f621577b3bcb?pvs=21)-enabled landing page. Isso permite que a AppsFlyer atribua instalações de aplicativos que resultam de usuários que visualizaram um anúncio e depois instalaram o aplicativo, mesmo em diferentes plataformas, sem exigir um clique direto.

Quando um usuário clica em um anúncio do TikTok web e acessa uma [Smart Script](https://www.notion.so/TikTok-Web-integration-setup-for-PC-and-console-apps-28fb7b13af5f8084bf59f621577b3bcb?pvs=21) ou [Smart Banner](https://www.notion.so/TikTok-Web-integration-setup-for-PC-and-console-apps-28fb7b13af5f8084bf59f621577b3bcb?pvs=21)-enabled landing page, a AppsFlyer pode atribuir a instalação do aplicativo downstream. Se disponível, o `ttclid` será incluído no postback para o TikTok a fim de aumentar a fidelidade da atribuição.

Para ativar a atribuição de view-through:

1. Na AppsFlyer, na barra lateral, abra **Colaborar** > **Integrações de parceiros** > **Integrações ativas** > **Anúncios web do TikTok**.
2. Na aba **Integração**, vá até a seção **Atribuição de instalação**.
3. Ative a **Atribuição de instalação por view-through**.
4. **[Opcional]** Ative a **Prioridade de atribuição equitativa entre plataformas** e defina sua janela de lookback. Para mais informações, veja o artigo <Anchor target="_blank" href="/marketers/pt/docs/set-up-cross-platform-links-for-multi-device-campaigns#step-3-enable-equal-priority-for-crossplatform-impressions">Ativar prioridade equitativa para impressões entre plataformas</Anchor>.
5. Clique na aba do **link de atribuição**.
6. Vá até **Atribuição de view-through** e defina a **janela de lookback de view-through** desejada (de até 24 horas).
7. Clique em **Salvar integração** para aplicar suas configurações.

#### Postbacks padrão

Os postbacks de instalação são enviados automaticamente apenas para o TikTok web.

#### Aba Permissões

Configure o mapeamento de postbacks de eventos in-app enviados para o TikTok web. Esses eventos podem ser visualizados no TikTok Ads Manager

1. Ative **Postbacks de eventos in-app.**
2. Para mapear a nova ação de conversão para o evento de postback da AppsFlyer, recupere o ID da ação de conversão: Na página **Resumo** das metas de conversão, clique na ação de conversão que você criou e copie o valor do parâmetro de consulta `ctid=*` do URL da página. A tabela a seguir descreve os campos a serem preenchidos:

| **Nome do parâmetro** | **A descrição** |
| --- | --- |
| Evento na AppsFlyer | O nome do evento, conforme recebido do SDK integrado no aplicativo ou de eventos de servidor para servidor.<ul><li>Clique em Adicionar item, insira o nome do evento e clique em.</li></ul> |
| Mapeado para evento do parceiro | O nome ou ID único de cada evento, como definido pelo parceiro.<ul><li>Selecione na caixa suspensa o evento de parceiro predefinido mais adequado</li></ul> |
| para utilizadores de | Apenas esse parceiro: os postbacks de eventos in-app são enviados apenas para eventos atribuídos a esse parceiro, ou seja, o usuário que realizou esses eventos chegou ao seu app a partir desse parceiro em específico. |
| Incluindo | Valores e receita: todos os parâmetros de eventos, incluindo o valor da receita (se existir), são enviados no postback. |

3. [Opcional] Clique no ícone **Adicionar condição** para <Anchor target="_blank" href="/marketers/pt/docs/in-app-event-postback-configuration#postbacks-condicionais-de-eventos-in-app">definir condições</Anchor> para um evento.
4. Defina a **janela de postbacks de eventos in-app**, se necessário (saiba mais sobre a <Anchor target="_blank" href="/marketers/pt/docs/in-app-event-postback-configuration#janela-de-postback-de-eventos-in-app">configuração dessa janela aqui</Anchor>).
5. Clique em **Salvar integração**.
6. [Opcional] Após salvar a integração, você pode integrar mais aplicativos com o parceiro em questão:
   1. No canto superior esquerdo, abaixo do nome do parceiro, clique no nome do aplicativo para abrir a lista de apps.
   2. Selecione um aplicativo diferente a partir da lista suspensa.
   3. Repita as etapas de integração para o aplicativo selecionado.

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Separador de Links de Atribuição">

A opção de criar um link de atribuição na AppsFlyer não está disponível no momento. No entanto, você pode usar uma landing page multiplataforma com o SmartScript ou criar um link de atribuição direto (veja a tabela abaixo).

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
        **Recomendado**: Quando sua campanha promove um aplicativo que também está disponível em várias plataformas, como Epic e Steam.  
        <Anchor target="_blank" href="/marketers/pt/docs/ctv-pc-and-console-platform-attribution-concepts#landing-page">Saiba mais sobre landing pages multiplataforma</Anchor>  
        <Anchor target="_blank" href="/marketers/pt/docs/cross-platform-landing-pages-with-smart-script">Saiba como configurar uma landing page multiplataforma</Anchor>

        * Certifique-se de que todos os parâmetros de URL relevantes (que serão posteriormente capturados pelo Smart Script) sejam anexados à URL do anúncio
        * Certifique-se de que o script pegue o TTCLID da URL de entrada e o adicione ao link gerado. Ou seja, mapeie o parâmetro de URL ttclid de saída para o parâmetro de URL ttclid de entrada. **Nota**! Para exibir nos relatórios de dados brutos da AppsFlyer, o parâmetro ttclid de entrada também deve ser mapeado para um dos parâmetros de saída  `af_sub[1-5]`.
        * Opcional: use as macros dinâmicas de URL do TikTok em vez de codificar os valores manualmente. [Saiba mais](https://ads.tiktok.com/help/article/track-offsite-web-events-with-utm-parameters)
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
        Se você não usa uma landing page multiplataforma, pois você possui somente 1 app em 1 plataforma, você pode criar links de atribuição direta e colocá-los em seus anúncios.   
        <Anchor target="_blank" href="/marketers/pt/docs/ctv-pc-and-console-platform-direct-attribution-links">Saiba como criar links de atribuição direta</Anchor>

        * Certifique-se de que os parâmetros obrigatórios estejam incluídos em seu link:
          * `media_source`
          * `af_campaign_id`
          * `af_r`
        * Use as seguintes macros recomendadas para o parâmetro `af_os_version`:
          * Clique: `__OS_VERSION__`
          * Impressão: `__TPL_OS_VERSION__`

        Template a ser usado para o link de anúncio web do TikTok:

        ```http
        https://engagements.appsflyer.com/v1/c2s/click/app/{platform}/{app_id}?af_media_source=tiktokweb_int&af_campaign_id=__CAMPAIGN_ID__&af_campaign=__CAMPAIGN_NAME__&af_adset=__AID_NAME__&af_adset_id=__AID__&af_ad=__CID_NAME__&af_ad_id=__CID__&af_r={encoded landing page and URL params}&af_os_version=__TPL_OS_VERSION__
        ```

        Exemplo de link de anúncio web do TikTok que leva ao Steam:

        ```http
        https://engagements.appsflyer.com/v1.0/c2s/click/app/steam/123456?af_media_source=tiktokweb_int&af_campaign_id=__CAMPAIGN_ID__&af_campaign=__CAMPAIGN_NAME__&af_adset=__AID_NAME__&af_adset_id=__AID__&af_ad=__CID_NAME__&af_ad_id=__CID__&af_r=https%3A%2F%2Fstore.steampowered.com%2Fapp%2F440%2FTest_app2%2F%3Futm_term%3Dhello&af_os_version=__OS_VERSION__
        ```

        **Observação**: O template inclui alguns parâmetros de URL dinâmicos suportados pelo TikTok. Se preferir, você pode substituí-los manualmente por valores reais.
      </td>
      <td>
        Marketer
      </td>
    </tr>
  </tbody>
</Table>

> 👍 **Dica**
>
> Para simplificar a análise da campanha, inclua o tipo de campanha (web ou mobile) como um prefixo ou sufixo no nome da campanha (por exemplo, nome-da-campanha\_web)

</Accordion>

<div id="cost-tab" />

<Accordion title="Aba de Custos">

O custo não está disponível para o TikTok web.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Receita de anúncios">

A receita de anúncios não está disponível para o TikTok web.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Aba permissões">

No momento, as permissões não são concedidas ao TikTok web.

</Accordion>

## Configurar campanhas no TikTok web para aplicativos de PC e console

Ao configurar sua nova campanha:

* Selecione **Website** como local de conversão.
* Ao nomear seu pixel de conversão do TikTok, insira o mesmo ID de pixel inserido para `tiktokweb_int` no *AppsFlyer Partner Marketplace*.
* Ao selecionar o URL do site como destino do seu anúncio, o URL deve ser:
  * Uma web landing page (recomendado quando o seu aplicativo está disponível em mais de uma plataforma)
  * Store URL (recomendado quando o seu aplicativo está disponível em uma única loja ou plataforma.

## Ver os dados de atribuição de web-to-app

Embora os eventos de conversão baseados na web sejam enviados ao TikTok sob o PID original `tiktokweb_int`, eles são reportados no dashboard da AppsFlyer e nos relatórios de dados brutos sob o PID `tiktokglobal_int`. Isso se aplica tanto a eventos de conversão primários quanto a eventos de assistência de conversão.

Essa visualização unificada permite que você analise a performance das campanhas na web e no aplicativo em um só lugar, incluindo relatórios completos de custos na web e no mobile.

### Ver no dashboard

Todas as atribuições de web-to-app do TikTok aparecem sob `tiktokglobal_int` nos dashboards de visão geral e de atividade. Isso fornece uma visão única e consolidada dos resultados da campanha em várias plataformas. Use filtros e detalhamentos padrão para comparar o tráfego do aplicativo e da web nos seus dados do TikTok Ads.

### Ver em dados brutos e relatórios da API

As exportações de dados brutos e as respostas da API incluem o PID `tiktokglobal_int` no campo `media_source` para a atividade web do TikTok. Para verificar os detalhes da configuração da campanha na web, consulte o campo `original_url`, que mostra o PID `tiktokweb_int` usado durante a criação da campanha na web.

## Especificações e limitações

| Caraterística | A descrição |
| --- | --- |
| Cliques e impressões (limitação temporária) | Cliques e impressões para campanhas com segmentação para aplicativos de PC & console estão temporariamente indisponíveis no TikTok SRN. |

<div data-zendesk-anchors="h_01K8X90869H29Q9N873FAT8BM4=aten%C3%A7%C3%A3o overview=escrit%C3%B3rios h_01K8X90869QTX2RG0KHHM8EHAT=escrit%C3%B3rios prerequisite=pr%C3%A9-requisito h_01K8X9086AJ6B9BKNF0EZQASCJ=pr%C3%A9-requisito activating-partner-in-appsflyer=ativando-o-parceiro-na-appsflyer h_01K8X9086ADTE56DR3MK8MXAFR=ativando-o-parceiro-na-appsflyer setting-up-tiktok-web-in-appsflyer=configura%C3%A7%C3%A3o-do-tiktok-web-na-appsflyer h_01K8X9086AMHZR7GADTH8N07DZ=configura%C3%A7%C3%A3o-do-tiktok-web-na-appsflyer h_01K8X9086AHN8761VPM4QA7E6S=integration-tab activate-partner=ativar-parceiro h_01K8XAAM5SH1XXNX0DNGGS5NHT=ativar-parceiro general-settings=configura%C3%A7%C3%B5es-gerais h_01K8XAATC3M5NW722QD93DRN94=configura%C3%A7%C3%B5es-gerais h_01K8X9086A2FFDCRE2JHXQHGET=nota enable-viewthrough-attribution=ative-a-atribui%C3%A7%C3%A3o-de-view-through h_01K8XAB2SK68WTGYZY7EGHR4SZ=ative-a-atribui%C3%A7%C3%A3o-de-view-through default-postbacks=postbacks-padr%C3%A3o h_01K8XABK08NCFQSRN41ASKQ7SY=postbacks-padr%C3%A3o inapp-event-postbacks=aba-permiss%C3%B5es h_01K8XAC3NAYY8S012K2W60TKBJ=aba-permiss%C3%B5es h_01K8X9086A001XKD94G50XY708=attribution-link-tab h_01K88N0TDSFDX5J22YWZPF2J1N=dica h_01K8X9086AFH7J75J9K1QRV1DR=cost-tab h_01K8X9086ACM5WBH6GW243A0PZ=ad-revenue-tab h_01K8X9086AEHV42XZZKA0ATBH2=permissions-tab setting-up-campaigns-in-tiktok-web-for-pc-and-console-apps=configurar-campanhas-no-tiktok-web-para-aplicativos-de-pc-e-console h_01K8X9086AARVTEDRMQW32BABF=configurar-campanhas-no-tiktok-web-para-aplicativos-de-pc-e-console TikTok-view=ver-os-dados-de-atribui%C3%A7%C3%A3o-de-web-to-app view-webtoapp-attribution-data-from-november-2-2025=ver-os-dados-de-atribui%C3%A7%C3%A3o-de-web-to-app h_01K88J8JFNEYBZNR18133NMRP9=ver-os-dados-de-atribui%C3%A7%C3%A3o-de-web-to-app view-in-the-dashboard=ver-no-dashboard h_01K88J8JFNMHCVZ0C34E3D7AST=ver-no-dashboard view-in-raw-data-and-api-reports=ver-em-dados-brutos-e-relat%C3%B3rios-da-api h_01K88J8JFN8W2572N92466YFZQ=ver-em-dados-brutos-e-relat%C3%B3rios-da-api traits-and-limitations=especifica%C3%A7%C3%B5es-e-limita%C3%A7%C3%B5es h_01KB58BEK7MDZGT7G7RQ9VK9MZ=especifica%C3%A7%C3%B5es-e-limita%C3%A7%C3%B5es" />
