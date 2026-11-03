---
title: Obtenha dados de postback SKAN do Google Ads
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
  created_at: '2021-06-28T19:34:39Z'
  edited_at: '2026-09-09T00:29:27Z'
  id: 4403215779857
  locale: pt
  section: SKAN interoperation
  section_id: 6552115163153
  url: https://support.appsflyer.com/hc/pt/articles/4403215779857
---
> **Visão geral:** permita que o Google compartilhe o conteúdo dos postbacks do seu aplicativo SKAdNewtork (SKAN) para iOS com a AppsFlyer.

## Obtenha dados de postback SKAN do Google Ads

Se você trabalha com vários parceiros de ad networks, a prática recomendada é que você os configure na AppsFlyer. Assim, as métricas de performance do SKAN para todos os seus parceiros de ad network, enriquecidas com outras métricas como custo, estarão disponíveis através da plataforma da AppsFlyer.

**Escopo dos relatórios SKAN com o Google Ads**

* O Google Ads compartilha postbacks agregados do SKAN para iOS que eles recebem com a AppsFlyer no contexto de campanhas de aplicativos para iOS. Esses postbacks representam instalações de vários canais, como display e YouTube, mas geralmente excluem a maior parte da pesquisa, pois o SKAN não é atualmente compatível com o acompanhamento web->aplicativo.
* A AppsFlyer decodifica o postback e, em seguida, atualiza o painel e os relatórios SKAN (incluindo o relatório de dados brutos do postback).
* <Anchor target="_blank" href="/marketers/pt/docs/self-reporting-networks-srns#ios-145-srn-attribution">Implicações do iOS 14.5 nos relatórios de SRNs</Anchor>

**Considerações**:

Ao receber o postback do iOS, o Google determina o horário do último clique usando sinais de veiculação de anúncios. No entanto, a AppsFlyer considera o tempo de clique como o tempo de instalação. Isso pode levar a diferenças entre os painéis da AppsFlyer e do Google.

Devido à metodologia de relatórios de cliques do Google e à atualização diária retroativa de dados, a AppsFlyer extrai os dados dos 45 dias anteriores e exibe a instalação no último clique antes da data de instalação.  Por exemplo, um clique em 1º de julho pode ser informado à AppsFlyer até 15 de agosto. A AppsFlyer exibe esta instalação na data do clique informada pelo Google. Isso afeta os <Anchor target="_blank" href="/marketers/pt/docs/skadnetwork-skan-solution-guide#reporting-options">relatórios</Anchor> da seguinte forma:

* Os relatórios agregados e o painel são atualizados retroativamente.
* <Anchor target="_blank" href="/marketers/pt/docs/skan-raw-data-reports">Os relatórios de dados brutos</Anchor> não mudam retroativamente. Os dados (fornecidos via Data Locker) são fornecidos em pastas de acordo com a data em que o Google os forneceu à AppsFlyer (data de chegada dos dados).

## Configurar interoperação

Para configurar a interoperação com o Google Ads, siga as etapas nas abas a seguir.

<Accordion title="Configurar postbacks">

**Para configurar o envio de postbacks:**

