---
title: Guia de integração do Protect360
metadata:
  keywords:
    - Marketers
    - Protect360
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-yanai
    - Marketers
    - Protect360
  created_at: '2025-04-21T09:58:52Z'
  edited_at: '2026-08-18T00:08:09Z'
  id: 34554022072209
  locale: pt
  section: Protect your traffic
  section_id: 6551015912465
  url: https://support.appsflyer.com/hc/pt/articles/34554022072209
---
> **Resumo:** comece a proteger seus investimentos de marketing com esse guia de integração passo a passo, e impulsione o valor do Protect360 em apenas 6 semanas.

## **Cronograma de integração e o que esperar**

Esse guia traz um onboarding que dura 6 semanas:

* **Configuração (semanas 1–3)**: Faça a integração e validação do Protect360.
* **Otimização (semanas 3–5)**: Otimize com base em insights iniciais.
* **Reconciliação (semanas 5–6)**: Faça a reconciliação dos dados de fraude com seus parceiros de anúncios.
* **Proteção avançada (semana 6+) [opcional]**: Ative camadas avançadas de proteção contra fraudes.

## **Sobre o Protect360**

O Protect360 é uma solução avançada de proteção contra fraudes projetada para detectar, prevenir e responder a fraudes de anúncios. Usando IA e detecção em tempo real, ele ajuda a bloquear fraudes, reduzir desperdícios e proteger seu marketing contra ameaças como injeção de cliques, instalações falsas e bots. Ele oferece mais controle e total transparência por meio de recursos como regras de validação e Fraud Protection Studio.

<div id="setup-weeks-1-3" />

<Accordion title="Configuração (semanas 1–3)">

Nessa etapa, o foco é enviar dados do aplicativo para a AppsFlyer, definir as configurações básicas de proteção e alinhar seus termos de BI com a AppsFlyer.

**Dados de eventos in-app**

Você pode enviar esses dados usando dois métodos diferentes: SDK e Server-to-Server (S2S). Dependendo do método usado, algumas ações podem ser necessárias:

* **SDK**: Nenhuma ação necessária
* **Server-to-Server (S2S)**: Certifique-se de que os eventos sejam enviados pela API3. <Anchor target="_blank" href="/marketers/pt/docs/bulletin-upgrading-the-appsflyer-s2s-api">Saiba mais aqui.</Anchor>

> 📘 **Atenção**
>
> Se você não souber qual você usa, fale com sua equipe de desenvolvimento ou operações de marketing

#### **Configurações do Fraud Protection Studio**

O Fraud Protection Studio permite que você avalie o impacto das diferentes camadas da solução de proteção contra fraudes da AppsFlyer. Ele permite que você faça uma distinção clara da detecção e da aplicação do bloqueio de fraudes.

Entender essas diferenças e as opções disponíveis é fundamental para tomar decisões informadas:

* **Implemented** (padrão): Bloqueia automaticamente atividades fraudulentas em tempo real ou as sinaliza como fraude pós-atribuição. Esse esquema é indicado se a prevenção imediata é um dos seus objetivos.
* **Tagged**: A fraude é detectada e sinalizada com uma tag, mas permanece válida para atribuição, permitindo que você analise e revise sem um bloqueio automático. Escolha essa opção se preferir flexibilidade e análises iniciais mais detalhadas antes de bloquear.

> 📘 **Atenção**
>
> Você pode alternar entre os modos **Implemented** e **Tagged** a qualquer momento (<Anchor target="_blank" href="/marketers/pt/docs/user-management">somente admins</Anchor>), a depender dos seus objetivos de negócios. <Anchor target="_blank" href="/marketers/pt/docs/beta-fraud-protection-studio#key-concepts">Saiba mais aqui</Anchor>.

<Image alt="" src="https://files.readme.io/70bf87550e949fed4898270f731424e948a24f7cf2cff39e81ba44473af94189-35506628777105.png" width="624px" />

Dica: Nessa etapa, enquanto sua equipe se familiariza com o Protect360, recomendamos que você veja o card de <Anchor target="_blank" href="/marketers/pt/docs/beta-fraud-protection-studio#app-detection-evaluation">**avaliação da detecção para aplicativos**</Anchor> no Fraud Protection Studio para testar e entender como essas configurações são implementadas no nível do aplicativo.

