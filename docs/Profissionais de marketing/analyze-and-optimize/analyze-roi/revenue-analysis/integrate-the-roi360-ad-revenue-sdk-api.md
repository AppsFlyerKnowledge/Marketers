---
title: >-
  Guia de Integração da API SDK de Receita de Anúncios ao Nível de Impressão
  ROI360
metadata:
  keywords:
    - ROI
    - ad revenue
    - Advertisers
    - Advertiser
    - Developer
    - Developers
    - ad revenue SDK
    - Marketers
    - ROI360
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-michael-talapov
    - Marketers
    - ROI360
  created_at: '2022-01-12T09:09:07Z'
  edited_at: '2026-08-18T00:02:05Z'
  id: 4416353506833
  locale: pt
  section: Revenue analysis
  section_id: 6551069075089
  url: https://support.appsflyer.com/hc/pt/articles/4416353506833
---
> **Resumo:** A API SDK de receita de anúncios da AppsFlyer trabalha com redes de anúncios para gerar relatórios de receita com detalhe ao nível da impressão.

![mceclip1__1_.png](https://files.readme.io/202ded6950dfbf370bb48738876224936d28ecfae0c0aba09d1c49892b774cb5-31202279100177.png)

<div id="impression-level-ad-revenue-reporting-by-sdk-api" />

## Relatórios de Receita de Anúncios ao Nível de Impressão via API SDK

**Opções de Relatório de Receita de Anúncios**

A receita de anúncios é reportada à AppsFlyer com granularidade agregada (via API) ou ao nível de impressão (via SDK). Dados de impressão ao nível via SDK:

* Possui melhor atualização de dados e está disponível mais rapidamente na AppsFlyer.
* Suporta SKAN.
* É para o SDK V6.15+ da AppsFlyer. Para versões anteriores do SDK, é utilizado um conector SDK em vez da API. Links para programadores estão incluídos nesta documentação quando relevante.

**Nota:**

* As impressões de receita de anúncios são recolhidas e processadas na AppsFlyer, mas não são consideradas no seu pacote in-app.
* Existe um <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/ad-revenue-unity">plugin de receita de anúncios da AppsFlyer para Unity</Anchor>.

<div id="reporting-ad-revenue-using-the-sdk-api" />

### Relatório de Receita de Anúncios Utilizando a API SDK

**Princípios de Funcionamento do SDK**

A API SDK de receita de anúncios envia dados de receita de impressões para o SDK da AppsFlyer. Estes eventos de impressão são recolhidos e processados na AppsFlyer, e o evento de receita publicitária,  , é gerado na plataforma com a receita atribuída à fonte de UA original.

**Exibição de Dados**

O evento `af_ad_revenue` é utilizado para identificar a receita de anúncios. Este evento é utilizado em toda a plataforma, incluindo painéis e outras ferramentas de entrega de dados.

**Redes Suportadas**

A lista de redes de mediação e monetização de receitas de anúncios que podem enviar-nos dados através da API SDK é a seguinte:

* <Anchor target="_blank" href="/marketers/pt/docs/ironsource-campaign-configuration#ad-revenue-tab">Mediação Unity LevelPlay</Anchor> (antigo ironSource)
* <Anchor target="_blank" href="/marketers/pt/docs/applovin-max-ad-revenue-configuration">Applovin Max</Anchor>
* <Anchor target="_blank" href="/marketers/pt/docs/google-admob-ad-revenue-attribution-configuration">Google AdMob</Anchor>
* <Anchor target="_blank" href="/marketers/pt/docs/fyber-campaign-configuration">Fyber</Anchor>
* <Anchor target="_blank" href="/marketers/pt/docs/appodeal-campaign-configuration">Appodeal</Anchor>
* Admost
* Topon
* Topon Pte.
* Tradplus
* <Anchor target="_blank" href="/marketers/pt/docs/yandex-direct-campaign-configuration">Yandex</Anchor>
* <Anchor target="_blank" href="/marketers/pt/docs/chartboost-campaign-configuration">Chartboost</Anchor>
* customMediation (quando a solução de mediação não está na lista de parceiros de mediação suportados)
* Rede de Monetização Direta (quando a aplicação se integra diretamente com redes de monetização sem mediação)

**Frescura dos Dados**

A **API SDK envia os dados de receita para a plataforma no momento em que o anúncio é exibido. Para clientes premium do ROI360, os dados ficam disponíveis em:**

* **O tópico de nível de impressão do DataLocker à 1h e, depois disso, a cada 1 hora adicional,**
* **Os relatórios de Atividade e Coorte da AppsFlyer às 5h UTC, e depois a cada 4 horas.**

<div id="implementing-appsflyer-ad-revenue-sdk-api" />

## Implementação da API SDK de Receita de Anúncios da AppsFlyer

**Para implementar a API SDK de receitas de anúncios da AppsFlyer**:

1. <Anchor target="_blank" href="/marketers/pt/docs/roi360-guide-ad-revenue-attribution#connect-to-ad-revenue-integrated-partners">Ative a receita de anúncios ao nível do SDK na AppsFlyer</Anchor> para o parceiro que deseja conectar. **Nota**: Isto deve ser feito para cada aplicação individualmente.
2. Peça ao seu programador para integrar a API SDK de receitas de anúncios da AppsFlyer utilizando <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/ad-revenue">estas instruções</Anchor>.
3. Para registar a receita de anúncios no seu painel do SKAdNetwork, siga as <Anchor target="_blank" href="/marketers/pt/docs/skadnetwork-skan-solution-guide#recording-ad-revenue">instruções de receita de anúncios da SKAN</Anchor>.
4. Teste sua integração: depois de integrar, verifique se os eventos de receita de anúncios estão sendo recebidos usando um dos métodos a seguir:
   * No <Anchor target="_blank" href="/marketers/pt/docs/testing-the-sdk-integration-for-marketers#view-live-events">visualizador de Eventos em tempo real</Anchor>, verifique se os eventos de receita de anúncios aparecem em tempo real. Observe que o visualizador de Eventos em tempo real exibe apenas eventos enviados por dispositivos de teste registrados.
   * Na página **Configurações de receita**, edite a integração de receita de anúncios relevante e clique em **Testar conexão** para verificar se algum evento de receita de anúncios válido foi processado recentemente. Para mais informações, consulte <Anchor target="_blank" href="/marketers/pt/docs/roi360-guide-ad-revenue-attribution#connect-to-ad-revenue-integrated-partners">Conectar-se a parceiros integrados de receita de anúncios</Anchor>.

<div id="traits-and-limitations" />

## Características e Limitações

| Caraterística | Observações |
| --- | --- |
| AdMob | <ul><li>Para ativar o iLTV para AdMob, siga <Anchor target="_blank" href="https://support.google.com/admob/answer/11322405#getstarted">este link</Anchor></li><li>Para Android e Unity, a receita de impressão é reportada pelo Admob iLTV SDK em <Anchor target="_blank" href="https://developers.google.com/android/reference/com/google/android/gms/ads/AdValue#public-long-getvaluemicros">microunidades</Anchor>. Para que o valor correto da receita de anúncios em dólares seja exibido na AppsFlyer, antes de enviar o valor da receita para a AppsFlyer, divida o valor extraído do evento iLTV por 1 milhão.</li></ul> |
| Valor da Receita de Anúncios | Os eventos de impressão com valores de receita superiores a 10 dólares (ou equivalente noutras moedas) não são processados pela API do SDK. |

<div data-zendesk-anchors="impressionlevel-ad-revenue-reporting-by-sdk-API=relat%C3%B3rios-de-receita-de-an%C3%BAncios-ao-n%C3%ADvel-de-impress%C3%A3o-via-api-sdk 01H8HHAQHK6CDK8X2Y6N4GANNC=relat%C3%B3rios-de-receita-de-an%C3%BAncios-ao-n%C3%ADvel-de-impress%C3%A3o-via-api-sdk reporting-ad-revenue-using-the-sdk-API=relat%C3%B3rio-de-receita-de-an%C3%BAncios-utilizando-a-api-sdk 01H8HHAQHKQ3H3R21Z1JYNJ2EE=relat%C3%B3rio-de-receita-de-an%C3%BAncios-utilizando-a-api-sdk implementing-generic-appsflyer-ad-revenue-sdk-API=implementa%C3%A7%C3%A3o-da-api-sdk-de-receita-de-an%C3%BAncios-da-appsflyer 01H8HHAQHKCXKPJJE8EDT1J9CR=implementa%C3%A7%C3%A3o-da-api-sdk-de-receita-de-an%C3%BAncios-da-appsflyer traits-and-limitations=caracter%C3%ADsticas-e-limita%C3%A7%C3%B5es 01H8HHAQHMCSVQ2ZAT3G7XJKAN=caracter%C3%ADsticas-e-limita%C3%A7%C3%B5es" />
