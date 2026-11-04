---
title: Estúdio de conversão SKAN
metadata:
  keywords:
    - Advertisers
    - Marketers
    - SKAdNetwork (SKAN)
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - SKAdNetwork (SKAN)
  created_at: '2021-07-08T09:26:58Z'
  edited_at: '2026-08-19T00:31:00Z'
  id: 4403727223185
  locale: pt
  section: SKAN solution
  section_id: 6552135379985
  url: https://support.appsflyer.com/hc/pt/articles/4403727223185
---
> **Visão Geral**: Utilize o SKAN Conversion Studio para definir quais interações dos utilizadores na aplicação serão medidas e por quanto tempo. Mede receitas, conversões, envolvimento e retenção durante um período pós-instalação específico. Ao integrar a medição de Fonte Única da Verdade, conseguimos informá-lo se o utilizador foi atribuído tanto pela AppsFlyer como pela SKAN.

<Embed title="SKAN 4 Conversion Studio (incluindo janela de bloqueio)" typeOfEmbed="iframe" url="https://player.vimeo.com/video/810457121?h=a3acc3ee41&amp;badge=0&amp;autopause=0&amp;player_id=0&amp;app_id=58479" providerUrl="https://player.vimeo.com" />

<div id="skan-conversion-studio-basics" />

## Conceitos básicos do SKAN Conversion Studio

No fluxo de atribuição do SKAdNetwork (SKAN), um dispositivo iOS envia postbacks SKAN com os valores de conversão (CV) mais recentes após cada janela de medição.

Para o SKAN 3 e anteriores, há 1 postback que chega após o fim da janela de atividade inicial. A janela de atividade pode variar entre 12 horas e 63 dias. O CV é limitado a 6 bits, resultando em 64 valores possíveis (0-63).

Para o SKAN 4, existem 3 postbacks que chegam após o final de cada uma das 3 janelas, ocorrendo nos dias 2, 7 e 35, respetivamente. Para:

* Na janela 1, o CV detalhado está limitado a 6 bits, resultando em 64 valores possíveis (0-63).
* Nas janelas 1-3, o CV geral está limitado a um CV de nível baixo, médio ou alto. (As janelas 2 e 3 não possuem CV detalhados).

Estas limitações de CV significam que pode ter de tomar decisões importantes sobre como utilizar os 64 valores possíveis para CVs detalhados e os 3 valores possíveis para CVs gerais.

O Conversion Studio oferece-lhe máxima flexibilidade para garantir que todos os valores e bits possíveis sejam utilizados eficazmente. Decide com precisão quais os dados de medição a serem codificados no CV, incluindo quais atividades medir e por quanto tempo durante o período pós-instalação. Existem vários modos de medição que pode usar para configurar as definições do seu CV.

