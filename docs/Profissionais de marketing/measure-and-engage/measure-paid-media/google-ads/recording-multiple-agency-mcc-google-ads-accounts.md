---
title: Registrando contas do Google Ads de múltiplas agências/MCC
metadata:
  keywords:
    - Advertisers
    - Multiple Agencies
    - MCC
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
  created_at: '2017-09-28T11:11:04Z'
  edited_at: '2026-08-18T00:30:04Z'
  id: 115004970386
  locale: pt
  section: Google Ads
  section_id: 6551205645457
  url: https://support.appsflyer.com/hc/pt/articles/115004970386
---
> **Num relance:** configure o registro para diferentes contas do Google Ads para que o tráfego seja atribuído corretamente.

<div id="introduction" />

## Introdução

O tráfego do Google Ads provém muitas vezes de várias contas, como agências especializadas em Google Ads ou mesmo diferentes equipes internas da organização do proprietário do app. É importante entender como configurar registros para diferentes contas do Google Ads para que a atribuição seja feita às partes corretas.

Este artigo aborda esses casos, desde a medição das agências até a utilização de MCCs e também de MCCs de MCCs.

<div id="note" />

> 📘 **Nota**
>
> As informações a seguir aplicam-se **apenas** a clientes que utilizam a nova API do Google Ads.

Para mais detalhes sobre a configuração da conta da agência no Google Ads<Anchor target="_blank" href="/marketers/pt/docs/google-ads-adwords-integration-setup-for-agencies">, clique aqui</Anchor>.

<div id="important-definitions" />

## Definições importantes

* **ID de link** - **um** **identificador único de um app definido no Google Ads**.

<div id="note-1" />

> 📘 **Observação**
>
> As versões para Android e iOS do mesmo app requerem IDs de link diferentes.

* **ID do cliente** - **identificador único de uma conta do Google Ads**.  
  Cada conta pode publicitar vários IDs de link, por exemplo, para todos os apps da empresa. Ao conectar contas de agência a apps existentes no dashboard da AppsFlyer, você pode definir até 10 IDs de cliente.
* **MCC** - Uma conta de administrador do Google Ads (MCC, antiga My Client Center (Minha Central de Clientes)) é uma **ferramenta** do Google Ads **criada para gerir várias contas do Google Ads**.  
  Com uma conta MCC, você pode conectar várias contas e visualizá-las em um único lugar<Anchor target="_blank" href="https://support.google.com/google-ads/answer/6139186?hl=en&ref_topic=7554904">(Ler mais</Anchor>).

<div id="setting-up-google-ads-recording" />

## Configurar o registro do Google Ads

A AppsFlyer pode registrar um único ID de link por app. **Quando várias contas lidam com o mesmo app, todas devem utilizar o mesmo ID de link.** Isso deve ser configurado no dashboard da AppsFlyer para fins de atribuição.

<div id="sharing-google-link-id-with-another-account" />

### Compartilhar o ID de link do Google com outra conta

Os proprietários de apps com uma única conta do Google Ads ou que planejam trabalhar com agências que gerem tráfego do Google Ads devem utilizar o seguinte método.

O proprietário de app pode compartilhar qualquer ID de link com qualquer outra conta, identificada pelo seu ID de cliente, como mostra a imagem abaixo. A seguir, você encontra mais detalhes sobre o <Anchor target="_blank" href="/marketers/pt/docs/google-ads-adwords-integration-setup-for-agencies#configurar-a-atribuição-do-google-ads-para-agências">compartilhamento do ID de link com uma agência</Anchor>.

<div id="important" />

> 🚧 **Importante**
>
> * Se a MCC for o Administrador de Registros (Recording Manager) das subcontas, não é necessário compartilhar o ID de link da MCC com as subcontas. No entanto, se uma subconta, sob a MCC, for o seu próprio administrador de registros, então a MCC deve compartilhar o ID de link com o Administrador de Registros da subconta.
> * Importar conversões Se a MCC for o administrador de registros, então a MCC é responsável pela importação de conversões para as subcontas controladas por ela. No entanto, se uma subconta na MCC for o seu próprio administrador de registros, essa subconta também deve importar as conversões.

<div id="note-2" />

