---
title: Mensuração de atribuição com mais de uma MMP
metadata:
  keywords:
    - Marketers
    - Platform essentials
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-negri
    - Marketers
    - Platform essentials
  created_at: '2023-07-27T08:29:19Z'
  edited_at: '2026-08-18T00:18:12Z'
  id: 17316973509393
  locale: pt
  section: Marketer onboarding
  section_id: 6550866490129
  url: https://support.appsflyer.com/hc/pt/articles/17316973509393
---
> **Visão geral:** veja quais canais de mídia conseguem mensurar a atribuição simultânea de mais de uma MMP. Assim, você pode comparar os resultados de atribuição da AppsFlyer com os de outras MMPs.

## Visão geral

Ao considerar migrar para a AppsFlyer, é possível que você queira comparar a mensuração das duas MMPs simultaneamente, nos mesmos canais de mídia e campanhas. Para isso, é necessário que:

* O aplicativo de teste tenha **integrado os SDKs das duas MMPs**
* Os canais de mídia tenham sido **configurados para oferecer suporte à atribuição com duas MMPs**

No entanto, nem todos os canais de mídia oferecem suporte à mensuração com mais de uma MMP.  

## Informações e limitações

Listamos abaixo todas as informações e limitações dos canais de mídia ao trabalhar simultaneamente com mais de uma MMP.

### Redes de autorrelato

| SRN | Informações e limitações | Compatível com mensuração |
| --- | --- | --- |
| Anúncios de Busca da Apple | O ASA oferece suporte sem limitações. Quando há uma solicitação de chamada de API de várias MMPs, os dados são enviados às MMPs correspondentes. | ✓ |
| DV360 (GMP) | Há suporte para mais de uma MMP. No entanto, a configuração da campanha deve ter itens de linha separados para cada acompanhamento/tag do Floodlight (link ID). | ✓ |
| Google Ads | O Google Ads oferece suporte para a mensuração em mais de uma MMP:<ul><li>Os anunciantes podem vincular os link IDs das MMPs a uma única conta do Google Ads e receber postbacks de cada uma delas</li><li>O Google Ads pode receber postbacks de mais de uma MMP</li><li>A performance de cada MMP pode ser mensurada</li></ul>**Observação:** quando os dados passam a ser enviados à nova MMP, o Google Ads recomenda o interrompimento da integração antiga. | ✓ |
| Meta Ads | O Meta Ads recebe solicitações de dados de mais de uma MMP. No entanto, recomendamos que você **não** tenha mais de uma MMP nesse canal pelos seguintes motivos:<ul><li>O Meta Ads só consegue fazer a desduplicação de instalações. Assim, os eventos devem ser enviados de uma única MMP</li><li>Ao inserir mais de um SDK, há uma alta probabilidade da ocorrência de problemas e erros secundários durante o processo de desduplicação.</li><li>Quando uma grande quantidade de dados é enviada para o Meta Ads, os dados duplicados podem acabar sendo inseridos em seus sistemas de otimização e mensuração.</li></ul>Assim, a atribuição de mais de uma MMP é compatível somente por um curto período de tempo. | Limitada |
| Snapchat | É possível transferir dados entre o Snapchat e várias MMPs. No entanto, recomendamos que você reduza ao máximo o período de sobreposição da migração. Ao receber dados de mais de uma MMP, esse canal não oferece a opção de otimização para uma MMP específica. Isso significa que a otimização é feita para ambas as MMPs e há uma grande probabilidade de sobreposição dos dados. | Limitada |
| TikTok para Empresas | O envio de postbacks para o TikTok for Business é compatível com uma única MMP. Ao migrar de outra MMP, para permitir que a AppsFlyer atribua conversões ao TikTok for Business, primeiro você terá que desativar os postbacks antigos para depois fazer a configuração da AppsFlyer. | X |
| AppsFlyer | Sem suporte para a integração com mais de uma MMP | X |

### SKAN

O envio de <Anchor target="_blank" href="/marketers/pt/docs/skan-conversion-studio#conceitos-básicos-do-skan-conversion-studio">postbacks de conversão da SKAN</Anchor> **não é compatível com mais de uma MMP**. Apenas um SDK pode acionar o envio de postbacks para parceiros. Isso significa que, quando mais de um SDK estiver integrado ao seu aplicativo, os postbacks da SKAN serão enviados para um único SDK.

### Ad networks que não são SRN

