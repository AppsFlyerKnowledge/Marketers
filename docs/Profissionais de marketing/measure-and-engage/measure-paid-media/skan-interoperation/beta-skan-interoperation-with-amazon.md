---
title: '[Beta] Interoperabilidade do SKAN com a Amazon'
metadata:
  keywords:
    - Marketers
    - Beta feature
    - SKAdNetwork (SKAN)
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - SKAdNetwork (SKAN)
  created_at: '2024-08-15T09:36:46Z'
  edited_at: '2026-09-09T00:29:25Z'
  id: 27548444974353
  locale: pt
  section: SKAN interoperation
  section_id: 6552115163153
  url: https://support.appsflyer.com/hc/pt/articles/27548444974353
---
<span class="af-tag af-tag--beta-feature">Beta feature</span>

> **Resumo:** A interoperabilidade da SKAN permite que a Amazon compartilhe postbacks da SKAN com a AppsFlyer e permite que a AppsFlyer compartilhe com a Amazon o mapeamento de mensuração do valor de conversão.

<div id="note" />

> 📘 **Atenção**
>
> Para participar deste beta fechado, informe seu representante da Amazon.

<div id="skan-interoperability-appsflyer---amazon" />

## Interoperabilidade com SKAN: AppsFlyer &lt;-> Amazon

Se você trabalha com vários parceiros de ad networks, o recomendado é que você os configure na AppsFlyer. Desta forma, as métricas de desempenho do SKAN, enriquecidas com outras métricas como o custo, ficam disponíveis através da plataforma AppsFlyer.

<div id="scope-of-skan-interoperability-with-amazon" />

### Escopo da interoperabilidade da SKAN com a Amazon

A interoperação permite que a AppsFlyer e a Amazon compartilhem o mapeamento do valor de conversão SKAN (definido na AppsFlyer). Isso permite que ambos os lados forneçam métricas de desempenho. Veja a <Anchor target="_blank" href="/marketers/pt/docs/skan-integrated-partners-list">lista de campos de enriquecimento</Anchor> compatíveis com a Amazon.

<div id="amazon-dsp-app-install-ads-guidance" />

### Guia para anúncios de instalação do aplicativo do Amazon DSP

O Programa Alpha do Amazon DSP para iOS permite que usuários da AppsFlyer executem campanhas de download de aplicativos iOS, aproveitando a plataforma da Amazon e a SKAdNetwork da Apple para mensuração de performance com foco em privacidade. Este programa foi desenvolvido para anunciantes que buscam adquirir e engajar usuários de aplicativos iOS com eficácia. Para configurar:

**Pré-requisitos**

* Certifique-se de que o <Anchor target="_blank" href="/marketers/pt/docs/sdk-integration-overview">SDK da AppsFlyer</Anchor> esteja atualizado.
* Configure a SKAdNetwork na AppsFlyer
  * Integre o SDK da AppsFlyer no seu aplicativo.
  * Configure o esquema de valor de conversão da SKAdNetwork no Conversion Studio da AppsFlyer.
  * Verifique se a SKAdNetwork está habilitada e se o esquema de conversão está configurado corretamente.
* Aceite os Termos e Condições do Anunciante da Amazon

  * **Clientes de serviço gerenciado:** Seu representante da Amazon ajudará você a aceitar o Contrato de Audiência do Anunciante.
  * **Clientes de autoatendimento:**
    * Faça login na sua conta do Amazon Ads.
    * Acesse Amazon DSP > Campaign Manager > Events Manager > guia Conversions.
    * Se solicitado, aceite os termos para prosseguir.

  **Etapas de integração**
* Registre seu aplicativo no Amazon Ads
  * **Clientes de serviço gerenciado:** Forneça o ID do aplicativo no iTunes e o nome do seu aplicativo ao seu representante da Amazon.
  * **Clientes de autoatendimento:**
    * Faça login em advertising.amazon.com.
    * Acesse Amazon DSP > Gerenciador de Campanhas > Gerenciador de Eventos > guia Aplicativos.
    * Clique em **Add App**, selecione **AppsFlyer** como sua parceira de mensuração mobile e forneça os seguintes detalhes:
      * Plataforma: iOS
      * Nome do aplicativo: o nome do seu aplicativo
      * iTunes App ID: Encontrado na URL do aplicativo na loja de aplicativos da Apple (por exemplo, 123456789).
  * Ative a **mensuração da SKAdNetwork** e salve.
  * Verifique a guia Conversions para confirmar que a Amazon reconhece seu esquema de conversão. Se algum evento estiver faltando, entre em contato com seu representante da Amazon.

**Próximas etapas**

* Clientes gerenciados: notifique seu representante da Amazon quando o onboarding estiver concluído.
* Clientes self-service: siga o guia de configuração de campanha da Amazon para começar a criar campanhas

