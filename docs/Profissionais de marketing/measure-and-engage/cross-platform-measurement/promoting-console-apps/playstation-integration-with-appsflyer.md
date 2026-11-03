---
title: Integração do PlayStation com a AppsFlyer
metadata:
  keywords:
    - CTV
    - Marketers
    - PC & Console Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roi-tamir
    - Marketers
    - PC & Console Attribution
  created_at: '2022-11-03T15:12:14Z'
  edited_at: '2026-09-16T00:20:45Z'
  id: 10342860530961
  locale: pt
  section: Promoting Console apps
  section_id: 15329052471057
  url: https://support.appsflyer.com/hc/pt/articles/10342860530961
---
> **At a glance:** Saiba como integrar seu aplicativo PlayStation ao AppsFlyer e como mensurar anúncios em execução no PlayStation.

Este artigo aborda duas integrações relacionadas, mas distintas.

* [Integre seu aplicativo PlayStation ao AppsFlyer](#integre-seu-aplicativo-do-playstation-com-a-appsflyer): receba dados de atribuição e de evento do seu aplicativo PlayStation, independentemente de onde seus usuários venham.
* [Mensure anúncios em execução no PlayStation](#mensure-anúncios-em-execução-no-playstation): ative a integração do PlayStation Ads para mensurar anúncios em execução nos consoles PlayStation e impulsionar instalações do seu aplicativo.

## Integre seu aplicativo do PlayStation com a AppsFlyer

O sistema operacional do PlayStation para aplicativos de console e CTV (Connected TV) é executado em todos os dispositivos PlayStation.

Os aplicativos em execução no PlayStation podem se integrar à AppsFlyer por meio da API S2S (server-to-server) para receber dados de atribuição e mensuração de performance sobre quais fontes e campanhas impulsionam a abertura do aplicativo e os eventos in-app. Esses insights são usados para mensurar e otimizar atividades de marketing.

A integração da API do PlayStation é compatível com:

* PlayStations.
* Atribuição e registro de eventos para aplicativos do PlayStation, o que significa atribuição e registro no dispositivo PlayStation do usuário.

### Exemplo de fluxo de atribuição

A seguir está um exemplo de fluxo que destaca as etapas mais importantes na jornada do usuário, do engajamento do anúncio à atribuição. Ele Inclui a página de destino multiplataforma recomendada pela AppsFlyer. **Observação**: Embora recomendemos usar a página de destino multiplataforma, você também pode usar links de atribuição direta.

<Image alt="Diagrama do fluxo de atribuição, de um touchpoint de marketing por uma landing page cross-platform até a instalação de um aplicativo PlayStation" src="https://files.readme.io/33c9138ef2064832a0bd5d08d52c84bea3e70efb674af362a8ef0d3e5d505db1-small-16332549715217.jpg" width="3938px" />

1. <span id="marketing-touchpoint"></span>Touchpoints de marketing: clientes interagem com sua marca por meio de canais online ou offline. Eles podem incluir e-mail e newsletters, redes sociais, web mobile e muito mais.
2. Página inicial do jogo: Uma página inicial de um jogo direciona os clientes para a página de download do aplicativo. Esta etapa é importante para coletar UTM (Urchin Tracking Module) e outros parâmetros de URL para atribuir clientes do clique/instalação às fontes e campanhas de mídia originais ou às suas mídias próprias.  
   A página de destino também é útil porque fornece links para as diversas plataformas compatíveis com seu jogo. Por exemplo, você também pode ter links para a sua página do Xbox, da Microsoft Store e do Steam na sua landing page.
3. Página do aplicativo: Este é o URL da página do seu aplicativo no PlayStation que hospeda seu aplicativo para os clientes fazerem download.
4. Instalação do jogo: O usuário instala o jogo, acionando a atribuição e a gravação de eventos e sessões no aplicativo.

### Procedimentos de integração

A tabela abaixo lista as tarefas necessárias para integrar seu aplicativo do PlayStation à AppsFlyer.

| Função | Ações | Quem está envolvido |
| --- | --- | --- |
| Configuração do aplicativo | <ul><li><Anchor target="_blank" href="https://www.appsflyer.com/get-started/">Crie uma conta</Anchor></li><li><Anchor target="_blank" href="/marketers/pt/docs/user-management">Adicione usuários à conta, atribuindo as permissões necessárias</Anchor></li><li><Anchor target="_blank" href="/marketers/pt/docs/adding-an-app-to-appsflyer">Adicione seu aplicativo do PlayStation à AppsFlyer</Anchor></li></ul> | Marketer |
| Integração da API com o seu app (via S2S) | <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/pc-console-ctv-api-overview">Integre a API da AppsFlyer</Anchor> ao seu aplicativo com comandos para reportar os seguintes eventos à AppsFlyer.<ul><li>Primeira abertura do app</li><li>https://files.readme.io/797989d738fddcce1de7a45a98e13b898d53817c285c839ff1fbb5a92522ccf0-19284078965009.jpg</li><li>Sessions</li></ul>**Observação**:<ul><li>Reporte o evento da primeira abertura do aplicativo antes dos eventos in-app e das sessões.</li><li>Para o parâmetro `device_ids`, selecione o tipo `custom`.<ul><li>O ID `personalizado` gerado para as <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/post_first-open-app-platform-app-id">primeiras aberturas</Anchor> deve corresponder ao ID que você usa para <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/post_inapp-app-platform-app-id">eventos in-app</Anchor> e <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/post_session-app-platform-app-id">sessões</Anchor>.</li></ul></li><li>Envie eventos usando a API. Compartilhe com seu programador quais eventos devem ser enviados. Ao configurar a API, verifique se você mapeou os eventos que quer enviar para a AppsFlyer.</li><li>O tipo de ID de dispositivo `psid` é destinado ao uso como ID de publicidade. No momento, o PlayStation não oferece suporte à correspondência de IDs de publicidade, portanto não é necessário usar esse tipo de ID de dispositivo.</li><li>Recomendamos compartilhar o `psn_uid`, que é o ID da conta do PlayStation, no campo `customer_user_id`. Certifique-se de anonimizar o valor antes de compartilhá-lo.</li></ul>Para comunicar os engajamentos de mídias próprias, integre a <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/get_impression-app-platform-app-id">impression engagement API.</Anchor> | Desenvolvedor do aplicativo |
| Configurar uma landing page multiplataforma | **Recomendado**: Uma página inicial multiplataforma que executa o Smart Script da AppsFlyer permite que você faça a atribuição web-to-app. Isso é recomendado quando sua campanha promove um aplicativo que também está disponível em outras plataformas, como Epic e Native PC.<br /><br /><Anchor target="_blank" href="/marketers/pt/docs/ctv-pc-and-console-platform-attribution-concepts#landing-page">Saiba mais sobre landing pages multiplataformas</Anchor><br /><br /><Anchor target="_blank" href="/marketers/pt/docs/cross-platform-landing-pages-with-smart-script">Aprenda a configurar uma landing page multiplataforma</Anchor><br /><br />**Observação**:<br /><br />Para o PlayStation, os seguintes parâmetros são necessários:<ul><li>**plataforma**: playstation</li><li>**app\_id**: O ID do app</li><li>**fonte\_de\_mídia**</li></ul>Os seguintes parâmetros não são obrigatórios, mas são recomendados:<ul><li>**Twitter**</li><li>**Anúncio**</li><li>**ad\_set**</li></ul> | `{1>Profissional de marketing (a assistência de um desenvolvedor pode ser necessária) <1}` |
| Configuração do OneLink | Se você não usa uma página inicial multiplataforma, você pode criar links de atribuição direta e colocá-los em seus anúncios.<br /><br /><Anchor target="_blank" href="/marketers/pt/docs/ctv-pc-and-console-platform-direct-attribution-links">Aprenda a criar links de atribuição direta</Anchor> | Marketer |
| Configuração de relatórios/visualização de dados | <Anchor target="_blank" href="/marketers/pt/docs/ctv-pc-and-console-platform-attribution-concepts#disponibilidade-de-dados">Saiba mais sobre a disponibilidade de dados em painéis e relatórios</Anchor> | Profissional de marketing/engenheiro de dados |

## Mensure anúncios em execução no PlayStation

A AppsFlyer oferece suporte à mensuração de anúncios em execução em consoles PlayStation que impulsionam instalações do seu aplicativo PlayStation. Esse fluxo é separado da integração geral em [Procedimentos de integração](#procedimentos-de-integração) acima; ele se aplica apenas se o PlayStation também for uma das suas fontes de anúncios e está disponível para anunciantes que já têm um aplicativo PlayStation ativo configurado na AppsFlyer.

Para veicular e mensurar anúncios no PlayStation:

1. **Crie um link de atribuição.** Siga as diretrizes em <Anchor target="_blank" href="/marketers/pt/docs/ctv-pc-and-console-platform-direct-attribution-links">links de atribuição direta para plataformas de CTV, PC e console</Anchor> e defina o valor da plataforma como `playstation`.
2. **Envie o link para o PlayStation.** Peça à sua equipe de gestão de anúncios do PlayStation para incluir o link de atribuição nos seus anúncios.
3. **Ative a integração do PlayStation Ads na AppsFlyer.** Use o ID do parceiro `playstation_int`. Para ver as etapas gerais de ativação, consulte <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner">Configurar um parceiro integrado</Anchor>.
4. **Veja os resultados na AppsFlyer.** A performance aparece nos seus dashboards e relatórios padrão da AppsFlyer, atribuída ao canal de mídia do PlayStation.

> 🚧 **Importante:**
>
> Nesta etapa, você não pode compartilhar sinais, como conversões, eventos ou postbacks, com a equipe de anúncios do PlayStation. Os dados de mensuração permanecem na AppsFlyer e não são enviados de volta ao PlayStation para otimização.

### Exemplos de links de atribuição

A seguir, veja exemplos de links de atribuição por clique e por impressão para o PlayStation.

**Click-through rate**

```
https://engagements.appsflyer.com/v1.0/s2s/click/app/playstation/10000000
?af_media_source=playstation_int
&af_campaign_id={campaign_id}
&af_ip={USER_IP}
&af_campaign={campaign_name}
```

**Impressão**

```
https://engagements.appsflyer.com/v1.0/s2s/impression/app/playstation/10000000
?af_media_source=playstation_int
&af_campaign_id={campaign_id}
&af_ip={USER_IP}
&af_campaign={campaign_name}
```

| Placeholder | Tipo de valor esperado | Significado |
| --- | --- | --- |
| 10000000 | Parâmetros do path | O App ID do aplicativo PlayStation do anunciante na AppsFlyer. Substitua pelo App ID real, sem o prefixo da plataforma. |
| s2s / c2s | Parâmetros do path | Se a solicitação é enviada de servidor para servidor (s2s) ou de cliente para servidor (c2s). Substitui o segmento s2s mostrado nos exemplos de URLs acima. A equipe de anúncios do PlayStation decide qual opção se aplica. |
| `{campaign_id}` | Parâmetro de consulta | ID da campanha, preenchido pelo PlayStation. |
| `{campaign_name}` | Parâmetro de consulta | Nome da campanha, preenchido pelo PlayStation. |
| `{USER_IP}` | Parâmetro de consulta | Endereço IP do usuário final, preenchido pelo PlayStation. |

## Especificações e limitações

| Caraterística | A descrição |
| --- | --- |
| Dados de custos | Envie os dados de custo via <Anchor target="_blank" href="/marketers/pt/docs/import-cost-data">Ad Spend Ingestion</Anchor>, usando o método de upload de arquivo por e-mail. |

> 📄 **Veja também**
>
> * <Anchor target="_blank" href="/marketers/pt/docs/ctv-pc-and-console-platform-attribution-concepts">Visão geral da plataforma CTV, PC e console</Anchor>

<div data-zendesk-anchors="integrate-your-playstation-app-with-appsflyer=integre-seu-aplicativo-do-playstation-com-a-appsflyer 01H7Z1HPD0AB0VP6REMBF2HCR8=integre-seu-aplicativo-do-playstation-com-a-appsflyer example-attribution-flow=exemplo-de-fluxo-de-atribui%C3%A7%C3%A3o h_01HP1Q8B11P0Q8F2Z2FRDSPNDE=exemplo-de-fluxo-de-atribui%C3%A7%C3%A3o 01H7Z19FJ54WZ7XV91Y36EKYQ6=marketing-touchpoint 01H7Z1HPD0VAMPEHBPN8MAT3ST=procedimentos-de-integra%C3%A7%C3%A3o run-and-measure-ads-on-playstation=mensure-an%C3%BAncios-em-execu%C3%A7%C3%A3o-no-playstation h_01M2FS60HDHKN7GZWFADVMAEKD=mensure-an%C3%BAncios-em-execu%C3%A7%C3%A3o-no-playstation h_01M2FS60HDVJVBNN2MGCA8CVXG=importante sample-attribution-links=exemplos-de-links-de-atribui%C3%A7%C3%A3o h_01M2FS60HDQGDT1KCSGCPJAFJC=exemplos-de-links-de-atribui%C3%A7%C3%A3o traits-and-limitations=especifica%C3%A7%C3%B5es-e-limita%C3%A7%C3%B5es 01H7Z1HPD0CS7CTX2KS2RVD3VA=especifica%C3%A7%C3%B5es-e-limita%C3%A7%C3%B5es h_01HE0T79YSNWGB3W4S7WEBW1B5=veja-tamb%C3%A9m" />
