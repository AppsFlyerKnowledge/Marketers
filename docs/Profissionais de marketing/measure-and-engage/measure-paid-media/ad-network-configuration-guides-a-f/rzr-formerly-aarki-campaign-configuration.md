---
title: Configuração da campanha da RZR (anteriormente Aarki)
metadata:
  keywords:
    - Advertisers
    - aarki
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2018-03-12T06:15:54Z'
  edited_at: '2026-09-10T00:24:15Z'
  id: 360000423105
  locale: pt
  section: Ad network configuration guides (A-F)
  section_id: 6551990971793
  url: https://support.appsflyer.com/hc/pt/articles/360000423105
---
> **Visão geral:** RZR, um parceiro integrado de ad network da AppsFlyer, é uma DSP mobile bem conhecida. RZR oferece atribuição mobile baseada em cliques e view-through. Além disso, RZR também oferece retargeting baseado em cliques, que você pode acompanhar com a AppsFlyer.

<Image align="center" alt="Logotipo horizontal da RZR com gradiente preto (3).png" src="https://files.readme.io/b1064bdec0e836399c583c3f55e5e79a81380a9a8d86eeaee19391b6d09f2bbd-small-46161100230545.png" width="58.83%" />

<div id="setting-up-rzr" />

## Configurando a RZR

