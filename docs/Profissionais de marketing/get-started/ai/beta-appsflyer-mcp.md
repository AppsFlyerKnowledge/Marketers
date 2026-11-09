---
title: '[Beta] MCP da AppsFlyer'
metadata:
  keywords:
    - Marketers
    - Beta feature
    - MCP
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-eden-locker
    - Marketers
    - MCP
  created_at: '2025-06-19T07:19:33Z'
  edited_at: '2026-11-03T01:20:36Z'
  id: 36349070304785
  locale: pt
  section: AI
  section_id: 36348470056081
  url: https://support.appsflyer.com/hc/pt/articles/36349070304785
---
<span class="af-tag af-tag--beta-feature">Beta feature</span>

> **Resumo:** Nosso MCP conecta seus dados da AppsFlyer a grandes modelos de linguagem (LLMs), como Claude, ChatGPT, Gemini CLI, Copilot CLI e VS Code. Faça perguntas, obtenha insights de performance e receba informações da AppsFlyer na sua conversa com a IA ou no seu ambiente de desenvolvimento.

<Embed title="[Beta] MCP da AppsFlyer" typeOfEmbed="youtube" url="https://www.youtube.com/embed/jAw7oocIx6o?si=-s107vTaTTwO076n" providerUrl="https://www.youtube.com" />

<div id="disclaimer" />

<Accordion title="Permissões">

**O MCP Server é um serviço em fase Beta, fornecido pela AppsFlyer para fins de avaliação.**

Ao usá-lo para se conectar a ferramentas de IA, você concorda que a AppsFlyer não tem nenhuma responsabilidade por tais ferramentas, seus outputs, resultados, performance, operação, legalidade ou confiabilidade. A AppsFlyer não controla, endossa ou verifica essas ferramentas ou seus resultados e se isenta de todas as garantias, expressas ou implícitas, relacionadas a elas. A AppsFlyer não é responsável pelo armazenamento, retenção, processamento ou uso de dados por tais ferramentas. É de sua exclusiva responsabilidade garantir o compliance com as leis aplicáveis e suas próprias políticas internas. Você declara que possui todos os direitos e consentimentos necessários para conectar essas ferramentas ao MCP e fornecer-lhes acesso aos seus dados. A utilização está sujeita aos termos do<Anchor target="_blank" href="https://www.appsflyer.com/legal/msa/">Contrato de Serviços Mestres</Anchor>, ou, se tiver sido assinado um acordo definitivo, os termos desse acordo. O serviço é oferecido no estado que se encontra apenas para os casos de uso contemplados. O uso fora desse escopo é de sua exclusiva responsabilidade.

</Accordion>

<div id="what-is-appsflyer-mcp" />

## O que é o MCP da AppsFlyer?

O MCP permite que você conecte LLMs de forma segura à plataforma da AppsFlyer, permitindo que você interaja com seus dados de marketing através de um chat simples. O MCP ajuda você a tomar decisões mais inteligentes e rápidas com base em dados em tempo real.

Com ele, você pode:

* Obter informações instantâneas sobre a performance, tendências e KPIs de uma campanha.
* Comparar métricas como ROAS, instalações e LTV.
* Crie links do OneLink e audite e solucione problemas em templates e links do OneLink.
* Audite e solucione problemas nas conexões de audiências.
* Relembrar passos de configuração e recuperar documentação de produtos.

<div id="set-up-appsflyer-mcp" />

## Configurar o MCP da AppsFlyer

Nosso MCP pode se conectar a chats, CLIs, IDEs, plataformas de automação e agentes self-hosted. A configuração depende do cliente utilizado e do método de autenticação compatível.

> 📘 **Atenção**
>
> Algumas plataformas podem exigir a aprovação do administrador para conectar os servidores do MCP. Se você não encontrar as opções de configuração descritas abaixo, entre em contato com sua equipe de TI ou com o administrador do seu workspace.

<div id="authentication-methods" />

## Métodos de autenticação

O MCP da AppsFlyer aceita dois métodos de autenticação. Use o método que corresponde à forma como você pretende se conectar ao nosso MCP.

| Método de autenticação | Usado por | Ideal para | Duração do acesso |
| --- | --- | --- | --- |
| Login OAuth pelo navegador | Gemini CLI, Copilot CLI, ChatGPT, Claude.ai e Claude Desktop | Perguntas ad hoc, análises exploratórias e relatórios pontuais | Válido por 7 dias a partir da conexão. É necessário se autenticar novamente ao final da sessão. |
| Autenticação por token Bearer | Claude Code, plataformas de automação, agentes self-hosted e integrações | Automações, tarefas agendadas, agentes em segundo plano e fluxos de trabalho não interativos | Válido até ser revogado manualmente |

<div id="browser-based-oauth-login" />

### Login OAuth pelo navegador

O login OAuth pelo navegador permite que você se conecte interativamente através do seu navegador. Ao se conectar, o cliente MCP abre uma janela do navegador e solicita que você faça login na AppsFlyer. Depois de aprovar o acesso, o cliente se conecta à sua conta da AppsFlyer.

Use esse método para sessões interativas, análises exploratórias e relatórios pontuais.

<div id="bearer-token-authentication" />

### Autenticação por token Bearer

A autenticação por token Bearer permite que ferramentas não interativas se conectem ao MCP da AppsFlyer por meio de um token do MCP. O token é incluído no cabeçalho da solicitação:

```http
Cabeçalho de autorização: Bearer <YOUR_MCP_TOKEN>
```

Use esse método para automações, tarefas agendadas, agentes em segundo plano e integrações que não podem fazer login pelo navegador.

Para criar um token, acesse **Menu da conta > Central de segurança > Tokens da AppsFlyer** e crie um token do MCP.

<div id="set-up-by-client" />

## Configurar por cliente

<div id="h_claude-ai-and-claude-desktop" />

<Accordion title="Claude.ai e Claude Desktop">

Use o Claude.ai e o Claude Desktop com login OAuth pelo navegador. Estas instruções se aplicam ao Claude na web e no desktop.

<div id="note-1" />

> 📘 **Atenção**
>
> Para usuários dos planos Team e Enterprise, somente os proprietários ou administradores podem adicionar integrações para toda a empresa.

<div id="set-up-claude-chat-and-cowork" />

#### Configurar o Claude.ai e o Claude Desktop

1. Clique no seu nome no canto inferior esquerdo e selecione **Configurações**. Ou, em um novo chat, clique em **Pesquisa e ferramentas** > **Gerenciar conectores**.
2. Abra a aba <Anchor target="_blank" href="https://claude.ai/settings/integrations">Conectores</Anchor>.
3. Vá para **Organization connectors**.
4. Na seção de conectores, clique em **Adicionar conector**.
5. Insira as seguintes informações sobre o conector:
   * **Nome do conector:** AppsFlyer
   * **URL do Conector:** `https://mcp.appsflyer.com/auth/mcp`
6. Clique em **Adicionar**.
7. Vá para **Your connectors**.
8. Na seção conectores, clique em **Connect** ao lado da conexão da AppsFlyer.
9. Faça login na AppsFlyer quando solicitado.

<div id="test-the-claude-connection" />

#### Teste a conexão com o Claude

1. Em qualquer janela do chat, clique no botão de configurações.   
   <Image align="center" alt="" src="https://files.readme.io/5f27783a0743f9005c5df4f580455777aa3ef612feb220d1058664ee63431cf3-46334217789073.png" width="25%" />
2. Se o MCP da AppsFlyer estiver configurado corretamente, as ferramentas da AppsFlyer aparecem no menu.

<div id="note-2" />

> 📘 **Atenção**
>
> **Comece mais rápido com o Cowork: salve como uma Skill.** Se a sua equipe trabalha no Claude Cowork, use o <Anchor target="_blank" href="https://github.com/AppsFlyerKnowledge/appsflyer-ai-agents-examples/tree/main/Claude/AppsFlyer%20Cowork%20Starter%20Kit">kit inicial do Claude Cowork para profissionais de marketing</Anchor> para configurar tudo mais rapidamente. O kit inicial inclui um plano de ativação, modelos prontos para uso e prompts de copiar e colar para trabalhar com seus dados da AppsFlyer por meio de IA desde o primeiro dia, para que você não precise criar seus primeiros fluxos de trabalho, relatórios ou briefs do zero.

