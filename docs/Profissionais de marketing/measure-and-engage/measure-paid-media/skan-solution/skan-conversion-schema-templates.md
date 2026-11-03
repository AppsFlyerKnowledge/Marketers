---
title: Modelos de esquema de conversão da SKAN
metadata:
  keywords:
    - Marketers
    - SKAdNetwork (SKAN)
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - SKAdNetwork (SKAN)
  created_at: '2024-10-06T09:58:43Z'
  edited_at: '2026-08-19T00:30:56Z'
  id: 28968432692241
  locale: pt
  section: SKAN solution
  section_id: 6552135379985
  url: https://support.appsflyer.com/hc/pt/articles/28968432692241
---
> **Resumo:** os modelos de esquema de conversão da SKAN são modelos prontos para usar. Simplificam a configuração da SKAN ao oferecer modelos com base em uma combinação de dados da vertical e dados específicos do aplicativo, fornecendo insights da vertical e melhores práticas. Os modelos de esquema de conversão da SKAN podem ser encontrados no Conversion Studio.

## Principais vantagens

* Esses modelos simplificam a configuração da SKAN, permitindo criar um esquema de conversão com apenas alguns cliques.
* Ao utilizar melhores práticas e insights da vertical, os profissionais de marketing podem refinar seu esquema e aumentar a confiança na eficácia dele usando modelos baseados em dados da vertical combinados com dados específicos do aplicativo.

## Como começar

1. No menu à esquerda, acesse **Configurações > SKAN Conversion Studio**
2. Clique no botão **Modelos da vertical**
3. A janela de modelos será aberta
4. Selecione na lista de indústrias e verticais do lado esquerdo
5. O lado direito da tela exibe como fica o esquema de conversão sugerido
   1. Use o botão de alternância **Modo SKAN 4** para ativar ou desativar o suporte ao SKAN 4  
      **Observação:** com o SKAN 4, são sugeridas três janelas de atividade, junto com valores de conversão aproximados para a primeira janela. Com ele desativado, somente valores de conversão detalhados para a primeira janela serão sugeridos.
   2. Use o ? clique nos ícones ao lado de cada mensuração para ver uma explicação de por que esse evento ou essa mensuração foi sugerido, junto com informações de benchmark
6. Clique em **Selecionar & personalizar**  
   **Observação:** isso ainda não salvará suas configurações
7. Você será redirecionado para a página de edição do **Conversion Studio**
   1. Use os <Anchor target="_blank" href="/marketers/pt/docs/skan-conversion-studio#componentes-de-medição">recursos e ferramentas padrão</Anchor> do Conversion Studio para personalizar o modelo de acordo com as necessidades do seu aplicativo

## O que são os modelos de esquema de conversão da SKAN?

Os modelos de conversão da SKAN sugerem mapeamentos de valores de conversão para atividades relevantes do usuário pós-instalação, personalizados por vertical. As sugestões podem ser personalizadas para atender às necessidades específicas do aplicativo, combinando insights baseados em dados e expertise da vertical.

### Estrutura do modelo

* **Estratégia**: define se o foco será em eventos in-app, mensuração de receita ou em uma combinação de ambos. A estratégia é predefinida, mas pode ser personalizada na página de edição do Conversion Studio.
* **Versão da SKAN**: indica qual versão do SKAN tem suporte, seja SKAN4 ou versões anteriores. Por padrão, o SKAN 4 tem suporte. Se o SKAN 4 estiver desativado, as mensurações de valores de conversão aproximados serão desativadas, e o Conversion Studio mudará para o modo "personalizado".
* **Mensurações**: o modelo sugere atividades específicas de pós-instalação para mensurar. Isso inclui eventos específicos ou faixas de receita, bem como o uso de recursos como funil e Single Source of Truth (SSOT), que é sugerido por padrão.
  * As mensurações sugeridas podem ser personalizadas na página de edição do Conversion Studio.
  * Os eventos pré-selecionados são adaptados para cada modelo.
  * As faixas de receita são personalizadas com base em dados específicos do aplicativo, usando modelos avançados de recomendação de receita. Quando não há dados históricos suficientes, dados da vertical são usados para fazer sugestões.

## O que é o esquema de conversão da SKAN?

