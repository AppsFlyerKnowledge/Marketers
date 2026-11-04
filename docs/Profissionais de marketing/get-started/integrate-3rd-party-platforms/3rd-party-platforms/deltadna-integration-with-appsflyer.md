---
title: integração do deltaDNA com a AppsFlyer
metadata:
  keywords:
    - deltaDNA
    - Advertisers
    - Ad Networks
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
    - Ad Networks
  created_at: '2016-09-04T06:41:51Z'
  edited_at: '2026-09-10T00:10:34Z'
  id: 212247706
  locale: pt
  section: 3rd-party platforms
  section_id: 6551199962257
  url: https://support.appsflyer.com/hc/pt/articles/212247706
---
> **At a glance:** **Visão geral:** a deltaDNA, parceira integrada da AppsFlyer, é a principal plataforma de análises em tempo real e marketing para gaming mobile. A combinação de funcionalidades avançadas de deep data líderes de mercado, performance ultra-alta e um ambiente aberto e flexível permite que os usuários maximizem o engajamento e o valor do tempo de vida por meio da segmentação de jogadores, modelagem preditiva e intervenções direcionadas em tempo real.

> 🚧 **Important**
>
> **Importante!**
>
> <Anchor target="_blank" href="/marketers/pt/docs/about-raw-data-identifier-restrictions#restrições-por-fonte-de-mídia">Algumas fontes de mídiarestringem</Anchor> o compartilhamento de dados com terceiros. Portanto, os postbacks de eventos restritos não serão enviados para esse parceiro, independentemente da configuração de envio de postbacks.

<div id="integrating-with-deltadna" />

## Integração com a deltaDNA

> 🚧 **Important**
>
> **Importante!**
>
> O userID do SDK da deltaDNA, seja gerado automaticamente ou fornecido pelo jogo, deve ser definido como o customer user id no SDK da AppsFlyer para garantir que os dados de atribuição recebidos da AppsFlyer sejam aplicados ao usuário correto. Isso deve ser feito apenas em builds do jogo integradas ao ambiente LIVE, do lado da deltaDNA.

1. Se você estiver usando um ID de usuário proprietário e preenchendo esse ID tanto no parâmetro custom\_user\_id da AppsFlyer quanto no parâmetro user da deltaDNA – não será necessária nenhuma implementação de código adicional.
2. Se você não estiver usando um ID de usuário proprietário, deverá obter a propriedade userID da deltaDNA e implementá-la no SDK da AppsFlyer no parâmetro **customer\_user\_id**. O código a seguir deve ser implementado depois que ambos os SDKs forem iniciados.

<Tabs>
<Tab title="Android iOS">

```java
AppsflyerLib.getInstance().setCustomerUserId(DDNA.instance().getUserId())
```

</Tab>

<Tab title="Exemplo">

```objectivec
[AppsFlyerTracker sharedTracker].customerUserID = [DDNASDK sharedInstance].userID;
```

</Tab>

<Tab title="Unity">

```swift
https://files.readme.io/e0af8513fdda3268ab799a6ef08396c03970bd0850bde851f07649e459a8b20e-206781143.png
```

</Tab>
</Tabs>

Siga as instruções abaixo para configurar a integração com a deltaDNA

**Na deltaDNA:**

1. Crie um evento AppsFlyerAttribution na deltaDNA com a ferramenta de gerenciamento de eventos

![Delta DNA 1](https://files.readme.io/e5224bbaa730d997699e1a930425946f69a2b86ef94e241b4ba6fdb9ad978c66-206781083.png)

2. Obtenha a chave do ambiente Live na página Game Details no dashboard da deltaDNA:

![Delta DNA 2](https://files.readme.io/6b28184264dfd695000e8bfae9538862a3e17ea6f9d355af0996ccf107b4e6c2-206768886.png)

**No AppsFlyer, ative ou edite a integração:**

1. **Para ativar:** No AppsFlyer, no menu lateral, selecione a guia **Collaborate** > **Partner Integrations > Marketplace** .  
   **Para editar**: No AppsFlyer, no menu lateral, selecione a guia **Collaborate** > **Partner Integrations > Active Integrations** .
2. Pesquise por **deltaDNA** e selecione-a.
3. Clique em **Configurar Integração**. Você será direcionado para a página de configuração da integração.
4. Na aba **Integração**, selecione o Aplicativo para a integração e ative **Ativar parceiro**.  
   **Observação:** Essa opção deve permanecer <Anchor target="_blank" href="/marketers/pt/docs/partner-activation-deactivation">(ativada)</Anchor> enquanto você trabalhar com o parceiro.
5. Insira a Enviorment\_key obtida no console da deltaDNA (consulte a Seção 2).
6. Defina a **opção de envio** como **Todos os canais de mídia, incluindo orgânico**.
7. Clique em **Salvar Integração**.

Depois de salvar a configuração, a AppsFlyer envia os seguintes dados à deltaDNA para cada instalação orgânica e não orgânica:

* Chave do ambiente
* ID do usuário
* Tempo de instalação
* Media Source
* Campaign name

> 📘 **Note**
>
> **Importante!**
>
> deltaDNA rejeita postbacks de instalação do AppsFlyer se não houver um Customer User ID ou UserID definido.

<div id="viewing-the-attribution-data-in-the-deltadna-console" />

## Visualizar os dados de atribuição no console da deltaDNA

Os dados de atribuição recebidos da AppsFlyer podem ser usados para:

* Filtrar gráficos do Measure
* Criar dashboards e relatórios personalizados
* Executar análises detalhadas
* Criar segmentos de jogadores personalizados para direcionar jogadores com campanhas e ofertas personalizadas.

O filtro Canal de aquisição, na parte superior de todos os gráficos do Measure, das matrizes de retenção e dos preditores de LTV e retenção, usa e se baseia no canal de mídia da AppsFlyer.

![Delta DNA 3](https://files.readme.io/21cf4f1c8641351a1ecc200d8b95d7558b92f4daf38f49975601d996a0fcfb86-206781123.png)

Há 8 parâmetros de atribuição que a AppsFlyer pode enviar para a deltaDNA para uso em suas análises, relatórios e consultas. Todos eles têm o prefixo das letras **afAttr.**   
*Por exemplo. afAttrCampaign, afAttrAgency, afAttrMediaSource para a campanha, a agência e o canal de mídia, respectivamente.*

Todos os parâmetros de atribuição estão listados em **appsFlyerAttribution**, adicionado à tela de Gerenciamento de eventos.

![Delta DNA 4](https://files.readme.io/e0af8513fdda3268ab799a6ef08396c03970bd0850bde851f07649e459a8b20e-206781143.png)

Use-os para criar consultas de análise e relatórios personalizados em qualquer uma das ferramentas Analyze da deltaDNA.

![Delta DNA 5](https://files.readme.io/f4b9d0320feb3990182a0c9a835a18565ba959fabf7269c45a4651506666f941-206768946.png)

<div data-zendesk-anchors="integrating-with-deltadna=integra%C3%A7%C3%A3o-com-a-deltadna h_01H9FK6N8V597T8AY0RF0H6CZW=integra%C3%A7%C3%A3o-com-a-deltadna viewing-the-attribution-data-in-the-deltadna-console=visualizar-os-dados-de-atribui%C3%A7%C3%A3o-no-console-da-deltadna h_01H9FK6N8W8011X3JVG2EZ66H4=visualizar-os-dados-de-atribui%C3%A7%C3%A3o-no-console-da-deltadna" />
