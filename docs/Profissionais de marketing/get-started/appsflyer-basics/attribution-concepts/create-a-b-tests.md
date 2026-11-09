---
title: Guia de testes A/B da AppsFlyer
metadata:
  keywords:
    - Advertisers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-moran-davida
    - Marketers
    - Mobile Attribution
  created_at: '2019-05-07T09:17:43Z'
  edited_at: '2026-08-18T00:09:29Z'
  id: 360001523657
  locale: pt
  section: Attribution concepts
  section_id: 6551394235409
  url: https://support.appsflyer.com/hc/pt/articles/360001523657
---
> **Visão geral:** Use a AppsFlyer para fazer o teste A/B de canais de mídia, campanhas, criativos, segmentação e posicionamento de anúncios.

<Image align="center" alt="AB_TESTING.jpg" src="https://files.readme.io/259277a96d044e85cbac39de0f636bad531706e53e2ad5a21475277ea9dbd3a6-360002822018.jpg" />

<div id="what-is-ab-testing" />

## O que é teste A/B?

O teste A/B é um método usado por profissionais de marketing para testar diferentes elementos de seus anúncios e campanhas. Cada anúncio contém elementos (segmentação, visuais, textos) que podem afetar as taxas de conversão de usuários em potencial. Encontrar as variações com melhor desempenho dos elementos do seu anúncio pode ter um impacto significativo nos resultados de seus esforços de marketing mobile.

Este artigo explica **como os anunciantes podem realizar testes A/B usando a AppsFlyer para encontrar os elementos de anúncio com melhor desempenho**.

<div id="how-to-ab-test-mobile-campaigns" />

## Como fazer testes A/B em campanhas mobile

Para fazer o teste A/B de um elemento, divida seu tráfego mobile 50/50 entre duas fontes que mostram a mesma oferta. Em seguida, crie duas variações do elemento que você deseja testar. Depois que houver tráfego suficiente, você poderá comparar os resultados da sua versão existente (controle) com a nova versão (variação).

As etapas a seguir se aplicam a um teste A/B que você executa usando a AppsFlyer.

**Configuração**:

