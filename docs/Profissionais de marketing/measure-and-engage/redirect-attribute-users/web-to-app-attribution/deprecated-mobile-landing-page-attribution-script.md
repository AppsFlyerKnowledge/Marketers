---
title: '[Descontinuado] Script de atribuição de página inicial em mobile'
deprecated: true
metadata:
  keywords:
    - Landing Page
    - Facebook
    - Adwords
    - Advertisers
    - Agencies
    - GCLID
    - Developers
    - Marketers
    - Smart Banners and Scripts
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-asaf-mashiah
    - Marketers
    - Agencies
    - Smart Banners and Scripts
  created_at: '2020-12-16T17:28:55Z'
  edited_at: '2026-08-19T00:34:31Z'
  id: 360016643258
  locale: pt
  section: Web-to-app attribution
  section_id: 6551240476177
  url: https://support.appsflyer.com/hc/pt/articles/360016643258
---
> **Visão geral:** Esse script foi descontinuado em 17 de dezembro de 2020 e foi substituído pelo <Anchor target="_blank" href="/marketers/pt/docs/onelink-smart-script-overview">Smart Script do OneLink</Anchor>. Esta versão continua funcionando, mas não será atualizada ou alterada. O script gera URLs que são incorporados atrás de um botão em seu site para dispositivos móveis e redireciona os visitantes para baixar seu aplicativo. Os URLs também são compatíveis com atribuição de instalação e deep linking.

