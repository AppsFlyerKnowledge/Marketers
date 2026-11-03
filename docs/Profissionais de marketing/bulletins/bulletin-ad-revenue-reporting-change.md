---
title: 'Boletim: mudança na geração de relatórios de receita de anúncios'
metadata:
  keywords:
    - ad revenue
    - Agencies
    - data freshness
    - Marketers
    - ROI360
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-michael-talapov
    - Marketers
    - Agencies
    - ROI360
  created_at: '2020-05-05T15:30:21Z'
  edited_at: '2026-10-20T03:57:12Z'
  id: 360007980057
  locale: pt
  section: Bulletins
  section_id: 6551161473041
  url: https://support.appsflyer.com/hc/pt/articles/360007980057
---
* **O que está mudando**: A data dos dados de receita de anúncios (em nível de usuário e agregado) na plataforma passa a ser o próprio dia do evento de exibição do anúncio (o dia em que a receita do anúncio ocorre), em vez do dia seguinte. Isso significa que, se um anúncio for exibido na segunda-feira, a receita aparecerá na segunda-feira. Isso dá aos anunciantes uma visão mais precisa e acionável dos dados de receita de anúncios.
* **Quem é impactado**: proprietários de aplicativos, agências
* **Onde isso está mudando**: Essencialmente, o alinhamento dos dados ao dia do evento de exibição do anúncio está ativo em todos os relatórios e APIs, para todos os tipos de integrações de network. Consulte a tabela a seguir para ver onde e quando o alinhamento entrou em vigor.

#### Mudança nos relatórios de receita de anúncios

| Método de relatório | Data de vigência (quando a mudança ocorre) | Data de publicação (data do anúncio) |
| --- | --- | --- |
| Relatórios de coorte | 13 de maio de 2020 | 7 de maio de 2020 |
| Relatório Retargeting | 17 de junho de 2020 | 14 de junho de 2020 |
| Pull API (para dados brutos) | 17 de junho de 2020 | 14 de junho de 2020 |
| Dashboard de atividades | 17 de junho de 2020 | 14 de junho de 2020 |
| Data Locker (pasta h=23) | 3 de agosto de 2020 | 3 de agosto de 2020 |
| Pull API (para dados agregados) | 1 de setembro de 2020 | 31 de agosto de 2020 |

### Antes da mudança

A data dos dados de receita de anúncios na plataforma é o dia seguinte ao próprio evento de exibição do anúncio. Isso significa que, se um anúncio for exibido na segunda-feira, a receita aparecerá na terça-feira. Os dados ficam disponíveis na plataforma na quarta-feira, após o processamento.

Isso significa que a data da receita do anúncio não está alinhada ao engajamento real do usuário. Para alguns verticais, essa falta de alinhamento distorce significativamente os KPIs.

### Depois da mudança

A mudança depende do tipo de integração entre o aplicativo e a network de monetização, como segue:

* Essa mudança afeta a receita de anúncios em nível de usuário e em nível agregado, disponível pelos métodos de geração de relatórios descritos na tabela anterior.
* A data dos dados de receita de anúncios na plataforma é o próprio dia do evento de exibição do anúncio. Isso significa que, se um anúncio for exibido na segunda-feira, a receita aparecerá na segunda-feira. Os dados ficam disponíveis nos relatórios a partir de quarta-feira, após o processamento.
* Não há nenhuma alteração nos dados históricos registrados antes da data de vigência.
* A receita na data de vigência inclui a receita de dois dias, ou seja, a receita da data de vigência e a receita do dia anterior. Dependendo do cenário de relatório, você poderá identificar um pico de receita nesse dia.

Veja o exemplo a seguir.

> 📄 **Exemplo**
>
> * A exibição de anúncios e a receita de anúncios ocorrem no Dia 0 (o dia da aquisição de usuários).
> * Os dados de receita de anúncios são extraídos no Dia 1.
> * Os dados de receita de anúncios são processados e ficam disponíveis na plataforma AppsFlyer no Dia 2.
> * Os dados de receita de anúncios são incluídos no relatório no Dia 0.
>   * No dashboard Atividade, no Data Locker (pasta h=23) e nos relatórios de dados brutos, o horário de exibição do anúncio também está disponível.
>
> [![](https://files.readme.io/b22207f1e7009f3f8f1172fbb8bf9147c1251e7d1f51864b777cbf4eab4b84e4-360010993537.jpg)](https://files.readme.io/b22207f1e7009f3f8f1172fbb8bf9147c1251e7d1f51864b777cbf4eab4b84e4-360010993537.jpg)

<div data-zendesk-anchors="ad-revenue-reporting-change=mudan%C3%A7a-nos-relat%C3%B3rios-de-receita-de-an%C3%BAncios before-the-change=antes-da-mudan%C3%A7a after-the-change=depois-da-mudan%C3%A7a" />
