---
title: Audiências - Use eventos da Braze na criação de audiências
metadata:
  keywords:
    - Advertisers
    - Premium Feature
    - Marketers
    - Audience Segmentation
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-neama-benhabib
    - Marketers
    - Audience Segmentation
  created_at: '2021-11-17T09:55:26Z'
  edited_at: '2026-10-05T00:17:54Z'
  id: 4411130243217
  locale: pt
  section: Audiences
  section_id: 6551336428945
  url: https://support.appsflyer.com/hc/pt/articles/4411130243217
---
> **At a glance:** **De relance:** Envie eventos de interação de mensagens do Braze para o AppsFlyer Audiences e utilize-os para aumentar a precisão nas suas definições de público.

Ao definir uma ligação de entrada entre a sua conta Braze e o AppsFlyer Audiences, está a integrar os dados de eventos de interação de mensagens do Braze no Audiences. Você pode então usar esses dados em <Anchor target="_blank" href="/marketers/pt/docs/audiences-guide#tudo-sobre-conjuntos-de-regras">conjuntos de regras</Anchor> ao definir audiências.

> 🚧 **Important**
>
> **Pré-requisitos**
>
> * Os SDKs do Braze e do AppsFlyer precisam de estar integrados na sua app.
> * É necessário subscrever à funcionalidade **Currents** no Braze.

<div id="set-up-the-braze-incoming-connection" />

## Configurar a ligação de entrada do Braze

São 3 os passos principais para configurar a ligação de entrada do Braze:

