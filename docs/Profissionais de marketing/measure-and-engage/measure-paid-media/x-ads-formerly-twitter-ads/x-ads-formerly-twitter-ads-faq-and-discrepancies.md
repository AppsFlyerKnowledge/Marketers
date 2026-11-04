---
title: Guia de configuração do Twitter Ads — perguntas frequentes e discrepâncias
metadata:
  keywords:
    - Advertisers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
  created_at: '2021-11-09T09:34:59Z'
  edited_at: '2026-11-03T01:31:35Z'
  id: 4410464352017
  locale: pt
  section: X Ads (formerly Twitter Ads)
  section_id: 6551370375569
  url: https://support.appsflyer.com/hc/pt/articles/4410464352017
---
> **Visão geral:** resolva as perguntas frequentes do Twitter Ads e entenda as discrepâncias.

<div id="x-ads-faq-and-discrepancies" />

## Perguntas frequentes e discrepâncias do Twitter Ads

<div id="who-can-perform-the-twitter-setup-on-appsflyer" />

<Accordion title="Quem pode realizar a configuração do Twitter na AppsFlyer?">

O usuário que estiver autorizando a integração entre a AppsFlyer e o Twitter deve ter acesso de Administrator de conta do Twitter.

</Accordion>

<div id="what-happens-if-no-twitter-accounts-are-selected-for-attributing-on-appsflyer" />

<Accordion title="O que acontece se nenhuma conta do Twitter for selecionada para atribuição no AppsFlyer?">

Todas as atribuições são para campanhas na conta selecionada. Se nenhuma conta for selecionada, não ocorrerá o envio de eventos in-app e de atribuições para o Twitter, mesmo se o mapeamento do evento in-app ainda estiver visível na janela de Configuração do Twitter.

</Accordion>

<div id="do-the-account-owner-and-the-team-members-see-the-same-twitter-data" />

<Accordion title="O proprietário da conta e os membros da equipe visualizam os mesmos dados do Twitter?">

Não. O proprietário da conta visualiza todas as contas do Twitter conectadas. Os membros da equipe veem apenas suas contas do Twitter conectadas.

</Accordion>

<div id="how-do-i-disconnect-twitter-from-appsflyer" />

<Accordion title="Como desconecto a AppsFlyer do X Ads?">

Você pode desconectar a AppsFlyer de sua conta do Twitter. As instruções a seguir assumem que você está logado em sua conta do Twitter usando um navegador de desktop ou laptop.

1. Faça login no X Ads.
2. No menu à esquerda, clique em **Mais** > **Configurações e Privacidade**.
3. Vá para **Segurança e acesso à conta** > **Aplicativos e sessões** > **Aplicativos conectados**.
4. Clique em AppsFlyer.
5. Clique em **Revogar Acesso**.

Agora você pode voltar para sua conta da AppsFlyer e <Anchor target="_blank" href="/marketers/pt/docs/x-ads-formerly-twitter-ads-integration-setup">conectar uma conta diferente do Twitter</Anchor> se desejar.

</Accordion>

<div id="is-it-possible-to-attribute-installs-to-multiple-twitter-accounts" />

<Accordion title="É possível atribuir instalações a várias contas do X Ads?">

Sim, mas isso requer algumas ações no X Ads. Mas primeiro são necessárias algumas informações:

Você pode conectar **apenas um identificador** (também conhecido como um usuário do twitter) à sua conta da AppsFlyer. Ao conectar esse identificador, sua conta do X Ads aparece na configuração do X Ads no dashboard da AppsFlyer.

Se um dos membros da sua equipe também tiver uma conta do X Ads, isso significa que essa pessoa tem um identificador diferente do seu e não pode conectar esse identificador à AppsFlyer. Isso ocorre porque o **seu identificador é o único que já está conectado à conta da AppsFlyer**. Para que a conta do X Ads dessa pessoa também apareça na AppsFlyer, ela precisa **dar acesso ao seu identificador como administrador da conta na conta do X Ads dela**.

Digamos que o membro da equipe seja Jenny e que o identificador dela é @jenny. Seu identificador é @nivi e é o identificador conectado à AppsFlyer. Para que a conta do X Ads dela apareça na conta da AppsFlyer, **ela precisa dar acesso ao seu identificador como administrador da conta na conta do X Ads dela**. Jenny precisa dar acesso à conta do X Ads dela para Nivi, e não o contrário. Quando ela faz isso, a AppsFlyer examina o identificador de Nivi e vê todas as contas de anúncios às quais está associado, inclusive a de Jenny.

**Para conectar a conta do X Ads da Jenny à AppsFlyer:**

