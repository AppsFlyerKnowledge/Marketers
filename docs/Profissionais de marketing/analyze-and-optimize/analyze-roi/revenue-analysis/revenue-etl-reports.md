---
title: Relatórios de Revenue ETL do ROI360
metadata:
  keywords:
    - Marketers
    - revenue
    - etl
    - revenueetl
    - revenue etl
    - ROI360
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-michael-talapov
    - Marketers
    - ROI360
  created_at: '2023-06-25T16:57:02Z'
  edited_at: '2026-08-18T00:02:08Z'
  id: 16464765619985
  locale: pt
  section: Revenue analysis
  section_id: 6551069075089
  url: https://support.appsflyer.com/hc/pt/articles/16464765619985
---
> **Visão geral:** Saiba mais sobre os relatórios de receita do ROI360, suas fontes, como são gerados, quando estão disponíveis e como você pode acessá-los. Entenda os campos e a estrutura dos relatórios baixando a amostra de dados.

## ETL de receitas

Com o Revenue ETL do ROI360, seus dados de receita são enviados via Data Locker para armazenamento na nuvem para envio aos seus sistemas de BI.

A tabela a seguir mostra os relatórios de receita disponíveis. **Atenção**: Com exceção dos relatórios de Legacy ad revenue [versão única], todos os relatórios exigem uma assinatura do ROI360 Advanced.