</Accordion>

<div id="h_claude-code" />

<Accordion title="Claude Code">

Use o Claude Code com autenticação por token Bearer para automação, agendamento e fluxos de trabalho não interativos.

<div id="add-appsflyer-mcp-to-claude-code" />

#### Adicione o MCP da AppsFlyer ao Claude Code

1. Na AppsFlyer, acesse **Menu da conta > Central de segurança > Tokens da AppsFlyer**.
2. Crie um token do MCP.
3. No terminal, adicione o MCP Server da AppsFlyer:

   ```bash
   claude mcp add-json appsflyer '{"type":"http","url":"https://mcp.appsflyer.com/auth/mcp","headers":{"Authorization":"Bearer YOUR_APPSFLYER_MCP_TOKEN"}}'
   ```
4. Inicie o Claude Code:

   ```bash
   claude .
   ```
5. Verifique se o servidor do MCP foi adicionado:

   ```bash
   claude mcp list
   ```
6. Confirme se `appsflyer` aparece na lista de servidores configurados.
7. Faça uma pergunta sobre a AppsFlyer. Exemplo:

   ```text
   Quais aplicativos estão na minha conta da AppsFlyer?
   ```

   ```text
   Quais foram meus principais canais de mídia nos EUA na semana passada para "Mypets.android.com"?
   ```

   ```text
   Faça um resumo da performance de "Mypets.android.com" no último dia, segmentado por campanha.
   ```

</Accordion>

<div id="h_cursor-ide" />

<Accordion title="Cursor IDE">

Use o Cursor IDE para conectar o MCP da AppsFlyer a partir do seu ambiente de desenvolvimento local.

1. Crie ou abra um arquivo de configuração, dependendo do seu escopo:
   * **Configuração global:**`~/.cursor/mcp.json`
   * **Configuração específica do projeto:** `.cursor/mcp.json`
2. Adicione a seguinte entrada ao campo `mcpServers` em seu arquivo JSON:

   ```json
   {
     "mcpServers": {
       "appsflyer": {
         "url": "https://mcp.appsflyer.com/auth/mcp"
       }
     }
   }
   ```
3. Reinicie o Cursor IDE para aplicar a nova configuração.
4. Quando solicitado, faça a autenticação para acessar os serviços do MCP da AppsFlyer.

</Accordion>

<div id="h_vs-code" />

<Accordion title="VS Code">

1. Insira `Cmd+Shift+P` ou `Ctrl+Shift+P` para abrir a paleta de comandos.
2. Selecione **Configurar servidores do MCP**.
3. Em `.vscode/mcp.json`, adicione a configuração do MCP Server da AppsFlyer:

   ```json
   {
     "servers": {
       "appsflyer": {
         "url": "https://mcp.appsflyer.com/auth/mcp"
       }
     }
   }
   ```
4. Salve o arquivo e reinicie o Copilot Chat.

</Accordion>

<div id="h_chatgpt" />

<Accordion title="ChatGPT">

Existem duas formas de usar o ChatGPT com o MCP da AppsFlyer.