![5648_Sunset_and_deprecation-01.png](https://files.readme.io/f2a154145e26577b698d00c4c3719be3eea7298576e6883bd47e6fb42897c71a-360015062398.png)

**<Anchor target="_blank" href="/marketers/pt/docs/onelink-smart-script-overview">Migrate to OneLink Smart Script</Anchor>**

As páginas iniciais são uma técnica muito comum entre os profissionais de marketing digital. Elas permitem que os profissionais de marketing capturem os detalhes de seus leads para remarketing, mesmo que esses usuários não convertam no início.

No entanto, para a aquisição de usuários de mobile, a estratégia da página inicial tem vantagens e desvantagens.

#### As vantagens:

* Os leads, que eventualmente instalam, devem estar mais engajados com o aplicativo.
* Os serviços mais complicados (por exemplo, serviços financeiros) exigem mais explicações para converter seus leads, o que é possível nas páginas iniciais.

#### As desvantagens:

* O funil mais longo reduz o número final de leads convertidos.
* É mais tecnicamente desafiador atribuir.

## Os desafios da atribuição mobile nas páginas iniciais

* **Diferentes canais de mídia requerem métodos diferentes** para concluir o cenário da página inicial com os dados de atribuição corretos.
* **O modelo de atribuição de último clique pode causar a perda da atribuição correta**, se a página inicial tiver seus próprios links de atribuição.
* **Os visitantes diretos do site são registrados como orgânicos**, a menos que a página inicial tenha seus próprios links de atribuição.
* **Os visitantes do desktop são registrados como orgânicos**, a menos que a página inicial tenha um método de registrar suas conversões em usuários móveis.

## A solução

Para resolver os problemas de atribuição da página inicial mencionados, você precisa implementar um fluxo javascript em sua página inicial. Oferecemos um exemplo de implementação de script que você pode usar. Certifique-se de ajustar o script para atender às suas necessidades.

Em alguns casos, você também precisa fazer alguns ajustes em suas campanhas.

Os cenários abaixo abrangem os requisitos para todos os casos de canal de mídia possíveis.

## Cenários de páginas iniciais

Siga as instruções de implementação abaixo **para todos os canais de mídia** enviando leads para suas página iniciais.

<div id="facebook-ads-crossplatform-attribution" />

<Accordion title="Meta ads: atribuição multiplataforma">

#### Descrição:

O Meta Ads é um SRN, que não usa links de atribuição externa.

Após a primeira inicialização do aplicativo, a AppsFlyer consulta os anúncios do Meta se o usuário já engajou anteriormente (nos últimos 28 dias) com um anúncio no aplicativo do Facebook. Se sim, o Meta ads faz a auto-atribuição.

O Meta ads também faz atribuição multiplataforma, o que significa que o usuário pode interagir com qualquer tipo de campanha, mobile ou não, em qualquer plataforma, para ser autoatribuído pelo Meta ads.

#### Conclusão:

Um lead com o ID do dispositivo disponível, proveniente do aplicativo do Facebook para uma página inicial, é atribuído corretamente ao Meta ads. Isso acontece independentemente do novo clique registrado na página inicial.  
No entanto, quando os usuários optam por não compartilhar o ID do dispositivo, como esperado com os usuários do iOS 14 em 2021, a atribuição multiplataforma do Meta ads pode não funcionar mais.

**Quando o compartilhamento de ID do dispositivo se tornar opcional, use o comando [Outro método de SRNs](/docs/deprecated-mobile-landing-page-attribution-script#other-srns-add-parameter) para Meta ads.**

* Os novos usuários que compartilharem o ID do dispositivo serão atribuídos corretamente ao Meta ads.
* Novos usuários que não compartilham seu ID de dispositivo seriam atribuídos a "Facebook\_LP".

#### Instruções:

1. Na sua conta do Meta ads, crie uma **campanha «Tráfego» ou «Conversões» com a atribuição mobile ativada**, enviando leads para a sua página inicial.
2. Botão de download do Android da página inicial - link direto para o Google Play.
3. Botão de download do iOS da páginal inicial - link direto para o iTunes (OU link de atribuição **sem o ID do dispositivo**).

#### O que o script faz

O script da página inicial não faz alterações. O script foi projetado para detectar um usuário vindo do aplicativo do Facebook. Se sim, ele não faz nada. Ele deixa os links diretos da página inicial para as lojas de aplicativos como estão Ele deixa os links diretos da página inicial para as lojas de aplicativos como estão Isso evita que outro clique seja registrado, o que pode afetar o CTR.

No script, procure um método chamado***isFacebook()*** para saber mais sobre o que o script faz quando um usuário vem do aplicativo do Facebook.

</Accordion>

<div id="google-ads-gclid-offline-conversion-upload" />

<Accordion title="Google Ads: GCLID + upload de conversão off-line">

#### Descrição:

O processo usual para a atribuição de instalações de campanhas do Google Ads requer que os leads que clicam sejam redirecionados para o URL da página da loja do aplicativo.

Portanto, ao redirecionar leads do Google Ads para uma página inicial, use um mediador para se conectar entre a instalação mobile e o clique original na campanha do Google Ads não mobile.

#### Conclusão:

A solução para o Google Ads tem 2 partes.

A primeira parte se ocupa de **atribuir na AppsFlyer** os usuários de mobile que acessam a página inicial do Google e instalam o aplicativo a partir dela. Isso requer a marcação dos URLs de clique do Google, identificando-os na página inicial e criando um OneLink dinâmico com dados do URL.

A segunda parte se ocupa de **notificar o Google Ads** sobre essas instalações para dispositivos mobile, usando o método de upload de conversões offline do Google.

> 📘 **Observação**
>
> Esta solução GCLID não é oficialmente apoiada ou recomendada pelo Google.
> Caso o Google descontinue o parâmetro GCLID, alteraremos o script para que aceite as mudanças.
> Recomendamos seguir este artigo, clicando no botão ***Seguir*** no topo do artigo, para ser informado quando houver uma atualização do artigo ou script.

#### Instruções:

Parte 1 - Atribuindo para o Google Ads na AppsFlyer

No painel do Google - **Ative marcação automática** (<Anchor target="_blank" href="https://support.google.com/analytics/answer/1033981?hl=en">Veja como</Anchor>).

Com a marcação automática ativada, **o URL para a página inicial contém o *GCLID* parâmetro**.

Exemplo de URL: `http://www.yoursite.com/yourlandingpage?gclid={USER_GCLID}`

No carregamento da página inicial -

1. Ative a função Javascript ***generateUrl***
2. A funcao (veja abaixo) procura o parâmetro ***GCLID*** e cria um URL do OneLink longo contendo seu valor sob o parâmetro af\_sub1 (você pode usar qualquer um dos <Anchor target="_blank" href="/marketers/pt/docs/about-link-structure-and-parameters#what-are-subscriber-parameters-good-for">parâmetros de assinante</Anchor> af\_sub1 - af\_sub5).
3. O botão de download da página inicial usa o URL do OneLink gerado.  
   Exemplo de URL do OneLink: `https://yourapp.onelink.me/abcd?pid=google_lp&c={CAMPAIGN_NAME}&af_sub1={USER_PARSED_GCLID}`
4. Novos usuários mobile são atribuídos ao canal de mídia **google\_lp** e à campanha CAMPAIGN\_NAME (opcional).
5. Nenhum postback é enviado para o canal de mídia

Neste ponto, as instalações são reportadas na AppsFlyer sob o canal de mídia ***google\_lp*** com o GCLID, mas não no Google Ads.

Parte 2 - Fazendo upload de instalações para o Google como conversões offline

**Essa etapa só será necessária se você quiser que as conversões sejam registradas na plataforma do Google Ads.**

Para usuários atribuídos a google\_lp, os dados brutos da AppsFlyer agora exibem o valor do GCLID na coluna **af\_sub1**. O GCLID é necessário para fazer o upload de conversões off-line para o Google Ads, você pode encontrar mais informações sobre o processo <Anchor target="_blank" href="https://support.google.com/adwords/answer/7014069">aqui</Anchor>).

As conversões podem ser carregadas manualmente ou por meio de uma API do Adwords (mais informações sobre a API <Anchor target="_blank" href="https://developers.google.com/adwords/api/docs/guides/conversion-tracking#importing_conversions">aqui</Anchor>).

Você pode exportar os CSVs com essas informações da sua conta da AppsFlyer ou obter esses dados da API Push em tempo real para cada instalação.

> 👍 **Dica**
>
> Você também pode ver as palavras-chave que seus usuários pesquisaram nos dados brutos da AppsFlyer de maneira semelhante à obtenção do GCLID:
>
> 1. Para registro de palavras-chave, você deve incluir a palavra-chave <Anchor target="_blank" href="https://support.google.com/google-ads/answer/2375447">Parâmetro ValueTrack</Anchor> no URL final do Google Ads para a página inicial
>    Exemplo de URL: `http://www.yoursite.com/yourlandingpage?gclid={USER_GCLID}&keyword={USER_KEYWORD}`
> 2. A função Javascript (veja abaixo) procura o parâmetro ***keyword***
> 3. O valor é adicionado ao URL do OneLink gerado em af\_keywords
>    Exemplo de URL do OneLink: `https://yourapp.onelink.me/abcd?pid=google_lp&c={CAMPAIGN_NAME}&af_sub1={USER_PARSED_GCLID}&af_keywords={USER_PARSED_KEYWORD}`
>
> A função JS abaixo já contém o código para analisar o parâmetro keyword também.

#### O que o script faz

O Google Ads traz um parâmetro gclid. O script procura esse parâmetro no URL da página inicial. Se ele o vir, ele cria o OneLink de forma que reflita que o usuário vem do Google Ads. O script então coloca o OneLink como o link atrás dos botões de download na página inicial.

No script, procure por**gclidValue** para saber como o script detecta usuários provenientes do Google Ads e cria o OneLink de acordo.

</Accordion>

<div id="other-srns-add-parameter" />

<Accordion title="Outros SRNs: adicionar parâmetro">

#### Descrição:

Outro <Anchor target="_blank" href="/marketers/pt/docs/self-reporting-networks-srns#srns-integradas-à-appsflyer">SRNs</Anchor>, por exemplo, Snapchat ou Twitter, não são multiplataforma como o Meta Ads e exigem um pouco de trabalho para que seus usuários mobile sejam atribuídos a eles.

Suas campanhas com outros SRNs levam seus usuários à página inicial, e você é cobrado de acordo com os cliques, sem nenhuma relação com qualquer usuário mobile derivado.

#### Conclusão:

Ao definir o URL da página inicial de uma campanha em SRNs (além do Meta Ads e do Google Ads), adicione um parâmetro de ID do parceiro ao URL, que indica o SRN original.  
A página inicial lança um javaScript (veja abaixo) que analisa esse parâmetro e cria um URL do OneLink, que tem o valor de ID do parceiro. Quando os usuários de mobile clicam no OneLink e instalam, eles são atribuídos ao canal de mídia indicado.

#### Instruções:

Na sua conta SRN -

1. Criar uma campanha não mobile
2. Ao definir o URL da página inicial, adicione um parâmetro de ID de parceiro + página inicial ao URL (que não é um link de atribuição AF). O formato é "***&af\_pid=srn\_lp***". (veja o exemplo abaixo)

No carregamento da página inicial -

1. Ative a função Javascript ***generateUrl***
2. A função procura o parâmetro ***af\_pid*** e cria um URL do OneLink contendo seu valor sob o parâmetro ***pid***
3. O botão de download da página inicial usa o URL do OneLink gerado
4. Novos usuários de mobile são atribuídos ao canal de mídia personalizado "ID do parceiro + página inicial"
5. Nenhum postback é enviado para o canal de mídia

Se você especificar o nome real do SRN, por exemplo, twitter\_int, um postback poderá ser enviado para esse SRN. Isso pode resultar em cobranças duplas. Veja a nota abaixo para nomes alternativos.

O próprio script contém lógica para evitar que você use esses nomes. Procure `var SRNs` no script. Você deve ver uma lista de nomes SRN e uma condição que verifica se `pidValue` é qualquer um desses nomes. Remova essa lógica depois de terminar de testar o script.

> 📘 **Observação**
>
> Se você estiver enviando usuários para sua página inicial, recomendamos que inclua o seguinte parâmetro no URL da sua página inicial:
>
> * Para o Twitter: use "***&af\_pid=twitter\_lp***"
> * Para Snapchat: use "***&af\_pid=snapchat\_lp***"
> * Para Doubleclick: use "***&af\_pid=doubleclick\_lp***"
> * Para post do Meta ads (não pago): use "***&af\_pid=fbpost\_lp***"
> * Para Oath (anteriormente Yahoo Gemini): use "***&af\_pid=oath\_lp***"

#### O que o script faz

O script vê o parâmetro af\_pid na URL da página inicial e conclui que o usuário vem de um SRN ou de alguma outra rede personalizada. O script cria um OneLink de acordo e o define como o link por trás do botão de download na página inicial.

Para saber mais sobre o que o script faz, procure **pidValor** no script.

</Accordion>

<div id="attribution-links-redirect-with-af_r" />

<Accordion title="Links de atribuição: redirecionar com af_r">

#### Descrição:

Os links de atribuição são usados para qualquer canal de mídia, que não seja uma SRN. Isso inclui milhares de parceiros integrados e qualquer mídia própria que você deseja atribuir.

Felizmente, a solução para atribuição de página inicial ao usar os links de atribuição da AppsFlyer é simples (e semelhante à solução para Meta ads).

#### Conclusão:

O link de atribuição redireciona o lead para uma página inicial e, com isso, também cuida da atribuição correta (se uma instalação mobile seguir).

Tudo o que resta a fazer é NÃO impedir a atribuição correta com outro último clique.

#### Instruções:

1. <Anchor target="_blank" href="/marketers/pt/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#crie-um-link-do-onelink">Criar o link de atribuição</Anchor> para o canal de mídia
2. Adicione o <Anchor target="_blank" href="/marketers/pt/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#redirection">parâmetro da página inicial</Anchor> que leva para a sua página inicial para o link de atribuição
3. Adicione `&af_redirect=true` ao valor da página inicial em **quaisquer parâmetros de redirecionamento** (ou seja, af\_r, af\_ios\_url e af\_android\_url) no link de atribuição.  
   Exemplo: `https://yourapp.onelink.me/abcd?pid=email&c={CAMPAIGN_NAME}&af_r=http://www.yoursite.com/yourlandingpage?af_redirect=true`
4. **Opcional**- adicione o ID do dispositivo (GAID / IDFA) ao link de atribuição para permitir a atribuição por correspondência de ID em vez de modelagem probabilística
5. Botão de download do Android da página inicial - link direto para o Google Play
6. Botão de download do iOS da página inicial - link direto para o iTunes  

   > 📘 **Observação**
   >
   > O script e a página de exemplo HTML fornecem a opção de definir um botão de download que serve para Android e iOS. Leia os comentários no script para saber como implementá-lo.


#### O que o script faz

O script procura o parâmetro **af\_redirect** no URL da página inicial. Se ele o vir, ele não fará alterações nos botões de download na página inicial. Isso ocorre porque o parâmetro af\_redirect indica que o usuário acessa a página inicial após um clique. Portanto, não há necessidade de links de atribuição adicionais.

Para saber mais sobre o que o script faz para lidar com casos em que os usuários acessam a página inicial depois de clicar em um link de atribuição, veja o método **isAFLink()** no script.

</Accordion>

<div id="links-with-utm-parameters-dynamic-onelink" />

<Accordion title="Links com parâmetros utm: OneLink dinâmico">

#### Descrição

Você pode ter fontes de tráfego, que redirecionam os usuários para sua página inicial usando links com parâmetros UTM.

#### Conclusão:

Se o URL original NÃO for um link de atribuição da AppsFlyer, o script procura os parâmetros ***utm\_source*** e ***utm\_campaign*** no link. Se existirem, o script prepara um URL do OneLink, que os tem como nome do canal de mídia (pid) e nome da campanha (c), respectivamente.

Observe que, com os links de atribuição da AppsFlyer, que também contêm parâmetros UTM, os parâmetros da AppsFlyer estão sendo usados, em vez dos parâmetros UTM.

#### Instruções:

Sobre o canal de mídia -

1. Certifique-se de que ***utm\_source*** existe no link.
2. O parâmetro ***utm\_campaign*** é opcional, mas altamente recomendado.

No carregamento da página inicial -

1. Ative a função Javascript ***generateUrl***
2. A função procura os parâmetros ***utm\_source*** e ***utm\_campaign*** e cria um URL do OneLink contendo seus valores
3. O botão de download da página inicial usa o URL do OneLink gerado
4. Novos usuários móveis são atribuídos ao valor de***utm\_source*** como canal de mídia
5. Nenhum postback é enviado para o canal de mídia.

#### O que o script faz

O script procura parâmetros UTM no URL da página inicial. Se ele encontrar algum parâmetros, ele o converte em parâmetros do OneLink. Dessa forma, as informações da campanha são transferidas para a atribuição final.

</Accordion>

<div id="mobile-organic-visitors-onelink-with-pidwebsite" />

<Accordion title="Visitantes orgânicos em mobile: OneLink com pid=website">

#### Descrição

Os visitantes orgânicos em mobile são, por definição, leads diretos da web móvel de fontes desconhecidas. Eles raramente visitam páginas iniciais dedicadas, mas podem ser a grande maioria das instalações em mobile provenientes do site do anunciante.

#### Conclusão:

Se você tiver uma quantidade significativa de tráfego orgânico em mobile do seu site, é altamente recomendável registrar os dados de atribuição do seu próprio tráfego.

#### Instruções:

Para atribuir visitantes orgânicos em mobile, o site deve ter botões de ***download*** ou ***instalação***, com um link de atribuição do OneLink atrás deles. O OneLink permite diagnosticar o tipo de dispositivo e redirecionar o lead para a loja de aplicativos correta de acordo com ele.

Para saber como definir e criar URLs do OneLink, clique <Anchor target="_blank" href="/marketers/pt/docs/create-a-onelink-template">aqui</Anchor>.

> 👍 **Dica**
>
> Adicione "&pid=website" ao seu link de atribuição para atribuir todos esses visitantes ao seu site.
> Em cada página do seu site, que possui um botão de download/instalação com um link de atribuição, adicione "&c=`{PAGE NAME}`". Isso pode ajudar você a encontrar as páginas de maior e menor conversão em seu site.

#### O que o script faz

Esgotando todas as outras opções, o script determina que o usuário é um usuário orgânico que não vem de nenhuma campanha. O script cria um OneLink que reflete isso e o coloca como o link por trás do botão de download na página inicial.

</Accordion>

<div id="desktop-visitors-telephoneemail-form" />

<Accordion title="Visitantes em desktop: formulário de telefone/e-mail">

#### Descrição

Todas as opções abordadas acima pressupõem que os usuários usem dispositivos móveis ao interagir com a campanha e a página inicial.

Mas e os usuários de desktop?

Os usuários de desktop podem chegar à sua página inicial/site e, posteriormente, visitar "independentemente" a loja de aplicativos com seus dispositivos móveis e instalar o aplicativo mobile. Sem o engajamento anterior com os dispositivos móveis, é impossível atribuir esses usuários e, portanto, eles são rotulados como "Orgânicos".

#### Conclusão:

Uma ótima solução para esse problema de atribuição é usar um **Formulário de texto para download em sua página inicial**, somente para usuários de desktop. Isso deve ser seguido pelo envio ao dispositivo mobile de um SMS/e-mail com URL do OneLink.

#### Instruções:

1. Identificar que um visitante é um usuário de desktop
2. Quando seu usuário digitar o número de telefone, envie a ele uma mensagem de texto com o link para seu aplicativo, com um URL curto do OneLink. Você também pode solicitar o endereço de e-mail para enviar mensagens de download do aplicativo por e-mail.
3. O uso do OneLink é crucial aqui, pois a plataforma do dispositivo mobile não é conhecida ao enviar a mensagem aos usuários. As funcionalidades de diagnóstico e redirecionamento do OneLink cuidam disso para você.
4. Adicione "&pid=desktop\_website" ao URL do OneLink para identificar essa fonte.
5. Adicione "&c=`{PAGE NAME}`" para ajudar a encontrar as páginas de maior e menor conversão em seu site para usuários de desktop.

#### O que o script faz

O script detecta o dispositivo ou a plataforma em que o usuário está. Se for desktop, o script retornará um link para um URL de formulário da web e o colocará atrás dos botões de download. Quando o usuário clica em download, ele é enviado para um formulário da web onde preenche os dados para receber um SMS ou um e-mail com um link para baixar o aplicativo.

Cabe a você criar o formulário da web e fornecer o URL para ele no script. Para saber mais, procure**isMobileDevice()** no script.

</Accordion>

## Javascript da página inicial

Abaixo, você pode encontrar a implementação de código do javascript que executa todo o escopo de atribuição de canais de mídia e campanhas em cenários de página inicial. **Se você quiser ter dados adicionais, como conjuntos de anúncios e IDs de anúncios, faça os ajustes necessários no script**.

Para sua conveniência, você também pode baixar o exemplo de página inicial em anexo.

Abaixo do código, você pode encontrar as instruções para adaptá-lo às necessidades da sua página inicial.

<div id="the-script" />

<Accordion title="O script">

Considere o seguinte antes de implementar o script:

* O script é oferecido apenas como exemplo. Ele abrange a página inicial comum ao fluxo de atribuição. Adapte o script para atender às suas necessidades.
* O script procura parâmetros específicos no URL da página inicial, como canal de mídia, campanha, palavras-chave etc. O script procura parâmetros específicos no URL da página inicial, como canal de mídia, campanha, palavras-chave etc. Se você quiser adicionar outros parâmetros, como ID do site e conjuntos de anúncios, precisará modificar o script de acordo. O script procura parâmetros específicos no URL da página inicial, como canal de mídia, campanha, palavras-chave etc. Se você quiser adicionar outros parâmetros, como ID do site e conjuntos de anúncios, precisará modificar o script de acordo.

```javascript
// Retorna o valor de um parâmetro existente na URL da página ou ' ' se não existir.
function getParameterFromURL(name, url) {
  if (!url) url = window.location.href;
  name = name.replace(/[\[\]]/g, '\\$&');
  var regex = new RegExp('[?&]' + name + '(=([^&#]*)|&|#|$)'),
    results = regex.exec(url);
  if (!results) return null;
  if (!results[2]) return '';
  return decodeURIComponent(results[2].replace(/\+/g, ' '));
}

function isMobileDevice() {
  return (typeof window.orientation !== "undefined") || (navigator.userAgent.indexOf('IEMobile') !== -1);
}

function getMobileOperatingSystem() {
  var userAgent = navigator.userAgent || navigator.vendor || window.opera;
  if (userAgent) {
    if (/android/i.test(userAgent)) {
      return "Android";
    }

    // Detecção de iOS de: http://stackoverflow.com/a/9039885/177710
    if (/iPad|iPhone|iPod/.test(userAgent) && !window.MSStream) {
      return "iOS";
    }
  }
  return "unknown";
}

function isAFLink() {
  return getParameterFromURL('af_redirect');
}

// Observação: quando o compartilhamento do Device ID se tornar opcional, pare de chamar este método (ou sempre retorne false)
function isFacebook() {
  if (document.referrer && document.referrer != "") {
    return document.referrer.toLowerCase().includes('facebook');
  } else {
    return false;
  }
}

// generateUrl retorna a URL a ser usada por trás dos botões de "download" do iOS e do Android em uma landing page, com base na fonte do visitante da página.
// Por padrão, esses botões devem direcionar para as páginas dos aplicativos no iTunes e no Google Play.
// Se esses links devem ser mantidos sem alteração, generateUrl retorna ' '.
// Caso contrário, generateUrl retorna a URL a ser usada em AMBOS os botões (um único botão de download do aplicativo também pode ser usado neste caso).
// Parâmetros: isDebug - se for true, alertas serão emitidos para cada caso; caso contrário, não.  	 
function generateUrl(isDebug) {
  var oneLinkURL = 'https://yourapp.onelink.me/abcd';   // **** Substitua pela sua URL básica do OneLink ****
  var webFormURL = 'https://yoursite.com/webform.html'; // **** Substitua pela URL do seu formulário web para obter o e-mail ou SMS do usuário ****
  var finalURL = "";
  var partnerIDParam = '?pid=';

  var campaignValue;
  if (getParameterFromURL('c')) {
    campaignValue = getParameterFromURL('c');
  } else if (getParameterFromURL('utm_campaign')) {
    campaignValue = getParameterFromURL('utm_campaign');
  } else if (document.getElementsByTagName('title')[0]) {
    campaignValue = document.getElementsByTagName('title')[0].innerText;
  } else {
    campaignValue = 'unknown';
  }
  var campaignParam = '&c=';
  var gclidParam = '&af_sub1=';
  var gclidValue = getParameterFromURL('gclid');
  var kwParam = '&af_keywords=';
  var pidValue;
  var kwValue = getParameterFromURL('keyword');

  if (getParameterFromURL('af_pid')) {
    pidValue = getParameterFromURL('af_pid');
  } else if (getParameterFromURL('utm_source')) {
    pidValue = getParameterFromURL('utm_source');
  }

  // Impedir o uso de nomes reais de SRN. Remova esta parte depois de terminar de testar o script.
    var SRNs = [
    'twitter_int',
    'facebook_int',
    'snapchat_int',
    'doubleclick_int',
    'yahoogemini_int',
    'yahoojapan_int',
  ];

  if (SRNs.includes(pidValue)) {
  	alert("NÃO USE NOMES DE SRNS em af_pid ou utm_source - use os nomes listados na seção Other SRNs: Add Parameter no artigo da landing page\nhttps://support.appsflyer.com/hc/en-us/articles/360000677217#other-srns-add-parameter");
    return;
  }

  // Usuário de desktop
  if (!isMobileDevice()) {
    return webFormURL;
  }

  // O usuário foi redirecionado usando o parâmetro af_r em um link de atribuição da AppsFlyer
  if (isAFLink()) {
    if (isDebug) {
      alert("Este usuário veio da AppsFlyer por redirecionamento e está pronto para ser atribuído. \nMantenha os links diretos da loja de aplicativos.");
    }
    return; // neste caso, os links originais da loja nos botões de instalação permanecem os mesmos

    /*
    Se você quiser um botão de instalação na landing page que sirva tanto para iOS quanto para Android, descomente o código abaixo
    O código identifica o sistema operacional e retorna o link direto relevante para o Google Play ou iTunes

    if (getMobileOperatingSystem() === 'Android') {
      return 'link direto para o Google Play';
    } 

    if (getMobileOperatingSystem() === 'iOS') {
      return 'link direto para o iTunes';
    }
    */
  }

  // Google Ads
  if (gclidValue) {
    partnerIDParam += 'google_lp';
    campaignParam += campaignValue;
    gclidParam += gclidValue
    if (!kwValue) {
      finalURL = oneLinkURL + partnerIDParam + campaignParam + gclidParam;
      if (isDebug) {
        alert("Este usuário veio do Google AdWords\n " + finalURL);
      }
      return finalURL;

    } else { // Google Ads com KW
      kwParam += kwValue;
      finalURL = oneLinkURL + partnerIDParam + campaignParam + gclidParam + kwParam;
      if (isDebug) {
        alert("Este usuário veio do Google AdWords - há uma palavra-chave associada ao anúncio\n " + finalURL);
      }
      return finalURL;
    }

  // Outras SRNs e networks personalizadas  
  } else if (pidValue) {
    campaignParam += campaignValue;
    partnerIDParam += pidValue;
    finalURL = oneLinkURL + partnerIDParam + campaignParam;
    if (isDebug) {
      alert("Este usuário veio da SRN ou network personalizada " + pidValue + "\n" + finalURL);
    }
    return finalURL;
  } else if (isFacebook()) {
    if (isDebug) {
      alert("Este usuário veio de um anúncio pago do Facebook - não faça nada. \nMantenha os links diretos da loja de aplicativos.");
    }
    return ' ';

  } else { // usuário mobile orgânico
    campaignParam += campaignValue;
    partnerIDParam += 'website'; //**** Substitua o valor se quiser que usuários orgânicos sejam atribuídos a outro canal de mídia que não seja 'website' ****
    finalURL = oneLinkURL + partnerIDParam + campaignParam;
    if (isDebug) {
      alert("Este usuário veio de uma fonte mobile desconhecida.\n O usuário seria atribuído ao canal de mídia 'website' e à campanha " + campaignParam + "\n" + finalURL);
    }
    return finalURL;
  }
}
```

</Accordion>

<div id="html-sample-for-landing-page" />

<Accordion title="Exemplo de HTML para página inicial">

```html Markup
<html>
<head>
  <title>Landing Page</title>
</head>
<body>
  <h1>Landing Page</h1>
  <!-- Por padrão, os botões de instalação devem ter links diretos para as lojas -->
  <div>
    <a id="andrd_link" href="https://play.google.com/store/apps/details?id=com.appsflyer.sampleapp"><img src="/images/andrd.png"alt=""></a>
  </div>
  <div>
    <a id="ios_link" href="https://itunes.apple.com/us/app/id3********"><img src="/images/ios.png" alt=""></a>
  </div>
  <!-- Se você quiser um botão para servir tanto Android quanto iOS, use o código abaixo
  <a id="store_link" href=""><img src="download.png" alt=""></a>
  -->
  <script type="text/javascript" src="/landing-page-test.js"></script>
  <script type="text/javascript">
    window.onload = function () {
      var url = generateUrl(true);

      // OneLink é gerado
      if (url) {
        document.getElementById('andrd_link').setAttribute('href', url);
        document.getElementById('ios_link').setAttribute('href', url);
      }

      // caso contrário, se o OneLink não for gerado, significa que o usuário foi redirecionado
      // e os links da loja nos botões permanecem os mesmos

      /* para a solução de um botão para Android e iOS, use o código abaixo

      document.getElementById('store_link').setAttribute('href', url);

      */

    };
  </script>
</body>

</html>
```

</Accordion>

> 👍 **Dica**
>
> Você pode implementar o trecho do javascript usando o Google Tag Manager. O Google Tag Manager facilita o controle de quando e onde o javascript da página inicial deve ser usado.

### Instruções

1. Ative o script ***generateUrl*** no carregamento da página de qualquer página em seu site, que os visitantes podem acessar diretamente, e que tem o(s) botão(ões) ***Download*** para seu(s) aplicativo(s) mobile.  

   > 🚧 **Importante!**
   >
   > **Por padrão, os botões *Download* devem direcionar para as páginas de aplicativos no iTunes e no Google Play**. Se esses links forem mantidos sem alteração (ou seja, visitante do link de atribuição de AF ou anúncios da Meta), ***generateUrl*** retorna ' '. Caso contrário, ele retorna o URL a ser usado com AMBOS os botões Download (um único botão ***Download*** também pode ser usado neste caso para cobrir ambos os aplicativos com OneLink).

2. Substitua o valor do parâmetro ***oneLinkURL*** com seu próprio URL básico do OneLink no formato exato como placeholder `https://yourapp.onelink.me/abcd`.  
   OBRIGATÓRIO atribuir visitantes de todos os SRNs (exceto anúncios pagos do Meta ads) e para visitantes orgânicos mobile.
3. Substitua o parâmetro ***webFormURL*** pelo seu próprio link de formulário da web. O formulário da web deve ser capaz de obter o e-mail ou SMS do usuário e enviar ao dispositivo mobile do usuário uma mensagem com um URL do OneLink para baixar o aplicativo.  
   OBRIGATÓRIO para atribuir visitantes em desktop.
4. Substitua o valor do parâmetro ***partnerIDParam***, se você deseja que os usuários orgânicos mobile sejam atribuídos a outro canal de mídia que não seja 'site'.
5. Por padrão, os usuários são atribuídos à página web em que estão ao clicar no botão ***Download*** a menos que outro nome de campanha seja especificado no URL da página inicial (`&c={CAMPAIGN_NAME}`). Para alterar isso, substitua o valor do parâmetro ***campaignParam***.  
   Opcional para TODOS os cenários, exceto anúncios pagos do Meta Ads.

## Visualizando os resultados

[![dashboard_landing_page_results.png](https://files.readme.io/29d7b6b096687a1f106efa4dcfc65ab1f550976516c87c3ffafde29f852855bb-360001342158.png)](https://files.readme.io/29d7b6b096687a1f106efa4dcfc65ab1f550976516c87c3ffafde29f852855bb-360001342158.png)

Como acontece com qualquer canal de mídia, você pode visualizar os resultados da sua página inicial no painel do seu aplicativo, dados brutos ou por meio das APIs da AppsFlyer.

Se o seu funil de marketing móvel sempre leva à sua página inicial, esses canais de mídia representam o seguinte:

| **Fonte** | **Descrição** |
| --- | --- |
| **Orgânica** | Usuários que não passaram pela página inicial ou não engajaram com ela. Como alternativa, os usuários que engajaram, mas não foram atribuídos por vários motivos, por exemplo, passaram pela janela de lookback de atribuição antes de iniciar o aplicativo. |
| **Site** | Usuários orgânicos em mobile que visitam sua página inicial/site e instalam depois |
| **Meta Ads** | Usuários de anúncios pagos do Meta |
| **fbpost\_lp** | Usuários de posts virais de anúncios não pagos do Meta |
| **google\_lp** | Usuários do Google Ads |
| **[SRN]\_lp** | Usuários de outras SRNs, ou seja. Usuários de outros SRNs, ou seja, Twitter (twitter\_lp), Snapchat (snapchat\_lp), Doubleclick (doubleclick\_lp) ou Oath (oath\_lp) |
| **ID de parceiro integrado** | Usuários provenientes de um anúncio de parceiro integrado, que usa o link de atribuição da AppsFlyer. Por exemplo, inmobi\_int, tapjoy\_int |
| **Desktop** | Usuários de desktop que preenchem o formulário da web e concluem uma instalação após clicar no SMS ou e-mail enviado para seus dispositivos mobile posteriormente |
| **Outros canais** | Usuários provenientes de canais de mídia próprios, que usam os links de atribuição da AppsFlyer. Por exemplo, e-mail, sms, blog\_post, etc |

## OneLink para solução de página inicial

O OneLink™ é um link de atribuição exclusivo da AppsFlyer, usado para detecção e redirecionamento de dispositivos ou para deep linking.

A solução <Anchor target="_blank" href="/marketers/pt/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#social-app-landing-page">Página inicial de aplicativos sociais</Anchor> requer que o anunciante tenha um URL básico do OneLink. Os usuários que clicam em anúncios em aplicativos de mídia social são redirecionados para uma página inicial gerada pela AppsFlyer. A partir daí, pode haver um link direto ou eles podem continuar a instalar o aplicativo.

A AppsFlyer fornece uma variedade de templates de páginas iniciais de aplicativos de redes sociais. As posições dos elementos nos templates são fixas, mas os próprios elementos são personalizáveis, incluindo a imagem ou cor de fundo, títulos, textos, imagens, botões, tags e muito mais.

Se você não implementou o OneLink para seu aplicativo:

1. Configure o <Anchor target="_blank" href="/marketers/pt/docs/create-a-onelink-template#como-criar-templates-do-onelink">template do OneLink</Anchor>.
2. Crie um <Anchor target="_blank" href="/marketers/pt/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#crie-um-link-do-onelink">URL OneLink</Anchor> com base no template.
3. No script, substitua https://yourapp.onelink.me/abcd pelo URL do OneLink.

<div data-zendesk-anchors="the-upsides=as-vantagens the-downsides=as-desvantagens the-challenges-of-mobile-attribution-on-landing-pages=os-desafios-da-atribui%C3%A7%C3%A3o-mobile-nas-p%C3%A1ginas-iniciais the-solution=a-solu%C3%A7%C3%A3o landing-page-scenarios=cen%C3%A1rios-de-p%C3%A1ginas-iniciais description=descri%C3%A7%C3%A3o conclusion=conclus%C3%A3o instructions=instru%C3%A7%C3%B5es what-the-script-does=o-que-o-script-faz description::7888dd9d=descri%C3%A7%C3%A3o-1 conclusion::11bed45=conclus%C3%A3o-1 instructions::5aa3290f=instru%C3%A7%C3%B5es-1 what-the-script-does::2a675257=o-que-o-script-faz-1 description::650e3f28=descri%C3%A7%C3%A3o-2 conclusion::a982e4bd=conclus%C3%A3o-2 instructions::afffc83f=instru%C3%A7%C3%B5es-2 what-the-script-does::3fd4ce35=o-que-o-script-faz-2 description::9c3fcdaa=descri%C3%A7%C3%A3o-3 conclusion::bf993a93=conclus%C3%A3o-3 instructions::350b4cb1=instru%C3%A7%C3%B5es-3 what-the-script-does::3dda504d=o-que-o-script-faz-3 description::5150e1b5=descri%C3%A7%C3%A3o-4 conclusion::d51c1aec=conclus%C3%A3o-4 instructions::e083609=instru%C3%A7%C3%B5es-4 what-the-script-does::85ffec6c=o-que-o-script-faz-4 description::f5a2038b=descri%C3%A7%C3%A3o-5 conclusion::4593a93c=conclus%C3%A3o-5 instructions::2e4dd2ee=instru%C3%A7%C3%B5es-5 what-the-script-does::d6370587=o-que-o-script-faz-5 description::e20640cf=descri%C3%A7%C3%A3o-6 conclusion::c818491=conclus%C3%A3o-6 instructions::ba61ae3e=instru%C3%A7%C3%B5es-6 what-the-script-does::3668d917=o-que-o-script-faz-6 landing-page-javascript=javascript-da-p%C3%A1gina-inicial instructions::10da52a9=instru%C3%A7%C3%B5es-7 viewing-the-results=visualizando-os-resultados onelink-for-landing-page-solution=onelink-para-solu%C3%A7%C3%A3o-de-p%C3%A1gina-inicial" />