#### **Configuração de conexão de dados**

Você pode exportar os dados do Protect360 de três formas diferentes: <Anchor target="_blank" href="/marketers/pt/docs/protect360-raw-data-reports#sobre-os-relatórios-de-dados-brutos-do-protect360">Relatório de dados brutos</Anchor>, <Anchor target="_blank" href="/marketers/pt/docs/protect360-raw-data-reports#pull-api">Pull API</Anchor> ou <Anchor target="_blank" href="/marketers/pt/docs/protect360-raw-data-reports#data-locker">Data Locker</Anchor>. Independentemente da sua escolha, é importante configurar suas conexões de dados para garantir relatórios precisos e análises eficazes.

<Image alt="" src="https://files.readme.io/d6a96db3fd8ffd3ed6f3f8abb680b4f3778a457142166d69e1ade7fe3263709e-35506660373393.png" width="624px" />

> 🚧 **Importante!**
>
> Para aproveitar ao máximo o Protect360, exporte o <Anchor target="_blank" href="/marketers/pt/docs/protect360-raw-data-reports#postattribution-reports">relatório pós-atribuição</Anchor> no 8o dia de cada mês, para que você possa comparar os resultados com seus parceiros.

#### **Como exibir hijacked installs (instalações sequestradas) corretamente em seu BI**

Para garantir o alinhamento e a granularidade dos dados de proteção contra fraudes em seus sistemas, você pode usar os **relatórios de dados brutos, Pull APIs ou Data Locker para visualizar hijacked installs em seu BI.**

#### **Relatório de dados brutos**

Para exibir hijacked installs em seu BI:

1. Procure o campo **Rejected Reason Value**.
2. O campo será preenchido com um dos seguintes:
   1. Blank, organic, contributor1, contributor2, etc.
3. Informe a sua equipe de BI sobre o significado de cada um, para que ela possa entender os termos e suas implicações.

* Blank - sem hijacked installs
* Organic - alterar a atribuição para orgânico
* Contributor1, contributor2, contributor3, etc. - atribuição correta para o canal de mídia especificado.

> 📘 **Atenção**
>
> Para mais informações sobre seus dados **tagged**, acesse esses 4 relatórios de dados brutos:
>
> * Tagged Installs
> * Tagged post attribution installs
> * Eventos in-app com tags
> * Tagged post attribution in-app events

