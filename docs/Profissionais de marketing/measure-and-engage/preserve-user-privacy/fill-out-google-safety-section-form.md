---
title: Formulário da seção de segurança do Google
metadata:
  keywords:
    - Google Play
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-guy-sarfatty
    - Marketers
    - Mobile Attribution
  created_at: '2022-01-19T15:00:21Z'
  edited_at: '2026-08-18T00:34:26Z'
  id: 4417197430289
  locale: pt
  section: Preserve user privacy
  section_id: 6551440878097
  url: https://support.appsflyer.com/hc/pt/articles/4417197430289
---
> **Visão geral**: desde abril de 2022, os desenvolvedores de aplicativos devem preencher o formulário da seção de segurança de dados do Google Play e publicar um link para uma política de privacidade, mesmo que não coletem nenhum dos tipos de dados especificados pelo Google. Esta página tem como objetivo fornecer informações para te ajudar a responder ao Questionário da Seção de Segurança do Google, somente em relação aos dados que a AppsFlyer processa em nome dos clientes.

Os clientes devem trabalhar em estreita colaboração com consultores jurídicos e outros profissionais para determinar exatamente como as políticas do Google se aplicam a eles e adaptar suas respostas de acordo com suas configurações e usos específicos.

<div id="disclaimer" />

#### **Isenção de responsabilidade**

As informações contidas neste artigo têm como objetivo auxiliar na resposta ao Questionário da Seção de Segurança do Google em relação **apenas** ao que a AppsFlyer processa em nome dos clientes.

É fornecido apenas para fins informativos e de conveniência. Os clientes devem trabalhar em estreita colaboração com consultores jurídicos e outros profissionais para determinar exatamente como as políticas do Google se aplicam a eles e adaptar suas respostas de acordo com suas configurações e usos específicos.

<div id="introduction" />

## Introdução

A partir de abril de 2022, os desenvolvedores de aplicativos deverão fornecer informações relacionadas às suas práticas de privacidade através da seção de segurança dedicada do Google. Especificamente, os desenvolvedores de aplicativos precisarão fornecer detalhes sobre os dados que coletam, como eles são tratados e compartilhados, inclusive por meio do uso de SDKs de terceiros.

As informações fornecidas por cada aplicativo serão exibidas na página da Google Store, ajudando os usuários finais a entender melhor as práticas de privacidade de um aplicativo.

<div id="audience" />

## público

Todos os desenvolvedores de aplicativos deverão preencher o questionário da seção de segurança e publicar um link para uma política de privacidade, mesmo que não coletem nenhum dos tipos de dados especificados pelo Google.

<div id="google-safety-form-questionnaire" />

## Formulário de segurança do Google (questionário)

O Google publicou um formulário (questionário) que os desenvolvedores de aplicativos deverão preencher. O questionário inclui as seguintes seções:

* Coleta de dados e segurança
* Tipo de dados
* Uso e tratamento de dados

Os desenvolvedores de aplicativos precisarão primeiro avaliar suas práticas de coleta e tratamento de dados antes de responder ao questionário.

Com relação ao uso da AppsFlyer, os desenvolvedores de aplicativos são lembrados de que eles têm controle total sobre como implementam e configuram a AppsFlyer, incluindo os dados coletados e como eles são usados. Portanto, cada desenvolvedor de aplicativos pode ter respostas diferentes para o questionário com base em suas práticas de dados e no uso da AppsFlyer.

Os desenvolvedores de aplicativos devem responder ao questionário de acordo com seus casos de uso específicos, configurações e integrações de parceiros.

<div id="data-collection-and-security" />

### Coleta de dados e segurança

Nesta seção, você receberá algumas perguntas gerais com resposta sim/não:

1. Seu aplicativo coleta ou compartilha algum dos tipos de dados necessários?
2. Todos os dados do usuário coletados pelo seu aplicativo são criptografados em trânsito?
3. Você fornece uma maneira para os usuários solicitarem que seus dados sejam excluídos?