1. Jenny faz login no <Anchor target="_blank" href="https://ads.x.com/">X Ads</Anchor> com o identificador @jenny.
2. Na conta dela do X Ads, Jenny abre as configurações de acesso à conta e concede acesso a @nivi como **Administrador da conta**. Consulte as <Anchor target="_blank" href="https://help.x.com/en/business-and-advertising/multi-user-login-faq">Perguntas frequentes sobre login com vários usuários</Anchor> na Central de ajuda do X.
3. Jenny faz login na AppsFlyer, acessa **Colaborar** > **Integrações de parceiros** > **Integrações ativas**, procura por **X Ads** e o seleciona.
4. A conta dela do X Ads agora aparece nas configurações de integração, e ela pode configurar a integração. Jenny vê apenas a conta dela do X Ads. O administrador da conta vê todas as contas do X Ads conectadas, incluindo a dela.

</Accordion>

<div id="any-special-instructions-for-agencies" />

<Accordion title="Há instruções especiais para agências?">

Sim.  
Quando uma agência cria uma nova campanha no Twitter, o nome da campanha deve começar com o nome da agência e um underline (Exemplo: "NomeAgencia\_Campanha1").

<div id="note" />

> 📘 **Nota**
>
> Para estabelecer a conexão entre a AppsFlyer e o Twitter, é OBRIGATÓRIO que o anunciante configure o Twitter para permitir que as agências executem o tráfego do Twitter.

Para mais detalhes, acesse <Anchor target="_blank" href="/partners/pt/docs/about-agency-accounts#configurações-srn">aqui</Anchor>.

</Accordion>

<div id="do-you-make-twitters-raw-data-available-to-agencies" />

<Accordion title="Os dados brutos do X Ads estão disponíveis para agências?">

Não fornecemos dados brutos do Twitter às agências porque seus termos de serviço consideram as agências como terceiros.

</Accordion>

<div id="im-clicking-save-close-but-twitters-configuration-is-not-saved-help" />

<Accordion title="Estou clicando em Save & Close, mas a configuração do X Ads não é salva! o que devo fazer?">

Se seu aplicativo foi inscrito em outro provedor de atribuição no passado, que foi usado para atribuir instalações do Twitter, podem ocorrer os seguintes erros ao configurar o Twitter no painel da AppsFlyer:

**Erro:  o aplicativo está associado a um provedor de atribuição diferente. Associe-o à AppsFlyer.**

Como alternativa, o seguinte erro também pode aparecer:  

