---
title: Gerenciar usuários
metadata:
  keywords:
    - Advertisers
    - Marketers
    - Platform essentials
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-negri
    - Marketers
    - Platform essentials
  created_at: '2021-10-17T11:54:49Z'
  edited_at: '2026-09-21T00:14:40Z'
  id: 4409128270481
  locale: pt
  section: Account management
  section_id: 6551191075473
  url: https://support.appsflyer.com/hc/pt/articles/4409128270481
---
> **Resumo:** crie e gerencie os usuários da sua conta na AppsFlyer e atribua permissões para acessar recursos, aplicativos e dados.

<div id="overview" />

## Visão geral

As contas da AppsFlyer permitem vários usuários, cada um com permissões gerenciadas individualmente. O número máximo de usuários por conta é determinado pelo seu plano de assinatura.

As permissões de cada usuário são definidas da seguinte maneira:

* **Função** (capacidade de acessar recursos e executar funções)
* **Acesso ao aplicativo** para aplicativos atuais e futuros
* **Acesso a dados** por canal de mídia e geolocalização
  * Importante! Alguns dashboards e recursos da AppsFlyer não estão disponíveis para usuários com acesso limitado (a canais de mídia e geolocalização). Esses dashboards e recursos estão [listados aqui](#dashboard-and-feature-availability-for-users-with-limited-media-sourcegeo-access).

As permissões dentro de cada uma dessas dimensões são atribuídas de forma independente. Ou seja, você pode atribuir uma **função** com amplos recursos funcionais a um usuário, mas permitir que ele exerça esses recursos apenas em um conjunto definido de **aplicativos, canais de mídia e geolocalizações.** A única exceção é a [função de administrador](#administrador), pois ela possui acesso a todos os recursos, aplicativos, canais de mídia e geolocalizações.

Os administradores podem [adicionar usuários a várias contas](#multiple-accounts) para alternar facilmente entre contas.

<div id="user-management-page" />

## Página de gestão de usuários

**Para acessar a página de gestão de usuários:**

* Na barra superior, abra o menu da conta (menu suspenso do endereço de e-mail) > **gerenciar usuários**.

[![user-management-page.jpg](https://files.readme.io/0ca6dd472b6f50bfde693bba9c131ce9454dc1df90e3a0fb029e2e05b2330db4-31780969019665.jpg)](https://files.readme.io/0ca6dd472b6f50bfde693bba9c131ce9454dc1df90e3a0fb029e2e05b2330db4-31780969019665.jpg)

<div id="users-tab" />

<Accordion title="Aba usuários">

A aba **usuários** exibe uma tabela de todos os usuários existentes em sua conta. Esse é o ponto de partida para criar, gerenciar e excluir usuários.

Dicas para navegar na aba usuários:

* Clique em **usuário** para classificar a tabela em ordem alfabética (ascendente/decrescente).
* Use a caixa de pesquisa para encontrar e exibir usuários específicos.
* Clique no ícone de filtro <Image alt="filter_icon.png" src="https://files.readme.io/1ceaac3efead3a218909988be1d50a2f0af93b07360f7197cd398b11d661992b-16162502598417.png" width="25px" /> no cabeçalho da coluna **Função** para filtrar os usuários por função (incluindo funções temporárias).
  * Para limpar o filtro, selecione **nenhum** na lista suspensa de filtros.
* Clique em **último login** para ordenar os usuários pela data da última vez em que eles se conectaram à AppsFlyer.
  * **Dica:** use esse recurso para identificar facilmente e [excluir](#deleting-users) usuários inativos, mantendo a sua conta protegida contra logins não autorizados.
* Use as caixas de seleção para selecionar e [editar vários usuários](#edição-multiusuário) ao mesmo tempo.
* Apenas administradores: clique no ícone de download <Image alt="download_icon.png" src="https://files.readme.io/fba5d56ceb7f6b3dc3191e5ec33c85ccbba0f7dc409ad0390de238c12b479b61-31780969029777.png" width="24px" /> no canto superior direito da página para baixar a tabela completa de usuários como um arquivo CSV.
  * O arquivo baixado inclui as mesmas colunas da tabela na aba **usuários**.

</Accordion>

<div id="roles-tab" />

<Accordion title="Aba Funções">

A aba **funções** exibe uma lista de todas as funções definidas na sua conta, incluindo:

* [Funções predefinidas](#funções-predefinidas)
* [Funções personalizadas](#gerenciar-funções-personalizadas) criadas por você
* Qualquer [função temporária](#funções-temporárias) atualmente atribuída aos usuários

Ao lado de cada função, você pode ver o número de usuários que possuem uma determinada função.

Clique no nome de qualquer função no painel esquerdo para ver os detalhes completos dos recursos da função.

</Accordion>

Listamos abaixo as ações disponíveis para garantir uma gestão eficaz dos seus usuários e suas respectivas funções.

<div id="manage-users" />

## Gerenciar usuários

Os administradores podem criar novos usuários, adicioná-los a várias contas, editar suas informações, como funções e acesso a aplicativos e dados, e excluir usuários. Algumas dessas ações podem ser feitas [em massa usando uma API dedicada](#gerenciar-usuários-em-massa-através-da-api).

<div id="creating-users" />

<Accordion title="Criar usuários">

<Embed title="Gerenciar usuários" typeOfEmbed="youtube" url="https://www.youtube.com/embed/wLCXP5dFrKg" providerUrl="https://www.youtube.com" />

Na página dedicada para criar ou editar usuários inclui várias seções. Certifique-se de completá-las, conforme descrito abaixo. Quando terminar de fazer as alterações necessárias, clique em **salvar** no canto inferior direito da página.

<div id="user-details" />

#### Detalhes do usuário

1. Na aba **usuários**, clique em **novo usuário**.
2. Insira o nome do usuário (obrigatório):
   * Pode incluir letras, números, espaços, pontos (.), hífens (-), sublinhados (\_) e aspas simples (') ou duplas (").
   * Outros caracteres especiais não são permitidos.
3. Digite o endereço de e-mail do usuário (obrigatório):

   * Você pode incluir letras, números, apóstrofes ('), e comercial (&), cifrões ($), símbolos hash (#), hífens (-), sublinhados (\_) e pontos (.)
   * Dois pontos consecutivos (..) e outros caracteres especiais não são permitidos.
   * Você deve inserir um e-mail válido.

   <div id="important" />

   > 🚧 **Importante!**
   >
   > O endereço de e-mail de um usuário é o que o identifica na plataforma da AppsFlyer, o que significa que:
   >
   > * Ele não pode ser alterado posteriormente sem que seja feito o processo de excluir e recriar um usuário.
   > * Deve ter um endereço de e-mail válido no qual o usuário possa receber e-mails.
   > * Em teoria, ele não pode estar associado a outro usuário em outra conta da AppsFlyer. No entanto, ele pode ser um [usuário com acesso a múltiplas contas](#multiple-accounts). Se o endereço de e-mail já estiver em uso (na sua conta ou em outra), você verá a mensagem *não é possível criar esse usuário.* Nesse caso, siga as [etapas de solução de problemas abaixo](/docs/user-management#troubleshooting-can-t-create-this-user).

4. [Opcional] Selecione o departamento do usuário.

<div id="role" />

#### Cargo

Selecione a função do usuário (obrigatório) – pode ser uma função predefinida ou uma função personalizada que você já tenha criado.

<div id="app-access" />

#### Acesso ao aplicativo

Selecione quais aplicativos o usuário pode acessar:

* A configuração padrão permite o acesso a todos os aplicativos atuais e futuros da conta. Para alterar essa configuração, use as caixas de seleção para marcar e desmarcar aplicativos.
* Um usuário pode ter acesso a todos os aplicativos futuros somente se tiver acesso a todos os aplicativos atuais.

<div id="data-access" />

#### Acesso de dados

Defina os níveis de acesso do usuário para fontes de mídia e geos. Você pode conceder acesso a tudo ou a opções específicas.

<div id="note" />

> 📘 **Nota**
>
> Usuários com acesso limitado a fontes de mídia ou geos não conseguem acessar certos [dashboards e recursos](/docs/user-management#dashboard-and-feature-availability-for-users-with-limited-media-sourcegeo-access).

<div id="media-sources" />

#### Canais de mídia

Por padrão, a configuração **todos** permite acesso a todas as fontes de mídia dentro da conta. Isso inclui aquelas que podem ser adicionadas no futuro. Selecionar fontes de mídia específicas não inclui acesso a futuras fontes de mídia.

<div id="note-1" />

> 📘 **Nota**
>
> * Usuários com acesso limitado não conseguem acessar certos [dashboards e recursos](/docs/user-management#dashboard-and-feature-availability-for-users-with-limited-media-sourcegeo-access).
> * Funções de administração e segurança têm acesso irrestrito a todas as fontes de mídia. Isso não pode ser alterado.

**Tipos de fonte de mídia:**

Existem dois tipos de fontes de mídia na lista:

* **Fontes de mídia pagas:** ad networks, redes de autorrelato (SRNs) e agências
* **Fontes de mídia personalizadas:** fontes de mídia predefinidas. Inclui links de mídia próprios, links de fonte única, links do OneLink e links que o anunciante criou fora da AppsFlyer.

**Especificações da lista de fontes de mídia:**

* Apresenta fontes de mídia com tráfego dos últimos 24 meses, com aquelas com o tráfego mais recente no topo da lista.
* As agências são agrupadas separadamente na parte inferior da lista.
* Contém um máximo de 10.000 fontes de mídia:
  * Até 5.000 ad networks, SRNs e fontes de mídia personalizadas.
  * Até 5.000 agências.
* É atualizada uma vez por dia. As fontes de mídia recém-adicionadas só são exibidas um dia após o tráfego ter entrado no sistema.
* Fontes de mídia sem tráfego por mais de 5 anos são removidas da lista.

**Para alterar a configuração padrão:**

1. Em **fontes de mídia (media sources)**, clique em **todas (all)**.
2. Na lista suspensa, selecione as fontes de mídia específicas que o usuário pode acessar.

Após salvar, os dashboards dos usuários mostram apenas dados das fontes de mídia selecionadas.

<div id="geos" />

#### Geolocalização

Selecione se os usuários podem acessar dados para **todas** as geos ou apenas geos específicas. A configuração padrão permite o acesso a todas as geos. Usuários com acesso limitado não conseguem acessar certos [dashboards e recursos](/docs/user-management#dashboard-and-feature-availability-for-users-with-limited-media-sourcegeo-access).

**Para alterar a configuração padrão:**

1. Em **geos**, clique em **todas (all)**.
2. Na lista suspensa, selecione as geos específicas que o usuário pode acessar.

<div id="user-activation" />

#### Ativação do usuário

Depois que o usuário for criado, você poderá vê-lo na tabela de usuários com um ícone de envelope ![pending_invitation_icon.png](https://files.readme.io/68ac08ab6e52191a592350f82996f7ade9d181773d0bdbc6e2cb60315b60a8f2-16162502609553.png). Isso indica que um convite foi enviado e a conta está aguardando ativação. O usuário deve ativar sua conta através do link em seu e-mail. O link de ativação é válido por 48 horas. Depois que o usuário ativa a conta, o envelope desaparece.

<div id="note-2" />

> 📘 **Nota**
>
> Se o usuário não recebeu o convite ou se o link expirou, você pode [reenviar o convite](/docs/user-management#resending-a-user-invitation).

</Accordion>

<div id="multiple-accounts" />

<Accordion title="Adicione usuários a várias contas">

Os usuários podem ser adicionados a várias contas e atribuídos a diferentes funções em cada conta. Isso permite que os usuários trabalhem em diferentes contas, sem precisar alterar suas credenciais.

<div id="log-in-to-multiple-accounts" />

#### Login em mais de uma conta

Os usuários podem fazer login em várias contas usando todos os métodos de login: credenciais (nome de usuário e senha), <Anchor target="_blank" href="/marketers/pt/docs/implementing-and-using-2fa-login">autenticação de dois fatores</Anchor> e <Anchor target="_blank" href="/marketers/pt/docs/set-up-sso-authentication-with-your-identity-provider-idp">SSO</Anchor>.

<div id="note-3" />

> 📘 **Importante!**
>
> Ao alternar entre contas (não durante o login inicial), os usuários também precisam inserir um código de verificação de 6 dígitos enviado para o e-mail, independentemente do método de login usado para entrar. <Anchor target="_blank" href="/marketers/pt/docs/welcome-to-appsflyer#alternar-entre-contas">Veja este artigo para mais informações sobre como alternar entre contas</Anchor>.

<div id="supported-accounts-and-users" />

#### Contas e usuários disponíveis

As contas de anunciantes permitem que um mesmo usuário acesse diversas contas. Com as permissões corretas, elas podem adicionar usuários a todas as suas contas. Veja as limitações abaixo.

<div id="limitations-on-adding-users-to-multiple-accounts" />

#### Limitações para adicionar usuários a várias contas

* Esse recurso está disponível apenas para contas de anunciantes e apenas para usuários com permissões apropriadas de gestão de usuários.
* Um usuário pode ter a função de [proprietário](#proprietário-da-conta) em apenas uma conta. Em outras contas, ele pode desempenhar qualquer outra função.
* Usuários que ainda não [ativaram suas contas](#ativação-do-usuário) não podem ser adicionados a outra conta.

<div id="add-users-to-multiple-accounts" />

#### Adicione usuários a várias contas

**Para adicionar o mesmo usuário a várias contas:**

1. Faça login na conta na qual deseja adicionar o usuário.
2. **Na barra de menu, clique no** **menu suspenso no endereço de e-mail** > Gerenciar usuários.
3. Em **usuários**, clique em **novo usuário**.
4. Insira os detalhes necessários, selecione a função do usuário nessa conta e clique em **salvar**.
5. Repita as etapas 1 a 4 para adicionar os usuários a outras contas.

</Accordion>

<div id="editing-users" />

<Accordion title="Editar usuários">

Os usuários podem ser editados um de cada vez ou em grupos.

<div id="individual-editing" />

#### Edição individual

**Para editar um usuário individualmente:**

1. Em **usuários**, clique no botão **ações** <Image alt="actions_icon.png" src="https://files.readme.io/24ad987d1e77d9dfa8559a370733a7b62a6d86954ec1d552eac9c406445ed927-16162502616593.png" width="25px" /> no lado direito da linha do usuário.
2. Selecione **editar** no menu.
3. Edite as configurações do usuário conforme necessário.
4. Todas as configurações, exceto o endereço de e-mail, são editáveis (incluindo função, aplicativos, fontes de mídia e geos).
5. Clique em **salvar**.

<div id="multi-user-editing" />

#### Edição multiusuário

A edição multiusuário é uma maneira eficiente de alterar as permissões da conta de vários usuários ao mesmo tempo. O uso desse recurso em combinação com os recursos de pesquisa e filtragem da aba **usuários** pode ser particularmente útil para gerenciar um grande número de usuários.

<div id="note-4" />

> 📘 **Nota**
>
> Não é possível atribuir a função de administrador usando a opção de edição multiusuário.

**Para editar vários usuários:**

1. Em **usuários**, marque as caixas de seleção do usuário ou usuários que você deseja editar.
   * Marque a caixa de seleção no cabeçalho da coluna para selecionar todos os usuários visíveis.
   * O número de usuários selecionados é exibido no lado direito da caixa de pesquisa. Observe que o [proprietário da conta](#proprietário-da-conta) não pode ser selecionado e não está incluído no número de usuários selecionados.
2. Uma série de botões aparece no canto superior direito da tabela: **Função, apps, canais de mídia** e **geos.**
   * Se um ou mais usuários selecionados tiverem acesso a aplicativos futuros, o botão **aplicativos** não estará disponível. (Consulte [limitações temporárias](/docs/user-management#limitações-da-função-temporária) abaixo.)
3. Clique no botão das permissões que você deseja alterar.
4. Faça as alterações necessárias usando a caixa de diálogo ou as listas suspensas exibidas.
   * Lembre-se de que suas alterações se aplicam a todos os usuários selecionados!
5. Os usuários editados são destacados na tabela e aparecerão da forma devida assim que as alterações forem salvas. No entanto, você ainda tem a oportunidade de revisar suas alterações e confirmá-las ou cancelá-las na próxima etapa.
6. Revise suas alterações. Clique em **salvar** para confirmar ou em **cancelar** para desfazer.

<div id="example" />

> 📄 **Exemplo**
>
> **Cenário:**
>
> * Você possui 30 usuários em sua conta. Dez deles possuem a função **Marketing–limitado**.
> * Alice, José e Pedro acabaram de ser promovidos, e você quer mudá-los da função **Marketing–limitado** para a função Marketing.
> * Alice trabalhará com o aplicativo Astounding. José trabalhará com o aplicativo Beautiful. Pedro trabalhará com o aplicativo Charming.
>
> **Cenário:**
>
> 1. Use o filtro de função <Image alt="filter_icon.png" src="https://files.readme.io/1ceaac3efead3a218909988be1d50a2f0af93b07360f7197cd398b11d661992b-16162502598417.png" width="25px" /> para ver somente os usuários na função **Marketing—** limitado.
> 2. Mude Alice, José e Pedro para a função **Marketing**:
>    * Marque as caixas de seleção para Alice, José e Pedro.
>    * Clique no botão **função**.
>    * Selecione **Marketing** na lista suspensa.
>    * Clique em **salvar** para confirmar.
>    * Observe que, depois de confirmar as alterações, o filtro **função** é limpo e a tabela exibe todos os usuários.
> 3. Dê a Alice, José e Pedro acesso ao aplicativo apropriado:
>    * Use a caixa de pesquisa para encontrar Alice e, em seguida, edite seu usuário individualmente para dar a ela acesso ao aplicativo Astounding.
>    * Repita essas etapas para José e Pedro para dar a eles acesso a Beautiful and Charming, respectivamente.

</Accordion>

<div id="deleting-users" />

<Accordion title="Excluir usuários">

Você pode excluir usuários em massa.

<div id="note-5" />

> 📘 **Nota**
>
> * O [proprietário da conta](/docs/user-management#proprietário-da-conta) não pode ser excluído.
> * Esse processo é irreversível

<span id="to-delete-users"></span>**Para excluir usuários:**

1. Em **usuários**, marque o(s) usuário(s) que você deseja excluir. Você pode usar a barra de pesquisa e filtros para encontrar os usuários.
2. Depois de selecioná-los, clique no botão **excluir** que aparece no canto superior direito da tabela.
3. A janela de confirmação lista os usuários que serão excluídos. Clique em **sim, excluir**para confirmar.

</Accordion>

<div id="manage-users-in-bulk-via-api" />

### Gerenciar usuários em massa através da API

Algumas ações de gestão de usuários podem ser feitas em massa usando <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/bulk-users-management-overview">uma API dedicada</Anchor> :

* [Criar](https://dev.appsflyer.com/hc/reference/bulk-users-post) múltiplos usuários
* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/bulk-users-delete">Excluir</Anchor> múltiplos usuários
* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/bulk-users-get">Obter</Anchor> detalhes de acesso de múltiplos usuários

A API oferece os principais recursos de gestão de usuários na plataforma e inclui as mesmas verificações de erro.

<div id="manage-roles" />

## Gerenciar funções

Cada usuário da sua conta da AppsFlyer deve ter uma função. Cada uma dessas funções define os recursos específicos que o usuário pode acessar e as funções que ele pode executar. A lista completa desses recursos por função está disponível na [aba funções](#roles-tab) da página de **gerenciamento de usuários**.

As funções na AppsFlyer podem ser [predefinidas](#funções-predefinidas), [personalizadas](#funções-personalizadas) ou (em certos casos) [temporárias](#funções-temporárias).

<div id="predefined-roles" />

### Funções predefinidas

A AppsFlyer possui diversas funções predefinidas:

* [Administrador — uma função especial](#administrador)
* Gerente de equipe
* Líder de marketing
* marketing
* Marketing — limitado
* Contribuinte
* Contabilidade
* Segurança
* Controle de qualidade

<div id="note-6" />

> 📘 **Nota**
>
> Para cada uma dessas funções, os recursos disponíveis são fixos. No entanto, você pode alterar os recursos funcionais de um usuário a qualquer momento alterando sua função (com a exceção do [proprietário da conta](#proprietário-da-conta))

<div id="example-1" />

> 📄 **Exemplo**
>
> Você atribuiu a José Silva a função de **gerente de equipe.** Essa função permite que ele gerencie os **templates do OneLink**, mas não permite que ele acesse as páginas **Meu plano** e **Pagamentos**.
>
> **Pergunta:** posso manter José na função de gerente de equipe, mas também permitir que ele acesse as páginas Meu plano e Pagamentos? Posso excluir seu acesso aos templates do OneLink?
>
> **Resposta:** Não. **Resposta:** enquanto José permanecer na função de gerente de equipe, você não poderá permitir que ele acesse as páginas Meu plano e Pagamentos. Você também não poderá remover sua capacidade de gerenciar templates do OneLink. Você pode atribuir uma função predefinida diferente - assim o acesso de José mudará de acordo com a sua nova função. Ou então, você pode criar uma função personalizada para José, que muda seu acesso de acordo com as suas necessidades.

<div id="admin" />

### Administrador

Uma conta da AppsFlyer pode ter **um ou mais administradores**. Essa função tem várias características únicas:

<div id="access" />

#### Acesso

A função de administrador tem acesso a **todos** os recursos da conta, incluindo:

* Todos os recursos e funções
* Todos os aplicativos atuais e futuros
* Todas as fontes de mídia e geos

Esse “acesso completo” não pode ser alterado ou limitado.

<div id="manage-tokens" />

#### Gerenciar tokens

Apenas um usuário com um papel de administrador pode <Anchor target="_blank" href="/marketers/pt/docs/managing-appsflyer-tokens">gerenciar tokens</Anchor>: criar, renomear e remover tokens de API e de servidor para servidor (S2S).

<div id="role-duplication" />

#### Duplicar funções

A função de administrador **não pode ser duplicada** na hora de criar [funções personalizadas](#gerenciar-funções-personalizadas).

<div id="invite-new-partners-to-appsflyer" />

#### Convide novos parceiros para a AppsFlyer

Um usuário com um papel de administrador pode <Anchor target="_blank" href="/marketers/pt/docs/partner-integrations#convide-novos-parceiros-para-a-appsflyer">enviar um link de convite</Anchor> via Marketplace de parceiros para convidar um parceiro que não está integrado com a AppsFlyer.

<div id="account-owner" />

### Proprietário da conta

O usuário criado no momento em que a conta foi aberta, ou seja, o "proprietário da conta", recebe a função de **administrador por padrão**. O proprietário da conta é inicialmente responsável por criar usuários adicionais, até que usuários adicionais com recursos de gerenciamento de usuários sejam criados.

Essa função tem características únicas além do papel de administrador. O proprietário da conta **não** pode ser excluído, removido da função de administrador ou editado na página [gerenciar usuários.**Se você precisar alterar o proprietário da conta, siga os** passos listados abaixo.](/docs/user-management#página-de-gestão-de-usuários)

<div id="custom-roles" />

### Funções personalizadas

As funções predefinidas na AppsFlyer foram configuradas com combinações específicas para a maioria das situações. Por isso, muitos anunciantes não sentem a necessidade de personalizar ainda mais essas funções. Quando isso se torna necessário, as funções predefinidas ainda são um ótimo ponto de partida para gerenciar os recursos dos seus usuários.

Saiba mais sobre como [gerenciar funções personalizadas](#gerenciar-funções-personalizadas).

<div id="temp-roles" />

### Funções temporárias

Se você já tinha uma conta da AppsFlyer em nosso antigo sistema de gerenciamento de usuários (quando os únicos tipos de conta disponíveis eram administrador e membro da equipe), todos os usuários foram trazidos para o novo sistema com permissões inalteradas. Como resultado, a maioria desses usuários possui **funções temporárias**.

Saiba mais sobre como [gerenciar funções temporárias](#managing-temp-roles).

<div id="get-roles-data-via-api" />

### Obter dados de funções via API

Através da <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/get_roles">Get roles API</Anchor>, você pode recuperar uma lista de funções atuais e seus atributos correspondentes específicos para sua conta.

<div id="manage-custom-roles" />

## Gerenciar funções personalizadas

<div id="creating-custom-roles" />

<Accordion title="Criar funções personalizadas">

* **Pré-requisito:** Apenas [proprietários da conta](#proprietário-da-conta) ou usuários com [acesso de administrador](#administrador) podem criar uma função personalizada.

**Para criar uma função personalizada:**

1. No painel esquerdo da aba **Funções**, na barra de pesquisa, clique em **+ Nova função personalizada**.
2. **Nome da função:** insira um nome para a nova função que você está criando.
   * **Atenção:** depois que você salvar uma função personalizada, o nome da função não pode ser editado.
   * **Recomendação:** crie um nome descritivo e facilmente identificável.
3. **Modelo de função:** como ponto de partida, selecione uma função predefinida que se aproxime das permissões que você deseja incluir na nova função personalizada.
4. Ajuste as configurações do modelo selecionado de acordo com os requisitos da sua função personalizada. Os níveis de permissão de todos os recursos editáveis são exibidos como botões. Clique nesses botões para alterar os níveis de permissão para o novo papel personalizado. (Certifique-se de rolar para baixo para ver a lista completa de recursos).
   * **Atenção:** recursos que não aparecem como botões não podem ser editados.
5. Após definir as permissões para todos os recursos relevantes, clique em **salvar função**.  
   A nova função personalizada é exibida no painel esquerdo e pode ser atribuída ao criar novos usuários ou editar usuários existentes.

</Accordion>

<div id="editing-custom-roles" />

<Accordion title="Editar funções personalizadas">

**Para editar uma função personalizada:**

1. no painel à esquerda da aba **funções**, clique no nome da função personalizada que você deseja editar.
2. Clique no ícone **editar** <Image alt="edit-icon.jpg" src="https://files.readme.io/d32f150cb5d0271c5504fb3c107e23f73e59c9a3be1630769ad309edf4e79ea0-31780971794321.jpg" width="25px" /> no canto superior direito da página. O painel à direita é alterado, permitindo a criação de uma nova função personalizada.
   * **Atenção:** o nome da função não pode ser editado. Para alterá-lo, você deve excluir a função e criar uma nova com um nome diferente.
3. Os níveis de permissão de todos os recursos editáveis são exibidos como botões. Clique nesses botões para alterar os níveis de permissão para o novo papel personalizado. (Certifique-se de rolar para baixo para ver a lista completa de recursos).
4. Quando você estiver satisfeito com todas as suas seleções, clique no botão **salvar função**.
5. Os níveis de permissão da função são alterados para todos os usuários novos e existentes.

<div id="important-1" />

> 🚧 **Importante!**
>
> Quaisquer alterações que você fizer em uma função personalizada são automaticamente aplicadas a **todos os usuários existentes** nessa função.

</Accordion>

<div id="deleting-custom-roles" />

<Accordion title="Excluir funções personalizadas">

**Para excluir uma função personalizada:**

1. No painel à esquerda da aba **funções**, clique no nome da função personalizada que você deseja excluir.
2. Clique no ícone **excluir** <Image alt="delete-icon.jpg" src="https://files.readme.io/87f206e21926af0836690be064a5af7cb3bce0007f0fc62301b2925701b1d9f9-31780971797265.jpg" width="24px" /> no canto superior direito da página.
3. Confirme que deseja excluir a função.
   * Uma função personalizada só pode ser excluída quando não há usuários atribuídos a ela. Se houver usuários atualmente atribuídos a uma função personalizada, atribua a esses usuários uma função diferente antes de eliminar a função personalizada.

</Accordion>

<div id="special-situations-and-additional-procedures" />

## Situações especiais e procedimentos adicionais

<div id="managing-temp-roles" />

<Accordion title="Gerenciar funções temporárias">

Se sua conta usou nosso sistema de gerenciamento de usuários anterior no passado, [**as funções temporárias**](/docs/user-management#funções-temporárias) foram atribuídas aos usuários existentes para garantir que eles fossem trazidos para o novo sistema com recursos inalterados.

* Os usuários com os mesmos recursos receberam a mesma função temporária.
* Use os recursos da aba [Funções](/docs/user-management#roles-tab) para revisar os recursos de cada função temporária e uma lista de usuários que está atualmente nela.

<div id="temp-role-limitations" />

#### Limitações da função temporária

As funções temporárias foram projetadas especificamente para permitir uma transição perfeita do nosso sistema anterior de gerenciamento de usuários. Como tal, eles estão disponíveis apenas em situações limitadas:

* As funções temporárias não podem ser atribuídas a outros usuários (sejam novos ou existentes).
* Um usuário com uma função temporária não pode receber uma função temporária diferente (embora você possa alterar os aplicativos, fontes de mídia e geolocalizações às quais ele tem acesso).
  * Observe que o acesso de um usuário a aplicativos futuros **não pode** ser alterado enquanto o usuário estiver em uma função temporária.
* Quando um usuário com uma função temporária é alterado para uma função pré-definida, ele não pode ser retornado para a função temporária atribuída anteriormente (ou para qualquer outra função temporária).
* Se o último usuário em uma função temporária for removido dela, a função não aparecerá mais na sua conta.

<div id="example-2" />

> 📄 **Exemplo**
>
> Sua conta já usou nosso sistema de gerenciamento de usuários anterior. Diana e Eduardo eram usuários existentes no momento em que sua conta foi movida para o novo sistema. Diana está agora na função Temporária 1, e Eduardo está na função Temporária 2.
>
> * Você contratou uma nova funcionária, Flávia. Você pode atribuir à Flávia qualquer uma das [funções predefinidas](/docs/user-management#funções-predefinidas). No entanto, você não pode atribuir a Flávia as funções Temporária 1 ou a Temporária 2.
> * A Diana não pode ser transferida da função temporária 1 para a função temporária 2. No entanto, você pode atribuir qualquer uma das funções predefinidas a ela. Você também pode alterar o acesso dela a aplicativos, fontes de mídia e geolocalizações conforme necessário.
> * Se você mover Diana da função Temporária 1 para a função Contabilidade, ela não poderá ser movida de volta para a função Temporária 1.
> * Se Diana foi a última usuária da função Temporária 1 quando a transferiu para a função Contabilidade, a função Temporária 1 deixará de aparecer na sua conta.

</Accordion>

<div id="dashboard-and-feature-availability-for-users-with-limited-media-sourcegeo-access" />

<Accordion title="Dashboard e disponibilidade de recursos para usuários com acesso limitado ao canal de mídia/geolocalização">

Os seguintes dashboards da AppsFlyer **não estão disponíveis** para usuários cujo acesso é limitado a canais de mídia e localizações específicos:

* Visão geral do SKAN
* Estúdio de conversão SKAN
* Os alertas do Protect360 são atualizados no horário UTC diário.
* Retenção
* People-based attribution
* Incrementalidade

Além disso, os seguintes recursos da AppsFlyer **não estão disponíveis** para esses usuários:

* Pivot
* Os links diretos universais do OneLink
* Regras de validação
* Audiences (indisponível para usuários com restrições de fontes de mídia; disponível para usuários com restrições de geolocalização)
* Informações do SDK
* Ingestão de gastos com anúncios
* ETL de custos

</Accordion>

<div id="combined-media-source-and-agency-access" />

<Accordion title="Acesso combinado à fonte de mídia e à agência">

Quando você concede a um usuário acesso a uma agência específica **e** a um canal de mídia específico, o acesso aos dados dele reflete apenas a sobreposição entre os dois. O usuário não vê todos os dados dessa agência em todas as fontes de mídia, nem todos os dados dessa fonte de mídia em todas as agências — apenas a parte em que ambas as permissões se sobrepõem.

<div id="example-3" />

> 📄 **Exemplo**
>
> Você concede a um usuário acesso à Agência B e à Fonte de Mídia A. A Agência B gerencia instalações de aplicativo provenientes de várias fontes de mídia, incluindo a Fonte de Mídia A. Esse usuário vê apenas as instalações da Fonte de Mídia A que a Agência B gerencia — não os dados da Agência B de outras fontes de mídia nem os dados da Fonte de Mídia A gerenciados por outras agências.

</Accordion>

<div id="changing-the-account-owner" />

<Accordion title="Mudar o proprietário da conta">

Como todos os administradores têm as mesmas permissões que o proprietário da conta, geralmente não é necessário alterar o proprietário da conta. Mas se você achar que precisa fazer essa alteração, siga as etapas abaixo.

<div id="important-2" />

> 🚧 **Importante!**
>
> Essa alteração deve ser concluída manualmente, seguindo essas etapas. Isso não pode ser feito a partir da página de **gerenciamento de usuários**.

<div id="1assign-a-team-member-the-admin-role" />

#### #1–Atribua a um membro da equipe a função de administrador

A alteração do proprietário da conta só pode ser solicitada por um usuário com a função de administrador. Portanto, recomenda-se:

* Atribua a um membro da equipe que possa concluir todas as etapas a função de **Admin** .
* O usuário deve ativar a conta (ou seja, fazer login pelo menos uma vez).

<div id="2send-an-email-request" />

#### #1– Enviar uma solicitação por e-mail

Para iniciar o processo de alteração do proprietário da conta, envie uma solicitação por e-mail para a AppsFlyer **a partir do e-mail do proprietário da conta atual.**

* Certifique-se de que este é o endereço de e-mail do proprietário da conta atual, conforme aparece na sua conta da AppsFlyer.
* Se o proprietário da conta atual tiver saído da sua empresa, peça à sua equipe de TI para permitir que você envie um e-mail do endereço dele.

Inclua as seguintes informações na sua solicitação:

| Para: | Seu CSM da AppsFlyer ou hello@appsflyer.com |
| --- | --- |
| CC: | E-mail do novo proprietário da conta |
| Assunto: | Solicitação para alterar o proprietário da conta para `{account name}` |
| Corpo: | Mensagem curta, incluindo o nome e o título do novo proprietário da conta |

Use este exemplo de e-mail como referência:

![account_owner_change_email.png](https://files.readme.io/eb10736386a7a8cfc274979a3aa933e23288c74d1b26c0f06d72005ceebafe06-31780969048081.png)

<div id="3next-steps" />

#### #2 – Próximas etapas

Assim que a alteração for processada, você receberá uma notificação por e-mail da AppsFlyer.

* Se você quiser que o proprietário da conta anterior continue usando sua conta da AppsFlyer, [crie um novo usuário](/docs/user-management#creating-users) para ele e atribua a ele uma nova função.
* As APIs que usam o token v2 não são afetadas pela alteração do proprietário da conta. <Anchor target="_blank" href="/marketers/pt/docs/managing-appsflyer-tokens">Saiba mais sobre como gerenciar tokens</Anchor>.

</Accordion>

<div id="troubleshooting-can-t-create-this-user" />

<Accordion title="Resolução de problemas: não é possível criar o usuário">

Se você receber a mensagem de erro *Não é possível criar esse usuário* ao inserir o endereço de e-mail de um novo usuário, isso geralmente significa que o e-mail já está associado a um usuário da AppsFlyer (na sua conta ou em uma conta diferente). Siga as etapas relevantes para sua situação:

Se o usuário estiver em sua conta:

* Verifique se o usuário ativou sua conta. Caso contrário, [reenvie o convite](/docs/user-management#resending-a-user-invitation), se necessário.
* Se o usuário ativou sua conta, peça que ele tente fazer login novamente usando o endereço de e-mail associado ao usuário. Aconselhe-os a seguir as etapas **Esqueci minha senha**, se necessário.

Se o e-mail do usuário for usado em uma conta diferente ou você não conseguir determinar a conta na qual o e-mail do usuário é usado, selecione uma das seguintes opções:

* Exclua-o da outra conta e adicione-o à sua (requer que você ou o usuário tenha as permissões necessárias na outra conta); ou
* Adicione-o à sua conta usando um endereço de e-mail diferente. Deve ser um endereço de e-mail válido no qual ele possa realmente receber um e-mail; ou
* Entre em contato com seu Customer Success Manager (CSM) ou envie um e-mail para nossa equipe de Engajamento do Cliente em [hello@appsflyer.com](mailto:hello@appsflyer.com).

</Accordion>

<div id="resending-a-user-invitation" />

<Accordion title="Reenviar um convite para o usuário">

Se um novo usuário não recebeu o [convite de ativação da conta](#ativação-do-usuário) ou se ele não o ativou em 48 horas, você pode reenviar o e-mail da seguinte maneira:

1. Na aba **Usuários**, clique no botão **Ações** <Image alt="actions_icon.png" src="https://files.readme.io/24ad987d1e77d9dfa8559a370733a7b62a6d86954ec1d552eac9c406445ed927-16162502616593.png" width="25px" /> no lado direito da linha do usuário.
   * Observe que o usuário ainda é mostrado com um ícone de envelope ![pending_invitation_icon.png](https://files.readme.io/68ac08ab6e52191a592350f82996f7ade9d181773d0bdbc6e2cb60315b60a8f2-16162502609553.png), indicando que ele ainda não ativou sua conta.
2. Selecione **Reenviar convite por e-mail** no menu.

</Accordion>

<div id="resetting-twofactor-authentication-2fa" />

<Accordion title="Resetar a autenticação de dois fatores (2FA) de um usuário">

Se sua conta usa autenticação de dois fatores, pode haver ocasiões em que você precise resetar as configurações de 2FA de um usuário. Faça o seguinte:

1. Em **usuários**, clique no botão **ações** <Image alt="actions_icon.png" src="https://files.readme.io/24ad987d1e77d9dfa8559a370733a7b62a6d86954ec1d552eac9c406445ed927-16162502616593.png" width="25px" /> no lado direito da linha do usuário.
2. Selecione **resetar autenticação de dois fatores** no menu.

**Atenção:** Um administrador pode resetar a autenticação de dois fatores de qualquer outro administrador, exceto a sua própria ou a do [proprietário da conta](#proprietário-da-conta). Para resetar a autenticação de dois fatores do proprietário da conta, entre em contato com a equipe de suporte da AppsFlyer.

</Accordion>

<div data-zendesk-anchors="background=vis%C3%A3o-geral h_01H9Q9007QP8YMPDVZ57N4M1HD=vis%C3%A3o-geral user-management-page=p%C3%A1gina-de-gest%C3%A3o-de-usu%C3%A1rios h_01H9Q9007QW1RD3MTTV01Q8QRE=p%C3%A1gina-de-gest%C3%A3o-de-usu%C3%A1rios h_01J6W88SQ45MA3AZ29K3WMW9PV=users-tab h_01J6W88SQ5B16Q897YMJ7ZNMQX=roles-tab managing-users=gerenciar-usu%C3%A1rios h_01H9Q9007QYSJZYZMP0C8NA98G=gerenciar-usu%C3%A1rios h_01H9Q9007QH3ME2P8PHC9DJBZV=creating-users user-details=detalhes-do-usu%C3%A1rio h_01HMP4EYM562HFSP80MQQ82B47=detalhes-do-usu%C3%A1rio h_01H9Q9007Q6SK4391P8C3A147N=importante role=cargo h_01HMP4Q56XP10343YFW17VX00W=cargo app-access=acesso-ao-aplicativo h_01HMP4RDXVRM3Z0WDCJD3P2W8S=acesso-ao-aplicativo data-access=acesso-de-dados h_01HMP4SW7RMESGDFNP1KFN7641=acesso-de-dados h_01HR6VBJHTZM48493B29FCWQT8=nota media-sources=canais-de-m%C3%ADdia h_01HRPRS4BHX2AMR9W4FNGE0N1P=canais-de-m%C3%ADdia 01HRPRSF0F8ENJ9ZAE1ZDTMAMB=nota-1 geos=geolocaliza%C3%A7%C3%A3o h_01HRPRVXYFX4P2ZG0H5HPNF2AG=geolocaliza%C3%A7%C3%A3o user-activation=ativa%C3%A7%C3%A3o-do-usu%C3%A1rio h_01HFRCWNR8T5J990TV68K6B45T=ativa%C3%A7%C3%A3o-do-usu%C3%A1rio h_01HFRFRQXD1RD66EBRQH0T7Q78=nota-2 01HFRF6SENRY51A4ZAQJTMTDA3=multiple-accounts log-in-to-multiple-accounts=login-em-mais-de-uma-conta h_01J2GN6ZA29SFC12HR4ZVBDFDT=login-em-mais-de-uma-conta h_01M2ZBMHB9P3FEAFDA637ZH4MC=importante-1 supported-accounts-and-users=contas-e-usu%C3%A1rios-dispon%C3%ADveis h_01H9Z7XXE0CKRSE191ZN017MGE=contas-e-usu%C3%A1rios-dispon%C3%ADveis limitations-on-adding-users-to-multiple-accounts=limita%C3%A7%C3%B5es-para-adicionar-usu%C3%A1rios-a-v%C3%A1rias-contas 01J2GMV7ZYV5G0Q6C18RRY1TY0=limita%C3%A7%C3%B5es-para-adicionar-usu%C3%A1rios-a-v%C3%A1rias-contas add-users-to-multiple-accounts=adicione-usu%C3%A1rios-a-v%C3%A1rias-contas h_01H9G1MP3Z7VCQQ8ZSQDGSWPC3=adicione-usu%C3%A1rios-a-v%C3%A1rias-contas h_01H9Q9007RTMXVRMR4RM6J80CW=editing-users individual-editing=edi%C3%A7%C3%A3o-individual h_01H9Q9007R3QW4AYRJBTF0X7B9=edi%C3%A7%C3%A3o-individual multiuser-editing=edi%C3%A7%C3%A3o-multiusu%C3%A1rio h_01H9Q9007R4JQPKQS2HVB251GH=edi%C3%A7%C3%A3o-multiusu%C3%A1rio h_01H9Q9007R9M9YDMJ2YYNZDW3D=nota-3 h_01H9Q9007RAFXB899YK6CADD9R=exemplo h_01H9Q9007RF8QKS7YBZ1GRXVCF=deleting-users h_01HGTR4NEBYJZTW4BA5V9JJX5X=nota-4 h_01HGTK2664A0R2RBJM37EYWNZG=to-delete-users manage-users-in-bulk-via-api=gerenciar-usu%C3%A1rios-em-massa-atrav%C3%A9s-da-api h_01HYASD07FG0HGX22FTHEQ9APP=gerenciar-usu%C3%A1rios-em-massa-atrav%C3%A9s-da-api more-about-roles=gerenciar-fun%C3%A7%C3%B5es h_01H9Q9007Q8CMR2RD6E4KN26YE=gerenciar-fun%C3%A7%C3%B5es predefined-roles=fun%C3%A7%C3%B5es-predefinidas h_01H9Q9007Q28D43B6JRP71NDQM=fun%C3%A7%C3%B5es-predefinidas h_01J6VZ7ANV3JHJZ5EVBF1BY585=nota-5 h_01H9Q9007QXSGG375PR2SCS7QS=exemplo-1 admin%E2%80%94a-special-role=administrador h_01H9Q9007Q4A6KETAAGAWEPQQ9=administrador access=acesso h_01HF8N2Z8ZP3HV06XJPMQ19DTK=acesso manage-tokens=gerenciar-tokens h_01HV1F5S0FE083B73P8MEYX4FM=gerenciar-tokens role-duplication=duplicar-fun%C3%A7%C3%B5es h_01HF8N6DKWYKMBE35QKKB55KEM=duplicar-fun%C3%A7%C3%B5es invite-new-partners-to-appsflyer=convide-novos-parceiros-para-a-appsflyer h_01HVK8EB3SMC09VD8TJND9YWCD=convide-novos-parceiros-para-a-appsflyer account-owner=propriet%C3%A1rio-da-conta h_01HF8N69VYE3ZJVFW1ENC0XA62=propriet%C3%A1rio-da-conta custom-roles=fun%C3%A7%C3%B5es-personalizadas h_01H9Q9007QZ7F2TX8B9D1TNYPN=fun%C3%A7%C3%B5es-personalizadas temp-roles=fun%C3%A7%C3%B5es-tempor%C3%A1rias h_01H9Q9007QE8YT1DNRPNTFQWYH=fun%C3%A7%C3%B5es-tempor%C3%A1rias get-roles-data-via-api=obter-dados-de-fun%C3%A7%C3%B5es-via-api h_01J6VZ2XP6HM6NJ2TB5DJXD6SA=obter-dados-de-fun%C3%A7%C3%B5es-via-api managing-custom-roles=gerenciar-fun%C3%A7%C3%B5es-personalizadas h_01H9Q9007RQHHNHZ3M38E88YPW=gerenciar-fun%C3%A7%C3%B5es-personalizadas h_01H9Q9007RYZD19CFNSM60EARZ=creating-custom-roles h_01H9Q9007R6E6JGD8BC2WY8G3G=editing-custom-roles h_01H9Q9007RANMZP4T6S8R6WA1B=importante-2 h_01H9Q9007R16190B6RB884FY61=deleting-custom-roles special-situations-and-additional-procedures=situa%C3%A7%C3%B5es-especiais-e-procedimentos-adicionais h_01H9Q9007RSWFVAZQ5DNVNN7T2=situa%C3%A7%C3%B5es-especiais-e-procedimentos-adicionais h_01H9Q9007RNZ28128XDB76ZVZC=managing-temp-roles temp-role-limitations=limita%C3%A7%C3%B5es-da-fun%C3%A7%C3%A3o-tempor%C3%A1ria h_01H9Q9007RJ0CQRGEYNEQJ2QR5=limita%C3%A7%C3%B5es-da-fun%C3%A7%C3%A3o-tempor%C3%A1ria h_01H9Q9007RHBYD2B6PHQRD7TWV=exemplo-2 h_01H9Q9007RRY6QERXQ0C4FSYCN=dashboard-and-feature-availability-for-users-with-limited-media-sourcegeo-access h_01K7B3N5G8R2M4X9Y1D6W0T3PQ=combined-media-source-and-agency-access h_01K7B3N7H9S3N5Y0Z2E7X1U4RT=exemplo-3 h_01H9Q9007R221KXA7DFTXJY0PE=changing-the-account-owner h_01H9Q9007RR4M8V599A19B2M0F=importante-3 1%E2%80%93send-an-email-request=1atribua-a-um-membro-da-equipe-a-fun%C3%A7%C3%A3o-de-administrador h_01H9Q9007RSA5406WXCB1E4JRK=1atribua-a-um-membro-da-equipe-a-fun%C3%A7%C3%A3o-de-administrador h_01K5P1G80QACK6YMKX4AGJA5ZK=1-enviar-uma-solicita%C3%A7%C3%A3o-por-e-mail 2%E2%80%93next-steps=2--pr%C3%B3ximas-etapas h_01H9Q9007RZ2X9RAY8067SZETF=2--pr%C3%B3ximas-etapas troubleshooting-can%E2%80%99t-create-this-user=troubleshooting-can-t-create-this-user h_01H9Q9007RR4VYEPGT90MEHV3T=troubleshooting-can-t-create-this-user h_01H9Q9007R11BQWQZC66X5FV0N=resending-a-user-invitation h_01H9Q9007R72FAH89XW58MWCXT=resetting-twofactor-authentication-2fa" />
