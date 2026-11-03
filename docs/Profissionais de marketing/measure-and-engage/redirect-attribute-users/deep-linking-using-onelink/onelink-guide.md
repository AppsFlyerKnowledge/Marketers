---
title: Guia do OneLink
metadata:
  keywords:
    - Marketers
    - start
    - Smart Banners and Scripts
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-asaf-mashiah
    - Marketers
    - Smart Banners and Scripts
  created_at: '2017-10-19T08:53:16Z'
  edited_at: '2026-08-19T00:33:28Z'
  id: 115005248543
  locale: pt
  section: Deep linking using OneLink
  section_id: 6551203111057
  url: https://support.appsflyer.com/hc/pt/articles/115005248543
---
> **Visão geral:** crie links com atribuição, redirecionamento e funções de deep linking para converter usuários obtidos através de mídia própria ou paga em usuários do seu app em qualquer dispositivo, sistema operacional, canal ou plataforma.  Esses links te ajudam a fornecer uma experiência melhor para os seus usuários, independentemente da fonte de mídia usada para a conversão: site, banners, publicações nas redes sociais, e-mails, textos e muito mais.

## Vídeo de introdução

<Embed title="Guia do OneLink" typeOfEmbed="youtube" url="https://www.youtube.com/embed/golT4p9D8MA" providerUrl="https://www.youtube.com" />

## Vantagens

As ferramentas de experiência do cliente e deep linking do OneLink da AppsFlyer permitem que você crie links para mensurar suas campanhas de marketing mobile em todos os seus principais canais. Esses links permitem que você:

* Interaja com seus clientes em diversos pontos de contato online e offline.
* Aumente as conversões, fornecendo as melhores experiências contextuais aos seus usuários em qualquer ponto de contato, desde o clique até a instalação.
* Acesse atribuições e métricas precisas em relação aos resultados da sua campanha.
* Envie novos usuários para a loja de aplicativos ou URL da web corretos em qualquer dispositivo, sistema operacional, canal ou plataforma.
* Envie usuários existentes diretamente para o aplicativo (usando App Links, Universal Links, e esquemas URI).
* Leve usuários para páginas ou experiências específicas no aplicativo.

<Anchor target="_blank" href="/marketers/pt/docs/use-onelink-api-to-create-links-in-large-scale-campaigns">OneLink API</Anchor> e <Anchor target="_blank" href="/marketers/pt/docs/perform-onelink-bulk-actions-via-csv">criação de links em massa</Anchor>: escale e execute várias campanhas de uma só vez, e crie milhares de OneLinks de forma rápida e fácil, economizando tempo e esforço. Para manter as suas experiências do OneLink a funcionar sem problemas, certifique-se de que o seu plano permanece ativo.

## Experiências

O conjunto de ferramentas de experiência do cliente e deep linking do OneLink da AppsFlyer permite que você crie links que oferecem a melhor experiência para os seus usuários. Listamos algumas das experiências que podem ser configuradas:

* **Social-to-app**: engaje seus usuários nas redes sociais e envie-os das suas publicações para o seu app.
* App-to-app: conduza os usuários ao seu aplicativo de dentro de outros aplicativos.
* <Anchor target="_blank" href="/marketers/pt/docs/convert-your-mobile-web-visitors-to-app-users">Web-to-app</Anchor>: **converta os visitantes do seu site mobile em novos usuários de aplicativos mobile usando Smart Banners ou Smart Script.**
* QR-to-app/span>: use QR codes para impulsionar as instalações de aplicativos, fazendo com que os usuários digitalizem um QR code em pontos-chave durante a experiência offline do cliente. Você também pode colocar QR codes em seu site para desktop ou em anúncios de TV e CTV para direcionar os usuários ao seu aplicativo.
* **Email-to-app**: use provedores de serviços de e-mail (ESPs) para engajar os usuários por e-mail e direcioná-los da caixa de entrada para o seu aplicativo./span>
* **Text-to-app**: crie /span>links para suas campanhas de SMS e mensagens e engage com os usuários por mensagens de texto.
* Referral-to-app: **crie links que permitam aos usuários e influenciadores convidar outros para seu aplicativo ou compartilhar conteúdo específico em seu aplicativo, por exemplo, um artigo.**
* **Personalizado**: independentemente de onde seus usuários venham, seja via desktop ou celular, online ou offline, mídia própria ou paga, use o OneLink para enviar seus usuários facilmente para o lugar certo./span>

## Configurando o OneLink

Para fornecer a melhor experiência aos seus usuários, desde o clique no link até a instalação do aplicativo, é necessário:

* Profissionais de marketing e desenvolvedores devem trabalhar em conjunto.
* <Anchor target="_blank" href="/marketers/pt/docs/create-a-onelink-template">Crie um template do OneLink</Anchor> que represente a lógica de roteamento de todos os seus links, para redirecionar:
  * Novos usuários sem o app instalado para a loja de aplicativos ou URL corretos.
  * Usuários existentes que já têm o seu app instalado para o aplicativo em si, via Android App Links, iOS Universal Links, ou esquemas URI.

    * Se nenhuma dessas opções estiver configurada, esses usuários serão enviados para o mesmo fluxo de novos usuários, que não têm o app instalado.

    **Observação**: Um template do OneLink não é um link clicável para os seus usuários finais; ele é a base para gerar muitos links personalizados. Com base no template, você pode criar links personalizados do OneLink, nos quais os usuários podem clicar. É incomum que seja necessário mais de um ou dois templates do OneLink durante a vida útil de um aplicativo (sem considerar testes).
