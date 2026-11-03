---
title: Configure sua domain redirect allowlist
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
  created_at: '2024-05-15T11:31:00Z'
  edited_at: '2026-08-18T00:17:31Z'
  id: 25068636064529
  locale: pt
  section: Account security
  section_id: 6551173202065
  url: https://support.appsflyer.com/hc/pt/articles/25068636064529
---
> **Em resumo:** Configure uma lista de permissões de redirecionamento de domínio (domain redirect allowlist) para garantir que os usuários sejam redirecionados para domínios verificados e confiáveis, protegendo seus dados e a integridade da sua marca.

## <Image alt="Main redirect allowlist image.png" src="https://files.readme.io/a13b1c4641f4b265ef93ba9b65c57b0a7891336d6f6c21e94dd2ff5d83b948d6-30258741325713.png" width="1340px" />Informações sobre a redirect allowlist

Use a redirect allowlist para definir uma lista de domínios raiz e subdomínios específicos para os quais o redirecionamento de links é permitido, protegendo seus links contra redirecionamentos não autorizados, ataques de phishing e fraudes. Depois que sua allowlist estiver ativa, os links criados por meio da AppsFlyer redirecionarão os usuários apenas para URLs da web cujos domínios estão listados na allowlist. Caso contrário, os usuários serão direcionados para a loja de aplicativos. A redirect allowlist se aplica ao <Anchor target="_blank" href="/marketers/pt/docs/onelink-guide">OneLink</Anchor>, links de atribuição de plataforma única por meio da <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#attribution-link-tab">integração de parceiros</Anchor> e <Anchor target="_blank" href="/marketers/pt/docs/ctv-pc-and-console-platform-direct-attribution-links">links de atribuição direta</Anchor> para plataformas de CTV, PC e console. A redirect allowlist (e redirecionamento web personalizado) está disponível para assinantes dos planos Growth e Enterprise. Para evitar abuso, os assinantes do plano Zero devem ter um cartão de crédito cadastrado (não será cobrado).

## Configure sua redirect allowlist

Você pode configurar sua allowlist manualmente ou via arquivo CSV. Antes da configuração, verifique sua lista de domínios confiáveis ​​com sua equipe de segurança.

<div id="manual-setup" />

<Accordion title="Configuração manual">

**Para configurar manualmente:**

1. Na barra superior, abra o menu da conta (menu suspenso no endereço de e-mail) > **Central de segurança.**

