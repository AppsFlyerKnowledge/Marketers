---
title: Interoperação do SKAN com o Snapchat
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
  created_at: '2021-02-10T20:20:51Z'
  edited_at: '2026-08-19T00:30:30Z'
  id: 360017604077
  locale: pt
  section: SKAN interoperation
  section_id: 6552115163153
  url: https://support.appsflyer.com/hc/pt/articles/360017604077
---
> **Visão geral:** A interoperabilidade com SKAN permite que o Snapchat compartilhe postbacks SKAN com a AppsFlyer e permite que a AppsFlyer compartilhe seu mapeamento de mensuração do valor de conversão com o Snapchat.

## Interoperabilidade com SKAN: AppsFlyer &lt;-> Snapchat

Se você trabalha com vários parceiros de ad networks, a prática recomendada é que você os configure sua integração com o SKAN na AppsFlyer. Assim, as métricas de performance da SKAN, enriquecidas com outras métricas como custo, estarão disponíveis na plataforma da AppsFlyer. 

**Escopo da interoperabilidade do SKAN com o Snapchat**

A interoperação permite que a AppsFlyer e o Snapchat compartilhem o mapa de valores de conversão do SKAN, o que permite que ambos forneçam métricas de performance. Se você ativar a integração do parceiro Snapchat na AppsFlyer, a AppsFlyer fornecerá eventos ao Snapchat para fins de otimização.

**Guia para anúncios de instalação de apps do Snapchat**

Ao configurar sua campanha de instalação do aplicativo do Snapchat iOS 14, , considere as seguintes orientações do Snapchat:

*A partir de 18 de fevereiro de 2021, a SKAdNetwork estará disponível no Snapchat Ads Manager para todos os anunciantes. Recomendamos que os aplicativos configurem e comecem a testar, para garantir que não haja interrupção na mensuração ou escala das campanhas de aquisição de aplicativos do iOS 14 no Snapchat. No futuro, a SKAdNetwork será um requisito para acessar os lances baseados em metas do aplicativo para campanhas iOS no Snapchat.*

