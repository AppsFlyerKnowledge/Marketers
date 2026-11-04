---
title: Migrar do Firebase Dynamic Links para a AppsFlyer
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
  created_at: '2023-06-19T09:27:37Z'
  edited_at: '2026-08-22T00:17:16Z'
  id: 16282289097105
  locale: pt
  section: Marketer onboarding
  section_id: 6550866490129
  url: https://support.appsflyer.com/hc/pt/articles/16282289097105
---
> **Visão geral:** Faça a transição do Firebase Dynamic Links para a AppsFlyer de forma simples usando nosso guia passo a passo de migração

## ![53375 imagem da KB de migração do Firebase.png](https://files.readme.io/b5340a5b30c160bca2b420052fd60b23f4bfe0de6d2868f91ad4342bee36c7df-30063560499345.png)

<div id="about-the-migration" />

## Sobre a migração

O <Anchor target="_blank" href="https://firebase.google.com/docs/dynamic-links">Firebase Dynamic Links</Anchor> do Google será descontinuado em 25 de agosto de 2025. A partir dessa data, todos os links veiculados pelo Firebase Dynamic Links (tanto os hospedados em domínios personalizados quanto os do subdomínio page.link) deixarão de funcionar, e a criação de novos links será desativada. Se você usa o Firebase Dynamic Links, é essencial tomar medidas proativas o quanto antes para migrar seus links para outro lugar e evitar interrupções nas jornadas dos usuários das suas campanhas.

O OneLink da AppsFlyer permite criar facilmente links com atribuição, redirecionamento e recursos de deep linking em mídia própria ou paga, independentemente do dispositivo, sistema operacional, canal ou plataforma. Faça parceria com a AppsFlyer para criar jornadas contextuais e personalizadas que levem os usuários ao seu app e maximizem a conversão e a receita. Siga as instruções abaixo para começar a migrar seus links do Firebase Dynamic Links para a AppsFlyer.

<div id="migrate-from-firebase-to-appsflyer" />

## Como migrar do Firebase para a AppsFlyer

Com o <Anchor target="_blank" href="https://firebase.google.com/support/dynamic-links-faq">anúncio do Google</Anchor> de que encerrará o Firebase Dynamic Links, agora é a hora de migrar para a AppsFlyer - é simpes.

**Para migrar para a AppsFlyer:**

**Pré-requisitos**

Antes de começar, você precisará de:

* Seus links dinâmicos do Firebase
* Seu desenvolvedor de aplicativos

<div id="step-1-create-an-appsflyer-account" />

<Accordion title="1. Crie uma conta">

* <Anchor target="_blank" href="https://www.appsflyer.com/get-started/">Crie uma conta na AppsFlyer</Anchor>.
* Adicione usuários de conta com as permissões adequadas

</Accordion>

<div id="step-2-add-your-app" />

<Accordion title="2. Adicione o aplicativo">

* <Anchor target="_blank" href="/marketers/pt/docs/adding-an-app-to-appsflyer">Adicione o aplicativo</Anchor> à AppsFlyer
* [Opcional] Altere a  <Anchor target="_blank" href="/marketers/pt/docs/set-up-re-attribution-window">janela de reatribuição</Anchor>  padrão de 90 dias para alinhar  com a sua definição de usuários ativos.

