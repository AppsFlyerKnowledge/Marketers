---
title: Mensuração de campanha com preservação da privacidade
metadata:
  keywords:
    - Agencies
    - Ad Networks
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-moran-davida
    - Marketers
    - Mobile Attribution
    - Agencies
    - Ad Networks
  created_at: '2023-11-28T07:10:15Z'
  edited_at: '2026-08-18T00:10:19Z'
  id: 20489739742609
  locale: pt
  section: Attribution scenarios
  section_id: 6551328497041
  url: https://support.appsflyer.com/hc/pt/articles/20489739742609
---
> **Em resumo:** Encontre respostas para as dúvidas mais comuns nas perguntas frequentes sobre métodos de mensuração de campanha com preservação da privacidade, as networks envolvidas e as implicações no retargeting, no view-through e nas limitações de aplicativos direcionados a crianças.

<div id="overview" />

## Escritórios

Na atual era de maior conscientização sobre privacidade, plataformas e tecnologias estão limitando cada vez mais o uso de IDs de anunciantes, direcionando a vertical para métodos de mensuração que atendam aos requisitos de privacidade, sem deixar de permitir uma mensuração eficaz de campanhas. Para esses casos, a AppsFlyer oferece suporte a vários métodos de mensuração de campanha com preservação da privacidade para ad networks SRN e não SRN, conforme descrito abaixo.

<div id="what-methods-of-attribution-dont-require-collecting-device-ids" />

<Accordion title="Como a AppsFlyer mensura a performance da campanha quando os IDs de anunciante não estão disponíveis?">

A AppsFlyer fornece os seguintes métodos de mensuração:

* <Anchor target="_blank" href="/marketers/pt/docs/appsflyer-attribution-model#install-referrer-android-only">Correspondência por Install referrer</Anchor> (apenas para Android)
* <Anchor target="_blank" href="/marketers/pt/docs/appsflyer-attribution-model#probabilistic-modeling">Parâmetros de modelagem probabilística para ad networks</Anchor>
* <Anchor target="_blank" href="/marketers/pt/docs/appsflyer-attribution-model#deep-link">Deep linking</Anchor> (apenas para retargeting)

</Accordion>

<div id="what-networks-can-be-attributed-without-using-a-device-id" />

<Accordion title="Quais métodos de atribuição as ad networks oferecem suporte?">

