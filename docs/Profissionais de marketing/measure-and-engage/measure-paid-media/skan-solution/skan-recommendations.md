---
title: Recomendações da SKAN
metadata:
  keywords:
    - Marketers
    - SKAN
    - SKAdNetwork
    - SKAdNetwork (SKAN)
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - SKAdNetwork (SKAN)
  created_at: '2022-06-23T07:56:50Z'
  edited_at: '2026-08-18T00:32:38Z'
  id: 7078169815057
  locale: pt
  section: SKAN solution
  section_id: 6552135379985
  url: https://support.appsflyer.com/hc/pt/articles/7078169815057
---
> **Visão geral**: use as recomendações da SKAN para otimizar suas configurações de valores de conversão e receba mensurações de atividade pós-instalação mais precisas.

## Visão geral

A SKAdNetwork (SKAN), parte do iOS da Apple, ajuda os anunciantes a mensurar a performance da campanha, ao mesmo tempo em que mantém a privacidade do usuário. Com o SKAdNetwork, a atividade pós-instalação é mensurada usando apenas valores de conversão de números - entre 0-63.

O  <Anchor target="_blank" href="/marketers/pt/docs/skan-conversion-studio">Conversion Studio</Anchor> da AppsFlyer oferece a máxima flexibilidade para fazer com que cada valor de conversão (CV) conte. Você determina exatamente quais dados de mensuração devem ser codificados dentro do CV—incluindo quais atividades devem ser mensuradas durante o período pós-instalação, e por quanto tempo.

Entretanto, considerando a capacidade limitada de mensuração da SKAN, pode ser difícil decidir o que mensurar (por exemplo, receita, eventos in-app ou retenção) e como melhor utilizar os CVs entre 0-63. As decisões podem ser baseadas em estimativas, tentativa e erro, ou ferramentas de machine learning que utilizam dados internos da aplicação. E as mensurações nem sempre são tão precisas quanto poderiam ser.

As recomendações da SKAN pela AppsFlyer:

* Fornecem sugestões para melhorar suas configurações atuais de CV e melhorar sua eficiência de CV e precisão de mensuração.
* Resolvem as dificuldades que você pode ter ao tomar decisões de configuração de CV.
* São baseadas na sua vertical, geolocalização, dados do aplicativo SKAN e não-SKAN e comportamento específico do usuário.

## Recomendações

<div id="revenue" />

<Accordion title="Resultados">

#### **Compreendendo as recomendações de receita**

Ter o esquema de configuração de receita certo é fundamental para obter relatórios de receita precisos.

A configuração do valor de conversão (CV) para o qual você deve reportar a receita não é necessariamente 100% precisa, e a receita reportada pelo SKAN pode ser diferente da receita real. Por exemplo, o ARPPU real (AF reportado) pode ser de US$ 10, mas sua configuração atual de CV reporta um ARPPU de SKAN de US$ 7, o que significa que o SKAN reporta a receita para cada usuário pagante em US$ 3 a menos.

A AppsFlyer verifica seus dados de receita não-SKAN (que são 100% precisos) diariamente, para fazer recomendações personalizadas que você pode implementar para melhorar a precisão dos seus relatórios de receita SKAN. As recomendações também se baseiam em sua configuração da janela de atividade salva no Conversion Studio, assim como na sua vertical, geolocalização e comportamento do usuário no aplicativo.

As recomendações:

* Oferecem uma visualização clara da performance da campanha com relatórios de receita precisos.
* Economizam valores de conversão usando menos intervalos para a mensuração precisa da receita.
* Leve em consideração tanto as compras in-app quanto a receita publicitária.

#### **Layout das recomendações de receita**