* <Anchor target="_blank" href="/marketers/pt/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink">Criando um link do OneLink</Anchor>. Esse é o link clicável ou o QR code exibido nos seus anúncios. Durante a configuração do link, você define a experiência desejada e adiciona quaisquer parâmetros necessários.

A tabela a seguir descreve os detalhes das tarefas do profissional de marketing e do desenvolvedor.

| Função | Detalhes | Recursos |
| --- | --- | --- |
| Criar template do OneLink | <ul><li>O profissional de marketing/gerente de produto configura o template na AppsFlyer.</li><li>O desenvolvedor do Android configura métodos de abertura do aplicativo para usuários existentes (Android App Links e esquema URI).</li><li>O desenvolvedor do iOS configura métodos de abertura do aplicativo para usuários existentes (esquema URI e Universal Links do iOS).</li></ul> | <ul><li>Dashboard da AppsFlyer</li><li><Anchor target="_blank" href="/marketers/pt/docs/create-a-onelink-template">Instruções para profissionais de marketing</Anchor></li><li>Instruções para desenvolvedores para <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_android_init_setup#app-opening-methods">Android</Anchor> e <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_ios_init_setup">iOS</Anchor></li></ul> |
| Criar um link do OneLink | <ul><li>O profissional de marketing/gerente de produto configura o link na AppsFlyer, incluindo a experiência desejada e adicionando qualquer atribuição ou parâmetros de deep linking necessários.</li><li>Os desenvolvedores do Android e do iOS implementam o método UDL para deep linking (se o deep linking for necessário).</li></ul> | <ul><li><Anchor target="_blank" href="/marketers/pt/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink">Instruções para profissionais de marketing</Anchor></li><li>Instruções para desenvolvedores para <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_android_unified_deep_linking">Android</Anchor> e <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/dl_ios_unified_deep_linking">iOS</Anchor></li><li>Amostras de aplicativo (Github)</li></ul> |

## Opções adicionais

Depois de concluir algumas ou todas as configurações na interface do usuário, considere implementar os recursos adicionais descritos abaixo.

* **Observação**: todos os recursos estão inclusos como parte dos <Anchor target="_blank" href="/marketers/pt/docs/account-management-plans-payments-and-billing">planos Zero e Growth</Anchor>, exceto a OneLink API, que é um recurso premium.
* <Anchor target="_blank" href="/marketers/pt/docs/export-onelink-urls">Exportar URLs do OneLink</Anchor>: baixe todas as URLs do OneLink criadas na interface do usuário da AppsFlyer (URLs do OneLink criadas via SDK, OneLink API ou upload em massa não estão incluídas).
* <Anchor target="_blank" href="/marketers/pt/docs/measuring-push-notification-re-engagement-campaigns">Mensure campanhas de reengajamento com notificações push</Anchor>: Use notificações push com o OneLink para mensurar o reengajamento de usuários mobile.
* <Anchor target="_blank" href="/marketers/pt/docs/cross-promotion-attribution-for-marketers">Atribuição em promoção cruzada</Anchor>: os usuários existentes do seu aplicativo são excelentes candidatos para instalar seus novos aplicativos. Saiba como usar métodos do SDK para criar e mensurar facilmente campanhas de promoção cruzada.
* <Anchor target="_blank" href="/marketers/pt/docs/understand-onelink-short-vs-long-urls">URLs longas:</Anchor> adicione parâmetros aos links personalizados do OneLink ou gere um grande número de links personalizados do OneLink aplicando suas próprias fórmulas simples em uma planilha.
* <Anchor target="_blank" href="/marketers/pt/docs/redirect-app-users-to-a-website">Redirecionamento app-to-web</Anchor>: Redirecione os usuários do seu aplicativo para um site ou página de rede social.

## Solução de problemas e perguntas frequentes

Encontre rapidamente soluções para testar e depurar problemas de redirecionamento/comportamento de links personalizados do OneLink com nosso <Anchor target="_blank" href="/marketers/pt/docs/onelink-troubleshooting-and-faq">guia de solução de problemas do OneLink</Anchor>.

## Limitações

* O OneLink não é compatível com o Meta mobile app install objective - apenas Meta App Links são aceitos.
* Se o seu plano de assinatura paga expirar, determinados links e recursos do OneLink deixarão de estar disponíveis. Isso pode afetar links de ESP e de domínios personalizados, desativar a criação e as solicitações de links por SDK e API (a menos que tenham sido adquiridos separadamente) e revogar o acesso ao Web-to-app e à criação de links em massa.

<div data-zendesk-anchors="introduction-video=v%C3%ADdeo-de-introdu%C3%A7%C3%A3o h_01HGE1D5JZ4Y603BD55W2P7DPW=v%C3%ADdeo-de-introdu%C3%A7%C3%A3o benefits=vantagens h_01HGE1D5JZJGY8BZX8ZTSXQ635=vantagens experiences=experi%C3%AAncias h_01HGE1D5JZV65E9YWG424HYRNW=experi%C3%AAncias setup=configurando-o-onelink h_01HGE1D5K0RKHHV9SVH4VREMXQ=configurando-o-onelink additional-options=op%C3%A7%C3%B5es-adicionais h_01HGE1D5K2VCKYJY3Y8MKYVT2V=op%C3%A7%C3%B5es-adicionais troubleshooting-and-faq=solu%C3%A7%C3%A3o-de-problemas-e-perguntas-frequentes h_01HGE1D5K24FG3F8G54DYTK599=solu%C3%A7%C3%A3o-de-problemas-e-perguntas-frequentes limitations=limita%C3%A7%C3%B5es h_01HGE1D5K2M0VMJPMP4EJ0QGPY=limita%C3%A7%C3%B5es" />
