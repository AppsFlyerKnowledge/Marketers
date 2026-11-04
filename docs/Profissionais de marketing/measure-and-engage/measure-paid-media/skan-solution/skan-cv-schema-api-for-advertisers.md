---
title: API de esquema SKAN CV para anunciantes
metadata:
  keywords:
    - Developers
    - Marketers
    - SKAdNetwork (SKAN)
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - SKAdNetwork (SKAN)
  created_at: '2022-08-24T12:59:10Z'
  edited_at: '2026-08-19T00:31:06Z'
  id: 8610329713553
  locale: pt
  section: SKAN solution
  section_id: 6552135379985
  url: https://support.appsflyer.com/hc/pt/articles/8610329713553
---
> **Em resumo:** Veja o esquema atual de valor de conversão (CV) do SKAdNetwork (SKAN) conforme configurado no AppsFlyer Conversion Studio.

<div id="skan-conversion-value-schema-api" />

## API do esquema de valor de conversão da SKAN

<div id="api-basics" />

<Accordion title="Noções básicas da API">

| Escritórios | Veja o esquema atual de valor de conversão (CV) do SKAdNetwork (SKAN) conforme configurado no AppsFlyer Conversion Studio.<br /><br />**Observação**:<ul><li>O histórico do esquema de CV da SKAN não está disponível.</li><li>Você também pode ver seu esquema da SKAN baixando o arquivo de mapeamento CSV disponível no Conversion Studio.</li></ul> |
| --- | --- |
| Caminho | `https://hq1.appsflyer.com/api/skan-pull-cs-api/v1/conversion-studio-schema/app/<app_id>` |
| Parâmetros de caminho (obrigatórios) | `<app_id>`: é o identificador do Aplicativo, conforme encontrado no dashboard do AppsFlyer. Insira-o exatamente como é exibido no dashboard. Exemplo: id123456789 |
| Método HTTP | `BAIXAR` |
| Tipo de conteúdo da resposta | `text/plain` |
| Autorização | O cabeçalho HTTP `Authorization` que contém o token da API V2 (token Bearer) é obrigatório.<br /><br />![AppsFlyerAdmin_us-en.png](https://files.readme.io/d67fdedd94c56e8da776e590b12883503f47d36f0d58b996c4c64cc5d0e9c675-16281491712785.png)Um usuário administrador <Anchor target="_blank" href="/marketers/pt/docs/managing-appsflyer-tokens">obtém o token V2 no dashboard,</Anchor> from a barra superior, abra o menu da conta (lista suspensa do endereço de e-mail) > **Security Center** > **AppsFlyer API and S2S tokens**. |
| Limitação de taxa | <ul><li>As consultas retornam até 50 mil linhas</li><li>10 chamadas por minuto</li></ul> |
| Data da última  alteração de configuração | <ul><li>No modo de decodificação, a data é exibida no nome do arquivo.</li><li>Em todos os outros modos, a data é exibida na coluna last\_config\_change.</li></ul> |

<div id="request-example-curl" />

### Exemplo de solicitação (cURL)

```shell
curl --request \ GET 'https://hq1.appsflyer.com/api/skan-pull-cs-api/v1/conversion-studio-schema/app/<app_id>' \
--header 'Authorization: Bearer <V2_AUTH_TOKEN_HERE (700+ characters string)>'
```

</Accordion>

<div id="report-name" />

<Accordion title="Nome do Relatório">

A API retorna um arquivo CSV com o seguinte padrão de nomenclatura:

No modo de decodificação: `conversion_value_mapping_<data da última alteração na configuração do esquema>`

Em todos os outros modos: `conversion_schema_report_custom_encode`

</Accordion>

<div id="traits-and-limitations" />

<Accordion title="Especificações e limitações">

| Caraterística | Observações |
| --- | --- |
| Acesso à rede de anúncios | Se você for um parceiro de análise, peça permissão ao anunciante. |
| Acesso à agência | Disponível |
| Acesso do utilizador à conta | O token de autorização está disponível para um utilizador administrador no painel de controlo. |

</Accordion>

<div id="http-response-codes-and-troubleshooting" />

<Accordion title="Códigos de resposta HTTP e solução de problemas">

| HTTP | Tempo de | Considerações |
| --- | --- | --- |
| 200 | OK | Dados válidos retornados (CSV) |
| 400 | Erro na solicitação | Solicitação inválida |
| 401 | Não autorizado | O token de autorização está ausente ou é inválido<br /><br />Certifique-se de usar o token corretamente |
| 401 | Pedidos em excesso | Limite de taxa excedido |
| 403 | Sem permissão | Você não tem permissão para ter acesso a este relatório. Se você for um parceiro de análise, peça ao anunciante que conceda permissão a você. |
| 404 | Não encontrado | <ul><li>Resolva quaisquer problemas relacionados à network ou ao firewall.</li><li>Certifique-se de que os <Anchor target="_blank" href="/marketers/pt/docs/appsflyer-server-ip-address-ranges-allowlisting">endereços IP da AppsFlyer estejam na lista de permissões</Anchor></li></ul> |

</Accordion>

<div data-zendesk-anchors="skan-conversion-value-schema-api=api-do-esquema-de-valor-de-convers%C3%A3o-da-skan h_01HKW1B4XQH2JCJ3T0M1D6W7EM=api-do-esquema-de-valor-de-convers%C3%A3o-da-skan h_01HKW1B4XQCZPQBQFADGNTZDC3=api-basics request-example-curl=exemplo-de-solicita%C3%A7%C3%A3o-curl h_01HKW1B4XQXQW0Z0G8ZF9EE8AZ=exemplo-de-solicita%C3%A7%C3%A3o-curl h_01HKW1B4XQ6ZD45YPHKHDHAZX0=report-name h_01HKW1B4XQVFNM33WV73BA5QXG=traits-and-limitations h_01HKW1B4XQY0V30B4BYCRF9HP5=http-response-codes-and-troubleshooting" />
