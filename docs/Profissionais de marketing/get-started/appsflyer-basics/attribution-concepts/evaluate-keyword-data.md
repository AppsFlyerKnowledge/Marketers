---
title: Dados de palavras-chave
metadata:
  keywords:
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-moran-davida
    - Marketers
    - Mobile Attribution
  created_at: '2023-07-25T08:19:25Z'
  edited_at: '2026-08-18T00:09:34Z'
  id: 17255366785553
  locale: pt
  section: Attribution concepts
  section_id: 6551394235409
  url: https://support.appsflyer.com/hc/pt/articles/17255366785553
---
> **Resumo:** Obtenha dados detalhados de palavras-chave que permitem ver quais termos de pesquisa são mais populares, para que você possa otimizar as conversões orgânicas.

## Dados de palavras-chave

A busca orgânica é uma fonte de tráfego valiosa para seus aplicativos. Usuários orgânicos não incurrem em custos de aquisição e geralmente estão entre os grupos mais engajados.

Com algumas alterações na página do seu aplicativo, é possível aumentar a quantidade de novas instalações orgânicas. Para otimizar as buscas orgânicas, você precisa obter dados de palavras-chave orgânicas para seu aplicativo.

### palavras-chave iOS

Se você trabalha com Apple Search Ads, pode obter dados detalhados de palavras-chave para seus usuários não orgânicos atribuídos ao Apple Search Ads. No iOS, os dados de palavras-chave orgânicas não estão disponíveis.

### Palavras-chave do Android

O Google compartilha dados de palavras-chave orgânicas (na URL de referência) para usuários que fazem o seguinte:

* Use dispositivos Android
* Use o navegador Chrome
* Visite o Google.com e faça uma pesquisa
* Instale um aplicativo a partir da página de resultados do Google
* Inicialize o aplicativo

O SDK extrai as palavras-chave quando fornecidas pelo Google no parâmetro &utm\_term do referenciador, se fizer parte do link para o Google Play. Os valores, quando possível, estão contidos nos seguintes campos de dados brutos do AppsFlyer: http\_referrer, gp\_broadcast\_referrer, keywords.

Espere que menos de 1% dos usuários orgânicos do Android sigam este funil e tenham dados de palavras-chave orgânicas.

Em outros cenários, o Google não compartilha dados de palavras-chave orgânicas. Por exemplo, os usuários que buscam no Google Play não têm dados orgânicos de palavras-chave.

> 📘 **Nota**
>
> Esta limitação é aplicada pelo Google a todos os fornecedores externos, incluindo todos os fornecedores de atribuição.

### Usando os dados da palavra-chave

Os dados de palavras-chave orgânicas são encontrados no seguinte:

* Relatórios de dados orgânicos brutos  
  No AppsFlyer, no menu lateral, selecione Relatório > Exportação de Dados Brutos para ver a divisão das palavras-chave orgânicas utilizadas.
* Relatórios avançados   
  Vá para os relatórios de Pivot, Retenção e Coorte e agrupe por palavras-chave.  
  Compare a qualidade dos usuários orgânicos com base em suas palavras-chave.
* mensagens da <Anchor target="_blank" href="/marketers/pt/docs/push-api-streaming-raw-data">Push API</Anchor>

### Testando dados de palavras-chave orgânicas

1. Use um dispositivo Android na <Anchor target="_blank" href="/marketers/pt/docs/registering-test-devices">allowlist</Anchor>.
2. Abra o navegador Chrome e vá para Google.com.
3. Use uma palavra-chave forte para pesquisar seu aplicativo.   
   Este exemplo usa "hotéis hoje à noite".  
     
   [<Image alt="organic_keywords_search.jpg" src="https://files.readme.io/b06db96b53df1502939b86cefd7217991d842f1c7e736cab6ba2c6e0de691400-32966747169425.jpg" width="426px" />](https://files.readme.io/b06db96b53df1502939b86cefd7217991d842f1c7e736cab6ba2c6e0de691400-32966747169425.jpg)
4. Clique em Instalar para ser redirecionado para a Google Play Store.
5. Instale e inicie o aplicativo.  
   [<Image alt="Hotels_Tonight_3.png" src="https://files.readme.io/c455f8229ba7879157eec6782d0eb2d94a91e1080a3c081f5452cc7e92608047-205710046.png" width="373px" />](https://files.readme.io/c455f8229ba7879157eec6782d0eb2d94a91e1080a3c081f5452cc7e92608047-205710046.png)
6. Pesquise a palavra-chave nas fontes do AppsFlyer descritas acima.

<div data-zendesk-anchors="keyword-data=dados-de-palavras-chave h_01HKA1D1TW1R20X6K05Q9GX904=dados-de-palavras-chave ios-keywords=palavras-chave-ios h_01HKA1D1TW9YXBMGERHW4EHZZN=palavras-chave-ios android-keywords=palavras-chave-do-android h_01HKA1D1TWT1VQ6NZ789BTCZJX=palavras-chave-do-android h_01HKA1D1TW7E2RM7SXC9R5SA99=nota using-the%C2%A0keyword%C2%A0data=usando-os-dados-da-palavra-chave h_01HKA1D1TWRPGTNGJKF7T1R71B=usando-os-dados-da-palavra-chave testing-organic%C2%A0keyword%C2%A0data=testando-dados-de-palavras-chave-org%C3%A2nicas h_01HKA1D1TW5W9A72V2NMPX932H=testando-dados-de-palavras-chave-org%C3%A2nicas" />
