---
title: Plataforma de colaboração de dados (DCP) - Enriqueça fontes com ID5
metadata:
  keywords:
    - Marketers
    - Audience Activation
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-yael-sharabi
    - Marketers
    - Audience Activation
  created_at: '2026-01-08T07:53:48Z'
  edited_at: '2026-08-18T00:07:10Z'
  id: 42626850533137
  locale: pt
  section: Data Collaboration Platform
  section_id: 26230608274065
  url: https://support.appsflyer.com/hc/pt/articles/42626850533137
---
> **Em resumo:** Enriqueça seus dados party com identificadores ID5 para unificar dados fragmentados de usuários e melhorar as taxas de correspondência com parceiros de ativação, resultando em audiências maiores.

## Sobre o enriquecimento com ID5

A plataforma de colaboração de dados da AppsFlyer se integra ao ID5, um provedor líder de soluções de identidade para a web aberta. O ID5 conecta identificadores distintos, como endereços IP, e-mails com hash (HEM) e IDs de anúncios mobile (MAIDs), em um ID unificado com foco em privacidade. Isso aumenta as taxas de correspondência entre os conjuntos de dados dos colaboradores, permitindo que mais usuários sejam reconhecidos, vinculados e ativados em audiências. Este guia explica como funciona o enriquecimento com ID5 no DCP, como configurá-lo e como usá-lo para colaborações e ativação.

**O enriquecimento com ID5 ajuda você a:**

* Aumentar as taxas de correspondência entre seus dados first-party e parceiros de mídia ou colaboradores
* Maximizar o tamanho das audiências-alvo
* Unificar identificadores como HEM, MAID e IP + carimbo de data/hora em uma identidade única
* Preparar sua ativação para o futuro à medida que os cookies third-party deixam de ser usados

**Casos de uso comuns incluem:**

* **Enriquecimento de dados first-party da marca** - Uma marca faz upload da sua fonte de dados first-party no DCP e a enriquece com IDs ID5 usando sua conexão com o ID5.
* **Colaboração entre varejista e marca** - Um varejista colabora com uma marca e compartilha acesso à sua assinatura do ID5. No escopo seguro da colaboração, a marca enriquece seus dados de clientes usando a conexão do ID5 do varejista, melhorando as taxas de correspondência sem exigir sua própria conta direta no ID5.
* **Ativação de parceiro** - Fontes enriquecidas podem ser enviadas a parceiros de ativação compatíveis para aumentar as taxas de correspondência, o que significa que mais usuários dos seus dados podem ser correspondidos e incluídos nas audiências do lado do parceiro.

## Como o ID5 funciona

O DCP usa os IDs ID5 retornados para enriquecer sua fonte, resultando em uma nova fonte enriquecida disponível para segmentação e ativação.

**Dois fluxos de enriquecimento compatíveis:**

| Fluxo | A descrição | Quando utilizar |
| --- | --- | --- |
| Fluxo com tag | O proprietário dos dados já aplica a marcação do site do ID5 em seu domínio; portanto, os dados enviados por upload já contêm uma coluna de ID5. | Quando você gerencia a tag do ID5 diretamente no seu site e quer usar o DCP sem enriquecimento adicional. |
| Fluxo de enriquecimento servidor a servidor (S2S) | A AppsFlyer envia sua fonte de dados selecionada ao ID5, o ID5 a enriquece com IDs ID5 e a devolve ao DCP como uma fonte enriquecida. | Quando sua fonte não inclui uma coluna de ID5 ou quando você quer que a AppsFlyer faça o enriquecimento automaticamente. |

## Comece a usar o enriquecimento do ID5

Esta seção descreve como criar uma conexão do ID5 no DCP e usá-la para enriquecimento.

**Pré-requisitos:**

* Uma conta da AppsFlyer com permissões do DCP
* Um token do ID5 (fornecido pelo gerente de contas do ID5)
* Uma fonte que contenha pelo menos um dos identificadores com suporte: HEM, MAID ou IP + carimbo de data/hora

<div id="create-an-id5-connection" />

<Accordion title="Criar uma conexão do ID5">

Para usar o enriquecimento do ID5, primeiro crie uma conexão de **Data & Identity** no DCP.

1. Acesse a plataforma de colaboração de dados clicando em **Collaborate** > **Data Clean Room** no menu lateral do AppsFlyer.

   <Image alt="Clique em Data Clean Room.png" src="https://files.readme.io/2dc54e035b17aafa17b7eb4c526643284aa7979919f8caa0add13b7e6ae19e0c-41945704690065.png" width="33.49%" />
2. Vá até **Gerenciar conexões** (no canto superior direito).
3. Na guia **Data & Identity**, selecione **+ Nova conexão**.

   **<Image alt="+Nova conexão.png" src="https://files.readme.io/815ec20e84d85da413dfe9c9358b54d772461e1eeb3dff3ff7c5c31ced1088ac-42729247721873.png" width="72.63%" />**
4. Selecione **ID5.**

   **<Image alt="Selecione ID5.png" src="https://files.readme.io/a0c53243318fa7eed48ac5886ff5f3272bec0e6fd83a41117d53473757ab16d7-42729260095633.png" width="66.76%" />**
5. Insira seu token do ID5 (se aplicável).
6. Clique em **Guardar**.

Depois de salva, a conexão fica disponível para suas fontes e colaborações (sujeito a permissões).

</Accordion>

<div id="enrich-a-source-with-id5" />

<Accordion title="Enriquecer uma fonte com ID5">

Você pode enriquecer suas fontes usando o fluxo S2S.

**Para enriquecer uma fonte:**