![adicionar](https://files.readme.io/7f7bab2277d0f45434618d28714c727ccbb9e414192b765dd22551bcbd5b0a37-16950840602769.png)

</Accordion>

<div id="step-3-create-a-onelink-template" />

<Accordion title="3. Configure o template do OneLink">

**Você e o desenvolvedor do seu aplicativo são necessários para esta etapa**.

É necessário um template para criar links e experiências do usuário final. Isso forma a base da lógica de redirecionamento para todos os links do OneLink que você criar para suas várias campanhas de marketing.

* <Anchor target="_blank" href="/marketers/pt/docs/create-a-onelink-template#como-criar-templates-do-onelink">Crie um template do OneLink</Anchor>
  * Você deve ser um usuário administrador da AppsFlyer ou ter <Anchor target="_blank" href="/marketers/pt/docs/user-management">permissão para adicionar/editar templates do OneLink</Anchor>

</Accordion>

<div id="step-4-set-up-the-appsflyer-sdk" />

<Accordion title="4. Configure o SDK">

O profissional de marketing deve ser um usuário administrador da AppsFlyer, ou ter permissão para adicionar/editar templates do OneLink.

O SDK da AppsFlyer integrado ao aplicativo é a conexão entre o aplicativo e a plataforma da AppsFlyer. Ele oferece:

* Deep linking - O SDK permite a implementação do unified deep linking (UDL)
* Atribuição - o SDK relata instalações de aplicativos, abertura de aplicativos, eventos in-app e outros.

Integre o SDK da AppsFlyer em seu aplicativo usando as etapas abaixo.

<div id="appsflyer-sdk-integration-steps" />

#### Etapas da Integração do SDK da AppsFlyer

1. Integre o SDK da AppsFlyer ao aplicativo.  
   Consulte os guias de integração do SDK para <Anchor target="_blank" href="/marketers/pt/docs/sdk-integration-overview">Android</Anchor> e <Anchor target="_blank" href="/marketers/pt/docs/sdk-integration-overview">iOS</Anchor>.
2. Mapeie os eventos in-app que você quiser registrar usando os esquemas da AppsFlyer.  
   Isso pode ser feito via <Anchor target="_blank" href="/marketers/pt/docs/in-app-events-overview">SDK</Anchor> ou <Anchor target="_blank" href="/marketers/pt/docs/server-to-server-events-api-for-mobile-s2s-mobile">S2S</Anchor>.
3. Lidar com o SDK do Firebase.  
   Você pode fazer isso imediatamente e mudar exclusivamente para a AppsFlyer, ou executar os dois SDKs simultaneamente por algumas semanas. Veja mais detalhes sobre essas opções na tabela abaixo.

| Opção | O que acontece em seguida?  <br /> lançamento da versão atualizada do aplicativo | Impacto |
| --- | --- | --- |
| Remover o SDK do Firebase (recomendado) | Apenas a AppsFlyer registra novas instalações e a atualização de usuários.  <br />O concorrente ainda mostra eventos realizados pelos usuários, até que os usuários também atualizem seu aplicativo. | <ul><li>Transição rápida</li><li>Sem atribuição dupla</li><li>Permite ver se ainda tem versões de aplicações com o SDK do Firebase</li></ul> |
| Manter o SDK do Firebase durante um período de transição | A AppsFlyer e o concorrente atribuem novas instalações e registram eventos. Posteriormente, remove o SDK do Firebase. | <ul><li>A validação de dados é possível. Ou seja, você pode comparar dados da AppsFlyer e do outro fornecedor.</li><li>Atribuição dupla, que pode causar cobranças duplas com ad networks.</li><li>Maior carga de trabalho.</li></ul> |

4. Depois que todas as outras tarefas no escopo do trabalho forem concluídas, atualize a versão do aplicativo com o SDK da AppsFlyer para o mercado. Novos usuários são atribuídos pela AppsFlyer.   
   **Observação:**
   * Certifique-se de atualizar o aplicativo para iOS, Google Play e outros mercados relevantes fora da loja Android.
   * Seu aplicativo Android pode existir em sites de APK não oficiais, mesmo que você não os conheça (pesquise na internet o nome do pacote do seu aplicativo para saber). Os sites de APK levam algum tempo para atualizar para a versão mais recente, portanto podem trazer usuários orgânicos, que instalam versões antigas sem o SDK da AppsFlyer.
   * Os lançamentos de atualizações do aplicativo nas app stores podem levar alguns dias para serem totalmente concluídos. Os usuários que fizerem a instalação durante essa fase ainda podem obter a versão anterior.

</Accordion>

<div id="step-5-understand-parameter-mapping" />

<Accordion title="5. Compreender o mapeamento de parâmetros">

O profissional de marketing deve ser um usuário administrador da AppsFlyer, ou ter permissão para adicionar/editar templates do OneLink.

Entenda como os parâmetros do Firebase Dynamic Links são mapeados para os parâmetros correspondentes da AppsFlyer.

Um mapeamento correto e a compreensão dos parâmetros correspondentes garantirão que seus links obtêm os mesmos resultados.

A tabela abaixo lista todos os parâmetros do Firebase e os parâmetros correspondentes da AppsFlyer.

Use esta tabela como referência para todos os parâmetros que você usa atualmente ao migrar para a AppsFlyer.

<div id="note" />

> 📘 **Observação:**
>
> Se um parâmetro do Firebase não estiver listado, é porque a AppsFlyer cobre isso na configuração do template do OneLink sem que você precise colocar um parâmetro nos seus links.

<table><thead><tr><th>Agrupamento</th><th>Firebase</th><th>A AppsFlyer</th><th>Descrição</th></tr></thead><tbody><tr><td>Parâmetros mobile</td><td>link</td><td><ul><li>af_dp</li><li>deep_link_value</li></ul></td><td><ul><li> Esquema de URI usado como um método de fallback para inicializar aplicativos iOS e Android.</li><li> O <strong>deep_link_value</strong> é o nome do valor para o conteúdo in-app específico para o qual os usuários serão direcionados.</li></ul></td></tr><tr><td> <br/>Parâmetros do Android</td><td>afl</td><td>af_android_url</td><td>Permite redirecionar usuários do Android para uma página web personalizada.</td></tr><tr><td rowspan="2">Parâmetros da API<br/><br/> </td><td>ifl</td><td>af_ios_url</td><td>Permite redirecionar usuários do iOS para uma página web personalizada.</td></tr><tr><td>efr</td><td>af_force_deeplink</td><td>Usado para forçar um aplicativo iOS a abrir usando o esquema de URI af_dp. Sem isto, o aplicativo não será aberto usando o esquema de URI.</td></tr><tr><td>URL de outra plataforma</td><td>ofl</td><td>af_web_dp</td><td>Permite redirecionar usuários de desktop para uma página web personalizada.</td></tr><tr><td rowspan="3"> <br/><span>Tags de mídia social</span><br/><br/><br/> </td><td>st</td><td>af_og_title</td><td>Usado para personalizar o título do conteúdo compartilhado nas mídias sociais.</td></tr><tr><td>sd</td><td>af_og_description</td><td>Usado para personalizar a descrição de conteúdo compartilhado nas mídias sociais.</td></tr><tr><td>si</td><td>af_og_image</td><td>Usado para personalizar a imagem de conteúdo compartilhado nas mídias sociais.</td></tr><tr><td rowspan="5"><p>Parâmetros de análise <br/><br/><br/><br/> </p></td><td>utm_source</td><td>pid</td><td>Fonte de mídia</td></tr><tr><td>utm_medium</td><td>af_canal</td><td>Identifica os canais de origem de mídia onde seus anúncios são distribuídos.</td></tr><tr><td>utm_campaign</td><td>C</td><td>Nome da campanha</td></tr><tr><td>utm_term</td><td>af_keywords</td><td>Lista de palavras-chave para campanhas que usam texto para target.</td></tr><tr><td>utm_content</td><td>af_adset</td><td>Coleção de anúncios associados a uma campanha.</td></tr></tbody></table>

</Accordion>

<div id="step-6-create-onelink-links-with-mapped-parameters" />

<Accordion title="Passo 6: Passo 6: Criar links do OneLink com parâmetros mapeados">

Usando seus parâmetros mapeados, é possível criar links OneLink no seu template do OneLink.

Os links podem ser criados usando o <Anchor target="_blank" href="/marketers/pt/docs/onelink-guide">painel da AppsFlyer</Anchor>, <Anchor target="_blank" href="/marketers/pt/docs/perform-onelink-bulk-actions-via-csv">em massa</Anchor> através de um CSV, programaticamente com nossa <Anchor target="_blank" href="/marketers/pt/docs/use-onelink-api-to-create-links-in-large-scale-campaigns">API OneLink</Anchor>, no <Anchor target="_blank" href="/marketers/pt/docs/user-invite-attribution">SDK</Anchor> ou através de <Anchor target="_blank" href="/marketers/pt/docs/understand-onelink-short-vs-long-urls">links longos</Anchor>.

Use a tabela a seguir para determinar o método que melhor se adequa à sua necessidade.

| Firebase | A AppsFlyer | Use se | Observações |
| --- | --- | --- | --- |
| Console do Firebase | <Anchor target="_blank" href="/marketers/pt/docs/onelink-guide">Página de gerenciamento do OneLink</Anchor> | Você quer criar links OneLink um a um. Desta forma, você pode usar todas as funcionalidades e possibilidades do OneLink |  |
| API do Dynamic Link Builder | <Anchor target="_blank" href="/marketers/pt/docs/user-invite-attribution">SDK</Anchor> | Você quer criar links in-app gerados programaticamente para usos como convites e referências de usuários | <ul><li>Requer um desenvolvedor iOS ou Android</li></ul> |
| API REST do Firebase | <Anchor target="_blank" href="/marketers/pt/docs/use-onelink-api-to-create-links-in-large-scale-campaigns">API OneLink</Anchor> | Você quer criar links de forma programática fora do aplicativo mobile | <ul><li>Requer um desenvolvedor</li><li>Não disponível no plano gratuito</li></ul> |
| Criação manual de links | <Anchor target="_blank" href="/marketers/pt/docs/understand-onelink-short-vs-long-urls">Links longos</Anchor> | Você quer criar manualmente o link com os seus parâmetros de consulta. Use se você não precisa de links curtos. Por exemplo, se o link estiver atrás de um botão ou de um banner |  |
|  | <Anchor target="_blank" href="/marketers/pt/docs/perform-onelink-bulk-actions-via-csv">Links em massa</Anchor> | Você quer migrar todos os seus links dinâmicos do Firebase em massa para a AppsFlyer.<br /><br />Esta opção é recomendada para passar rapidamente por todos os seus links sem quaisquer erros | <ul><li>Requer uma etapa prévia de [mapeamento das chaves e valores dos parâmetros do link de acordo com os parâmetros correspondentes do Firebase](/docs/migrate-from-firebase-dynamic-links-to-appsflyer#map-parameters)</li><li>Não disponível no plano gratuito.</li></ul> |
|  | <Anchor target="_blank" href="/marketers/pt/docs/smart-banners-mobile-web-to-app-for-marketers">Smart Banner</Anchor> | Página de links em massa |  |
|  | <Anchor target="_blank" href="/marketers/pt/docs/set-up-smart-script-to-convert-web-visitors">Smart Script</Anchor> | Se você quiser construir um link longo dinamicamente em uma página web para uma experiência web-to-app |  |

</Accordion>

<div id="see-also" />

> 📄 **Veja também**
>
> * <Anchor target="_blank" href="/marketers/pt/docs/brand-onelink-with-your-domain">Domínios de marca</Anchor>
> * <Anchor target="_blank" href="/marketers/pt/docs/using-firebase-and-google-tag-manager-with-appsflyer-overview">Usando Firebase e Google Tag Manager com a AppsFlyer—Visão geral</Anchor>

<div data-zendesk-anchors="overview=sobre-a-migra%C3%A7%C3%A3o h_01J7ZPPQ340PNQ70FZAQY4GBZ1=sobre-a-migra%C3%A7%C3%A3o 01H8K961JHRXNQHBVN930XW70Q=sobre-a-migra%C3%A7%C3%A3o how-to-migrate-from-firebase-to-appsflyer=como-migrar-do-firebase-para-a-appsflyer 01H8K961JHCK0Z4GTTHCAKF98E=como-migrar-do-firebase-para-a-appsflyer h_01J5QWWGWGDBEF8RY3DZ5XAN3G=step-1-create-an-appsflyer-account h_01J5QWWGWGN17673GYFZWPNKQR=step-2-add-your-app h_01J5QWWGWGKJPRCG9N93B8KBYW=step-3-create-a-onelink-template h_01J5QWWGWGCQFHBQ9EC0QTPF4S=step-4-set-up-the-appsflyer-sdk appsflyer-sdk-integration-steps=etapas-da-integra%C3%A7%C3%A3o-do-sdk-da-appsflyer h_01J5QXST2K890DV7QS6S9K3A01=etapas-da-integra%C3%A7%C3%A3o-do-sdk-da-appsflyer h_01J5QWWGWGPRF5DRMMQ14BJCFA=step-5-understand-parameter-mapping 01H8K961JHBXVKXM0XQYY605EQ=observa%C3%A7%C3%A3o h_01J5QWWGWG3ST19WDRZXN8FK8Q=step-6-create-onelink-links-with-mapped-parameters h_01HE7SZPKKQETH260G45V0D0HN=veja-tamb%C3%A9m" />