*Conclua a integração da SKAdNetwork no painel MMP da AppsFlyer e conclua a configuração do mapeamento do valor de conversão antes de lançar os conjuntos de anúncios da SKAdNetwork no Snapchat Ads Manager. O guia de configuração do Snapchat para SKAdNetwork pode ser encontrado [aqui](https://businesshelp.snapchat.com/s/article/skadnetwork).*

**Requisitos de implementação**

Considere o seguinte no Snapchat:

* Configure um [ID do aplicativo Snap](https://businesshelp.snapchat.com/en-US/a/snap-app-id) para cada aplicativo que você anuncia no Snapchat.
* Ative os conjuntos de anúncios do Snapchat para mensuração da SKAN.
* Para um determinado aplicativo, você está limitado a um máximo de 10 conjuntos de anúncios por vez que optou pela atribuição do SKAN.

### Ativando a interoperação da AppsFlyer SKAN com o Snapchat

A interoperação é alcançada por meio de configurações nos painéis da AppsFlyer e do Snapchat. Nenhuma interoperação é necessária no próprio aplicativo. No entanto, você precisa adotar o SDK mais recente da AppsFlyer.

<Table>
  <thead>
    <tr>
      <th>
        Etapa
      </th>
      <th>
        Ação
      </th>
      <th>
        Detalhes
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        1
      </td>
      <td>
        Pré-requisitos do aplicativo
      </td>
      <td>
        * Adote a versão mais recente do <Anchor target="_blank" href="/marketers/pt/docs/sdk-integration-overview">SDK</Anchor> da AppsFlyer em seu aplicativo.
      </td>
    </tr>
    <tr>
      <td>
        2
      </td>
      <td>
        Revisão das configurações de SKAN
      </td>
      <td>
        Configure e ative a solução <Anchor target="_blank" href="/marketers/pt/docs/skadnetwork-skan-solution-guide">SKAN da AppsFlyer.</Anchor>

        **Para visualizar as configurações da SKAN**:

        1. Na AppsFlyer, acesse **configurações** > **Conversion Studio da SKAN**.
        2. Clique nas opções (⋮) e verifique se **a métrica SKAN** está ativada.  

           ![skan-settings.png](https://files.readme.io/5a5b9b8b8a809336055340a14e49dacc16c5c0e95cda62c6dfb2ca9a11618d71-27548444964497.png)
        3. Selecione seu modo de mensuração preferido.  
           Saiba mais sobre o <Anchor target="_blank" href="/marketers/pt/docs/skan-conversion-studio">SKAN Conversion Studio</Anchor>.
        4. Anote os nomes exatos dos eventos definidos. Você precisa deles para a próxima etapa.
      </td>
    </tr>
    <tr>
      <td>
        3
      </td>
      <td>
        Mapeamento de eventos in-app
      </td>
      <td>
        Revise, e se necessário, faça mudanças em seus mapeamentos de eventos in-app do Snapchat.

        **Para visualizar e definir mapeamentos de eventos in-app**:

        1. Na AppsFlyer, acesse **Configurações** > Integrações ativas.
        2. Pesquise e selecione **Snapchat**.
        3. Na aba **Integração**, se **Ativar parceiro** não estiver ativado, ative-o.
        4. Verifique e, se necessário, atualize o ID do aplicativo Snap exibido na AppsFlyer com o ID do aplicativo exibido no <Anchor target="_blank" href="https://businesshelp.snapchat.com/s/article/snap-app-id?language=en_US">Dashboard do Snapchat</Anchor>.
        5. Se não estiver ativada, ative a opção **Postback de eventos in-app**.  

           [<Image alt="mceclip0.png" src="https://files.readme.io/9df3455b102ff280e8b0fae4bfc006fa87f8830d74064eb955fc829d06708165-23458868914577.png" width="432px" />](https://files.readme.io/9df3455b102ff280e8b0fae4bfc006fa87f8830d74064eb955fc829d06708165-23458868914577.png)

           Nos eventos in-app, verifique se os **nomes de eventos do SDK** que você definiu na mensuração do SKAN estão mapeados para **Identificadores de eventos de parceiros,** ou seja, para os nomes de eventos do Snapchat. Você deve mapear os eventos do tipo de mensuração da SKAN selecionados no momento ou os eventos em seu <Anchor target="_blank" href="/marketers/pt/docs/skan-cv-decode-map-your-cv-to-events">Mapa de conversão personalizado</Anchor>. **Atenção**! O tipo de mensuração padrão é receita.

           #### Guia de mapeamento de eventos in-app

        | Tipo de mensuração | Requisitos de mapeamento |
        | --- | --- |
        | Personalizada | Mapeie os eventos in-app que você configura em Personalizado para os eventos correspondentes do Snap.<br /><br />Para informar a receita por postback, você deve definir **Enviar receita**como **Valores e receita**.<br /><br />![SendValueandRevenue.png](https://files.readme.io/412c60db2b09d80a989b7546a6819aa1b030732e0ce004b323dc09db1015c238-11331054047377.png)<br /><br />*af\_skad\_revenue* é usado para receita geral e mapeado para o evento de receita de anúncios do Snap.<br /><br />**Atenção**! Não há problema em mapear mais de um evento para o evento de receita do Snap. |
        | Resultados | Mapeie af\_skad\_revenue para PURCHASE |
        | Conversão | Mapeie de 1 a 6 eventos de conversão para os eventos correspondentes do Snapchat. |
        | com o anúncios | Mapeie o evento de engajamento que você definiu para o evento correspondente do Snapchat. |

        6. Clique em **Salvar integração.**
      </td>
    </tr>
    <tr>
      <td>
        4
      </td>
      <td>
        Permitir que o Snapchat compartilhe postbacks com a AppsFlyer
      </td>
      <td>
        1. Vá para o painel do Snapchat.
        2. Em **,Compartilhe postbacks com este MMP**, selecione AppsFlyer.

           [<Image alt="SnapchatSelectAppsFlyer.png" src="https://files.readme.io/e142c4bf54019e8587722af4c5cf5aa95ca49a76948f66e3fb584b003aaacdd6-360017154717.png" width="268px" />](https://files.readme.io/e142c4bf54019e8587722af4c5cf5aa95ca49a76948f66e3fb584b003aaacdd6-360017154717.png)
        3. Clique em **Atualizar**.
      </td>
    </tr>
  </tbody>
</Table>

## Informações adicionais

<div id="discrepancies-guide" />

<Accordion title="Guia de discrepâncias">

| Discrepância | Detalhes |
| --- | --- |
| Filtros de painel | **Causa da discrepância**<ul><li>AppsFlyer: O painel do SKAN contém instalações relacionadas a postbacks do iOS recebidos.</li><li>Snapchat: Por padrão, o painel e o relatório do Snapchat incluem SKAN e instalações atribuídas tradicionalmente (IDFA). Filtre o relatório do Snapchat para obter apenas instalações do SKAN.</li></ul>**Solução**<br /><br />Alinhe os filtros do painel do Snapchat para exibir as instalações da SKAN somente conforme indicado na captura de tela a seguir.<br /><br />[![SnapchatFilter.png](https://files.readme.io/6e067557aabe899df48454aaf4b7be7f466da55e41b7cd3c68db802e48df7d07-360019782137.png)](https://files.readme.io/6e067557aabe899df48454aaf4b7be7f466da55e41b7cd3c68db802e48df7d07-360019782137.png) |
| Diferenças de data de instalação | **Causa da discrepância**<br /><br />Pode haver diferenças entre as datas de instalação da AppsFlyer e do Snapchat da seguinte forma:<ul><li>AppsFlyer: Deriva a data de instalação usando a seguinte fórmula: Tempo de chegada do postback - 24 horas - janela de medição (padrão 24 horas). Portanto, o ajuste padrão é de 48 horas. Todos os horários UTC. <Anchor target="_blank" href="/marketers/pt/docs/about-data-freshness-and-timezone-support#skan">Atualização de dados da SKAN</Anchor></li><li>Snapchat: Normalmente usa a hora de chegada do iOS após o horário de retorno do postback como a data de instalação sem ajuste.</li></ul>**Solução**<br /><br />Leve em consideração o que foi dito acima ao comparar os resultados. |

</Accordion>

> 📄 **Veja também**
>
> * <Anchor target="_blank" href="/marketers/pt/docs/skadnetwork-skan-solution-guide">Guia de soluções do SKAN da AppsFlyer</Anchor>

<div data-zendesk-anchors="skan-interoperability-appsflyer-snapchat=interoperabilidade-com-skan-appsflyer---snapchat h_01HDNZ3SP97C331D45AP1F8CM7=interoperabilidade-com-skan-appsflyer---snapchat enabling-appsflyer-skan-interoperation-with-snapchat=ativando-a-interopera%C3%A7%C3%A3o-da-appsflyer-skan-com-o-snapchat h_01HDNZ3SP9FZ3AXCNG185DJQY1=ativando-a-interopera%C3%A7%C3%A3o-da-appsflyer-skan-com-o-snapchat inapp-event-mapping-guide=guia-de-mapeamento-de-eventos-in-app h_01HDNZ3SPA742313RAJPYSEHWV=guia-de-mapeamento-de-eventos-in-app additional-information=informa%C3%A7%C3%B5es-adicionais h_01HDNZ3SPASN8P9G5YYQGRFC8F=informa%C3%A7%C3%B5es-adicionais h_01HDNZ3SPA99XHVBPXVWB5MN86=discrepancies-guide h_01HDNZ1BW5EBP0JCX84MTYPQ6K=veja-tamb%C3%A9m" />