**Pré-requisito:** antes de configurar a integração, certifique-se de [entrar em contato com o parceiro](#) e abrir uma conta com ele. Antes de criar uma integração, certifique-se de <Anchor target="_blank" href="/marketers/pt/docs/partner-integrations#contact-details">entrar em contato com o parceiro</Anchor> e abrir uma conta com ele.

**Para ativar a integração:**

1. Na aba **Integração**, habilite **Ativar parceiro**.  
   **Para editar**: **Na AppsFlyer, vá para o menu lateral e selecione** Colaborar **>** **Integrações ativas**.
2. Selecione o aplicativo correspondente.
3. Na aba **Integração**, selecione o aplicativo e clique em **Ativar parceiro**.
4. Na **primeira visita** aqui, você precisará ativar a opção ***Ativar parceiro*** para habilitar a configuração dos parâmetros de integração. A opção **deve** permanecer ativada enquanto você trabalhar com o parceiro.  
      
   Para obter mais detalhes sobre a ativação do parceiro, clique <Anchor target="_blank" href="/marketers/pt/docs/partner-activation-deactivation">aqui</Anchor>.
5. Complete a configuração utilizando as abas relevantes, conforme descrito abaixo. Para obter uma descrição detalhada do header da Janela de Configuração de Parceiros, clique <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#about-the-integrated-partner-page">aqui</Anchor>.

<div id="integration-tab" />

<Accordion title="Aba Integração">

<div id="activate-partner" />

### Ativar parceiro

<span id="01ECJ9TJKEFXN53XDEBJ5Z92SS"></span>Em seu **primeiro acesso**, você precisará ativar o botão ***Ativar parceiro*** para habilitar a configuração dos parâmetros da aba de integração. O botão DEVE estar ATIVADO enquanto você trabalhar com o parceiro. Para mais informações sobre a ativação de parceiros, por favor clique <Anchor target="_blank" href="/marketers/pt/docs/user-level-data-retention"><span id="01ECJ9TJKFY5Q8P4QS57HD44T3"></span>aqui</Anchor>.

<div id="note" />

> 📘 **Nota**
>
> Como uma network all-installs, a RZR prefere receber postbacks para todas as novas instalações do seu aplicativo a partir de QUALQUER fonte, inclusive orgânica. Recomenda-se selecionar **Eventos atribuídos a qualquer parceiro** para enviar todos os postbacks de instalação à RZR.

<div id="general-settings" />

### Configurações gerais

<span id="01ECJ9TJKF9QBT98Z7XJM3H8F1"></span>**ID do parceiro**

<span id="01ECJ9TJKF6R5F2K8VGMR7KFHN"></span>A RZR se conecta à AppsFlyer por meio de um ID de network exclusivo. Se você ainda não tiver o ID da network, deverá obtê-lo com a RZR para continuar com a integração.

<span id="01ECJ9TJKFZN0WVXXS0B89CMBY"></span>**Habilitar a atribuição de view-through**

<span id="01ECJ9TJKFE4E8GZQ2EN3Z1SM4"></span>Alterne para LIGADO se quiser atribuir instalações view-through da RZR. O cursor de lookback de view-through está disponível na aba do link de atribuição (conforme descrito abaixo).

<div id="default-postbacks" />

### Postbacks padrão

<span id="01ECJ9TJKFT13WB1T328ET3PGC"></span>Envie postbacks automáticos para a RZR após instalações e reengajamentos do usuário. Use esta seção para definir a **origem dos usuários** que permitem o envio desses postbacks.

<span id="01ECJ9TJKFQH37DQZ3V3NAESRF"></span>Selecione **Somente eventos atribuídos a este parceiro** para eventos provenientes apenas de usuários atribuídos à RZR. Selecione **Eventos atribuídos a qualquer parceiro ou orgânico** para ter toda a sua base de usuários disponível para ser reportada à RZR.

<div id="in-app-events-settings" />

### Configurações de eventos in-app

<span id="01ECJ9TJKF6QKF23NRTA5VS8Y9"></span>Nesta seção, você pode mapear os eventos da AppsFlyer com a RZR por meio de postbacks.

**Para configurar os postbacks de eventos na aplicação:**

1. Ative **postbacks de eventos in-app.**
2. Clique em **Adicionar evento** para incluir um SDK ou evento de servidor para servidor. A tabela a seguir descreve os campos a serem preenchidos:

| Nome do parâmetro | A descrição |
| --- | --- |
| **Evento na AppsFlyer** | O nome do evento, conforme recebido pela AppsFlyer do SDK integrado no aplicativo ou de eventos de servidor para servidor.<br />**Dica**: não encontrou o evento que está procurando?<ul><li>Certifique-se de ativar o evento em um dispositivo com uma instalação não orgânica e verifique novamente.</li><li>Digite-o em **Evento AppsFlyer**, depois clique em **Criar personalizado**. Saiba mais sobre o <Anchor target="_blank" href="/marketers/pt/docs/in-app-event-postback-configuration#eventos-personalizados">mapeamento de eventos personalizados</Anchor>.</li></ul> |
| **Mapeado para evento do parceiro** | O nome exclusivo ou ID de cada evento, conforme definido pelo parceiro. As configurações de mapeamento possíveis são:<ul><li>**Campo de texto:** obtenha o ID de evento correspondente do parceiro.</li><li>**Menu suspenso:** selecione o AppsFlyer event pré-definido mais adequado</li><li>**Sem alterações**: envie os eventos como eles estiverem, sem o mapeamento de nomes.</li></ul> |
| **para utilizadores de** | Selecione a opção de envio para o evento:<ul><li>**Apenas este parceiro**: Envie postbacks apenas quando este evento for atribuído a este parceiro.</li><li>**Todas as fontes de mídia, incluindo orgânicas:** Envie postbacks para eventos atribuídos a qualquer parceiro, assim como eventos orgânicos.</li></ul> |
| **Incluindo** | <ul><li>**Nenhum dado (padrão)**: envia apenas o evento em si sem nenhum valor de evento.</li><li>**Valores e receita**: envia todos os parâmetros do evento, **incluindo** o valor da receita (se existir no evento).</li><li>**Valores sem receita**: envia todos os parâmetros **excluindo** o valor da receita.</li></ul> |

3. [Opcional] Clique no ícone **Adicionar condição**<Image alt="conditional-iae-postbacks-icon.png" src="https://files.readme.io/575c9ab0dd82a125319591072b17604a7f9d1b71fff6baff4124d99edc1a7fc7-16570673855121.png" width="30px" /> para <Anchor target="_blank" href="/marketers/pt/docs/in-app-event-postback-configuration#postbacks-condicionais-de-eventos-in-app">definir condições</Anchor> para um evento.
4. Clique em **Guardar integração**.
5. [Opcional] Após guardar a integração, permanecendo na página de configuração, pode integrar mais das suas aplicações com o parceiro:
   1. No canto superior esquerdo, embaixo do nome do parceiro, clique no nome do aplicativo para abrir a lista de apps.
   2. Selecione um aplicativo diferente na lista suspensa.
   3. Repita as <Anchor target="_blank" href="/marketers/pt/docs/amazon-ads-campaign-configuration#integration-tab">etapas de integração</Anchor> para o aplicativo selecionado.

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Separador de Links de Atribuição">

<span id="01ECSMR3VTP3SVSP9YXGW526PA"></span>Nesta guia, você pode criar os links de atribuição que deseja enviar à RZR para atribuir as campanhas, conjuntos de anúncios ou até mesmo anúncios individuais da RZR. Observe que a AppsFlyer NÃO salva seus links de atribuição gerados pelo parceiro.

<span id="01ECJ9TJKFTGNEZ68AR6DGXJNA"></span>Essa guia está dividida em diferentes seções:

<div id="attribution-link-parameters" />

### Parâmetros de link de atribuição

<span id="01ECJ9TJKFJRJ2BYN069CK80C8"></span>Nesta seção, selecione quais parâmetros você deseja adicionar ao link de atribuição.

<span id="01ECJ9TJKG144FJ8R72S2XDKQS"></span>A adição de parâmetros ao link de atribuição aqui permite que você realize análises de detalhamento completas mais tarde. Os parâmetros que já estão definidos no link de atribuição podem ser editados adicionando-os junto com seus novos valores aqui.

* <span id="01ECJ9TJKGTPN4NF8CC66XBRRS"></span>**<span id="01ECJ9TJKGZP0D1TYCB5R8XJ80"></span>Campanha** - adicione-a para comparar diferentes campanhas em execução com Aarki. **Parâmetro de link de atribuição:** c
* <span id="01ECJ9TJKGSVH0XGW2R8HRDA4T"></span>**Conjunto de anúncios** - defina nomes de conjuntos de anúncios para comparar diferentes conjuntos de anúncios em campanhas específicas da Aarki. **Parâmetro de link de atribuição:** af\_adset
* <span id="01ECJ9TJKGC25XCE8GEB04ZE0P"></span>**Nome do anúncio** - defina nomes de conjuntos de anúncios para comparar diferentes criativos em conjuntos de anúncios específicos dentro de campanhas específicas da Aarki. **Parâmetro do link de atribuição:** af\_ad
* <span id="01ECJ9TJKGWG1QBKJ9MVW4Q5FG"></span>**ID do site** e **ID do subsite** - defina o parâmetro de ID do site para atribuir instalações a publishers específicos. Caso existam muitos publishers, aconselhamos limitar o número de IDs do site usados e usar o parâmetro de ID do subsite, para evitar <Anchor target="_blank" href="/marketers/pt/docs/measure-exceeded-dimensions-and-cardinality-limits#exceeded_siteid_limit"><span id="01ECJ9TJKGEPHEXZ60NAN9JPWG"></span>exceder as limitações de ID do site</Anchor>. **Parâmetros do link de atribuição:** af\_siteid e af\_sub\_siteid
* <span id="01ECJ9TJKGQPS0GAY5SY562VFS"></span>**Parâmetros de assinante** - use qualquer um dos 5 parâmetros de assinante para inserir valores úteis. Observe que esses parâmetros são analisados e aparecem no relatório de dados brutos, o que os torna muito úteis para realizar agregação ou filtragem de dados. **Parâmetros do link de atribuição:** af\_sub1, af\_sub2, af\_sub3, af\_sub4, af\_sub5

<span id="01ECJ9TJKGQN0Y1H6F2WNHRBCV"></span>Adicione qualquer outro parâmetro ao link de atribuição, basta digitá-lo em uma nova caixa de parâmetro. Para mais informações <Anchor target="_blank" href="/marketers/pt/docs/about-link-structure-and-parameters">**<span id="01ECJ9TJKG3AQCMW2FDDZ7HWWB"></span>sobre a estrutura e os parâmetros do link de atribuição da AppsFlyer**</Anchor>.

<div id="retargeting-settings" />

### Configurações de retargeting

<span id="01ECJ9TJKG820HKXXZTS89ES65"></span>Quando ativado, o AppsFlyer reconhece um link como um link de atribuição de <Anchor target="_blank" href="/marketers/pt/docs/retargeting-attribution-guide"><span id="01ECJ9TJKGRTSNR53S5XX76K61"></span>retargeting</Anchor>, em vez de um link de aquisição de usuários, ao adicionar &is\_retargeting=true ao link de registro de cliques. Observe que, atualmente, o retargeting é compatível apenas com atribuição click-through e não com atribuição view-through.**Parâmetro do link de atribuição:** is\_retargeting.

<span id="01ECJ9TJKGPRH6P36208EH0C44"></span>O exemplo a seguir abaixo é exibido quando o retargeting está ativado.

<span id="01ECJ9TJKH63B6KS5WE93F0SMM"></span>1. Link padrão vs. OneLink

<span id="01ECJ9TJKHH7YZCNS0P0TT0B45"></span>Selecione a opção ***link de atribuição padrão*** se:

* <span id="01ECJ9TJKHCZFTSWGGC2XHW6N5"></span><span id="01ECJ9TJKHP90T48TJPV80AP2T"></span>Não for necessário realizar link direto com o URL ou
* <span id="01ECJ9TJKHYPT6RQ5NTVPV8FA2"></span>Planeja usar apenas <Anchor target="_blank" href="/marketers/pt/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#social-app-landing-page"><span id="01ECSNC07ND552HVWJD2GF8YSD"></span>esquemas de URI</Anchor> para deep linking

<span id="01ECJ9TJKH6GTCN390D87MYPHV"></span>Selecione ***Usar OneLink*** para:

* <span id="01ECJ9TJKHVJCE2XM6X6AJS4YY"></span><span id="01ECJ9TJKHSJAC8HW8YERAKDVC"></span>Usar um único link para aplicativos Android e iOS ou
* <span id="01ECJ9TJKH0W7PXF4EJKM20ZRQ"></span>Links diretos usando links universais ou do aplicativo

<span id="01ECJ9TJKHEDATPHFM1EN5NZFQ"></span>Observe que selecionar o OneLink altera o link de registro de cliques, de específico do aplicativo para uma <Anchor target="_blank" href="/marketers/pt/docs/onelink-guide"><span id="01ECJ9TJKHQTEYP3PPXHVWYF9V"></span>URL do OneLink</Anchor>.

<span id="01ECJ9TJKH59CKTD3ZNMZ37W09"></span>2. Deep Link URL

<span id="01ECJ9TJKHKQMJFN1Z3G7JTN5V"></span>Use este campo se o link se destinar a fazer deep linking de usuários para qualquer atividade específica no seu aplicativo.**Parâmetro do link de atribuição:** af\_dp. Você pode encontrar mais informações sobre a solução de Deep linking da AppsFlyer <Anchor target="_blank" href="/marketers/pt/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink"><span id="01ECJ9TJKHK7S19JDRMS3Z318C"></span>neste guia.</Anchor>

<span id="01ECJ9TJKH1QVW9NG1P4JY165N"></span>3. Janela de reengajamento

<span id="01ECJ9TJKHAZ5N1Y7NACJPMT4S"></span>Defina o período após o reengajamento, onde os eventos in-app do usuário são atribuídos à fonte de mídia de retargeting. Pode definir o valor em dias (1-90), horas (até 23) ou mesmo vitalício.

<span id="01ECJ9TJKH449C02X1Y3ESR48Y"></span>**Parâmetro do link de atribuição:** af\_reengagement\_window

<div id="click-through-attribution" />

### Atribuição de click-through

<span id="01ECJ9TJKHGWANE9EGZZ0KKEX9"></span>Essa barra deslizante permite definir o **tempo máximo entre o clique e a instalação**. Somente as instalações (primeiras inicializações) que ocorrerem dentro da janela de lookback podem ser atribuídas à RZR.

<span id="01ECJ9TJKHF1JQM37P7SAYP8G6"></span>**Parâmetro do link de atribuição:** af\_click\_lookback

<span id="01ECJ9TJKHY557S7J91YTE5VH8"></span>Mais detalhes sobre a <Anchor target="_blank" href="/marketers/pt/docs/set-up-lookback-windows"><span id="01ECJ9TJKHWEDC7RP2ZHHPFDNV"></span>janela de lookback de clique aqui</Anchor>.

<div id="click-attribution-link" />

### Clique no link de atribuição

<span id="01ECJ9TJKJ6TJBPEP5JNEPYTVB"></span>Este é o link de atribuição que contém todas as informações de configuração definidas para ele. Envie para a RZR para ser ativado quando os leads clicarem em um anúncio correspondente.

<div id="view-through-attribution-lookback-window" />

### Janela de retrospetiva da atribuição por visualização

<span id="01ECJ9TJKJVDX13ZVFH8T5BVG7"></span>Essa barra deslizante permite definir o **tempo máximo entre a impressão e a instalação**. Somente instalações (primeiras aberturas) que ocorrem dentro desta janela de lookback após uma impressão de anúncio são atribuídas à RZR, desde que não tenha havido nenhum outro clique em anúncio relevante.

<span id="01ECJ9TJKJ1JEA3HME63V9EWA0"></span>Você pode personalizar esse valor para 1 a 23 horas ou 1 a 7 dias.

<span id="01ECJ9TJKJB20VJH63A8NK3KGB"></span>**Parâmetro do link de atribuição:** af\_viewthrough\_lookback

<span id="01ECJ9TJKJNTQ7AJVYKVWYMJNZ"></span>Mais detalhes sobre a <Anchor target="_blank" href="/marketers/pt/docs/set-up-lookback-windows"><span id="01ECJ9TJKJX8GHDCAW0QQYD4BV"></span>atribuição view-through aqui</Anchor>.

<div id="impressions-attribution-link" />

### Link de atribuição para impressões

<span id="01ECJ9TJKJ34K4MSK1BK687Q9Y"></span>O link de atribuição de impressão contém dados de atribuição semelhantes ao link de gravação de clique (além da janela de lookback diferente). Envie-o à RZR para ser ativado quando um anúncio correspondente for assistido, normalmente por 1 segundo ou mais.

</Accordion>

<div id="cost-tab" />

<Accordion title="Aba de Custos">

A AppsFlyer obtém detalhes de custo por API. Consulte a <Anchor target="_blank" href="/marketers/pt/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api">tabela de integração de custos da ad network</Anchor> para obter informações completas sobre as dimensões, métricas e recursos compatíveis. **Observação:** Os dados de custo requerem uma assinatura do ROI360.

**Para ativar a Cost API**:

* Siga <Anchor target="_blank" href="/marketers/pt/docs/set-up-roi360-cost-api-to-measure-cost-data#enable-cost-api">essas instruções de integração</Anchor>.

<Anchor target="_blank" href="/marketers/pt/docs/set-up-roi360-cost-api-to-measure-cost-data#cost-api-status">Visualize o status da API de custo</Anchor> e a última vez que a AppsFlyer conseguiu extrair dados de custo correspondentes no painel de status de integração de custo (e receita de publicitária) ou no painel individual da ad network. 

<div id="warning" />

#### Atenção

<span id="01ECJ9TJKQX7K80360QJ9RACV1"></span>Após definir o custo da RZR, não altere o nome de nenhuma campanha em execução, conjunto de anúncios ou anúncio único, pois isso pode causar sérias discrepâncias ou a ausência de dados de custo.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Receita de anúncios">

<span id="01ECJ9TJKQNQBY77FTTFRZ0PGS"></span>Os dados de receita de anúncios não são compatíveis com a RZR.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Aba permissões">

<span id="01ECJ9TJKQ8FK7KPD84RHW11HQ"></span>Nessa aba, você pode selecionar as permissões a serem concedidas à RZR, independentemente de o parceiro atuar como uma ad network, agência ou até mesmo ambos. Observe que, mesmo que a atribuição esteja desativada para a RZR, a aba de permissões está ativa e você pode conceder controle à RZR.

<span id="01ECJ9TJKQFJM45QTAMC6AJQW3"></span>Use essas chaves seletoras a fim de conceder permissões à rede de anúncios para gerenciar sua própria configuração do aplicativo:

<div id="ad-network-permissions" />

### Permissões da rede de anúncios

* <span id="01ECJ9TJKQAHY9CZ2H3W09GQPZ"></span>***<span id="01ECJ9TJKQXT4HNE0HKH13F4SX"></span>Permitir a configuração da integração*** - permite que o parceiro configure a aba de integração (exceto postbacks de evento in-app)
* <span id="01ECJ9TJKQKZVDT6A960BMPW5Q"></span>***Permitir a configuração de postbacks de evento in-app*** – permite que o parceiro configure o mapeamento de postbacks de evento in-app para si mesmo na guia de integração
* <span id="01ECJ9TJKQYN16W3C8YYFM14XP"></span>***Permitir o acesso ao relatório de retenção*** – somente aos próprios dados de retenção do parceiro
* <span id="01ECJ9TJKQQSP4G7H71AZBQMXW"></span>***Permitir acesso aos dados agregados de usuário fiéis*** — apenas aos dados de usuários fieis do parceiro
* <span id="01ECJ9TJKQXG55YJGYJV9AZFNH"></span>***Permitir acesso aos dados agregados de eventos in-app** —* apenas aos dados de eventos in-app próprios do parceiro
* <span id="01ECJ9TJKQ9809CG0G2QK43RGQ"></span>***Permitir acesso aos dados agregados de receita*** — apenas aos dados da receita atribuídos ao parceiro
* <span id="01ECJ9TJKQZJGSVZMKFDHE2ACJ"></span>***Permitir o acesso ao painel Protect360*** – somente aos próprios dados do Protect360 do parceiro e desde que o recurso esteja ativado para o anunciante

<span id="01ECJ9TJKQJ0Y1QQK4EM92C06V"></span>Saiba mais sobre a concessão de <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#permissions-tab"><span id="01ECJ9TJKQZ5ADC4QSTHP0KN95"></span>permissões de ad networks</Anchor>.

<div id="01ECJ9TJKRMD549KXA59E682CH" />

<div id="agency-permissions" />

### Permissões da agência

<span id="01ECJ9TJKRNETK1FH4ZRSNE1V4"></span>Use essas chaves seletoras a fim de conceder permissões à agência para gerenciar sua própria configuração do aplicativo:

* <span id="01ECJ9TJKRADJZ8B7KNZH0HSQQ"></span>***<span id="01ECJ9TJKR3ZRZX5W0KD91BFV3"></span>Opção principal*** - defina como Ativada para revelar as opções de permissões da agência
* <span id="01ECJ9TJKRMQDVQV6EJAEC8DPG"></span>***Permitir a configuração de postbacks de evento in-app*** - permite que a agência configure o mapeamento de postbacks de evento in-app para si mesma na aba de integração
* <span id="01ECJ9TJKRF7NMH6E1NDZ57S0E"></span>***Permitir acesso a dados orgânicos agregados***
* <span id="01ECJ9TJKRKVWZG0WYVK1533A9"></span>***Permitir o acesso ao seu relatório de retenção*** - somente aos próprios dados de retenção da agência

<span id="01ECJ9TJKRS878CPXQYSBAJCA1"></span>Saiba mais sobre a concessão de <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#permissões-da-agência">permissões da agência</Anchor>.

</Accordion>

<div data-zendesk-anchors="setting-up-aarki=configurando-a-rzr h_01HJR5M5C0P759S4X5SSJCY501=configurando-a-rzr h_01J4KVYPZMZWJKV6KZQHNBZV0T=integration-tab activate-partner=ativar-parceiro 01ECJ9TJKE15MJE7WS26VP52A0=ativar-parceiro h_01J4KWRE6ECKEWEG4WP10N3BF7=nota general-settings=configura%C3%A7%C3%B5es-gerais 01ECJ9TJKFGQQVWA7SA3PRS690=configura%C3%A7%C3%B5es-gerais default-postbacks=postbacks-padr%C3%A3o 01ECJ9TJKF7G9KMGMGMAD414ZF=postbacks-padr%C3%A3o inapp-events-settings=configura%C3%A7%C3%B5es-de-eventos-in-app 01ECJ9TJKFWH38NKYPDEZR4FRV=configura%C3%A7%C3%B5es-de-eventos-in-app h_01J4KVYPZMF0CZMR1PTS97JNNJ=attribution-link-tab attribution-link-parameters=par%C3%A2metros-de-link-de-atribui%C3%A7%C3%A3o 01ECJ9TJKFD91X9DQXB8PV3840=par%C3%A2metros-de-link-de-atribui%C3%A7%C3%A3o retargeting-settings=configura%C3%A7%C3%B5es-de-retargeting 01ECJ9TJKGJF1FS642MEM6WX4A=configura%C3%A7%C3%B5es-de-retargeting clickthrough-attribution=atribui%C3%A7%C3%A3o-de-click-through 01ECJ9TJKHWMXAZYWNMVPDS8NY=atribui%C3%A7%C3%A3o-de-click-through click-attribution-link=clique-no-link-de-atribui%C3%A7%C3%A3o 01ECJ9TJKJ0EQE45TB9S0WS2ZB=clique-no-link-de-atribui%C3%A7%C3%A3o viewthrough-attribution-lookback-window=janela-de-retrospetiva-da-atribui%C3%A7%C3%A3o-por-visualiza%C3%A7%C3%A3o 01ECJ9TJKJ72AN26F2FQ8VVKQ4=janela-de-retrospetiva-da-atribui%C3%A7%C3%A3o-por-visualiza%C3%A7%C3%A3o impressions-attribution-link=link-de-atribui%C3%A7%C3%A3o-para-impress%C3%B5es 01ECJ9TJKJZV9PADNEETA6GFRZ=link-de-atribui%C3%A7%C3%A3o-para-impress%C3%B5es h_01J4KVYPZMEDPXBXYFVT85AJ67=cost-tab warning=aten%C3%A7%C3%A3o 01ECJ9TJKQ8A7BFZR3MJ5H35CA=aten%C3%A7%C3%A3o h_01J4KVYPZMQHGHDPEE1Q5M1KX8=ad-revenue-tab h_01J4KVYPZMRFMNCR61M4Z4388Y=permissions-tab ad-network-permissions=permiss%C3%B5es-da-rede-de-an%C3%BAncios 01ECJ9TJKQ9E3A5863Z3TRVAWZ=permiss%C3%B5es-da-rede-de-an%C3%BAncios agency-permissions=permiss%C3%B5es-da-ag%C3%AAncia 01ECJ9TJKQ0SAV4ZJB8DFRTE5C=permiss%C3%B5es-da-ag%C3%AAncia" />
