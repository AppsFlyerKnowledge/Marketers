---
title: Alterando as configurações de moeda do aplicativo
metadata:
  keywords:
    - Marketers
    - Platform essentials
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-negri
    - Marketers
    - Platform essentials
  created_at: '2025-12-24T08:22:42Z'
  edited_at: '2026-08-18T00:17:47Z'
  id: 42223406543249
  locale: pt
  section: Manage your apps
  section_id: 6551015977105
  url: https://support.appsflyer.com/hc/pt/articles/42223406543249
---
> **Em resumo:** Gerencie facilmente as configurações de moeda do seu aplicativo para alinhar o relatório de receita às necessidades da sua empresa. Este artigo esclarece como as alterações de moeda afetam seus dados históricos e futuros, ajuda você a entender quem pode fazer alterações e descreve as etapas de aprovação necessárias.

## **Sobre a alteração das configurações de moeda do aplicativo**

Por padrão, os dashboards da AppsFlyer exibem os dados usando a moeda local selecionada por você. Você pode alternar facilmente para a visualização em USD a qualquer momento, sem alterar as configurações reais de moeda do seu aplicativo.

Se você estiver visualizando dados de vários aplicativos com moedas locais diferentes, o dashboard muda automaticamente para USD por padrão.

## **Quem pode alterar a moeda do aplicativo?**

As alterações de moeda dependem dos dados existentes do seu aplicativo:

* **Aplicativos sem receita ou custo:** Você pode alterar a moeda diretamente.
* **Aplicativos com receita ou custo:** Somente um **administrador da AppsFlyer** pode fazer a alteração.  
  Para solicitar uma alteração de moeda:

1. Entre em contato com seu representante da AppsFlyer ou envie um ticket de suporte.
2. Forneça os detalhes do seu aplicativo.
3. Anexe uma aprovação por escrito reconhecendo o impacto ao reportar.

## **Como as alterações de moeda afetam seus dados**

Alterar a moeda do seu aplicativo afeta a exibição e a precisão dos dados de receita:

<div id="future-data" />

<Accordion title="Dados futuros">

Depois que a moeda for alterada, todos os eventos futuros com o parâmetro af\_revenue usarão a nova moeda. Os relatórios após a alteração refletirão isso, mas relatórios que abrangem a data da alteração podem mostrar moedas diferentes.

</Accordion>

<div id="historical-data-accuracy" />

<Accordion title="Precisão dos dados históricos">

Os dados históricos permanecem, mas se tornam imprecisos:

* Os eventos de receita anteriores à alteração permanecem na moeda antiga.
* Os eventos de receita posteriores à alteração usam a nova moeda.
* Essa mistura causa imprecisões em métricas como LTV e ROAS.

O impacto varia:

* **Histórico extenso de receita:** Discrepâncias significativas.
* **Histórico mínimo de receita:** Menor impacto.

</Accordion>

### **Exemplo**

<div id="reporting-impacts" />

<Accordion title="Impactos de reportar">

Se você alterar a moeda do seu aplicativo em **1º de outubro**, veja como os métodos de reportar receita são afetados:

| **Método de relatório** | **Antes de 1º de out** | **Abrangendo 1º de out** | **Após 1º de out** |
| --- | --- | --- | --- |
| **LTV & coorte (D0–180)** | Moedas mistas (impreciso) | Moedas mistas (impreciso) | Precisa |
| **atividade** | Mostra a moeda anterior | Moedas mistas (impreciso) | Precisa |
| **Métricas** | Preciso até 7 dias antes da alteração | Moedas mistas (impreciso) | Precisa |

</Accordion>

> 🚧 **Importante!**
>
> * As alterações de moeda são **permanentes**.
> * Os dados históricos **não podem ser convertidos nem restaurados**.
> * Confirme todas as implicações com seu gerente de conta da AppsFlyer antes de fazer alterações.

<div data-zendesk-anchors="about-changing-app-currency-settings=sobre-a-altera%C3%A7%C3%A3o-das-configura%C3%A7%C3%B5es-de-moeda-do-aplicativo h_01KD7Q6FR8VKG3HGXDJC6YB5J3=sobre-a-altera%C3%A7%C3%A3o-das-configura%C3%A7%C3%B5es-de-moeda-do-aplicativo who-can-change-the-app-currency=quem-pode-alterar-a-moeda-do-aplicativo h_01KD7Q6FR96NRV4SBRQ8YEW12X=quem-pode-alterar-a-moeda-do-aplicativo how-currency-changes-impact-your-data=como-as-altera%C3%A7%C3%B5es-de-moeda-afetam-seus-dados h_01KD7Q6FRB9TCV2N0KT2N4599A=como-as-altera%C3%A7%C3%B5es-de-moeda-afetam-seus-dados h_01KD7QJQ4FF197R69RAD5Q6KKT=future-data h_01KD7QM57R8TJY5T10R36EB1P9=historical-data-accuracy example=exemplo h_01KD7QW856FFEQ779153KNCYW6=exemplo h_01KD7QG6CB2KFGXE6D4M46B65H=reporting-impacts h_01KD7QS7EYS21KX0Q9WB7ETV99=importante" />
