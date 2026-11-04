---
title: Prepare-se para a avaliação da App Store—tabelas nutricionais
metadata:
  keywords:
    - iOS
    - iTunes
    - Apple
    - IDFA
    - Guidelines
    - IFA
    - Ad Tracking
    - Advertisers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-guy-sarfatty
    - Marketers
    - Mobile Attribution
  created_at: '2014-04-12T13:28:26Z'
  edited_at: '2026-08-18T00:34:32Z'
  id: 207032086
  locale: pt
  section: Preserve user privacy
  section_id: 6551440878097
  url: https://support.appsflyer.com/hc/pt/articles/207032086
---
> **Visão geral**: a partir do iOS 14, os desenvolvedores de aplicativos devem fornecer informações da App Store relacionadas às Práticas de Privacidade quando enviarem um aplicativo. A App Store publica essas informações no formato de *rótulo nutricional.*

**Observação dos nossos advogados:** *o conteúdo aqui mencionado não é um aconselhamento jurídico. Ele serve apenas para sua informação e conveniência. Trabalhe diretamente com consultores jurídicos e outros profissionais para determinar exatamente como as políticas da Apple se aplicam a você.*

<div id="nutrition-labels-and-the-app-store-review" />

## Rótulos nutricionais e avaliação da App Store

* Para gerar os rótulos de privacidade, os desenvolvedores de aplicativos devem responder a um questionário ao enviar o aplicativo para o App Store Connect, que inclui as seguintes seções:
  * Tipos de dados coletados
  * [Finalidades para as quais os dados são coletados](/docs/preparing-for-the-app-store-review-nutrition-labels#finalidades-do-uso-de-dados)
  * [Se os tipos de dados estão conectados a uma identidade](/docs/preparing-for-the-app-store-review-nutrition-labels#dados-conectados-a-uma-identidade)
  * Se os dados são usados para acompanhamento (inclusive em relação a qualquer serviço de terceiros ou SDK incluído em um aplicativo).
* Desenvolvedores de aplicativos:
  * Têm controle total sobre como implementar e configurar o software da AppsFlyer, quais dados coletar e como os dados são usados.
  * Podem ter respostas muito diferentes para o questionário baseado em como eles configuram o software da AppsFlyer e os pontos de dados que eles optam por coletar.
* De acordo com o entendimento da AppsFlyer sobre a política da Apple, a AppsFlyer não *rastreia usuários.* No entanto, os desenvolvedores de aplicativos devem responder ao questionário de acordo com seus usos específicos e integrações de parceiros.
* Se você usar dados coletados para fins de rastreamento, deve implementar o prompt da ATT.
* O seguinte pressupõe as configurações padrão do software da AppsFlyer. Os desenvolvedores de aplicativos têm a responsabilidade de garantir que eles se adaptam segundo as suas configurações e usos específicos.

<div id="data-types-collected" />

#### Tipos de dados coletados

| **Tipo de dados** | **Coleta de dados da AppsFlyer** | **Observações** |
| --- | --- | --- |
| **Informações de contato**<ul><li>Nome</li><li>Endereço de e-mail (incluindo hash)</li><li>Número de telefone (incluindo hash)</li><li>Endereço físico</li><li>Outras informações de contato do usuário</li></ul> | Não | As informações de contato não devem ser coletadas. No entanto, se você configurou seu aplicativo para transmitir e-mails ou números de telefone com hash, forneça tal informação no questionário da App Store. |
| **Fitness** | Não | Não colete |
| **Informações financeiras**<ul><li>Informações de pagamento</li><li>Informações de crédito</li><li>Outras informações financeiras</li></ul> | Não | Não colete |
| **Informações de localização**<ul><li>Localização precisa</li><li>Localização vaga</li></ul> | Ver observações | <ul><li>Localização precisa: não</li><li>Localização vaga: sim. O endereço IP é coletado e mapeado para fornecer uma locação geográfica vaga.</li></ul> |
| **Informações sensíveis** | Não | Não colete |
| **Contatos** | Não | Não colete |
| **Conteúdo do usuário**<ul><li>E-mails ou mensagens de texto</li><li>Fotos ou vídeos</li><li>Dados de áudio</li></ul> | Não | Não colete |
| **Histórico de navegação** | Não | Não colete |
| **Histórico de pesquisa** | Não | Não colete |
| **Identificadores**<ul><li>ID do usuário</li><li>ID do dispositivo (IDFA)</li></ul> | OPCIONAL | <ul><li>ID de usuário: desenvolvedores de aplicativos podem definir e transmitir ID de usuário (CUID)</li><li>ID do dispositivo: A ID de publicidade (IDFA) é coletada somente quando acessível.</li></ul> |
| **Compras**<ul><li>Histórico de compras</li></ul> | OPCIONAL | Desenvolvedores de aplicativos podem optar por configurar determinados eventos de compra in-app para mensuração. |
| **Dados de uso**<ul><li>Interação com produtos</li><li>Dados publicitários</li><li>Outros dados de uso</li></ul> | <ul><li>Sim</li><li>OPCIONAL</li><li>Não</li></ul> | <ul><li>Interações com o produto: As inicializações do aplicativo são medidas, assim como qualquer outra interação do usuário configurada pelo desenvolvedor do aplicativo.</li><li>Dados publicitários: serão recebidos se o desenvolvedor do aplicativo usar o módulo de receita publicitária da AppsFlyer.</li></ul> |
| **Dados de diagnóstico**<ul><li>Dados de falha</li><li>Dados de desempenho</li><li>Outros dados de diagnóstico</li></ul> | <ul><li>Não</li><li>Sim</li><li>Não</li></ul> | Hora da inicialização e/ou níveis de bateria podem ser recebidos para detecção de fraudes. |
| **Outros dados**<ul><li>Outros tipos de dados</li><li>IDFV</li></ul> | Sim | <ul><li>Informações técnicas do dispositivo (por exemplo, sistema operacional, tipo de dispositivo, idioma, tamanho da tela etc) ou informações sobre a rede (por exemplo, endereço de IP, agente usuário HTTP) são recebidas pela AppsFlyer.</li><li>A AppsFlyer aplica uma ID de instalação a cada instalação de aplicativo chamada AF ID.</li><li>IDFV é coletada</li></ul> |

<div id="data-use-purposes" />

### Finalidades do uso de dados

A Apple tem uma lista de finalidades a partir da qual os desenvolvedores de aplicativos precisam escolher, conforme detalhado na tabela a seguir. Você precisa identificar as finalidades correspondentes a cada tipo de dados relacionados ao seu uso específico.

| Finalidade do dado | Seleção baseada em como os dados da AppsFlyer serão usados |
| --- | --- |
| Publicidade de terceiros | Selecione se você compartilhar o tipo de dado com terceiros para exibir anúncios de terceiros no seu aplicativo. |
| Publicidade ou marketing do desenvolvedor | Selecione se você usar para exibir anúncios primários no seu aplicativo (inclusive se você compartilhar com terceiros para exibir seus anúncios) ou para outros fins de marketing. |
| Análise | Sim |
| Personalização de produto | Selecione se você usar dados para qualquer personalização de produto. |
| Funcionalidade do aplicativo | Sim |
| Outras finalidades | Selecione se você usar os dados para qualquer finalidade diferente das mencionadas. |

<div id="data-linked-to-an-identity" />

### Dados conectados a uma identidade

Os tipos de dados coletados através da AppsFlyer geralmente são conectados a um identificador como ID do dispositivo (quando disponível) ou a outros identificadores, como IDs emitidas pelo cliente, quando configuradas.

Portanto, os desenvolvedores de aplicativos devem selecionar **Sim** quando perguntados se os dados estão conectados a uma identidade.

<div id="see-also" />

> 📄 **Veja também**
>
> * <Anchor target="_blank" href="https://www.appsflyer.com/services-privacy-policy/">Política de Privacidade dos Serviços AppsFlyer</Anchor>: como a AppsFlyer gerencia e usa dados.
> * <Anchor target="_blank" href="https://developer.apple.com/app-store/app-privacy-details/">Detalhes de privacidade do aplicativo na App Store da Apple</Anchor>.

<div data-zendesk-anchors="nutrition-labels-and-the-app-store-review=r%C3%B3tulos-nutricionais-e-avalia%C3%A7%C3%A3o-da-app-store h_01HE7T7J409620K5KX5XKPEQVZ=r%C3%B3tulos-nutricionais-e-avalia%C3%A7%C3%A3o-da-app-store data-types-collected=tipos-de-dados-coletados h_01HE7T7J4004XVJTMF6S964DVB=tipos-de-dados-coletados data-use-purposes=finalidades-do-uso-de-dados h_01HE7T7J4098NNW8D0BCD3EFBJ=finalidades-do-uso-de-dados data-linked-to-an-identity=dados-conectados-a-uma-identidade h_01HE7T7J41BJG9GTBWMVKG7031=dados-conectados-a-uma-identidade h_01HE7TES34MEF1XR4B6BDEMJW4=veja-tamb%C3%A9m" />
