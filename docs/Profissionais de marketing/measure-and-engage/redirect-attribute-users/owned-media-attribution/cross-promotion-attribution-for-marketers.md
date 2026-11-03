---
title: Atribuição promoção cruzada para profissionais de marketing
metadata:
  keywords:
    - tracking
    - Advertisers
    - Cross Promotion
    - cross-promotion
    - Marketers
    - OneLink
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-asaf-mashiah
    - Marketers
    - OneLink
  created_at: '2017-08-30T13:26:03Z'
  edited_at: '2026-08-18T00:35:40Z'
  id: 115004481946
  locale: pt
  section: Owned media attribution
  section_id: 6551214397585
  url: https://support.appsflyer.com/hc/pt/articles/115004481946
---
> **Visão geral:** Atribuir instalações de campanhas de promoção cruzada que promovem os seus aplicativos em outros aplicativos que você possui.

![CrossPromo_jornadaDoUtilizador](https://files.readme.io/4ecc5b536021355247c51f1a19b23d71623da9f9578387622d6c6f0a57d4801b-4404615401489.png)

## Sobre a promoção cruzada

As campanhas de promoção cruzada são uma das melhores formas de promover seus aplicativos existentes ou de orientar os seus usuários para novos aplicativos lançados pela sua empresa. Este tipo de campanha pode resultar em taxas de conversão e retenção mais elevadas em comparação com a maioria das outras fontes de tráfego. Como a promoção cruzada é publicidade em mídias próprias, você pode usar [a correspondência de ID de dispositivo](/docs/cross-promotion-attribution-for-marketers#atribuição-de-promoção-cruzada) para atribuir deterministicamente novas instalações. A atribuição de promoção cruzada está disponível para todas as contas, independentemente do seu plano da AppsFlyer.

A imagem seguinte mostra o painel do aplicativo promovido com um detalhamento das métricas para campanhas executadas em meios de comunicação próprios **(af\_cross\_promotion**) e outras fontes de comunicação. Você pode ver que o número de instalações e a taxa de conversão da campanha de promoção cruzada são muito mais elevados do que os dos outros canais de mídia.

[![CrossPromo_origemDeMídia](https://files.readme.io/e9a085a0fb987a559c4d35db956d3258c5ee783807eb5e2a222716f0259c1c16-4404613090321.png)](https://files.readme.io/e9a085a0fb987a559c4d35db956d3258c5ee783807eb5e2a222716f0259c1c16-4404613090321.png)

### Como a promoção cruzada funciona?

1. O usuário recebe um anúncio de promoção cruzada em um aplicativo existente que pertence à sua empresa. O anúncio está promovendo outro aplicativo que também pertence à sua empresa. O anúncio criativo pode ser um banner, um vídeo ou qualquer objeto clicável.
2. [opcional] O <Anchor target="_blank" href="/marketers/pt/docs/cross-promotion-attribution-for-developers">SDK registra e envia</Anchor> uma impressão de promoção cruzada para a AppsFlyer.
3. O usuário clica no anúncio.
4. O SDK registra o clique e redireciona o usuário para a página do aplicativo promovido na loja de aplicativos. O clique registrado pelo SDK já inclui o ID de publicidade do dispositivo.
5. Quando o aplicativo promovido é instalado e iniciado, o [painel da AppsFlyer](/docs/cross-promotion-attribution-for-marketers#painel-de-controle-de-aplicativos-promovidos) mostra o usuário recém-adquirido no canal de mídia **af\_cross\_promotion**.
   * Para alterar o valor do canal de mídia, seu desenvolvedor precisa adicionar um parâmetro personalizado chamado `pid` com o valor desejado. **Observação**: Observação: para Android, isso só funciona para o SDK V6.4.2+.
   * O aplicativo que conduz a instalação, o aplicativo de origem, aparece como um **ID do site** deste canal de mídia.
6. O SDK gera automaticamente um evento in-app.  
   O nome do evento para Android é `af_cross_promotion` e para iOS  é`af_cross_promotion_clicked`.

## Atribuição de promoção cruzada

A AppsFlyer permite que você use a correspondência de ID de dispositivo como método de atribuição para registrar e atribuir instalações que têm origem nas suas campanhas de promoção cruzada. Você pode atribuir impressões e cliques, o que permite que você calcule a <Anchor target="_blank" href="/marketers/pt/docs/about-conversion-rates#estágios-de-funil-de-marketing-e-taxas-de-conversão-1">taxa de cliques</Anchor> ou a taxa instalações/impressões.

O identificador de dispositivo usado para a correspondência depende do seguinte:

* O dispositivo do usuário e a versão do sistema operacional
* A versão do SDK da AppsFlyer no aplicativo de origem

| Correspondência de ID de dispositivo para promoção cruzada | Versão do dispositivo/SO | Versão do SDK | Observações |
| --- | --- | --- | --- |
| IDFA | iOS 9 – 14.4 | V5.0.0+ |  |
| IDFV | Lançamento+ | V6.0.2+ | O IDFV é coletado automaticamente, nenhuma ação adicional é exigida pelo desenvolvedor. |
| GAID | Dispositivos Android com serviços Google Play |  |  |
| OAID, Android ID, IMEI, Fire ID | Dispositivos Android sem Google Play Services |  |  |

## Configurar promoção cruzada

O processo de configuração da atribuição de promoção cruzada exige que o profissional de marketing e o desenvolvedor trabalhem juntos para implementar um código adicional no SDK da AppsFlyer.

O fluxo para o profissional de marketing e para o desenvolvedor é o seguinte:

| Etapa | Cargo | Função | Atenção |
| --- | --- | --- | --- |
| 1 | Marketer | Decida quais aplicativos existentes em que executar a campanha de promoção cruzada. | O aplicativo de origem atribuído à instalação aparecerá como o **ID do site** no painel do aplicativo promovido. |
| 2 | Marketer | Determine se você deseja incluir <Anchor target="_blank" href="/marketers/pt/docs/about-link-structure-and-parameters">parâmetros adicionais</Anchor>, como a janela de lookback, o nome do conjunto de anúncios e os parâmetros do assinante. Envie estes nomes e valores de parâmetros adicionais para o desenvolvedor. |  |
| 3 | Desenvolvedor | Implementar o código no SDK. | A documentação do desenvolvedor está <Anchor target="_blank" href="/marketers/pt/docs/cross-promotion-attribution-for-developers">aqui</Anchor>. |
| 4 | Marketer | No [painel de controle do aplicativo promovido](/docs/cross-promotion-attribution-for-marketers#painel-de-controle-de-aplicativos-promovidos), veja o tráfego proveniente da campanha de promoção cruzada e otimize as suas campanhas de acordo. |  |
| 5 [Opcional] | Marketer | Crie um [painel de controle personalizado](/docs/cross-promotion-attribution-for-marketers#painel-personalizado) para comparar o tráfego de promoções cruzadas e compartihe dados com os usuários da conta. |  |

## Visualizar dados de promoção cruzada

### Painel de controle de aplicativos promovidos

O painel de controle do aplicativo promovido permite que você determine quais aplicativos de origem enviam o melhor tráfego para o aplicativo promovido.

**Para comparar o tráfego dos aplicativos de origem:**

1. Vá para **Visão geral**.
2. Selecione o canal de mídia **af\_cross\_promotion** (ou o seu canal de mídia personalizado).
3. Agrupe por **ID do site** para ver a lista de aplicativos de origem.[![CrossPromo_IDDoSite](https://files.readme.io/e057085e90a4a8e56e6769a0af332785488d7757cb5430418e8db6b3cfa67210-4404613179025.png)](https://files.readme.io/e057085e90a4a8e56e6769a0af332785488d7757cb5430418e8db6b3cfa67210-4404613179025.png)

#### Análise

Visualizar dados de instalações, cliques, impressões e taxas de conversão de vários aplicativos existentes, todos veiculando anúncios para o mesmo aplicativo promovido, permite que você realize uma análise de afinidade. Os aplicativos de origem (IDs do site) com as melhores taxas de conversão têm a maior afinidade com o aplicativo promovido e os seus usuários têm maior probabilidade de a instalar. Com base nestas informações, você pode otimizar as suas campanhas de promoção cruzada de acordo.

> 📄 **Exemplo**
>
> Você é um profissional de marketing de aplicativos de jogos para a PlayIt Gaming International. Você tem alguns aplicativos de sucesso, incluindo Bowling (com.playit.bowling) e Golfing (com.playit.golfing). Você acabou de lançar um novo aplicativo chamado Billards. Você decide realizar testes de promoção cruzada para ver quantos usuários clicam no anúncio do Billards em um dos aplicativos existentes. A campanha vai bem no Bowling, com uma taxa de conversão de 7,92%, então você decide anunciar também no Golfing.
>
> Quando você verifica o painel de controle, você vê que a taxa de conversão para o Golfing, 18,22%, é muito mais elevada do que a taxa para o Bowling, o que permite determinar que existe uma maior afinidade entre o Golfing e o aplicativo promovido, BIlliards.
>
> [![CrossPromo_taxaDeConversão](https://files.readme.io/347e3abacdff19a3c61b0a5712d3c656d33ddbf14988414ae2e13fc9c22f09b0-4404615475857.png)](https://files.readme.io/347e3abacdff19a3c61b0a5712d3c656d33ddbf14988414ae2e13fc9c22f09b0-4404615475857.png)
>
> Com base nesses insights, você pode otimizar a sua campanha da seguinte forma:
>
> * Execute uma campanha de promoção cruzada em grande escala no Golfing.
> * Comece a <Anchor target="_blank" href="/marketers/pt/docs/measure-view-through-engagements#fluxo-de-atribuição-de-exibição">atribuir impressões</Anchor> além dos cliques. Como você inicialmente configurou a sua campanha para medir apenas cliques, as instalações de usuários que vêem o anúncio sem clicar e depois instalam são contabilizadas como instalações orgânicas em vez de não orgânicas. Isto significa que você ainda não dispõe de uma imagem completa do desempenho da campanha para cada aplicativo de origem.

### Painel Personalizado

O painel de controle do aplicativo promovido é excelente para obter uma imagem dos aplicativos de origem que estão gerando o melhor tráfego. Mas e se você quiser avaliar o desempenho de um único aplicativo existente que está sendo usado para promover vários aplicativos? É aqui que um painel de controle personalizado pode fazer exatamente o que você precisa.

Um <Anchor target="_blank" href="/marketers/pt/docs/custom-dashboards">painel de controle personalizado</Anchor> permite que você visualize informações de vários aplicativos promovidos em um único local, incluindo tráfego de promoção cruzada. Além disso, um painel de controle personalizado é uma forma rápida e fácil de compartilhar dados com os usuários da conta.

> 📄 **Exemplo**
>
> Você é um profissional de marketing da eCommerce Apps, Ltd. e tem um aplicativo de grande sucesso chamado Shoes. Agora você está lançando 3 novos aplicativos: Accessories, Jackets and Coats, and Sport Shoes. Você decide realizar uma campanha de promoção cruzada no aplicativo Shoe para ver qual dos seus novos aplicativos faz o melhor trabalho de promoção.
>
> Você divide a sua base de usuários em 3 segmentos. Sempre que um usuário inicializa o aplicativo Shoe, é apresentado 1 de 3 anúncios possíveis: 1 para Accessories, 1 para Jackets and Coats e 1 para Sport Shoes.
>
> Para visualizar as métricas dos 3 aplicativos promovidos em um único local, crie um painel de controle personalizado. Na imagem seguinte, você pode ver que a Sport Shoes tem uma taxa de conversão de 20,23%, o que significa que a Shoes tem uma afinidade muito maior com a Sport Shoes do que com os outros dois aplicativos que está promovendo.
>
> ![CrossPromo_widgetPersonalizadoSobMedida](https://files.readme.io/9363a68994956bc19115f6f9babb9acb0c7d4fe75478683b2a45720987486956-4404613319953.png)

<div data-zendesk-anchors="about-crosspromotion=sobre-a-promo%C3%A7%C3%A3o-cruzada h_01HE7RXZ2CZCYENE4K40W5YSHF=sobre-a-promo%C3%A7%C3%A3o-cruzada how-does-crosspromotion-work=como-a-promo%C3%A7%C3%A3o-cruzada-funciona h_01HE7RXZ2CE5EQV42Y4B9SK4FN=como-a-promo%C3%A7%C3%A3o-cruzada-funciona attributing-crosspromotion=atribui%C3%A7%C3%A3o-de-promo%C3%A7%C3%A3o-cruzada h_01HE7RXZ2CWB2GZ8HV6447RVV1=atribui%C3%A7%C3%A3o-de-promo%C3%A7%C3%A3o-cruzada setting-up-crosspromotion=configurar-promo%C3%A7%C3%A3o-cruzada h_01HE7RXZ2C9JGFYV8K8FECFFJN=configurar-promo%C3%A7%C3%A3o-cruzada viewing-crosspromotion-data=visualizar-dados-de-promo%C3%A7%C3%A3o-cruzada h_01HE7RXZ2CE9NWMQ1PT3G98QVN=visualizar-dados-de-promo%C3%A7%C3%A3o-cruzada promoted-app-dashboard=painel-de-controle-de-aplicativos-promovidos h_01HE7RXZ2CQG9M35Y2FJNPZWDA=painel-de-controle-de-aplicativos-promovidos analysis=an%C3%A1lise h_01HE7RXZ2CVQD8H0J6EVRJM5T7=an%C3%A1lise h_01HE7RXZ2CW1P0QNA8FFXP5KBS=exemplo custom-dashboard=painel-personalizado h_01HE7RXZ2C7N3DKNPF898WM4AD=painel-personalizado h_01HE7RXZ2C51KJMP795QYS26YK=exemplo-1" />
