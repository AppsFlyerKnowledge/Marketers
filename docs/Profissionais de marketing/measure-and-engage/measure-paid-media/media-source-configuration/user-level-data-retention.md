---
title: Retenção de dados user-level
metadata:
  keywords:
    - Advertisers
    - Agencies
    - Ad Networks
    - SRN
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
    - Agencies
    - Ad Networks
  created_at: '2020-02-23T15:35:57Z'
  edited_at: '2026-11-03T01:30:30Z'
  id: 360006091197
  locale: pt
  section: Media source configuration
  section_id: 6551067072785
  url: https://support.appsflyer.com/hc/pt/articles/360006091197
---
> **Resumo:** As políticas de retenção e uso de dados user-level (dados brutos) são determinadas pela AppsFlyer, por leis relevantes e pelos termos de uso de SRNs ("**parceiros**").

> ❗️ **Atenção**
>
> Nesse artigo, essas explicações são fornecidas somente para fins informativos.  *Nada aqui declarado é aconselhamento jurídico. Esses fatos são fornecidos para sua informação e conveniência.*

## Obrigações de retenção e exclusão de dados

A AppsFlyer recebe dados user-level de aplicativos, parceiros e outras fontes.

### Disponibilidade de dados user-level para anunciantes

Normalmente, os dados user-level são disponibilizados aos anunciantes por meio de ferramentas de relatórios de dados brutos, se o pacote de assinatura incluir dados brutos durante uma janela de acesso de 90 dias (saiba mais em <Anchor target="_blank" href="/marketers/pt/docs/data-availability-windows">janelas de disponibilização de dados</Anchor>). Em alguns casos, existem <Anchor target="_blank" href="/marketers/pt/docs/about-raw-data-identifier-restrictions">restrições de dados brutos</Anchor>.

### Retenção de dados

A AppsFlyer retém dados user-level por um período de retenção limitado. Os períodos de retenção de dados brutos variam dependendo do método de entrega e dos requisitos do parceiro. No geral:

* O período de retenção de dados brutos **user-level** se baseia no tipo de integração e nos requisitos do parceiro.
* **Dados agregados** são retidos por até 25 anos.

Antes do final do período de retenção, os eventos do usuário são atribuídos à fonte de mídia que traz o usuário. Após o término do período de retenção, os eventos do usuário são atribuídos como orgânicos.

O período de retenção é determinado de acordo com o seguinte:

* <Anchor target="_blank" href="https://www.appsflyer.com/legal/processing-customer-data/">Política de privacidade dos serviços da AppsFlyer</Anchor>
* Conforme orientado, exigido ou permitido por lei
* Termos de uso e período de retenção do parceiro, conforme listado na tabela a seguir.

Considere o seguinte:

* A janela de acesso e o período de retenção podem ser diferentes
* Em alguns casos, a AppsFlyer pode prolongar a janela de acesso
* O período de retenção pode variar de acordo com o parceiro que traz o usuário
* Alguns dados user-level são atribuídos ao <Anchor target="_blank" href="/marketers/pt/docs/about-raw-data-identifier-restrictions">canal de mídia restrita</Anchor>, o que significa que os dados brutos não contêm os dados de atribuição. Isso pode ocorrer nos seguintes casos:
  * Política de compartilhamento de dados de parceiros
  * <Anchor target="_blank" href="/marketers/pt/docs/apply-aggregated-advanced-privacy-framework">Privacidade Avançada Agregada</Anchor> está ativa

#### Períodos de retenção de dados de parceiros

| SRN/partner | Partner ID (PID) | Após a instalação, exclua os dados após [x] meses |
| --- | --- | --- |
| Anúncios da Amazon | amazondsp\_int | 12 |
| Anúncios de Busca da Apple | Anúncios de Busca da Apple | Sem limite |
| Discord | discord\_int | 6 |
| DV360 | dv360\_int, doubleclick\_int | 6 |
| Google Ads* | googleadwords\_int (todos os canais) | 6 |
| Hotstar | hotstar\_int | 6 |
| Meta ads* | facebook\_int (todos os canais) | 6 |
| Microsoft | microsoftdisplay\_int e bingsearch\_int | 13 |
| Pinterest | pinterest\_int | 6 |
| Samsung DSP | samsungdsp\_int | 3 |
| Snapchat (<Anchor target="_blank" href="https://businesshelp.snapchat.com/en-US/article/attribution-terms">Termos de Serviço</Anchor>) | "snapchat\_int" | 6 |
| TikTok for Business* | tiktokglobal\_int | 13 |
| X Ads (antigo Twitter) | twitter\_int | 3 |
| Walmart | walmart\_int | 6 |

> 📘 **Atenção***
>
> Para SRNs, os períodos de retenção desta tabela se aplicam apenas aos dados fornecidos diretamente pela SRN. Eles não se aplicam a atribuições feitas por meio dos links de atribuição W2A da AppsFlyer (`googleads_int`, `metaweb_int`, `tiktokweb_int`, `snapweb_int`).

<div data-zendesk-anchors="h_01H95FY07TRAAD3K0A0TSG3RB6=aten%C3%A7%C3%A3o data-retention-and-deletion-obligations=obriga%C3%A7%C3%B5es-de-reten%C3%A7%C3%A3o-e-exclus%C3%A3o-de-dados h_01H95FY07TABPC769R7TYGY5DD=obriga%C3%A7%C3%B5es-de-reten%C3%A7%C3%A3o-e-exclus%C3%A3o-de-dados availability-of-userlevel-data-to-advertisers=disponibilidade-de-dados-user-level-para-anunciantes h_01H95FY07T2Q9QAGW5A5S6KP6J=disponibilidade-de-dados-user-level-para-anunciantes data-retention=reten%C3%A7%C3%A3o-de-dados h_01H95FY07TXS63FVDJC2NEFXYC=reten%C3%A7%C3%A3o-de-dados partner-data-retention-periods=per%C3%ADodos-de-reten%C3%A7%C3%A3o-de-dados-de-parceiros h_01H95FY07TZ4N0RRJRGJ6FN2EK=per%C3%ADodos-de-reten%C3%A7%C3%A3o-de-dados-de-parceiros h_01KRKAWSHH2WFZT9Q5M0FSBBAB=aten%C3%A7%C3%A3o-1" />