![from account click security center Cropped.jpg](https://files.readme.io/4ee3279e382e97817a6b977f50bff7054868f03c22186ed2bd79d712e2316ad4-25381243839377.jpg)

2. Em **Redirect allowlist** , clique em **gerenciar redirect allowlist**.

<Image alt="Manage redirect allowlist with arrow.jpg" src="https://files.readme.io/e9cd8c263eb618b86d3c10b1d9fc367390dfd1f9b6cc12afd7ac5f37411ba25c-25644439175313.jpg" width="549px" />  

A página **Redirect allowlist** é aberta.

3. Na aba **Manual**, insira um domínio raiz ou subdomínio no campo **Nome de domínio** e clique em **Adicionar domínio à lista**.

<Image alt="Manually add domains.jpg" src="https://files.readme.io/95b37db2064ddba8c787d2dd5ac5ab2aa7698605f5c6eb3b4a59dd6324dee355-25103405228689.jpg" width="403px" />

* Use apenas letras, números, hífens e pontos.
* O domínio deve começar e terminar com uma letra ou número e pode ter até 253 caracteres.
* Não adicione prefixos, como https://.

Veja também as [características e limitações](/docs/set-up-your-domain-redirect-allowlist#características-e-limitações) da allowlist.

Os domínios adicionados serão exibidos no lado direito.

4. Clique em **Salvar lista**.

Feito isso, a lista será aplicada aos cliques em cerca de uma hora.

</Accordion>

<div id="setup-via-csv-file" />

<Accordion title="Configuração via arquivo CSV">

**Para configurar via upload de arquivo CSV:**

1. Na barra superior, abra o menu da conta (menu suspenso no endereço de e-mail) > **Central de segurança.**  

![from account click security center Cropped.jpg](https://files.readme.io/4ee3279e382e97817a6b977f50bff7054868f03c22186ed2bd79d712e2316ad4-25381243839377.jpg)

2. Em **Redirect allowlist** , clique em **gerenciar redirect allowlist**.  
<Image alt="Manage redirect allowlist with arrow.jpg" src="https://files.readme.io/e9cd8c263eb618b86d3c10b1d9fc367390dfd1f9b6cc12afd7ac5f37411ba25c-25644439175313.jpg" width="530px" />  

A página **Redirect allowlist** é aberta.

3. Clique na aba **Arquivo CSV** e siga as **instruções do arquivo** para criar um novo arquivo contendo sua lista de domínios.  
![CSV file upload.jpg](https://files.readme.io/2be73080048545f79e102e6f48df0db956e6739f156153c172c4fef5a2ea339f-25381979219345.jpg)

4. Faça o upload o arquivo CSV no campo de correspondente.

* Assim que o arquivo for carregado, ele será analisado e os valores serão validados.
* Os valores válidos serão adicionados automaticamente e exibidos no lado direito.
* Valores inválidos não serão adicionados. As informações sobre valores inválidos serão exibidas na seção **Status do upload** para que você possa realizar a seguinte ação: revisar ou corrigir os valores e fazer o upload novamente. Veja as [características e limitações](/docs/set-up-your-domain-redirect-allowlist#características-e-limitações) da allowlist para mais detalhes.

5. Clique em **Salvar lista**.

Depois de salva, a redirect allowlist atualizada será aplicada aos cliques em cerca de uma hora.

</Accordion>

<div id="edit-the-redirect-allowlist" />

<Accordion title="Editar a redirect allowlist">

Você pode adicionar ou excluir domínios a qualquer momento.

**Para excluir um domínio:**

1. No lado direito, passe o mouse sobre o domínio que deseja excluir e um ícone de exclusão aparecerá.
2. Clique no ícone excluir.
3. Clique em **Salvar lista** para salvar a alteração.

**Atenção:** Depois de salva, a redirect allowlist atualizada será aplicada aos cliques em cerca de uma hora.

</Accordion>

## Características e limitações

| Caraterística | Observações |
| --- | --- |
| Configuração | <ul><li>A redirect allowlist pode ser acessada e gerenciada pelas funções "Admin" e "Segurança".</li><li>A redirect allowlist está disponível no nível da conta e se aplica a todos os aplicativos da conta e a todos os links da AppsFlyer.</li><li>A redirect allowlist não estará disponível para membros da equipe associados a várias contas se uma conta não tiver uma forma de pagamento.</li><li>Antes da ativação, avise seus colegas de trabalho e as partes interessadas que gerenciam a criação de links da AppsFlyer sobre a aplicação da redirect allowlist e os domínios de redirecionamento permitidos.</li></ul> |
| Aplicabilidade | <ul><li>A allowlist afeta **todos os links criados via AppsFlyer**, seja com o <Anchor target="_blank" href="/marketers/pt/docs/onelink-guide">OneLink</Anchor>, links de atribuição de plataforma única via <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#attribution-link-tab">integração de parceiros</Anchor> ou <Anchor target="_blank" href="/marketers/pt/docs/ctv-pc-and-console-platform-direct-attribution-links">links de atribuição direta</Anchor> para plataformas de CTV, PC e console, independentemente de terem sido criados antes ou depois da ativação da lista.</li><li>Inclua os domínios de qualquer URL definida como um valor na configuração de redirecionamento especificada aqui, seja um site/landing page personalizada, o Google Play/App Store ou outro site da loja de aplicativos. A allowlist oferece suporte e protege redirecionamentos para:<ul><li>Parâmetros de link:<ul><li>`af_r`</li><li>`af_web_dp`</li><li>`af_ios_url`</li><li>`af_android_url`</li></ul></li><li>Configuração de redirecionamento de template do OneLink para iOS, Android e Desktop</li><li>`af_dp` com um valor de URL da web, no entanto, esse não é um tipo de valor recomendado. Esse parâmetro tem como objetivo preencher um <Anchor target="_blank" href="/marketers/pt/docs/about-link-structure-and-parameters#af_dp">esquema URI</Anchor> para abrir seu aplicativo.</li></ul></li><li>**As prévias de link podem mostrar conteúdo alternativo:** quando a AppsFlyer gera uma prévia social para um link, ela valida os parâmetros de redirecionamento do link em relação à sua lista de permissões de redirecionamento. Se não estiver, a AppsFlyer não buscará uma prévia dessa página e, em vez disso, mostrará uma prévia alternativa.</li></ul> |
| Domínios | <ul><li>A allowlist deve incluir pelo menos um domínio.</li><li>Somente domínios ou subdomínios raiz são permitidos, e não caminhos específicos. Não inclua protocolos "https://" ou "http://" no valor.</li><li>Ao adicionar um domínio raiz, ele se aplicará a todos os subdomínios dentro do domínio raiz.<br />Por exemplo, se o domínio raiz "website.com" for adicionado, ele também cobrirá "abc.website.com" e "xyz.website.com".</li><li>O redirecionamento é permitido apenas para domínios que podem ser publicamente acessados.</li><li>Não inclua domínios da AppsFlyer (por exemplo, onelink.me, app.appsflyer.com) ou outros domínios que tenham seu próprio mecanismo de redirecionamento (por exemplo, bit.ly) para fortalecer a previsibilidade do redirecionamento de seus links.</li><li>Até 100 domínios/subdomínios podem ser adicionados à allowlist. Você pode visualizar o número de domínios já adicionados acessando a redirect allowlist, onde o número de domínios é indicado.</li></ul> |
| Redirecionamento | Se você não tiver certeza se um domínio é permitido:<br /><br />Revise a allowlist para garantir que ele esteja incluído.<br /><br />Ou<br /><br />Use a ferramenta de <Anchor target="_blank" href="/marketers/pt/docs/discover-your-campaign-link-parameters-and-behavior">descoberta de links</Anchor>. Quando um link é inserido, um alerta aparece na coluna **parâmetros** (em **redirecionamento**) se um domínio não estiver na allowlist. |

<div data-zendesk-anchors="overview=informa%C3%A7%C3%B5es-sobre-a-redirect-allowlist h_01HYTJSH4YMAJ3CV88KZ9JD9XR=informa%C3%A7%C3%B5es-sobre-a-redirect-allowlist set-up-your-redirect-allowlist=configure-sua-redirect-allowlist h_01HY0BNRBEN91348744YME42SW=configure-sua-redirect-allowlist h_01HY04JEK8J3664HE8J9783S61=manual-setup h_01HY04JEK8Y51EG3H6WFKHYYH4=setup-via-csv-file h_01HY04JEK840Q4DZ2SRMTB7HRE=edit-the-redirect-allowlist traits-and-limitations=caracter%C3%ADsticas-e-limita%C3%A7%C3%B5es h_01J6S6HS0H0M6GQ81WGZ3XT0P9=caracter%C3%ADsticas-e-limita%C3%A7%C3%B5es" />
