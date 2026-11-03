---
title: Otimização de criativos — integrações de parceiros
metadata:
  keywords:
    - Premium
    - Marketers
    - Creative Optimization
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-omer-katzburg
    - Marketers
    - Creative Optimization
  created_at: '2023-09-14T13:52:36Z'
  edited_at: '2026-08-19T00:03:20Z'
  id: 18565403047569
  locale: pt
  section: Creative Optimization
  section_id: 4419063475217
  url: https://support.appsflyer.com/hc/pt/articles/18565403047569
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **Visão geral:** configure integrações de parceiros para importar automaticamente todos os seus dados de criativos para a ferramenta de otimização de criativos.

![Creative integrations New.jpg](https://files.readme.io/2bfead93dbaac902956ea4379e3f360120d59e7454be354c567b2f182382ab2d-20130430776337.jpg)

## Sobre integrações de parceiros

A integração com um parceiro importa de forma simples e contínua seus criativos de campanhas executadas por meio do parceiro para a ferramenta de <Anchor target="_blank" href="/marketers/pt/docs/creative-optimization-guide">otimização de criativos</Anchor>.

### Disponibilidade de dados

Depois que uma integração de parceiro for adicionada:

* O sistema preenche dados de criativos e dados de desempenho da AppsFlyer dos últimos 90 dias. Os dados normalmente ficam disponíveis no Creative Optimization em 24 horas.
* Os dados dos criativos continuarão a ser extraídos de parceiros integrados duas vezes por dia, todos os dias. Os dados são incorporados e combinados com outros pontos de dados de performance da AppsFlyer, como atribuição, gastos, cliques, impressões, receita etc. (os dados de performance da AppsFlyer são atualizados de hora em hora). Os **dashboards de otimização de criativos exibem os dados combinados de todos os processos acima e são atualizados uma vez por dia** **em UTC + 10** (todos os dados dos últimos 90 dias são atualizados).

> 📘 **Atenção**
>
> para ver os dados de custo da AppsFlyer (como ROAS), é necessária uma <Anchor target="_blank" href="/marketers/pt/docs/roi360-cost-aggregation-overview">assinatura do ROI360</Anchor>.

## Integrações de parceiros de mídia

Essa seção descreve como configurar integrações com cada parceiro.

<div id="adikteev" />

<Accordion title="Adikteev">

**Pré-requisitos:**

* Credenciais para integração:
  * E-mail (nome de usuário Adikteev)
  * Senha do Adikteev
  * **Atenção:** devem ser as mesmas credenciais usadas para acessar o dashboard do Adikteev.
* Para nos permitir a extração de todos os dados de custos do Adikteev, o mesmo usuário que integrou o <Anchor target="_blank" href="/marketers/pt/docs/roi360-cost-aggregation-overview">ROI360</Anchor> deve integrar também a otimização de criativos.

**Para adicionar uma integração:**

1. Faça login em **otimização de criativos** e siga um desses procedimentos:
   * Se você não tiver integrações de parceiros, clique em + **Adicionar nova integração**.
   * Caso contrário, clique no ícone  ⋮  no canto superior direito para acessar **Integrações de criativos**.  
     ![Main menu icon and filter bar New Default view.jpg](https://files.readme.io/b70e69e0624f5592d3bbfc0b4be148d7ba6bc06ce496529ff1708e9dbc489915-21381993469969.jpg)
2. Clique em **+ Nova integração**.
3. Na lista de **parceiros**, selecione **Adikteev**.
4. Selecione os aplicativos que você está promovendo.
5. Insira seu e-mail e senha.
6. Clique em **Salvar**.

**Atenção:** o Adikteev também é conhecido como Trademob (trademob\_int).

</Accordion>

<div id="adjoe" />

<Accordion title="Adjoe">

**Pré-requisito:**

* Credencial para integração:
  * Token  
    Entre em contato com seu gerente de conta da Adjoe para obter o token. Veja a <Anchor target="_blank" href="https://drive.google.com/file/d/16zMpKbRLmTLU-plnodELGAHZVe0CuC_F/view">documentação do Adjoe</Anchor>

**Para adicionar uma integração:**

1. Faça login em **otimização de criativos** e siga um desses procedimentos:
   * Se você não tiver integrações de parceiros, clique em + **Adicionar nova integração**.
   * Caso contrário, clique no ícone  ⋮  no canto superior direito para acessar **Integrações de criativos**.  
     ![Main menu icon and filter bar New Default view.jpg](https://files.readme.io/b70e69e0624f5592d3bbfc0b4be148d7ba6bc06ce496529ff1708e9dbc489915-21381993469969.jpg)
2. Clique em **+ Nova integração**.
3. Na lista de **parceiros**, selecione **Adjoe GmbH**.
4. Selecione os aplicativos que você está promovendo.
5. Insira o token.
6. Clique em **Salvar**.

</Accordion>

<div id="applovin" />

<Accordion title="AppLovin">

**Pré-requisitos:**

* Você precisará de permissões de conta de anúncios para os aplicativos relevantes que você deseja integrar. **Atenção**: a autenticação na AppLovin deve ser feita pelo administrador da conta.
* Um **Account ID**, **chave da Campaign Management API** e **chave da Reporting API** são necessários. Você pode obter essas informações no seu dashboard da AppLovin Axon (clique na sua conta no canto superior direito e selecione "keys").

**Para adicionar uma integração:**

1. Faça login em **otimização de criativos**e siga um desses procedimentos:

   * Se você não tiver integrações de parceiros, clique em + **Adicionar nova integração**.
   * Caso contrário, clique no ícone  ⋮  no canto superior direito para acessar **Integrações de criativos**.

   ![Main menu icon and filter bar New Default view.jpg](https://files.readme.io/b70e69e0624f5592d3bbfc0b4be148d7ba6bc06ce496529ff1708e9dbc489915-21381993469969.jpg)
2. Clique em + **Nova integração**.
3. Na lista de **parceiros**, selecione **AppLovin**.
4. Selecione os aplicativos que você está promovendo.
5. Insira o **Account ID**, a **Campaign Management API key** e a **Reporting API key**.
6. Feito isso, clique em **Salvar**.

> 📘 **Atenção**
>
> A API de relatórios a nível de asset da AppLovin retorna apenas os dados do dia anterior. Ela não disponibiliza lookback histórico. Por isso, ao ativar a integração, a AppsFlyer só pode começar a coletar dados a nível de asset após a data de ativação. Como resultado, a cobertura total dos dados aumenta gradualmente e o processo costuma ser concluído em até 30 dias após a ativação.

</Accordion>

<div id="google-ads" />

<Accordion title="Google Ads">

**Pré-requisitos:**

* Permissões de administrador da conta de anúncios para os aplicativos relevantes que você deseja integrar.
* Para que possamos extrair todos os dados de criativos do Google, o mesmo usuário que integrou o <Anchor target="_blank" href="/marketers/pt/docs/roi360-cost-aggregation-overview">ROI360</Anchor> deve integrar também a ferramenta de otimização de criativos. Se não houver assinatura do ROI360, você deverá ter permissões de administrador para todos os aplicativos e contas de anúncios relevantes no Google AdWords.

**Atenção:**

* A integração com o Google Ads é feita por usuário, o que significa que vários usuários podem ter integrações ativas simultaneamente.

**Para adicionar uma integração:**

1. Faça login em **otimização de criativos**e siga um desses procedimentos:
   * Se você não tiver integrações de parceiros, clique em + **Adicionar nova integração**.
   * Caso contrário, clique no ícone  ⋮  no canto superior direito para acessar **Integrações de criativos**.  
     ![Main menu icon and filter bar New Default view.jpg](https://files.readme.io/b70e69e0624f5592d3bbfc0b4be148d7ba6bc06ce496529ff1708e9dbc489915-21381993469969.jpg)
2. Clique em + **Nova integração**.
3. Clique na lista de **parceiros** e selecione **Google Ads (AdWords)**.
4. Selecione os aplicativos que você está promovendo.
5. Clique em **Login com o Google**. A janela **Login com o Google** é aberta.
6. Conclua o login e forneça suas permissões. Observe que, para que a AppsFlyer extraia dados completos, é recomendado que você tenha permissões completas.
7. Clique em **Salvar**.

**Atenção:** oferecemos suporte apenas para os tipos de anúncios de campanha UAC (ACi, ACe e ACpre). Os dados de anúncios não compatíveis estarão disponíveis na Otimização de criativos apenas no nível do anúncio (não no nível do criativo).

</Accordion>

<div id="ironsource" />

<Accordion title="ironSource">

**Pré-requisitos:**

* Credenciais ironSource para integração:
  * Chave secreta
  * Atualizar token
  * <Anchor target="_blank" href="https://developers.is.com/ironsource-mobile/ios/authentication/#step-1">Saiba</Anchor> onde encontrar suas credenciais exclusivas.
* Uma função de usuário Administrador ou Colaborador no ironSource. <Anchor target="_blank" href="https://developers.is.com/ironsource-mobile/air/user-management/#step-1">Aprenda como configurar funções de usuário</Anchor>.

**Para adicionar uma integração:**

1. Faça login em **otimização de criativos**e siga um desses procedimentos:
   * Se você não tiver integrações de parceiros, clique em + **Adicionar nova integração**.
   * Caso contrário, clique no ícone  ⋮  no canto superior direito para acessar **Integrações de criativos**.  
     ![Main menu icon and filter bar New Default view.jpg](https://files.readme.io/b70e69e0624f5592d3bbfc0b4be148d7ba6bc06ce496529ff1708e9dbc489915-21381993469969.jpg)
2. Clique em **+ Nova integração**.
3. Na lista de **parceiros**, selecione **IronSource**.
4. Selecione os aplicativos que você está promovendo.
5. Insira a chave secreta e atualize o token.
6. Clique em **Salvar**.

**Atenção:** ertos tipos de anúncios não são compatíveis, o que significa que seus dados na Otimização de criativos estão disponíveis somente no nível do anúncio (não no nível do criativo). Os tipos de anúncio não compatíveis incluem anúncios Offerwall.

</Accordion>

<div id="liftoff" />

<Accordion title="Liftoff">

**Para adicionar uma integração:**

1. Faça login em **otimização de criativos**e siga um desses procedimentos:
   * Se você não tiver integrações de parceiros, clique em + **Adicionar nova integração**.
   * Caso contrário, clique no ícone  ⋮  no canto superior direito para acessar **Integrações de criativos**.  
     ![Main menu icon and filter bar New Default view.jpg](https://files.readme.io/b70e69e0624f5592d3bbfc0b4be148d7ba6bc06ce496529ff1708e9dbc489915-21381993469969.jpg)
2. Clique em **+ Nova integração**.
3. Na lista de **Parceiros**, selecione **Liftoff**.
4. Selecione os aplicativos que você está promovendo.
5. Entre em contato com seu CSM da Liftoff para obter seu nome de usuário e senha da API para relatórios da Liftoff.
6. Clique em **Salvar**.

</Accordion>

<div id="facebook-ads" />

<Accordion title="Meta Ads">

**Pré-requisitos:**

* Permissões da conta de anúncios para os aplicativos que você deseja integrar. **Atenção**: a integração com o Meta ads é feita por usuário, o que significa que vários usuários podem ter integrações ativas simultaneamente.
* Para extrair criativos exibidos em páginas internas e/ou externas do Facebook, certifique-se de que o administrador do Facebook Business Center forneça as permissões relevantes ao usuário que configura a integração com a ferramenta de otimização de criativos.

**Para adicionar uma integração:**

1. Faça login em **otimização de criativos**e siga um desses procedimentos:
   * Se você não tiver integrações de parceiros, clique em + **Adicionar nova integração**.
   * Caso contrário, clique no ícone  ⋮  no canto superior direito para acessar **Integrações de criativos**.  
     ![Main menu icon and filter bar New Default view.jpg](https://files.readme.io/b70e69e0624f5592d3bbfc0b4be148d7ba6bc06ce496529ff1708e9dbc489915-21381993469969.jpg)
2. Clique em **+ Nova integração**.
3. Na lista de **parceiros**, selecione **Meta ads**.
4. Selecione os aplicativos que você está promovendo.
5. Clique em **Login com Meta ads**.
6. Conclua o login e forneça suas permissões. **Atenção**: para que a AppsFlyer extraia dados completos, recomendamos que você tenha permissões completas.
7. Clique em **Salvar**.

**Atenção:**

* Como os anúncios flexíveis do Meta oferecem apenas um asset para relatórios, apenas os dados de performance associados ao asset que possui a melhor performance (de um anúncio) são exibidos.
* certos tipos de anúncios não são compatíveis, o que significa que seus dados na Otimização de criativos estão disponíveis somente no nível do anúncio (não no nível do criativo). Tipos de anúncios compatíveis: Catalog/DPA

</Accordion>

<div id="mintegral" />

<Accordion title="Mintegral">

**Pré-requisitos:**

* Credenciais da Mintegral para integração:
  * chave de API
  * Chave de acesso
  * <Anchor target="_blank" href="https://adv-new.mintegral.com/doc/en/guide/introduction/register.html">Saiba</Anchor> onde encontrar suas credenciais exclusivas.

**Para adicionar uma integração:**

1. Faça login em **otimização de criativos**e siga um desses procedimentos:
   * Se você não tiver integrações de parceiros, clique em + **Adicionar nova integração**.
   * Caso contrário, clique no ícone  ⋮  no canto superior direito para acessar **Integrações de criativos**.  
     ![Main menu icon and filter bar New Default view.jpg](https://files.readme.io/b70e69e0624f5592d3bbfc0b4be148d7ba6bc06ce496529ff1708e9dbc489915-21381993469969.jpg)
2. Clique em **+ Nova integração**.
3. Na lista de **Parceiros**, selecione **Mintegral**.
4. Selecione os aplicativos que você está promovendo.
5. Insira a **API key** e a **chave secreta**.
6. Clique em **Salvar**.

</Accordion>

<div id="moloco" />

<Accordion title="Moloco">

**Pré-requisitos:**

* Para poder extrair criativos, você precisará de uma função de <Anchor target="_blank" href="https://help.moloco.com/hc/en-us/articles/360050566173-Invite-and-manage-users">“Proprietário do workplace” ou “Proprietário da conta de anúncio”</Anchor>.
* Acesso à sua chave da Moloco API.

**Para adicionar uma integração:**

1. Faça login em **otimização de criativos**e siga um desses procedimentos:
   * Se você não tiver integrações de parceiros, clique em + **Adicionar nova integração**.
   * Caso contrário, clique no botão ⋮ no canto superior direito para acessar **Integrações de criativos**.![Main menu icon and filter bar New Default view.jpg](https://files.readme.io/b70e69e0624f5592d3bbfc0b4be148d7ba6bc06ce496529ff1708e9dbc489915-21381993469969.jpg)
2. Clique em **+ Nova integração**.
3. Na lista de **Parceiros**, selecione **Moloco**.
4. Selecione os aplicativos que você está promovendo.
5. Insira sua chave da Moloco API.
6. Clique em **Salvar**.

**Atenção**:

* certos tipos de anúncios não são compatíveis, o que significa que seus dados na Otimização de criativos estão disponíveis somente no nível do anúncio (não no nível do criativo). Os tipos de anúncios não suportados incluem anúncios de CTV.

</Accordion>

<div id="personaly" />

<Accordion title="Persona.ly">

**Pré-requisitos:**

**Para adicionar uma integração:**

1. Faça login em **otimização de criativos**e siga um desses procedimentos:
   * Se você não tiver integrações de parceiros, clique em + **Adicionar nova integração**.
   * Caso contrário, clique no ícone  ⋮  no canto superior direito para acessar **Integrações de criativos**.  
     <Image alt="Main menu icon and filter bar New Default view.jpg" src="https://files.readme.io/b70e69e0624f5592d3bbfc0b4be148d7ba6bc06ce496529ff1708e9dbc489915-21381993469969.jpg" width="927px" />
2. Clique em **+ Nova integração**.
3. Na lista de **Parceiros**, selecione **Persona.ly**.
4. Selecione os aplicativos que você está promovendo.
5. Insira a **API key** da Persona.ly (você pode obtê-la na sua conta da Persona.ly).
6. Clique em **Salvar**.

</Accordion>

<div id="reddit" />

<Accordion title="Reddit">

**Pré-requisitos:**

* Para poder extrair criativos, você precisa de uma função de "Criador" ou "Administrador" do Reddit.

**Para adicionar uma integração:**

1. Faça login em **otimização de criativos**e siga um desses procedimentos:
   * Se você não tiver integrações de parceiros, clique em + **Adicionar nova integração**.
   * Caso contrário, clique no ícone  ⋮  no canto superior direito para acessar **Integrações de criativos**.  
     ![Main menu icon and filter bar New Default view.jpg](https://files.readme.io/b70e69e0624f5592d3bbfc0b4be148d7ba6bc06ce496529ff1708e9dbc489915-21381993469969.jpg)
2. Clique em **+ Nova integração**.
3. Na lista de **parceiros**, selecione **Reddit**.
4. Selecione os aplicativos que você está promovendo.
5. Clique em **Login com o Reddit**.
6. Conclua o login e forneça suas permissões. **Atenção**: para que a AppsFlyer extraia dados completos, recomendamos que você tenha permissões completas.
7. Clique em **Salvar**.

</Accordion>

<div id="remerge" />

<Accordion title="Remerge">

**Pré-requisitos:**

* Credenciais para integração (**Atenção**: são as mesmas credenciais usadas para acessar o dashboard do Remerge. Ver <Anchor target="_blank" href="https://help.remerge.io/hc/en-us/articles/115003440434-Remerge-Reporting-API">Documentação do Remerge</Anchor>):
  * E-mail do usuário
  * Senha

**Para adicionar uma integração:**

1. Faça login em **otimização de criativos**e siga um desses procedimentos:
   * Se você não tiver integrações de parceiros, clique em + **Adicionar nova integração**.
   * Caso contrário, clique no botão ⋮ no canto superior direito para acessar **Integrações de criativos**.![Main menu icon and filter bar New Default view.jpg](https://files.readme.io/b70e69e0624f5592d3bbfc0b4be148d7ba6bc06ce496529ff1708e9dbc489915-21381993469969.jpg)
2. Clique em **+ Nova integração**.
3. Na lista de **parceiros**, selecione **Remerge**.
4. Selecione os aplicativos que você está promovendo.
5. Insira seu e-mail e senha.
6. Clique em **Salvar**.

</Accordion>

<div id="revx" />

<Accordion title="RevX">

**Pré-requisitos:**

**Para adicionar uma integração:**

1. Faça login em **otimização de criativos**e siga um desses procedimentos:
   * Se você não tiver integrações de parceiros, clique em + **Adicionar nova integração**.
   * Caso contrário, clique no ícone  ⋮  no canto superior direito para acessar **Integrações de criativos**.  
     <Image alt="Main menu icon and filter bar New Default view.jpg" src="https://files.readme.io/b70e69e0624f5592d3bbfc0b4be148d7ba6bc06ce496529ff1708e9dbc489915-21381993469969.jpg" width="927px" />
2. Clique em **+ Nova integração**.
3. Na lista de **Parceiros**, selecione **RevX**.
4. Selecione os aplicativos que você está promovendo.
5. Insira a **API key** da RevX (entre em contato diretamente com seu gerente de conta da RevX para obter sua API key).
6. Clique em **Salvar**.

</Accordion>

<div id="smadex" />

<Accordion title="Smadex">

**Pré-requisitos:**

* Credenciais Smadex para integração (**Atenção**: são as mesmas credenciais usadas para acessar seu dashboard do Smadex):
  * E-mail
  * Senha

**Para adicionar uma integração:**

1. Faça login na **otimização de criativos** e siga um desses procedimentos:
   * Se você não tiver integrações de parceiros, clique em + **Adicionar nova integração**.
   * Caso contrário, clique no botão ⋮ no canto superior direito para acessar **Integrações de criativos**.![Main menu icon and filter bar New Default view.jpg](https://files.readme.io/b70e69e0624f5592d3bbfc0b4be148d7ba6bc06ce496529ff1708e9dbc489915-21381993469969.jpg)
2. Clique em **+ Nova integração**.
3. Na lista de **parceiros**, selecione **Smadex**.
4. Selecione os aplicativos que você está promovendo.
5. Insira as credenciais necessárias.
6. Clique em **Salvar**.

</Accordion>

<div id="snap" />

<Accordion title="Snapchat">

Pré-requisitos: Você precisará de permissões de conta de anúncios para os aplicativos relevantes que deseja integrar. **Atenção**: A integração com o Snapchat é feita por usuário, o que significa que vários usuários podem ter integrações ativas simultaneamente.

**Para adicionar uma integração:**

1. Faça login em **otimização de criativos**e siga um desses procedimentos:
   * Se você não tiver integrações de parceiros, clique em + **Adicionar nova integração**.
   * Caso contrário, clique no ícone  ⋮  no canto superior direito para acessar **Integrações de criativos**.  
     ![Main menu icon and filter bar New Default view.jpg](https://files.readme.io/b70e69e0624f5592d3bbfc0b4be148d7ba6bc06ce496529ff1708e9dbc489915-21381993469969.jpg)
2. Clique em **+ Nova integração**.
3. Na lista de **parceiros**, selecione **Snapchat**.
4. Selecione os aplicativos que você está promovendo.
5. Clique em **Login com Snap**. A **janela** será aberta.
6. Conclua o login e forneça suas permissões. Observe que, para que a AppsFlyer extraia dados completos, é recomendado que você tenha permissões completas.
7. Clique em **Salvar**.

**Atenção:** certos tipos de anúncios não são compatíveis, o que significa que seus dados na Otimização de criativos estão disponíveis somente no nível do anúncio (não no nível do criativo). Os tipos de anúncios não compatíveis incluem Collection Ads.

</Accordion>

<div id="tiktok" />

<Accordion title="Tiktok">

**Pré-requisitos:**

* Você precisará de permissões de conta de anúncios para os aplicativos relevantes que você deseja integrar. **Atenção**: A integração com o TikTok é feita por usuário, o que significa que vários usuários podem ter integrações ativas simultaneamente.
* Para extrair dados de criativos do Spark Ads, certifique-se de que o administrador do TikTok Business Center forneça as permissões relevantes ao usuário que está configurando a integração com a ferramenta de otimização de criativos.

**Para adicionar uma integração:**

1. Faça login em **otimização de criativos**e siga um desses procedimentos:
   * Se você não tiver integrações de parceiros, clique em + **Adicionar nova integração**.
   * Caso contrário, clique no ícone  ⋮  no canto superior direito para acessar **Integrações de criativos**.  
     ![Main menu icon and filter bar New Default view.jpg](https://files.readme.io/b70e69e0624f5592d3bbfc0b4be148d7ba6bc06ce496529ff1708e9dbc489915-21381993469969.jpg)
2. Clique em **+ Nova integração**.
3. Na lista de **parceiros**, selecione **TikTok**.
4. Selecione os aplicativos que você está promovendo.
5. Clique em **Login com o TikTok**. A **janela** será aberta.
6. Conclua o login e forneça suas permissões. Observe que, para que a AppsFlyer extraia dados completos, é recomendado que você tenha permissões completas.
7. Clique em **Salvar**.

> 📘 **Observações**
>
> * `bytedanceglobal_int` está sendo gradualmente retirada e será desativada até março de 2024. Saiba mais no <Anchor target="_blank" href="/marketers/pt/docs/bulletin-tiktok-for-business-advanced-srn">boletim</Anchor>.
>   * Se a integração legada (bytedanceglobal\_int) ainda estiver ativa após a nova (tiktokglobal\_int) ser integrada, haverá uma duplicação de dados de performance na Otimização de criativos, pois eles serão extraídos de ambas as redes.
>   * Os criativos não serão duplicados, pois a IA identifica os assets reais.
>   * A remoção da integração legada não excluirá os dados históricos do produto.
>   * Para extrair todos os dados necessários, quem conecta o TikTok SRN deve ter as permissões relevantes (recomenda-se um administrador de conta de anúncios).
> * certos tipos de anúncios não são compatíveis, o que significa que seus dados na Otimização de criativos estão disponíveis somente no nível do anúncio (não no nível do criativo). Os tipos de anúncios não compatíveis incluem Collection Ads e Shopping Ads.

</Accordion>

<div id="unity-ads" />

<Accordion title="Unity Ads">

**Pré-requisitos:**

* Credenciais da conta de serviço da Unity para integração:
  * ID da chave
  * Chave secreta
  * Organization core ID

[Consulte as instruções para recuperar suas credenciais.](/docs/creative-optimization-partner-integrations#instruções-para-recuperar-suas-credenciais)

* Uma das seguintes funções de conta de serviço (organização) deve ser selecionada na Unity:
  * A função **Advertise API Admin** é necessária para obter criativos.
  * A função **Advertisers API Stats Viewer** é necessária se você quiser extrair métricas da Unity (além de criativos). <Anchor target="_blank" href="https://services.docs.unity.com/statistics/#section/Migrating-from-the-previous-version-of-the-API/Query-parameters">Saiba mais</Anchor>

**Atenção:** Se essas funções não estiverem disponíveis para você, entre em contato com seu CSM da Unity Ads.

#### Instruções para recuperar suas credenciais

**Para recuperar o Key ID e a chave secreta:**

1. Faça login na Unity Ads.
2. No painel lateral do menu principal, clique em **Administration** e depois em **Service Accounts**.
3. Clique na conta de serviço específica.
4. Clique em **+ Add Key**.  
   Isso abre o Key ID e a chave secreta.
5. Copie o **Key ID** e a **Chave secreta**.  
   ![Unity: imagem.jpg para obter o ID da chave & a chave secreta](https://files.readme.io/9c4d1b1e0e476546b8f8be3a7375c610c48db6f94344a3dbe48277a6d115f52e-20344146224401.jpg)

**Pararecuperar o** <Anchor target="_blank" href="https://services.docs.unity.com/advertise/v1/index.html#section/General-Information/Resource-IDs-Used-in-the-API-Calls">**Organization core ID:**</Anchor>

1. Na Unity Ads, clique em **Products** no menu lateral.
2. Clique em **Grow**.  
   ![Unity Org ID step 1 cropped.jpg](https://files.readme.io/5e8d2f54f5999c58b2e2b3591ae889f5051cae4073aa6c5ef17e16da6a60131f-22859368875153.jpg)
3. Clique em **Unity Ads User Acquisition**.  
   <Image alt="Unity Org ID step 2 cropped.jpg" src="https://files.readme.io/07a1c8e878a9ed7b6832012b3261866477b825d3b23e4973b8c5dadd675973e2-22859368883473.jpg" width="347px" />
4. Clique em Settings.   
   ![Get Organization core ID instructions 2 arrows.jpg](https://files.readme.io/aff97bcb1c255771fc46483d8d94a2f13c7ef26c45a7fc884b1c03c83da91ae5-20344868139153.jpg)
5. Copie o **Organization core ID**.

#### **Para selecionar uma função de conta de serviço (organização):**

1. No dashboard da Unity, cliqueem **Administration**.   
   **<Image alt="Funções da organização, etapa 1.jpg" src="https://files.readme.io/b9a9258cf324cdf0c73ab9be8d1646c43d2211d23cebafa3624582e6e964851f-20347001525777.jpg" width="372px" />**
2. Clique em **Service Accounts**.
3. Clique na conta de serviço relevante e clique em **+ Manage organization roles**.  
   **![Org roles step 2.jpg](https://files.readme.io/f72334c392a89084c22fc6c6d97cedb051b4a53de9bad1eb3722c2e0f31852de-20347023191697.jpg)**
4. Em **Grow** , selecione as seguintes funções de organização da conta de serviço:
   * **Advertisers API Stats Viewer**, para extrair métricas da Unity.
   * Uma das outras funções abaixo, para extrair os criativos:
     * Administrador da API de publicidade
     * Advertise API Viewer
     * Editor de pacotes de criativos da Advertise API  
       <Image alt="Org roles step 3 without role names.jpg" src="https://files.readme.io/7b46417e6389f7c3675cc6f72b33e9b2833d5c561ef1d79122ed24605533b265-20347535827217.jpg" width="471px" />
5. Clique em **Save**.

**Atenção**: se você não tiver acesso a essas funções, entre em contato com seu customer success manager da Unity ou envie um e-mail para [unitads-support@unity3d.com](mailto:unityads-support@unity3d.com) para solicitar as permissões necessárias.

#### **Para adicionar uma integração da Unity ao dashboard da otimização de criativos:**

1. No dashboard da **otimização de criativos**, siga um desses procedimentos:
   * Se você não tiver integrações de parceiros, clique em + **Adicionar nova integração**.
   * Caso contrário, clique no ícone  ⋮  no canto superior direito para acessar **Integrações de criativos**.  
     ![Main menu icon and filter bar New Default view.jpg](https://files.readme.io/b70e69e0624f5592d3bbfc0b4be148d7ba6bc06ce496529ff1708e9dbc489915-21381993469969.jpg)
2. Clique em **+ Nova integração**.
3. Na lista **parceiros**, selecione **Unity Ads**.
4. Selecione os aplicativos que você está promovendo.
5. Insira o key ID, a chave secreta e o organization core ID.
6. Insira as informações <Anchor target="_blank" href="/marketers/pt/docs/creative-optimization-guide#partner-metrics::e592ecd3">de métricas do parceiro</Anchor> para obter também as métricas relatadas pela Unity Ads.
7. Clique em **Salvar**.

</Accordion>

<div id="x-ads" />

<Accordion title="X Ads (antigo Twitter Ads)">

**Pré-requisitos:**

* Para poder extrair criativos, você precisa de uma função de "Administrador da conta" ou "Gerente de anúncios" do X Ads.

**Para adicionar uma integração:**

1. Faça login em **otimização de criativos**e siga um desses procedimentos:
   * Se você não tiver integrações de parceiros, clique em + **Adicionar nova integração**.
   * Caso contrário, clique no ícone  ⋮  no canto superior direito para acessar **Integrações de criativos**.  
     <Image alt="Main menu icon and filter bar New Default view.jpg" src="https://files.readme.io/b70e69e0624f5592d3bbfc0b4be148d7ba6bc06ce496529ff1708e9dbc489915-21381993469969.jpg" width="927px" />
2. Clique em **+ Nova integração**.
3. Na lista de **parceiros**, selecione **X Ads**.
4. Selecione os aplicativos que você está promovendo.
5. Clique em **Login com X Ads**.
6. Conclua o login e forneça suas permissões. **Atenção**: para que a AppsFlyer extraia dados completos, recomendamos que você tenha permissões completas.
7. Clique em **Salvar**.

</Accordion>

<div id="youappi" />

<Accordion title="YouAppi">

**Pré-requisito:**

Credenciais YouAppi para integração:

* Token  
  **Atenção**: Você pode entrar em contato com seu gerente de conta na YouAppi para obter o token. Para mais informações, consulte a <Anchor target="_blank" href="https://support.youappi.com/knowledgebase/reporting-api-for-re-engagement/">documentação da YouAppi</Anchor>.

**Para adicionar uma integração:**

1. Faça login em **otimização de criativos** e siga um desses procedimentos:
   * Se você não tiver integrações de parceiros, clique em + **Adicionar nova integração**.
   * Caso contrário, clique no ícone  ⋮  no canto superior direito para acessar **Integrações de criativos**.  
     ![Main menu icon and filter bar New Default view.jpg](https://files.readme.io/b70e69e0624f5592d3bbfc0b4be148d7ba6bc06ce496529ff1708e9dbc489915-21381993469969.jpg)
2. Clique em **+ Nova integração**.
3. Na lista de **parceiros**, selecione **YouAppi**.
4. Selecione os aplicativos que você está promovendo.
5. Insira o token.
6. Clique em **Salvar**.

</Accordion>

## Informações adicionais

<div id="creative-integrations-dashboard" />

<Accordion title="Dashboard de integrações de criativos">

O dashboard de integrações de criativos é onde você pode adicionar novas integrações de parceiros de mídia. Para adicionar uma nova integração, siga as [instruções específicas por parceiro](/docs/creative-optimization-partner-integrations#disponibilidade-de-dados).

Depois de adicionado, o dashboard exibe o status de todas as suas integrações atuais, com as seguintes colunas:

| Coluna | Descrição |
| --- | --- |
| Parceiro | O nome do parceiro integrado, por exemplo, Meta Ads ou ironsource\_int. Expanda a coluna do parceiro para ver todas as diferentes conexões para o parceiro. Por exemplo, cada usuário pode ter sua própria conexão. |
| Aplicativo | A lista de aplicativos por parceiro integrado e conexão de usuário específica. |
| Atualização da integração | A data em que as configurações da integração de parceiros foram atualizadas pela última vez. |
| Status da cobertura | A quantidade de dados de performance de criativos disponíveis a partir da integração do parceiro, exibida nos dashboards e relatórios da otimização de criativos:<ul><li>**Baixa**: Todos os aplicativos incluídos nessa integração têm dados em falta.</li><li>**Parcial**: Alguns aplicativos incluídos nessa integração têm dados em falta</li><li>**Alta**: Todos os aplicativos incluídos nessa integração têm dados o suficiente.</li><li>**Em andamento**: Aguarde até 24 horas para uma atualização no status.</li><li>**Sem dados**: Não há dados desse parceiro nos últimos 30 dias.</li></ul>Clique no status para ver o detalhamento do status da cobertura por aplicativo. O status por aplicativo mostra coisas diferentes, a depender se você é um assinante do ROI360 ou não.<br /><br />**Para assinantes do ROI360**<ul><li>**Alta**: O aplicativo tem muitos dados disponíveis. Isso significa que os criativos extraídos cobrem mais de 85% do total de instalações de aplicativos (conforme relatado pela AppsFlyer) nos últimos 30 dias.</li><li>**Baixa**: O aplicativo está com falta de dados. Isso significa que os criativos extraídos cobrem menos de 85% do total de instalações de aplicativos (conforme relatado pela AppsFlyer) nos últimos 30 dias.</li></ul>**Para assinantes do ROI360:**<ul><li>**Alta**: Os criativos extraem mais de 85% do custo, conforme mensurado pelo ROI360 da AppsFlyer nos últimos 30 dias.</li><li>**Baixa**: Os criativos extraíram menos de 85% do custo, conforme mensurado pelo ROI360 da AppsFlyer nos últimos 30 dias.<br />**Exemplo**:<ul><li>A AppsFlyer obtém dados da fonte de mídia "Network A" com um gasto total de US$100 em anúncios.</li><li>O Criativo 1 teve um gasto em anúncios de US$85 e o Criativo 2, de US$15.</li><li>Se a AppsFlyer extrair os dados do Criativo 1, esse valor cobre 85% do custo, então é uma cobertura "alta".</li><li>Se a AppsFlyer extrair apenas os dados do Criativo 2, esse valor cobre apenas 15% do custo, então é uma cobertura "baixa".</li></ul></li></ul>**Para assinantes do ROI360 e usuários sem assinatura:**<ul><li>**Em andamento**: Aguarde até 24 horas para uma atualização no status.</li><li>**Poucos dados**: Certifique-se de que o parceiro esteja integrado corretamente, seguindo as [instruções específicas do parceiro](/docs/creative-optimization-partner-integrations#disponibilidade-de-dados).</li><li>**Sem dados**: Não há dados desse aplicativo nos últimos 30 dias.<ul><li>Certifique-se de que sua configuração geral da AppsFlyer esteja concluída e funcionando (não especificamente para o modo de otimização de criativos).</li><li>Verifique se o aplicativo está ativo e se há tráfego.<br />Se a integração for gerenciada por uma agência, certifique-se de que a integração esteja correta, seguindo as [instruções da agência](/docs/creative-optimization-partner-integrations#agencies).</li></ul></li></ul> |

</Accordion>

<div id="agencies" />

<Accordion title="Integrações de agências">

#### Adicionar uma integração de agência

Você pode se integrar com suas agências parceiras para extrair seus dados para o dashboard da otimização de criativos.

**Para adicionar uma integração de agência:**

1. Faça login em **otimização de criativos**e siga um desses procedimentos:
   * Se você não tiver integrações de parceiros, clique em + **Adicionar nova integração**.
   * Caso contrário, clique no ícone  ⋮ no canto superior direito do painel para acessar **Integrações criativas**.  
     <Image alt="Main menu icon and filter bar New Default view.jpg" src="https://files.readme.io/b70e69e0624f5592d3bbfc0b4be148d7ba6bc06ce496529ff1708e9dbc489915-21381993469969.jpg" width="927px" />
2. Clique em **+ Nova integração**.
3. Após selecionar o parceiro e os aplicativos na janela de integração de parceiros, clique nas **configurações avançadas: No menu suspenso da agência,** selecione a agência relevante.  

   <Image alt="Creative agencies.png" src="https://files.readme.io/74f0dc492bc530278687becdd0061e9c06081653b69ed525f237b97a9568e413-38395601553169.png" width="288px" />
4. Clique em **Salvar**.  
   A integração da agência foi adicionada.

**Atenção:**

* Para cada agência cujos dados de criativos você deseja ver no dashboard, será necessário criar uma integração de parceiro separada com a caixa de seleção "Agência" marcada.
* Os dados estão disponíveis apenas para agências transparentes. <Anchor target="_blank" href="/marketers/pt/docs/view-agency-data">Saiba mais</Anchor>
* Os dados de criativos serão extraídos apenas da agência. Isso significa que se você selecionou o Google Ads como parceiro, como no exemplo acima, mas também tem campanhas veiculadas diretamente com o Google Ads, será necessário criar uma integração de parceiro adicional para o Google Ads.

#### Conceda o acesso ao dashboard

Você pode conceder às suas agências acesso para visualizar seus próprios dados de performance criativa no dashboard de Otimização de criativos se elas tiverem uma <Anchor target="_blank" href="/partners/pt/docs/about-agency-accounts">conta de agência na AppsFlyer</Anchor>. Isso pode ajudar a aumentar a transparência e a colaboração.

**Para permitir o acesso:**

1. No menu lateral da AppsFlyer, clique em **Colaborar** > **Partner Marketplace**  

   **<Image alt="From Collaborate click Partner Marketplace.png" src="https://files.readme.io/96485cefae79412a680915810c16b23619f73d9109212bfc45d1c0d42c2e529a-39258887136785.png" width="33.9%" />**
2. Pesquise a agência parceira na barra de pesquisa no topo da página e clique na agência desejada.

   <Image alt="Search bar.png" src="https://files.readme.io/f1ff34a547af45eec73e7abd41105bbab9ff12d4a2636ed4b99634985ec58044-39258887138449.png" width="1210px" />
3. Na página do parceiro, vá para a aba **Permissões** e habilite **Permissões da agência**

   <Image alt="Agency permissions.png" src="https://files.readme.io/b307601f9b41800a146c664bdd9f6d24a5398be9022801505419aebb0741162c-39258856594705.png" width="71.31%" />
4. Ative o**acesso ao dashboard de Otimização de criativos**  

   A agência agora terá acesso para ver os criativos compartilhados no seu dashboard. Para agências que ainda não configuraram uma conta de agência na AppsFlyer e gostariam de fazê-lo, saiba mais <Anchor target="_blank" href="/partners/pt/docs/getting-started-agency-onboarding">aqui.</Anchor>

</Accordion>

<div id="update-credentials" />

<Accordion title="Atualizar credenciais">

Depois que determinadas integrações de parceiros forem configuradas, suas credenciais em nível de conta não poderão ser alteradas (isso não se aplica a Meta Ads, Google Ads, TikTok e AppLovin). Se você precisar atualizar as credenciais de um parceiro:

1. Em **Integrações de criativos** , selecione o expansor à esquerda do parceiro para abrir as conexões do parceiro.
2. Clique em <Image alt="3 dots icon.png" src="https://files.readme.io/a43c9bec16ef919203a2535aee8aa1f284fb3db7851d5e61245163fe2d8b08cb-22469580700177.png" width="7px" />  à direita de conexão, e depois clique em **Deletar integração**. ![partner-integration-side-menu.png](https://files.readme.io/43ba588af05ffb8dafa165cf5d760010d36bd8b6409f6f9f4ef131d695989ed2-18565371542033.png)
3. Crie uma nova integração para o parceiro com as credenciais atualizadas.

</Accordion>

<div data-zendesk-anchors="about-creative-partner-integrations=sobre-integra%C3%A7%C3%B5es-de-parceiros h_01HAP6JQEFKAFK96WDBN0MERB6=sobre-integra%C3%A7%C3%B5es-de-parceiros media-partner-integrations=disponibilidade-de-dados h_01HEQ2QR21MZB57S6MQ5ZWZ7ZQ=disponibilidade-de-dados h_01K4M4JF53A3J1R5VACNVN4X8A=aten%C3%A7%C3%A3o h_01HC7W736NDRRAJ95Z28JS2J46=integra%C3%A7%C3%B5es-de-parceiros-de-m%C3%ADdia h_01HBAZ8724YYFVQWYV5F8F4F5S=adikteev 01H7SZ8RA055S4M11TTX1J0E55=adjoe 01H7SZ8RA0A52YQEMYX0GV44AB=applovin h_01KY4CAH2MKX650JS1R0N8X6B4=aten%C3%A7%C3%A3o-1 01H7SZ8RA0980TH09EP2ED9WSF=google-ads 01H7SZ8RA0DRWC76119ED96KHP=ironsource 01H7SZ8RA0428ZPRYD99GWRMK0=liftoff 01H7SZ8RA06V5BR4ABV0ZVK82Z=facebook-ads h_01JXCRAESXDAHGGJ71EB32NAPD=mintegral 01H7SZ8RA06G1W04NSEHSPSV2D=moloco h_01KRGPVZH0Z0DHEEJNP4ST5CD9=personaly 01J9V2ZJR6KYJERPR2Y2XNCREP=reddit 01H7SZ8RA0CDR1M5V2F177TG84=remerge h_01KRGPVZH00WKJ4VJN8QHAW3YS=revx h_01HZEP4F6M2W5HC76WVFP5Z5C0=smadex 01H7SZ8RA1H0Q47N1W3NST4PZW=snap 01H7SZ8RA1E221TK8VRWEF1FA4=tiktok 01H8VVCC8GW5AZ3M475XFZY9JW=observa%C3%A7%C3%B5es 01H7SZ8RA1YTA3MGVJMXVTP78Y=unity-ads instructions-for-retrieving-the-credentials=instru%C3%A7%C3%B5es-para-recuperar-suas-credenciais h_01GT6Z998RCBQWKDC9YGPJQGN6=instru%C3%A7%C3%B5es-para-recuperar-suas-credenciais to-select-a-service-account-organization-role=para-selecionar-uma-fun%C3%A7%C3%A3o-de-conta-de-servi%C3%A7o-organiza%C3%A7%C3%A3o h_01GT6ZFTGKMR18DTNVX706DH1R=para-selecionar-uma-fun%C3%A7%C3%A3o-de-conta-de-servi%C3%A7o-organiza%C3%A7%C3%A3o to-add-a-unity-connection-to-the-creative-dashboard=para-adicionar-uma-integra%C3%A7%C3%A3o-da-unity-ao-dashboard-da-otimiza%C3%A7%C3%A3o-de-criativos h_01GT6ZS52ZWY47BCT2NJVCFFEP=para-adicionar-uma-integra%C3%A7%C3%A3o-da-unity-ao-dashboard-da-otimiza%C3%A7%C3%A3o-de-criativos 01J9V2ZJSKN37WSGKA6D12MYBH=x-ads 01H7SZ8RA1E37649AAH1DNRXA9=youappi agency-integrations=informa%C3%A7%C3%B5es-adicionais h_01HC7WCZ143S29PGTVNFEX962Y=informa%C3%A7%C3%B5es-adicionais 01J9WK9A78RP6BKX6860MAABFM=creative-integrations-dashboard h_01HC7WCE9EJK3NDJQE88RZ3T0Z=agencies add-an-agency-integration=adicionar-uma-integra%C3%A7%C3%A3o-de-ag%C3%AAncia h_01K5PE1K1G75KEF9HXMAW9YP2F=adicionar-uma-integra%C3%A7%C3%A3o-de-ag%C3%AAncia grant-dashboard-access=conceda-o-acesso-ao-dashboard h_01K5PE1WK5AE2MX235B8FA4YJ0=conceda-o-acesso-ao-dashboard 01J9WKGYM1D04ZT14EPZ13VE4P=update-credentials" />