> 📘 **Nota**
>
> * No painel de controle do Google Ads, clique em (3 pontos) >> ***Contas associadas*** >> ***Detalhes da análise de apps de terceiros*** [![](https://files.readme.io/d3b59e7e4a46e8ae4c075c02a652faed58c3b48340e2f0d253a1330694bdad93-49929446651665.png)](https://files.readme.io/d3b59e7e4a46e8ae4c075c02a652faed58c3b48340e2f0d253a1330694bdad93-49929446651665.png)
> * A outra conta precisa aprovar o "compartilhamento".
> * Assim, a outra conta estará autorizada a executar campanhas do Google Ads para o app.

<div id="tip" />

> 👍 **Dica**
>
> A AppsFlyer recomenda compartilhar o ID do link da conta principal do anunciante com as outras contas, em vez de gerar IDs de link diretamente nessas contas. Essa é a opção mais rápida e que permite separar facilmente o anunciante e as agências quando o trabalho mútuo estiver concluído.

## MCC

As agências ou os grandes anunciantes, que gerem várias contas do Google Ads, utilizam frequentemente uma MCC (My Client Center), que permite visualizar todas as suas contas em um único local.

Durante a configuração da MCC, é possível configurar se a MCC ou as subcontas administram as conversões.

<Image align="center" alt="MCC_1_new.png" src="https://files.readme.io/a4d1a0e1cdbc0bd2b1ffdc4c3d0953eba58303a00c2eb9524f5e4f639d4e9fd6-49929501047313.png" />

Essa configuração pode ser alterada posteriormente, se necessário.

<Image align="center" alt="mmc-googleads-settings.png" src="https://files.readme.io/89355ae020242b00c2002153b46ee3525fa71568e581533f2822cac500d28eb7-49929446653713.png" />

<div id="mcc-of-mccs" />

## MCC de MCCs

<Image align="center" alt="" src="https://files.readme.io/b86511bca7ae029df80cafe46d21aaeb7bb7b4b34b3f65e2368e5ec4064aa614-49929446654097.png" />

Os grandes anunciantes que trabalham com várias agências podem utilizar uma conta MCC de MCCs. Semelhante à conta MCC padrão. Recomenda-se que seja a MCC de nível mais elevado dos MCC ou do Anunciante a gerar o ID da link. A configuração correta para esta estrutura requer que as subcontas selecionem o nível correto de MCC (muito provavelmente, o nível mais elevado de MCC) como o administrador de registros. Se esta for a configuração utilizada, então o ID de link não precisa de ser compartilhado com subcontas e as conversões de importação mais gerais são suficientes.

<div id="tip-1" />

> 👍 **Dica**
>
> Para mais informações sobre as MCCs e as hierarquias de contas, consulte os links abaixo:
>
> * <Anchor target="_blank" href="https://support.google.com/google-ads/answer/7456530">Conectar contas ao seu administrador de conta</Anchor>
> * <Anchor target="_blank" href="https://support.google.com/google-ads/answer/7519925?hl=en&ref_topic=7554359">Visualizar a hierarquia da conta de administrador</Anchor>
> * <Anchor target="_blank" href="https://support.google.com/google-ads/topic/7554359?hl=en&ref_topic=6031997">Trabalhar com contas administradas</Anchor>
>
> Para questões relacionadas a estruturas de conta e recomendações, consulte o seu representante do Google.

<div id="opening-a-google-ads-campaign" />

## Abrir uma campanha do Google Ads

Uma MCC não pode abrir diretamente uma campanha do Google Ads. Em vez disso, isso deve ser feito via uma subconta padrão do Google Ads.

Existem duas opções para o registro de conversões:

1. **MCC administra o registro de subcontas**  
   Comum quando existem diferentes equipes na mesma empresa, por exemplo, **uma conta do Google Ads por região na mesma empresa**.  
   A MCC detém a configuração de registro (administrador de registros) para todas as suas subcontas. Quaisquer alterações na configuração do registro são efetuadas apenas no escopo da MCC e todas as subcontas herdam essas configurações automaticamente.  
   A MCC também precisa importar as conversões, o que é feito uma vez e abrange todas as subcontas, e também obter os IDs de link compartilhados para as subcontas.
2. **As subcontas gerem o seu próprio registro**  
   Comum para contas que não estão conectadas, exceto por uma única entidade que as serve, por exemplo, **uma agência que serve diferentes contas de clientes anunciantes**.  
   A importação das conversões, neste caso, deve ser efetuada com cada subconta separadamente. A AppsFlyer registra um único ID de link por app, portanto, para registro de dispositivos móveis, a MCC ou anunciante deve compartilhar o ID do link com as subcontas.

As conversões no Google Ads só podem ser importadas depois de ocorrer a primeira instância de qualquer conversão, seja uma instalação ou um evento in-app.

<div data-zendesk-anchors="introduction=introdu%C3%A7%C3%A3o important-definitions=defini%C3%A7%C3%B5es-importantes setting-up-google-ads-recording=configurar-o-registro-do-google-ads sharing-google-link-id-with-another-account=compartilhar-o-id-de-link-do-google-com-outra-conta mcc-of-mccs=mcc-de-mccs opening-a-google-ads-campaign=abrir-uma-campanha-do-google-ads" />