Com relação ao seu uso da AppsFlyer, a AppsFlyer criptografa todos os dados em trânsito transmitidos pelo SDK. A AppsFlyer também oferece aos clientes a capacidade de excluir dados específicos do usuário final por meio de sua estrutura OpenGDPR. Para os tipos de dados coletados, consulte a tabela na seção [Tipos de dados](/docs/fill-out-google-safety-section-form#tipo-de-dados).

<div id="data-types" />

### Tipo de dados

Nesta seção, você precisará selecionar os tipos de dados coletados e responder ao seguinte:

1. Se os dados são compartilhados
2. Os dados são processados de modo efêmero?
3. Os dados são necessários ou os usuários finais podem recusar?
4. A finalidade

A seguinte tabela pressupõe as configurações padrão do software da AppsFlyer. Os desenvolvedores de aplicativos têm a responsabilidade de garantir que eles se adaptam segundo as suas configurações e usos específicos.

“Coletados” significa dados transmitidos para fora do dispositivo por qualquer meio (por exemplo, webview ou SDK).  Uma exceção é se a criptografia de ponta a ponta for usada, tornando os dados ilegíveis para qualquer pessoa.

| Tipo de dados | Coleta de dados padrão da AppsFlyer | Notas |
| --- | --- | --- |
| Informações de localização<ul><li>Localização aproximada</li><li>Localização precisa</li></ul> | Consultar notas -> | Localização precisa: não<br /><br />Localização aproximada: sim, o endereço IP é recebido e mapeado para um nível de região/cidade. |
| Informações pessoais<ul><li>Nome</li><li>Endereço de e-mail</li><li>Identificadores pessoais (ID, número ou nome da conta)</li><li>Endereço</li><li>Número de telefone</li><li>Raça e etnia</li><li>Crenças políticas ou religiosas</li><li>Orientação sexual ou identidade de gênero</li><li>Outras informações pessoais</li></ul> | Consultar notas -> | As informações pessoais não devem ser coletadas, e a AppsFlyer restringe a coleta de tais dados pessoais, como nome e endereço. No entanto, se os desenvolvedores de aplicativos tiverem configurado para transmitir e-mails ou números de telefone com hash ou se tiverem configurado um ID de conta de usuário do cliente (CUID), eles precisarão responder adequadamente. |
| Informações financeiras<ul><li>Número do cartão de crédito, cartão de débito ou conta bancária</li><li>Histórico de compras</li><li>Informações de crédito</li><li>Outras informações financeiras</li></ul> | Não   <br />  <br />Opcional<br /><br />Não  <br />Não | Informações financeiras, como cartões de crédito e informações de crédito, não devem ser coletadas.<br /><br />Se você estiver medindo compras in-app (histórico de compras), responda **Sim** |
| Saúde e fitness<ul><li>Informações de saúde</li><li>Informações de condicionamento físico</li></ul> | Não | Não deve ser coletado |
| Mensagens<ul><li>E-mails</li><li>Mensagens SMS ou MMS</li><li>Outras mensagens in-app</li></ul> | Não | Não deve ser coletado |
| Fotos ou vídeos<ul><li>Fotos</li><li>Vídeos</li></ul> | Não | Não deve ser coletado |
| Arquivos de áudio<ul><li>Gravações de voz ou som</li><li>Arquivos de música</li><li>Outros arquivos de áudio</li></ul> | Não | Não deve ser coletado |
| Calendário<ul><li>Eventos do calendário</li></ul> | Não | Não deve ser coletado |
| Atividade do aplicativo<ul><li>Visualizações de página e toques in-app</li><li>Histórico de pesquisas no aplicativo</li><li>Aplicativos instalados</li><li>Outros conteúdos gerados pelo usuário</li><li>Outras ações</li></ul> | Consultar notas -> | Por padrão, a AppsFlyer mede as inicializações do aplicativo que podem ser consideradas visualizações de página ou outras ações.<br /><br />Além disso, se você configurar seu aplicativo para medir eventos específicos no aplicativo, responda Sim de acordo com suas configurações. |
| Navegação na web | Não | Não deve ser coletado |
| Informações e desempenho do aplicativo<ul><li>Registros de falhas</li><li>Diagnósticos</li><li>Outros dados de desempenho do aplicativo</li></ul> | Não<br /><br />Sim<br /><br />Sim | Hora da inicialização ou níveis de bateria podem ser recebidos para fins detecção de fraudes. |
| Dispositivo ou outros identificadores<ul><li>Dispositivo ou outros identificadores (por exemplo, IMEI, MAC e ID do anúncio)</li></ul> | Consultar notas -> | O Android SDK da AppsFlyer, por padrão, coleta o Google Advertiser Identifier (GAID).   <br />Você pode desativar essa coleta usando [revoking AD\_ID permission](https://dev.appsflyer.com/hc/docs/install-android-sdk#revoking-the-ad_id-permission) e fazendo a chamada [setDisableAdvertisingIdentifiers](https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib). |

“Compartilhado” significa a transferência de dados para terceiros (seja no dispositivo ou fora dele).

As exceções incluem o seguinte:

* Transferências para provedores de serviços que processam os dados em seu nome e de acordo com suas instruções
* Transferências necessárias para fins legais (por exemplo, em resposta a uma solicitação do governo)
* Ação do usuário final ou com base em uma divulgação e consentimento proeminentes no aplicativo
* Dados anônimos

É importante observar que, embora a AppsFlyer atue exclusivamente como um provedor de serviços em seu nome e de acordo com suas instruções, se você estiver compartilhando dados com redes de terceiros (por exemplo, por meio de postbacks, SRNs e públicos), isso seria considerado compartilhamento.  Portanto, cada desenvolvedor de aplicativos precisará avaliar suas configurações e integrações de parceiros e responder de acordo.

<div id="ephemeral-processing" />

## Processamento efêmero

O processamento efêmero refere-se aos dados processados na memória, apenas pelo período de tempo necessário para processar uma ação específica em tempo real e sem outra finalidade. Dada a natureza dos serviços da AppsFlyer, os dados processados pela AppsFlyer em seu nome não são processados de forma efêmera.

<div id="user-choice" />

## Escolha do usuário

Em geral, os dados coletados são necessários para realizar os serviços. No entanto, os desenvolvedores de aplicativos têm a capacidade de submeter qualquer coleta de dados a controles de optar por participar ou por não participar.

<div id="purpose" />

## Propósito

O Google forneceu uma lista de finalidades a partir das quais os desenvolvedores de aplicativos devem escolher, conforme detalhado na tabela a seguir. Você deve identificar o propósito relevante.

| Propósito | Notas |
| --- | --- |
| Funcionalidade do aplicativo | Selecione se você usa os dados para ativar qualquer recurso no aplicativo. |
| Análise | Sim |
| Comunicações do desenvolvedor | Selecione se você usa os dados para enviar notificações aos usuários |
| Publicidade e marketing | Selecione se você compartilha o tipo de dados com terceiros com a finalidade de exibir anúncios de terceiros ou para promover produtos ou enviar notificações push |
| Fraude, prevenção, segurança e compliance | Sim |
| Personalização | Selecione se você usa os dados para qualquer tipo de personalização de produto. |
| Gerenciamento de contas | Selecione se você usa os dados para a configuração e o gerenciamento de contas de usuário |

<div id="see-also" />

> 📄 **Veja também**
>
> Para saber mais sobre como se preparar para a seção de segurança do Google Play e como completar o formulário obrigatório, leia esses artigos:
>
> * <Anchor target="_blank" href="https://android-developers.googleblog.com/2021/07/new-google-play-safety-section.html">Preparando-se para a nova seção de segurança do Google Play</Anchor>
> * <Anchor target="_blank" href="https://support.google.com/googleplay/android-developer/answer/10787469">Forneça informações para a seção de segurança de dados do Google Play</Anchor>

<div data-zendesk-anchors="disclaimer=isen%C3%A7%C3%A3o-de-responsabilidade h_01HDP3NTTKH3X3585J3DM6MCDC=isen%C3%A7%C3%A3o-de-responsabilidade introduction=introdu%C3%A7%C3%A3o h_01HDP3NTTK1BDTZTHNWRM3411D=introdu%C3%A7%C3%A3o audience=p%C3%BAblico h_01HDP3NTTKQE2N0HZDNGK2ZQPC=p%C3%BAblico google-safety-form-questionnaire=formul%C3%A1rio-de-seguran%C3%A7a-do-google-question%C3%A1rio h_01HDP3NTTKK6DJSF49326V3BEG=formul%C3%A1rio-de-seguran%C3%A7a-do-google-question%C3%A1rio data-collection-and-security=coleta-de-dados-e-seguran%C3%A7a h_01HDP3NTTK89K8YPT6C7S9QM3W=coleta-de-dados-e-seguran%C3%A7a data-types=tipo-de-dados h_01HDP3NTTK9DYZTQ2B64QMKGX8=tipo-de-dados ephemeral-processing=processamento-ef%C3%AAmero h_01HDP3NTTKT7C0TGVCZJ4GR9BF=processamento-ef%C3%AAmero user-choice=escolha-do-usu%C3%A1rio h_01HDP3NTTK4CT8MJ1S84MAG8VD=escolha-do-usu%C3%A1rio purpose=prop%C3%B3sito h_01HDP3NTTKD3MND388MWCC6PAT=prop%C3%B3sito h_01HDP3RBENN69F150ESQMSVP3Q=veja-tamb%C3%A9m" />