O esquema de conversão da SKAN define a configuração de mensuração da estrutura SKAdNetwork (SKAN). Ele especifica quais métricas de engajamento do usuário (por exemplo, eventos in-app ou receita) serão mensuradas e reportadas. A SKAdNetwork não reporta diretamente o engajamento pós-instalação com o aplicativo. Em vez disso, ela reporta "Valores de conversão", que são mapeados pelo desenvolvedor do aplicativo para atividades significativas de pós-instalação. Esse mapeamento é conhecido como o esquema de conversão da SKAN.

## Em que esses modelos se baseiam?

Os modelos se baseiam em uma análise orientada por dados de esquemas de conversão por vertical, juntamente com pesquisa qualitativa e insights de especialistas do setor. Algumas das sugestões se baseiam em dados específicos do aplicativo, conforme descrito abaixo.  
As principais etapas do processo de criação do modelo:

1. **Amostragem dos principais aplicativos**: identificamos aplicativos de amostra para análise quantitativa. Usando conjuntos de dados internos e externos, classificamos os aplicativos em hierarquias de verticais. Para cada subvertical, analisamos dezenas de aplicativos líderes e os classificamos pelo volume de tráfego da SKAN que geraram.
2. **Definição da estratégia**: com base em dados de benchmark da vertical, estabelecemos uma estratégia padronizada adaptada a cada vertical. Depois de analisar a porcentagem de aplicativos em cada vertical que mensuram eventos, receita ou ambos, selecionamos uma estratégia para cada vertical. Também consideramos a contagem média de eventos e o volume de aplicativos que utilizam o recurso de funil para determinar o número de eventos por modelo e se um funil é apropriado.
3. **Criação de grupos coletivos de eventos**: mapeamos os vários nomes de eventos, conforme definidos pelos aplicativos, em grupos predefinidos, com cada grupo refletindo uma coleção de eventos de negócios semelhantes.
4. **Eventos sugeridos**: identificamos os eventos de negócios mais recomendados para mensurar em cada vertical. Usando os grupos de eventos criados na etapa anterior, analisamos a porcentagem de aplicativos que mensuram cada evento. Após a análise por especialistas do setor e a validação em relação a dezenas de esquemas de conversão de aplicativos líderes, selecionamos a melhor combinação de eventos para cada subvertical.
5. **Faixas de receita definidas**: Sugerimos as melhores faixas de receita para maximizar a precisão da receita reportada. Quando um usuário abre a caixa de diálogo do modelo, verificamos em tempo real se o Aplicativo está qualificado para receber recomendações de receita com base em nossos modelos avançados. Se sim, o modelo cria faixas de receita personalizadas usando os dados do Aplicativo. Caso contrário, sugerimos faixas de receita com base em dados da vertical, derivados da aplicação dos nossos modelos de recomendação de receita aos dados dos aplicativos líderes na vertical.
6. **Eventos específicos do aplicativo mapeados**: Depois que o Aplicativo aplica um modelo específico, associamos os eventos in-app relevantes aos nomes de evento de negócios predeterminados no modelo da vertical. O aplicativo deve verificar se os eventos corretos foram selecionados.

<div data-zendesk-anchors="intro=principais-vantagens h_01J9GM9NV7HDA1N9WZH4Y6K1VH=principais-vantagens how-to-get-started=como-come%C3%A7ar h_01J9GME5K3C0BMPVK6K1D46HT0=como-come%C3%A7ar what-are-skan-conversion-schema-templates=o-que-s%C3%A3o-os-modelos-de-esquema-de-convers%C3%A3o-da-skan h_01J9GMP733JQSY60AJH22FGPRS=o-que-s%C3%A3o-os-modelos-de-esquema-de-convers%C3%A3o-da-skan template-structure=estrutura-do-modelo h_01J9GMPACY2TY0MYNEEJNW39Z5=estrutura-do-modelo what-is-skan-conversion-schema=o-que-%C3%A9-o-esquema-de-convers%C3%A3o-da-skan h_01J9GMQX4R8BMSQQ3XW4C97VEJ=o-que-%C3%A9-o-esquema-de-convers%C3%A3o-da-skan what-are-these-templates-based-on=em-que-esses-modelos-se-baseiam h_01J9GMR0FTV2Q75N9N5FQZW98F=em-que-esses-modelos-se-baseiam" />
