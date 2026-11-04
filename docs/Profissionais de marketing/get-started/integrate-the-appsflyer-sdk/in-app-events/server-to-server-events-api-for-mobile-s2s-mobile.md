---
title: API de eventos de servidor para servidor (S2S mobile) para mobile
metadata:
  keywords:
    - iOS
    - Android
    - API
    - In-App
    - S2S
    - HTTP API
    - appsflyer_id
    - Developers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-guy-sarfatty
    - Marketers
    - Mobile Attribution
  created_at: '2014-05-21T17:47:21Z'
  edited_at: '2026-08-19T00:14:02Z'
  id: 207034486
  locale: pt
  section: In-app events
  section_id: 6551285343761
  url: https://support.appsflyer.com/hc/pt/articles/207034486
---
> **At a glance:** **Resumo:** envie eventos de seus servidores para a AppsFlyer para mensurar eventos mobile que ocorrem fora do aplicativo.

![S2S_us-en.png](https://files.readme.io/2f228a03ca00df529e42bd033825a0dca595e99a537cadcfd5419754a29b5490-35863179575441.png)

<div id="server-to-server-events-api-for-mobile" />

## API de eventos de servidor para servidor para mobile

Para aplicativos do iOS, a partir do iOS 14, você deve enviar o parâmetro do sistema operacional.

A plataforma da AppsFlyer atribui e grava eventos de aplicativos mobile pelo SDK da AppsFlyer e pelas APIs. Use a API S2S para reportar eventos que ocorrem fora do aplicativo. Por exemplo, um usuário renova a assinatura usando sua interface da web. Eventos S2S, uma vez gravados, estão disponíveis em toda a plataforma, incluindo dashboards, dados brutos e analytics. Para eventos PBA web, veja <Anchor target="_blank" href="/marketers/pt/docs/web-server-to-server-events-api-for-pba-web-s2s">Web S2S para PBA.</Anchor>

A AppsFlyer preenche eventos S2S com:

* Valores enviados na mensagem S2S
* Alguns valores de atribuição da instalação da AppsFlyer, como hora de instalação e fonte de mídia

Para enviar eventos via API, diga ao seu desenvolvedor para seguir as <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/s2s-events-api3-post">instruções da API de eventos de servidor para servidor</Anchor>.

<div id="populating-parameters" />

## Preenchimento de parâmetros

<div id="difference-between-organic-and-nonorganic" />

<Accordion title="Diferença entre orgânico e não orgânico">

Quando a AppsFlyer processa eventos in-app S2S, os campos de atribuição são preenchidos usando o AppsFlyer ID para identificar o evento de instalação anterior aos eventos in-app.

Isso significa que alguns dados que a AppsFlyer associa a eventos in-app S2S não orgânicos não estão associados a eventos in-app S2S orgânicos.

> 📘 **Note**
>
> **Exemplo**
>
> Por exemplo, se você comparar relatórios de dados brutos de eventos in-app S2S não orgânicos e orgânicos, os eventos não orgânicos contêm dados que os eventos in-app não orgânicos não contêm.
>
> Eventos in-app não orgânicos incluem dados sobre a fonte de mídia, campanha, tipo de toque atribuído e hora do toque atribuído.
>
> Eventos in-app orgânicos, por outro lado, seguem uma instalação orgânica. Instalações orgânicas não possuem dados relacionados a campanhas, fonte de mídia, tipo do toque atribuído e hora de instalação.

</Accordion>

<div id="mapping-appsflyer-id-with-customer-user-id-cuid" />

<Accordion title="Mapeamento do AppsFlyer ID com customer user ID (CUID)">

A lógica do backend é necessária para obter os valores e preencher o parâmetro. Veja a seguir como você pode obter o AppsFlyer ID:

* O AppsFlyer ID é obrigatório e é usado para atribuir eventos.
* Ele é gerado quando um usuário instala o aplicativo mobile pela primeira vez.
* Para mapear o seu CUID com AppsFlyer ID, você deve definir o CUID no aplicativo.

Para que seja mais fácil saber qual usuário executou qual evento, implemente o fluxo abaixo:

* <Anchor target="_blank" href="/marketers/pt/docs/customer-user-id-field-cuid">Defina o customer user ID</Anchor> quando o usuário instalar o aplicativo.
* Os relatórios de dados brutos da AppsFlyer contêm o CUID e o AppsFlyer ID. Use uma das ferramentas de entrega de dados para obter essa informação ou use a Push API da AppsFlyer.
* Use os relatórios de dados brutos para combinar o CUID com o AppsFlyer ID.
* O AppsFlyer ID está disponível no SDK integrado ao seu aplicativo (Android/iOS).
* Mapeie o AppsFlyer ID para o customer user ID em seus sistemas internos (importante para uso futuro).

Depois de mapear o ID da AppsFlyer com o seu CUID, você pode associar o usuário aos eventos realizados. Você pode obter os outros valores (valor do evento, moeda do evento, horário do evento etc.) e enviar o evento in-app de servidor para servidor.

</Accordion>

<div id="fetching-the-appsflyer-id" />

<Accordion title="Como acessar o AppsFlyer ID">

`appsflyer_id` é um parâmetro obrigatório em mensagens de eventos de servidor para servidor. A AppsFlyer usa esse parâmetro para atribuir o evento ao dispositivo original e à fonte de mídia atribuída. Você pode obter o ID usando um dos seguintes métodos:

* No dispositivo mobile, chame a AppsFlyer SDK API:

  <Tabs>
  <Tab title="Iniciando o SDK no Android native">

  <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/android-sdk-reference-appsflyerlib#getappsflyeruid">getAppsFlyerUID</Anchor>

  </Tab>

  <Tab title="Android nativo iOS nativo Unity React nativo">

  <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/ios-sdk-reference-appsflyerlib#getappsflyeruid">getAppsFlyerUID</Anchor>

  </Tab>

  <Tab title="Unity">

  <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/api#getappsflyerid">getAppsFlyerId</Anchor>

  </Tab>

  <Tab title="CONTEXTO">

  <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/rn_api#getappsflyeruid">getAppsFlyerUID</Anchor>

  </Tab>
  </Tabs>

* Na plataforma AppsFlyer, usando uma dessas opções: <Anchor target="_blank" href="/marketers/pt/docs/pull-api-raw-data?query=pull">Pull API,</Anchor> <Anchor target="_blank" href="/marketers/pt/docs/push-api-streaming-raw-data">Push API,</Anchor> Export <Anchor target="_blank" href="/marketers/pt/docs/raw-data-reporting-overview">raw data installation.</Anchor>

</Accordion>

<div id="time-stamping-s2s-events" />

<Accordion title="Eventos S2S com stamping de data e hora">

![time stamping logic diagram](https://files.readme.io/2d9138cc505b0ab1bb106c00fb2d71bd1d070ee236d7f928c8b8b85afe14af59-35863166628497.png)

Quando os eventos S2S chegam em massa à AppsFlyer, eles recebem um timestamp de data/hora com base nos seus valores da propriedade `eventTime` e na hora de chegada. A propriedade `eventTime` indica o momento em que o evento ocorreu no aplicativo.

Na chegada, os eventos são marcados com a hora da seguinte forma:

* Se o parâmetro `eventTime` não estiver incluído no registro do evento, a data/hora do evento será definida como a hora de chegada da mensagem HTTP.
* Eventos que chegam antes das 02:00 UTC recebem o timestamp com o valor `eventTime`. Ou seja, para que os eventos sejam marcados com `eventTime`, eles devem ser reportados no próprio dia do evento ou no dia seguinte até às 02:00 UTC.
* Eventos que ocorreram no dia anterior ou antes, e chegam após 02:00 UTC, são carimbados com a hora de chegada (a hora da chamada da API).
* Eventos que chegam com um valor `eventTime` futuro (eventTime > hora de chegada):
  * Se o `eventTime` relatado e a hora de chegada forem o mesmo dia do calendário, o evento é marcado com o valor `eventTime`.
  * Se o `eventTime` relatado for o dia seguinte, o evento é marcado com a hora de chegada.
* Os eventos com valor `eventTime` inválido recebem a marcação com a hora de chegada da mensagem HTTP.

https://files.readme.io/2d9138cc505b0ab1bb106c00fb2d71bd1d070ee236d7f928c8b8b85afe14af59-35863166628497.png

* Um evento é enviado com `eventTime` = Monday 21:00.

| Chegada à AppsFlyer | Timestamp da AppsFlyer | Observação |
| --- | --- | --- |
| Tuesday 01:00 | Segunda-feira 21:00 | Chegou antes do encerramento do dia. O tempo é definido com o valor `eventTime`. |
| Quarta-feira 09:00 | Quarta-feira 09:00 | Chegou após o encerramento do dia. A hora final é a hora de chegada. |

</Accordion>

<div id="sending-negative-revenue" />

<Accordion title="Envio de receita negativa">

Eventos com um valor de receita negativo podem ser enviados. Por exemplo, se uma compra for cancelada. O parâmetro `af_revenue` pode assumir valores negativos para registrar esse tipo de situação.

Se você preencher `af_quantity`, poderá optar por introduzir um valor negativo conforme a lógica do seu sistema. A AppsFlyer não utiliza `af_quantity`.

</Accordion>

<div id="h_01_including-user-agent-and-ip-address-in-s2s-events" />

<Accordion title="Inclusão de User Agent e endereço IP em eventos S2S">

Ao enviar eventos S2S para o endpoint `metaweb_int`, o payload deve incluir os parâmetros `ua` (User Agent) e `ip` (IP address). A Meta exige esses valores para otimizar a performance da campanha por meio da Conversions API (CAPI).

A AppsFlyer inclui `ua` e `ip` automaticamente para eventos reportados por meio do SDK. Para eventos S2S, os anunciantes devem enviar esses parâmetros explicitamente no payload da solicitação.

</Accordion>

> 📘 **Note**
>
> **Atenção**
>
> Para serem mensurados para <Anchor target="_blank" href="/marketers/pt/docs/incrementality-for-remarketing-overview">Incrementalidade</Anchor>, os eventos S2S devem incluir o advertising ID em seu payload (IDFA para iOS, GAID para Android).

<div id="increasing-the-volume-of-data-transactions" />

## Aumentar o volume de transações de dados

Com o escalonamento gradual, a AppsFlyer oferece suporte a um grande volume de transações por segundo (TPS) através de soluções de auto-escalonamento. Por exemplo:

* Comece com 10 mil transações por segundo (TPS) e aumente gradualmente, com base em intervalos mínimos de 1 minuto.
  * 00:00:00 - enviar 10 mil TPS (valor base)
  * 00:01:00 - aumentar para 12 mil TPS
  * 00:02:00 - aumentar para 14 mil TPS
  * 00:03:00 - aumentar para 16 mil TPS
  * 00:04:00 - aumentar para 18 mil TPS
  * …
* Implemente um mecanismo de repetição para quando erros forem identificados.

<div id="troubleshooting" />

## Resolução de problemas

<div id="events-arent-displaying-in-the-dashboard" />

<Accordion title="Eventos não são exibidos no dashboard">

* Endpoint: Verifique se o endpoint utilizado está correto.
* Verifique se o payload contém os parâmetros obrigatórios. Consulte [aqui](/docs/server-to-server-events-api-for-mobile-s2s-mobile#mapping-appsflyer-id-with-customer-user-id-cuid).
* Certifique-se de que o AppsFlyer ID que você está usando para disparar o evento é um appsflyer\_id real e que de fato corresponde a uma instalação do aplicativo. Consulte [aqui](/docs/server-to-server-events-api-for-mobile-s2s-mobile#fetching-the-appsflyer-id).
* Os eventos S2S não oferecem suporte a vários eventos em uma solicitação S2S. Cada evento deve ser enviado separadamente.
  * Os eventos podem ser enviados com método assíncrono para melhorar o tempo de resposta.
* No dashboard de visão geral, o período de datas mostrado está relacionado à data de instalação do aplicativo (LTV) e não à data do evento.
  * Certifique-se de selecionar o período correto.
  * Certifique-se de que o período mostrado no dashboard corresponde à data de instalação no dispositivo (appsflyer\_id) e não à data do evento.
* Relatórios de dados brutos do evento: o período mostrado está relacionado à data do evento e não à data da instalação.

</Accordion>

<div id="events-dont-contain-revenue" />

<Accordion title="Os eventos não contêm receita">

Se você enviar eventos S2S, mas sua receita não for registrada, certifique-se de que o JSON que você enviou está em formato de string. A parte mais importante é o parâmetro do valor do evento no JSON. Ele deve estar em strings, como mostrado no exemplo a seguir.

```json
"{\"af_revenue\":\"6\" ,\"af_content_type\":\"wallets\"}"
```

Se não estiver em formato de strings, o valor do evento não será processado corretamente e a receita não será gravada.

Os valores da receita não devem ser formatados de forma alguma. Eles podem conter um ponto decimal. Não inclua sinais de moeda ou códigos nem delimitadores como `,`. A receita pode ser prefixada por um `-`. `-`

* Exemplos de valores válidos: `123`, `-123.45`, `123.456`.
* Exemplos de valores inválidos: `1,234.56`, `1,234`.

</Accordion>

<div id="not-all-fields-are-populated-in-s2s-events" />

<Accordion title="Nem todos os campos são preenchidos nos eventos S2S">

Os campos de dados brutos são preenchidos exclusivamente com os valores enviados na chamada S2S (ao contrário dos campos de postback, que podem ser preenchidos com valores do evento de instalação). Os seguintes campos não podem ser reportados através da S2S API e, portanto, não são preenchidos para eventos S2S em relatórios de dados brutos:

* WiFi
* Operador
* Idioma
* Modelo do dispositivo
* Categoria do dispositivo
* Versão do aplicativo: você pode usar `app_version_name`.
* Nome do aplicativo

</Accordion>

<div id="S2S_in-app_events_are_wrongly_attributed_as_organic" />

<Accordion title="Eventos in-app S2S são incorretamente atribuídos como orgânicos.">

Os eventos S2S, como os de início de sessão, podem chegar à AppsFlyer logo que o aplicativo é instalado e o é SDK iniciado. No entanto, se esses eventos chegarem antes da AppsFlyer concluir o processamento do evento de instalação, que geralmente demora 20 a 30 segundos ou mais, eles podem ser marcados como eventos orgânicos não atribuídos.

Recomendamos um pequeno atraso antes de reportar aos nossos servidores eventos in-app S2S que ocorrem imediatamente após a instalação.

</Accordion>

<div data-zendesk-anchors="servertoserver-events-api-for-mobile=api-de-eventos-de-servidor-para-servidor-para-mobile h_01H9Q8KBYGXAA8H4AKKXP8T8DY=api-de-eventos-de-servidor-para-servidor-para-mobile populating-parameters=preenchimento-de-par%C3%A2metros h_01H9Q8KBYGHY1SDSMSFZRT2JXZ=preenchimento-de-par%C3%A2metros h_01H9Q8KBYG6W4TERWHARZZZASZ=difference-between-organic-and-nonorganic h_01H9Q8KBYG6EBKPS5Y2KC1QT7G=mapping-appsflyer-id-with-customer-user-id-cuid h_01H9Q8KBYGR26VMQR9Y0CK85F6=fetching-the-appsflyer-id h_01H9Q8KBYG8ASB1WB9X4XM3CYZ=time-stamping-s2s-events h_01H9Q8KBYG63SZWNM4GWSJG605=sending-negative-revenue including-user-agent-and-ip-address-in-s2s-events=h_01_including-user-agent-and-ip-address-in-s2s-events increasing-the-volume-of-data-transactions=aumentar-o-volume-de-transa%C3%A7%C3%B5es-de-dados h_01HX77GDZ1CCWN48CN616P860D=aumentar-o-volume-de-transa%C3%A7%C3%B5es-de-dados troubleshooting=resolu%C3%A7%C3%A3o-de-problemas h_01H9Q8KBYGYR9Y7DPCNWSB4QY0=resolu%C3%A7%C3%A3o-de-problemas h_01H9Q8KBYGYHCWAPPNMG9WB8QN=events-arent-displaying-in-the-dashboard h_01H9Q8KBYGDC68637RH4DE2FZX=events-dont-contain-revenue h_01H9Q8KBYGDQKZF90EJAXRTMF3=not-all-fields-are-populated-in-s2s-events h_01JWV0CS5BFBXDT333794BHFER=S2S_in-app_events_are_wrongly_attributed_as_organic" />
