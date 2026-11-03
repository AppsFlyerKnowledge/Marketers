---
title: Interoperação da SKAN com TikTok for Business
metadata:
  keywords:
    - Advertisers
    - ios14
    - Marketers
    - SKAdNetwork (SKAN)
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - SKAdNetwork (SKAN)
  created_at: '2021-03-14T12:05:58Z'
  edited_at: '2026-08-18T00:31:56Z'
  id: 360018499098
  locale: pt
  section: SKAN interoperation
  section_id: 6552115163153
  url: https://support.appsflyer.com/hc/pt/articles/360018499098
---
> **Resumo:** A interoperabilidade com SKAN permite que o TikTok compartilhe postbacks SKAN com a AppsFlyer e permite que a AppsFlyer compartilhe seu mapeamento de mensuração do valor de conversão com o TikTok.

## Interoperabilidade com SKAN: AppsFlyer &lt;-> TikTok

Se você trabalha com vários parceiros de ad networks, o recomendado é que você os configure na AppsFlyer. Assim, as métricas de performance da SKAN, enriquecidas com outras métricas como custo, estarão disponíveis através da plataforma da AppsFlyer.

### Escopo da interoperabilidade da SKAN com o TikTok

A interoperação permite que a AppsFlyer e o TikTok compartilhem o mapeamento do valor de conversão SKAN (definido na AppsFlyer). Isso permite que ambos os lados forneçam métricas de desempenho. Ao ativar a integração do TikTok for Business (seja a integração antiga ou <Anchor target="_blank" href="/marketers/pt/docs/tiktok-for-business-advanced-srn-integration-setup">avançada do SRN</Anchor>), a AppsFlyer fornece eventos do TikTok para fins de otimização. Veja a <Anchor target="_blank" href="/marketers/pt/docs/skan-integrated-partners-list">lista de campos de enriquecimento</Anchor> compatíveis com o TikTok.

### Guia do TikTok for Business

Ao configurar suas campanhas do TikTok for Business, leia <Anchor target="_blank" href="https://ads.tiktok.com/help/article?aid=10000858">Impacto e Guia do iOS 14 do TikTok e</Anchor> leve em consideração o seguinte:

