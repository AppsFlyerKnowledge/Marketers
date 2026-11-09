---
title: Audiências – use seus cohorts do Amplitude como audiências
metadata:
  keywords:
    - Audiences
    - Premium
    - Marketers
    - Audience Segmentation
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-neama-benhabib
    - Marketers
    - Audience Segmentation
  created_at: '2022-02-23T14:27:13Z'
  edited_at: '2026-08-18T00:36:47Z'
  id: 4470658876817
  locale: pt
  section: Audiences
  section_id: 6551336428945
  url: https://support.appsflyer.com/hc/pt/articles/4470658876817
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **Visão geral:** Tire proveito dos seus dados próprios sincronizando os seus grupos do Amplitude com a AppsFlyer como audiências importadas.

<div id="about-the-amplitude-integration" />

## Sobre a integração Amplitude

A **integração entre AppsFlyer Audiences e Amplitude** permite sincronizar diretamente os grupos definidos na sua conta Amplitude com a AppsFlyer como <Anchor target="_blank" href="/marketers/pt/docs/audiences-import-audience-segments-from-internal-systems">audiências importadas</Anchor>. A AppsFlyer pode então funcionar como o seu local centralizado para conectar e manter estes segmentos de audiência com parceiros, consultar métricas de campanhas conectadas e unir as suas informações próprias do Amplitude e AppsFlyer para maximizar o potencial de ambos.

Os grupos do Amplitude podem ser sincronizados com a AppsFlyer de forma única ou como uma sincronização agendada com atualizações diárias ou horárias.

<div id="setting-up-the-integration" />

## Configuração da integração

Configure a integração Audiences-Amplitude diretamente na plataforma Amplitude.

<div id="define-appsflyer-data-destinations" />

### Definir destinos de dados na AppsFlyer

**Siga estes passos no Amplitude para definir os destinos de dados da AppsFlyer.** **Note que deve definir um destino de dados separado para cada aplicação onde irá importar audiências da AppsFlyer.**

1. Na secção **Destinos de Dados** em Amplitude, selecione a opção **AppsFlyer**.
2. Em **Destinos de Grupo,** selecione **AppsFlyer.**
3. Introduza as seguintes informações na caixa de diálogo **Conectar-se à AppsFlyer**.

   **Importante!** Se já existirem destinos de dados AppsFlyer anteriormente criados na sua conta Amplitude, a caixa de diálogo será uma lista clicável que mostra todos os destinos existentes. Para criar um novo destino, deslize até ao final da lista e clique em **Adicionar outro destino.**

   <Image align="center" alt="" src="https://files.readme.io/ba47fc9a411bd55d84ad34ccd5c1d74fecb1648f8f7aed3ae713965bef616ae8-33375708375441.png" />

   

| Campo | Descrição |
| --- | --- |
| Nome | Introduza um nome para o destino.<br /><br />Se for criar mais de um destino AppsFlyer num único projeto Amplitude (por exemplo, se tiver mais de uma aplicação no projeto), assegure-se de criar um nome que possa identificar facilmente mais tarde. |
| Token API AppsFlyer V2.0 | **Para obter o token API da AppsFlyer, siga estes passos na AppsFlyer:**<ol><li>Na barra de menu superior, aceda ao menu do utilizador (menu suspenso com o endereço de e-mail no canto superior direito).</li><li>Selecione **Centro de Segurança.**</li><li>Na secção **Tokens de API da AppsFlyer**, clique em **Gerir os seus tokens de API da AppsFlyer.**</li><li>Copie o token **V2.0**.</li></ol> |
| ID da Aplicação AppsFlyer | Insira o ID da aplicação para este destino, conforme aparece no dashboard da AppsFlyer:<br /><br />![amplitude_app_id_from_appsflyer_dashboard.png](https://files.readme.io/2e7da9a20f0c4b59e58f51823dd9753ecc36b77e84622821cb3cb65e4f7b2743-33375708378385.png) |
| Plataforma | Selecione a plataforma da aplicação (iOS ou Android). |
| Identificador | Indique à AppsFlyer como conectar os seus dados do Amplitude aos dados da AppsFlyer, selecionando uma Propriedade de Utilizador do Amplitude à esquerda e a chave da AppsFlyer para mapear à direita. A chave que escolher na AppsFlyer deve ser uma das seguintes:<ul><li>**Para audiências iOS:** ID de Anunciante iOS, ID de Utilizador Amplitude ou ID de Utilizador do Cliente AppsFlyer</li><li>**Para audiências Android:** ID de Anunciante do Google, ID de Utilizador do Amplitude ou ID de Utilizador do Cliente da AppsFlyer</li></ul> |

4. Clique em **Guardar** para salvar o novo destino da AppsFlyer.

<div id="sync-amplitude-cohorts-to-appsflyer-destinations" />

### Sincronizar coortes do Amplitude com destinos AppsFlyer

**Depois, siga estes passos para sincronizar qualquer um dos seus coortes do Amplitude com os seus destinos AppsFlyer:**

1. Na secção **Coortes** da plataforma Amplitude, selecione o coorte para o qual deseja criar uma audiência AppsFlyer. (Em alternativa, pode criar uma nova coorte.)
2. Siga o link: **Clique para ver os detalhes da coorte.**
3. Na página **Definição de Coorte**, clique no botão **Sincronizar com…** .
4. Selecione o bloco AppsFlyer, depois clique em **Seguinte.**

   A janela de diálogo **Definir Destino e Frequência** será aberta.

   <Image align="center" alt="amplitude_define_destination_and_cadence_dialog.png" src="https://files.readme.io/e9f726c731e865e6313bf430b1e5506db5a820fc7d3d544747a873cf08139b26-33375708382097.png" />
5. Na lista **Selecione um destino de API para sincronizar**, escolha o nome do destino relevante da AppsFlyer.
6. Decida se deseja sincronizar esta coorte com a AppsFlyer apenas uma vez ou de forma agendada. (Para sincronizações agendadas, escolha se deseja atualizar diariamente ou a cada hora.)
7. Clique no botão **Sincronizar** para iniciar a sincronização.

Após a conclusão bem-sucedida da primeira sincronização, um novo público para esta coorte será visível no separador de Públicos-alvo do painel de Públicos.

Por padrão, o nome do novo público é o nome da coorte do Amplitude sincronizada, seguido de um identificador alfanumérico. Pode editar o nome do público no painel de Públicos, se desejar.

<Image align="center" alt="amplitude_imported_audience.png" src="https://files.readme.io/a4f8efc6818d94a68b28ca62ae26215f17bfc7edcfb990855a042a2dee71f8b6-33375708383249.png" />

<div data-zendesk-anchors="overview=sobre-a-integra%C3%A7%C3%A3o-amplitude h_01HNZP6HDVC5RBMKTCZY81HG4M=sobre-a-integra%C3%A7%C3%A3o-amplitude setting-up-the-integration=configura%C3%A7%C3%A3o-da-integra%C3%A7%C3%A3o h_01HNZP6HDVZH6Q1KGJE7FXSPMT=configura%C3%A7%C3%A3o-da-integra%C3%A7%C3%A3o define-appsflyer-data-destinations=definir-destinos-de-dados-na-appsflyer h_01HNZP6HDVV3GSEPARCY1VABX8=definir-destinos-de-dados-na-appsflyer sync-amplitude-cohorts-to-appsflyer-destinations=sincronizar-coortes-do-amplitude-com-destinos-appsflyer h_01HNZP6HDV6EFPCM5FE5XBAS78=sincronizar-coortes-do-amplitude-com-destinos-appsflyer" />