| Tipo | Modo de medição | Descrição | Janela de Atividade |
| --- | --- | --- | --- |
| Flexível | [SKAN 4.0](/docs/skan-conversion-studio#skan-4)<br /><br />[Melhor prática]<br /><br />[Predefinição] | Defina uma combinação de métricas de receita, conversão (eventos na aplicação) e envolvimento durante três janelas de medição configuráveis.<br /><br />As três janelas medem períodos distintos de tempo pós-instalação, sem sobreposição. Ou seja, a janela 2 abrange os dias 3 a 7 após a instalação, e não os dias 0 a 7. | <ul><li>Janela 1: 1-2 dias</li><li>Janela 2: 3-7 dias</li><li>Janela 3: 8-35 dias</li></ul> |
| Flexível | Personalizado | Defina uma combinação de métricas de receita, conversão (eventos na aplicação) e envolvimento em uma janela de atividade configurável. | 12-1512h (o padrão é até 72 horas, mas pode ser estendido) |
| Fixado* | Resultados<br /><br />[Legado] | Meça a receita utilizando uma das seguintes faixas:<ul><li>1 a 630 USD em incrementos de 10 USD</li><li>1 a 63 USD em incrementos de 1 USD</li><li>0,01 a 0,63 USD em incrementos de 0,01 USD</li></ul> | 24 h |
| Fixado* | Conversão<br /><br />[Legado] | Selecione 1 a 6 eventos na aplicação. | 24 h |
| Fixado* | com o anúncios<br /><br />[Legado] | Número de vezes que um utilizador realiza um evento | 24 h |
| Flexível | <Anchor target="_blank" href="/marketers/pt/docs/skan-cv-decode-map-your-cv-to-events">Decode</Anchor> | <ul><li>Crie o seu próprio mapeamento de eventos para CV e configure o CV na aplicação você mesmo. Use esta opção se não conseguir integrar o SDK da AppsFlyer na sua aplicação. Para utilizar o Decode, aceda a **SKAN Conversion Studio,** clique em opções (⋮) e selecione **Carregar ficheiro de mapeamento personalizado de descodificação**.</li></ul> | 12-15:12h (63 dias) |

*Os modos fixos não estarão disponíveis para novas aplicações a partir de 23/06/2024.  Todas as funcionalidades são suportadas nos modos Custom e SKAN4.

**Dica!** Experimente o Conversion Studio. Na AppsFlyer, vá a > **Definições** > **SKAN Conversion Studio**.

<div id="measurement-principles-and-definitions" />

<Accordion title="Princípios e definições de medição">

**Definições**

* **Janela de medição SKAN**: Relevante para SKAN 4+. Existem três períodos durante os quais a atividade pós-instalação do utilizador é medida:
  * Janela 1: 1-2 dias
  * Janela 2: 3-7 dias
  * Janela 3: 8-35 dias
  * As três janelas medem períodos distintos de tempo pós-instalação, sem sobreposição. Ou seja, a janela 2 abrange os dias 3 a 7 após a instalação, e não os dias 0 a 7.
* **Janela de Atividades:** Relevante para SKAN 3 e versões anteriores. Tem uma duração definida, normalmente de 24 horas, a partir da primeira vez que a aplicação é aberta. Se usar SKAN 4+, mas os dispositivos do utilizador ou redes de anúncios ainda não suportarem SKAN 4, a janela de atividade é de 48 horas.
* **Valor de Conversão (CV)**: A avaliação da qualidade do utilizador reportada nos postbacks enviados pelo iOS, ao final das janelas do SKAN 4 ou, para o SKAN 3 e anteriores, ao final da janela de atividades. O SDK da AppsFlyer define os valores de conversão (CVs) por si. Entretanto, se desejar configurar o CV, use <Anchor target="_blank" href="/marketers/pt/docs/skan-cv-decode-map-your-cv-to-events">Decode</Anchor> para fazer o upload do ficheiro de mapeamento do CV.
  * Para o SKAN 4+, existem valores de conversão precisos e gerais.
* **Capacidade de valores de conversão:** O número de CVs necessários para mapear a sua configuração. Quanto mais componentes e elementos de medição selecionar, maior será a capacidade de valores de conversão necessária. Cada intervalo ou elemento de configuração selecionado consome capacidade de valores de conversão. (E cada unidade de configuração adicional incluída num único componente consome-a exponencialmente!) [Exemplos de uso maximizado do CV.](/docs/skan-conversion-studio#maximized-custom-cv-examples)
* Fonte Única da Verdade (SSOT): <Anchor target="_blank" href="/marketers/pt/docs/single-source-of-truth-ssot-guide-for-ios-attribution">Mecanismo para identificar</Anchor> se o utilizador foi atribuído pelo SKAN e por outro método de correspondência de atribuição. A identificação é utilizada para eliminar dados duplicados de instalação nos dados brutos do SKAN e para calcular métricas de desempenho reais.
* **Componentes de medição:**  
  * **Receita:** Mede a receita gerada.
  * **Evento na aplicação:** Mede a conversão (número de utilizadores únicos que realizam um evento),  
    engajamento (número de vezes que um evento foi realizado), ou ambos.
  * **Funil:** Mede a ocorrência de eventos na aplicação com base numa lista de eventos sequenciais num funil. Quando um utilizador realiza qualquer evento no funil, considera-se que realizou todos os eventos anteriores a esse.
  * **Prioridade:** Um componente que pode incluir receita, evento na aplicação ou ambos.

**Princípios**

* **![Admin.png](https://files.readme.io/d67fdedd94c56e8da776e590b12883503f47d36f0d58b996c4c64cc5d0e9c675-16281491712785.png) Apenas Administradores:** Somente um administrador pode guardar as definições do Conversion Studio. Os utilizadores da conta podem visualizar as definições.
* Apenas um modo está ativo em qualquer momento.
* Para um determinado modo, a AppsFlyer mapeia as combinações definidas pelas suas definições para CVs. Pode [visualizar e descarregar a tabela de mapeamento](/docs/skan-conversion-studio#view-cv-mapping).
* Na aplicação, a AppsFlyer configura o CV após cada ação mensurável do utilizador, utilizando o modo de medição ativo quando a aplicação é iniciada pela primeira vez.
* O iOS leva em conta o <Anchor target="_blank" href="https://developer.apple.com/documentation/storekit/skadnetwork/receiving_postbacks_in_multiple_conversion_windows">anonimato da multidão da Apple</Anchor> antes de preencher o CV no postback.
* As ações do utilizador que ocorrem após o final de uma janela são ignoradas.
* Painel e Relatórios SKAN:
  * O layout e as métricas do painel SKAN dependem do modo e da configuração.
  * O layout é atualizado diariamente com base no modo ativo à meia-noite UTC. O layout atualizado deve estar disponível por volta das 05:00 UTC.
  * No SKAN 4, Custom e Decode, os dados orgânicos para eventos na aplicação e a receita geral não estão disponíveis.

<div id="s2s-principles" />

#### **Princípios S2S**

As ações mensuráveis podem ser relatadas pela API de [servidor para servidor (S2S)](/docs/skan-conversion-studio#report-events-by-servertoserver-api). Considere o seguinte por modo:

* SKAN 4 e Personalizado: O S2S está sempre ativado.
* Descodificação: O S2S não é adequado para o modo de descodificação e não está disponível. A AppsFlyer não define o CV neste modo.
* [Legado] Modos de receita, conversão e engajamento: Necessita ativar a [gravação de eventos S2S](/docs/skan-conversion-studio#report-events-by-servertoserver-api) antes de enviar eventos.

</Accordion>

<div id="setting-up-conversion-values-in-skan-conversion-studio" />

## Configuração de valores de conversão no SKAN Conversion Studio

Existem vários modos disponíveis no SKAN Conversion Studio para definir os valores de conversão:

* SKAN 4: Utilize diferentes componentes de medição, como receita, eventos na aplicação, prioridade e Fonte Única da Verdade, para determinar o que é medido em cada uma das três janelas de medição.
* Personalizado: Utilize diversos componentes de medição como receita, eventos na aplicação, prioridade e Fonte Única da Verdade para determinar o que é medido durante a janela de atividades.
* [Legado] Modos fixos: Meça o valor do utilizador usando uma das seguintes medições:
  * Resultados
  * Conversão
  * com o anúncios

Saiba mais sobre os diferentes modos de medição nas secções seguintes.

<div id="important" />

> 🚧 **Importante!**
>
> A configuração dos valores de conversão no SKAN Conversion Studio deve ser realizada por um administrador ou utilizador da conta com permissões de **Gerir** no **SKAN Conversion Studio**.
>
> **Para visualizar ou alterar as permissões de utilizador:**
>
> 1. Na AppsFlyer, no canto superior direito, clique no seu endereço de e-mail.
> 2. Selecione **Gestão de Utilizadores** > Selecione o utilizador.
> 3. Se necessário, conceda ao utilizador permissões para **Gerir** no **SKAN Conversion Studio**. Para mais informações sobre permissões, consulte <Anchor target="_blank" href="/marketers/pt/docs/user-management">Gestão de Utilizadores</Anchor>.
>
> *Observação: usuários cujo acesso é limitado a canais de mídia e geolocalizações específicas talvez não consigam ver nem acessar o SKAN Conversion Studio.

<div id="skan-4" />

<Accordion title="SKAN 4">

No SKAN 4, utiliza diferentes componentes de medição, como receita, eventos in-app, prioridade, e Fonte Única de Verdade, para determinar o que é medido em cada uma das três janelas de medição. Juntos, os componentes formam o seu modo de medição SKAN 4.

Se estiver a atualizar para o SKAN 4 a partir de um modo anterior, o mapeamento do seu esquema atual é transferido para a configuração precisa da janela 1. A AppsFlyer mapeia automaticamente os valores aproximados para si nas janelas 1 a 3.

Para definir manualmente o SKAN 4, experimente diferentes opções. À medida que faz alterações, o resumo da **capacidade do valor de conversão** é atualizado. Otimize as suas configurações para capturar os dados mais relevantes para si sem exceder a capacidade. Veja [Cálculo da Capacidade do Valor de Conversão.](/docs/skan-conversion-studio#conversion-value-capacity-formula)

![CapacitCounter.png](https://files.readme.io/c976bbf52b8348ffa8de092f5f75eb66b137cc9fa63bc34d0b84e50fc7d112f7-4405725161233.png)

**Nota: Se estiver a atualizar para o SKAN 4 de um modo anterior, o seu mapeamento atual será transferido para as medições precisas e a AppsFlyer mapeará automaticamente os valores aproximados para si. E se é novo no SKAN, a AppsFlyer oferece um mapeamento padrão inicial.**

**![AppsFlyerAdmin_us-en.png](https://files.readme.io/d67fdedd94c56e8da776e590b12883503f47d36f0d58b996c4c64cc5d0e9c675-16281491712785.png) altAppsFlyerAdmin\_us-en.pngaltPara definir manualmente os valores de conversão no Conversion Studio usando o modo SKAN 4:**

1. No painel da AppsFlyer, aceda a **Definições** > **SKAN Conversion Studio.**
2. Clique nas opções (⋮) para mostrar o menu de opções e certifique-se de que a **medição SKAN** está ativada. **Nota**! Se estiver desativado, o SDK não chama funções SKAN do iOS, como *registerAppForAdNetworkAttribution*, *updateConversionValue.*
3. Selecione o modo de medição **SKAN 4.0**.
4. Clique em **Continuar**.  
   As configurações para **Janela 1 (1-2 dias) precisa** de CV abrem.
5. [Opcional] Ative a **Fonte Única de Verdade (SSOT)**.  
   O mecanismo SSOT sinaliza (e desduplica) instalações reportadas por mais de um método de correspondência de atribuição. <Anchor target="_blank" href="/marketers/pt/docs/single-source-of-truth-ssot-guide-for-ios-attribution">Saiba mais</Anchor>
6. Clique em **+ Adicionar medição** para adicionar diferentes [componentes de medição](/docs/skan-conversion-studio#componentes-de-medição).  
   As secções seguintes detalham as opções de configuração e os componentes. Utilize-as como guias enquanto experimenta as diferentes definições de medição SKAN:
   * Resultados
   * Evento na app
   * Funil
   * Prioridade
7. Clique em **'Coarse'** e repita os passos 6 a 7 para definir o CV coarse da **Janela 1 (1-2 dias)**.   
   **Nota**:
   * Apenas os componentes de medição de receita e eventos na aplicação estão disponíveis.
   * Para garantir que o postback é enviado, o CV baixo deve corresponder a uma sessão do utilizador.
8. [Opcional] Ative **Bloquear janela** e defina a condição (tempo ou valor de conversão coarse) para bloquear a janela SKAN antes do padrão. [Saiba mais](/docs/skan-conversion-studio#lock-window)
9. Clique em **Janela 2 (3-7 dias)** e repita os passos 6 a 8 para definir o CV da janela 2.   
   **Nota**:
   * Apenas os componentes de medição de receita e eventos na aplicação estão disponíveis.
   * [Recomendado] O CV baixo deve ser uma sessão de utilizador.
10. Clique em **Janela 3 (8-35 dias)** e repita os passos 6 a 8 para definir o CV da janela 3.   
    **Nota**:
    * Apenas os componentes de medição de receita e eventos na aplicação estão disponíveis.
    * [Recomendado] O CV baixo deve ser uma sessão de utilizador.
11. Clique em **Guardar**.
12. Verifique se os mapeamentos de postback de eventos na aplicação do seu parceiro correspondem aos eventos que configurou.

</Accordion>

<div id="custom" />

<Accordion title="Personalizado">

No modo Personalizado, pode utilizar componentes de medição diferentes, como receita, eventos na aplicação, prioridade e Fonte Única da Verdade, para determinar o que é medido e definir uma janela de atividade que determina durante quanto tempo e em que intervalos a medição ocorre. Em conjunto, os componentes formam o seu modo de medição personalizado.

Para configurar o modo Personalizado, experimente diferentes opções. À medida que faz alterações, o resumo da **capacidade do valor de conversão** é atualizado. Otimize as suas configurações para capturar os dados mais relevantes para si sem exceder a capacidade. Veja [Cálculo da Capacidade do Valor de Conversão.](/docs/skan-conversion-studio#conversion-value-capacity-formula)

![CapacitCounter.png](https://files.readme.io/c976bbf52b8348ffa8de092f5f75eb66b137cc9fa63bc34d0b84e50fc7d112f7-4405725161233.png)

Observação: por padrão, a AppsFlyer exibe o SKAN 4 no Conversion Studio. Para reverter para um modo anterior, clique nas opções (⋮) para exibir o menu de opções e selecione Reverter para a versão anterior do SKAN.

**![AppsFlyerAdmin_us-en.png](https://files.readme.io/d67fdedd94c56e8da776e590b12883503f47d36f0d58b996c4c64cc5d0e9c675-16281491712785.png) altAppsFlyerAdmin\_us-en.pngaltPara definir manualmente os valores de conversão no Conversion Studio utilizando o modo Personalizado:**

1. No painel da AppsFlyer, aceda a **Definições** > **SKAN Conversion Studio.**
2. Clique nas opções (⋮) para mostrar o menu de opções e certifique-se de que a **medição SKAN** está ativada. **Nota**! Se estiver desativado, o SDK não chama funções SKAN do iOS, como *registerAppForAdNetworkAttribution*, *updateConversionValue.*
3. Selecione o modo de medição **Personalizado**.
4. Clique em **Continuar**.
5. [Opcional] Ative a **Fonte Única de Verdade (SSOT)**.  
   O mecanismo SSOT sinaliza (e desduplica) instalações reportadas por mais de um método de correspondência de atribuição. <Anchor target="_blank" href="/marketers/pt/docs/single-source-of-truth-ssot-guide-for-ios-attribution">Saiba mais</Anchor>
6. Clique em **+ Adicionar medição** para incluir diferentes componentes de medição.  
   As secções seguintes detalham as opções de configuração e os componentes. Utilize-as como guias enquanto experimenta as diferentes definições de medição SKAN:
   * Resultados
   * Evento na app
   * Funil
   * Prioridade
7. Defina a duração da janela de atividade (12 horas a 63 dias) durante a qual pretende monitorizar a atividade do utilizador.  
   O **Temporizador de atividade** padrão permite definir a janela para 24 a 72 horas. E a configuração padrão de **Intervalo** permite definir 12 ou 24 horas. Utilize a **janela personalizada** para estender a janela de atividade até 63 dias e definir intervalos mais longos.
8. Clique em **Guardar**.
9. Verifique se os mapeamentos de postback de eventos na aplicação do seu parceiro correspondem aos eventos que configurou.

</Accordion>

<div id="fixed-modes" />

<Accordion title="[Legado] Modos fixos">

<div id="note" />

> 📘 **Nota**
>
> Os modos fixos não estarão disponíveis para novas aplicações a partir de 23/06/2024.  Todas as funcionalidades são suportadas nos modos Custom e SKAN4.

Com modos fixos, pode medir o valor do utilizador utilizando uma das seguintes medidas:

* * Resultados
  * Conversão
  * com o anúncios

À medida que faz alterações nas definições do modo, o resumo da **capacidade do valor de conversão** é atualizado. Otimize as suas configurações para capturar os dados mais relevantes para si sem exceder a capacidade. Veja [Cálculo da Capacidade do Valor de Conversão.](/docs/skan-conversion-studio#conversion-value-capacity-formula)

![CapacitCounter.png](https://files.readme.io/c976bbf52b8348ffa8de092f5f75eb66b137cc9fa63bc34d0b84e50fc7d112f7-4405725161233.png)

**Nota!**

* A medição no modo fixo destina-se a uma janela de atividade de 24 horas, começando com a primeira vez que a aplicação é aberta.
* Se quiser enviar eventos utilizando S2S, é necessário ativar explicitamente [SKAN S2S](/docs/skan-conversion-studio#report-events-by-servertoserver-api)

**![AppsFlyerAdmin_us-en.png](https://files.readme.io/d67fdedd94c56e8da776e590b12883503f47d36f0d58b996c4c64cc5d0e9c675-16281491712785.png) altAppsFlyerAdmin\_us-en.pngaltPara definir manualmente os valores de conversão no Conversion Studio utilizando um modo fixo:**

1. No painel da AppsFlyer, aceda a **Definições** > **SKAN Conversion Studio.**
2. Clique em opções (⋮) para ver o menu de opções e:
   * Assegure-se de que a **medição SKAN** está ativada. **Nota**! Se estiver desativado, o SDK não chama funções SKAN do iOS, como *registerAppForAdNetworkAttribution*, *updateConversionValue.*
   * [Opcional] [Ativar o envio de eventos por S2S](/docs/skan-conversion-studio#report-events-by-servertoserver-api). Disponível se o modo selecionado for receita, conversão ou envolvimento.
3. Escolha um modo de medição fixo.
4. Siga as informações e instruções na tabela seguinte para o modo de medição fixo selecionado.
5. Clique em **Guardar**.
6. Verifique se os mapeamentos de postback de eventos na aplicação do seu parceiro correspondem aos eventos que configurou.

<div id="fixed-mode-measurement" />

#### Medição em modo fixo

| Modo de medição | Descrição |
| --- | --- |
| Resultados | ![RevenueFixed.png](https://files.readme.io/ee0882a8b76e50c6fc0ce9bdb04934f3c22324bcaeb15181caf685b00c014a80-4406058625809.png)<br /><br />**Receita gerada durante a janela de atividade de 24 horas.**<br /><br />Escolha uma taxa de unidade para USD de uma das seguintes opções:<ul><li>0,01 dólares para medir até 0,63 dólares</li><li>1 dólar para medir até 63 dólares</li><li>10 dólares para medir até 630 dólares</li></ul>A AppsFlyer preenche automaticamente 63 intervalos de medição de receitas. Certifique-se de que o nome do evento `af_skad_revenue` está bem mapeado para os parceiros. No painel, a receita é registada como o máximo do intervalo. Por exemplo, se o intervalo for de 60 a 61 dólares, a receita registada será de 61 dólares. Nota! A receita personalizada usa um método diferente para calcular a receita.<br /><br />**Métricas disponíveis:**<ul><li>Resultados<ul><li>ROI</li><li>ROAS</li><li>ARPU: Receita/utilizadores a instalar a aplicação</li><li>Taxa de conversão de utilizadores: Utilizadores que fazem uma compra/utilizadores que instalam a aplicação</li><li>eCPA</li></ul></li></ul> |
| Conversão | ![mceclip0.png](https://files.readme.io/29535e45638cb2b1eecdf43e4fbee0fa52665c90aefe064caaaac9d0fc98472f-4406052008593.png)<br /><br />**Eventos na aplicação ocorridos uma ou mais vezes durante a janela de atividade de 24 horas**<br /><br />**Definições**:<ul><li>Escolha de 1 a 6 eventos na aplicação para medir na lista suspensa. Limitação: A lista está limitada aos 300 principais eventos durante os últimos 30 dias.</li><li>No painel SKAdNetwork, selecione um evento como o <Anchor target="_blank" href="/marketers/pt/docs/skadnetwork-skan-overview-dashboard-by-appsflyer#dashboard-settings">evento de conversão</Anchor>.</li></ul>**Métricas por evento na aplicação:**<ul><li>Contagem de utilizadores que realizam um evento<ul><li>Taxa de conversão: Utilizadores que realizam o Evento de Conversão/utilizadores que instalam a aplicação</li><li>eCPA</li><li>Sessões (usa o evento *af\_app\_opened*)</li></ul></li></ul>Exemplo de contagens de utilizadores:<ul><li>Registo concluído</li><li>Efetuou uma compra</li><li>Alcançou um nível no jogo</li></ul>Esclarecimento! **Utilize a medição de conversão para verificar** se **um utilizador realizou um evento. Para contabilizar quantas vezes um utilizador executa um evento, utilize a medição de interação.** |
| com o anúncios | ![mceclip1.png](https://files.readme.io/51b38d6693e843f04fe7ce02706ae2959d88a047606b41cccad6ed09a46eea39-4406058637841.png)<br /><br />**Número de vezes que o utilizador realizou um evento específico na aplicação durante o Período de Atividade**<br /><br />**Configurações:**<ul><li>Selecione um evento na aplicação a partir da lista suspensa.</li><li>A seleção na aplicação também é designada como Evento de Conversão.</li><li>Intervalo de valores: 0-63</li></ul>**Métricas para o evento na aplicação**:<ul><li>Contagem de utilizadores a realizar o evento<ul><li>Número médio de eventos por utilizador</li><li>Taxa de conversão</li><li>eCPA</li><li>Sessões</li></ul></li></ul>Exemplos:<ul><li>Meça o número de vezes:<ul><li>um utilizador abriu a aplicação</li><li>o utilizador visualizou um anúncio</li></ul></li></ul> |

</Accordion>

<div id="decode" />

<Accordion title="Decode">

Desenvolva o seu próprio mapeamento de CV para evento e defina o CV na aplicação você mesmo. Use esta opção se não conseguir integrar o SDK da AppsFlyer na sua aplicação.

**Para utilizar a Descodificação**:

1. No painel da AppsFlyer, aceda a **Definições** > **SKAN Conversion Studio.**
2. Clique em opções (⋮) para ver o menu de opções e:
   * Assegure-se de que a **medição SKAN** está ativada. **Nota**! Se estiver desativado, o SDK não chama funções SKAN do iOS, como *registerAppForAdNetworkAttribution*, *updateConversionValue.*
   * Carregue o ficheiro de mapeamento Decode.
3. Clique em **Guardar**.
4. Verifique se os mapeamentos de postback de eventos na aplicação do seu parceiro correspondem aos eventos que configurou.

</Accordion>

<div id="measurement-components" />

## Componentes de medição

<div id="single-source-of-truth" />

<Accordion title="Fonte Única da Verdade">

<table><tbody><tr><td colspan="2"><p><img alt="SSOTControl.png" src="https://files.readme.io/fd99117e9278ebda3b1f0cc137afb266643e5e45325345ec51aeb58c16d4f13c-31247514683153.png"/></p><p>O mecanismo <a href="./single-source-of-truth-ssot-guide-for-ios-attribution" target="_blank">Single Source of Truth (SSOT)</a> sinaliza (e elimina duplicatas) instalações reportadas por mais do que um método de atribuição. Ou seja, SKAN e outro método. O sinalizador está disponível nos relatórios de dados SKAN em bruto e é considerado ao calcular métricas na <a href="./single-source-of-truth-ssot-guide-for-ios-attribution#visualização-do-painel-de-visão-geral-da-fonte-única-da-verdade" target="_blank">visualização SSOT</a> do painel de Visão Geral. </p></td></tr><tr><td>Obrigatório</td><td>Não</td></tr><tr><td>Uso múltiplo permitido</td><td>Não</td></tr><tr><td>Opções de configuração</td><td><p>Se o SSOT estiver ligado, o CV é configurado para sinalizar se um utilizador é atribuído por SKAN e outro método de correspondência de atribuição. </p><p>Onde é usado o sinalizador SSOT?</p><ul><li>Visualização SSOT do painel de visão geral da AppsFlyer</li><li>Os relatórios de dados SKAN em bruto têm o campo <em>af_attribution_flag</em>. Se verdadeiro, o utilizador foi atribuído por SKAN e outro método. </li><li>Relatórios agregados da API de atribuição SKAN.</li></ul></td></tr></tbody></table>

</Accordion>

<div id="inapp-event-component" />

<Accordion title="Componente de evento na aplicação">

<Table>
  <tbody>
    <tr>
      <td colSpan="2">
        ![ConversionStudioIn-app-event.png](https://files.readme.io/7b110093a72b13c0750ccb66da5efe737b8f83c0adcb95eb35185a4dc77bad6c-4406051824657.png)
      </td>
    </tr>
    <tr>
      <td>
        Obrigatório
      </td>
      <td>
        Não
      </td>
    </tr>
    <tr>
      <td>
        Uso múltiplo permitido
      </td>
      <td>
        Sim
      </td>
    </tr>
    <tr>
      <td>
        Opções de configuração
      </td>
      <td>
        Selecione um evento na aplicação; em seguida, configure os intervalos de acordo com o seu objetivo de medição:

        * **Apenas conversão:** Configure um intervalo de 0 a 1
        * **Envolvimento e conversão:** Configure vários intervalos com os seus valores selecionados
      </td>
    </tr>
    <tr>
      <td>
        Intervalos para o envolvimento
      </td>
      <td>
        Para medir o envolvimento, deve criar intervalos de ocorrência. Quando uma ocorrência do evento de engajamento selecionado é reportada, o SKAN associa-a ao intervalo correto com base no número de ocorrências do evento.

        **Características**

        * Cada intervalo contem um intervalo de receita que consiste num valor **de** e num valor **até**. O valor inferior não é incluído no intervalo; no entanto, o valor superior é. Por exemplo, 5–10 significa mais que 5 e até 10, inclusive.
        * O intervalo com o valor mais baixo começa sempre em 0, mas sem incluir o 0.
        * Pode criar quantos intervalos desejar, mas lembre-se de que cada intervalo afeta a sua capacidade de valor de conversão.
        * Os intervalos devem ser sequenciais, sem espaços entre eles.

        **Medir o envolvimento usando intervalos**

        * Quando uma ocorrência de evento é reportada, o SKAN associa-a ao intervalo correspondente. As ocorrências registadas são derivadas da média do intervalo. O valor é arredondado para o número inteiro mais próximo. Por exemplo, 5,7 é arredondado para 6.
        * Se o número de ocorrências ultrapassar o máximo do intervalo mais alto, as ocorrências serão associadas a esse intervalo mais alto. O número de ocorrências registado é o valor médio do intervalo de valor mais alto. Ou seja, o número real de ocorrências é ignorado.
        * Nos dados brutos, tanto o número real de ocorrências como os intervalos estão disponíveis.

        **Exemplo:**

        Na imagem, estão representados os seguintes intervalos de ocorrência:

        Os intervalos de ocorrência definidos são:

        * A: 0-5
        * B: 5-10
        * C: 10-20

        O número de ocorrências é registado utilizando os intervalos seguintes:

        | Exemplo | Número de ocorrências reportadas pelo SDK | Intervalo associado | Número de ocorrências reportadas |
        | --- | --- | --- | --- |
        | 1 | 5 | E | 3 |
        | 2 | 6 | B | 8 |
        | 3 | 10 | B | 8 |
        | 4 | 125 | C | 15 |
      </td>
    </tr>
    <tr>
      <td>
        Limitação
      </td>
      <td>
        Um evento na aplicação pode ser associado uma única vez a este componente.
      </td>
    </tr>
  </tbody>
</Table>

</Accordion>

<div id="revenue-component" />

<Accordion title="Componente de Receita">

<Table>
  <tbody>
    <tr>
      <td colSpan="2">
        ![ConversionStudioRevenue.png](https://files.readme.io/202c258f11cd93248f8aceff410126efc02ced11e9a9b159bac8ba81cbc8d9fe-4406075612305.png)
      </td>
    </tr>
    <tr>
      <td>
        Obrigatório
      </td>
      <td>
        Não
      </td>
    </tr>
    <tr>
      <td>
        Uso múltiplo permitido
      </td>
      <td>
        Sim, se a fonte de receita de eventos na aplicação for utilizada.
      </td>
    </tr>
    <tr>
      <td>
        Opções de configuração
      </td>
      <td>
        A receita global de todos os fluxos pode ser registada com um único evento ou individualmente, ao selecionar eventos específicos na aplicação que geram receita.

        As seguintes opções de fonte de receita são suportadas:

        * **Receita geral**
          * A receita global, incluindo a de todos os eventos na aplicação e a receita de anúncios (quando aplicável), pode ser medida com um único evento `af_skad_revenue`. Assegure-se de que o nome do evento `af_skad_revenue` está corretamente mapeado para os parceiros.
          * O componente pode ser incluído uma única vez.
        * **Evento na Aplicação**
          * A medição de diferentes fluxos de receita pode ser feita selecionando eventos específicos na aplicação no esquema SKAN. Após adicionar a medição de receita, selecione "evento na aplicação" na seleção da fonte de receita. Assegure-se de que todos os eventos estão corretamente mapeados para as redes de anúncios.  
            Nota: Ao medir a receita de eventos específicos na aplicação, `af_skad_revenue` não deve ser mapeado.
          * O componente pode ser utilizado múltiplas vezes.
          * Ao reportar receita via postback para redes de anúncios, verifique se os mapeamentos de postback de eventos na aplicação incluem os eventos de receita que definiu.
      </td>
    </tr>
    <tr>
      <td>
        Intervalos
      </td>
      <td>
        Para medir receita, devem ser criados intervalos de receita. Quando a receita é reportada, o SKAN associa a receita reportada ao intervalo adequado.

        **Características**

        * Cada intervalo contém um intervalo de ocorrência composto por um valor **de início** e um valor **de fim**. O valor inferior não está incluído, mas o valor superior está. Por exemplo, 5–10 significa mais que 5 e até 10, inclusive.
        * O intervalo com o valor mais baixo começa sempre em 0, mas sem incluir o 0.
        * Pode criar quantos intervalos desejar, mas lembre-se de que cada intervalo afeta a sua capacidade de valor de conversão.
        * Os intervalos devem ser sequenciais (sem lacunas entre eles).
        * Os montantes estão em USD.
        * Se conduzir campanhas nos anúncios do Meta, deverá ter 4 ou mais intervalos.
        * Os valores dos intervalos podem ter até 4 dígitos decimais.

        **Registo de receitas utilizando intervalos**

        * Quando a receita é reportada, o SKAN associa a receita ao intervalo apropriado. A receita registada corresponde ao valor médio do intervalo.
        * Se a receita reportada ultrapassar o valor médio do intervalo de maior valor, a receita é associada a esse intervalo. **Nota**! A receita registada é o valor médio deste intervalo. Em outras palavras, o montante real da receita é ignorado.
        * Nos dados brutos, estão disponíveis a receita registada e o intervalo associado.

        **Exemplo:**

        Na imagem, são representados os seguintes intervalos de receita:

        * A: 0-5
        * B: 5-10
        * C: 10-20

        A receita é registada utilizando os intervalos da seguinte forma:

        | Exemplo | Receita reportada pelo SDK | Intervalo associado | Receita registrada |
        | --- | --- | --- | --- |
        | 1 | 5 | E | 2,5 USD |
        | 2 | 6 | B | 7,5 USD |
        | 3 | 10 | B | 7,5 USD |
        | 4 | 125 | C | 15 USD |
      </td>
    </tr>
  </tbody>
</Table>

</Accordion>

<div id="funnel-component" />

<Accordion title="Componente do funil">

<Table>
  <tbody>
    <tr>
      <td colSpan="2">
        ![ConversionValueFunnel.png](https://files.readme.io/b43b5db0cee11c9addd50fb56af1ac6d3221e1956e2ee3c4c21a6940e9dfe61b-4406051997969.png)
      </td>
    </tr>
    <tr>
      <td>
        Obrigatório
      </td>
      <td>
        Não
      </td>
    </tr>
    <tr>
      <td>
        Uso múltiplo permitido
      </td>
      <td>
        Não
      </td>
    </tr>
    <tr>
      <td>
        Opções de configuração
      </td>
      <td>
        Liste um conjunto sequencial de eventos num funil. Como a ocorrência de um único evento é tratada como a ocorrência de todos os eventos anteriores, a ordem em que lista os eventos é de extrema importância, conforme ilustrado no exemplo seguinte.
      </td>
    </tr>
    <tr>
      <td>
        Exemplo
      </td>
      <td>
        Um funil contém os eventos a, f, b, k e z, conforme ilustrado na imagem anterior.

        | Exemplo | Evento realizado | Eventos registados |
        | --- | --- | --- |
        | 1 | a | a |
        | 2 | b | a, f, b |
        | 3 | z | a, f, b, k, z |
      </td>
    </tr>
  </tbody>
</Table>

</Accordion>

<div id="priority-measurement-component" />

<Accordion title="Componente de medição de prioridade">

Utilize o componente de medição de prioridade, que faz parte do modo Personalizado, para classificar as jornadas de ação do utilizador na aplicação com base na lógica do seu negócio, de modo a que as medições de alta prioridade prevaleçam sobre as de baixa prioridade. Isto permite escolher o que medir em cada etapa do funil de conversão.

Cada prioridade (máximo de 63) pode incluir receita, evento na aplicação ou ambos. Quando um utilizador realiza ações na aplicação, a AppsFlyer determina a prioridade adequada para essas ações e ajusta o CV em conformidade.

Para facilitar a compreensão, vamos comparar o uso de Personalizado com e sem o componente de prioridade. **Sem** prioridade, a AppsFlyer mapeia todas as combinações possíveis de medição para os CVs. Por outro lado, **com** prioridade, apenas as combinações de medição que você definiu explicitamente são mapeadas para os CVs.

A prioridade é explicada mais detalhadamente no [exemplo pormenorizado](/docs/skan-conversion-studio#priority-measurement-detailed-example) deste artigo.

**Princípios de prioridade**

* Pode definir entre 1 a 63 prioridades. O número disponível depende da sua janela de atividade e das configurações da Fonte Única da Verdade.
* A prioridade 1 tem sempre a importância mais alta. A prioridade com o maior número tem a importância mais baixa.
* Uma prioridade pode consistir em [receita](/docs/skan-conversion-studio#revenue-component), [evento na aplicação](/docs/skan-conversion-studio#inapp-event-component) ou em ambos os componentes. Uma prioridade específica pode conter múltiplos eventos na aplicação e fluxos de receita.
* O funil não está disponível em prioridades. No entanto, defina vários eventos na aplicação dentro de uma prioridade para medir a conversão do utilizador num funil.
* Para utilizar o componente de medição prioritária, não pode ter outros componentes configurados, como eventos na aplicação ou receita.

**Para definir a medição usando a** prioridade:

1. Na AppsFlyer, vá ao **SKAN Conversion Studio.**
2. Selecione **Personalizado** e clique em **Continuar**.
3. Se necessário, clique em **Eliminar** para remover as configurações atuais.
4. Clique em **+ Adicionar medição**. Selecione **Prioridade**.   
   A prioridade 1 aparece.  
   [![CVmapping.png](https://files.readme.io/f0bc64c4fbb95462a17a1e6bb8d250d3396096b743b3d412cd0605d9b0a1079d-4756458366865.png)](https://files.readme.io/f0bc64c4fbb95462a17a1e6bb8d250d3396096b743b3d412cd0605d9b0a1079d-4756458366865.png)
5. Selecione um componente de medição a partir de:
   * Resultados
   * Evento na app
6. Preencha os campos de acordo com a interface do utilizador.
   * Considere que uma prioridade pode incluir receita, evento na aplicação ou ambos.
   * Os valores dos intervalos de ocorrências de eventos e receitas podem ser em ordem crescente ou decrescente, mas devem ser contínuos. Por exemplo, os seguintes intervalos são contínuos: 1-5, 5-8, 8-10 e assim por diante. Um determinado intervalo pode ser usado mais de uma vez (repetido) se, da segunda vez, fizer parte de uma combinação única e for o mesmo intervalo da última prioridade com intervalo. Por exemplo, 1-5, 1-5 + adicionar ao carrinho.  
     **Exemplo de aumento e redução de receita**

| Evento | Ocorrência | Resultados |
| --- | --- | --- |
| Evento P1\_a | 2-3 | $5 - $50 |
| Evento P2\_a | 2-3 | $0 - $5 |
| Evento P3\_a | 1-2 | $5 - $50 |
| Evento P4\_a | 1-2 | $0 - $5 |
| Evento P5\_a | 0 a 1 | $5 - $50 |
| Evento P6\_a | 0 a 1 | $0 - $5 |

7. Clique em **Validar.**  
   A mensagem **Prioridade é válida** aparece. Caso contrário, corrija a prioridade antes de prosseguir.
8. Faça uma das seguintes opções:
   * Para adicionar uma prioridade, clique em **+ Adicionar prioridade.** A atual prioridade 1 é rebaixada para prioridade 2. Conclua as configurações de prioridade como descrito anteriormente.
   * Para eliminar uma prioridade, clique em … > **Eliminar.** > **Excluir.**
   * Para alterar o nível de prioridade, clique em **Opções** (⋮) e escolha entre **Alterar ordem** ou **Tornar prioridade mais baixa**.
   * Para duplicar uma prioridade, clique em **Opções** (⋮) e selecione **Duplicar**.
   * Clique em **Guardar** para finalizar a definição das prioridades.

</Accordion>

<div id="lock-window" />

<Accordion title="Janela de bloqueio">

**Nota**: A janela de bloqueio só é relevante para SKAN 4 e versões posteriores.

<table><tbody><tr><td colspan="2"><img alt="lock_window.png" src="https://files.readme.io/d9db51890a5d589b7343ed389d55af0c4181b249a2c5e970b9a5e1244c489abc-14240675527057.png"/></td></tr><tr><td>Uso</td><td>Por predefinição, as janelas SKAN medem o valor do utilizador em momentos específicos após a instalação. Pode bloquear as janelas antecipadamente e enviar postbacks com todos os dados disponíveis. Para isso, defina as condições para quando bloquear as janelas.</td></tr><tr><td>Obrigatório</td><td>Não</td></tr><tr><td>Uso múltiplo permitido</td><td>Sim, um para cada janela SKAN</td></tr><tr><td>Opções de condição</td><td><p>A janela de Bloqueio oferece duas opções para bloquear antecipadamente a janela SKAN:</p><ul><li>Tempo: Deve escolher um momento pós-instalação (antes do tempo padrão) para bloquear a janela. <strong>Nota</strong>: O bloqueio baseado no tempo só é efetivo se o utilizador abrir a aplicação.</li><li>Valor bruto elevado: Assim que o valor bruto elevado for atingido, a janela encerra.</li></ul></td></tr><tr><td>Impacto do uso da janela de bloqueio</td><td>Os postbacks SKAN não indicam quando uma janela encerra, logo, o estado da janela de bloqueio não é considerado ao estimar o tempo de instalação. Assim, bloquear a janela antecipadamente pode afetar a precisão das estimativas de tempo de instalação.</td></tr></tbody></table>

</Accordion>

<div id="activity-window" />

<Accordion title="Janela de Atividade">

**Nota**:

* A janela de atividade só é relevante para SKAN 3 e anteriores (ou seja, nos modos personalizado e fixo).
* Se usar SKAN 4+, mas os dispositivos do utilizador ou redes de anúncios ainda não suportarem SKAN 4, a janela de atividade é de 48 horas.

<table><tbody><tr><td colspan="2"><img alt="flex_activity_window.jpg" src="https://files.readme.io/ac51126eda5b9d319ccdd90adb936baaa512dcd844ad191cac6c20a45cd4aae8-6390396808081.jpg"/></td></tr><tr><td>Obrigatório</td><td>Sim </td></tr><tr><td>Uso múltiplo permitido</td><td>Não</td></tr><tr><td>Características do tempo</td><td><ul><li>O cronómetro tem uma duração fixa, definida por si, e funciona em paralelo com o cronómetro do iOS.</li><li>Por outro lado, o cronómetro do iOS começa com uma duração inicial de 24 horas. Sempre que o valor da conversão aumenta, o temporizador é reiniciado.</li><li>Duração padrão de 24 horas.</li><li>A medição para quando qualquer temporizador atinge 0. </li></ul></td></tr><tr><td>Duração do temporizador</td><td><ul><li>Intervalo: 12-72 horas. Para mais opções, veja <strong>Medição flexível</strong> nesta tabela.  </li><li>Quando o temporizador termina, a AppsFlyer interrompe a medição.</li><li>Se a duração do temporizador for superior a 24 horas, o utilizador deve estar ativo na aplicação pelo menos uma vez por intervalo. Caso contrário, a medição pode terminar precocemente, pois a AppsFlyer não consegue impedir que o temporizador do iOS chegue a 0, o que significa que o iOS encerra a medição. </li></ul></td></tr><tr><td>Intervalo</td><td><p>12 ou 24 horas. Os intervalos afetam a precisão do período da última atividade e do instante de instalação. Para mais opções, veja <strong>Medição flexível</strong> nesta tabela. </p><p>O período da última atividade está disponível nos relatórios de dados brutos nas colunas <em>min_install_time</em> e <em>max_install_time</em> e é utilizado para determinar o instante de instalação, conforme descrito nesta secção.</p><p>Exemplo:</p><ul><li>A duração do temporizador está definida para 48 horas.</li><li>O utilizador esteve ativo pela última vez durante a hora 40.</li><li>Dependendo da configuração do intervalo, o período da última atividade é: <br/> <ul><li>Intervalo de 12 horas: 36–48 horas</li><li>Intervalo de 24 horas: 24–48 horas</li></ul></li></ul></td></tr><tr><td>Tempo de Instalação</td><td><p>O tempo de instalação é calculado da seguinte forma:</p><p><code>Tempo de instalação = horário de chegada do postback - [intervalo médio da última atividade] - [atraso do postback do iOS]</code></p><ul><li> <code>Postback arrival time</code>:  Momento em que o postback do iOS foi recebido diretamente do dispositivo; geralmente pela rede de anúncios. </li><li> <code>Average last-active range</code> considera o CV e é calculado assim:<ul><li>Se CV = 0, assume-se que o último intervalo ativo é 0. </li><li>Se CV &gt; 1 ou CV = nulo: Usando min_install_time e max_install_time, estes são definidos com base no intervalo e na última vez que o utilizador foi visto ativo na aplicação.  Por exemplo, se o intervalo for 12 horas, como o utilizador foi visto pela última vez 25 horas após a instalação, o resultado é [24 + 36] / 2 = 30 horas. </li></ul></li><li> <code>iOS postback delay</code>: [24 + 48] / 2 = 36. Considere que o temporizador do iOS termina 24 horas depois da última alteração no CV e o postback é enviado 0 a 24 horas depois disso. <strong>36 horas é uma constante</strong>. </li></ul></td></tr><tr><td>Opções de configuração</td><td><p>A janela de atividade é composta por duas configurações: duração e intervalos. </p><ul><li>Duração: 24 a 72 horas com intervalos de 24 horas. Máximo de 3 intervalos.</li><li>Duração: 12 a 72 horas com intervalos de 12 horas. Máximo de 6 intervalos.</li></ul></td></tr><tr><td>Impacto da alteração da duração da janela de atividade</td><td><ul><li>O postback é enviado entre 0 e 24 horas após o temporizador do iOS expirar. </li><li>Inicialmente, o temporizador do iOS está configurado para terminar após 24 horas. </li><li>Se definir a janela de atividade para mais de 24 horas, o utilizador precisa estar ativo pelo menos uma vez por intervalo para garantir que o temporizador do iOS não expire.</li></ul></td></tr><tr><td><p>Considerações relativas às redes de anúncios</p></td><td><ul><li>A duração padrão do temporizador é de 24 horas.</li><li>É possível definir uma duração diferente, mas antes, verifique com os seus parceiros de rede de anúncios se suportam um período diferente do padrão. </li><li><span>Ao utilizar a janela de 24 horas, pode melhorar as suas métricas dividindo o período em dois intervalos de 12 horas cada. Ao fazê-lo, conseguirá saber se o utilizador continuou a usar a aplicação após as primeiras 12 horas. </span></li></ul></td></tr><tr><td>Exemplo de requisitos de capacidade para intervalos</td><td>A imagem nesta secção mostra um temporizador de 60 horas com um intervalo de 12 horas. </td></tr><tr><td>Opções flexíveis para a janela de atividade</td><td><p>A medição flexível permite definir uma janela de atividade mais longa com granularidade horária. Da mesma forma, para a definição dos intervalos. As configurações apresentam as seguintes características:</p><ul><li>Janela de atividade:<ul><li>Intervalo: 12 a 1512 horas (63 dias)  </li><li>Granularidade: 1 hora</li></ul></li><li>Intervalos:<ul><li>Intervalo: <span>Mínimo de 1 hora e outros múltiplos da janela de atividade</span> </li><li>Granularidade de 1 hora</li></ul></li></ul><p>Consideração: A relação entre a janela de atividade e os intervalos deve ser expressa em números inteiros.</p><p>Melhor prática: Não defina o intervalo para mais de 24 horas, pois isso diminui a precisão da estimativa do tempo de instalação</p></td></tr></tbody></table>

</Accordion>

<div id="additional-information" />

## Informações adicionais

<div id="view-cv-mapping" />

<Accordion title="Ver mapeamento de CV">

* Visualize os eventos associados a um CV ao selecionar o CV. Os eventos mapeados são apresentados abaixo da tabela.
* Descarregue a tabela de mapeamento de CV como um ficheiro CSV. Clique em **Descarregar ficheiro de mapeamento.**
* Obtenha o mapeamento de CV através da <Anchor target="_blank" href="/marketers/pt/docs/skan-cv-schema-api-for-advertisers">API do esquema SKAN CV para anunciantes</Anchor>.

<Image alt="SKAN_download_mapping.png" src="https://files.readme.io/62dc60da0001c0eccc96791f3f3320f8ea0bc24db3977af4390643c5a95a5ad3-46095838352401.png" width="2482px" />

<div id="csv-mapping-file-columns" />

#### Colunas do ficheiro de mapeamento CSV

| Coluna | Descrição |
| --- | --- |
| ID\_da\_aplicação |  |
| valor\_de\_conversão | Valor CV:<ul><li>0 a 63</li><li>Baixo, médio ou elevado</li></ul> |
| nome\_do\_evento |  |
| mínimo\_contador\_evento | Limiar inferior do contador de eventos |
| máximo\_contador\_evento | <ul><li>Limiar superior do contador de eventos.</li><li>Nos relatórios gerados pela AppsFlyer, o número de eventos é calculado utilizando a seguinte fórmula: Arredondar para cima ([mínimo\_contador\_evento + máximo\_contador\_evento]) / 2</li></ul> |
| mínimo\_rendimento\_evento | Limiar inferior da gama de rendimentos do evento em USD |
| máximo\_rendimento\_evento | <ul><li>Limiar superior da gama de rendimentos do evento em USD</li><li>Nos relatórios gerados pela AppsFlyer, o rendimento é calculado através da seguinte fórmula: ([mínimo\_rendimento\_evento + máximo\_rendimento\_evento]) / 2)</li></ul> |
| mínimo\_tempo\_pós\_instalação | Limiar inferior em horas pós-instalação, indicando quando o utilizador esteve ativo pela última vez na aplicação. |
| máximo\_tempo\_pós\_instalação | Limiar superior em horas pós-instalação, indicando quando o utilizador esteve ativo pela última vez na aplicação. |
| última\_alteração\_configuração | Data em que guardou a configuração no SKAN Conversion Studio. |

</Accordion>

<div id="conversion-value-capacity-formula" />

<Accordion title="Fórmula de capacidade de valor de conversão">

Como mencionado anteriormente, o número máximo de valores de conversão disponíveis é de 64. A fórmula seguinte calcula quantos dos valores de conversão disponíveis são utilizados pelo modo.

```http
(duração do tempo de atividade em horas / tamanho do intervalo em horas) * \n(número de faixas de receita + 1 ) * \n(número de faixas de eventos in-app + 1 ) * \n(número de etapas em um funil + 1)
```

Ajuste a fórmula para incluir todos os componentes de medição

</Accordion>

<div id="maximized-custom-cv-examples" />

<Accordion title="Exemplos de CV personalizados maximizados">

<div id="example-1" />

#### Exemplo 1

| Componente | Descrição |
| --- | --- |
| Janela de Atividade | <ul><li>Duração: 24 horas</li><li>Intervalo: 24 horas correspondendo a 1 intervalo</li></ul> |
| Resultados | <ul><li>A receita é reportada utilizando um único evento na aplicação (geral)</li><li>Intervalos de receita: 15</li></ul> |
| Na aplicação | Nenhum |
| Funil | 3 eventos na aplicação |

<div id="example-2" />

#### Exemplo 2

| Componente | Descrição |
| --- | --- |
| Janela de Atividade | <ul><li>Duração: 24 horas</li><li>Intervalo: 12 horas correspondendo a 2 intervalos</li></ul> |
| Resultados | <ul><li>A receita é reportada alocada por tipo utilizando 2 eventos diferentes na aplicação</li><li>Intervalos de receita: 3 (por evento na aplicação)</li></ul> |
| Definido na aplicação para conversão | 1 evento na aplicação para medir a conversão; cada evento na aplicação requer 1 intervalo |
| Funil | Nenhum |

<div id="example-3" />

#### Exemplo 3

| Componente | Descrição |
| --- | --- |
| Janela de Atividade | <ul><li>Duração: 24 horas</li><li>Intervalo: 24 horas correspondendo a 1 intervalo</li></ul> |
| Resultados | <ul><li>A receita é reportada utilizando um único evento na aplicação (geral)</li><li>Intervalos de receita: 3</li></ul> |
| Definido na aplicação para envolvimento | <ul><li>2 eventos na aplicação para medir ocorrências de engajamento</li><li>Intervalos de ocorrência: 3 por evento na aplicação</li></ul> |
| Funil | Nenhum |

<div id="example-4" />

#### Exemplo 4

| Componente | Descrição |
| --- | --- |
| Janela de Atividade | <ul><li>Duração: 48 horas</li><li>Intervalo: 12 horas divididas em 4 intervalos</li></ul> |
| Resultados | <ul><li>A receita é reportada utilizando um único evento na aplicação (geral)</li><li>Intervalos de receita: 7</li></ul> |
| Definido na aplicação para conversão | 1 evento na aplicação para medir a conversão; requer 1 intervalo |
| Funil | Nenhum |

</Accordion>

<div id="priority-measurement-detailed-example" />

<Accordion title="Exemplo detalhado de medição por prioridade">

Numa aplicação de compras, o anunciante quer focar a medição nas:

* Ações de utilizadores **não pagantes**
* Receita de utilizadores **pagantes**

Ao fazer isto, o anunciante utiliza CVs para registar receitas com mais precisão. Estes requisitos de medição transformam-se num conjunto de prioridades de medição como indicado na tabela seguinte.

Considere:

* A prioridade máxima é sempre 1. **Nota**! Os números de prioridade não se traduzem diretamente em CVs. Os mapeamentos de CV são apresentados na interface do usuário.
* O número máximo de prioridades é 63. O número exato disponível depende da janela de atividade e se a fonte única de verdade está ativada.
* Cada prioridade consiste num intervalo de receita ou de ocorrências de eventos na aplicação, ou ambos.
* Valores dos intervalos: O valor mais baixo do limite não está incluído no intervalo, mas o valor mais alto está. Por exemplo, o intervalo de $5 a $10 não inclui o valor 5, mas inclui o valor 10.

<div id="measurement-priorities-setting-example" />

#### Exemplo de configuração de prioridades de medição

<table><thead><tr><th>Prioridade #</th><th>Faixa de receita</th><th>Evento na app</th></tr></thead><tbody><tr><td>1 [Prioridade máxima]</td><td>5 a 10 dólares</td><td>enviar_recomendação</td></tr><tr><td>2</td><td>5 a 10 dólares</td><td>--</td></tr><tr><td>3</td><td>US$ 0 a US$ 5</td><td>enviar_recomendação</td></tr><tr><td>4</td><td>US$ 0 a US$ 5</td><td>--</td></tr><tr><td>5</td><td>--</td><td>enviar_recomendação<br/>adicionar_ao_carrinho</td></tr><tr><td>6</td><td>--</td><td>enviar_recomendação</td></tr><tr><td>7 [Prioridade mínima]</td><td>--</td><td>adicionar_ao_carrinho</td></tr><tr><td colspan="3">-- Nenhum valor definido</td></tr></tbody></table>

A tabela a seguir contém cenários de viagem do utilizador. Cada cenário inclui a lista de ações realizadas pelo utilizador durante sua jornada e a prioridade determinada pela AppsFlyer.

Na tabela:

* Várias ações são separadas usando >
* O valor entre parênteses (), é a prioridade estabelecida pela AppsFlyer após o utilizador concluir a ação. Usando a prioridade, a AppsFlyer atualiza o CV no aplicativo.

<div id="user-journey-scenarios" />

#### Cenários de exploração do utilizador

| Cenário de jornada do utilizador | Ações do utilizador e prioridade |
| --- | --- |
| E | adicionar\_ao\_carrinho (7) |
| B | adicionar\_ao\_carrinho (7) > enviar\_recomendação (5) |
| C | Compra de $3 (4) |
| J | Compra de $6 (2) |
| E | Compra de $6 (2) > enviar\_recomendação (1) |

</Accordion>

<div id="fixed-mode-examples" />

<Accordion title="[Legado] Exemplos de modo fixo">

<div id="note-1" />

> 📘 **Nota**
>
> Os modos fixos não estarão disponíveis para novas aplicações a partir de 23/06/2024. Todas as funcionalidades são suportadas nos modos Custom e SKAN4.

<div id="example-a-revenue-measurement" />

#### Exemplo A: Medição de receita

| Fator | Observações |
| --- | --- |
| Cenário | <ul><li>20 utilizadores instalam a aplicação e realizam as seguintes compras:<ul><li>9 utilizadores, cada um faz uma compra de $10</li><li>5 utilizadores, cada um faz uma compra de $5</li><li>1 utilizador faz uma compra de $1, depois $3, depois $5, e finalmente $1. No total, $10.</li></ul></li><li>Dados de custos fornecidos pela API da rede de anúncios: $30</li></ul> |
| Configuração SKAN | <ul><li>Selecione o tipo de medição: receita</li><li>Definir fator de conversão: 1 unidade de conversão = $1</li><li>Evento de conversão designado: No SDK, deve enviar a receita utilizando o parâmetro *af\_revenue*.</li></ul> |
| Métricas Selecionadas | Métricas relacionadas com a receita disponíveis<ul><li>Instalações: 20</li><li>Receita: $125</li><li>Conversões: 15</li><li>ARPU: $6,25</li><li>ROI: 316%</li></ul> |
| Número de linhas de dados brutos por relatório | <Anchor target="_blank" href="/marketers/pt/docs/skan-raw-data-reports">Os relatórios de dados brutos estão disponíveis no Data Locker</Anchor><ul><li>Postbacks de dispositivos: 20 linhas</li><li>Instalações: 20 linhas</li><li>Eventos na Aplicação: 15 linhas. Nota! O utilizador que faz múltiplas compras é representado por uma única linha de $10.</li></ul> |
| Considerações do desenvolvedor | Os eventos que geram receitas são reconhecidos |

<div id="example-b-conversion-measurement" />

#### Exemplo B: Medição de conversão

<Table>
  <thead>
    <tr>
      <th>
        Fator
      </th>
      <th>
        Observações
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        Exemplo
      </td>
      <td>
        * 5 utilizadores (A-E) instalam a aplicação
        * Realizam de 0 a 3 eventos diferentes na aplicação, conforme mostrado na tabela
        * Dados de custos fornecidos pela API da rede de anúncios: $30

        <div id="inapp-events-performed-by-users" />

        #### Eventos na aplicação realizados pelos utilizadores

        |  | na\_aplicação-1 | na\_aplicação-2 | na\_aplicação-3 |
        | --- | --- | --- | --- |
        | Utilizador A | Realizado | Realizado | - |
        | Utilizador B | Realizado | - | Realizado |
        | Utilizador C | Realizado | Realizado | - |
        | Utilizador D | Realizado | Realizado | - |
        | Utilizador E | - | - | - |
      </td>
    </tr>
    <tr>
      <td>
        Configuração de Atribuição SKAdNetwork
      </td>
      <td>
        Selecione o tipo de medição: Conversão

        * Selecione eventos na aplicação: na\_aplicação-1, na\_aplicação-2, na\_aplicação-3
        * No <Anchor target="_blank" href="/marketers/pt/docs/skadnetwork-skan-overview-dashboard-by-appsflyer#dashboard-settings">painel</Anchor> da SKAdNetwork, seleciona um dos eventos para calcular a métrica de utilizadores convertidos. Pode alterar o evento selecionado conforme necessário.
      </td>
    </tr>
    <tr>
      <td>
        Métricas Selecionadas
      </td>
      <td>
        <div id="inapp-related-metrics-available" />

        #### Métricas relacionadas com eventos dentro da aplicação disponíveis

        | Métrica | Aplicação | na\_aplicação-1 | na\_aplicação-2 | na\_aplicação-3 |
        | --- | --- | --- | --- | --- |
        | Instalações | 5 |  |  |  |
        | Conversões | 4 |  |  |  |
        | Utilizadores únicos |  | 4 | 3 | 1 |
        | eCPA | $7,5 |  |  |  |

        **Nota!** Como o evento de conversão designado é na aplicação-1, o valor 4 é utilizado para calcular métricas a nível da aplicação e para métricas na aplicação-1.
      </td>
    </tr>
    <tr>
      <td>

      </td>
      <td>
        <Anchor target="_blank" href="/marketers/pt/docs/skan-raw-data-reports">Os relatórios de dados brutos estão disponíveis no Data Locker</Anchor>

        * Postbacks de dispositivos: 5 linhas
        * Instalações: 5 linhas
        * Eventos na Aplicação: 8 linhas
      </td>
    </tr>
    <tr>
      <td>
        Considerações do desenvolvedor
      </td>
      <td>
        * Garanta que envia os eventos realizados pelos utilizadores na aplicação.
        * A solução SKAdNetwork desconsidera os valores dos eventos, exceto quando se refere a medições de lucros.
      </td>
    </tr>
  </tbody>
</Table>

<div id="example-c-engagement-measurement" />

#### Exemplo C: Medição de envolvimento

<Table>
  <thead>
    <tr>
      <th>
        Fator
      </th>
      <th>
        Observações
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        Exemplo
      </td>
      <td>
        5 utilizadores instalam a aplicação e abrem-na o número de vezes indicado na tabela.

        <div id="app-opens" />

        #### Aberturas da Aplicação

        |  | Número de vezes que o evento é realizado |
        | --- | --- |
        | Utilizador A | 63 |
        | Utilizador B | 10 |
        | Utilizador C | 5 |
        | Utilizador D | 1 |
        | Utilizador E | - |
      </td>
    </tr>
    <tr>
      <td>
        Configuração de Atribuição SKAdNetwork
      </td>
      <td>
        * Selecione o tipo de medição: Envolvimento
        * Evento de conversão designado: af\_app\_opened. Atenção! Pode usar qualquer evento disponível.
      </td>
    </tr>
    <tr>
      <td>
        Métricas Selecionadas
      </td>
      <td>
        Exemplos de Métricas Disponíveis

        * Instalações: 5
        * Conversões: 4
        * Sessões: 79
      </td>
    </tr>
    <tr>
      <td>
        Número de linhas de dados brutos por relatório
      </td>
      <td>
        <Anchor target="_blank" href="/marketers/pt/docs/skan-raw-data-reports">Os relatórios de dados brutos estão disponíveis no Data Locker</Anchor>

        * Postbacks de dispositivos: 5 linhas
        * Instalações: 5 linhas
        * Eventos na Aplicação: 4 linhas; cada linha equivale a uma única sessão  
          Nota: Neste exemplo, existem quatro linhas diferentes, pois quatro utilizadores únicos diferentes realizaram este evento.  
          Para contar e calcular o número real de ocorrências do evento, as linhas terão uma contagem mínima e máxima de eventos associada a elas.
      </td>
    </tr>
    <tr>
      <td>
        Considerações do desenvolvedor
      </td>
      <td>
        Sempre que um utilizador realiza o evento de envolvimento selecionado, envie o evento na aplicação. A SKAdNetwork conta o número de vezes que o evento é enviado.
      </td>
    </tr>
  </tbody>
</Table>

<div id="skan-conversion-studio-api" />

<Accordion title="API do SKAN Conversion Studio">

Se tiver muitas aplicações para as quais precisa de configurações semelhantes de valor de conversão SKAN, pode ser desafiador e demorado criar o esquema para cada uma separadamente na interface do Conversion Studio. Para economizar tempo e esforço, configure o seu esquema SKAN uma vez na interface e utilize a API do SKAN Conversion Studio para aplicar o mesmo esquema em várias aplicações. **Nota**: A API só suporta esquemas configurados na interface utilizando SKAN 4 ou modos de medição personalizados.

**Para usar a API do SKAN Conversion Studio**:

1. Obtenha o <Anchor target="_blank" href="/marketers/pt/docs/managing-appsflyer-tokens">token de API</Anchor>. Um administrador necessita de recuperar o token.
2. Forneça o token API ao seu programador para ser usado no cabeçalho de autenticação.
3. Forneça aos programadores os IDs das aplicações:
   * A aplicação para a qual o esquema SKAN está configurado na interface (ou seja, a aplicação de onde pretende copiar o esquema SKAN).
   * Todas as aplicações que pretende que tenham o mesmo esquema.
4. Peça ao programador para seguir as <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/skan-studio-config-overview-1">instruções da API SKAN Conversion Studio</Anchor> no hub do programador.

**Nota**:

* A API pode ser usada para copiar o esquema para uma aplicação por chamada de API. O programador pode também criar um script para replicar o esquema necessário em várias aplicações.
* A API SKAN Conversion Studio não está disponível para agências.

</Accordion>

<div id="skan-schema-analysis" />

<Accordion title="Análise do esquema do SKAN">

Entenda como seus valores de conversão estão sendo usados, identifique configurações de esquema com baixo desempenho e refine sua configuração de mensuração do SKAN com base em dados reais de uso.

Os insights da distribuição dos valores de conversão são compostos por três abas que ajudam você a otimizar diferentes aspectos do seu esquema do SKAN:

* Aba Valores de conversão
* Aba Receita
* Aba Eventos

<div id="conversion-values-tab" />

#### **Valores de conversão**

Veja quais valores de conversão estão realmente sendo usados e quais não estão.

Uma distribuição equilibrada dos valores de conversão garante que o seu esquema de SKAN capture o comportamento do usuário de forma eficaz. Valores de conversão não utilizados significam combinações de mensuração mal aproveitadas, causando desperdício e perda de oportunidades de otimização.

* Exibe a frequência de cada valor de conversão nos últimos 7 dias de postbacks.
* Destaca valores que receberam 0 postbacks.
* Ajuda a otimizar a alocação de valores e evitar o desperdício de capacidade de mensuração.
* Especialmente útil para aplicativos que usam esquemas baseados em prioridade.

**Limite para identificar valores não usados**  
✅ Todos os CVs são usados  
⚠️ Se pelo menos um CV não tiver nenhum postback, este símbolo de erro será exibido.

<div id="revenue-tab" />

#### **Receita**

Verifique se os buckets de receita definidos correspondem ao gasto real dos usuários.

A precisão da receita pode ser melhorada otimizando os intervalos de receita predefinidos da SKAN. A SKAN relata o valor médio de cada intervalo, o que pode não refletir os gastos reais do usuário. Intervalos desalinhados geram discrepâncias, levando ao reporte de receita impreciso e afetando o ROAS e a alocação de orçamento.

O gráfico exibe a distribuição dos usuários pagantes entre os buckets de receita definidos. Quando há uma discrepância entre o gasto real dos usuários e a receita média por usuário pagante (ARPPU) informada, é fornecida uma recomendação para revisar o esquema.

* Mostra se o seu esquema inclui mapeamento de receita.
* Mostra como os usuários pagantes estão distribuídos entre faixas de receita.
* Identifica discrepâncias entre a receita média por usuário pagante (ARPPU) e o gasto real.
* Sugere atualizações no esquema para melhorar a precisão da receita.
* Se o seu aplicativo estiver qualificado para o Modelo de Recomendação de Receita, também será exibido um cálculo personalizado da precisão do ARPPU com base no seu esquema.

**Limite para erro de reportar**

✅ Erro de receita ≤ 3%

⚠️ Erro de receita > 3%

<div id="events-tab" />

#### **Aba Eventos**

Verifique se os eventos mapeados para SKAN ocorrem com frequência suficiente para gerar valor.

Esta aba mostra se pelo menos um evento in-app está mapeado para SKAN.

O gráfico mostra a porcentagem de instalações que acionaram cada evento mapeado durante a primeira janela de atividade. Eventos com baixa frequência ou sem ocorrência são destacados, ajudando você a garantir o uso otimizado do seu esquema de conversão.

Garantir que todos os eventos selecionados ocorram na primeira janela de atividade evita capacidade de mensuração não utilizada e ajuda a aproveitar ao máximo os valores de conversão disponíveis.

* Aparece se pelo menos um evento estiver mapeado no esquema.
* Fica oculto se nenhum evento mapeado tiver registrado instalações nos últimos 7 dias.
* Exibe a porcentagem de instalações que acionaram cada evento mapeado durante a primeira janela de atividade.
* Destaca eventos que ocorrem raramente ou não ocorrem.
* Ajuda a evitar eventos subutilizados que desperdiçam o potencial do esquema.

**Limite para frequência de eventos**

✅ Todos os eventos ≥ 3 % das instalações

⚠️ Um ou mais eventos &lt; 3 %

</Accordion>

</Accordion>

<div id="additional-procedures" />

## Procedimentos adicionais

<div id="change-skan-measurement-mode" />

<Accordion title="Alterar o modo de medição SKAN">

Considere:

* Após começar a usar o modo de medição SKAN 4, não é aconselhável regressar a um modo anterior.
* Quando altera as definições, estas passam a vigorar a partir das 00h00 UTC, iniciando um período de transição. Durante este período, descodificamos o valor de conversão com base nas definições mais recentemente selecionadas. Contudo, um postback que chega agora refere-se a uma instalação que aconteceu em algum momento no passado.
* O número de instalações reportado não está afetado pela alteração das definições e é exato.

</Accordion>

<div id="disable-skan-measurement" />

<Accordion title="Desativar a medição SKAN">

Para desativar a medição SKAdNetwork:

1. No AppsFlyer, aceda a **Definições** > **SKAN Conversion Studio.**
2. Clique em ⋮.
3. Desative a **medição SKAdNetwork.**   
   Entre outras ações, o SDK deixa de chamar funções SKAN como *registerAppForAdNetworkAttribution*, *updateConversionValue.*
4. Clique em **Guardar alterações.**

</Accordion>

<div id="report-events-by-servertoserver-api" />

<Accordion title="Reportar eventos via API servidor a servidor">

![SKAdNetwork_-_S2S__2_.png](https://files.readme.io/ed55e5c10184afcc27ce7e414a3213f69d2c20bd70d38f78be338f1b17254ee2-16281446657937.png)

Tanto o SDK quanto a <Anchor target="_blank" href="/marketers/pt/docs/server-to-server-events-api-for-mobile-s2s-mobile">API servidor a servidor (S2S)</Anchor> podem enviar eventos na app para os servidores da AppsFlyer.

O fluxo S2S é da seguinte forma:

* Ocorre um evento relacionado ao utilizador nos servidores do anunciante. A aplicação pode estar aberta ou fechada nesse momento.
* Os servidores do anunciante reportam o evento à AppsFlyer via S2S.
* A AppsFlyer calcula o valor de conversão atualizado e, em seguida:
  * Se a aplicação estiver aberta no dispositivo do utilizador, o SDK é notificado sobre o valor atualizado. O SDK atualiza o valor de conversão do iOS no dispositivo.
  * Se a aplicação não estiver aberta no dispositivo do utilizador, o servidor espera até que a aplicação seja aberta para notificar o SDK sobre o valor da conversão. Isto deve ocorrer antes da expiração do prazo da Janela de Atividade. Se a notificação falhar, o evento é desconsiderado.

**Versão do SDK necessária**

* Adote a versão mais recente do SDK na aplicação. **Nota!** Não é necessária qualquer ação adicional por parte do desenvolvedor.

**Para implementar o envio de eventos na aplicação pela API de servidor para servidor:**

1. Faça uma das seguintes opções:
   * Se o modo selecionado for SKAN 4 ou Personalizado:
     * Nenhuma alteração nas definições é necessária.
   * Se o modo selecionado for receita, conversão ou envolvimento:
     1. No AppsFlyer, aceda a **Definições** > **SKAN Conversion Studio.**
     2. Clique em opções (⋮).
     3. Ative a opção **Registar eventos na aplicação enviados pela API de servidor para servidor**.
2. Envie eventos por S2S.

**Limitação**

* Se implementar *anonimização do utilizador* para um determinado utilizador, não poderá enviar eventos por S2S para esse utilizador.

</Accordion>

<div id="add-ssot-to-fixed-mode-measurements" />

<Accordion title="Adicione SSOT às medições de modo fixo">

<div id="note-2" />

> 📘 **Nota**
>
> Os modos fixos não estarão disponíveis para novas aplicações a partir de 23/06/2024. Todas as funcionalidades são suportadas nos modos Custom e SKAN4.

Se tiver configurado o modo de medição de Receita ou Envolvimento, a Fonte Única da Verdade (SSOT, que desduplica e reporta com precisão os dados do iOS) não é suportada. <Anchor target="_blank" href="/marketers/pt/docs/single-source-of-truth-ssot-guide-for-ios-attribution">Saiba mais sobre o SSOT</Anchor>

**Para ativar o SSOT quando o modo Receita ou Envolvimento estiver configurado**:

1. Na AppsFlyer, aceda a **Definições** > **SKAN Conversion Studio**.
2. Desça até ao seu modo de medição ativo.
3. Clique em **+ Adicionar Fonte Única da Verdade**.
   * A alternância da Fonte Única da Verdade é ativada automaticamente.
   * As gamas de medição no modo fixo são minimamente alteradas para permitir ao SSOT algum espaço no valor de conversão.
4. Clique em **Guardar.**

<div id="conversion-value-decrease" />

<Accordion title="Diminuição do valor de conversão">

No modo [SKAN 4](/docs/skan-conversion-studio#skan-4), tem a capacidade de aumentar ou diminuir o valor de conversão (CV). Por defeito, o CV está configurado para aumentar. Ao permitir que os valores de conversão diminuam, o postback incluirá o valor mais recente na janela ao enviar uma receita negativa, mesmo que anteriormente fosse superior. Esta funcionalidade é relevante para valores de conversão detalhados e gerais em todas as [três janelas.](/docs/skan-conversion-studio#measurement-principles-and-definitions)   
**Nota:** O valor da receita publicitária nunca será negativo.

Para permitir a diminuição do valor de conversão:

1. Na AppsFlyer, aceda a **Definições** > **SKAN Conversion Studio**.
2. Selecione o modo de medição **SKAN 4.0**.
3. Clique nas opções (⋮) para abrir o menu de opções e:
   * Certifique-se de que a opção **Permitir redução de conversão** está ativada.   
     Atenção! Isto estará disponível apenas para:
     * Aplicações previamente guardadas no modo SKAN 4 no Conversion Studio.
     * Usuários com acesso de edição

<div id="examples" />

#### Exemplos

**Exemplos com receita negativa**

| CVs | Resultados | Evento na app |
| --- | --- | --- |
| 3 | 20 USD - 30 USD |  |
| 2 | 10 USD - 20 USD | af\_add\_to\_cart |
| 1 | 0 USD - 10 USD |  |
| 0 | NA | instalação |

**Exemplo 1**

O utilizador fez uma compra de 5 dólares – verá um aumento para o CV 1  
Depois, o utilizador fez uma compra de 20 dólares – verá um aumento para o CV 3  
O utilizador fez uma compra de -10 dólares — verá uma diminuição para o CV 1  
Em seguida, o utilizador realizou um evento de adicionar ao carrinho – verá um aumento para o CV 2

**Exemplo 2**

O utilizador fez uma compra de 25 dólares – verá um aumento para o CV 3  
O utilizador acionou o evento af\_add\_to\_cart – permanecerá no CV 3  
O utilizador fez uma compra de -20 dólares – verá uma diminuição para o CV 1

**Exemplo de esquema na app**

| CVs | Evento na app |
| --- | --- |
| 3 | af\_compra |
| 2 | af\_add\_to\_cart |
| 1 | sessão |
| 0 | instalação |

**Exemplo**

O utilizador realizou um evento de sessão - verá um aumento para o CV 1  
Depois, o utilizador realizou um evento de compra - verá um aumento para o CV 3  
O utilizador realizou mais um evento de sessão - permanecerá no CV 3

</Accordion>

<div id="support-anonymized-users" />

<Accordion title="Suporte a Utilizadores Anônimos">

Ativar a opção **Suporte a utilizadores anónimos** assegura que os valores de conversão SKAN são atualizados corretamente para <Anchor target="_blank" href="/marketers/pt/docs/apply-privacy-preserving-sdk-methods#como-anonimizar-informações-do-usuário">utilizadores anonimizados</Anchor>, enquanto ainda protege a sua privacidade.

<div id="important-1" />

> 🚧 **Importante!**
>
> Esta funcionalidade é relevante apenas para apps que utilizam o <Anchor target="_blank" href="/marketers/pt/docs/apply-privacy-preserving-sdk-methods#como-anonimizar-informações-do-usuário">método de anonimização do utilizador</Anchor> para remover e fazer hash de todas as informações que identificam o utilizador. Para assegurar relatórios precisos do SKAN, estas apps devem ativar a opção **Suporte a utilizadores anónimos**.

Por que é necessário?  
O SKAN utiliza identificadores para atualizar os valores de conversão com base na atividade após a instalação. Quando uma app utiliza o **método de anonimização do utilizador** após chamar o método de início, o sistema pode não conseguir associar alguns eventos pós-instalação à instalação original, resultando em atualizações imprecisas dos valores de conversão.  
Ao ativar a opção **Suporte a utilizadores anónimos**, o sistema cria identificadores com hash para todos os utilizadores no momento da instalação. Isso permite que a app associe corretamente a atividade do utilizador à instalação original, mesmo que o utilizador venha a ser anonimizado posteriormente, garantindo relatórios precisos.

</Accordion>

</Accordion>

<div id="ssot-mapping-patterns" />

<Accordion title="Padrões de mapeamento do SSOT">

Quando o Single Source of Truth (SSOT) estiver habilitado no seu esquema SKAN, você poderá configurar como os valores de conversão são estruturados. Isso permite um melhor alinhamento com seus objetivos de relatórios e necessidades estratégicas de atribuição.

Os padrões de mapeamento definem como os valores de conversão (CVs) são organizados para representar diferentes tipos de instalações. Isso inclui instalações atribuídas pelos métodos clássicos de atribuição da AppsFlyer e instalações não atribuídas.  
A AppsFlyer oferece suporte a dois padrões de mapeamento:

<div id="half-and-half" />

#### **Meio a meio**

* Divide os CVs em duas metades:
  * A metade inferior representa níveis crescentes de engajamento.
    * Lógica: CVs com `af_attribution_flag=false`
  * A metade superior duplica a metade inferior, mas marca explicitamente os valores como atribuídos pelos métodos clássicos de atribuição da AppsFlyer.
    * Lógica: Duplicatas dos CVs inferiores com `af_attribution_flag=true`

<div id="pairing" />

#### **Emparelhamento**

* Agrupa os CVs em pares.
  * Cada CV é seguido imediatamente por outro que representa o mesmo nível de engajamento, mas é explicitamente marcado e atribuído por atribuição clássica.
  * Garante a ordem crescente dos CVs e representa consistentemente níveis crescentes de engajamento do usuário
  * Lógica: Cada CV é seguido por sua duplicata marcada com `af_attribution_flag=true`

<div id="how-to-configure-mapping-patterns" />

#### Como configurar padrões de mapeamento

Para usar padrões de mapeamento:

1. Habilite o SSOT no seu esquema SKAN.
2. No editor de esquema, clique no menu **Mais opções** (três pontos).
3. Selecione **Padrão de mapeamento**.
4. Escolha seu padrão preferido:
   * **Meio a meio** (padrão)
   * **Emparelhamento**
5. Revise a prévia atualizada do esquema e a visualização de calendário.
6. Salve seu esquema.

<div id="faq" />

#### **Perguntas frequentes**

**P: O que acontece se o SSOT estiver desativado?**  
R: O seletor do padrão de mapeamento fica indisponível quando o SSOT está desativado.

**P: Posso voltar ao padrão padrão?**  
R: Sim. **Meio a meio** é o padrão e pode ser selecionado novamente a qualquer momento.

**P: Essas alterações são refletidas nas APIs de esquema?**  
R: Sim. Todos os padrões selecionados são refletidos nas APIs de esquema do SKAN para profissionais de marketing e networks.

**P: Dois CVs podem ter o mesmo evento, mas flags de SSOT diferentes?**  
R: Sim. Agora isso é considerado um comportamento válido segundo a lógica de validação atualizada.

</Accordion>

<div id="specifications-and-limitations" />

<Accordion title="Especificações e limitações">

| Especificações | Observações |
| --- | --- |
| Agências | As agências têm <Anchor target="_blank" href="/partners/pt/docs/getting-started-agency-onboarding#acesso-ao-skan-conversion-studio">acesso limitado ao SKAN Conversion Studio dos anunciantes</Anchor>. |
| Valores aproximados | <ul><li>Até 10 componentes de medição.</li><li>Ao utilizar mais de uma medição, todos os eventos devem ocorrer para que o valor seja codificado.</li></ul> |
| Eventos orgânicos in-app | No SKAN 4, nos modos Personalizado e de Descodificação, as métricas orgânicas para eventos in-app e receita total não estão disponíveis. |
| Dados ambíguos | Após alterar a configuração do SKAN nas próximas 48 a 72 horas, os dados no painel de controlo e nos relatórios de dados brutos são ambíguos. Devido a problemas com o temporizador do iOS, não é certo se a configuração utilizada para descodificar os postbacks coincide com a configuração utilizada para os codificar anteriormente. |
| Restrições de geolocalização | Usuários cujo acesso é limitado a canais de mídia e geolocalizações específicos talvez não consigam ver nem acessar o SKAN Conversion Studio. |

</Accordion>

<div data-zendesk-anchors="skan-conversion-studio-basics=conceitos-b%C3%A1sicos-do-skan-conversion-studio 01H7Z08MFDASBCBJD18QTXYSXK=conceitos-b%C3%A1sicos-do-skan-conversion-studio 01H7Z08MFDX3VYJTSWXQ5HQ7BZ=measurement-principles-and-definitions s2s-principles=princ%C3%ADpios-s2s 01H7Z08MFDWRGVNXB62Z6CT1G7=princ%C3%ADpios-s2s setting-up-conversion-values-in-skan-conversion-studio=configura%C3%A7%C3%A3o-de-valores-de-convers%C3%A3o-no-skan-conversion-studio 01H7Z08MFDB76C6Z5SSXHFT71P=configura%C3%A7%C3%A3o-de-valores-de-convers%C3%A3o-no-skan-conversion-studio 01H7Z08MFDEAYHJAG9XA2TGBWV=importante 01H7Z08MFD7VY1QP85W0YPK8RC=skan-4 01H7Z08MFD3SWVZK68K45NYDP8=custom 01H7Z08MFDZ1EKDQNZWGF7DHK9=fixed-modes h_01J14HX28C9TFDP0MDRYWFV6Q3=nota fixed-mode-measurement=medi%C3%A7%C3%A3o-em-modo-fixo 01H7Z08MFDAYVJKJBT08R82N26=medi%C3%A7%C3%A3o-em-modo-fixo 01H7Z08MFDCJGZGQR2JR4WQVHR=decode measurement-components=componentes-de-medi%C3%A7%C3%A3o 01H7Z08MFDFE345QWHF77RGTD7=componentes-de-medi%C3%A7%C3%A3o 01H7Z08MFE5G01NGY5EFTAW93M=single-source-of-truth 01H7Z08MFERDJHSD8NT5KN7DKN=inapp-event-component 01H7Z08MFETMGAE67X499V4092=revenue-component 01H7Z08MFEQG2HRJBWBYFTW3ZK=funnel-component 01H7Z08MFE22J8DDBDNJ18KBEJ=priority-measurement-component 01H7Z08MFES844SS08HS17Y29R=lock-window 01H7Z08MFE61QCC0MZW5RJ910B=activity-window additional-information=informa%C3%A7%C3%B5es-adicionais 01H7Z08MFET64PSAVMREQ4HP4S=informa%C3%A7%C3%B5es-adicionais 01H7Z08MFEKP9WNGJD2GBVKB0P=view-cv-mapping csv-mapping-file-columns=colunas-do-ficheiro-de-mapeamento-csv 01H7Z08MFETCB428W1TXTH2HJ8=colunas-do-ficheiro-de-mapeamento-csv 01H7Z08MFE5CBQK024CF8FARJ9=conversion-value-capacity-formula 01H7Z08MFETZVQSNWX639E56SK=maximized-custom-cv-examples example-1=exemplo-1 01H7Z08MFEXME7RV67XTZRDWJE=exemplo-1 example-2=exemplo-2 01H7Z08MFEHRF4656X5AR301D8=exemplo-2 example-3=exemplo-3 01H7Z08MFEK0725CN35TP3MPYT=exemplo-3 example-4=exemplo-4 01H7Z08MFES7W3EF2JJ8B75K99=exemplo-4 01H7Z08MFF2JXA0BFNKCW3ZCZ7=priority-measurement-detailed-example measurement-priorities-setting-example=exemplo-de-configura%C3%A7%C3%A3o-de-prioridades-de-medi%C3%A7%C3%A3o 01H7Z08MFFXAAC37MBV0ES6ADQ=exemplo-de-configura%C3%A7%C3%A3o-de-prioridades-de-medi%C3%A7%C3%A3o user-journey-scenarios=cen%C3%A1rios-de-explora%C3%A7%C3%A3o-do-utilizador 01H7Z08MFFJ9TQMH0Q93B7N1A8=cen%C3%A1rios-de-explora%C3%A7%C3%A3o-do-utilizador 01H7Z08MFFNBXECB8A5Y0KH9C8=fixed-mode-examples h_01JJH6WZY2QMKAR1C7B5JTMMKE=nota-1 example-a-revenue-measurement=exemplo-a-medi%C3%A7%C3%A3o-de-receita 01H7Z08MFFVKZN3Y2R1ZEVEW4D=exemplo-a-medi%C3%A7%C3%A3o-de-receita example-b-conversion-measurement=exemplo-b-medi%C3%A7%C3%A3o-de-convers%C3%A3o 01H7Z08MFFNBA5786R5XZDA5FG=exemplo-b-medi%C3%A7%C3%A3o-de-convers%C3%A3o inapp-events-performed-by-users=eventos-na-aplica%C3%A7%C3%A3o-realizados-pelos-utilizadores 01H7Z08MFFA7C6HWQPADZXQQNC=eventos-na-aplica%C3%A7%C3%A3o-realizados-pelos-utilizadores inapp-related-metrics-available=m%C3%A9tricas-relacionadas-com-eventos-dentro-da-aplica%C3%A7%C3%A3o-dispon%C3%ADveis 01H7Z08MFF1PEE91J5CJN1GC7V=m%C3%A9tricas-relacionadas-com-eventos-dentro-da-aplica%C3%A7%C3%A3o-dispon%C3%ADveis example-c-engagement-measurement=exemplo-c-medi%C3%A7%C3%A3o-de-envolvimento 01H7Z08MFF8V718C23PQ2NG3C3=exemplo-c-medi%C3%A7%C3%A3o-de-envolvimento app-opens=aberturas-da-aplica%C3%A7%C3%A3o 01H7Z08MFF4PRHSR8NCJ1Q78WM=aberturas-da-aplica%C3%A7%C3%A3o 01H7Z08MFFVS6MYC9EB3KP0H2Y=skan-conversion-studio-api h_01K15P5NJ4CGSH4YR9JXD93PD9=skan-schema-analysis conversion-values-tab=valores-de-convers%C3%A3o h_01K15P7QQSDHNY1ZN3FC37XTHP=valores-de-convers%C3%A3o revenue-tab=receita 01K15PMAQGDZ4SFKEERXVRR0C2=receita events-tab=aba-eventos 01K15PZK56TVQ6WHGYCA54AA4Q=aba-eventos additional-procedures=procedimentos-adicionais 01H7Z08MFFPZ4GKM5GFMAE2HDJ=procedimentos-adicionais 01H7Z08MFFPKCX5TFQQTMYJEGW=change-skan-measurement-mode 01H7Z08MFF78F9NMWJATYE2YFE=disable-skan-measurement 01H7Z08MFFD4T3D71A6R9K83A3=report-events-by-servertoserver-api 01H7Z08MFFFAEW6NP0YAX773B3=add-ssot-to-fixed-mode-measurements h_01JJH6WZY2R2H1F9ZBGTR0FDNM=nota-2 h_01HKVT9N2KFJQGCWVMGP59YWRH=conversion-value-decrease examples=exemplos h_01HM3C8BEG5Z7ZRY12MF3Q4W4K=exemplos 01JCWF4HM4KKB0WC8MN00SV4XK=support-anonymized-users 01JCWFY9RZ7JSC63TVBTPRCYHH=importante-1 h_01JRFAN7GT7K18ADDAYGVQ4GGT=ssot-mapping-patterns half-and-half=meio-a-meio h_01JRFB0793MK8H75T7CGTNPDCK=meio-a-meio pairing=emparelhamento h_01JRFB1B9A44CRYVBRTK4CRQGP=emparelhamento how-to-configure-mapping-patterns=como-configurar-padr%C3%B5es-de-mapeamento h_01JRFBAGEZP2GT3XZW4RT255M3=como-configurar-padr%C3%B5es-de-mapeamento faq=perguntas-frequentes h_01JRFBBYER8QMW5XMBBCWFGDP1=perguntas-frequentes 01H7Z08MFFG9EQFVEKN3AXE9DD=specifications-and-limitations" />
