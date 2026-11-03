---
title: >-
  Plataforma de Colaboração de Dados (DCP) - Integração com o Salesforce Data
  Cloud
metadata:
  keywords:
    - Premium
    - Marketers
    - Data Clean Room
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-yael-sharabi
    - Marketers
    - Data Clean Room
  created_at: '2024-02-29T14:30:51Z'
  edited_at: '2026-08-18T00:07:13Z'
  id: 22977208909969
  locale: pt
  section: Data Collaboration Platform
  section_id: 26230608274065
  url: https://support.appsflyer.com/hc/pt/articles/22977208909969
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **Em resumo:** a integração com o Salesforce Data Cloud permite trazer seus dados primários para a plataforma de colaboração de dados da AppsFlyer com o clique de um botão.

> 🚧 **Antes de começar:**
>
> Antes de integrar o Salesforce Data Cloud, você deve **instalar a extensão de Aplicativo da AppsFlyer** a partir do Salesforce AppExchange. Isso deve ser realizado por um usuário administrador do Salesforce com permissão para fazer download de pacotes do AppExchange.
>
> 1. Acesse a <Anchor target="_blank" href="https://appexchange.salesforce.com/appxListingDetail?listingId=6c756ddf-777c-42fc-9eaf-d96ca36ed2e3">listagem da AppsFlyer</Anchor> no Salesforce AppExchange.
> 2. Clique em **Get It Now**.
> 3. Siga as etapas descritas no <Anchor target="_blank" href="https://developer.salesforce.com/docs/atlas.en-us.appExchangeInstallGuide.meta/appExchangeInstallGuide/appexchange_install_installation.htm">Guia de instalação de aplicativos</Anchor>.
>
> Após a instalação bem-sucedida, o processo estará concluído e não será necessária nenhuma configuração adicional do pacote.

## Configurando o Amplitude

A integração envolve criar uma conexão com o Salesforce Data Cloud e, em seguida, criar fontes. Você só precisa de uma conexão para autenticar sua conta do Salesforce. Usando essa conexão, você pode criar várias fontes com base em tabelas do Salesforce.

> 📘 **Nota**
>
> Se você já configurou uma conexão com o Salesforce Data Cloud, não poderá criar outra.

### Criar uma conexão com o Salesforce Data Cloud

1. Na AppsFlyer, no menu lateral, vá para **Colaborar** > **Data Clean Room.**
2. No canto superior direito da página, clique em **Gerenciar conexões** > **+ Nova conexão**.
3. Na caixa de diálogo **Nova conexão**, selecione **Provedores de dados** > **Salesforce Data Cloud**.  

   <Image alt="salesforce-data-cloud-new-connection.jpg" src="https://files.readme.io/6b240e0cff3f0bc9e6b7f6eaf45520a78252e1619769a696855e8d68d322ce60-23301617982353.jpg" width="517px" />
4. Clique em **Log in to Salesforce**.
5. Prossiga com o processo de autenticação e permita que o Salesforce acesse a AppsFlyer.   
   **Observação:** Se a autenticação não for bem-sucedida, você retornará à caixa de diálogo **Nova conexão** para tentar novamente.
6. Após a autenticação bem-sucedida, você retornará à caixa de diálogo **New connection** com uma indicação de que tem uma conexão ativa com o Salesforce. Agora você pode prosseguir e criar uma fonte.
7. Clique em **Create source** e siga as [instruções abaixo](#criar-uma-fonte-do-salesforce-data-cloud) para criar uma fonte do Salesforce Data Cloud.

### Criar uma fonte do Salesforce Data Cloud

Depois de autenticar sua conta do Salesforce e configurar a conexão com o Salesforce Data Cloud, a próxima etapa é criar fontes. Essas fontes fornecem à AppsFlyer os dados necessários sempre que você faz atualizações.

Acesse a aba **Fontes** usando os seguintes métodos:

* Depois de concluir a etapa anterior, clique em **Criar fonte**.
* No menu lateral do AppsFlyer, navegue até **Collaborate** > **Data Clean Room** > **+ New Source**, exibido no canto superior direito da página.

> 📘 **Nota**
>
> Ao criar sua fonte, certifique-se de que dados restritos não sejam enviados para a AppsFlyer.

**Para criar uma fonte:**

1. **Defina o nome da fonte:** Digite um <Anchor target="_blank" href="/marketers/pt/docs/data-clean-room-working-with-sources#1-name-the-source">nome para a fonte</Anchor> e clique em **Próximo**.
2. **Set source location:**
   * **Selecione a conexão:** O Salesforce Data Cloud é preenchido automaticamente após a adição da conexão. Caso contrário, selecione-o na lista de conexões.
   * **Tabela ou visualização:** Depois que a conexão do Salesforce Data Cloud for selecionada, os nomes de tabelas e visualizações da sua conta do Salesforce serão preenchidos automaticamente. Selecione a tabela ou visualização e clique em **Próximo**.  

     ![create-source-sf-3-steps.jpg](https://files.readme.io/44549ef1cd59b99610944c604c1cdfd4d598352cd106877fab3a301ce14650f8-23306070497169.jpg)
3. **Configure o esquema da fonte:** Depois que uma tabela ou visualização for selecionada, os nomes e tipos de campo serão preenchidos automaticamente. Você pode editar os tipos de campo ou remover os campos indesejados selecionando o ícone da lixeira no final da linha do campo.  
   **Observação:** Certifique-se de que pelo menos um tipo de campo funcione como identificador. Por exemplo, CUID, ID da plataforma, ID do AppsFlyer e ID com hashing SHA256.
4. Clique em **Guardar**. A nova fonte é exibida na lista de todas as fontes existentes.

<div data-zendesk-anchors="h_01HPKB2ERPGD2PS4JBSDGYW3MC=antes-de-come%C3%A7ar set-up-the-integration=configurando-o-amplitude 01HRW9TK3YZV32CXRM6Q2HCHS4=configurando-o-amplitude 01HRSFKVQNJ264M16A9X9AEP53=nota create-a-salesforce-data-cloud-connection=criar-uma-conex%C3%A3o-com-o-salesforce-data-cloud h_01HRSDCVMHQ6C5R6R4S5XRT5KQ=criar-uma-conex%C3%A3o-com-o-salesforce-data-cloud create-a-salesforce-data-cloud-source=criar-uma-fonte-do-salesforce-data-cloud h_01HRSG0P4Q38WHGQWBY3S3D11W=criar-uma-fonte-do-salesforce-data-cloud h_01HRVPJ801B0VC879APZCGKDNE=nota-1" />