[![](https://files.readme.io/ce96a20f87dc3033e8abcd6666aeb1a9dd9ea646731cfc70fe808443b68e25e0-49929550177297.png)](https://files.readme.io/ce96a20f87dc3033e8abcd6666aeb1a9dd9ea646731cfc70fe808443b68e25e0-49929550177297.png)

**Erro:  houve um erro ao salvar a configuração do Twitter. Falha ao atualizar algumas contas:  XX Vários ids de provedor para o mesmo (appid, conversionType) para o evento appid2872.**

Se a seleção de conta não for salva, isso pode ocorrer porque a conta do Twitter em questão foi anteriormente associada a um provedor diferente pelo Twitter. Para resolver isso:

* Entre em contato com o X Ads para que removam o outro provedor do seu lado
* Selecione o nome da Conta ativa
* Clique em **Save and Close**.
* Se isso ainda não resolver o problema, você terá que entrar em contato com seu provedor de mensuração anterior e pedir para remover as tags antigas do X Ads associadas à sua conta.

</Accordion>

<div id="how-can-i-set-up-retargeting-campaigns-with-twitter" />

<Accordion title="Como posso configurar campanhas de retargeting com o Twitter?">

Para obter detalhes sobre como configurar uma Campanha de Retargeting do Twitter, clique aqui.

</Accordion>

<div id="does-retargeting-affect-inapp-events-sending-to-twitter" />

<Accordion title="O retargeting afeta o envio de eventos in-app ao Twitter?">

Sim. Se o retargeting estiver ativado, a AppsFlyer não envia postbacks do evento af\_app\_opened ao Twitter, conforme solicitado pelo Twitter.  
Observe que mesmo que a janela de configuração do Twitter permita esta seleção, os postbacks de af\_app\_opened não serão enviados com o retargeting.

</Accordion>

<div id="how-can-i-stop-measuring-twitter-attributions" />

<Accordion title="Como posso parar de medir as atribuições do X Ads?">

Para desativar a integração com o Twitter, desmarque todas as contas e clique em **Save & Close**.

</Accordion>

<div id="can-an-agency-measure-twitter-attributions-for-advertisers" />

<Accordion title="Uma agência pode medir as atribuições do Twitter para os anunciantes?">

Sim!  
Para estabelecer a conexão entre a AppsFlyer e o Twitter, é OBRIGATÓRIO que o anunciante selecione uma conta ativa na página de parceiros do Twitter no dashboard da AppsFlyer, para que ao menos uma conta do Twitter seja verificada.  
Depois, a agência precisa conectar sua conta do Twitter diretamente em seu próprio dashboard de agência.

</Accordion>

<div id="can-an-agency-configure-inapp-events-for-twitter" />

<Accordion title="Uma agência pode configurar eventos in-app no Twitter?">

Agências não podem configurar eventos in-app no Twitter. Assim como o Meta ads, eles devem ser configurados pelo anunciante.

</Accordion>

<div id="for-how-long-do-you-keep-twitter-s-userlevel-data" />

<Accordion title="Por quanto tempo a AppsFlyer guarda os dados no nível dos usuários do X Ads?">

O Twitter exige que os provedores de atribuição excluam seus dados em nível de usuário três meses após a instalação. Isso significa que os eventos realizados por esses usuários três meses após a instalação do aplicativo são contados como orgânicos.

Os dados agregados passados permanecem os mesmos.

</Accordion>

<div id="why-do-i-see-duplicated-cost-data" />

<Accordion title="Por que vejo dados de custo duplicados?">

Ao configurar uma campanha no Twitter, você pode adicionar vários aplicativos à campanha. Quando o Twitter relata o custo, os dados de custo total da campanha são exibidos em cada aplicativo na AppsFlyer e não são divididos por aplicativo.

Por exemplo, se você executar uma campanha que custa $1000 para um aplicativo Android e iOS, um custo de $1000 será exibido no painel da AppsFlyer nos aplicativos Android e iOS. O custo não é dividido, por exemplo, para $500 cada.

Para evitar a duplicação de custos, recomendamos que você defina apenas um aplicativo por item de linha/campanha.

</Accordion>

<div id="im-trying-to-link-my-twitter-account-with-appsflyer-but-i-get-an-error-message" />

<Accordion title="Estou tentando vincular minha conta do Twitter à AppsFlyer, mas recebo uma mensagem de erro">

Sua conta do Twitter precisa ser uma conta ativa do tipo Ad para receber dados de atribuição da AppsFlyer.

**Para resolver esse problema:**

1. Faça logout no X Ads.
2. Na AppsFlyer, no menu lateral, selecione **Colaborar > Integrações de parceiro >** **Integrações ativas.**
3. Procure por X Ads e selecione-o. Clique no ícone do Twitter,  
   a janela de configuração do parceiro se abrirá.
4. Na aba **Integração**, clique em **Ativar parceiro**.
5. Clique em **Fazer login com Twitter** e   
   uma janela de login do Twitter será aberta.
6. Faça login com sua conta do X Ads.

</Accordion>

<div id="discrepancies-between-x-ads-and-appsflyer" />

## Discrepâncias entre o X Ads e a AppsFlyer

Embora trabalhemos em estreita colaboração com o X Ads, podem aparecer discrepâncias entre o dashboard do X Ads e o dashboard/relatórios da AppsFlyer.

Estes são os motivos comuns para essas discrepâncias dos quais os anunciantes devem estar cientes:

| Causa | Exemplo | A AppsFlyer |
| --- | --- | --- |
| **Janela de atribuição** | O Twitter permite que seus usuários configurem a janela de atribuição e oferece suporte às atribuições de clique e de exibição. Por padrão — 14 dias de clique e 1 dia de exibição. | Se você não configurou a janela de lookback de atribuição da AppsFlyer para o Twitter com os mesmos valores que no Twitter, poderão ocorrer discrepâncias. |
| **Atribuição de fonte multicanal** | A atribuição do X Ads funciona conforme especificado acima, independentemente de outras fontes. | A AppsFlyer usa a atribuição do último clique (mais informações sobre a atribuição da AppsFlyer disponíveis <Anchor target="_blank" href="/marketers/pt/docs/appsflyer-attribution-model">aqui</Anchor>). |
| **Diferenças de fuso horário** | O fuso horário do Twitter é definido pelo fuso horário configurado pelo aplicativo do anunciante. | O fuso horário padrão da AppsFlyer é UTC±00:00, mas qualquer fuso horário pode ser definido pelo anunciante. |
| **Diferenças de horário de instalação** | O X Ads mostra instalações com base no tempo de clique (conhecido como "tempo de engajamento"). | A AppsFlyer exibe a hora em que o primeiro aplicativo foi aberto. |
| **Tipo de toque de atribuição** | A atribuição do X Ads se baseia em seus próprios cliques e impressões. | A AppsFlyer dá prioridade à atribuição de clique sobre a atribuição de exibição. Se o Twitter conta uma impressão e a AppsFlyer reconhece um clique adicional na janela de atribuição de clique, o clique de outra fonte é atribuído no painel da AppsFlyer. No Twitter, a impressão é atribuída e apresentada no painel deles. |
| **Configurações de compartilhamento de dados do X Ads** | O Twitter permite que seus usuários NÃO <Anchor target="_blank" href="https://twitter.com/settings/account/personalization">compartilhem seus dados pessoais com terceiros</Anchor>. Esses dados incluem anúncios com os quais eles interagem.<br /><br />As estatísticas no painel do Twitter refletem todos os engajamentos, incluindo os usuários que optaram por não compartilhar os dados. | A AppsFlyer mostra os dados agregados desses usuários do Twitter, mas não informa seus dados brutos no nível do usuário (mais <Anchor target="_blank" href="/marketers/pt/docs/x-ads-formerly-twitter-ads-setup-guide-overview#privacidade-do-usuário-no-x-ads">detalhes</Anchor>). |
| **Lógica de reengajamento do X Ads** | O Twitter conta usuários únicos. Se um usuário reengajar mais de uma vez como resultado da mesma campanha, o Twitter mostrará esses engajamentos como uma única conversão. | A AppsFlyer conta cada instância de reengajamento e, portanto, em um caso semelhante, mostra esses engajamentos como múltiplas conversões. |

<div id="note-1" />

> 📘 **Nota**
>
> Como resultado das <Anchor target="_blank" href="/marketers/pt/docs/implement-validation-rules-to-prevent-fraud">Regras de validação da AppsFlyer</Anchor>, os resultados podem diferir nos painéis, pois algumas instalações são mostradas no Twitter e não no painel da AppsFlyer.

<div data-zendesk-anchors="twitter-ads-faq-and-discrepancies=perguntas-frequentes-e-discrep%C3%A2ncias-do-twitter-ads h_01HE7S15F9YR28FBA1TYCE3N0X=perguntas-frequentes-e-discrep%C3%A2ncias-do-twitter-ads h_01HE7S15F9NSQJSP268B0WF0JP=who-can-perform-the-twitter-setup-on-appsflyer h_01HE7S15F9PFZ8CATJC5YWC6QP=what-happens-if-no-twitter-accounts-are-selected-for-attributing-on-appsflyer h_01HE7S15F989Y94YFJ7TGK7QN5=do-the-account-owner-and-the-team-members-see-the-same-twitter-data h_01HE7S15F9GNWTK2N50GAHN52Q=how-do-i-disconnect-twitter-from-appsflyer h_01HE7S15F9CE4F29R97EVCG791=is-it-possible-to-attribute-installs-to-multiple-twitter-accounts h_01HE7S15F9G4M44CB2Q1KQMJPJ=any-special-instructions-for-agencies h_01HE7S15F9VG8XMJE7YSNN245P=nota h_01HE7S15F9A7BBAW8BNN6H4AKQ=do-you-make-twitters-raw-data-available-to-agencies h_01HE7S15F9MM26SGKMAPGDH9F8=im-clicking-save-close-but-twitters-configuration-is-not-saved-help h_01HE7S15F923NKTTCS3Z1C40B5=how-can-i-set-up-retargeting-campaigns-with-twitter h_01HE7S15F931EWS48QVCQYPBCH=does-retargeting-affect-inapp-events-sending-to-twitter h_01HE7S15F98VN1TS99751S34C5=how-can-i-stop-measuring-twitter-attributions h_01HE7S15F9MEKBKAQ3NA76TFKY=can-an-agency-measure-twitter-attributions-for-advertisers h_01HE7S15F921V3T885F39VSPCQ=can-an-agency-configure-inapp-events-for-twitter for-how-long-do-you-keep-twitter%E2%80%99s-userlevel-data=for-how-long-do-you-keep-twitter-s-userlevel-data h_01HE7S15F90RXSWJ7HV3GSJB65=for-how-long-do-you-keep-twitter-s-userlevel-data h_01HE7S15F9B39KV628NSD29P6P=why-do-i-see-duplicated-cost-data h_01HE7S15F9N3CCJEMAD2QB38F9=im-trying-to-link-my-twitter-account-with-appsflyer-but-i-get-an-error-message discrepancies-between-twitter-and-appsflyer=discrep%C3%A2ncias-entre-o-x-ads-e-a-appsflyer h_01HE7S15F9YWCY883DP9TEGQXK=discrep%C3%A2ncias-entre-o-x-ads-e-a-appsflyer h_01HE7S15FAPS2696J3KQG3P3ME=nota-1" />
