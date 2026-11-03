---
title: Integração da Adobe Experience Platform (AEP) com o AppsFlyer Data Locker
metadata:
  keywords:
    - Advertisers
    - Marketers
    - Data Locker
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-rona-einat
    - Marketers
    - Data Locker
  created_at: '2023-03-19T06:54:23Z'
  edited_at: '2026-08-18T00:24:37Z'
  id: 13856826626321
  locale: pt
  section: Adobe
  section_id: 6551419728657
  url: https://support.appsflyer.com/hc/pt/articles/13856826626321
---
> **Em resumo:** Configure uma solução integrada com a Adobe Experience Platform (AEP) para enviar dados de eventos em nível bruto ao data lake da Adobe. A AEP é a camada de dados para todos os clientes. Ela centraliza os dados na Adobe, uma plataforma de dados do cliente que captura as jornadas do cliente, disponibiliza esses dados e permite analisá-los.

## Escritórios

A integração entre o Data Locker e a AEP permite que você use dados do AppsFlyer na Adobe Experience Platform. A integração usa o componente pronto para uso (OOTB), com suporte da plataforma de dados do cliente em tempo real (RTCDP). Para fazer upload de dados do AppsFlyer para a Adobe Experience Platform (AEP), os clientes devem primeiro configurar uma conexão com um bucket do Data Locker (GCS e AWS) e, em seguida, configurar a AEP para carregar os dados do bucket para um conjunto de dados existente ou novo.

## Configuração da integração

<span id="prerequisites"></span>**Pré-requisitos**:

* A <Anchor target="_blank" href="/marketers/pt/docs/data-locker">Data Locker</Anchor> subscription
* Uma conta da <Anchor target="_blank" href="https://business.adobe.com/products/experience-platform/adobe-experience-platform.html">Experience Platform</Anchor> com permissões de administrador

**Para configurar a integração**:

1. <span id="step-1-aws-create-an-aws-iam-user-with-bucket-access"></span>Crie um bucket com permissões para o Data Locker. Siga as instruções para armazenamento do <Anchor target="_blank" href="/marketers/pt/docs/data-locker-cloud-service-setup#gcs-storage">GCS</Anchor> ou do <Anchor target="_blank" href="/marketers/pt/docs/data-locker-cloud-service-setup#aws-storage">AWS</Anchor>.
2. Configure o Data Locker. Siga as <Anchor target="_blank" href="/marketers/pt/docs/data-locker-for-marketers#set-up-data-locker">instruções de configuração do Data Locker</Anchor> e, ao selecionar seu bucket do GCS ou da AWS, certifique-se de selecionar **Tornar esta conexão compatível com a Adobe Experience Platform**.
3. Configure o esquema do Data Locker na AEP.
   1. Faça login na AEP usando suas credenciais de administrador.
   2. Crie uma [classe de evento de experiência](https://experienceleague.adobe.com/docs/experience-platform/xdm/classes/experienceevent.html?lang=en#) do Adobe XDM.
   3. Adicione um novo grupo de campos para os campos da AppsFlyer.
   4. Crie o primeiro campo como um campo de objeto chamado AppsFlyer.  
      Este é o campo pai. Todos os outros campos criados são campos filhos desse campo de objeto.
   5. Adicione os outros campos do esquema do Data Locker. Se você estiver usando o Adobe CJA, marque customer\_user\_id como identificador de negócio.
4. Configure a fonte do bucket na AEP.
   1. Na AEP, adicione um conector de bucket (o mesmo bucket da AWS ou do GCS que você usou no Data Locker).
   2. Preencha os detalhes de autenticação obrigatórios.
   3. Clique em **Conectar à fonte**.
5. Configure o fluxo de dados no AEP.
   1. Em **AEP Select data**, selecione os relatórios relevantes do AppsFlyer Data Locker na lista de pastas do bucket.
   2. Configurado:
      * Formato dos dados: Delimited.
      * Delimitador: ",".
      * Tipo de compactação: Gzip.
   3. Clique em **próximo**.
   4. Em **Dataflow details**, preencha os detalhes do conjunto de dados e do fluxo de dados.
   5. Clique em **próximo**.
   6. Em **Scheduling**, defina a frequência como 60 minutos.
   7. Repita para cada relatório desejado do Data Locker.

> 📄 **Consulte também**
>
> * <Anchor target="_blank" href="/marketers/pt/docs/adobe-launch-sdk-extension?query=adobe">Extensão do SDK do Adobe Launch</Anchor>
> * <Anchor target="_blank" href="/marketers/pt/docs/adobe-air-plugin?query=adobe">Plug-in do Adobe Air</Anchor>

<div data-zendesk-anchors="overview=escrit%C3%B3rios h_01HDNYXDFCQQBNBB6ZQQTJS189=escrit%C3%B3rios setting-up-the-integration=configura%C3%A7%C3%A3o-da-integra%C3%A7%C3%A3o h_01HDNYXDFCEVVDS5RANQMP6K3G=configura%C3%A7%C3%A3o-da-integra%C3%A7%C3%A3o h_01HDNZ1AS5YTK6N26PD7S7C0XF=consulte-tamb%C3%A9m" />