![](https://files.readme.io/70d33b5c4359f839da8d46c4b07baf277148fc4d5c6ebc7a3e8b2d600bd7c5fc-35506628785169.png)

#### **Extrair API**

Para exibir hijacked installs em seu BI:

4. Procure o campo **Rejected Reason Value**.
5. O campo será preenchido com um dos seguintes:
   1. Blank, organic, contributor1, contributor2, etc.
6. Informe a sua equipe de BI sobre o significado de cada um, para que ela possa entender os termos e suas implicações.

* Blank - sem hijacked installs
* Organic - alterar a atribuição para orgânico
* Contributor1, contributor2, contributor3, etc. - atribuição correta para o canal de mídia especificado.

#### **Relatório do Data Locker**

Para exibir hijacked installs em seu BI:

7. Procure o campo **validation\_reason\_value**.
8. O campo será preenchido com um dos seguintes:
   1. Blank, organic, contributor1, contributor2, etc.
9. Informe a sua equipe de BI sobre o significado de cada um, para que ela possa entender os termos e suas implicações.

* Blank - sem hijacked installs
* Organic - alterar a atribuição para orgânico
* Contributor1, contributor2, contributor3, etc. - atribuição correta para o canal de mídia especificado.

#### **Regras de validação**

As regras de validação permitem adicionar uma camada de lógica à sua proteção contra fraudes, adaptada à sua estratégia de marketing. Com as regras de validação, você pode definir quais instalações são consideradas válidas ou inválidas com base em vários parâmetros de diferentes casos de uso.

Entre em contato com seu customer success manager ou account manager para saber mais sobre as práticas recomendadas para sua vertical.

> 📘 **Atenção**
>
> Para que as regras funcionem da forma mais eficiente possível, recomendamos que você revise sua estratégia de UA/marketing/compra de mídia e avalie quais tipos de instalações ou eventos do app correspondem aos seus esforços, para permitir a atribuição ou bloquear de acordo com suas necessidades. Por exemplo, se você não promover seu aplicativo no país (geo) X, você pode criar uma regra para bloquear automaticamente qualquer atividade desse tipo que chegue do geo X. Você pode criar várias regras para alinhar a proteção à sua estratégia de marketing.

#### **Sobre nossos dashboards**

O <Anchor target="_blank" href="/marketers/pt/docs/protect360-dashboard">dashboard do Protect360</Anchor> oferece uma visão geral dos seus dados de fraude, permitindo que você investigue e entenda melhor a detecção de fraudes e seu impacto em suas atividades.

<Image alt="" src="https://files.readme.io/4717e1f00d832a9808ac6469d89bf3a87f6701afb24a47f3b4393e4e393111ee-35506628785809.png" width="624px" />

</Accordion>

<div id="optimization-weeks-3-5" />

<Accordion title="Otimização (semanas 3–5)">

#### **Otimização da campanha**

Agora é hora de otimizar sua campanha para garantir que você aproveite ao máximo o Protect360. Para isso:

* Veja as [práticas recomendadas](/docs/protect360-onboarding-guide#práticas-recomendadas).
* [Avalie suas configurações de proteção contra fraudes](/docs/protect360-onboarding-guide#avalie-suas-configurações-de-proteção-contra-fraudes)

#### Práticas recomendadas

* Combine dados em tempo real e dados pós-atribuição para avaliar a performance da campanha com base na qualidade (retenção, eventos in-app, etc) e nos dados de fraude.
* Otimize campanhas com base no site\_id ou subsite\_id.
* Analise as taxas e tipos de fraude específicos de parceiros.

#### Avalie suas configurações de proteção contra fraudes

Revise suas [configurações do Fraud Protection Studio](/docs/protect360-onboarding-guide#configurações-do-fraud-protection-studio) para garantir que elas ainda estejam alinhadas com seus objetivos.

> 📘 **Atenção**
>
> As instalações **tagged** são um subconjunto válido. Mude para o modo **implemented** para bloquear em tempo real de acordo com a detecção do Protect360

</Accordion>

<div id="reconciliation-weeks-5-6" />

<Accordion title="Reconciliação (semanas 5—6)">

#### **Conciliação de dados de fraudes**

Depois de implementar o Protect360 e acumular semanas de dados de detecção de fraudes, é hora de reconciliar seus insights de fraudes com seus parceiros de anúncios.

Essa etapa ajuda a garantir que você e seus parceiros estejam alinhados em relação à performance da campanha, métodos de detecção de fraudes e precisão.

Baixe seus <Anchor target="_blank" href="/marketers/pt/docs/protect360-anti-fraud-guide#postattribution-detection">dados pós-atribuição</Anchor> e colabore diretamente com seus parceiros de anúncios para comparar métricas de fraude. Essa reconciliação ajuda a identificar discrepâncias, resolver disputas de forma proativa e garantir a transparência. Saiba como reconciliar dados de fraude com parceiros de anúncios <Anchor target="_blank" href="/marketers/pt/docs/protect360-anti-fraud-guide#fraud-reconciliation-with-ad-networks">aqui</Anchor>.

</Accordion>

<div id="advanced-protection-setup-week-6--optional" />

<Accordion title="Configuração de proteção avançada (semana 6+) [opcional]">

#### **Módulo de segurança avançado**

Disponível exclusivamente para clientes do Protect360, o módulo de segurança avançada foi projetado para aplicativos com um tráfego elevado. Ele adiciona uma camada de segurança fundamental ao seu SDK para Android, validando solicitações de ad networks em tempo real para bloquear instalações falsas e tráfego manipulado.

Isso ajuda a reduzir as discrepâncias na loja de aplicativos, fortalecendo a precisão da atribuição e protegendo seus dados contra fraudes cibernéticas sofisticadas.

Entre em contato com seu CSM ou envie um e-mail para `<hello@appsflyer.com>`

</Accordion>

<div data-zendesk-anchors="what-to-expect=cronograma-de-integra%C3%A7%C3%A3o-e-o-que-esperar h_01JSBWNSH94Q2FBXJ5JSB2JKQ6=cronograma-de-integra%C3%A7%C3%A3o-e-o-que-esperar about-protect360=sobre-o-protect360 h_01JSBWNSHDZ8J3B70KYEG2T03X=sobre-o-protect360 setup-weeks-1%E2%80%933=setup-weeks-1-3 h_01JSBWJJMHSF6YQ5PDEWE0YTN5=setup-weeks-1-3 h_01JVVK5Z1HWN0TXKZVNNGK1CBV=aten%C3%A7%C3%A3o fraud-protection-studio-settings=configura%C3%A7%C3%B5es-do-fraud-protection-studio h_01JSY4SNK5X23DBVD374FV12FG=configura%C3%A7%C3%B5es-do-fraud-protection-studio h_01JVVK5Z1HZAVV3ZEA1AM7KVAY=aten%C3%A7%C3%A3o-1 data-connection-setup=configura%C3%A7%C3%A3o-de-conex%C3%A3o-de-dados h_01JSY4SNK57K77TBXZB92QPBKA=configura%C3%A7%C3%A3o-de-conex%C3%A3o-de-dados h_01JVVK5Z1H0TZH02S76M7JRKWQ=importante how-to-display-hijacked-installs-correctly-in-your-bi=como-exibir-hijacked-installs-instala%C3%A7%C3%B5es-sequestradas-corretamente-em-seu-bi h_01JVVJBVB4FRATEHVZ2Q7EWC54=como-exibir-hijacked-installs-instala%C3%A7%C3%B5es-sequestradas-corretamente-em-seu-bi raw-data-report=relat%C3%B3rio-de-dados-brutos h_01JWDAV3K7JF8ATZP88D4NQRW4=relat%C3%B3rio-de-dados-brutos h_01JVVK5Z1HB5AVVF3XV5Q9KNGA=aten%C3%A7%C3%A3o-2 pull-api=extrair-api h_01JWDAV8GC5N1859AD1PMEQXH9=extrair-api data-locker=relat%C3%B3rio-do-data-locker h_01JWDAVEVDAJD47WQYY0FNSPE9=relat%C3%B3rio-do-data-locker validation-rules=regras-de-valida%C3%A7%C3%A3o h_01JSY4SNK5HAG08PAJQEPB7MQ4=regras-de-valida%C3%A7%C3%A3o h_01JVVK5Z1H05XX8BXECMXAJ4J7=aten%C3%A7%C3%A3o-3 working-with-dashboards=sobre-nossos-dashboards h_01JSY4SNK50RHSQ95E1E2ZK068=sobre-nossos-dashboards optimization-weeks-3%E2%80%935=optimization-weeks-3-5 h_01JSBWJJMH4YW52GSBE6639BP4=optimization-weeks-3-5 campaign-optimization=otimiza%C3%A7%C3%A3o-da-campanha h_01JV255GGVBY8XGQS28F0QZRVH=otimiza%C3%A7%C3%A3o-da-campanha best-practices=pr%C3%A1ticas-recomendadas h_01JV6WFR7MN2X8KTN7RMTXQ5KX=pr%C3%A1ticas-recomendadas review-your-fraud-protection-settings=avalie-suas-configura%C3%A7%C3%B5es-de-prote%C3%A7%C3%A3o-contra-fraudes h_01JV6WGDRP200GHN6MJNZJ5MQE=avalie-suas-configura%C3%A7%C3%B5es-de-prote%C3%A7%C3%A3o-contra-fraudes h_01JVVK5Z1HXPM2G6HAMTYV7MY5=aten%C3%A7%C3%A3o-4 reconciliation-weeks-5%E2%80%936=reconciliation-weeks-5-6 h_01JSBWJJMH1481TJW2EQMF118Q=reconciliation-weeks-5-6 fraud-data-reconciliation=concilia%C3%A7%C3%A3o-de-dados-de-fraudes h_01JV25RP3VAJBCEWWK2TEZFKB2=concilia%C3%A7%C3%A3o-de-dados-de-fraudes advanced-protection-setup-week-6-%5Boptional%5D=advanced-protection-setup-week-6--optional h_01JSBWJJMHZQNYE1N0W2BSJ37X=advanced-protection-setup-week-6--optional advanced-security-module=m%C3%B3dulo-de-seguran%C3%A7a-avan%C3%A7ado h_01JV260Y9M3M6CC48854YHQ01S=m%C3%B3dulo-de-seguran%C3%A7a-avan%C3%A7ado" />