**Principais recursos do programa**

* Tipo de campanha: campanhas de aquisição de usuários para aplicativos iOS.
* Measurement Framework: SKAdNetwork 2.0–4.0.
* Ambiente de anúncios: anúncios in-app em propriedades da Amazon e em determinadas exchanges de terceiros.
* Relatórios: insights de campanha em tempo real por meio da AppsFlyer.

<div id="enabling-interoperation" />

### Permitindo a interoperação

A interoperação é alcançada por meio de configurações nos dashboards da AppsFlyer e da Amazon. Nenhuma interoperação ou alteração é necessária no próprio aplicativo.

**Para ativar a interoperação da SKAN da AppsFlyer com** **Amazon:**

| Passo | Ação | Detalhes |
| --- | --- | --- |
| <span id="1"></span>1 | Pré-requisitos do app | <ul><li>Integre o SDK mais recente da AppsFlyer em seu aplicativo.</li></ul> |
| <span id="2"></span>2 | Revisão das configurações de SKAN | Configure e ative a solução <Anchor target="_blank" href="/marketers/pt/docs/skadnetwork-skan-solution-guide">SKAN da AppsFlyer.</Anchor><br /><br />**Para ver as configurações da SKAN**:<ol><li>Na AppsFlyer, acesse **configurações** > **SKAN Conversion Studio**.</li><li>**Clique nas opções (⋮**) e verifique se a mensuração SKAN está ativada.<br />![skan-settings.png](https://files.readme.io/5a5b9b8b8a809336055340a14e49dacc16c5c0e95cda62c6dfb2ca9a11618d71-27548444964497.png)</li><li>Selecione seu modo de mensuração preferido.<br />Saiba mais sobre o <Anchor target="_blank" href="/marketers/pt/docs/skan-conversion-studio">SKAN Conversion Studio</Anchor>.</li><li>Anote os nomes exatos dos eventos definidos. Você precisará deles na próxima etapa.</li></ol> |
| <span id="3"></span>3 | Mapeamento de eventos in-app | Revise e, se necessário, faça alterações nos seus mapeamentos de eventos in-app da Amazon. **Pelo menos um evento in-app deve ser mapeado para a Amazon** para que a Amazon recupere o esquema e conclua a integração.<br /><br />**Para visualizar e definir mapeamentos de eventos in-app**:<ol><li>Na AppsFlyer, acesse **Configurações** > Integrações ativas.</li><li>Pesquise e selecione **Amazon Ads**.</li><li>Na seção de **Postbacks de eventos in-app:**<ol><li>[Obrigatório] Se não estiver ativada, acesse **Postbacks de eventos in-app**.</li><li>Verifique se os eventos in-app que você definiu no <Anchor target="_blank" href="/marketers/pt/docs/skan-conversion-studio">SKAN Conversion Studio</Anchor> estão mapeados para nomes de eventos da Amazon ou para os eventos no seu <Anchor target="_blank" href="/marketers/pt/docs/skan-cv-decode-map-your-cv-to-events">mapa de conversão personalizado</Anchor>.<br />**Observação:** Map `af_skad_revenue` para o nome de evento da Amazon `OFF_AMAZON_purchases`</li></ol></li><li>Clique em **Guardar integração**.</li></ol> |

<div id="see-also" />

> 📄 **Veja também**
>
> * <Anchor target="_blank" href="/marketers/pt/docs/skadnetwork-skan-solution-guide">Guia de soluções do SKAN da AppsFlyer</Anchor>

<div data-zendesk-anchors="01JEBXBFKGN066TY78WKH0VEXC=aten%C3%A7%C3%A3o skan-interoperability-appsflyer-tiktok=interoperabilidade-com-skan-appsflyer---amazon h_01HDNYZ0CT1MGCRSSP3MXTJK5V=interoperabilidade-com-skan-appsflyer---amazon scope-of-skan-interoperability-with-tiktok=escopo-da-interoperabilidade-da-skan-com-a-amazon h_01HDNYZ0CT5NZHDHDBDSCFG911=escopo-da-interoperabilidade-da-skan-com-a-amazon tiktok-for-business-guidance=guia-para-an%C3%BAncios-de-instala%C3%A7%C3%A3o-do-aplicativo-do-amazon-dsp 01HR1TPFCSXRGYC610AR7KMTS5=guia-para-an%C3%BAncios-de-instala%C3%A7%C3%A3o-do-aplicativo-do-amazon-dsp enabling-interoperation=permitindo-a-interopera%C3%A7%C3%A3o h_01HDNYZ0CTJGY3GPC9F907NEPT=permitindo-a-interopera%C3%A7%C3%A3o h_01HDNZ1BW5EBP0JCX84MTYPQ6K=veja-tamb%C3%A9m" />