1. Selecione o elemento a ser testado.  
   Neste artigo, explicamos sobre o teste A/B de [criativos](/docs/create-a-b-tests#teste-ab-de-criativos-e-segmentação), posicionamentos de anúncios, canais de mídia e campanhas.
2. Crie duas campanhas (ou anúncios) idênticos e, em seguida, varie um único elemento dentro do anúncio. Por exemplo, cópia do botão de call to action.
   * Para testar o impacto da variação nas **taxas de conversão de instalações**, divida o tráfego igualmente entre as duas campanhas.   
     Se os dados completos de impressão estiverem disponíveis para ambas os canais, divida as instalações por impressões para calcular as taxas de conversão da instalação.
   * Para testar o impacto da variação na qualidade dos usuários, **após a instalação**, você pode enviar quantidades diferentes de tráfego para as duas campanhas.
3. Gere tráfego suficiente para cada campanha para alcançar significância estatística, o que significa pelo menos 50 instalações por campanha. Use a <Anchor target="_blank" href="https://neilpatel.com/ab-testing-calculator/">calculadora de significância do teste A/B</Anchor>.

**Análise:**

1. Use o dashboard e os dados da AppsFlyer para comparar o desempenho dos principais KPIs entre as duas campanhas.
2. Selecione a variação vencedora e use-a em suas campanhas ativas.

<div id="ab-testing-creatives-and-targeting" />

## Teste A/B de criativos e segmentação

Os criativos contêm muitos elementos com impacto variável nas taxas de conversão do usuário, incluindo textos, imagens, cores, fontes, botões etc. Parâmetros de segmentação, como país, idade ou gênero, também podem ter um grande impacto nas taxas de conversão. Parâmetros de segmentação, como país, idade ou gênero, também podem ter um grande impacto nas taxas de conversão. E para o iOS 15+, você também pode ter até 35 páginas de produtos personalizadas. **O teste A/B desses elementos pode ajudar você a descobrir quais fatores têm o maior impacto na melhoria das taxas de conversão do usuário**.

Abaixo, explicamos dois métodos de teste A/B usando:

* Um único canal de mídia
* Vários canais de mídia

| Método | Prós | Contras |
| --- | --- | --- |
| Teste A/B com uma única fonte de mídia | <ul><li>Configuração rápida</li><li>Taxa de conversão de instalação fácil de testar</li></ul> | <ul><li>Os resultados só podem se aplicar aos usuários do canal de mídia específico</li><li>Pode levar mais tempo para testar</li></ul> |
| Teste A/B em vários canais de mídia | <ul><li>Resultados rápidos</li><li>Os resultados se aplicam a usuários de todos os canais de mídia</li></ul> | <ul><li>É necessário atualizar os links de atribuição em vários lugares</li></ul> |

<div id="method-1-ab-testing-with-a-single-media-source" />

<Accordion title="Método 1: Teste A/B com uma única fonte de mídia">

**Configuração**:

1. Selecione um canal de mídia confiável com tráfego suficiente.
2. Crie duas campanhas ou <Anchor target="_blank" href="/marketers/pt/docs/smart-banners-mobile-web-to-app-for-marketers#3-banner-setup">Smart Banners</Anchor> na AppsFlyer usando um dos seguintes métodos:
   * Varie a campanha que é o nome do parâmetro "**c**" no link de atribuição.
   * Como alternativa, você pode criar dois conjuntos de anúncios ("**af\_adset**=") em uma campanha ou anúncios únicos (” **af\_ad=** “) em um conjunto de anúncios. **Observação**: Em Smart Banners, você também pode fazer o <Anchor target="_blank" href="/marketers/pt/docs/smart-banners-mobile-web-to-app-for-marketers#ab-testing-banner-performance">teste A/B colocando parâmetros diferentes para cada banner</Anchor> no mesmo grupo de banners.
   * Para iOS 15+, você também pode testar a eficácia de diferentes páginas de produtos personalizados, enviando diferentes URLs do OneLink para diferentes páginas de produtos. <Anchor target="_blank" href="/marketers/pt/docs/redirect-users-to-custom-app-store-product-pages">Saiba mais</Anchor>
3. Use o mesmo criativo nas duas campanhas, exceto na variação testada.
4. Envie a mesma quantidade de tráfego para as duas campanhas.

**Análise:**

* Compare os KPIs (por exemplo, taxa de conversão de instalação, ROI, ARPU, taxa de usuários fiéis) das campanhas na página Visão geral do dashboard.

</Accordion>

<div id="method-2-ab-testing-across-multiple-media-sources" />

<Accordion title="Método 2: Teste A/B em vários canais de mídia">

**Configuração**:

1. Selecione um parâmetro de assinante para manter o valor da variação.  
   Por exemplo, para testar 2 variações de texto de CTA, você pode usar af\_sub1="instale agora” ou af\_sub1="instale, por favor”. Saiba mais sobre os parâmetros do assinante e um exemplo de teste criativo <Anchor target="_blank" href="/marketers/pt/docs/about-link-structure-and-parameters#what-are-subscriber-parameters-good-for">aqui.</Anchor>
2. Adicione o parâmetro do assinante com o valor correspondente a cada link de atribuição ativo.
3. É recomendável usar os mesmos criativos em todas as campanhas, exceto na variação testada.

**Análise:**

1. Baixe os relatórios de dados brutos de instalação ou eventos in-app. Use a coluna de parâmetros de assinante selecionada para filtrar e classificar seus dados.
2. Compare o desempenho dos criativos com qualquer um dos dois valores armazenados.

</Accordion>

<div id="ab-testing-ad-placement-on-mobile-web" />

## Teste A/B de posicionamento de anúncios na web mobile

<Image align="center" alt="ad_placement.png" src="https://files.readme.io/6d64eed1a7a16c6daae9c93429d5bd46625dc4de12728e42b49a91ae69765f24-360002747977.png" />

A localização dos banners de seus aplicativos em sites móveis pode afetar significativamente as taxas de conversão do usuário. Na maioria dos casos, os anunciantes usam seu próprio web mobile para converter visitantes em usuários mobile.

Com o <Anchor target="_blank" href="/marketers/pt/docs/smart-banners-mobile-web-to-app-for-marketers">recurso Smart Banners da AppsFlyer</Anchor>, você pode configurar banners do web mobile de forma rápida e fácil. Além disso, o recurso também permite que você execute facilmente testes A/B para **determinar o melhor posicionamento para converter visitantes do site em usuários mobile**.

**Configuração**:

1. Implemente <Anchor target="_blank" href="/marketers/pt/docs/smart-banners-mobile-web-to-app-for-marketers">Smart Banners</Anchor> em seu web mobile.
2. Para cada novo visitante, determine se deseja mostrar o banner na parte superior ou inferior da página. Certifique-se de dividir o tráfego 50/50 entre os dois.  
   Dica do desenvolvedor - Um método simples para dividir o tráfego do seu site é usar um contador de visitantes e verificar se o valor do contador é ímpar (opção A) ou par (opção B) para cada novo visitante.
3. Defina a localização do banner e o link de atribuição de acordo com a localização determinada usando a <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_smart_banner_v2#showbanner">API ShowBanner do SDK</Anchor> dos Smart Banners.  
   Exemplo:

   ```javascript
   showBanner({ bannerContainerQuery: "#document.body", additionalParams:{ af_sub5: "top"}})
   ```

**Análise:**

1. Baixe os relatórios de dados brutos para instalação ou eventos in-app. Use a coluna de parâmetros de assinante selecionada (por exemplo: af\_sub5) para filtrar e classificar seus dados.
2. Compare o desempenho dos dois canais de anúncio, ou seja, qual canal teve mais instalações ou eventos pós-instalação.

<div id="ab-testing-media-sources" />

## Teste A/B de canais de mídia

Ajudar os anunciantes a identificar os canais de mídia com melhor (e pior) desempenho para seus aplicativos é o objetivo da AppsFlyer. No entanto, **se os anunciantes não compararem as fontes de mídia corretamente, correm o risco de chegar a conclusões erradas sobre a qualidade do tráfego**.

**Configuração:**

1. Crie um único anúncio criativo para AMBOS os canais de mídia.
2. Defina um anúncio para cada canal de mídia, com exatamente os mesmos parâmetros de segmentação de público.
3. Você pode enviar quantidades diferentes de tráfego para os dois canais de mídia.

**Análise:**

1. Se os anúncios que estão sendo testados forem os únicos veiculados em ambas as fontes de mídia, use o painel e os dados da AppsFlyer para comparar facilmente seu KPI principal entre os dois canais.  
     
   Caso contrário:
2. Acesse o Relatório de retenção, <Anchor target="_blank" href="/marketers/pt/docs/cohort-and-retention-dashboard">Relatório de Coorte</Anchor>, <Anchor target="_blank" href="/marketers/pt/docs/master-api-user-acquisition-metrics-via-api">Master API</Anchor> ou <Anchor target="_blank" href="/marketers/pt/docs/pivot-table-user-metrics">Tabela Pivot</Anchor>.
3. Agrupar por Canal de mídia -> Campanha -> Conjunto de anúncios -> Anúncio.
4. Compare os KPIs para identificar o canal de mídia com melhor desempenho.

<div id="example" />

> 📄 **Exemplo**
>
> <Image align="center" alt="" src="https://files.readme.io/bf907e0e67d24764a68579ba6fc42d0d49befbc7ffc7645b91ae1aa8f8b97c12-360002829938.png" />
>
> * 1 e 2 são anúncios diferentes no mesmo canal de mídia de mídia. Compare um único KPI para eles, por exemplo, a taxa de retenção no dia 4, para teste A/B de criativos, segmentação ou posicionamento do anúncio.
> * 2 e 3 são anúncios em diferentes canais de mídia. Se os criativos e a segmentação dos anúncios forem idênticos, comparar um único KPI fazer o teste A/B do canal de mídia.

<div id="using-audiences-split-for-easy-ab-testing-of-media-sources" />

### Usando a divisão de públicos para facilitar o teste A/B de canais de mídia

Se você definir os mesmos parâmetros de segmentação para cada canal de mídia, o teste incluirá as habilidades de segmentação das redes. Ao fazer teste A/B, é melhor testar uma única variação a cada vez. Como resultado, é aconselhável eliminar as diferenças nas habilidades de segmentação ao fazer o teste A/B de outros fatores no desempenho das redes.

Para conseguir isso, recomendamos dividir um público aleatoriamente e segmentar os dois públicos com o mesmo criativo, em cada rede testada. A AppsFlyer oferece um **método fácil para definir, dividir e distribuir automaticamente** públicos entre diferentes canais de mídia. Leia sobre isso <Anchor target="_blank" href="/marketers/pt/docs/audiences-guide#divisão-de-audiências-e-testes-de-incrementalidade">aqui</Anchor>.

<div data-zendesk-anchors="what-is-ab-testing=o-que-%C3%A9-teste-ab h_01HN5CNKKBHV52ENXJXCBV2CES=o-que-%C3%A9-teste-ab how-to-ab-test-mobile-campaigns=como-fazer-testes-ab-em-campanhas-mobile h_01HN5CNKKC02NKW4330QB6E01T=como-fazer-testes-ab-em-campanhas-mobile ab-testing-creatives-and-targeting=teste-ab-de-criativos-e-segmenta%C3%A7%C3%A3o h_01HN5CNKKCJPZSEEF1RAHC0HXD=teste-ab-de-criativos-e-segmenta%C3%A7%C3%A3o h_01HN5CNKKCMVE9YH379RP1S19W=method-1-ab-testing-with-a-single-media-source h_01HN5CNKKC53RTV61K08T9AVRA=method-2-ab-testing-across-multiple-media-sources ab-testing-ad-placement-on-mobile-web=teste-ab-de-posicionamento-de-an%C3%BAncios-na-web-mobile h_01HN5CNKKCVPSSZZTJ8QGJHY1B=teste-ab-de-posicionamento-de-an%C3%BAncios-na-web-mobile ab-testing-media-sources=teste-ab-de-canais-de-m%C3%ADdia h_01HN5CNKKC03ZAFCQZ0KJ0RHCE=teste-ab-de-canais-de-m%C3%ADdia h_01HN5CNKKC4M6YMPHTQCFHFDMD=exemplo using-audiences-split-for-easy-ab-testing-of-media-sources=usando-a-divis%C3%A3o-de-p%C3%BAblicos-para-facilitar-o-teste-ab-de-canais-de-m%C3%ADdia h_01HN5CNKKC551X3HQFNKHW1JBY=usando-a-divis%C3%A3o-de-p%C3%BAblicos-para-facilitar-o-teste-ab-de-canais-de-m%C3%ADdia" />
