---
title: '[Beta fechada] API de Regras de Validação'
metadata:
  keywords:
    - Marketers
    - Closed beta
    - Protect360
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-yanai
    - Marketers
    - Protect360
  created_at: '2026-07-02T09:03:27Z'
  edited_at: '2026-09-28T00:03:24Z'
  id: 48341412127249
  locale: pt
  section: Protect your traffic
  section_id: 6551015912465
  url: https://support.appsflyer.com/hc/pt/articles/48341412127249
---
<span class="af-tag af-tag--closed-beta">Closed beta</span>

> **At a glance:** Automatize a criação e a gestão de regras de validação em escala. A API de Regras de Validação permite que equipes técnicas criem, atualizem, apliquem patches e excluam regras de forma programática, indo além dos limites de valores da UI e eliminando a sobrecarga do gerenciamento manual de regras.

<div id="note" />

> 📘 **Atenção**
>
> A API de Regras de Validação está disponível para clientes do Protect360. No momento, ela está em beta fechada, e o acesso é limitado e habilitado por conta. Entre em contato com seu Customer Success Manager (CSM) para solicitar acesso.

<div id="about-the-validation-rules-api" />

## Sobre a API de Regras de Validação

Até agora, as Regras de Validação só podiam ser gerenciadas pela UI da AppsFlyer. Isso gerava duas limitações:

* Um limite de aproximadamente 17.000 valores por regra. Não é suficiente para listas de bloqueio em escala empresarial.
* Toda atualização exigia trabalho manual na UI. Isso consome tempo e gera altos custos operacionais para equipes que fazem alterações frequentes.

A API de Regras de Validação remove essas duas limitações. Ela dá às equipes técnicas controle programático total sobre suas regras, oferece suporte a até 300.000 valores por regra em regras grandes e permite automatizar atualizações de alta frequência sem precisar mexer na UI.

As regras criadas via API são sinalizadas como gerenciadas por API e aparecem como somente leitura na UI da AppsFlyer. As regras existentes criadas na UI não são afetadas. As regras gerenciadas pela UI e pela API coexistem na mesma conta.

<Accordion title="Isso é para você?">

A API de regras de validação foi criada para casos de uso específicos. Ela não foi criada para substituir a UI para todos os clientes. Considere a API se:

* Você gerencia uma blocklist ou allowlist que excede, ou está se aproximando, do limite de ~17.000 valores da UI.
* Sua equipe quer integrar o gerenciamento de regras aos seus próprios sistemas, scripts ou pipelines de automação.
* Sua lógica de fraude ou de bloqueio de tráfego muda com frequência, e as atualizações manuais na UI se tornaram um gargalo.

Se você gerencia um pequeno número de regras que raramente mudam, a IU de Regras de validação continua sendo a maneira mais simples de gerenciá-las.

</Accordion>

<Accordion title="Acesso e elegibilidade">

A API de Regras de validação está disponível para clientes do Protect360. No momento, ela está em beta fechado, e o acesso é habilitado por conta.

* Requer uma assinatura do Protect360.
* Controlado por uma flag de recurso. Entre em contato com seu Customer Success Manager (CSM) para solicitar acesso e ativação.
* Regras grandes (até 300.000 valores) exigem habilitação especial adicional além do acesso padrão à API. Entre em contato com seu CSM para ativá-las.

</Accordion>

<div id="how-it-works" />

## Como funciona

<Accordion title="Autenticar">

A API usa autenticação por token Bearer (JWT).

1. Na sua conta da AppsFlyer, acesse **Security Center** > **API tokens**.
2. Gere um token.
3. Inclua o token no cabeçalho **Authorization** das suas solicitações de API.

<div id="note-1" />

> 📘 **Atenção**
>
> O acesso à API deve ser habilitado por conta antes que um token funcione. Entre em contato com seu CSM para ativá-lo.

</Accordion>

<Accordion title="O que você pode fazer">

| Action | Descrição |
| --- | --- |
| Listar regras | Recupere todas as regras ativas (habilitadas e desabilitadas) da sua conta. |
| Criar regra | Crie uma nova regra de forma programática. |
| Recuperar uma regra | Obtenha os detalhes completos da regra, incluindo todas as condições. |
| Atualizar regra | Substitua uma regra existente por uma nova configuração. |
| Habilitar/desabilitar uma regra | Ative ou desative uma regra sem excluí-la. |
| Excluir regra | Remova uma regra de forma permanente. |
| Aplicar patch em uma regra | Adicione, remova ou substitua valores de uma única dimensão sem reescrever a regra inteira. |

O endpoint de patch é especialmente útil para atualizações de alta frequência. Você atualiza apenas o que mudou, não a regra inteira. Isso funciona bem para fluxos de trabalho, como atualizações diárias de listas de bloqueio de fontes de fraude.

</Accordion>

<div id="scope-and-supported-configurations" />

## Escopo e configurações compatíveis

Atualmente, a API de Regras de Validação oferece suporte a um subconjunto definido do que está disponível no construtor de regras da UI.

* Aplica-se apenas a eventos de instalação. Eventos in-app não são compatíveis nesta versão.
* Dimensões compatíveis:
  * Fonte de tráfego (população): ID do site, canal de mídia, agência, campanha, ID da campanha, ID do conjunto de anúncios e ID do anúncio
  * Condições: Geolocalização, Plataforma
* Operadores com suporte: Está na lista, Não está na lista.
* Lógica entre dimensões: apenas AND. OR não é suportado.
* Tipos de regra: Correspondência (bloquear tráfego correspondente) ou Sem correspondência (bloquear tráfego que não corresponde).
* Tipos de fonte: todo o tráfego, todo o tráfego não orgânico ou tráfego não orgânico de uma agência específica.
* Ações de bloqueio com suporte:
  * Bloquear atribuição e corrigi-la para o último canal de mídia válido.
  * Bloquear atribuição e marcar instalações como inválidas. Elas não aparecerão no dashboard do Protect360.

