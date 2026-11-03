---
title: Janelas de disponibilidade de dados
metadata:
  keywords:
    - Advertisers
    - Premium Feature
    - Marketers
    - Raw Reports
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-rona-einat
    - Marketers
    - Raw Reports
  created_at: '2022-01-04T03:33:13Z'
  edited_at: '2026-08-18T00:05:15Z'
  id: 4415473374865
  locale: pt
  section: Raw data reporting/APIs
  section_id: 6550930711057
  url: https://support.appsflyer.com/hc/pt/articles/4415473374865
---
> **Resumo:** a disponibilidade de dados depende do tipo de relatório e da janela de disponibilidade definida.

## Janelas de disponibilidade de dados

* Os termos **janela de disponibilidade** e **retenção de dados** têm significados diferentes. A <Anchor target="_blank" href="https://www.appsflyer.com/legal/services-privacy-policy/">retenção de dados</Anchor> corresponde ao período em que mantemos os dados brutos em nossos servidores, com uma duração maior que a janela de disponibilidade.
* A duração da janela depende do seu pacote de assinatura.
* O artigo não se aplica ao <Anchor target="_blank" href="/marketers/pt/docs/data-locker-for-marketers">Data Locker</Anchor>.

### Janela de disponibilidade de dados brutos

Uma janela de disponibilidade limita os dados fornecidos pela Pull API e pela página de exportação de dados agregados. A duração da janela depende do tipo de relatório, conforme detalhado na tabela abaixo.

| Tipo de evento de relatório | Exemplos de tipos de relatórios | Janela de disponibilidade padrão |
| --- | --- | --- |
| Atribuições | Instalações orgânicas, instalações não orgânicas, conversões de retargeting e desinstalações | 60 dos últimos 90 dias |
| Eventos in-app | Eventos in-app orgânicos, eventos in-app não orgânicos e eventos in-app de retargeting | 31 dos últimos 90 dias |

### Janela de disponibilidade de dados agregados

A janela de disponibilidade limita os dados brutos fornecidos pela Pull API e pela página de exportação de dados brutos. A duração da janela depende do tipo de relatório, conforme detalhado na tabela abaixo.

| Relatório | Janela de disponibilidade |
| --- | --- |
| Relatórios agregados | 25 meses (2 anos + 1 mês), <Anchor target="_blank" href="/marketers/pt/docs/bulletin-aggregated-ltv-data-availability">a partir da primeira instalação do aplicativo</Anchor> |

> 📄 **Veja também**
>
> * <Anchor target="_blank" href="/marketers/pt/docs/report-generation-quotas-rate-limitations">Cotas de geração de relatórios</Anchor>

<div data-zendesk-anchors="data-availability-windows=janelas-de-disponibilidade-de-dados h_01HE0FT9CNECNKYMVX9ZJJ9DNV=janelas-de-disponibilidade-de-dados raw-data-availability-window=janela-de-disponibilidade-de-dados-brutos h_01HE0FT9CNS4N1GD1AYRBSRWPF=janela-de-disponibilidade-de-dados-brutos aggregated-data-availability-window=janela-de-disponibilidade-de-dados-agregados h_01HE0FT9CPW91ASDH9MEW083ZH=janela-de-disponibilidade-de-dados-agregados h_01HE7S7VH4PC6FQAYKP6A0G4YY=veja-tamb%C3%A9m" />