1. [Configurar o SDK da AppsFlyer](/docs/audiences-use-braze-events-in-audience-creation#set-up-the-appsflyer-sdk)
2. [Criar uma ligação de entrada no AppsFlyer](/docs/audiences-use-braze-events-in-audience-creation#create-an-incoming-braze-connection-in-appsflyer)
3. [Criar um Current no Braze](/docs/audiences-use-braze-events-in-audience-creation#create-a-current-in-braze)

<Accordion title="Configurar o SDK da AppsFlyer">

Para criar uma ligação de entrada a partir do Braze, o SDK da AppsFlyer nas suas apps tem de estar configurado para transmitir o **ID Externo do Braze** de cada utilizador para o AppsFlyer. Pode fazer isto utilizando:

* Parâmetro de ID Externo do Braze
* Campo CUID

<div id="using-a-braze-external-id-parameter" />

#### **Uso de um parâmetro de ID Externo do Braze**

Pode configurar um parâmetro dedicado para passar a ID Externa do Braze para o AppsFlyer utilizando a `setPartnerData`função do SDK da AppsFlyer. Exemplos de utilização:

<Tabs>
<Tab title="Android / iOS">

```java
Map<String, Object> brazeData = new HashMap<>();
partnerData.put("external_user_id", "some-braze-external-id-value"); AppsFlyerLib.getInstance().setPartnerData("braze_int", brazeData);
```

</Tab>

<Tab title="https://files.readme.io/f28d0aac1797ee18fdc6083d9ea6d5d2f87d37a894a6c27ab0ea9b6ca51c53a1-49839256665233.png">

```objectivec
NSDictionary *brazeInfo = @{
@"external_user_id":@"some-braze-external-id-value"
};
[[AppsFlyerLib shared] setPartnerDataWithPartnerId:@"braze_int"
partnerInfo:brazeInfo];
```

</Tab>
</Tabs>

<div id="using-the-cuid-field" />

#### **Utilizar o campo CUID**

Não é necessário configurar um parâmetro dedicado para o ID Externo do Braze se:

* Tiver configurado o SDK para enviar à AppsFlyer um <Anchor target="_blank" href="/marketers/pt/docs/customer-user-id-field-cuid">CUID</Anchor> para cada utilizador
* O CUID tiver o mesmo valor que o ID Externo do Braze

Nesse caso, pode simplesmente selecionar a **opção CUID** como parâmetro do SDK ao [criar a sua ligação de entrada do Braze](/docs/audiences-use-braze-events-in-audience-creation#create-an-incoming-braze-connection-in-appsflyer).

</Accordion>

<Accordion title="Criar uma ligação de entrada do Braze no AppsFlyer">

**Siga os seguintes passos para criar uma ligação de entrada no AppsFlyer:**

1. No AppsFlyer, no menu lateral, selecione **Envolver** > **Audiências**
2. Na página Audiências, aceda a **Ligações > separador Entrada** .
3. Clique no botão **Nova ligação de entrada**.
4. Escolha Braze na lista de parceiros disponíveis.
5. Clique no botão **Guardar** para criar a ligação.  
   A janela de diálogo **Credenciais de ligação** irá abrir-se.
6. Copie as credenciais de ligação para utilizar ao configurar a ligação com o AppsFlyer Audiences na plataforma Braze:
   * ID da chave de acesso
   * Chave de acesso secreta
   * Nome do repositório
   * Caminho da pasta
7. Selecione o parâmetro SDK que está a usar para enviar o ID Externo do Braze:
   * ID Externo do Braze
   * CLIQUE

</Accordion>

<Accordion title="Criar um Current no Braze">

**Siga estes passos para criar uma Corrente no Braze:**

1. Aceda à secção de **Integração** na barra de menu à esquerda.
2. Clique em **Correntes.**
3. Clique no botão **Criar Corrente**.
4. Escolha **Exportação de Dados do Amazon S3.**
5. Na secção **Criar Integração de Correntes**:
   1. Insira um nome para a Corrente (por exemplo, AppsFlyer Audiences).
   2. Introduza o e-mail de um membro da sua equipa que o Braze notificará em caso de problemas com as credenciais da Corrente.
6. Na secção **Credenciais**:
   1. Mantenha a opção **AWS Secret Access Key** selecionada (é a opção predefinida).
   2. Insira as credenciais que copiou do AppsFlyer nos campos adequados.
   3. Deixe a opção **Ativar Encriptação** desmarcada.
7. Em **Definições Gerais**, mantenha **Incluir eventos de utilizadores anónimos** marcado.
8. Na secção **Eventos de Envolvimento de Mensagens**, selecione os eventos que pretende que o Braze envie para o AppsFlyer. Veja a lista de eventos suportados [abaixo](/docs/audiences-use-braze-events-in-audience-creation#eventos-suportados).
9. Na secção Comportamento do Cliente e Eventos do Utilizador, mantenha a opção **Acompanhar Comportamento do Cliente e Eventos do Utilizador** desativada.
10. Clique no botão **Lançar Corrente** para guardar a configuração e começar a enviar eventos de envolvimento de mensagens do Braze para Audiências.

<div id="supported-events" />

#### eventos suportados

> 📘 **Note**
>
> **Eventos do Braze compatíveis**
>
> * Alteração do Estado do Grupo de Assinaturas
> * Clique em E-mail
> * E-mail Aberto
> * Enviar E-mail
> * Entrega de E-mail
> * Marcar E-mail como Spam
> * Cancelar Subscrição de E-mail
> * Devolução de E-mail
> * Rejeição Suave de E-mail
> * Abertura de Push
> * Envio por Push
> * Rejeição de Push
> * Push em Primeiro Plano no iOS
> * Envio de SMS/MMS

</Accordion>

<div id="using-braze-data-in-audiences" />

## Utilização de dados Braze em Audiências

Depois que a conexão de entrada do Braze estiver configurada, os eventos de engajamento que você definiu aparecerão como opções nos <Anchor target="_blank" href="/marketers/pt/docs/audiences-guide#ruleset-filters">filtros do conjunto de regras</Anchor> para definir audiências.

<Image align="center" alt="audiences_braze_ruleset.png" src="https://files.readme.io/766a5ec25de3cf82c1411ce25864a5c8ce6c77ac338c20699e61be1c45ae3d98-33375723752337.png" />

**Nota:** Demora cerca de 24 horas para que os eventos de envolvimento de mensagens do Braze estejam disponíveis na AppsFlyer após lançar a campanha no Braze.

<div data-zendesk-anchors="set-up-the-braze-incoming-connection=configurar-a-liga%C3%A7%C3%A3o-de-entrada-do-braze h_01HKW0BS5H1ANWAJZTVBWDQHJH=configurar-a-liga%C3%A7%C3%A3o-de-entrada-do-braze using-a-braze-external-id-parameter=uso-de-um-par%C3%A2metro-de-id-externo-do-braze h_01HKW0BS5HGB2RYGWNXT1M163C=uso-de-um-par%C3%A2metro-de-id-externo-do-braze using-the-cuid-field=utilizar-o-campo-cuid h_01HKW0BS5HQJZRR60VKBCWGHQB=utilizar-o-campo-cuid supported-events=eventos-suportados h_01HKW0BS5JM8A9XFVX22KWFE3H=eventos-suportados using-braze-data-in-audiences=utiliza%C3%A7%C3%A3o-de-dados-braze-em-audi%C3%AAncias h_01HKW0BS5JTZQ71HFE305ZT1CS=utiliza%C3%A7%C3%A3o-de-dados-braze-em-audi%C3%AAncias" />