| Relatório | Tipo de integração | Descrição | Atualização dos dados |
| --- | --- | --- | --- |
| /docs/revenue-etl-reports#ad-revenue-single-version-report-device-level<ul><li>Receita de anúncios atribuída [versão única x+1]</li><li>Receita de anúncios orgânica [versão única x+1]</li><li>Receita de anúncios de retargeting [versão única x+1]</li></ul> | <ul><li>Nível de impressão (via SDK)</li><li>Nível de dispositivo (via S2S API)</li><li>Nível de impressão (via SDK) com nível de dispositivo (via S2S API)</li></ul> | <ul><li>Contém dados de receita de anúncios.</li><li>Versão única (sem mais atualizações de dados).</li><li>Se houver integrações de API e SDK, os relatórios conterão somente dados de API.</li></ul> | <ul><li>Diariamente (disponível no dia x+1) <Anchor target="_blank" href="/marketers/pt/docs/roi360-guide-ad-revenue-attribution#data-freshness">Saiba mais</Anchor></li></ul> |
| [Legacy ad revenue [versão única]](/docs/revenue-etl-reports#ad-revenue-single-version-report-device-level):<ul><li>Receita de anúncios atribuída [versionada]</li><li>Receita de anúncios orgânica [versionada]</li><li>Receita de anúncios de retargeting [versionada]</li></ul> | <ul><li>Nível de impressão (via SDK)</li><li>Nível de dispositivo (via S2S API)</li><li>Nível de impressão (via SDK) com nível de dispositivo (via S2S API)</li></ul> | <ul><li>Contém os dados de receita de anúncios mais atualizados.</li><li><Anchor target="_blank" href="/marketers/pt/docs/data-locker-for-marketers#version-folders">Versionado</Anchor></li></ul> | <ul><li>Intradiário. <Anchor target="_blank" href="/marketers/pt/docs/roi360-guide-ad-revenue-attribution#data-freshness">Saiba mais</Anchor></li><li>Os dados são atualizados de 4 horas a 14 dias após a impressão do anúncio.</li></ul> |
| [Receita de anúncios [Nível de impressão SDK]](/docs/revenue-etl-reports#impression-level-report) | <ul><li>Nível de impressão (via SDK)</li><li>Nível de impressão (via SDK) com nível de dispositivo (via S2S API)</li></ul> | <ul><li>Contém dados de receita de anúncios do SDK.</li><li>Oferece o máximo de atualização e granularidade.</li></ul> | Por hora. <Anchor target="_blank" href="/marketers/pt/docs/roi360-guide-ad-revenue-attribution#data-freshness">Saiba mais</Anchor> |
| [Relatório de receita da loja a nível de transação](/docs/revenue-etl-reports#transactionlevel-stores-revenue-report) | Integração da receita de assinaturas e de compras in-app no ROI360 | <ul><li>Contém dados brutos de assinaturas e compras in-app, validados pelo ROI360 no nível da transação.</li><li>Oferece o máximo de atualização e granularidade.</li><li>Inclui dados exclusivos relacionados à monetização e à receita líquida no ROI360.</li></ul> | Por hora |
| [Receita da loja a nível de dispositivo [versionada]](/docs/revenue-etl-reports#devicelevel-stores-revenue-report) | Integração da receita de assinaturas e de compras in-app no ROI360 | <ul><li>Contém dados brutos de assinaturas e compras in-app, validados pelo ROI360 a nível de dispositivo.</li><li>Inclui dados exclusivos de receita líquida do ROI360.</li></ul> | A cada 8 horas |

## Relatórios

Os detalhes sobre os diferentes relatórios — como funcionam, como assiná-los e como acessá-los — podem ser encontrados nas seções a seguir.

<div id="ad-revenue-single-version-report-device-level" />

<Accordion title="[Legado] Receita de anúncios (versão única)">

O relatório mostra uma única versão dos dados de receita de anúncios de um dia, agregados a nível de dispositivo. O relatório está disponível no dia X+1 (X é o dia da ocorrência do evento de receita).

**Atenção:** Relatórios separados fornecem os dados orgânicos e de receita de retargeting. Esses relatórios são idênticos em estrutura e disponibilidade.

<span id="download-the-report-data-sample"></span>[Baixe a amostra de dados do relatório de receita de anúncios em versão única](https://docs.google.com/spreadsheets/d/e/2PACX-1vSuZYSPuAWIG-MappxQDIT3sl8UmN6MLKP2SKsbREekVAvKSHuUAUAtUE6JapanANJbKsTzCOID8z7G/pub?output=xlsx).

#### Fontes de dados

Dependendo do tipo de parceiro de receita de anúncios, os dados do relatório podem ser enviados via:

* **SDK**: Cargas de dados a nível de impressão, enviadas pelo conector ROI360 Ad Revenue SDK.
* **S2S:** Relatórios a nível de dispositivo obtidos por uma solicitação da API de parceiros (redes de mediação ou monetização).

Para saber como definir o tipo de integração, consulte: Conectar-se a parceiros integrados de receita de anúncios.

#### Fluxo de dados

1. **Ingestão de dados:** O relatório pode se originar do conector de ad revenue SDK ou da solicitação da API S2S (consulte a seção acima).
2. **Processamento de dados**: O ROI360 Ad Revenue da AppsFlyer realiza o seguinte:

   1. Normalização de dados,
   2. Atribuição à fonte de instalação e enriquecimento de dados,
   3. Geração de eventos de receita de anúncios,
   4. Os eventos são agregados a nível de dispositivo

   **Atenção:** Um relatório pode ter mais de uma agregação a nível de dispositivo para o mesmo dispositivo. Isso pode acontecer porque a agregação a nível de dispositivo se baseia nas dimensões relacionadas à monetização, como rede de monetização, posição e tipo de anúncio. Por exemplo, se o aplicativo exibir anúncios em dois canais diferentes, os eventos de receita de cada canal serão agregados separadamente no nível do dispositivo.
3. **Entrega de dados**: Os dados a nível de dispositivo são registrados na versão única do relatório.

#### Quando os dados do relatório ficam disponíveis?

| Tipo de integração | Dia da versão (X = dia de ocorrência do evento de receita) | Versão disponível em | A versão inclui eventos de receita que ocorrem entre |
| --- | --- | --- | --- |
| SDK | Dia X+1 | 20:00 | 00:00 – 24:00 |
| SDK + S2S | Dia X+1 | 17:00 | 00:00 – 24:00 |

#### Como assinar o relatório?

1. Na AppsFlyer, no menu lateral, selecione **Relatório** > **Data Locker**.
2. No dashboard de **conteúdos do Data Locker**, vá até o bloco **ROI360 RevenueETL**.
3. Selecione **Receita atribuída [versão única].**

**Atenção:** Você também pode selecionar o mesmo relatório para retargeting e orgânico (Retargeting/Receita de anúncios orgânica [versão única]).

#### Como acessar o relatório no seu bucket?

O caminho (path) para o relatório consiste na seguinte hierarquia de pastas:

Com o seguinte formato: `<bucket-name>/t=attributed_ad_revenue/dt=<dt=yyyy-mm-dd>/h=23/`

#### Hierarquia de pastas de relatório

Exemplo da hierarquia da pastas de relatórios de versão única de receita de anúncios atribuída no bucket do anunciante:

```
bucket
|
└── t=attributed_ad_revenue
    |
    ├── dt=2023-06-02
    |   |
    |   └── h=23
    |        |
    |        ├── part-00000-4762858-d62a-446e-b499-dd05f2d5434d-c000.csv.gz
    |        |
    |        ├── part-00001-4762858-d62a-446e-b499-dd05f2d5434d-c000.csv.gz
    |        │
    |        └── part-00002-4762858-d62a-446e-b499-dd05f2d5434d-c000.csv.gz
    |
    ├── dt=2023-06-01
    |   |
    |   └── h=23
    |        |
    |        ├── part-00000-1d295376-d024-4321-8d34-1fbb37cbb58d-c000.csv.gz
    |        |
    |        ├── part-00001-1d295376-d024-4321-8d34-1fbb37cbb58d-c000.csv.gz
    |        │
    |        └── part-00002-1d295376-d024-4321-8d34-1fbb37cbb58d-c000.csv.gz
    |
    ├── dt=2023-05-31
    |   |
    .   . 
    .   .
```

**Legenda:**

* **dt**: data em que ocorreram os eventos de receita incluídos no relatório.
* **t:** tipo de relatório.
* **h:** hora de criação da versão única

</Accordion>

<div id="ad-revenue-versioned-report-device-level" />

<Accordion title="Receita de anúncios (versionada)">

O relatório mostra várias versões dos dados de receita de uma única data. Por exemplo, a receita obtida em 21 de junho é reportada em 21 de junho, 22 de junho, 23 de junho, 24 de junho, 28 de junho e 5 de julho.

O objetivo de coletar várias versões do mesmo dia é capturar as variações do cálculo da receita decorrentes de condições que dependem do tempo. Por exemplo, impressões que tiveram valor de receita em tempo real podem ter um valor diferente um dia depois.

**Atenção:** Relatórios separados fornecem os dados orgânicos e de receita de retargeting. Esses relatórios são idênticos em estrutura e disponibilidade.

[Baixe a amostra de dados do relatório versionado](https://docs.google.com/spreadsheets/d/e/2PACX-1vQek1x3rYnYQq3jctSz5hnWG_Nk_LQk2ixMTQFVMb8K6w-UmeNKvKOif3-nudAyIqp9tyuoq9R-FhVz/pub?output=csv).

#### Fontes de dados

Dependendo do tipo de integração do seu parceiro, os dados do relatório podem se originar via:

* **SDK**: Cargas de dados a nível de impressão, enviadas pelo conector ROI360 Ad Revenue SDK.
* **S2S:** Relatórios a nível de dispositivo obtidos por uma solicitação da API de parceiros (redes de mediação ou monetização).
* **S2S + SDK:** Cargas úteis originadas do SDK e do S2S.

Para saber como definir o tipo de integração, consulte: Conectar-se a parceiros integrados de receita de anúncios.

#### Fluxo de dados

1. **Ingestão de dados:** O relatório pode se originar ou do SDK ou da solicitação da API S2S (veja seção acima).
2. **Processamento de dados:** O ROI360 Ad Revenue da AppsFlyer realiza o seguinte:

   1. Normalização de dados,
   2. Atribuição à fonte de instalação e enriquecimento de dados,
   3. Geração de eventos de receita de anúncios,
   4. Os eventos são agregados a nível de dispositivo

   **Atenção:** Um relatório pode ter mais de uma agregação a nível de dispositivo para o mesmo dispositivo. Isso pode acontecer porque a agregação a nível de dispositivo se baseia nas dimensões relacionadas à monetização, como rede de monetização, posição e tipo de anúncio. Por exemplo, se o aplicativo exibir anúncios em dois canais diferentes, os eventos de receita de cada canal serão agregados separadamente no nível do dispositivo.
3. **Entrega de dados**: Os dados a nível de dispositivo são registrados em várias versões do relatório de acordo com um cronograma predeterminado (especificado abaixo).

#### Quando as versões do relatório estão disponíveis?

A tabela fornecida abaixo descreve os cronogramas de geração para as versões S2S e SDK. Os clientes que se beneficiam do ROI360 Ad Revenue Freshness to Accuracy receberão as duas versões, garantindo a melhor precisão e informações atualizadas.

**Atenção:** Algumas versões originadas pelo S2S podem não ser criadas. Se os dados do(s) parceiro(s) não mudaram desde a última extração, uma nova versão NÃO será gerada.

| Tipo de integração | Dia da versão (X = dia de ocorrência do evento de receita) | Versão disponível em | A versão inclui eventos de receita que ocorrem entre |
| --- | --- | --- | --- |
| SDK | Dia X | 03:00-04:00 | 00:00 – 03:00 |
| SDK | Dia X | 07:00-08:00 | 00:00 – 07:00 |
| SDK | Dia X | 11:00-12:00 | 12:00-13:00 |
| SDK | Dia X | 15:00-16:00 | Receita de anúncios (versionada) |
| SDK | Dia X | 19:00-20:00 | Oferece o máximo de atualização e granularidade. |
| SDK | Dia X | 23:00-24:00 | 00:00 – 23:00 |
| SDK | Dia X+1 | 04:00-05:00 | 00:00 – 03:00 |
| S2S | Dia X+1 | 10:00-11:00 | 00:00 – 03:00 |
| S2S | Dia X+1 | /docs/revenue-etl-reports#ad-revenue-single-version-report-device-level | 00:00 – 03:00 |
| S2S | Dia X+2 | 00:00-01:00 | 00:00 – 03:00 |
| S2S | Dia X+2 | 13:00-14:00 | 00:00 – 03:00 |
| S2S | Dia X+3 | 06:00-07:00 | 00:00 – 03:00 |
| S2S | Dia X+7 | 08:00-09:00 | 00:00 – 03:00 |
| S2S | Dia X+14 | 11:00-12:00 | 00:00 – 03:00 |
| SDK + S2S | Todas as versões do SDK e S2S acima |  |  |

#### Como assinar o relatório?

1. Na AppsFlyer, no menu lateral, selecione **Relatório** > **Data Locker**.
2. No dashboard de **conteúdos do Data Locker**, vá até o bloco **ROI360 RevenueETL**.
3. Selecione **Receita de anúncios atribuída [versionada].**

**Atenção:** Você também pode selecionar o mesmo relatório para retargeting e orgânico (Retargeting/Receita de anúncios orgânica [versionada]).

#### Como acessar o relatório no seu bucket?

O caminho (path) para o relatório consiste na seguinte hierarquia de pastas:

`<bucket-name>/t=attributed_ad_revenue_v2/dt=<dt=yyyy-mm-dd>/version=<9999999>/`

#### Hierarquia de pastas de relatório

Um exemplo da árvore de relatórios no bucket do anunciante:

```
bucket
|
└── t=attributed_ad_revenue_v2
    |
    └── dt=2023-06-01
        |
        ├── version=1685588879
        |   |
        │   ├── part-00000-4762858-d62a-446e-b499-dd05f2d5434d-c000.csv.gz
        |   |
        │   ├── part-00001-4762858-d62a-446e-b499-dd05f2d5434d-c000.csv.gz
        |   │
        |   └── part-00002-4762858-d62a-446e-b499-dd05f2d5434d-c000.csv.gz
        |
        ├── version=1685603326
        |   |
        │   ├── part-00000-1d295376-d024-4321-8d34-1fbb37cbb58d-c000.csv.gz
        |   |
        │   ├── part-00001-1d295376-d024-4321-8d34-1fbb37cbb58d-c000.csv.gz
        |   │
        |   └── part-00002-1d295376-d024-4321-8d34-1fbb37cbb58d-c000.csv.gz
        |
        ├── version=1685617877
        .
                .
                .
```

* **Legenda:**
  * **t:** tipo de relatório
  * **dt**: data em que ocorreram os eventos de receita incluídos no relatório.
  * **version:** o nome da versão é o timestamp da data e hora de criação da versão, por exemplo, **version=1685588879.**
* A origem da versão, seja S2S ou SDK, pode ser exibida no momento da criação da versão. As primeiras versões do SDK são originadas do SDK. As outros são originadas via S2S.

| Tipo de integração | Dia da versão (X = dia de ocorrência do evento de receita) | Versão disponível em | A versão inclui eventos de receita que ocorrem entre |
| --- | --- | --- | --- |
| SDK | Dia X | 03:00-04:00 | 00:00 – 03:00 |
| SDK | Dia X | 07:00-08:00 | 00:00 – 07:00 |
| SDK | Dia X | 11:00-12:00 | 00:00 – 11:00 |
| SDK | Dia X | 15:00-16:00 | 00:00 – 15:00 |
| SDK | Dia X | 19:00-20:00 | 00:00 – 19:00 |
| SDK | Dia X | 23:00-24:00 | 00:00 – 23:00 |
| SDK | Dia X+1 | 04:00-05:00 | 00:00 – 24:00 |
| S2S | Dia X+1 | 10:00-11:00 | 00:00 – 24:00 |
| S2S | Dia X+1 | 18:00-19:00 | 00:00 – 24:00 |
| S2S | Dia X+2 | 00:00-01:00 | 00:00 – 24:00 |
| S2S | Dia X+2 | 13:00-14:00 | 00:00 – 24:00 |
| S2S | Dia X+3 | 06:00-07:00 | 00:00 – 24:00 |
| S2S | Dia X+7 | 08:00-09:00 | 00:00 – 24:00 |
| S2S | Dia X+14 | 11:00-12:00 | 00:00 – 24:00 |

</Accordion>

<div id="impression-level-report" />

<Accordion title="Receita de anúncios (Nível de impressão no SDK)">

O relatório mostra dados a nível de impressão divididos em pastas por hora de ocorrência. Cada pasta contém **somente impressões que ocorreram durante aquela hora**.

[Faça o download da amostra de dados do relatório a nível de impressão de receita de anúncios](https://docs.google.com/spreadsheets/d/e/2PACX-1vR5zVxFGaCMNZMbCCYPae6f7MmbtelxrqXb-A5DBENuyTFCN4deRfICvbL0_dNeYVipojmAeUdrGbKI/pub?output=csv)

#### Fonte de dados

Os dados do relatório se originam de dados a nível de impressão enviados pelo conector ROI360 Ad Revenue SDK e exigem uma integração do tipo SDK.

Para saber como definir o tipo de integração, consulte: Conectar-se a parceiros integrados de receita de anúncios.

#### Fluxo de dados

1. **Ingestão de dados:** Os dados do relatório se originam de dados a nível de impressão enviados pelo conector ROI360 Ad Revenue SDK e exigem uma integração do tipo SDK.
2. **Processamento de dados**: O ROI360 Ad Revenue da AppsFlyer realiza o seguinte:
   1. Normalização de dados,
   2. Atribuição à fonte de instalação e enriquecimento de dados,
   3. Geração de eventos de receita de anúncios a nível de impressão.
3. **Entrega de dados**: Os eventos de impressão são gravados em arquivos divididos por pastas de acordo com a hora da ocorrência. Cada pasta contém somente impressões que ocorreram durante aquela hora.

#### Quando os dados do relatório ficam disponíveis?

| Tipo de integração | Dia da versão (X = dia de ocorrência do evento de receita) | Versão disponível em |
| --- | --- | --- |
| SDK | Dia X | No final de cada hora reportada |

#### Como assinar o relatório?

1. Na AppsFlyer, no menu lateral, selecione **Relatório** > **Data Locker**.
2. No dashboard de **conteúdos do Data Locker**, vá até o bloco **ROI360 RevenueETL**.
3. Selecione **Receita de anúncios [Nível de impressão SDK].**

#### Como acessar o relatório no seu bucket?

O caminho (path) para o relatório consiste na seguinte hierarquia de pastas:

`<bucket-name>/t=attributed_adrevenue_sdk_impression_level/dt=<dt=yyyy-mm-dd>/h=<hh>`

#### Hierarquia de pastas de relatório

Um exemplo da árvore de relatórios no bucket do anunciante:

```
bucket
|
└── t=attributed_adrevenue_sdk_impression_level/
    |
    ├── dt=2023-06-01
    |   |
    |   ├── h=0
    |   |   |
    |   │   ├── part-00000-4762858-d62a-446e-b499-dd05f2d5434d-c000.csv.gz
    |   ├── h=1
    |   |   |
    |   │   ├── part-00000-4762858-d62a-446e-b499-dd05f2d5434d-c000.csv.gz
    |   ├── h=2
    |   .   |
    |   .   ├── part-00000-4762858-d62a-446e-b499-dd05f2d5434d-c000.csv.gz
    |   .   .
    |   ├── h=23
    |   |   |
    |   │   ├── part-00000-4762858-d62a-446e-b499-dd05f2d5434d-c000.csv.gz
    |   └── h=24
    |       |
    |       └── part-00000-4762858-d62a-446e-b499-dd05f2d5434d-c000.csv.gz
    |    
    ├── dt=2023-06-02
    |   |  
    |   ├── h=0
        .   .
        .   .
```

**Legenda:**

* **t:** tipo de relatório
* **dt**: data em que ocorreram os eventos de receita incluídos no relatório.
* **h**: pasta por hora, que contém um arquivo CSV com as impressões que ocorreram durante aquela determinada hora.

</Accordion>

<div id="transactionlevel-stores-revenue-report" />

<Accordion title="Relatório de receita da loja a nível de transação">

Esse relatório apresenta dados brutos diários a nível de transação, divididos em pastas por hora, que contêm somente as transações relevantes para aquela hora.

[Faça o download da amostra de dados do relatório a nível de transação](https://docs.google.com/spreadsheets/d/e/2PACX-1vRGlRSg_Xrp2EsqK2uaisjhlqeSuZsypqKqSSRGX3AQBwBLlNdG_5LOOKCM9f9gCcLguMQgQwT--Dz7/pub?output=csv)

#### Fontes de dados

Os dados do relatório se originam de transações coletadas por meio do conector ROI360 SDK Purchase e de notificações de armazenamento S2S.

#### Fluxo de dados

1. Os dados do relatório se originam de transações coletadas por meio do conector ROI360 SDK Purchase ou das notificações das lojas S2S.
2. O ROI360 VIAP/Subscriptions da AppsFlyer processa os dados, os atribui e cria eventos e valores a nível de transação.
3. Os eventos a nível de transação são registrados no relatório, separados em pastas por hora.

#### Quando os dados do relatório ficam disponíveis?

| Dia da versão (X = dia de ocorrência do evento de receita) | Versão disponível em |
| --- | --- |
| Dia X | No final de cada hora reportada |

#### Como assinar o relatório?

1. Na AppsFlyer, no menu lateral, selecione **Relatório** > **Data Locker**.
2. No dashboard de **conteúdos do Data Locker**, vá até o bloco **ROI360 RevenueETL**.
3. Selecione **Relatório de receita da loja a nível de transação.**

#### Como acessar o relatório no seu bucket?

O caminho (path) para o relatório consiste na seguinte hierarquia de pastas:

`<bucket-name>/t=stores_rawdata/dt=<dt=yyyy-mm-dd>/h=<hh>`

#### Hierarquia de pastas de relatório

Um exemplo da árvore de relatórios no bucket do anunciante:

```
bucket
|
└── t=stores_rawdata
    |
    ├── dt=2023-06-01
    |   |
    |   ├── h=0
    |   |   |
    |   │   ├── part-00000-4762858-d62a-446e-b499-dd05f2d5434d-c000.csv.gz
    |   ├── h=1
    |   |   |
    |   │   ├── part-00000-4762858-d62a-446e-b499-dd05f2d5434d-c000.csv.gz
    |   ├── h=2
    |   .   |
    |   .   ├── part-00000-4762858-d62a-446e-b499-dd05f2d5434d-c000.csv.gz
    |   .   .
    |   ├── h=23
    |   |   |
    |   │   ├── part-00000-4762858-d62a-446e-b499-dd05f2d5434d-c000.csv.gz
    |   └── h=24
    |       |
    |       └── part-00000-4762858-d62a-446e-b499-dd05f2d5434d-c000.csv.gz
    |    
    ├── dt=2023-06-02
    |   |  
    |   ├── h=0
        .   .
        .   .
```

**Legenda:**

* **t:** tipo de relatório.
* **dt**: data em que ocorreram os eventos de receita incluídos no relatório.
* **h**: Pasta por hora contendo o arquivo CSV com as transações que ocorreram durante aquela determinada hora.

</Accordion>

<div id="devicelevel-stores-revenue-report" />

<Accordion title="Relatório de receitas da loja a nível de dispositivo (versionado)">

O relatório de receitas da loja a nível de dispositivo especifica eventos in-app de compras e assinaturas com renovação automática capturados pelos produtos do ROI360. Esses eventos incluem dimensões exclusivas relacionadas à monetização no ROI360. Eventos in-app emitidos pelo cliente não são incluídos nesse relatório.

<span id="download-the-report-data-sample::8cbba4e3"></span>[Faça o download da amostra de dados do relatório de receitas da loja a nível de dispositivo](https://docs.google.com/spreadsheets/d/e/2PACX-1vSpomvcf2axYeSFcCh0kEx3ShYYRGVfF9WYZXG1UYBkeymeVfh8mcypAOpq2drqE3zhdmbcmrMtahsl/pub?output=csv)

#### Fontes de dados

Os dados do relatório se originam de transações coletadas via:

1. Conector ROI360 SDK Purchase.
2. Lojas (por exemplo, a App Store e a Google Play Store) por meio de notificações S2S.

#### Fluxo de dados

1. Os dados do relatório se originam de transações coletadas por meio do conector ROI360 SDK Purchase ou das notificações das lojas S2S.
2. O ROI360 VIAP/Subscriptions da AppsFlyer processa os dados, os atribui e cria eventos in-app.
3. Os eventos in-app são agregados a nível de dispositivo e registrados em uma versão do relatório a cada quatro horas.

#### Quando as versões do relatório estão disponíveis?

| Dia da versão (X = dia de ocorrência do evento de receita) | Versão disponível em | A versão inclui eventos de receita que ocorrem entre |
| --- | --- | --- |
| Dia X | 04:00 - 05:00 | 00:00 – 04:00 |
| Dia X | 12:00 - 13:00 | 00:00 – 12:00 |
| Dia X | 20:00 - 21:00 | 00:00 – 20:00 |
| Dia X+1 | 05:00 - 06:00 | 00:00 – 24:00 |

#### Como assinar o relatório?

1. Na AppsFlyer, no menu lateral, selecione **Relatório** > **Data Locker**.
2. No dashboard de **conteúdos do Data Locker**, vá até o bloco **ROI360 RevenueETL**.
3. Selecione **Relatório de receitas da loja a nível de dispositivo [versionado]**.

#### Como acessar o relatório no seu bucket?

O caminho (path) para o relatório consiste na seguinte hierarquia de pastas:

`<bucket-name>/t=stores_devicedata/dt=<dt=yyyy-mm-dd>/version=<999999999>`

#### Hierarquia de pastas de relatório

Um exemplo da árvore de relatórios no bucket do anunciante:

```
bucket
|
└── t=stores_devicedata
    |
    └── dt=2023-06-01
        |
        ├── version=1685588879
        |   |
        │   ├── part-00000-4762858-d62a-446e-b499-dd05f2d5434d-c000.csv.gz
        |   |
        │   ├── part-00001-4762858-d62a-446e-b499-dd05f2d5434d-c000.csv.gz
        |   │
        |   └── part-00002-4762858-d62a-446e-b499-dd05f2d5434d-c000.csv.gz
        |
        ├── version=1685603326
        |   |
        │   ├── part-00000-1d295376-d024-4321-8d34-1fbb37cbb58d-c000.csv.gz
        |   |
        │   ├── part-00001-1d295376-d024-4321-8d34-1fbb37cbb58d-c000.csv.gz
        |   │
        |   └── part-00002-1d295376-d024-4321-8d34-1fbb37cbb58d-c000.csv.gz
        |
        ├── version=1685617877
        .
                .
                .
```

**Legenda:**

* **t:** tipo de relatório.
* **dt**: data em que ocorreram os eventos de receita incluídos no relatório.
* **version**: o nome da versão é o timestamp da data e hora de criação da versão, por exemplo, **version=1685588879.**

</Accordion>

<div data-zendesk-anchors="revenue-etl=etl-de-receitas h_01HMBTDD8TASZ2NEBXP7CZ3Q81=etl-de-receitas reports=relat%C3%B3rios h_01HME0BBF2M47M2AV437RYQ070=relat%C3%B3rios h_01HETBAQVVYW14END06HBPBQSN=ad-revenue-single-version-report-device-level h_01HETBAQVVZB87JNT0JVYSP80D=download-the-report-data-sample the-report-data-sources=fontes-de-dados h_01HETBAQVVSKVDM4J90A0WGFJW=fontes-de-dados the-report-data-flow=fluxo-de-dados h_01HETBAQVV97R7G6F67RM6K62K=fluxo-de-dados when-is-the-report-data-available=quando-os-dados-do-relat%C3%B3rio-ficam-dispon%C3%ADveis h_01HETBAQVVKDAWW2S98TG6682S=quando-os-dados-do-relat%C3%B3rio-ficam-dispon%C3%ADveis how-to-subscribe-to-the-report=como-assinar-o-relat%C3%B3rio h_01HETBAQVVFSDRW778VQSSE107=como-assinar-o-relat%C3%B3rio how-to-access-the-report-in-dl=como-acessar-o-relat%C3%B3rio-no-seu-bucket h_01HETBAQVV15T92VXRHG2CP2KJ=como-acessar-o-relat%C3%B3rio-no-seu-bucket the-report-folder-hierarchy-in-aws=hierarquia-de-pastas-de-relat%C3%B3rio h_01HETBAQVVA750VTE1ABSM2M47=hierarquia-de-pastas-de-relat%C3%B3rio h_01HETBAQVVCB2SYMW9876HPE7N=ad-revenue-versioned-report-device-level data-sources=fontes-de-dados-1 h_01HMTZ9VQ5WE6D7E5NEBYH71SZ=fontes-de-dados-1 data-flow=fluxo-de-dados-1 h_01HMTZ9VQ5PS8G9JTQ2YXF1G7X=fluxo-de-dados-1 when-are-the-report-versions-available=quando-as-vers%C3%B5es-do-relat%C3%B3rio-est%C3%A3o-dispon%C3%ADveis h_01HETBAQVVP1M40KHB66AW545S=quando-as-vers%C3%B5es-do-relat%C3%B3rio-est%C3%A3o-dispon%C3%ADveis how-to-subscribe-to-the-report::cae4aa15=como-assinar-o-relat%C3%B3rio-1 h_01HMTZ9VQ5BBFNNE7Z8EP084CF=como-assinar-o-relat%C3%B3rio-1 how-to-access-the-report-in-your-bucket=como-acessar-o-relat%C3%B3rio-no-seu-bucket-1 h_01HMTZ9VQ5FGBC56AP4R49P4BX=como-acessar-o-relat%C3%B3rio-no-seu-bucket-1 report-folder-hierarchy=hierarquia-de-pastas-de-relat%C3%B3rio-2 h_01HMTZ9VQ5HCKP7T3JQ2RHZV50=hierarquia-de-pastas-de-relat%C3%B3rio-2 h_01HETBAQVVR90NJC522WNAG190=impression-level-report the-source-of-the-report-data=fonte-de-dados h_01HETBAQVV3KBEW4VV4RY9VRA2=fonte-de-dados data-flow::c7ffb834=fluxo-de-dados-2 h_01HMTZ9VQ5J837PGG99S8ARAGV=fluxo-de-dados-2 when-is-the-report-data-available::272621c9=quando-os-dados-do-relat%C3%B3rio-ficam-dispon%C3%ADveis-1 h_01HMTZ9VQ5YQKBQ779YWBWESDZ=quando-os-dados-do-relat%C3%B3rio-ficam-dispon%C3%ADveis-1 how-to-subscribe-to-the-report::67646c99=como-assinar-o-relat%C3%B3rio-2 h_01HMTZ9VQ5ZST1M7JYKFC3DA62=como-assinar-o-relat%C3%B3rio-2 how-to-access-the-report-in-aws-the-bucket=como-acessar-o-relat%C3%B3rio-no-seu-bucket-2 h_01HETBAQVVHE80MH3SM3GX21V1=como-acessar-o-relat%C3%B3rio-no-seu-bucket-2 report-folder-hierarchy::26ec73c6=hierarquia-de-pastas-de-relat%C3%B3rio-2 h_01HMTZ9VQ5FFSA1XF7YSATM6WH=hierarquia-de-pastas-de-relat%C3%B3rio-2 h_01HETBAQVWZKYBAG5E71KVB9PM=transactionlevel-stores-revenue-report data-sources::68e71455=fontes-de-dados-2 h_01HMTZ9VQ5SWTWTSNW5M9KJ1XN=fontes-de-dados-2 data-flow::bde19643=fluxo-de-dados-4 h_01HMTZ9VQ6XVHDHBKV86F3Q9DJ=fluxo-de-dados-4 when-is-the-report-data-available::87d17fc2=quando-os-dados-do-relat%C3%B3rio-ficam-dispon%C3%ADveis-2 h_01HMTZ9VQ64AJQM861M6ENHVWC=quando-os-dados-do-relat%C3%B3rio-ficam-dispon%C3%ADveis-2 how-to-subscribe-to-the-report::6569d202=como-assinar-o-relat%C3%B3rio-3 h_01HMTZ9VQ60HMM6TXAPYSZG5CT=como-assinar-o-relat%C3%B3rio-3 how-to-access-the-report-in-your-bucket::b136ba80=como-acessar-o-relat%C3%B3rio-no-seu-bucket-3 h_01HMTZ9VQ67ZEX3KM6CV32SNBD=como-acessar-o-relat%C3%B3rio-no-seu-bucket-3 report-folder-hierarchy::805d4d8=hierarquia-de-pastas-de-relat%C3%B3rio-4 h_01HMTZ9VQ68VRJRHXSNAE38A0E=hierarquia-de-pastas-de-relat%C3%B3rio-4 h_01HETBAQVVWAFEMK8ENWN7DYEY=devicelevel-stores-revenue-report h_01HETBAQVV9PSDJNS76SNX522C=download-the-report-data-sample::8cbba4e3 the-report-data-sources::af31e5d1=fontes-de-dados-3 h_01HETBAQVWE2R75D034VCYMTR1=fontes-de-dados-3 the-report-data-processing-flow=fluxo-de-dados-4 h_01HETBAQVWZRBE84NV403BCZ9F=fluxo-de-dados-4 when-are-the-report-versions-available::2f1bc55f=quando-as-vers%C3%B5es-do-relat%C3%B3rio-est%C3%A3o-dispon%C3%ADveis-1 h_01HETBAQVWQFCKHMT6PJNPXX7D=quando-as-vers%C3%B5es-do-relat%C3%B3rio-est%C3%A3o-dispon%C3%ADveis-1 how-to-subscribe-to-the-report::a624afde=como-assinar-o-relat%C3%B3rio-4 h_01HETBAQVW54MD9Q09RNC673PE=como-assinar-o-relat%C3%B3rio-4 how-to-access-the-report-in-the-aws-bucket=como-acessar-o-relat%C3%B3rio-no-seu-bucket-4 h_01HETBAQVWYDR81WS9Q9G20ZND=como-acessar-o-relat%C3%B3rio-no-seu-bucket-4 the-report-folder-hierarchy-in-aws::45c0d598=hierarquia-de-pastas-de-relat%C3%B3rio-4 h_01HETBAQVWXHK6DXFA90GJQWPV=hierarquia-de-pastas-de-relat%C3%B3rio-4" />
