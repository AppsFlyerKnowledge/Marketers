---
title: >-
  Plataforma de colaboração de dados (DCP) - configure a mensuração de
  colaboração
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
  created_at: '2025-01-27T09:58:46Z'
  edited_at: '2026-04-06T15:35:15Z'
  id: 32147174933905
  locale: pt
  section: Collaboration measurement
  section_id: 38034865098641
  url: https://support.appsflyer.com/hc/pt/articles/32147174933905
---
**Resumo:** Aprenda a configurar a DCP para atribuição por SKU, com base nos dados de conversão, engajamento e mapeamento de campanhas.

<div id="overview" />

## Visão geral

Após <Anchor target="_blank" href="/marketers/pt/docs/data-collaboration-platform-dcp-prepare-collaboration-measurement">preparar os dados de conversão, engajamento e mapeamento de campanhas</Anchor>, você pode configurar a DCP para mensuração e atribuição:

1. [**Defina o tipo de campanha**](#selecionar-o-tipo-de-campanha-on-site-off-site-ou-ambos) – Escolha on-site, off-site ou ambos. Isso determina como a DCP processa seus dados e define as tarefas de configuração necessárias.
2. [**Atribua tarefas**](#atribuir-a-tarefa-de-configuração) – O proprietário atribui cada tarefa de configuração ao colaborador com acesso aos dados relevantes.
3. [**Configure tarefas**](#configurar-a-mensuração-de-campanhas-on-site-e-off-site) – Os colaboradores configuram conversões, engajamentos e mapeamento de campanhas. Isso inclui a configuração de campanhas on-site e off-site, para que todos os dados estejam conectados, mapeados e prontos para atribuição.
4. <Anchor target="_blank" href="/marketers/pt/docs/data-collaboration-platform-dcp-run-and-manage-measurement">**Execute e gerencie mensurações**</Anchor> – Execute mensurações históricas ou em tempo real, duplique-as, execute-as novamente ou altere o escopo.

<div id="start-the-measurement-setup" />

## Iniciar a configuração de mensuração

Para iniciar a configuração de mensuração, siga estas etapas:

1. Na AppsFlyer, no menu lateral, vá para **Colaborar** > **Data Clean Room.**
2. Na página **Plataforma de colaboração de dados**, selecione a colaboração que você deseja.
3. Na página “Colaboração”, execute **uma** das etapas abaixo:
   * Se for a primeira mensuração configurada na sua colaboração, clique em **Configurar mensuração.** Você verá a página **Criar mensuração**.
   * Se já existir um conjunto de mensurações em sua colaboração, clique no ícone de mais (+) no painel de seleção. Você verá a página **Criar mensuração**.

[![start-measurement.png](https://files.readme.io/c87bae214a48e807c085d192fd1b2132559a23a0954ea4fedae57b8d18372cae-44433074460305.png)](https://files.readme.io/c87bae214a48e807c085d192fd1b2132559a23a0954ea4fedae57b8d18372cae-44433074460305.png)

<div id="select-campaign-type-on-site-off-site-or-both" />

## Selecionar o tipo de campanha: on-site, off-site ou ambos

Como os tipos de campanha on-site e off-site diferem pelo local de conversão e processo de atribuição, o proprietário da colaboração deve especificar o tipo de campanha antes de configurar a mensuração. Para mais informações, consulte: <Anchor target="_blank" href="/marketers/pt/docs/data-collaboration-platform-dcp-collaboration-measurement-overview#on-site-vs-off-site-campaign-measurement">Mensuração de campanhas on-site e off-site</Anchor>.

Para selecionar o tipo de campanha, siga estas etapas:

1. [Inicie a configuração de mensuração](#iniciar-a-configuração-de-mensuração).
2. Na página **Criar mensuração**, selecione  <Image alt="On-site icon.png" src="https://files.readme.io/c9ff0bb1e2c31527ee38a9403a6180e3ecd4c3ad105935fb59ed14c2474f6039-32148924980113.png" width="3.27%" /> **On-site, <Image alt="off-site icon.png" src="https://files.readme.io/6de5841985237de221c74d427ad06f719572000aafe8077c7cef64e53ee8caf5-32156666763921.png" width="3.3%" /> Off-site** ou ambos. Faça **uma** das seguintes opções:
   * [Configure a campanha on-site](#configurar-a-mensuração-de-campanhas-on-site-e-off-site),
   * [Configure a campanha off-site](#configure-offsite-campaign-measurement),
   * [Configure uma campanha on-site e off-site](#configure-combined-onsite-and-offsite-campaign-measurement).

<div id="assign-configuration-task" />

## Atribuir a tarefa de configuração

A página “Configurações de mensuração” inclui cinco tarefas principais: conversão, engajamento, mapeamento de campanhas, parceiros de mídia e configuração da janela de lookback.

O proprietário da conta na DCP pode atribuir tarefas a colaboradores para garantir a privacidade dos dados e refletir a divisão de responsabilidades. Um colaborador pode, por exemplo, gerenciar dados de engajamento enquanto o outro gerencia conversões. Os colaboradores têm acesso apenas às tarefas atribuídas.

<div id="assign-a-configuration-task-to-a-collaborator" />

<Accordion title="Atribuir uma tarefa de configuração a um colaborador">

Para atribuir qualquer uma das tarefas acima, siga as etapas abaixo:

1. [Abra as configurações de mensuração](#iniciar-a-configuração-de-mensuração).
2. Em cada uma das quatro tarefas acima, na lista **Responsável**, selecione o colaborador que irá gerenciar a tarefa.
   * **Tarefa de conversões:** Atribua ao colaborador cuja plataforma processa conversões.
   * **Tarefa de campanhas:** Atribua ao colaborador cuja plataforma processa conversões.
   * **Tarefa de engajamentos:** Atribua ao colaborador onde ocorre o engajamento do usuário.
   * **Tarefa de parceiros de mídia:** Atribua ao colaborador cuja conta de parceiros de mídia é usada para campanhas externas.
   * **Tarefa de janelas de lookback** : atribuída automaticamente ao proprietário da colaboração. Você pode atribuir outro colaborador, mas é opcional.

</Accordion>

<div id="remove-the-configuration-task-assignment-from-a-collaborator" />

<Accordion title="Remover a atribuição da tarefa de configuração de um colaborador">

Em alguns casos, pode ser necessário revogar a atribuição da tarefa de configuração de um colaborador. Quando o proprietário da colaboração remove uma atribuição, ocorre o seguinte:

* O colaborador perde imediatamente o acesso à tarefa não atribuída.
* Qualquer configuração previamente fornecida pelo colaborador para essa tarefa é descartada.
* A mensuração da colaboração é interrompida.

Para remover uma atribuição da tarefa de configuração, siga as etapas abaixo:

1. Vá para a mensuração de colaboração. Veja Abrir configurações de mensuração.
2. Na etapa de configuração, remova o colaborador atribuído da lista **Responsável**.

</Accordion>

<div id="configure-on-site-and-off-site-campaign-measurement" />

## Configurar a mensuração de campanhas on-site e off-site

Defina a configuração de mensuração de campanhas em “Configurações de mensuração”. Siga as etapas abaixo com base nos tipos de campanhas mensuradas: on-site, off-site ou ambos.

<div id="configure-onsite-campaign-measurement::4f9b35af" />

<Accordion title="Configurar a mensuração de campanhas on-site">

Para configurar uma <Anchor target="_blank" href="/marketers/pt/docs/data-collaboration-platform-dcp-collaboration-measurement-overview#on-site-campaigns">campanha on-site</Anchor>, siga estas etapas:

1. [Inicie a configuração de mensuração](#iniciar-a-configuração-de-mensuração).
2. <Anchor target="_blank" href="/marketers/pt/docs/set-up-the-campaigns-task">Configure a tarefa de campanhas</Anchor>
3. <Anchor target="_blank" href="/marketers/pt/docs/set-up-the-conversions-task">Configure a tarefa de conversões</Anchor>
4. <Anchor target="_blank" href="/marketers/pt/docs/set-up-the-engagements-task">Configure a tarefa de engajamentos</Anchor>
5. <Anchor target="_blank" href="/marketers/pt/docs/set-up-the-lookback-windows-task">Configure a tarefa de janelas de lookback</Anchor>

</Accordion>

<div id="configure-offsite-campaign-measurement" />

<Accordion title="Configurar a mensuração de campanhas off-site">

Para configurar uma <Anchor target="_blank" href="/marketers/pt/docs/data-collaboration-platform-dcp-collaboration-measurement-overview#off-site-campaigns">campanha off-site</Anchor>, siga estas etapas:

1. [Inicie a configuração de mensuração](#iniciar-a-configuração-de-mensuração).
2. <Anchor target="_blank" href="/marketers/pt/docs/set-up-the-campaigns-task">Configure a tarefa de campanhas</Anchor>
3. <Anchor target="_blank" href="/marketers/pt/docs/set-up-the-conversions-task">Configure a tarefa de conversões</Anchor>
4. <Anchor target="_blank" href="/marketers/pt/docs/set-up-the-media-partners-task">Configure a tarefa de parceiros de mídia</Anchor>
5. <Anchor target="_blank" href="/marketers/pt/docs/set-up-the-lookback-windows-task">Configure a tarefa de janelas de lookback</Anchor>

</Accordion>

<div id="configure-combined-onsite-and-offsite-campaign-measurement" />

<Accordion title="Configurar a mensuração de uma campanha on-site e off-site">

Para configurar uma <Anchor target="_blank" href="/marketers/pt/docs/data-collaboration-platform-dcp-collaboration-measurement-overview#on-site-and-off-site-campaigns">campanha on-site e off-site</Anchor>, siga estas etapas:

1. [Inicie a configuração de mensuração](#iniciar-a-configuração-de-mensuração).
2. <Anchor target="_blank" href="/marketers/pt/docs/set-up-the-campaigns-task">Configure a tarefa de campanhas</Anchor>
3. <Anchor target="_blank" href="/marketers/pt/docs/set-up-the-conversions-task">Configure a tarefa de conversões</Anchor>
4. <Anchor target="_blank" href="/marketers/pt/docs/set-up-the-engagements-task">Configure a tarefa de engajamentos</Anchor>
5. <Anchor target="_blank" href="/marketers/pt/docs/set-up-the-media-partners-task">Configure a tarefa de parceiros de mídia</Anchor>
6. <Anchor target="_blank" href="/marketers/pt/docs/set-up-the-lookback-windows-task">Configure a tarefa de janelas de lookback</Anchor>

</Accordion>

<div data-zendesk-anchors="overview=vis%C3%A3o-geral h_01K3EHANCCZ703MMMM5PTEF68B=vis%C3%A3o-geral open-measurement-settings=iniciar-a-configura%C3%A7%C3%A3o-de-mensura%C3%A7%C3%A3o h_01JJKK3CQ8F9Q7VM7MM9AFKNN5=iniciar-a-configura%C3%A7%C3%A3o-de-mensura%C3%A7%C3%A3o select-campaign-type-onsite-offsite-or-both=selecionar-o-tipo-de-campanha-on-site-off-site-ou-ambos h_01K3EHANCCW8PQ8NWC6ZHWCMGT=selecionar-o-tipo-de-campanha-on-site-off-site-ou-ambos assign-configuration-task=atribuir-a-tarefa-de-configura%C3%A7%C3%A3o h_01K3EHANCCW97TV88ECVMQKF2N=atribuir-a-tarefa-de-configura%C3%A7%C3%A3o h_01K3EHANCD71R47V88DR61CTMV=assign-a-configuration-task-to-a-collaborator h_01K3EHANCDF1HMTV8X35Q1RHTS=remove-the-configuration-task-assignment-from-a-collaborator configure-onsite-campaign-measurement=configurar-a-mensura%C3%A7%C3%A3o-de-campanhas-on-site-e-off-site h_01K3EHANCD936QN2MKFY5QSDBZ=configurar-a-mensura%C3%A7%C3%A3o-de-campanhas-on-site-e-off-site h_01KJWCMN3XRTS3361N08RT1SD6=configure-onsite-campaign-measurement::4f9b35af h_01KJWCMN3XRXW6A71P5678AHH1=configure-offsite-campaign-measurement h_01KJWCMN3XKD8YJVPQEZ53K819=configure-combined-onsite-and-offsite-campaign-measurement" />