* [Custom GPT:](#adicione-o-custom-gpt-à-appsflyer) ideal para acesso simples a um assistente da AppsFlyer.
* [MCP no ChatGPT:](#adicione-o-mcp-da-appsflyer-no-chatgpt) ideal para usuários que desejam levar os dados da AppsFlyer para conversas do ChatGPT.

<div id="add-the-appsflyer-custom-gpt" />

#### Adicione o Custom GPT à AppsFlyer

1. Clique em <Anchor target="_blank" href="https://chatgpt.com/g/g-68b6a92eb8e0819194cbb81e1e635c0d-appsflyer">AppsFlyer Custom GPT</Anchor>.
2. Salve o GPT na barra lateral para facilitar o acesso.
3. Abra o Custom GPT.
4. Faça uma pergunta. Exemplo:

   ```text
   Mostre a performance da minha campanha na Meta da semana passada.
   ```

<div id="add-appsflyer-mcp-in-chatgpt" />

#### Adicione o MCP da AppsFlyer no ChatGPT

<div id="note-3" />

> 📘 **Atenção**
>
> Pode ser necessária uma configuração por um administrador para adicionar e publicar um conector na sua organização.

1. Adicione um conector e publique-o na sua empresa.
2. Insira as seguintes informações sobre o conector:
   * **Nome:** MCP da AppsFlyer
   * **URL:** `https://mcp.appsflyer.com/auth/mcp`
   * **Autenticação:** OAuth
3. Para se conectar pela primeira vez, acesse **Configurações > Aplicativos e fontes > MCP da AppsFlyer**.
4. Conecte-se ao MCP da AppsFlyer.
5. Siga as etapas para se conectar e fazer login com suas credenciais da AppsFlyer.

Depois da configuração, abra um chat, selecione **Fontes** ou **Conectores** e ative a conexão com a AppsFlyer.

Por motivos de segurança, o MCP é desconectado aproximadamente a cada 10 horas. Para se reconectar, repita o fluxo da conexão.

</Accordion>

<div id="h_gemini-cli" />

<Accordion title="Gemini CLI">

Use o Gemini CLI com o login OAuth pelo navegador.

<div id="add-appsflyer-mcp-to-gemini-cli" />

#### Adicione o MCP da AppsFlyer ao Gemini CLI

1. No terminal, adicione o MCP Server da AppsFlyer:

   ```bash
   gemini mcp add appsflyer https://mcp.appsflyer.com/auth/mcp -t http
   ```
2. Inicie o Gemini CLI:

   ```bash
   gemini
   ```
3. No prompt do Gemini CLI, insira:

   ```text
   auth
   ```
4. Complete o fluxo de autenticação no seu navegador e depois volte ao terminal.
5. Faça uma pergunta sobre a AppsFlyer. Exemplo:

   ```text
   Quais aplicativos estão na minha conta da AppsFlyer?
   ```

<div id="troubleshoot-gemini-cli-authentication" />

#### Resolução de problemas na autenticação do Gemini CLI

Se a autenticação falhar, inicie o Gemini CLI no modo de depuração:

```bash
GEMINI_LOG_LEVEL=debug gemini
```

Depois insira `auth` novamente no prompt do Gemini CLI.

</Accordion>

<div id="h_copilot-cli" />

<Accordion title="Copilot CLI">

Use o Copilot CLI com o login OAuth pelo navegador.

<div id="add-appsflyer-mcp-to-copilot-cli" />

#### Adicione o MCP da AppsFlyer ao Copilot CLI

1. Abra o terminal.
2. Inicie o Copilot CLI:

   ```bash
   copilot
   ```
3. Se você não tiver feito login, digite o seguinte comando no prompt do Copilot CLI:

   ```text
   /login
   ```
4. Conclua o login pelo navegador.
5. No prompt do Copilot CLI, digite:

   ```text
   /mcp add
   ```
6. Insira as seguintes informações sobre o servidor do MCP:

| Campo | Valor |
| --- | --- |
| Nome do servidor | `appsflyer` |
| Tipo de servidor | `HTTP` |
| a URL | `https://mcp.appsflyer.com/auth/mcp` |
| Ferramentas | `*` |

7. Pressione **Ctrl+S** para salvar a configuração.
8. Quando solicitado, complete o fluxo de autenticação da AppsFlyer no seu navegador.
9. Voltar ao terminal.
10. Faça uma pergunta sobre a AppsFlyer. Exemplo:

    ```text
    Quais aplicativos estão na minha conta da AppsFlyer?
    ```

</Accordion>

<div id="h_third-party-and-self-hosted-platforms" />

<Accordion title="Plataformas terceiras e self-hosted">

Use um token de MCP para autenticar sistemas de terceiros ou self-hosted com o MCP da AppsFlyer. Isso permite a automação e integrações de IA com plataformas como n8n, Make ou seus próprios agentes de LLM.

O token do MCP é um token Bearer no nível da conta que herda as permissões do administrador que o criou. Você pode acessá-lo e gerenciá-lo em <Anchor target="_blank" href="/marketers/pt/docs/managing-appsflyer-tokens">Central de segurança → Tokens da AppsFlyer</Anchor>.

<div id="mcp-connection-details" />

#### Detalhes da conexão do MCP

Para conectar sua plataforma de automação ou agente ao AppsFlyer MCP, use a seguinte configuração:

* **Tipo de autenticação:** Bearer Token
* **URL base / endpoint:** `https://mcp.appsflyer.com/auth/mcp`
* **Token Bearer:** Seu token do MCP

<div id="note-4" />

> 📘 **Atenção**
>
> Nunca compartilhe ou publique o seu token publicamente. Ele é uma credencial privada. Seu token do MCP concede acesso direto ao ambiente MCP.

<div id="example-use-cases" />

#### Exemplos de casos de uso

| Categoria | Exemplo |
| --- | --- |
| Agentes personalizados | Crie um agente de IA que usa o MCP para buscar dados, analisá-los e enviar recomendações. |
| Integrações de LLM | Permita que um LLM self-hosted consulte as métricas de performance da campanha via MCP. |

</Accordion>

<div id="h_other-platforms" />

<Accordion title="Outras plataformas">

O MCP da AppsFlyer também oferece suporte a conexões com as seguintes plataformas:

| Platform | URI de redirecionamento | Referência |
| --- | --- | --- |
| Microsoft 365 Copilot | `https://teams.microsoft.com/api/platform/v1.0/oAuthRedirect` | <Anchor target="_blank" href="https://github.com/MicrosoftDocs/m365copilot-docs/blob/main/docs/plugin-mcp-apps.md">Microsoft 365 Copilot: plug-ins & aplicativos MCP</Anchor> |
| Microsoft Azure AI Foundry | `https://cas.services.azure-ai.net/app/oauth/redirect` | <Anchor target="_blank" href="https://learn.microsoft.com/en-us/azure/foundry/agents/how-to/mcp-authentication">Azure AI Foundry: autenticação MCP</Anchor> |
| Microsoft Copilot Studio / Power Platform (conector personalizado) | `https://global.consent.azure-apim.net/redirect/{connector-slug}` | <Anchor target="_blank" href="https://learn.microsoft.com/en-us/graph/mcp-server/use-enterprise-mcp-server-copilot-studio">Usar um servidor MCP empresarial no Copilot Studio</Anchor> |
| Google Gemini Enterprise | `https://vertexaisearch.cloud.google.com/oauth-redirect` | <Anchor target="_blank" href="https://docs.cloud.google.com/gemini/enterprise/docs/connectors/custom-mcp-server/set-up-custom-mcp-server">Configurar um servidor MCP personalizado</Anchor> |
| Amazon Quick (antigo QuickSight) | `https://{region}.quicksight.aws.amazon.com/sn/oauthcallback` | <Anchor target="_blank" href="https://docs.aws.amazon.com/quick/latest/userguide/mcp-integration.html">Integração MCP – Amazon Quick</Anchor> |

Estamos expandindo continuamente esta lista à medida que validamos e documentamos mais plataformas. Se a plataforma que você está usando não estiver listada aqui, entre em contato com seu CSM ou envie um e-mail para [hello@appsflyer.com](mailto:hello@appsflyer.com) e ajudaremos você a se conectar.

</Accordion>

<div id="h_use-multiple-accounts-or-agencies" />

<Accordion title="Usar múltiplas contas ou agências">

O MCP da AppsFlyer conecta-se a uma conta da AppsFlyer por vez.

<div id="switch-between-accounts-browser-based-oauth" />

#### Alternar contas (OAuth pelo navegador)

Se você gerencia várias contas da AppsFlyer no mesmo e-mail, é possível mudar a conta conectada ao MCP:

1. Na AppsFlyer, defina a conta que você deseja conectar como sua conta principal.
2. Faça login novamente no seu cliente MCP.

Você não pode visualizar ou comparar várias contas em uma única conexão.

<div id="connect-multiple-accounts-simultaneously-bearer-token" />

#### Conectar várias contas simultaneamente (token Bearer)

Para se conectar a várias contas ao mesmo tempo (por exemplo, para agências), use um fluxo de múltiplos agentes em vez do login OAuth pelo navegador:

1. Para cada conta, crie um token do MCP em **Menu da conta > Central de segurança > Tokens da AppsFlyer**.
2. Na sua plataforma de agente, conecte cada conta separadamente usando seu próprio token Bearer.

Veja um exemplo desse fluxo <Anchor target="_blank" href="https://www.youtube.com/watch?v=o5oK-yWuE5E">neste vídeo</Anchor>.

</Accordion>

<div id="use-appsflyer-mcp" />

## Usar o MCP da AppsFlyer

<div id="use-cases-and-prompts" />

### Casos de uso e prompts

O MCP da AppsFlyer oferece um conjunto de ferramentas e recursos projetados para ajudar a recuperar análises de marketing, insights de performance e informações de configuração.

<div id="important" />

> 🚧 **Importante!**
>
> As respostas geradas através do MCP da AppsFlyer só são consideradas confiáveis quando usadas para os casos de uso listados abaixo. As respostas fora desses casos de uso não foram validadas pela AppsFlyer e podem não ser precisas. Não podemos garantir a precisão ou exatidão das respostas geradas por IA que não se enquadram no escopo pretendido da integração do MCP.

Alguns exemplos de casos de uso e prompts são:

<div id="analyze-performance" />

<Accordion title="Análise da performance">

Explore dados agregados da sua performance de marketing em tempo real. Você pode identificar campanhas de alta e baixa performance, fazer comparações, identificar tendências e descobrir insights para ajudar a orientar sua tomada de decisões.

**Prompt:** "Na semana passada, quais foram as fontes de mídia que mais trouxeram resultados nos EUA para Mypets.android.com?"

**Resposta esperada da IA:** A IA recupera quais fontes de mídia tiveram uma alta performance, incluindo instalações, receita e ROAS.

**Prompt:** "Qual é a melhor campanha em termos de ROAS, sendo que o total de instalações é de pelo menos 5.000?"

**Resposta esperada da IA:** A IA identifica e classifica as campanhas que atendem aos critérios de acordo com os insights de performance.

**Prompt:** "Quantas instalações tivemos ontem na China para o app Mypets.android.com?"

**Resposta esperada da IA:** A IA busca o número de instalações na China para esse dia e aplicativo.

**Prompt:** "Faça um resumo da performance do Mypets.android.com no último dia, segmentado por campanha."

**Resposta esperada da IA:** A IA responde com um relatório de performance segmentado por campanha para esse aplicativo.

**Prompt:** "Compare a retenção D1 entre a semana passada e a semana anterior, agrupando por fonte de mídia."

**Resposta esperada da IA:** A IA realiza uma comparação das taxas de retenção D1, agrupadas por fonte de mídia.

<div id="note-5" />

> 📘 **Atenção**
>
> **Comece mais rápido com o Cowork: salve como uma Skill.** Se a sua equipe trabalha no Claude Cowork, use o <Anchor target="_blank" href="https://github.com/AppsFlyerKnowledge/appsflyer-ai-agents-examples/tree/main/Claude/AppsFlyer%20Cowork%20Starter%20Kit">kit inicial do Claude Cowork para profissionais de marketing</Anchor> para configurar tudo mais rapidamente. O kit inicial inclui um plano de ativação, modelos prontos para uso e prompts de copiar e colar para trabalhar com seus dados da AppsFlyer por meio de IA desde o primeiro dia, para que você não precise criar seus primeiros fluxos de trabalho, relatórios ou briefs do zero.

</Accordion>

<div id="h_analyze-creative-performance" />

<Accordion title="Analise a performance dos criativos">

<Embed title="[Beta] MCP da AppsFlyer" typeOfEmbed="youtube" url="https://www.youtube.com/embed/FdZhZ497684" providerUrl="https://www.youtube.com" />

Explore dados de performance no nível do criativo (gasto, instalações, CPI, ROAS, cohorts de retenção e de receita) em networks, campanhas e aplicativos. Analise por nome do criativo, tipo, tamanho, duração, idade, end card, evento in-app (por exemplo, nível alcançado, primeiro depósito ou compra) e muito mais. Use essas informações para identificar seus criativos com melhor e pior performance, detectar a fadiga criativa com antecedência e exibir prévias dos assets junto com os números.

**Prompt:** "Quais foram os meus criativos com melhor performance por ROAS no mês passado para Mypets.android.com?"

**Resposta esperada da IA:** A IA recupera os principais criativos classificados por ROAS, incluindo gasto, instalações e ROAS de cada um.

**Prompt:** "Qual tipo de criativo (vídeo, imagem, HTML ou texto) teve o melhor CPI nos EUA neste trimestre?"

**Resposta esperada da IA:** A IA detalha a performance por tipo de criativo e retorna o CPI de cada um, destacando o com melhor performance.

**Prompt:** "Mostre os criativos da Meta que estão em execução há mais de 2 semanas e apresentam queda de ROAS (possível fadiga)."

**Resposta esperada da IA:** A IA retorna uma tendência diária de ROAS por criativo e sinaliza os criativos com tendência de queda contínua.

**Prompt:** "Mostre meus 5 principais criativos por cohort de receita do 7º dia para Mypets.android.com, com prévias."

**Resposta esperada da IA:** A IA retorna os 5 principais criativos classificados por receita no 7º dia, incluindo links dos assets para que você possa ver cada criativo junto com seus números.

**Prompt:** "Qual end card está impulsionando a melhor retenção para meus criativos em vídeo e como isso varia de acordo com a idade do criativo?"

**Resposta esperada da IA:** A IA detalha a retenção por tipo de end card e idade do criativo, destacando quais combinações têm a melhor performance.

**Prompt:** "Qual campanha teve o maior custo de instalação no mês passado e quais foram os 3 principais criativos que o impulsionaram?"

**Resposta esperada da IA:** A IA identifica a campanha de maior custo e classifica seus criativos por gasto ou instalações.

**Prompt:** "Quais criativos impulsionaram o maior número de primeiros depósitos no mês passado e qual foi o custo por primeiro depósito de cada um?"

**Resposta esperada da IA:** A IA detalha os eventos de primeiro depósito por criativo e retorna volume e custo por evento, junto com gasto e instalações.

**Prompt:** "Mostre ROAS e eventos de avanço de nível por tipo de criativo nos últimos 30 dias na Meta."

**Resposta esperada da IA:** A IA retorna o ROAS e a contagem de eventos de avanço de nível por tipo de criativo, destacando o tipo com melhor performance.

</Accordion>

<div id="h_analyze-incrementality-experiments" />

<Accordion title="Analise a incrementalidade em experimentos de UA">

Recupere seus experimentos de incrementalidade de UA e os resultados deles, incluindo lift, conversões incrementais, fator de incrementalidade e custo por conversão incremental. Use essas informações para ver quais campanhas impulsionaram um crescimento real e incremental e onde realocar o orçamento.

**Prompt:** "Quais experimentos de incrementalidade foram executados para Mypets.android.com nos EUA no último trimestre?"

**Resposta esperada da IA:** A IA retorna os experimentos correspondentes a esse aplicativo, país e intervalo de datas, incluindo o status de cada experimento, o canal de mídia, o evento mensurado e o período de teste.

**Prompt:** "Resuma os resultados do experimento de incrementalidade 12345"

**Resposta esperada da IA:** A IA retorna o lift do experimento, as conversões incrementais, o fator de incrementalidade em comparação com a atribuição clássica e o custo por conversão incremental, com o intervalo de credibilidade no nível de confiança do experimento.

**Prompt:** "Compare o custo por ação incremental e o ROAS incremental em todos os meus experimentos de incrementalidade nos últimos 6 meses."

**Resposta esperada da IA:** A IA compara lado a lado a eficiência dos seus experimentos concluídos nos últimos 6 meses, destacando quais campanhas geraram o maior valor incremental por dólar investido em anúncios.

</Accordion>

<div id="analyze-skan-performance" />

<Accordion title="Analise a performance da SKAN">

Obtenha informações sobre a performance da sua campanha no iOS usando a SKAdNetwork da Apple. Identifique campanhas de alta performance e analise tendências de KPI para apoiar sua tomada de decisões.

**Prompt:** "Qual foi o ROI por rede no último mês?"

**Resposta esperada da IA:** A IA recupera os resultados de ROI para o período selecionado e destaca as principais redes.

**Prompt:** "Quais campanhas têm o menor CPI?"

**Resposta esperada da IA:** A IA identifica as campanhas com um CPI mais baixo, classificando aquelas que têm a melhor performance.

**Prompt:** "Quais foram as taxas de conversão semanais para o evento af\_subscribed no último mês?"

**Resposta esperada da IA:** A IA fornece uma análise semanal das taxas de conversão para o evento e indica a tendência geral.

**Prompt:** "Quais redes têm taxas de 'null' mais altas e, nesse contexto, quais campanhas mostram taxas de 'null' mais altas?"

**Resposta esperada da IA:** A IA identifica as redes com taxas de 'null' mais elevadas e aponta as campanhas que mais contribuem para essas taxas.

</Accordion>

<div id="onelink-management" />

<Accordion title="Gerenciamento do OneLink">

Crie links do OneLink, consulte e audite templates e Smart Banners para oferecer roteamento consistente e jornadas de usuário precisas. O MCP pode ajudar você a solucionar problemas, verificar a configuração de links em escala e criar novos links a partir de uma conversa.

**Prompt:** "Crie um link do OneLink no template HolidayPush2025 para nossa newsletter por e-mail, com o nome da campanha black\_friday e o valor do deep link sale\_page."

**Resposta esperada da IA:** A IA encontra o template e o domínio dele, resume os parâmetros do link e pede que você confirme. Depois que você aprova, ela cria o link e retorna a URL curta.

**Prompt:** "Verifique o template HolidayPush2025 e mostre todos os links com parâmetros."

**Resposta esperada da IA:** A IA retorna uma tabela CSV com links curtos e valores de parâmetros associados.

**Prompt:** "Por que esse OneLink redireciona para a App Store para usuários existentes?"

**Resposta esperada da IA:** A IA retorna um insight para solucionar o problema, combinando parâmetros de link e lógica de fallback.

**Prompt:** "Liste todos os OneLinks com QR codes para o aplicativo TravelBuddy."

**Resposta esperada da IA:** A IA retorna uma lista de OneLinks gerados com links com QR codes e metadados associados.

**Prompt:** "Quais parâmetros, recursos e comportamento de redirecionamento este link tem: https://mypets.onelink.me/abc123?"

**Resposta esperada da IA:** A IA retorna os parâmetros do link por categoria, seus recursos habilitados, como deep linking e retargeting, e como ele redireciona os usuários por dispositivo, plataforma e status de instalação.

**Prompt:** "Liste todos os Smart Banners ativos da minha conta."

**Resposta esperada da IA:** A IA retorna os metadados do banner, incluindo ID do banner, nome, grupo, site e tipo de banner.

**Prompt:** "Compare a performance dos meus dois criativos de Smart Banner nos últimos 30 dias."

**Resposta esperada da IA:** A IA retorna impressões, cliques e instalações dos banners selecionados lado a lado.

</Accordion>

<div id="knowledge-base-and-developer-support" />

<Accordion title="Base de conhecimento e suporte a desenvolvedores">

Acesse rapidamente a documentação da AppsFlyer e recursos do DevHub. Obtenha respostas sobre a configuração do SDK, o comportamento do produto e a lógica de mensuração diretamente no chat.

**Prompt:** "Como configuro a desduplicação de eventos in-app no Android?"

**Resposta esperada da IA:** A IA fornece as etapas de configuração, snippets de código e práticas recomendadas.

**Prompt:** "Em qual dos meus aplicativos eu tenho uma janela de de lookback diferente?"

**Resposta esperada da IA:** A IA explica as últimas regras de atribuição específicas da plataforma.

**Prompt:** "Qual é a melhor maneira de otimizar o ROAS do meu aplicativo usando a AppsFlyer?"

**Resposta esperada da IA:** A IA descreve pontos estratégicos como segmentação, otimização de parceiros e melhores práticas de mensuração de LTV.

</Accordion>

<div id="apps-management" />

<Accordion title="Gestão de aplicativos">

Recupere os principais detalhes da configuração de aplicativos como janelas de atribuição, timeouts de sessões, configurações de reengajamento e mais. Use essas informações para verificar e comparar as configurações de aplicativos em todo o seu portfólio.

**Prompt:** "Qual é a janela de atribuição definida para meus aplicativos de jogos?"

**Resposta esperada da IA:** A IA retorna uma lista de aplicativos com as janelas de atribuição configuradas, destacando quaisquer desvios do padrão.

**Prompt:** "Qual é a janela de lookback de atribuição para instalações do TikTok?"

**Resposta esperada da IA:** A IA apresenta aplicativos com janelas de lookback fora do padrão e mostra seus valores configurados.

**Prompt:** "Liste todos os meus aplicativos do iOS que estão fixados e ativos."

**Resposta esperada da IA:** A IA retorna uma lista de aplicativos do iOS que estão fixados e ativos no momento, incluindo os IDs e nomes dos aplicativos.

Pouca atualização

**Resposta esperada da IA:** A IA responde com a configuração de timeout da sessão e explica seu impacto sobre o reengajamento.

</Accordion>

<div id="h_01M6DQ8W2JQ9ECH5VEZPRT7221" />

<Accordion title="Gerenciamento de integrações de parceiros">

Recupere o status e a configuração da integração de parceiros dos seus aplicativos, veja quais parceiros estão ativos, como eles estão configurados e se os mapeamentos de eventos e as configurações de atribuição estão definidos como esperado. Use isto para auditar a integridade da integração e solucionar problemas específicos de parceiros sem abrir a UI do AppsFlyer HQ.

<div id="note-6" />

> 📘 **Note**
>
> O gerenciamento de integrações de parceiros está atualmente somente para leitura. Você pode recuperar e auditar a configuração pelo MCP da AppsFlyer, mas as alterações ainda precisam ser feitas na UI do AppsFlyer HQ.

**Prompt:** "Quais parceiros estão ativos para Mypets.android.com?"

**Resposta esperada da IA:** A IA retorna uma lista de integrações de parceiros ativas para esse aplicativo, incluindo nome do parceiro, categoria do parceiro e plataforma.

**Prompt:** "Quais parceiros de tecnologia usamos para Mypets.android.com?"

**Resposta esperada da IA:** A IA retorna o subconjunto de integrações ativas classificadas como parceiros de tecnologia (integrações do tipo analytics) para esse aplicativo.

**Prompt:** "Qual janela de atribuição está configurada para a AppLovin neste aplicativo?"

**Resposta esperada da IA:** A IA retorna a janela de lookback de atribuição de instalação configurada para a integração do AppLovin.

**Prompt:** "Mostre a configuração completa do Moloco em Mypets.android.com."

**Resposta esperada da IA:** A IA retorna a configuração completa da integração, incluindo configurações de atribuição, controles de compartilhamento de dados e mapeamentos de eventos in-app.

</Accordion>

<div id="audiences-management" />

<Accordion title="Gestão do Audiences">

Tenha visibilidade sobre a estrutura das suas audiências, propriedades, conexões de parceiros e testes ativos. Monitore a integridade dos uploads, detecte falhas de conexão, identifique audiências obsoletas e descubra a configuração de cada audiência. Use essas informações para simplificar o gerenciamento de campanhas entre diferentes áreas.

**Prompt:** "Quais são todas as audiências ativas para o app FinancePro?"

**Resposta esperada da IA:** A IA retorna uma lista de audiências com metadados como data de criação, proprietário e parceiros.

**Prompt:** "Quem atualizou pela última vez a audiência Churned Users - Tier A?"

**Resposta esperada da IA:** A IA retorna o ID do usuário ou e-mail com a data/hora da última modificação.

**Prompt:** "Liste todas as audiências que estão em teste A/B com o Meta e TikTok."

**Resposta esperada da IA:** A IA retorna uma lista de audiências ativas com essa configuração de teste e porcentagens separadas.

**Prompt:** "Quero comparar a Moloco com o Google. Mostre todas as audiências conectadas ao Google."

**Resposta esperada da IA:** A IA retorna uma lista de audiências conectadas ao Google com seu status e configuração atuais.

Cabeçalho de autorização: Bearer `<YOUR_MCP_TOKEN>`

**Resposta esperada da IA:** A IA retorna todas as audiências ativas com seus parceiros conectados e status atual.

**Prompt:** "Mostre uma lista de todas as audiências ativas, seus parceiros conectados e suas divisões atuais."

**Resposta esperada da IA:** A IA retorna uma lista completa de audiências com cada conexão de parceiro e suas porcentagens separadas.

**Prompt:** "Alguma das minhas audiências da Meta está atualmente falhando ao fazer upload?"

**Resposta esperada da IA:** A IA retorna uma lista de audiências conectadas à Meta com falha no status de upload, incluindo a mensagem de erro de cada uma.

**Prompt:** "Quero ver minhas campanhas no TikTok. Quais audiências conectadas estão falhando e desde quando isso está acontecendo?"

**Resposta esperada da IA:** A IA retorna todos as audiências conectadas ao TikTok com falha no status e o horário do último upload realizado com sucesso.

**Prompt:** "Mostre todas as audiências que não tiveram sucesso no upload nos últimos 7 dias."

**Resposta esperada da IA:** A IA retorna uma lista de audiências sem sucesso no upload nos últimos 7 dias e o status atual das conexões.

</Accordion>

<div id="feedback-tool" />

<Accordion title="Ferramenta de feedback">

Envie um feedback sobre sua experiência com o MCP da AppsFlyer através da interface do assistente. Seu feedback nos ajudará a melhorar o produto.

**Prompt:** "As análises fornecidas na ferramenta de análise são incríveis e úteis para nossa tomada de decisão. Eu adoraria ver a mensuração de eventos in-app como uma opção na análise."

**Resposta esperada da IA:** A IA envia o feedback para a equipe de produto do MCP da AppsFlyer.

</Accordion>

<div id="cost-configuration-integration" />

<Accordion title="Integração de configuração de custos">

Tenha visibilidade e controle sobre seus dados de custo com o MCP para configuração de custos. Essa integração ajuda a maximizar a cobertura de custos, detectar falhas de integração e garantir que os dados de custo permaneçam completos e precisos em todas as ad networks.

**Prompt:** "Quais integrações de receita de anúncios estão ativas na minha conta da AppsFlyer?"

**Resposta esperada da IA:** A IA lista todas as integrações de receita de anúncios ativas na sua conta da AppsFlyer, incluindo aplicativos conectados e o status atual da integração.

**Prompt:** "Mostre os problemas das minhas integrações de receita de anúncios ativas."

**Resposta esperada da IA:** A IA mostra as integrações de receita de anúncios que tiveram problemas nos últimos 7 dias, classificadas por parceiro de mensuração, tipo de integração e aplicativo.

**Prompt:** "Quais integrações de custo devo conectar com base nos meus dados de atribuição recentes?"

**Resposta esperada da IA:** A IA mostra as ad networks que são compatíveis com a integração de custos, mas que ainda não estão conectadas, classificadas por volume de tráfego recente por aplicativo.

</Accordion>

<div id="ad-revenue-integrations" />

<Accordion title="Integrações de receita de anúncios">

Tenha visibilidade e controle sobre suas integrações de receita de anúncios usando o MCP da AppsFlyer. Você pode usar o MCP para confirmar quais integrações de receita de anúncios são permitidas, monitorar a integridade delas, detectar falhas com antecedência e manter o fluxo de dados de receita de anúncios constante entre seus aplicativos e parceiros de monetização.

**Prompt:** "Quais integrações de custo estão ativas na minha conta da AppsFlyer?"

**Resposta esperada da IA:** A IA lista todas as integrações de custo ativadas na sua conta da AppsFlyer, juntamente com os app IDs vinculados e o status atual.

**Prompt:** "Quero saber quais integrações de custo ativas apresentam problemas."

**Resposta esperada da IA:** A IA exibe uma lista de integrações de custo ativas que tiveram problemas nos últimos 7 dias, ordenadas por ad network e aplicativos conectados.

</Accordion>

<div id="user-management-and-role-control" />

<Accordion title="Gestão de usuários e controle de funções">

Relembre informações de usuários e funções da sua conta da AppsFlyer. Isso ajuda os administradores a manter uma base de dados de usuários organizada e a gerenciar os controles de acesso com eficiência.

**Prompt:** "Liste todos os usuários inativos que não fizeram login na AppsFlyer nos últimos 6 meses."

**Resposta esperada da IA:** A IA retorna os usuários inativos há mais de seis meses ou que nunca fizeram login, incluindo seus endereços de e-mail, funções e data/hora do último login.

**Prompt:** "Mostre todos os usuários agrupados por níveis de permissão e identifique todos os usuários que são administradores."

**Resposta esperada da IA:** A IA organiza os usuários por tipo de função e destaca administradores, incluindo os aplicativos associados e as permissões de acesso geográfico.

**Prompt:** "Um dos membros da equipe não consegue fazer login na AppsFlyer. Você pode verificar se o usuário existe e qual é o seu status?"

**Resposta esperada da IA:** A IA verifica se o usuário existe e retorna sua função atual, os aplicativos associados, a data do último login e as possíveis restrições de acesso.

**Prompt:** "Quais usuários têm acesso a mais de 5 aplicativos e quais são suas funções?"

**Resposta esperada da IA:** A IA retorna os usuários com acesso a vários aplicativos, suas funções e a lista completa de aplicativos que eles podem acessar.

</Accordion>

<div id="other-information" />

## Outras informações

<div id="h_privacy-and-security" />

<Accordion title="Segurança e privacidade">

Nosso MCP permite que a ferramenta de IA selecionada consulte os dados da AppsFlyer com base nas permissões existentes.

<div id="data-processing" />

#### Processamento de dados:

Nosso MCP atua como um proxy seguro. Ele busca os dados da AppsFlyer em tempo real e retorna os dados necessários para responder à consulta. O MCP não arquiva nem armazena resultados de consultas a longo prazo.

<div id="credentials" />

#### Credenciais

Seu login na AppsFlyer permite que o MCP faça chamadas à API em seu nome. Suas credenciais da AppsFlyer não são compartilhadas com a ferramenta de IA.

<div id="permissions" />

#### Authorization: Bearer

Nosso MCP utiliza suas permissões existentes. Os usuários só podem acessar os aplicativos e dados que eles já têm permissão para visualizar na AppsFlyer.

Não existe uma camada de permissões separada para configurar o acesso ao MCP.

<div id="read-and-write-access" />

#### Acesso de leitura e gravação

A maioria das ferramentas do MCP da AppsFlyer permite apenas leitura e consulta. A exceção é create\_onelink\_link, que cria links do OneLink na sua conta. Antes de um link ser criado, a IA mostra os detalhes dele e pede sua confirmação. Nada é criado sem a sua aprovação.

<div id="ai-provider-data-usage" />

#### Uso de dados dos fornecedores de IA

Os dados recuperados pelo MCP podem ser compartilhados com a ferramenta de IA selecionada para responder à sua consulta. Apenas os dados necessários para gerar a resposta são compartilhados.

A AppsFlyer não controla se a ferramenta de IA selecionada armazena, processa ou usa os dados para aprendizado. Revise os termos e políticas de uso de dados do seu fornecedor de IA antes de conectar o MCP.

<div id="certifications" />

#### Certificações

A AppsFlyer tem certificações ISO 27001, ISO 42001 e SOC 2. A ISO 42001 é a norma internacional para sistemas de gestão de IA.

</Accordion>

<div id="tool-mapping" />

<Accordion title="Mapeamento de ferramentas">

Por padrão, todas as ferramentas estão ativadas. Recomendamos que você mantenha-as ativadas para garantir total funcionalidade e evitar problemas durante o uso.

Cada ferramenta é mapeada para uma categoria funcional, como Analisar performance, gerenciar aplicativos ou gerenciar o OneLink. Algumas categorias podem incluir várias ferramentas.

Consulte a tabela abaixo para uma lista completa das ferramentas e suas categorias.

<table><thead><tr><th>Categoria</th><th>Ferramenta</th><th>Descrição</th></tr></thead><tbody><tr><td><a href="#analyze-performance">Análise da performance</a></td><td>fetch_aggregated_data</td><td>Recupere dados agregados do dashboard com os intervalos de datas, agrupamentos, métricas e filtros personalizados.</td></tr><tr><td><a href="#h_analyze-creative-performance">Analise a performance dos criativos</a></td><td>get_creative_performance</td><td>Recupera dados de performance agregados em nível de criativo (gasto, instalações, CPI, ROAS, retenção e cohorts de receita) em networks, campanhas e aplicativos, detalhados por nome, tipo, tamanho, duração, idade, end card, nome do evento in-app e muito mais. Inclui links de assets para prévias de criativos.</td></tr><tr><td rowspan="2"><a href="#analisar-experimentos-de-incrementalidade">Analisar incrementalidade para experiências de UA</a></td><td>incrementality_list_experiments</td><td>Lista experimentos de incrementalidade, filtrados por status, aplicativo, país, canal de mídia e intervalo de datas.</td></tr><tr><td>incrementality_get_experiment_results</td><td>Obtém os resultados de um experimento específico, incluindo lift, conversões incrementais, fator de incrementalidade e custo por conversão incremental.</td></tr><tr><td rowspan="2"><a href="#gerenciamento-de-aplicativos">Gerenciamento de aplicativos</a></td><td>get_apps</td><td>Lista todos os aplicativos permitidos organizados por status fixado e não fixado, com solicitações de transferência.</td></tr><tr><td>get_app_settings</td><td>Fornece as definições de configuração do aplicativo, incluindo janelas de atribuição, controles de privacidade, gestão de sessão e configurações específicas da plataforma.</td></tr><tr><td><a href="#h_01M6DQ8W2JQ9ECH5VEZPRT7221">Gerenciamento de integrações de parceiros</a></td><td>get_app_partner_integration_configuration</td><td>Obtém a configuração completa de uma integração de parceiro específica, incluindo configurações de atribuição, compartilhamento de dados e mapeamentos de eventos in-app.</td></tr><tr><td><a href="#cost-configuration-integration">Integração de configuração de custos</a></td><td><p>get_active_cost_integrations</p><p>list_cost_supported_media_source</p></td><td>Oferece uma visão geral do status das integrações de custo ativas e ausentes na sua conta.</td></tr><tr><td><a href="#ad-revenue-integrations">Integrações de receita de anúncios</a></td><td><p>list_adrevenue_supported_media_sources</p><p>obter_integrações_ativas_de_receita_de_anúncios</p></td><td>Verifica quais são as integrações ativadas, monitora a integridade, detecta falhas de configuração e ajuda a manter a consistência dos dados de receita de anúncios.</td></tr><tr><td><a href="#analyze-skan-performance">Performance do SKAN</a></td><td>skan_get_app_data</td><td>Recupera dados agregados de performance do SKAN, agrupados por rede, campanha ou evento em intervalos de datas personalizados.</td></tr><tr><td rowspan="4"><a href="#onelink-management">Gerenciamento do OneLink</a></td><td>get_onelink_templates</td><td>Lista todos os templates do OneLink.</td></tr><tr><td>get_onelink_template_links</td><td>Obtenha todos os links do OneLink criados a partir de um template específico.</td></tr><tr><td>get_onelink_details</td><td>Fornece detalhes de configuração para um OneLink específico.</td></tr><tr><td>discover_OneLink</td><td>Descobre os parâmetros, os recursos e o comportamento de redirecionamento de um link a partir de uma URL curta ou longa.</td></tr><tr><td> </td><td>create_onelink_link</td><td>Cria um novo link curto em um template existente do OneLink. Exige a confirmação do usuário antes que o link seja criado.</td></tr><tr><td> </td><td>list_smart_banners</td><td><p>Lista os Smart Banners da conta com metadados, com filtros por status ativo e data de criação.</p><p><strong>Atenção:</strong> list_smart_banners retorna no máximo 30 banners por conta, ordenados com os banners ativos primeiro e depois pelos modificados mais recentemente.</p></td></tr><tr><td> </td><td>obter_performance_do_smart_banner</td><td>Obtém a performance do Smart Banner para IDs de banners específicos, com granularidade total ou diária.</td></tr><tr><td rowspan="3"><a href="#audiences-management">Gestão do Audiences</a></td><td>list_active_audiences</td><td>Acesse uma lista de todas as audiências ativas que são calculadas diariamente.</td></tr><tr><td>list_audiences_connections</td><td>Lista as integrações de parceiros de anúncios para dados de audiências.</td></tr><tr><td>get_audience_connections</td><td>Obtenha conexões de parceiros para uma audiência específica.</td></tr><tr><td><a href="#knowledge-base-and-developer-support">Base de conhecimento e suporte a desenvolvedores</a></td><td>get_public_knowledge</td><td>Faz uma pesquisa por documentação da Central de ajuda e do DevHub da AppsFlyer.</td></tr><tr><td><a href="#feedback-tool">Ferramenta de feedback</a></td><td>send_feedback</td><td>Envie comentários sobre as ferramentas ou o sistema.</td></tr><tr><td><a href="#user-management-and-role-control">Gerenciamento de usuários e controle de funções</a></td><td>get_users</td><td>Lista usuários e funções na AppsFlyer.</td></tr></tbody></table>

</Accordion>

<div id="traits-and-limitations" />

<Accordion title="Características e limitações">

| Caraterística | Descrição |
| --- | --- |
| Uso de múltiplas contas | O MCP da AppsFlyer usa apenas dados da conta padrão. Para mudar de conta ou conectar várias contas ao mesmo tempo, [use múltiplas contas ou agências](#h_use-multiple-accounts-or-agencies). |
| Links do OneLink | <ul><li>**Criação de links do OneLink:**</li></ul><ul><li>Até 10 links podem ser criados por dia, por conta.</li><li>Os links são criados em um template existente do OneLink.</li></ul><ul><li>Inclui apenas links criados através da página de gerenciamento do OneLink (sem API, SDK ou links em massa).</li><li>O Discover OneLink (discover\_onelink) não tem essa restrição. Ele oferece suporte a todos os tipos de link da AppsFlyer, incluindo links de plataforma única (legados), domínios de marca e links criados pela UI, API, SDK ou criação em massa.</li></ul> |
| Integrações com parceiros | <ul><li>Os detalhes de configuração não estão disponíveis para integrações de parceiros do tipo agência por meio desta ferramenta.</li><li>As integrações de parceiros do tipo agência e do tipo rede de anúncios não são compatíveis.</li><li>As configurações de permissões não estão disponíveis.</li></ul> |
| Limites de taxa | <ul><li>Analytics: 20 solicitações por minuto</li><li>Audiences. 350 pedidos por minuto</li><li>SKAN: Até 10.000 linhas por consulta</li></ul> |
| Limite de linhas | As consultas de performance de criativos retornam no máximo 300 linhas por solicitação. No momento, a paginação não é suportada. Se uma consulta corresponder a mais de 300 criativos ou campanhas, restrinja-a por intervalo de datas, canal de mídia ou outro filtro para ficar dentro do limite. |
| Intervalo de datas | <ul><li>Analytics: 3 anos</li><li>SKAN: Máximo de 90 dias por pedido</li></ul> |
| Agrupamentos | <ul><li>Analytics: 4 agrupamentos por solicitação</li><li>SKAN: Conforme disponível no <Anchor target="_blank" href="/marketers/pt/docs/skadnetwork-skan-overview-dashboard-by-appsflyer#metrics">dashboard da SKAN</Anchor></li></ul> |
| Limites de aplicativos | <ul><li>Analytics: 10 aplicativos por solicitação</li><li>SKAN: Um aplicativo por solicitação (apenas iOS)</li></ul> |
| Dimensões compatíveis | A análise aceita todas as dimensões disponíveis no My Dashboards. |
| Dados agregados | Compatibilidade com dados agregados. Isso inclui níveis de granularidade semanais e mensais, além de métricas personalizadas. |
| Pouca atualização | Os dados do SKAN estão disponíveis com um atraso de até 3 dias, em UTC. |
| Moeda e fuso horário | Os dados do SKAN estão disponíveis em USD por padrão. As moedas alternativas são compatíveis ao utilizar `revenue_alt = true`. Os dados são informados em UTC. |
| Desativação do MCP | <ul><li>O MCP está ativado por padrão e pode ser desativado por um administrador em **Conta e perfil > Recursos de IA**.</li><li>Quando o MCP está desativado, os usuários não podem acessar os dados da AppsFlyer por meio do MCP em ferramentas externas de IA.</li><li>As conexões existentes podem continuar funcionando até que a sessão atual expire.</li><li>Desativar o MCP não afeta as conexões tradicionais da API nem outros recursos de IA na AppsFlyer.</li><li>Se um token do MCP estiver em uso, primeiro exclua-o em **Central de segurança > Tokens da AppsFlyer**.</li></ul> |

</Accordion>

<div id="troubleshoot-connection-issues" />

## Resolução de problemas de conexão

Se a conexão com o MCP da AppsFlyer não estiver funcionando, siga as etapas do seu método de autenticação.

<div id="h_troubleshoot-browser-based-oauth-login" />

<Accordion title="Login OAuth pelo navegador">

Use esta seção para clientes que se conectam através do login pelo navegador, como Gemini CLI, Copilot CLI, ChatGPT, Claude.ai e Claude Desktop.

1. **Faça a reautenticação da sua sessão.** As sessões do OAuth expiram aproximadamente a cada 7 dias. Reinicie o fluxo de conexão e faça novamente o login pelo navegador.
2. **Complete o fluxo de autenticação.** Certifique-se de que o login pelo navegador tenha sido concluído com sucesso. Quando solicitado, clique em **Permitir** ou **Aprovar** e depois volte para seu cliente MCP.
3. **Reinicie a sessão.** Reinicie a CLI, o chat ou a sessão do seu aplicativo. Em seguida, conecte-se novamente ao servidor do MCP.
4. **Verifique a configuração do servidor do MCP.** Confirme os seguintes valores:

| Campo | Valor |
| --- | --- |
| Tipo de servidor | `HTTP` |
| a URL | `https://mcp.appsflyer.com/auth/mcp` |

5. **Verifique as permissões dos usuários.** Certifique-se de que o usuário da AppsFlyer tem acesso aos aplicativos relevantes e aos dados solicitados.

</Accordion>

<div id="h_troubleshoot-bearer-token-authentication" />

<Accordion title="Autenticação por token Bearer">

Use esta secção para Claude Code, n8n, Make, agentes self-hosted e outras ferramentas de automação.

1. **Verifique se o token foi revogado.** Os tokens podem ser revogados manualmente. Tokens criados antes de **10 de março de 2026, 19:00 UTC** podem não funcionar mais.
2. **Crie um novo token do MCP.** Para recuperar o acesso:
   1. Faça login na AppsFlyer.
   2. Acesse **Menu de contas > Central de segurança > Gerenciamento de tokens**.
   3. Localize os tokens revogados.
   4. Exclua o token revogado.
   5. Crie um novo token do MCP.
   6. Atualize seu cliente MCP ou automação com o novo token.
3. **Atualize o cabeçalho Authorization.** Certifique-se de que o cabeçalho usa este formato:

   ```http
   Authorization: Bearer <YOUR_MCP_TOKEN>
   ```
4. **Verifique a configuração do servidor do MCP.** Confirme os seguintes valores:

| Campo | Valor |
| --- | --- |
| a URL | `https://mcp.appsflyer.com/auth/mcp` |
| Transporte | `HTTP` |
| Cabeçalho | `Authorization: Bearer <YOUR_MCP_TOKEN>` |

5. **Verifique se o servidor está registrado.** Para o Claude Code, execute:

   ```bash
   claude mcp list
   ```
6. **Adicione novamente o servidor do MCP, se necessário.**

   ```bash
   claude mcp remove appsflyer
   claude mcp add-json appsflyer '{"type":"http","url":"https://mcp.appsflyer.com/auth/mcp","headers":{"Authorization":"Bearer YOUR_APPSFLYER_MCP_TOKEN"}}'
   ```
7. **Verifique as permissões dos tokens.** O token do MCP herda permissões do administrador que o criou. Certifique-se de que o token tem acesso aos aplicativos relevantes e aos dados solicitados.

</Accordion>

<div id="h_access-and-permission-issues" />

<Accordion title="Problemas de acesso e permissões">

Se a autenticação for bem-sucedida, mas o acesso continuar falhando:

* O acesso ao MCP pode ser restringido pelo seu administrador da AppsFlyer.
* Se você não tiver acesso às configurações de Conta e perfil, o acesso ao MCP pode ser bloqueado.
* Entre em contato com seu administrador da AppsFlyer para autorizar o acesso.
* Certifique-se de que o usuário ou token tem acesso aos aplicativos relevantes e aos dados solicitados.

</Accordion>

<div id="h_general-connection-checks" />

<Accordion title="Verificações gerais">

Se o problema persistir:

* Certifique-se de que seu cliente aceita o MCP.
* Verifique se as restrições de rede ou firewall estão bloqueando o endpoint do MCP.
* Confirme se o URL do MCP está correto:

  ```text
  https://mcp.appsflyer.com/auth/mcp
  ```
* Tente se reconectar depois de uma nova sessão ou em um outro ambiente.

</Accordion>

<div data-zendesk-anchors="h_01K9CJ9WQ3JJSYWDMNJ5GP7N04=disclaimer what-is-appsflyer-mcp=o-que-%C3%A9-o-mcp-da-appsflyer h_01JY3G849QAT2GC714FR6CADH2=o-que-%C3%A9-o-mcp-da-appsflyer h_set-up-appsflyer-mcp=configurar-o-mcp-da-appsflyer set-up-appsflyer-mcp=configurar-o-mcp-da-appsflyer h_01KT8Y9JEJEZ26BRHK530JDB0D=aten%C3%A7%C3%A3o h_authentication-methods=m%C3%A9todos-de-autentica%C3%A7%C3%A3o authentication-methods=m%C3%A9todos-de-autentica%C3%A7%C3%A3o h_browser-based-oauth-login=login-oauth-pelo-navegador browser-based-oauth-login=login-oauth-pelo-navegador h_bearer-token-authentication=autentica%C3%A7%C3%A3o-por-token-bearer bearer-token-authentication=autentica%C3%A7%C3%A3o-por-token-bearer h_set-up-by-client=configurar-por-cliente set-up-by-client=configurar-por-cliente claude-ai-and-claude-desktop=h_claude-ai-and-claude-desktop h_01KT8Y9JEJQNXK3SZ7M0ETH5RN=aten%C3%A7%C3%A3o-1 h_set-up-claude-ai-and-desktop=configurar-o-claudeai-e-o-claude-desktop set-up-claude-ai-and-desktop=configurar-o-claudeai-e-o-claude-desktop h_test-claude-connection=teste-a-conex%C3%A3o-com-o-claude test-claude-connection=teste-a-conex%C3%A3o-com-o-claude h_01M09YV6XHR3DPYSHZA127XB50=aten%C3%A7%C3%A3o-5 claude-code=h_claude-code h_add-appsflyer-mcp-to-claude-code=adicione-o-mcp-da-appsflyer-ao-claude-code add-appsflyer-mcp-to-claude-code=adicione-o-mcp-da-appsflyer-ao-claude-code cursor-ide=h_cursor-ide vs-code=h_vs-code chatgpt=h_chatgpt custom-gpt-available-for-all-packages-including-free-enterprise=adicione-o-custom-gpt-%C3%A0-appsflyer mcp-in-chatgpt-supported-for-chatgpt-users-on-all-paid-plans=adicione-o-mcp-da-appsflyer-no-chatgpt h_01KT8Y9JEJ806MVHJACM0VNM0K=aten%C3%A7%C3%A3o-3 gemini-cli=h_gemini-cli h_add-appsflyer-mcp-to-gemini-cli=adicione-o-mcp-da-appsflyer-ao-gemini-cli add-appsflyer-mcp-to-gemini-cli=adicione-o-mcp-da-appsflyer-ao-gemini-cli h_troubleshoot-gemini-cli-authentication=resolu%C3%A7%C3%A3o-de-problemas-na-autentica%C3%A7%C3%A3o-do-gemini-cli troubleshoot-gemini-cli-authentication=resolu%C3%A7%C3%A3o-de-problemas-na-autentica%C3%A7%C3%A3o-do-gemini-cli copilot-cli=h_copilot-cli h_add-appsflyer-mcp-to-copilot-cli=adicione-o-mcp-da-appsflyer-ao-copilot-cli add-appsflyer-mcp-to-copilot-cli=adicione-o-mcp-da-appsflyer-ao-copilot-cli third-party-and-self-hosted-platforms=h_third-party-and-self-hosted-platforms h_mcp-connection-details=detalhes-da-conex%C3%A3o-do-mcp mcp-connection-details=detalhes-da-conex%C3%A3o-do-mcp h_01KT8Y9JEKZRB56RZJXMMN4WV0=aten%C3%A7%C3%A3o-4 h_example-use-cases=exemplos-de-casos-de-uso example-use-cases=exemplos-de-casos-de-uso other-platforms=h_other-platforms use-multiple-accounts-or-agencies=h_use-multiple-accounts-or-agencies h_switch-between-accounts=alternar-contas-oauth-pelo-navegador switch-between-accounts=alternar-contas-oauth-pelo-navegador h_connect-multiple-accounts-simultaneously=conectar-v%C3%A1rias-contas-simultaneamente-token-bearer connect-multiple-accounts-simultaneously=conectar-v%C3%A1rias-contas-simultaneamente-token-bearer using-appsflyer-mcp=usar-o-mcp-da-appsflyer h_01JY3G1ZEC5Q30KP49RAA7EHRS=usar-o-mcp-da-appsflyer use-cases-and-prompts=casos-de-uso-e-prompts h_01JY3WMZ41HHQ4G13DGV8DPJMW=casos-de-uso-e-prompts h_01JZHT6BA2NX8GXNV8675XNVWT=importante h_01JY3WZE6G2WB6DCWV68G1T36D=analyze-performance h_01M09YV6XJ7AM6S502BT2A594T=aten%C3%A7%C3%A3o-5 analyze-creative-performance=h_analyze-creative-performance analyze-incrementality-experiments=h_analyze-incrementality-experiments h_01K7P0A6V86FZ3YQTQ4N5JZ4ZX=analyze-skan-performance h_01JY3VJEQMRDFAFTKZMPZ90RHP=onelink-management h_01JY3VJEQMXD32NSEE0E0FWG60=knowledge-base-and-developer-support h_01K01CE5NQ56HRT967F78ETKMS=apps-management h_01K01CE5NQBW6AADMHEPBQQN7S=audiences-management h_01JY3VJEQNYKZ3Z724XM9JRWZF=feedback-tool h_01K9SHEQBWKK6AC0GD0YQVVJJ9=cost-configuration-integration h_01KGM1A7V6NB16A1Q07V5FQG2M=ad-revenue-integrations h_01K338G5KA09TESMNC6Z88RJCP=user-management-and-role-control other-information=outras-informa%C3%A7%C3%B5es h_01JZHTJ1FQMXX9GSAN31E8HAYF=outras-informa%C3%A7%C3%B5es privacy-and-security=h_privacy-and-security h_data-processing=processamento-de-dados data-processing=processamento-de-dados h_credentials=credenciais credentials=credenciais h_permissions=authorization-bearer permissions=authorization-bearer h_read-only-access=acesso-de-leitura-e-grava%C3%A7%C3%A3o read-only-access=acesso-de-leitura-e-grava%C3%A7%C3%A3o h_ai-provider-data-usage=uso-de-dados-dos-fornecedores-de-ia ai-provider-data-usage=uso-de-dados-dos-fornecedores-de-ia h_certifications=certifica%C3%A7%C3%B5es certifications=certifica%C3%A7%C3%B5es h_01K044H4H18ED75GYQWMPDRA4R=tool-mapping h_01K01DT8656BQM1GW0HDHXGCY2=traits-and-limitations h_troubleshoot-connection-issues=resolu%C3%A7%C3%A3o-de-problemas-de-conex%C3%A3o troubleshoot-connection-issues=resolu%C3%A7%C3%A3o-de-problemas-de-conex%C3%A3o troubleshoot-browser-based-oauth-login=h_troubleshoot-browser-based-oauth-login troubleshoot-bearer-token-authentication=h_troubleshoot-bearer-token-authentication access-and-permission-issues=h_access-and-permission-issues general-connection-checks=h_general-connection-checks" />
