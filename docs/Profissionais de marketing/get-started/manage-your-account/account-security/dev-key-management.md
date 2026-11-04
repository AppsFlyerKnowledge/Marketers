---
title: Gerenciamento de Dev Key
metadata:
  keywords:
    - Marketers
    - Platform essentials
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-negri
    - Marketers
    - Platform essentials
  created_at: '2025-07-14T11:20:11Z'
  edited_at: '2026-10-08T00:08:36Z'
  id: 37139123425809
  locale: pt
  section: Account security
  section_id: 6551173202065
  url: https://support.appsflyer.com/hc/pt/articles/37139123425809
---
> **Em resumo:** Controle e atualize a Dev Key do seu aplicativo diretamente nas Configurações do aplicativo. Oferecendo a você mais flexibilidade e segurança.

<div id="what-is-a-dev-key" />

## O que é uma Dev Key?

A Developer Key (Dev Key) é um identificador exclusivo do seu aplicativo, usado para autenticar os dados de evento enviados pelo SDK e por integrações server-to-server (S2S) para a AppsFlyer. Ela é essencial para habilitar a atribuição, as sessões e a mensuração de eventos in-app.  
Por padrão, todos os aplicativos da sua conta compartilham a mesma Dev Key. Mas, se necessário, você pode criar uma Dev Key exclusiva para cada aplicativo.  
Para dar a você mais controle, a guia Dev Key Management nas configurações do seu aplicativo permite que usuários administradores visualizem e gerenciem Dev Keys, incluindo a atualização ou substituição de uma Dev Key existente.

<div id="where-to-find-your-dev-keys" />

## Onde encontrar suas Dev Keys

Na AppsFlyer, no menu lateral, selecione **Configurações** > **Configurações do aplicativo** > **Dev Key Management**.

<div id="dev-key-management" />

## Gerenciamento de Dev Key

Os administradores podem usar a guia Dev Key Management para:

* Gerar uma Dev Key exclusiva para um aplicativo específico.
* Atribuir uma Dev Key já em uso por outro aplicativo na conta.
* Habilitar a geração padrão de dev keys exclusivas para novos aplicativos.

<div id="why-you-might-need-to-change-your-dev-key" />

### Por que talvez você precise alterar sua Dev Key

Você pode querer alterar sua Dev Key por vários motivos:

* **Segurança**: altere a chave se ela tiver sido exposta para evitar acesso não autorizado.
* **Transferências de conta**: Gere uma nova Dev Key após mover um aplicativo para uma conta diferente, para alinhá-la com a conta atual.
* **Granularidade**: atribua chaves exclusivas por aplicativo para simplificar o monitoramento, a solução de problemas ou o controle de acesso.

<div id="how-to-set-up-and-change-a-dev-key" />

### Como configurar e alterar uma Dev Key

Depois de gerar ou atribuir uma nova Dev Key, é importante:

* Atualizar o SDK: substitua a Dev Key no código do SDK do seu aplicativo.
* Lançar uma nova versão: envie uma nova versão do aplicativo com a chave atualizada para a loja de aplicativos.
* Ative a chave (obrigatório) - Ativar a Dev Key é uma **etapa obrigatória** para que a alteração entre em vigor.
* Depois que seu desenvolvedor atualizar o SDK com a nova Dev Key e a nova versão do aplicativo estiver disponível na loja de aplicativos, volte à seção **Gerenciamento de Dev Key** e clique em **Ativar Dev Key**.
* Até você ativar a Dev Key:
  * A Dev Key atual permanece ativa
  * A nova Dev Key permanecerá no estado *Pendente*
  * Nenhuma alteração será aplicada à coleta de dados

<div id="important" />

> 🚧 **Importante!**
>
> Ative a Dev Key somente depois que a versão atualizada do aplicativo estiver disponível. Ativar cedo demais pode fazer com que eventos in-app e sessões de versões mais antigas do aplicativo deixem de ser registrados.