<Accordion title="Tamanho e limites da regra">

|  | Regra padrão | Regra grande |
| --- | --- | --- |
| Total de valores em todas as condições | Até 17,000 | Até 300,000 |
| Requer habilitação especial | Yes | Yes |
| Máx. de regras por conta | 100 | Até 5 |

Limites adicionais:

* de 2.000 IDs de aplicativo por regra.
* 2 MB por chamada de API. Solicitações que excederem isso (aproximadamente 50.000 valores) devem ser divididas em várias chamadas.
* 300.000 valores por regra grande, em todas as dimensões combinadas, independentemente do tipo de operação (criar, atualizar ou aplicar patch).

Exceder qualquer limite retorna um erro que identifica qual limite foi ultrapassado.

</Accordion>

<Accordion title="Acesso a dados de tráfego bloqueado">

O tráfego bloqueado por regras gerenciadas por API é relatado da mesma forma que o tráfego bloqueado por regras criadas na IU.

| Relatório | Localização |
| --- | --- |
| Exportação de dados brutos | Protect360 & Regras de validação > Instalações |
| Relatório do Data Locker | Relatórios do Protect360 > relatório blocked\_installs |
| Extrair API | Exportação de dados brutos |

</Accordion>

<Accordion title="Documentação técnica">

Para ver todos os detalhes técnicos, incluindo referências de endpoints, esquemas de solicitação e resposta e códigos de erro, consulte a <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/updaterule">referência da API de regras de validação</Anchor>.

</Accordion>

<Accordion title="Especificações e limitações">

| Caraterística | A descrição |
| --- | --- |
| Suporte a eventos | Somente eventos de instalação. Eventos in-app não são compatíveis nesta versão. |
| Lógica | Somente a lógica AND é suportada entre dimensões. OR não é suportado. |
| Interação na IU | As regras criadas pela API aparecem como somente leitura na IU. Edite-as usando a API. |
| Tamanho da chamada | 2MB por chamada à API (aproximadamente 50,000 valores). Atualizações maiores devem ser divididas em várias chamadas. |

</Accordion>

<div id="faq" />

## Perguntas frequentes

<Accordion title="Quem pode usar a API de regras de validação?">

A API de regras de validação está disponível para clientes do Protect360. No momento, está em beta fechado, e o acesso é habilitado por conta. Fale com seu CSM para solicitar o acesso.

</Accordion>

<Accordion title="As regras gerenciadas pela API aparecem na interface?">

sim, sim, As regras criadas via API ficam visíveis na interface do AppsFlyer, mas são sinalizadas como gerenciadas pela API e aparecem como somente leitura.

</Accordion>

<Accordion title="Posso gerenciar algumas regras pela API e outras pela interface?">

sim, sim, Regras gerenciadas pela API e regras criadas na interface coexistem na mesma conta. As regras gerenciadas pela API aparecem como somente leitura na interface. As regras criadas na interface não são acessíveis via API.

</Accordion>

<Accordion title="Posso editar uma regra gerenciada pela API na interface?">

Não, a regra aparece como somente leitura. Você deve usar a API para atualizá-la.

</Accordion>

<Accordion title="Qual é a diferença entre Update e Patch?">

Update substitui a regra inteira. Patch atualiza apenas uma única dimensão, adicionando, removendo ou substituindo valores sem reescrever a regra inteira. Use Patch para atualizações frequentes e direcionadas.

</Accordion>

<Accordion title="O que acontece se eu exceder um limite?">

A API retorna um erro informando qual limite foi violado. Divida atualizações grandes em várias chamadas à API para ficar dentro do limite de 2 MB por chamada.

</Accordion>

<Accordion title="Quantas regras posso ter?">

Até 100 regras padrão por conta e até 5 regras grandes por conta. Tanto as regras padrão quanto as grandes exigem uma habilitação especial. Entre em contato com seu CSM para ativá-las.

</Accordion>

<Accordion title="A lógica OU tem suporte?">

Sem. Apenas a lógica E tem suporte entre dimensões.

</Accordion>

<Accordion title="Quais tipos de evento têm suporte?">

Somente eventos de instalação. Eventos in-app não são compatíveis com esta versão.

</Accordion>

<div id="see-also" />

> 📄 **Consulte também**
>
> * Implemente regras de validação para evitar fraudes

<div data-zendesk-anchors="h_01KWH1NW583T8SPZFF5REMQC6V=aten%C3%A7%C3%A3o about-the-validation-rules-api=sobre-a-api-de-regras-de-valida%C3%A7%C3%A3o h_01KWH1NW58A3YK7FKR1C4WBRF3=sobre-a-api-de-regras-de-valida%C3%A7%C3%A3o how-it-works=como-funciona h_01KWH1NW58P5AB47847E99YG6G=como-funciona h_01KWH1NW594YT5S9FT8VWX77SG=aten%C3%A7%C3%A3o-1 scope-and-supported-configurations=escopo-e-configura%C3%A7%C3%B5es-compat%C3%ADveis h_01KWH1NW594XM03VQKNJPY37B7=escopo-e-configura%C3%A7%C3%B5es-compat%C3%ADveis faq=perguntas-frequentes h_01KWH1NW59J9QHP37KMMK18JBG=perguntas-frequentes h_01KWH1NW59G3WG3KHVRGY9TMV4=consulte-tamb%C3%A9m" />
