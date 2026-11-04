---
title: Atribuição de pré-carga usando o Google Play Auto Install
metadata:
  keywords:
    - Advertisers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-alina-koifman
    - Marketers
    - Mobile Attribution
  created_at: '2021-07-25T11:31:06Z'
  edited_at: '2026-08-18T00:10:10Z'
  id: 4404557237649
  locale: pt
  section: Attribution scenarios
  section_id: 6551328497041
  url: https://support.appsflyer.com/hc/pt/articles/4404557237649
---
> **Visão geral:** A AppsFlyer usa o Google Play Auto Install (PAI) para atribuir instalações a campanhas de pré-carga, onde os profissionais de marketing contratam operadoras móveis e parceiros de descoberta de aplicativos para pré-carregar seu aplicativo no momento em que o dispositivo é ligado pela primeira vez pelo usuário. **Observação**: Esse método de atribuição difere da atribuição de <Anchor target="_blank" href="/marketers/pt/docs/appsflyer-factory-preinstall-using-manifest-android">pré-instalação do APK</Anchor>.

<div id="pai-preload-attribution" />

## Atribuição de pré-carga da API

Em campanhas de pré-carga, fabricantes de dispositivos originais (OEMs), operadoras de celular e parceiros de descoberta de aplicativos pré-carregam aplicativos em dispositivos que são baixados na primeira ativação do dispositivo.

As campanhas de pré-carga permitem que os anunciantes alcancem um público potencialmente grande sem executar campanhas on-line.

O Google Play Auto Install (PAI) (1 de 3 métodos de atribuição de pré-carga) fornece aos profissionais de marketing um mecanismo preciso e de preservação da privacidade para medir o desempenho de campanhas de pré-carga. Esse método fornece aos profissionais de marketing resultados de atribuição determinísticos e, simultaneamente, garante que a privacidade do usuário seja preservada, pois a atribuição é realizada por meio de correspondência de referenciador com um referenciador do Google Play gerado independentemente do dispositivo e dos identificadores do usuário.

A AppsFlyer dá a maior prioridade à atribuição de pré-carga. Isso significa que, se um usuário interagir com outras campanhas antes de abrir o aplicativo pela primeira vez, a atribuição será concedida à campanha de pré-carga. Outros engajamentos são considerados como instalações assistidas.

<div id="note" />

> 📘 **Nota**
>
> A configuração de prioridade de atribuição igual do pré-carregamento não se aplica ao Google PAI.

<div id="flow" />

### Fluxo

1. Um novo dispositivo é ativado pela primeira vez e aplicativos predefinidos são automaticamente instalados nele pelo Google Play, de acordo com as regras definidas pelo parceiro de pré-carregamento.
2. O usuário inicia um aplicativo pré-carga pela primeira vez.
3. O SDK da AppsFlyer consulta a API de referência do Google Play.
4. Atributos da AppsFlyer com base nos dados recuperados.