Os links de atribuição registram os engajamentos dos usuários e, posteriormente, são usados para a atribuição de engajamentos que se tornam instalações reais. Para permitir a atribuição simultânea de várias MMPs, a ad network deve garantir que os seguintes requisitos sejam atendidos:

| Requisitos | Atenção |
| --- | --- |
| Os dados de engajamento devem ser enviados para as duas MMPs | <ul><li>**Cliques:** como os links de atribuição redirecionam os usuários para uma loja de aplicativos, apenas um link pode ser usado. Recomendamos que você continue usando o link de atribuição da sua MMP antiga para <Anchor target="_blank" href="/partners/pt/docs/redirecting-users-to-the-app-store#visão-geral">enviar dados de atribuição de cliques para a AppsFlyer</Anchor>.</li><li>**Impressões:** como as impressões não redirecionam os usuários para uma loja de aplicativos, a ad network deve enviar os dados de impressão para ambas as MMPs.</li></ul> |
| Postbacks de instalação devem ser desduplicados | As ad networks recebem postbacks de instalação de ambas as MMPs. Para evitar cobranças duplas, a ad network deve desduplicar um desses postbacks. |
| Postbacks de eventos in-app devem ser desduplicados | Quando cada uma das MMPs é configurada para enviar postbacks de eventos in-app, as ad networks recebem esses postbacks de ambas as MMPs. Para evitar duplicações na atribuição e, consequentemente, cobranças duplas, a ad network deve desduplicar esses postbacks. Se a ad network não fizer isso, certifique-se de que os postbacks de eventos in-app sejam configurados em uma única MMP. |

### Mídias próprias

Assim como acontece com ad networks que não são SRNs, a atribuição de instalações de mídias próprias requer o uso de links de atribuição de MMPs. No entanto, para alguns tipos de mídias próprias, como listas de e-mail, SMS ou QR codes, as MMPs podem enviar os dados de um engajamento somente uma vez. A solução de <Anchor target="_blank" href="/marketers/pt/docs/convert-your-mobile-web-visitors-to-app-users">atribuição web-to-app mobile</Anchor> da AppsFlyer permite que você mensure **instalações provenientes de um site ou de uma landing page**. A vantagem do uso de mídias próprias para comparar a atribuição entre duas MMPs é o fato de que não é necessário desduplicar nenhuma instalação ou evento.

## Como evitar discrepâncias de atribuição

Quando as MMPs usam diferentes modelos de atribuição para mensurar o tráfego, podemos observar algumas discrepâncias. Você pode minimizar esse problema da seguinte forma:

* Certifique-se de que ambas as MMPs usam o mesmo fuso horário para o aplicativo. Saiba mais sobre como <Anchor target="_blank" href="/marketers/pt/docs/changing-app-time-zone-settings">configurar o fuso horário do seu app na AppsFlyer</Anchor>.
* Para não SRNs e mídias próprias: configure o link de atribuição usando os mesmos valores de parâmetro. Por exemplo, configure a mesma janela de lookback para ambas as MMPs.
* Ao comparar dados nos dashboards e relatórios de diferentes MMPs, certifique-se de usar os mesmos critérios. Por exemplo, compare o tráfego do mesmo período de tempo, na mesma localização.

<div data-zendesk-anchors="ability-to-measure-with-multiple-mmps=vis%C3%A3o-geral 01H7TP9P86DE0J04VHXJYKE3PA=vis%C3%A3o-geral details-and-limitations-of-media-source-measurement=informa%C3%A7%C3%B5es-e-limita%C3%A7%C3%B5es 01H81ANMGMEKCZCS2FNBY67321=informa%C3%A7%C3%B5es-e-limita%C3%A7%C3%B5es selfreporting-networks=redes-de-autorrelato 01H81APGNBGCMREZVFXJW9KN6H=redes-de-autorrelato 01H7TP9P86YQ75N0XFY7EW2JHQ=skan nonsrn-ad-networks=ad-networks-que-n%C3%A3o-s%C3%A3o-srn 01H7TP9P86TEWC47MZZVQ1965K=ad-networks-que-n%C3%A3o-s%C3%A3o-srn owned-media=m%C3%ADdias-pr%C3%B3prias 01H7W2YTXYMAEN403WCHYH8G7W=m%C3%ADdias-pr%C3%B3prias avoiding-attribution-discrepancies=como-evitar-discrep%C3%A2ncias-de-atribui%C3%A7%C3%A3o 01H7YVHVW3YY8XY8GHQX1B0WZN=como-evitar-discrep%C3%A2ncias-de-atribui%C3%A7%C3%A3o" />