**Ad networks não SRN** podem ser mensuradas usando os métodos adicionais de atribuição com preservação da privacidade descritos nas [perguntas frequentes acima](#what-methods-of-attribution-dont-require-collecting-device-ids).

**A maioria das** <Anchor target="_blank" href="/marketers/pt/docs/self-reporting-networks-srns">**SRNs**</Anchor> exige um ID de publicidade para a mensuração; no entanto, algumas, conforme especificado abaixo, oferecem suporte a outros métodos com preservação da privacidade.

| SRN | Mensuração |
| --- | --- |
| SRNs avançadas (como TikTok e Snapchat) | Com base em cliques e impressões da SRN avançada |
| Anúncios Meta | <ul><li><Anchor target="_blank" href="/marketers/pt/docs/meta-ads-integration-setup#aggregate-event-measurement-aem-para-ios">Usando AEM para dispositivos iOS</Anchor></li><li><Anchor target="_blank" href="/marketers/pt/docs/meta-ads-integration-setup#getting-userlevel-data-for-android-installs">Usando os seguintes parâmetros para dispositivos Android:</Anchor><ul><li>`gp_referrer`</li><li>`fb_referrer`</li><li>`ig_referrer`</li></ul></li></ul> |
| Google Ads | Usando o parâmetro `gbraid` para dispositivos iOS |
| Apple Search Ads | Usando a <Anchor target="_blank" href="/marketers/pt/docs/apple-ads-integration-setup#asa-attribution">atribuição ASA</Anchor> |
| <ul><li>Google Ads</li><li>Meta Ads</li><li>Snapchat</li><li>Tiktok</li><li>Anúncios X</li><li>Yahoo! Japan</li></ul> | <Anchor target="_blank" href="/marketers/pt/docs/skadnetwork-skan-solution-guide">SKAN</Anchor> |

</Accordion>

<div id="can-i-measure-retargeting-without-using-the-device-id" />

<Accordion title="Quais opções de mensuração de retargeting a AppsFlyer oferece?">

A atribuição de retargeting pode ser usada com os métodos mencionados [acima](#what-methods-of-attribution-dont-require-collecting-device-ids).   
**Observação:** a atribuição por Install referrer (para Android) é somente para reatribuições, não para reengajamentos.

</Accordion>

<div id="can-i-measure-viewthrough" />

<Accordion title="A mensuração de view-through é compatível com os métodos acima?">

O view-through é compatível por meio de <Anchor target="_blank" href="/marketers/pt/docs/appsflyer-attribution-model#probabilistic-modeling">modelagem probabilística</Anchor>. Outros métodos, como referrer e deep linking, oferecem suporte à mensuração de clique, mas não à view-through.

Saiba mais sobre a <Anchor target="_blank" href="/marketers/pt/docs/appsflyer-attribution-model#viewthrough-attribution">atribuição de view-through</Anchor>.

</Accordion>

<div id="can-deep-linking-be-done-without-a-device-id" />

<Accordion title="O deep linking requer um ID de publicidade?">

O deep linking de usuários de uma campanha para uma atividade específica no seu aplicativo pode ocorrer em diferentes cenários, dependendo de o aplicativo já estar instalado.

A disponibilidade de um ID de publicidade pode afetar o comportamento do deep linking, dependendo dos cenários a seguir:

* **Deep linking direto:** **sem impacto**.   
  O deep link direciona os usuários existentes diretamente para uma atividade específica no seu aplicativo. Conforme especificado na <Anchor target="_blank" href="/marketers/pt/docs/appsflyer-attribution-model#métodos-de-atribuição">tabela de métodos de atribuição</Anchor>, a atribuição é feita usando os detalhes na URL do deep link, que é enviada diretamente ao SDK.
* **Deep linking indireto:** **funciona somente se a atribuição for bem-sucedida**.   
  O deep link direciona os usuários existentes para uma atividade específica no seu aplicativo, mas o aplicativo não consegue abrir diretamente. Quando o usuário abre o aplicativo novamente mais tarde, um reengajamento é registrado e o **deep linking indireto é realizado. No entanto, isso acontece somente se a atribuição for bem-sucedida** (usando os métodos de atribuição [descritos acima](#what-methods-of-attribution-dont-require-collecting-device-ids)). Portanto, se a atribuição for bem-sucedida, o deep linking também funcionará.
* **Deferred deep linking:** **funciona somente se a atribuição for bem-sucedida**.  
  O deep link direciona novos usuários para a loja de aplicativos. Após a instalação, o aplicativo abre em uma atividade específica. **Isso acontece somente se a atribuição for bem-sucedida** (usando os métodos de atribuição [descritos acima](#what-methods-of-attribution-dont-require-collecting-device-ids)). Portanto, se a ausência de um ID de anunciante ainda permitir a atribuição, o deep linking também funcionará.

</Accordion>

<div id="what-are-the-implications-of-childdirected-app-limitations-on-attribution" />

<Accordion title="Como a mensuração difere quando um ID de publicidade não está disponível?">

Em determinados cenários com restrições de privacidade, a cobertura da mensuração pode ser mais limitada. A AppsFlyer continua fornecendo uma mensuração significativa de campanha, preservando a privacidade do usuário.

</Accordion>

<div id="see-also" />

> 📄 **Consulte também**
>
> * <Anchor target="_blank" href="/marketers/pt/docs/preserve-user-privacy">Preservar a privacidade do usuário</Anchor>
> * <Anchor target="_blank" href="/marketers/pt/docs/additional-sdk-integration-guide#privacidade-do-usuário">Privacidade do usuário no nível do SDK</Anchor>

<div data-zendesk-anchors="eeee=escrit%C3%B3rios h_01HMBEZD0P31S8N9ZERB17ZHPT=escrit%C3%B3rios h_01HGAC6QR6XJ20K92DE8KQ02P3=what-methods-of-attribution-dont-require-collecting-device-ids 01HMEBCTBWJX03WEHY3QTR3RAS=what-networks-can-be-attributed-without-using-a-device-id h_01HGAC6QR7VXFNPENAXTAV97Y7=can-i-measure-retargeting-without-using-the-device-id h_01HGAC6QR7E298ZTH8G4TTD7EC=can-i-measure-viewthrough h_01HMRHWVEQCHS7QBJHPZS3B8KZ=can-deep-linking-be-done-without-a-device-id h_01HGAC6QR752QPT4MSDQ7TWAXT=what-are-the-implications-of-childdirected-app-limitations-on-attribution h_01HGAC6QR7R4ZTWJEMSKHACNPF=consulte-tamb%C3%A9m" />