1. Acesse a plataforma de colaboração de dados clicando em **Collaborate** > **Data Clean Room** no menu lateral do AppsFlyer.
2. Vá para a guia **Fontes** e passe o cursor sobre a fonte relevante.
3. No menu de ações, selecione **Enriquecer**.

   <Image alt="Enriquecer.png" src="https://files.readme.io/51c3f33da62d84ec9214e178e3bbaef15d6a03a32827ad393166db0dcd9a70fd-42729376739473.png" width="245px" />
4. Clique em **Iniciar enriquecimento**.
5. Depois que o fluxo de enriquecimento for concluído, você terá uma nova fonte conectada à fonte original com a adição de IDs do ID5.  
   **Observação:** Se a fonte original for excluída, a nova fonte também será excluída.

</Accordion>

<div id="grant-id5-permissions-in-a-collaboration" />

<Accordion title="Conceder permissões do ID5 em uma colaboração">

Os proprietários da colaboração podem permitir que os colaboradores usem uma conexão ID5 em uma colaboração (sujeito ao acordo comercial com a ID5).

**Para conceder permissões do ID5 a um colaborador:**

1. Acesse a plataforma Data Collaboration clicando em **Collaborate** > **Data Clean Room** no menu lateral do AppsFlyer.
2. Na guia **Collaborations**, abra uma colaboração existente ou <Anchor target="_blank" href="/marketers/pt/docs/data-collaboration-platform-dcp-create-a-collaboration">crie uma nova</Anchor>.
3. Clique em **Collaboration with “your collaborator”.**

   **<Image alt="Atualizar política de colaboração.png" src="https://files.readme.io/25d707c47bed9f5f60cd1ba521c4b48f41afbb0e36949f0ffa35cecf9a932ddc-42838633495313.png" width="58.95%" />**
4. Clique em **Editar política de colaboração**.

   <Image alt="Clique em Editar política de colaboração.png" src="https://files.readme.io/07aab2a3165d26779e94f62eb8487893bc725dfa3ad4c406de576480e2ed6c13-42838633497489.png" width="80.3%" />
5. Clique em **Permissões de acesso**.

   **<Image alt="Clique em Permissões de acesso.png" src="https://files.readme.io/b239775d71e1fa1dcc23537e73e35b80bff0184c9ee2aa213f644d90251284f3-42838633499281.png" width="78.62%" />**
6. Ative a **conexão ID5**.

   <Image alt="ID5 permissions.png" src="https://files.readme.io/f2831ec4f775b51ef419da33444198de6aabfde3b27d83cc9af623eaed4a865c-42789059643793.png" width="79.6%" />
7. Clique em **Guardar**.

Depois, os colaboradores podem associar as próprias fontes à colaboração e enriquecê-las usando a conexão ID5 do parceiro.

</Accordion>

## Especificações e limitações

Esta seção descreve algumas das principais características e limitações.

| Característica/limitação | A descrição |
| --- | --- |
| Primeiro enriquecimento e atualizações diárias | A primeira execução do enriquecimento começa imediatamente e normalmente é concluída em algumas horas.<br /><br />Após a execução inicial, o enriquecimento continua diariamente em um horário fixo de processamento, garantindo mapeamentos de identidade atualizados.<br /><br />Você pode pausar o enriquecimento a qualquer momento para interromper as atualizações diárias. |
| Dependência da fonte | Se a fonte original for excluída, a fonte enriquecida será excluída automaticamente. |
| Escopo de ativação | Em uma colaboração, um anunciante pode usar dados enriquecidos para ativação, mas não pode fazer download nem consultá-los. |
| Restrições de status | Você pode enriquecer apenas fontes com status **Ativo**. |
| Latência de enriquecimento | As fontes com status **Waiting** ou **Processing** continuam o enriquecimento, mas só podem ser usadas depois de atingirem o status **Ativo**. |
| Janela de retenção | O ID5 armazena mapeamentos por 14 a 90 dias, dependendo da atividade. |
| Requisito de identificador | Se a fonte não tiver HEM, MAID ou IP + carimbo de data/hora, o enriquecimento será desativado. |
| Conflitos de conexão | Uma colaboração pode incluir apenas uma conexão ID5. Se ambas as party tiverem suas próprias conexões ID5, nenhuma das conexões poderá ser usada na colaboração. Nesse caso, cada party deve enriquecer seus dados separadamente em seu próprio ambiente, e somente as fontes enriquecidas resultantes poderão ser usadas na colaboração. |

<div data-zendesk-anchors="about-id5-enrichment=sobre-o-enriquecimento-com-id5 h_01KD7VPW5NX5QHVPJWX5YCGXAH=sobre-o-enriquecimento-com-id5 how-id5-works=como-o-id5-funciona h_01KD7VPW5NW24X53QQE2ZVDA2N=como-o-id5-funciona get-started-with-id5-enrichment=comece-a-usar-o-enriquecimento-do-id5 h_01KD7VPW5P0FEEAET9RXVPSECY=comece-a-usar-o-enriquecimento-do-id5 h_01KD80FBKDHB6HKTTMXFDPGH5E=create-an-id5-connection h_01KD80FBKE4Q8TMNW7WFCN4QGC=enrich-a-source-with-id5 h_01KD80FBKE6TB00E8PZCFWST6M=grant-id5-permissions-in-a-collaboration traits-and-limitations=especifica%C3%A7%C3%B5es-e-limita%C3%A7%C3%B5es h_01KD7VPW5P5XV61Z3X2CWZ7GV9=especifica%C3%A7%C3%B5es-e-limita%C3%A7%C3%B5es" />
