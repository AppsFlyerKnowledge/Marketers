---
title: 'Boletim: transição da integração do Google Marketing Platform (GMP)'
metadata:
  keywords:
    - Agencies
    - Marketers
    - Mobile Attribution
table_of_contents: false
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
    - Agencies
  created_at: '2023-12-18T11:43:04Z'
  edited_at: '2026-10-20T03:55:52Z'
  id: 21035061438737
  locale: pt
  section: Bulletins
  section_id: 6551161473041
  url: https://support.appsflyer.com/hc/pt/articles/21035061438737
---

<Table>
  <tbody>
    <tr>
      <td>
        **Novidades**
      </td>
      <td>
        Como parte dos preparativos para a <Anchor target="_blank" href="https://commission.europa.eu/strategy-and-policy/priorities-2019-2024/europe-fit-digital-age/digital-markets-act-ensuring-fair-and-open-digital-markets_en">Lei de Marketing Digital</Anchor> (DMA), o Google está atualizando sua <Anchor target="_blank" href="https://www.google.com/about/company/user-consent-policy/?sjid=15416941068016224808-NA">política de consentimento para usuários da UE</Anchor>. A AppsFlyer está fazendo as alterações necessárias para atender aos requisitos dessa nova política.

        As seguintes integrações do Google Marketing Platform (GMP) estão disponíveis:

        * [Legada] CM360 (DoubleClick) `doubleclick_int`
        * <Anchor target="_blank" href="/marketers/pt/docs/google-marketing-platform-display-video-360-dv360-integration">DV360 (nova integração)</Anchor> `dv360_int`

        A partir de julho de 2024, a integração legada doubleclick\_int está em modo de descontinuação e será descontinuada em breve (a data final será anunciada). Se você usa essa integração, é necessário fazer a transição para a nova integração DV360 para continuar realizando campanhas e mensurando-as usando o GMP.
      </td>
    </tr>
    <tr>
      <td>
        **Ação necessária**
      </td>
      <td>
        Faça a transição para a nova integração `dv360_int` do DV360 o mais rápido possível e, no máximo, até 30 de junho de 2025.
      </td>
    </tr>
    <tr>
      <td>
        **Passo a passo**
      </td>
      <td>
        Configure ambas as plataformas, GMP e AppsFlyer:

        **Configuração no GMP**

        1. Faça login na sua conta CM360 ou DV360.   
           **Observação:** se você concluir as etapas necessárias no CM360, você não terá que concluí-las novamente no DV360.
        2. Crie ou reutilize seu link de atribuição de parceiro (Link ID) seguindo <Anchor target="_blank" href="https://support.google.com/displayvideo/answer/10956727">essas instruções</Anchor>.

        **Configuração na AppsFlyer**

        1. Conclua a integração do DV360 na AppsFlyer usando <Anchor target="_blank" href="/marketers/pt/docs/google-marketing-platform-display-video-360-dv360-integration#integration-procedures">essas instruções</Anchor>.   
           **Observação:** para manter a consistência dos dados, certifique-se de que a nova configuração seja parecida com a da integração legada (janelas de lookback, postbacks de eventos in-app, etc).
        2. **Teste a nova integração.**   
           Aguarde cerca de um dia para confirmar os novos dados de integração. Você pode então desativar a integração legada.
      </td>
    </tr>
    <tr>
      <td>
        **O que você precisa saber**
      </td>
      <td>

      </td>
    </tr>
    <tr>
      <td>

      </td>
      <td>
        <table><thead><tr><th><strong>Considerações</strong></th><th>Opções disponíveis</th></tr></thead><tbody><tr><td colspan="2"><span id="media-source-pid"></span><strong>PID do canal de mídia</strong></td></tr><tr><td><span id="after-completing-the-migration-the-dv360-media-source-pid-changes-from-doubleclick_int-to-dv360_int"></span>Depois de concluir a migração, o PID do DV360 muda de <kbd>doubleclick_int</kbd> para <kbd>dv360_int</kbd>.</td><td>Se você extrai dados brutos da AppsFlyer para seu BI ou qualquer outra ferramenta de analytics, recomendamos que você altere o nome do canal de mídia.</td></tr><tr><td colspan="2"><span id="outofstore-apps"></span><strong>Aplicações fora das lojas</strong></td></tr><tr><td><span id="apps-from-unofficial-app-stores-arent-supported-in-the-dv360-integration-the-integration-relies-on-a-link-id-which-is-generated-for-apps-obtained-through-official-app-stores"></span>Aplicativos de lojas de aplicativos não oficiais não são suportados na integração do DV360. A integração depende de um ID de link, que é gerado para aplicativos obtidos através de lojas de aplicativos oficiais.</td><td>Se o seu aplicativo for baixado de fontes fora das lojas de aplicativos oficiais, entre em contato com seu CSM ou hello@appsflyer.com.</td></tr><tr><td colspan="2"><span id="attribution-data-duplication"></span><strong>Distribuição de dados de atribuição</strong></td></tr><tr><td colspan="2"><span id="while-both-integrations-are-active-in-appsflyer-data-duplication-is-expected-inapp-events-for-installsreengagements-attributed-to-the-legacy-integration-remain-credited-accordingly"></span>Quando ambas as integrações estão ativas e reivindicam a atribuição por instalações, a atribuição é dividida aleatoriamente entre elas, com uma sendo a fonte primária e a outra atuando como contribuinte. Isso garante que os dados não sejam duplicados. Por exemplo, se o DV360 for responsável por 100 instalações, você pode ver 70 instalações da integração legada e 30 do DV360, ou 80 instalações do DV360 e 20 instalações da integração legada.</td></tr><tr><td colspan="2"><span id="inapp-events-for-installsreengagements-attributed-to-the-legacy-integration-remain-credited-accordingly"></span>Os eventos in-app para instalações/reengajamentos atribuídos à integração legada permanecem creditados de acordo.</td></tr><tr><td colspan="2"><span id="reengagement-reengagement-attribution-is-supported-in-the-dv360-integration"></span><p><strong>Reengajamento</strong></p><p>A atribuição de reengajamento é suportada na integração do DV360.</p></td></tr></tbody></table>

        **Discrepâncias de campo**

        Devido a diferenças entre os campos de dados disponíveis nas APIs legadas e atualizadas, você pode ver diferenças em alguns campos do AppsFlyer, conforme visto abaixo:

        | **Campo AppsFlyer** | **Campo legado (doubleclick\_int)** | **Campo DV360 (dv360\_int)** |
        | --- | --- | --- |
        | Nome da campanha | placement\_id | line\_item\_name |
        | ID da campanha | placement\_id | line\_item\_id |
        | Nome do conjunto de anúncios | id\_anúncio | N/D (não compatível) |
        | ID do conjunto de anúncios | id\_anúncio | N/D (não compatível) |
        | Nome do anúncio | creative\_id | N/D (não compatível) |
        | ID do anúncio | creative\_id | creative\_id |
      </td>
    </tr>
  </tbody>
</Table>

<div data-zendesk-anchors="while-both-integrations-are-active-in-appsflyer-data-duplication-is-expected%0Ainapp-events-for-installsreengagements-attributed-to-the-legacy-integration-remain-credited-accordingly=while-both-integrations-are-active-in-appsflyer-data-duplication-is-expected-inapp-events-for-installsreengagements-attributed-to-the-legacy-integration-remain-credited-accordingly reengagement%0Areengagement-attribution-is-supported-in-the-dv360-integration=reengagement-reengagement-attribution-is-supported-in-the-dv360-integration" />
