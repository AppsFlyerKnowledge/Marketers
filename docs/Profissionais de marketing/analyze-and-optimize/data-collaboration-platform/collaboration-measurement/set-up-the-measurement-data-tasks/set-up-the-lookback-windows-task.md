---
title: Configure a tarefa de janelas de lookback
metadata:
  keywords:
    - Marketers
    - Data Clean Room
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-yael-sharabi
    - Marketers
    - Data Clean Room
  created_at: '2025-08-18T11:38:51Z'
  edited_at: '2026-08-18T00:06:26Z'
  id: 38191154658193
  locale: pt
  section: Set up the measurement data tasks
  section_id: 38035061674769
  url: https://support.appsflyer.com/hc/pt/articles/38191154658193
---
<div id="set-lookback-windows" />

## Definir janelas de lookback

> **Em resumo:** Defina janelas de atribuição para campanhas on-site e off-site para determinar até quanto tempo atrás os engajamentos do usuário podem ser associados às conversões.

As janelas de lookback definem o tempo máximo entre um engajamento do usuário (clique ou visualização) e a conversão resultante para fins de atribuição. Cada colaboração pode definir uma duração personalizada para a janela de lookback. Parceiros de mídia, como Google Ads ou Meta Ads, geralmente aplicam regras diferentes para configurar essas janelas. Este artigo explica como configurar janelas de lookback para colaboradores, Google e Meta.

<div id="prerequisites" />

## Pré-requisitos

Antes que um colaborador que não seja o proprietário da colaboração possa configurar a tarefa de janelas de lookback, o proprietário deve primeiro atribuí-la a ele. Para obter mais informações, consulte Atribuir tarefas de configuração.

<div id="open-the-lookback-windows-task" />

## Abrir a tarefa de janelas de lookback

A tarefa de janelas de lookback na página **Configurações de mensuração** é onde você configura as janelas de lookback de <Anchor target="_blank" href="/marketers/pt/docs/data-collaboration-platform-dcp-collaboration-measurement-overview#on-site-vs-off-site-campaign-measurement">campanhas on-site e off-site</Anchor>.

Para abrir a tarefa de janelas de lookback, siga estas etapas:

1. No AppsFlyer, no menu lateral, acesse **Colaborar** > **Data Clean Room**.
2. Na página **Plataforma de colaboração de dados**, selecione a colaboração que você deseja.
3. Na parte inferior da página de colaboração, clique em **Configurar mensuração.**
   * Se o link estiver esmaecido, configure as <Anchor target="_blank" href="/marketers/pt/docs/data-collaboration-platform-dcp-create-and-manage-sources">fontes de dados</Anchor> e as <Anchor target="_blank" href="/marketers/pt/docs/data-collaboration-platform-dcp-build-and-activate-audiences">audiências</Anchor> da colaboração.
4. Na página **Configurações de mensuração**, clique no painel da tarefa **janelas de lookback** para abrir a caixa de diálogo **janelas de lookback**.

   <div id="note" />

   > 📘 **Observação:**
   >
   > Se o painel **janelas de lookback** estiver esmaecido, peça ao proprietário da colaboração para atribuir a você a tarefa de janelas de lookback.


<div id="set-the-collaboration-lookback-window" />

## Definir a janela de lookback da colaboração

Para configurar a janela de lookback da colaboração, siga estas etapas:

1. Se você estiver configurando uma <Anchor target="_blank" href="/marketers/pt/docs/data-collaboration-platform-dcp-collaboration-measurement-overview#on-site-and-off-site-campaigns">campanha combinada on-site e off-site</Anchor> na caixa de diálogo **Lookback Windows**, expanda o painel <Image alt="AppsFlyer.png" src="https://files.readme.io/2536fe45ebde303e110c7b90cb3b2a95fc28672a5fa095efff485cdebbd466df-38392816916369.png" width="2.61%" /> **CMN Attribution**. Caso contrário, pule para a próxima etapa.
2. Nos controles deslizantes **Click-through** ou **View-through lookback window** , arraste o ponteiro para escolher a duração da janela em dias.
3. Clique em **Salvar**.

<div id="set-the-meta-ads-lookback-window" />

## Definir a janela de lookback do Meta Ads

Se você estiver executando uma campanha off-site com Meta Ads, a tarefa de janelas de lookback incluirá configurações dedicadas aos anúncios do Meta. Você pode definir separadamente as janelas de atribuição de click-through e view-through, de acordo com as durações de janela predefinidas do Meta Ads.

1. No painel **Lookback windows**, expanda o painel <Image alt="Meta.png" src="https://files.readme.io/4023aa4c9446f22aa46063ab349fc038d974638aeefcbb3288e04663896ec788-38392832989585.png" width="3.22%" /> **Meta Ads**.
2. Selecione as janelas de atribuição **Click-through** e **View-through** entre as seguintes opções:
   * **1 dia**
   * **7 dias**
   * **28 dias**

<div id="google-ads-lookback-window" />

## Janela de lookback do Google Ads

Se você estiver executando uma campanha off-site com o Google Ads, a tarefa Lookback windows incluirá um link para a plataforma do Google Ads.

1. Na caixa de diálogo **Lookback windows**, role até o painel <Image alt="Google-ads.png" src="https://files.readme.io/afa0e2cd15ea4214eba625da397dccd04118b564450c59993fd0e668c31f023b-38392832994321.png" width="2.86%" /> **Google Ads**.
2. Clique no **ícone de seta** para abrir a página de configurações da ação de conversão relevante na plataforma Google Ads.
3. Atualize as configurações da janela de lookback conforme necessário no Google Ads.

<div data-zendesk-anchors="set-lookback-windows=definir-janelas-de-lookback h_01K3G9Q0G79BDATM6T80T6F6TX=definir-janelas-de-lookback prerequisites=pr%C3%A9-requisitos h_01K3G9Q0G7XSM1VS4VF9VCTWD0=pr%C3%A9-requisitos open-the-lookback-windows-task=abrir-a-tarefa-de-janelas-de-lookback h_01K3G9Q0G7FM4MMR6CVWM4ATRA=abrir-a-tarefa-de-janelas-de-lookback h_01K3G9Q0G7DQRCX9FH9Q3N17N3=observa%C3%A7%C3%A3o set-the-collaboration-lookback-window=definir-a-janela-de-lookback-da-colabora%C3%A7%C3%A3o h_01K3G9Q0G7X7FY6C0H4DQYSP3F=definir-a-janela-de-lookback-da-colabora%C3%A7%C3%A3o set-the-meta-ads-lookback-window=definir-a-janela-de-lookback-do-meta-ads h_01K3G9Q0G71ADFQ9QHBXJBTEAA=definir-a-janela-de-lookback-do-meta-ads google-ads-lookback-window=janela-de-lookback-do-google-ads h_01K3G9Q0G7HEFS65XA6YD0V6YD=janela-de-lookback-do-google-ads" />