* Certifique-se de que o <Anchor target="_blank" href="/marketers/pt/docs/sdk-integration-overview">SDK da AppsFlyer</Anchor> esteja atualizado.
* [Configure um ID do aplicativo TikTok para cada aplicativo](https://ads.tiktok.com/help/article?aid=10001060) que você anuncia no TikTok for Business.
  * O App ID do TikTok é um código exclusivo gerado no TikTok Ads Manager e usado pelo TikTok para confirmar que o anunciante é o proprietário dos anúncios.
  * Embora não seja obrigatório, é recomendável inserir o ID do aplicativo de todos os seus aplicativos.  
    Isso ajuda você a controlar melhor seus dados do TikTok For Business e desbloquear produtos adicionais.
  * **Para adicionar mais de um TikTok App ID:**
    1. Insira seu primeiro TikTok App ID.
    2. Pressione **Enter.**
    3. Insira seu próximo TikTok App ID.
  * Configurar um TikTok App ID não afeta seus dados na AppsFlyer.
  * [Saiba mais sobre os requisitos do TikTok App ID para iOS 14](https://ads.tiktok.com/help/article?aid=10001070).
* [Mapeamento completo de eventos de conversão](/docs/skan-interoperation-with-tiktok-for-business#3) para bytedanceglobal\_int e tiktokglobal\_int.
* Analise o guia sobre limitação de campanhas e consolidação de contas/campanhas.

Trabalhe diretamente com seu gerente de conta do TikTok for Business na configuração e estratégia da SKAN.

O TikTok é compatível com SKAN da seguinte forma:

* Mensuração e otimização por meio da API de mensuração de conversão.
* Relatórios de campanhas dedicadas do iOS 14 no TikTok for Business.

### Limites de campanha para campanhas dedicadas do iOS 14

Devido às limitações da API SKAN, o TikTok for Business é compatível com o seguinte ao criar campanhas dedicadas para iOS 14 (aplicáveis a anúncios de instalação de aplicativos e anúncios dinâmicos de produtos para prospecção de aplicativos):

* ​Os aplicativos iOS estão limitados a 15 campanhas com 5 grupos de anúncios por campanha.
* Campanhas dedicadas para iOS 14:
  * Podem ser criadas a partir de várias contas de anúncios, mas o número total de campanhas ativas é limitado a 15.
  * Todos os objetivos relevantes contam para o limite (15) e, depois de atingirem o limite da campanha, os anunciantes devem esperar pelo menos 72 horas após uma campanha ter sido pausada, desativada ou excluída para liberar um espaço na campanha antes de começar uma nova campanha.

### Permitindo a interoperação

A interoperação é alcançada por meio de configurações nos painéis da AppsFlyer e do TikTok for Business. Nenhuma interoperação ou alteração é necessária no próprio aplicativo.

Para ativar a interoperação da SKAN da AppsFlyer com o TikTok for Business:

| Passo | Ação | Detalhes |
| --- | --- | --- |
| <span id="1"></span>1 | Pré-requisitos do app | <ul><li>Integre o SDK mais recente da AppsFlyer em seu aplicativo.</li></ul> |
| <span id="2"></span>2 | Revisão das configurações de SKAN | Configure e ative a solução <Anchor target="_blank" href="/marketers/pt/docs/skadnetwork-skan-solution-guide">SKAN da AppsFlyer.</Anchor><br /><br />**Para ver as configurações da SKAN**:<ol><li>Na AppsFlyer, acesse **configurações** > **SKAN Conversion Studio**.</li><li>**Clique nas opções (⋮**) e verifique se a mensuração SKAN está ativada.<br />![skan-settings.png](https://files.readme.io/5a5b9b8b8a809336055340a14e49dacc16c5c0e95cda62c6dfb2ca9a11618d71-27548444964497.png)</li><li>Selecione seu modo de mensuração preferido.<br />Saiba mais sobre o <Anchor target="_blank" href="/marketers/pt/docs/skan-conversion-studio">SKAN Conversion Studio</Anchor>.</li><li>Anote os nomes exatos dos eventos definidos. Você precisará deles na próxima etapa.</li></ol> |
| <span id="3"></span>3 | Mapeamento de eventos in-app | Revise, e se necessário, faça alterações em seus mapeamentos de eventos in-app do TikTok for Business.<br /><br />**Para visualizar e definir mapeamentos de eventos in-app**:<ol><li>Na AppsFlyer, acesse **Configurações** > Integrações ativas.</li><li>Pesquise e selecione **TikTok For Business**.</li><li>Na aba **Integração**, verifique se a integração com o TikTok for Business está ativada e configurada.</li><li>Na seção de **Postbacks de eventos in-app:**<ol><li>[Obrigatório] Se não estiver ativada, acesse **Postbacks de eventos in-app**.</li><li>Verifique se os eventos in-app que você definiu no <Anchor target="_blank" href="/marketers/pt/docs/skan-conversion-studio">SKAN Conversion Studio</Anchor> estão mapeados para nomes de eventos do TikTok for Business ou para os eventos em seu mapa de conversão personalizado.<br />**Atenção:** Mapeie apenas `af_skad_revenue` para o evento `Purchase` do TikTok quando seu esquema de conversão SKAN mensurar a receita total.<br />[![](https://files.readme.io/a5b5f9cccacd4cc531a09413e4e5040a8214abc3a8a7f795fbec678e81ab603e-25706935571217.jpg)](https://files.readme.io/a5b5f9cccacd4cc531a09413e4e5040a8214abc3a8a7f795fbec678e81ab603e-25706935571217.jpg)</li></ol></li><li>Clique em **Salvar integração.**</li></ol> |

> 📄 **Veja também**
>
> * <Anchor target="_blank" href="/marketers/pt/docs/skadnetwork-skan-solution-guide">Guia de soluções da AppsFlyer para SKAN</Anchor>

<div data-zendesk-anchors="skan-interoperability-appsflyer-tiktok=interoperabilidade-com-skan-appsflyer---tiktok h_01HDNYZ0CT1MGCRSSP3MXTJK5V=interoperabilidade-com-skan-appsflyer---tiktok scope-of-skan-interoperability-with-tiktok=escopo-da-interoperabilidade-da-skan-com-o-tiktok h_01HDNYZ0CT5NZHDHDBDSCFG911=escopo-da-interoperabilidade-da-skan-com-o-tiktok tiktok-for-business-guidance=guia-do-tiktok-for-business 01HR1TPFCSXRGYC610AR7KMTS5=guia-do-tiktok-for-business campaign-limits-for-dedicated-ios-14-campaigns=limites-de-campanha-para-campanhas-dedicadas-do-ios-14 h_01HDNYZ0CT7RNDAEWYKBHS6PET=limites-de-campanha-para-campanhas-dedicadas-do-ios-14 enabling-interoperation=permitindo-a-interopera%C3%A7%C3%A3o h_01HDNYZ0CTJGY3GPC9F907NEPT=permitindo-a-interopera%C3%A7%C3%A3o h_01HDNZ1BW5EBP0JCX84MTYPQ6K=veja-tamb%C3%A9m" />