| Etapa | Action | Atenção |
| --- | --- | --- |
| 1 | Revisão das definições do SKAN | Verifique se a <Anchor target="_blank" href="/marketers/pt/docs/skadnetwork-skan-solution-guide">solução SKAN</Anchor> da AppsFlyer está configurada e funcionando. Isso permite que o SDK da AppsFlyer chame as APIs do SKAN e defina o valor de conversão.<br /><br />**Para revisar as configurações do SKAN**:<ol><li>Na AppsFlyer, aceda a **Definições** > **SKAN Conversion Studio**.</li><li>Clique nas opções (⋮) e verifique se **a métrica SKAN** está ativada.</li></ol>![skan-settings.png](https://files.readme.io/5a5b9b8b8a809336055340a14e49dacc16c5c0e95cda62c6dfb2ca9a11618d71-27548444964497.png)<ol><li>Selecione o modo de medição que prefere.<br />Saiba mais sobre o <Anchor target="_blank" href="/marketers/pt/docs/skan-conversion-studio">SKAN Conversion Studio</Anchor>.</li><li>Registe os nomes exatos dos eventos definidos. Você precisará deles na próxima etapa. **Nota**! Os nomes diferenciam maiúsculas de minúsculas.</li></ol> |
| 2 | Mapeamento de eventos in-app na AppsFlyer | **Para visualizar e definir mapeamentos de eventos in-app**:<ol><li>Na AppsFlyer, aceda a **Colaborar** > **Integrações Ativas**.</li><li>Selecione **Google Ads**</li><li>Na aba **Integração**, verifique se **Ativar parceiro** está ativado. Caso contrário, você deverá primeiro concluir a <Anchor target="_blank" href="/marketers/pt/docs/google-ads-adwords-integration-setup-for-advertisers">integração com o Google Ads</Anchor>.</li><li>Na **seção Postbacks de eventos in-app:**<ol><li>Se não estiver ativada, ative a opção **Postbacks de eventos in-app**.</li><li>A prática recomendada é mapear os eventos relacionados ao tipo de métrica atualmente selecionado. Nota! No caso de métrica de receita, mapeie af\_skad\_revenue para o evento de receita apropriado do Google</li></ol></li><li>Vá até o final da página.</li><li>Clique em **Guardar integração**.</li></ol> |

</Accordion>

<Accordion title="Permitir que o Google Ads compartilhe dados do SKAN com a AppsFlyer">

Para ver as instalações SKAN atribuídas ao Google Ads no painel SKAN da AppsFlyer, você deve permitir que o Google Ads compartilhe dados SKAN com a AppsFlyer.

**Para conceder permissão ao Google Ads para compartilhar dados da SKAN com a AppsFlyer:**

1. O procedimento a seguir deve ser realizado pelo anunciante. No caso de uma agência, tanto a agência quanto o anunciante precisam ativar a mensuração do SKAN.
2. Na AppsFlyer, aceda a **Colaborar** > **Integrações Ativas**.
3. Pesquise e selecione **Google Ads**.
4. Vá para a aba **SKAN**. <Image alt="mceclip0.png" src="https://files.readme.io/ba8d881ca8430bfdcf67a37e862ad3e31a9af522f2f877d3fba30bc2e13006a6-4404428381457.png" width="309px" />
5. Se a **mensagem temporariamente indisponível for exibida**, na maioria das vezes, isso significa que um bloqueador de anúncios está ativo. Nesse caso, desative seu bloqueador de anúncios e recarregue a página. Se esse não for o caso, entre em contato com o suporte da AppsFlyer.  ![mceclip1.png](https://files.readme.io/e86b868f71e11ad347ff7557a793090d9d6adb8fe4df4f9010c8d770b373ac6a-4404428420497.png)
6. Clique em **Login do Google Ads**. **Google Ads**.
   * Você deve fazer login no Google Ads usando uma função de usuário administrador da conta.
   * Se a conta do Google estiver associada a vários aplicativos, faça login uma vez e todos os aplicativos serão autorizados. Em outras palavras, não há necessidade de autorização por aplicativo.
   * A AppsFlyer extrai dados de todos os aplicativos iOS da AppsFlyer aos quais sua conta do Google está associada, independentemente da configuração de ativação de parceiro do aplicativo.
7. Siga as instruções na interface do usuário.
8. Em alguns casos, pode ser que você tenha que conceder permissão à AppsFlyer para **gerenciar suas campanhas do AdWords.** Nesse caso, você deve ativar a permissão. Não se preocupe, não faremos alterações nas configurações da sua campanha. [<Image alt="GoogleManageAdWords.png" src="https://files.readme.io/bf327f152f937cdbea0b71cca72cc989aa83de6cef83677fca1f687b71aa8606-4405185007121.png" width="182px" />](https://files.readme.io/bf327f152f937cdbea0b71cca72cc989aa83de6cef83677fca1f687b71aa8606-4405185007121.png)
9. Verifique se o status da conta **Aguardando sincronização** aparece.  
   Esta mensagem persiste até recebermos dados do Google Ads (até 24 horas).
10. Espere até depois das 02:00 UTC do dia seguinte, depois verifique se o status mudou para **ativo.**  
    Os dados no painel SKAN são atualizados diariamente até às 08:00 UTC. **Nota**! Conforme descrito na seção de considerações, o Google pode atualizar os dados retroativamente em 45 dias.
11. Leia sobre as [diferenças entre as métricas](/docs/get-skan-postback-data-from-google-ads#measurement-and-timing-differences-between-appsflyer-and-google-ads).

</Accordion>

## Informações adicionais

<Accordion title="Desativando a integração do SKAN">

Ao desativar a integração do Google Ads, não basta desativar o botão **Ativar parceiro**, você deve remover separadamente as conexões SKAN para interromper a gravação de dados SKAN.

**Para desativar a integração da SKAN:**

1. Na AppsFlyer, acesse **colaborar**  >  **integrações ativas**.
2. Pesquise e selecione Google Ads.
3. Vá para a aba **SKAN**.
4. Clique no ícone de exclusão para a conta que você deseja remover.

</Accordion>

<Accordion title="Diferenças de métricas e tempo entre a AppsFlyer e o Google Ads">

| Item | Detalhes |
| --- | --- |
| Disponibilidade de dados inicial | Os dados ficam disponíveis a partir da data em que você habilita a integração de acordo com o horário UTC. Como o Google usa o tempo do clique, as instalações anteriores à data de início podem ser exibidas retroativamente. |
| Data de instalação | O Google define o tempo de instalação como o tempo estimado do último clique antes da instalação. É o Google quem determina o tempo de clique usando sinais de veiculação de anúncios.<br /><br />O seguinte deve ser considerado ao comparar fontes de mídia e o painel na AppsFlyer:<ul><li>A AppsFlyer não considera o fuso horário do aplicativo ou da conta de anúncios do Google Ads.</li><li>O Google pode relatar instalações retroativamente por 45 dias após a data do clique.</li><li>No caso de outras fontes de mídia, derivamos o tempo de instalação usando o horário de chegada do postback.</li></ul> |
| Instalações | A partir da Google Ads API V10+, a AppsFlyer exibe apenas instalações de postbacks com did\_win=TRUE. Como resultado, o número de instalações na AppsFlyer pode ser menor do que no painel do Google Ads. |

</Accordion>

<Accordion title="Identificação e solução de problemas e perguntas frequentes">

| Item | Detalhes |
| --- | --- |
| Envio de eventos para o Google Ads | **P**: Posso enviar postbacks de eventos adicionais para eventos ao Google Ads para eventos não selecionados na opção de métrica de valor?<br /><br />**R**: Para usuário que permitem o rastreamento, envie todos os eventos para maximizar a capacidade de otimização do Google Ads. |
| Mapear vários eventos para o mesmo evento do Google Ads | **P**: Posso mapear vários eventos in-app para um evento do Google Ads?<br /><br />**R**: Se vários eventos forem mapeados para um evento padrão do Google Ads, o Google Ads não será capaz de diferenciar os eventos. Assim, o Google Ads otimizará para o único evento que ele reconhece. |
| Tipos de campanha compatíveis | **P:** Que tipos de campanhas do Google Ads são compatíveis?<br /><br />**R**: Campanhas iOS web-to-app e app-to-app, incluindo pesquisa, vídeo, entre outras. |
| Não há dados para extrair | **P:** Por que o status da conexão exibe "Nenhum dado para extrair: verifique suas permissões de compartilhamento do Google"?<br /><br />**R**: Ainda não há dados SKAN ou você precisa fazer login no Google Ads usando uma função de usuário administrador na conta. |

</Accordion>

<Accordion title="Especificações e limitações">

| Especificação | Descrição |
| --- | --- |
| Visualizações engajadas | As visualizações engajadas são contadas como cliques e os postbacks são enviados para elas, assim como para qualquer atribuição de clique. |
| Atualização dos dados | <ul><li>Coletamos dados SKAN do Google Ads diariamente a partir da 01h UTC.</li><li>Dashboards e atualização de dados agregados 7 horas depois.</li><li>O Google ocasionalmente sofre atrasos no pipeline do SKAN, portanto os dados podem chegar mais tarde do que o habitual e os dados do Single Source of Truth (SSOT) também podem ser afetados.<ul><li>Quando o Google entrega os dados atrasados, eles são atualizados retroativamente.</li></ul></li></ul> |
| Relatórios disponíveis | Os dados do Google Ads estão disponíveis no painel SKAN, nos relatórios agregados e de dados brutos. Consulte <Anchor target="_blank" href="/marketers/pt/docs/skadnetwork-skan-solution-guide#reporting-options">as opções de relatórios SKAN.</Anchor> |
| Agências | Se a agência tiver um papel de usuário Administrador na conta do anunciante no Google Ads, ela pode realizar o procedimento neste artigo para permitir a interoperação Google SKAN em nome do anunciante. Os anunciantes não precisam fazer login em sua conta do Facebook Ads também. O login da agência será indicado na conta do anunciante. |

</Accordion>

<Accordion title="Não está vendo instalações de SKAN no Google Ads?">

Use esta checklist para confirmar se a sua configuração está correta e se os dados podem fluir para o dashboard de SKAN da AppsFlyer.

**Lista de soluções rápidas**

1. Verifique o status da integração.
   * Confirme se a integração do Google Ads está ativa na AppsFlyer.
   * Na guia **SKAN**, verifique se o status aparece como **Ativo**. Se aparecer **Temporariamente indisponível**, desative qualquer bloqueador de anúncios e recarregue a página.
2. Autorize a conexão com o Google Ads, caso ainda não esteja conectado.
   * Clique em **Conectar Google Ads**.
   * Faça login com uma conta de administrador do Google Ads e, se solicitado, permita que a AppsFlyer gerencie campanhas do AdWords.
3. Aguarde a sincronização.
   * Depois que você fizer login, o status aparecerá como **Aguardando sincronização**.
   * Quando a AppsFlyer começar a receber dados de SKAN do Google, o status mudará para **Ativo** — isso pode levar até 24 horas.
   * Etapa

**Ainda não funcionou?**

Se você concluiu as etapas acima e as instalações ainda não aparecem, verifique o seguinte:

* Se o status mostrar "No data to pull: Check your Google data-sharing permissions," o Google ainda não compartilhou dados de SKAN ou você precisa fazer login no Google Ads usando uma função de usuário Administrador.
* O procedimento a seguir deverá ser realizado pelo anunciante, agência ou ambos.
* Verifique as contagens de instalações diretamente no Google Ads:

  1. No Google Ads, acesse **Campanhas**.
  2. Clique no ícone **Relatórios** > **Metas e conversões** > **Conversões do SKAdNetwork**.
  3. Se aparecer "Erro ao carregar o relatório — Este relatório é incompatível com os filtros da visualização atual", clique em **Limpar filtros da visualização**.
  4. Use a pesquisa de colunas (ícone de lupa) para encontrar e adicionar colunas específicas de SKAN, como **Conv. do SKAdNetwork. segmento de valor**.

  Se não houver instalações no Google, não haverá nenhuma no AppsFlyer. Consulte o seu representante do Google para entender por que não há instalações.

**Bom saber**

* Os dados do SKAN são coletados do Google Ads diariamente a partir da 01h UTC. Os dados do Google podem ocasionalmente levar até dois dias extras para chegar.
* Somente campanhas iOS Web-to-app e App-to-app têm suporte para mensuração do SKAN.

</Accordion>

> 📄 **Veja também**
>
> * <Anchor target="_blank" href="/marketers/pt/docs/skadnetwork-skan-solution-guide">Guia de soluções do SKAN da AppsFlyer</Anchor>

<div data-zendesk-anchors="get-skan-postback-data-from-google-ads=obtenha-dados-de-postback-skan-do-google-ads h_01HCHYGCVJA3C8WJS8JH7BG0CD=obtenha-dados-de-postback-skan-do-google-ads set-up-interoperation=configurar-interopera%C3%A7%C3%A3o h_01HCHYGCVJY5KT4J6RQS0BJ90G=configurar-interopera%C3%A7%C3%A3o additional-information=informa%C3%A7%C3%B5es-adicionais h_01HCHYGCVJTS53PCGK21BEZB2T=informa%C3%A7%C3%B5es-adicionais h_01HE7RMSECNDW9VD9XY6H01H55=veja-tamb%C3%A9m" />