<table><tbody><tr><td colspan="2"><p><img alt="revenue_recommendions_layout.png" src="https://files.readme.io/1595d3f59b6e30154da560a99430e231d8353d1bd54ebed6192ec0f13cd3f5b3-8976338886801.png"/></p></td></tr><tr><td><p><span>E</span></p></td><td><span>Janela de atividade salva na configuração do Conversion Studio, durante a qual a receita da SKAN é mensurada.</span></td></tr><tr><td><p><span>B</span></p></td><td><span>Receita média real do aplicativo por usuário pagante (ARPPU) com base em dados precisos de usuários orgânicos e não orgânicos atribuídos pelos métodos da AppsFlyer (AF).</span></td></tr><tr><td><p><span>C</span></p></td><td><p><span>ARPPU de configuração atual (SKAN ARPPU), ou seja, o ARPPU mensurado <span>com base na sua configuração atual no Conversion Studio para janela de atividade e configuração de CV para relatórios de receita.</span></span></p></td></tr><tr><td><span>J</span></td><td><p>ARPPU estimado: o ARPPU esperado para o número de intervalos selecionado. Calculado com base em todos os dados de receita dos últimos 14 dias do aplicativo, independentemente do método de atribuição (como SKAN ou método clássico), dividido pelo número de usuários pagantes. <span>Consulte F e G</span></p><p><span><strong>Observação:</strong> </span><span>É importante destacar que esse número não está disponível em outros dashboards da AF.</span> Aqui, mostramos o ARPPU (receita média por usuário pagante), enquanto em outros dashboards apresentamos o ARPU (receita média por usuário).</p></td></tr><tr><td><p><span>E</span></p></td><td><p>Erro aproximado: <span>a diferença entre B e C. Pode ser um erro positivo ou negativo, dependendo se o seu ARPPU da SKAN é super ou sub-notificado.</span></p><p><span>Exemplo: se o ARPPU real for US$ 10 e o ARPPU da SKAN for US$ 7, o erro aproximado é uma sub-notificação de 30% (-US$ 3 por usuário).</span></p></td></tr><tr><td><p><span>F</span></p></td><td><p>Recomendações para sua configuração de receita na SKAN. Selecione o número de intervalos que deseja incluir na sua configuração.</p></td></tr><tr><td><p><span>G</span></p></td><td><p><span>Sua configuração de receita atual conforme definida no Conversion Studio.</span><span></span></p></td></tr></tbody></table>

#### **Como usar recomendações de receita**

**Pré-requisito:** as recomendações de receita exigem pelo menos 14 dias de dados de receita.

> 📘 **Atenção**
>
> Isso é atualizado todos os dias. Isso significa que o período de recomendação retroativo de 14 dias é contado a partir de ontem. Por exemplo: se hoje for 28 de agosto. Os dados de entrada para a recomendação são de 13 a 27 de agosto.

**Para usar as recomendações de receita:**

1. Na AppsFlyer, dependendo se você usa SKAN 4, modo personalizado ou fixo, acesse:
   * **Configuração** > **SKAN Conversion Studio** > **SKAN 4**> **Receita geral/evento in-app**.
   * **Configuração** > **SKAN Conversion Studio** > **Personalizado** > **Receita geral/evento in-app**.
   * **Configuração** > **> SKAN Conversion Studio** >  **Receita**.
2. Se você já tem um intervalo de receita configurado, pule essa etapa. Se você não tiver um intervalo de receita configurado, configure-o agora.  
   Quando o intervalo de receita é configurado, são exibidas informações sobre a precisão da configuração e o erro aproximado.
3. Clique em **ver as recomendações**.  
   As informações sobre sua configuração atual são exibidas, juntamente com as recomendações de faixa de receita e a precisão estimada (erro aproximado) que elas fornecerão se implementadas. São fornecidas recomendações para manter e alterar o número de intervalos.
4. Selecione uma recomendação de intervalo.
5. Clique em **aplicar recomendação**.
   * Se você tiver sua configuração de receita definida no modo personalizado, a recomendação será aplicada.
   * Se você tiver sua configuração de receita no modo fixo (receita), precisará registrar a recomendação de intervalo. Vá para **SKAN Conversion Studio** > **Personalizado** > **Receita geral** e configure o intervalo recomendado.
6. Clique em **Salvar**.
   * Se você alterar alguma coisa em sua configuração de receita, poderá verificar novamente sua configuração e visualizar novas recomendações.

</Accordion>

<div data-zendesk-anchors="overview=vis%C3%A3o-geral h_01HGSZ05CH4P8BQT23VYH6DKVP=vis%C3%A3o-geral recommendations=recomenda%C3%A7%C3%B5es h_01HGSZ05CHPZKWKY7MR6MA68YZ=recomenda%C3%A7%C3%B5es h_01HGSZ05CH2RG3514N576ZGDFM=revenue understanding-revenue-recommendations=compreendendo-as-recomenda%C3%A7%C3%B5es-de-receita h_01HGSZ05CHC93SHP28DN9EK27N=compreendendo-as-recomenda%C3%A7%C3%B5es-de-receita revenue-recommendations-layout=layout-das-recomenda%C3%A7%C3%B5es-de-receita h_01HGSZ05CH5DVKAQ24EED16JRN=layout-das-recomenda%C3%A7%C3%B5es-de-receita using-revenue-recommendations=como-usar-recomenda%C3%A7%C3%B5es-de-receita h_01HGSZ05CJ4W0V3Y4XBWRMFW8K=como-usar-recomenda%C3%A7%C3%B5es-de-receita h_01HGSZCYCWRYEJPWZKDBC9SX8H=aten%C3%A7%C3%A3o" />
