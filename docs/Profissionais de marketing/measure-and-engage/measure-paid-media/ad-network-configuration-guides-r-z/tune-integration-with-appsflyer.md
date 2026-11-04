---
title: Integração da TUNE com a AppsFlyer
metadata:
  keywords:
    - Advertisers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2021-08-25T08:58:17Z'
  edited_at: '2026-08-19T00:26:15Z'
  id: 4406153487505
  locale: pt
  section: Ad network configuration guides (R-Z)
  section_id: 6552025468305
  url: https://support.appsflyer.com/hc/pt/articles/4406153487505
---
> **Resumo:** A TUNE, um parceiro integrado da AppsFlyer, é uma plataforma de marketing de parceiros.  
> Integre com a TUNE para mensurar o tráfego recebido e habilitar deep linking no seu aplicativo.

<Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/hasoffers.png" width="79px" />

<div id="setting-up-tune-integration" />

## Configuração da integração com a TUNE

A integração da AppsFlyer com a TUNE oferece suporte à atribuição de cliques.

**Pré-requisitos:** Antes de criar uma integração, certifique-se de entrar em contato com o parceiro e abrir uma conta com ele.

**Para configurar a integração:**

1. **Para ativar:** na AppsFlyer, no menu lateral, selecione **Colaborar** > **Partner Marketplace**.
2. Selecione o aplicativo correspondente.
3. Procure Tune e selecione **Integrar**.
4. Na aba **Integração**, selecione o aplicativo e ative a opção **Ativar parceiro**.  
    Mantenha essa opção ativada enquanto você trabalhar com Tune.
5. Configure as demais guias conforme necessário abaixo.

| Aba de Configurações | Observação: |
| --- | --- |
| **integração** | Configure as <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner">configurações de integração</Anchor> adicionais conforme necessário.<br /><br />O campo Custom\_TUNE\_tracking\_domain é usado para criar a URL do endpoint específico. Por exemplo, se você inserir "**greatapp**", a URL do seu endpoint será:  <br />https://greatapp.go2cloud.org/aff_Isr?<br /><br />Use o mesmo nome para o domínio de rastreamento personalizado de eventos in-app. |
| **Link de atribuição** | Gere <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#attribution-link-tab">links de atribuição.</Anchor> |
| **Custo (3)** | Obtenha <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#cost-tab">dados de custo</Anchor>. |
| **Ad revenue** | Não disponível para este parceiro |
| **Authorization: Bearer** | Defina as <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#permissions-tab">permissões</Anchor> da ad network conforme necessário. |

**Para ativar ou editar a integração:**

**Para editar**: na AppsFlyer, no menu lateral, selecione **Colaborar** > **Integrações Ativas**.

<div id="enabling-deep-linking-into-your-app" />

## Como habilitar deep linking no seu aplicativo

Use <Anchor target="_blank" href="/marketers/pt/docs/brand-onelink-with-your-domain">links de marca do OneLink</Anchor> gerados na AppsFlyer para mensurar cliques na TUNE. O processo a seguir permite direcionar usuários por deep linking para uma página específica no seu aplicativo.

<div id="prerequisite" />

### Pré-requisito

Verifique  as versões do SDK mobile da AppsFlyer:

* iOS: V4.9.0 ou posterior
* Android: V4.9.0 ou posterior

<div id="step-1-configure-links-for-your-campaigns" />

### Etapa 1: Configure links para suas campanhas

* Crie um <Anchor target="_blank" href="/marketers/pt/docs/create-a-onelink-template#como-criar-templates-do-onelink">template do OneLink</Anchor> para suas campanhas de e-mail.
* <Anchor target="_blank" href="/marketers/pt/docs/brand-onelink-with-your-domain">Crie um link de marca.</Anchor>  
  Quando for solicitado que você adicione um CNAME ao seu domínio, use `yourdomain.esplinks.appsflyer.com`, em vez da URL oferecida na página de criação do link de marca.  
  **Exemplo:**
  * **Subdomínio:** `click.example.com`
  * **CNAME:** `example.appsflyer.com`

    ![link-de-marca-esp-new-en_us.png](https://files.readme.io/a7433ac0e3b343195bac9b4be49d22c18534ec1c145189198c5ec467fea510bb-21323417936145.png)

    Observe que, ao clicar em **Verificar** para verificar o domínio de marca, é exibida uma mensagem de falha referente ao CNAME da AppsFlyer.

    ![link-de-marca-esp-mensagem-de-falha-cname.png](https://files.readme.io/94f159a089152437111fc6e4308464bc48512ee18f5e249460006bfda05252c2-21323447961105.png)

    Ignore esta mensagem e altere o CNAME conforme as instruções acima.

<div id="step-2-set-up-the-attribution-link" />

### Etapa 2: Configurar o link de atribuição

1. Acesse a guia Link de atribuição e copie apenas os parâmetros do link em **Link de atribuição de clique** conforme destacado abaixo.[![](https://files.readme.io/51bb21c2fe4bd82965f30909fe5ed4ae6c5b906972789b143755982ea8b73f6e-4406164987537.png)](https://files.readme.io/51bb21c2fe4bd82965f30909fe5ed4ae6c5b906972789b143755982ea8b73f6e-4406164987537.png)
2. Adicione os parâmetros copiados ao seu link de marca.

   <div id="example" />

   > 📄 **Exemplo:**
   >
   > ![TUNE-link-example2-en_us.png](https://files.readme.io/58f38eb0bb724b66d0c958454651e0950a54f6fd990220f2ac24f93ca89ba344-small-4410086650769.png)

3. Para concluir a configuração, acesse o <Anchor target="_blank" href="https://support.tune.com/hc/en-us/articles/1500008336641-Managing-Mobile-Offers-with-Appsflyer">guia Managing Mobile Offers with AppsFlyer</Anchor> na central de ajuda da TUNE, role para baixo até Universal Links via OneLink e siga as instruções.

<div data-zendesk-anchors="setting-up-tune-integration=configura%C3%A7%C3%A3o-da-integra%C3%A7%C3%A3o-com-a-tune h_01HJZRGVZ1VQF4N93THDRT5YCJ=configura%C3%A7%C3%A3o-da-integra%C3%A7%C3%A3o-com-a-tune enabling-deep-linking-into-your-app=como-habilitar-deep-linking-no-seu-aplicativo h_01HJZRGVZ1KJ80ZA1THKFZ535P=como-habilitar-deep-linking-no-seu-aplicativo prerequisite=pr%C3%A9-requisito h_01HJZRGVZ1ZC9G7M72V2HW4XDS=pr%C3%A9-requisito step-1-configure-links-for-your-campaigns=etapa-1-configure-links-para-suas-campanhas h_01HJZRGVZ1GPR3NQQAXRBXV09Z=etapa-1-configure-links-para-suas-campanhas step-2-set-up-the-attribution-link=etapa-2-configurar-o-link-de-atribui%C3%A7%C3%A3o h_01HJZRGVZ2F83PHABEWJXMMJ22=etapa-2-configurar-o-link-de-atribui%C3%A7%C3%A3o h_01HJZRGVZ2435CGWY4FZ5FKKHV=exemplo" />