![PAI-attribution-flow_en-us.png](https://files.readme.io/c7f02a0a6637e9c73e9a39f97e71d5d37d8d2712b458735cd87b4b245ad0fccb-small-4404791877649.png)

<div id="data-availability" />

### Disponibilidade de dados

Os dados de desempenho de pré-carga do Google Play Auto Install (PAI) estão disponíveis nos seguintes locais:

* Painel de visão geral e relatórios agregados, agregados nos níveis de parceiro de pré-carga (canal de mídia) e campanha.
* Relatórios de dados brutos.

Os dados brutos incluem os seguintes campos:

* Media\_source = ID do parceiro
* Match\_type = preload\_pai
* Campaign\_name = pré-carregar campanha por `<preloadpartner ID>`

<div id="set-up-google-play-auto-install-pai-preload-attribution" />

### Configurar a atribuição de pré-carga do Google Play Auto Install (PAI)

**Para configurar a atribuição de pré-carga da API:**

1. Na AppsFlyer, vá para o menu lateral e selecione **colaborar** > **integrações ativas**.
2. Selecione o parceiro de pré-carga.
3. Ative **Atribuição de pré-carga**.
4. Defina a duração da **janela de lookback de pré-carga**.

   <div id="note-1" />

   > 📘 **Nota**
   >
   > O Google armazena dados do referenciador por até 90 dias. Defina a janela de lookback do PAI como 90 dias ou menos. Embora a UI permita até 180 dias, os dados além de 90 dias não ficam disponíveis no Google.

5. Clique em **Salvar integração**.
6. Informe ao parceiro de pré-carga que você está pronto para atribuir suas campanhas.

<div id="partners-supporting-google-play-auto-install-pai-preload-campaigns" />

### Parceiros que apoiam campanhas de pré-carga do Google Play Auto Install (PAI)

<table><thead><tr><th rowspan="2">Parceiro</th><th rowspan="2">PID</th></tr></thead><tbody><tr><td><p>Xiaomi</p></td><td><span>xiaomipai_int</span></td></tr><tr><td><p>Transsion</p></td><td><span>shalltrypai_int</span></td></tr><tr><td><p>Oppo</p></td><td><span>oppopaipreinstall_int</span></td></tr><tr><td><p>Vivo</p></td><td><span>vivootapreload_int</span></td></tr><tr><td><p>TCL</p></td><td><span>tclpai_int</span></td></tr><tr><td><p>Motorola</p></td><td><span>motorola_int</span></td></tr><tr><td><p>MITV</p></td><td><span>mitvpai_int</span></td></tr><tr><td><p>ZTE</p></td><td><span>ztepai_int</span></td></tr><tr><td><p>Lenovotab</p></td><td><span>lenovotabpai4p_int</span></td></tr><tr><td><p>Pré-instalação do KDDI</p></td><td><span>kddipai_int</span></td></tr></tbody></table>

<div id="note-2" />

> 📘 **Nota**
>
> **Observação**: As agências não podem ativar campanhas de pré-carga para seus clientes.

<div id="postbacks-for-preload-partners" />

## Postbacks para parceiros de pré-carga

Como parte da integração com a AppsFlyer, parceiros de pré-carga definem o conteúdo e os pontos finais dos postbacks enviados a elas pela AppsFlyer.

Quando incluídas em um postback, as macros contêm por dados relevantes ao usuário. As macros compatíveis estão listadas na tabela a seguir:

* **Fonte**: Indica de onde os dados se originam:
  * **SDK**: SDK da AppsFlyer incorporado no aplicativo ou na API de servidor para servidor
  * **AppsFlyer**: Após o processamento pela AppsFlyer.

| Macro de postback para parceiros de pré-carga (nome do parâmetro) | Fonte | Descrição |
| --- | --- | --- |
| ativado | SDK | Nome do aplicativo definido pelo anunciante |
| código\_país | A AppsFlyer | Código do país usando ISO 3166 (alfa-2) Exemplo: US, CN. |
| install\_time | SDK | Carimbo de data/hora da instalação |
| language | SDK | Idioma (localidade) reportado pelo dispositivo e definido pelo sistema operacional do dispositivo. |
| ativado | SDK | Identificador de aplicativo único na Appsflyer. |
| app\_version | SDK | Versão do aplicativo definido pelo desenvolvedor do aplicativo no código do aplicativo |
| device\_type | SDK | O nome do modelo comercial do dispositivo. Exemplo: SM-GM284 ou iPhone7 |
| os\_version | SDK | Versão do sistema operacional do dispositivo |

<div id="postback-example" />

#### Exemplo de postback

```http
http://YourCompanyDomain.com?pid=(preinstall_partner)&app_name=(app-name)&app_id=(app-id)&install_time=(install-unix-ts)
```

<div data-zendesk-anchors="pai-preload-attribution=atribui%C3%A7%C3%A3o-de-pr%C3%A9-carga-da-api h_01HEJG4FHSGJDZ77Y281F7SG4R=atribui%C3%A7%C3%A3o-de-pr%C3%A9-carga-da-api h_01K8XBQ3YKJ8KBMPMAAMBZP25E=nota pai-preload-attribution-flow=fluxo h_01HEJG4FHSF8X1TEMMNJBYP71Z=fluxo campaign-performance-data-availability=disponibilidade-de-dados h_01HEJG4FHSCMPJM5TRNSPNDHVN=disponibilidade-de-dados run-preload-referrer-campaigns=configurar-a-atribui%C3%A7%C3%A3o-de-pr%C3%A9-carga-do-google-play-auto-install-pai h_01HEJG4FHS7E5JZT2BBYG2BNEK=configurar-a-atribui%C3%A7%C3%A3o-de-pr%C3%A9-carga-do-google-play-auto-install-pai h_01K8XBJ9EJ38ST3KAFF879ZQ1H=nota-1 partners-supporting-preload-referrer-campaigns=parceiros-que-apoiam-campanhas-de-pr%C3%A9-carga-do-google-play-auto-install-pai h_01HEJG4FHSNEGR7R9VCSDT9TSZ=parceiros-que-apoiam-campanhas-de-pr%C3%A9-carga-do-google-play-auto-install-pai h_01K8XBVZJGG59K3XJ8R346X9FH=nota-2 postbacks-for-preload-partners=postbacks-para-parceiros-de-pr%C3%A9-carga h_01HEJG4FHSKD7DY6W7W65YBMGN=postbacks-para-parceiros-de-pr%C3%A9-carga preload-postback-example=exemplo-de-postback h_01HEJG4FHSBFB456Z752HFC8KN=exemplo-de-postback" />