1. Na AppsFlyer, no menu lateral, selecione Configurações > Configurações do aplicativo > Autenticação do SDK.
2. Clique em Gerenciar Dev Key.
3. Revise o impacto de alterar sua Dev Key antes de continuar.
4. Escolha como definir a nova Dev Key:
   1. **Selecione uma Dev Key existente** - Escolha uma Dev Key que já exista na sua conta (por exemplo, uma Dev Key usada por outro aplicativo).
      1. A Dev Key selecionada será atribuída a este aplicativo no estado *Pendente*
      2. Sua Dev Key atual permanecerá ativa até que você ative a nova
      3. **A ativação é obrigatória** depois que a versão atualizada do aplicativo estiver disponível
   2. **Gerar nova Dev Key** - Crie uma Dev Key totalmente nova e exclusiva para este aplicativo.

      1. A nova Dev Key será criada no estado *Pendente*
      2. Sua Dev Key atual permanecerá ativa até a ativação
      3. **A ativação é obrigatória** depois que a versão atualizada do aplicativo estiver disponível

      <div id="important-1" />

      > 🚧 **Importante!**
      >
      > Independentemente da opção escolhida, a alteração da Dev Key só entra em vigor depois que você ativar manualmente a Dev Key.

5. Clique em Avançar.
6. Copie e envie a Dev Key para seu desenvolvedor para que ele possa implementar as alterações no SDK e enviar a nova versão do seu aplicativo para a loja.
7. A Dev Key entrará em um estado pendente.
8. Clique em Ativar Dev Key.
9. A Dev Key passa de pendente para ativa.

<div id="note" />

> 📘 **Atenção**
>
> * Até que os usuários atualizem para a versão mais recente do aplicativo, eventos in-app e sessões de versões anteriores não serão registrados. No entanto, as instalações (atribuição) ainda serão processadas corretamente.
> * Se você estiver usando a API S2S (API2), alterações na Dev Key podem interromper eventos servidor a servidor.
> * Depois que a Dev Key for ativada, pode levar até 30 minutos para que os dados comecem a fluir para o sistema.

<div id="how-to-set-a-unique-dev-key-for-future-apps-coming-soon---q2-2026" />

### Como definir uma Dev Key exclusiva para aplicativos futuros (em breve - Q2, 2026)

1. No AppsFlyer, na barra lateral superior direita, clique em **Configurações da conta.**
2. Clique na aba **Conta**.
3. Em **Segurança**, ative Criar Dev Key exclusiva por aplicativo (para referência futura).
4. Observação: ao ativar Dev Keys exclusivas para aplicativos futuros, os aplicativos existentes não serão afetados.

<div data-zendesk-anchors="what-is-a-dev-key=o-que-%C3%A9-uma-dev-key h_01K04ARS7NRB6H9JVPAZNXE36H=o-que-%C3%A9-uma-dev-key where-to-find-your-dev-keys=onde-encontrar-suas-dev-keys h_01K0BS18HAZ2QK2ADHEZAH5QNF=onde-encontrar-suas-dev-keys dev-key-management=gerenciamento-de-dev-key h_01K04ASZEQHRAE4AVS88NMTTC4=gerenciamento-de-dev-key why-you-might-need-to-change-your-dev-key=por-que-talvez-voc%C3%AA-precise-alterar-sua-dev-key h_01K09HM57MXQY4R3MCVB4KCV1G=por-que-talvez-voc%C3%AA-precise-alterar-sua-dev-key how-to-set-up-and-change-a-dev-key=como-configurar-e-alterar-uma-dev-key h_01K04AXYR6J4ETE8GF6K7B8NSY=como-configurar-e-alterar-uma-dev-key h_01KGY7X3KFAZM49FG8WE5R8VHB=importante h_01KGY84Z53QW9QVNX4DJ2SR1QC=importante-1 h_01KGY12P0CJZR6FV9WEE6MNW0A=aten%C3%A7%C3%A3o how-to-set-a-unique-dev-key-for-future-apps=como-definir-uma-dev-key-exclusiva-para-aplicativos-futuros-em-breve---q2-2026 h_01K04AY1SF0FMHS4QJJDK6VZAK=como-definir-uma-dev-key-exclusiva-para-aplicativos-futuros-em-breve---q2-2026" />
