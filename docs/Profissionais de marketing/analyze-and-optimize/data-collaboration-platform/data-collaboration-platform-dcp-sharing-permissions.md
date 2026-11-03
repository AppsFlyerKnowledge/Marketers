---
title: Permissões de compartilhamento da plataforma de colaboração de dados (DCP)
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
  created_at: '2025-12-17T10:36:33Z'
  edited_at: '2026-08-19T00:07:08Z'
  id: 42009477902353
  locale: pt
  section: Data Collaboration Platform
  section_id: 26230608274065
  url: https://support.appsflyer.com/hc/pt/articles/42009477902353
---
> **Em resumo:** Defina as permissões de colaboração da DCP que determinam como seu colaborador pode usar seus dados compartilhados.

Este artigo descreve as permissões disponíveis ao compartilhar dados em uma colaboração da plataforma de colaboração de dados (DCP). As permissões de compartilhamento são definidas pela **Política de colaboração** que você configura ao <Anchor target="_blank" href="/marketers/pt/docs/data-collaboration-platform-dcp-create-a-collaboration">criar uma colaboração</Anchor> e especificam o que os colaboradores podem fazer com seus dados e quais recursos ou parceiros de ativação eles podem usar. Além dessa política padrão, permissões de dados personalizadas também podem ser definidas por fonte. A Política de colaboração define:

* [Permissões de dados](#permissões-de-dados)
* [Permissões de acesso](#permissões-de-acesso)

## Permissões de dados

As permissões de dados que você seleciona definem como seu colaborador pode usar seus dados associados e se aplicam a todas as fontes que você associa à colaboração. As permissões também podem ser modificadas individualmente por fonte.

<Image alt="Permissões de dados Dez 2025.png" src="https://files.readme.io/1e33caebbe4a8ff14fe84be6ba7f50b82a5fe7c268ba186db0250c7084718d54-42009477892241.png" width="704px" />

### As permissões de dados incluem:

| Permissão | A descrição |
| --- | --- |
| **Torne-as visíveis para o colaborador** | Permite que o colaborador visualize e use as fontes que você associa à colaboração, de acordo com as outras permissões que você concede. Quando desativada, suas fontes ficarão visíveis apenas para você. |
| **Consultar dados** | Permite que o colaborador consulte os dados e crie relatórios agregados. Você pode especificar se o colaborador:<ul><li>**Pode usar apenas dados sobrepostos** (Conjunto de dados sobreposto) - Refere-se aos usuários em comum de ambas as partes.<br />**Observação:** Quando essa opção é selecionada, o tamanho da fonte não fica disponível.</li><li>**Pode consultar todos os dados** (Conjunto de dados universal) - Refere-se a todos os dados que você associa à colaboração.</li></ul> |
| **Criar públicos** | Permite que o colaborador use os dados ao criar suas <Anchor target="_blank" href="/marketers/pt/docs/data-collaboration-platform-dcp-add-connections">audiências</Anchor>. Você pode especificar se o colaborador:<ul><li>**Pode consultar apenas dados sobrepostos** (Conjunto de dados sobreposto) - Refere-se aos usuários em comum de ambas as party.<br />**Observação:** Quando essa opção é selecionada, o tamanho da fonte não fica disponível.</li><li>**Pode usar todos os dados** (Conjunto de dados universal) - Refere-se a todos os dados que você associa à colaboração.</li></ul> |
| **Conexões de parceiros** | Permite que o colaborador envie as audiências criadas a partir das suas fontes para conexões de Parceiros para ativação. Ao habilitar essa opção, você pode conceder permissão de exportação para:<ul><li>**Todos os parceiros conectados** - Ao selecionar esta opção, você também pode **permitir conexões futuras de parceiros**, o que permite automaticamente a exportação de audiências para todos os parceiros de mídia com os quais a AppsFlyer DCP tem parceria.</li><li>**Apenas parceiros específicos**<ul><li>Ao selecionar parceiros específicos, você pode especificar ainda mais se permite que seu colaborador use apenas as conexões de ativação dele ou as suas (por exemplo, apenas a conexão Meta dele ou a sua conexão Meta).</li><li>Se você selecionar suas conexões, precisará escolher quais das suas contas conectadas o colaborador poderá usar (por exemplo, apenas a sua conexão Meta A, mas nenhuma das suas outras conexões Meta).</li></ul></li></ul>**Notas importantes:**<ul><li>Quando seus colaboradores estiverem prontos para <Anchor target="_blank" href="/marketers/pt/docs/data-collaboration-platform-dcp-build-and-activate-audiences#enviar-audiência-para-ativação">ativar audiências</Anchor> com base nas suas fontes, somente as conexões de parceiros para as quais você concedeu permissões estarão disponíveis para eles.</li><li>Se você não tiver concedido ao colaborador permissão para publicar ou exportar audiências, quando ele tentar ativar uma audiência, a solicitação de ativação será enviada a você para ser concluída.</li></ul> |
| **Exportar arquivo** | Permite que o colaborador exporte arquivos de audiência para o cloud bucket dele. |

## Permissões de acesso

As permissões de acesso definem os recursos que o seu colaborador pode acessar. Isso inclui a opção de conceder ao seu colaborador acesso às suas <Anchor target="_blank" href="/marketers/pt/docs/data-collaboration-platform-dcp-add-connections#create-data-identity-connections">conexões de Data & Identity (resolução de dados)</Anchor>, permitindo que ele use essas conexões para enriquecer as fontes dele.

**Observação:** Para conceder acesso, a conexão de Data & Identity relevante deve estar ativa.

## Especificações e limitações

Esta seção descreve algumas características e limitações importantes das permissões do DCP.

| Característica/limitação | Atenção |
| --- | --- |
| **Comportamento das audiências** | <ul><li>Se uma audiência for criada a partir de uma única fonte → as permissões de parceiros da fonte determinam quais parceiros de ativação estão disponíveis.</li><li>Se uma audiência for criada a partir de várias fontes com permissões de parceiros diferentes →<br />Aplica-se o menor denominador comum.<br />**Exemplo:** A fonte A permite todos os parceiros, a fonte B permite apenas a Meta → Somente a Meta estará disponível para ativação.</li></ul> |
| **Alterações nas permissões** | **Remoção total das permissões de ativação:**<ul><li>Qualquer audiência existente que utilize a fonte afetada expirará.</li><li>Novas audiências que utilizem a fonte se comportarão como hoje (exigirão novas permissões de ativação).</li></ul>**Remoção de um parceiro específico:**<ul><li>Se uma audiência existente estiver conectada apenas àquele parceiro removido → a audiência expirará.</li><li>Se a audiência estiver conectada a vários parceiros →<br />A audiência permanecerá ativa, mas a ativação com o parceiro removido não estará mais disponível.</li></ul> |

<div data-zendesk-anchors="data-permissions=permiss%C3%B5es-de-dados h_01KCKFQH3AVZY9V2KGZE06K3VT=permiss%C3%B5es-de-dados data-permissions-include=as-permiss%C3%B5es-de-dados-incluem h_01KCKJHVQ9EGTGAJ9NP021P42Q=as-permiss%C3%B5es-de-dados-incluem access-permissions=permiss%C3%B5es-de-acesso h_01KCKFQH3AFBDA50FJ0ZW9Q8J1=permiss%C3%B5es-de-acesso traits-and-limitations=especifica%C3%A7%C3%B5es-e-limita%C3%A7%C3%B5es h_01KCKFQH3AEM9WR95S2ZZ6NNNC=especifica%C3%A7%C3%B5es-e-limita%C3%A7%C3%B5es" />
