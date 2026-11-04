---
title: URLs longos do OneLink
metadata:
  keywords:
    - Marketers
    - parameters
    - QR-to-App
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-asaf-mashiah
    - Marketers
    - QR-to-App
  created_at: '2021-01-26T09:39:19Z'
  edited_at: '2026-08-19T00:33:42Z'
  id: 360017132597
  locale: pt
  section: Deep linking using OneLink
  section_id: 6551203111057
  url: https://support.appsflyer.com/hc/pt/articles/360017132597
---
> **Visão geral:** Entenda a diferença entre URLs curtos e longos do OneLink e como criar URLs longos fora da AppsFlyer.

<div id="about-onelink-links" />

## **Links personalizados do OneLink**

* Trabalhe em todos os canais de marketing de mídia para redirecionar os usuários para: 
  * O URL/loja de aplicativos correta.
  * Abra o aplicativo e, em seguida, faça o deep link dos usuários a uma atividade específica no aplicativo.
* Pode suportar a personalização da marca. Ou seja, o URL tem o seu <Anchor target="_blank" href="/marketers/pt/docs/brand-onelink-with-your-domain">domínio da marca</Anchor>, em vez do subdomínio OneLink.
* Podem ser URLs curtos ou longos:
  * URLs curtos são criados na AppsFlyer (ou <Anchor target="_blank" href="/marketers/pt/docs/onelink-guide">na interface do usuário</Anchor>, ou via <Anchor target="_blank" href="/marketers/pt/docs/use-onelink-api-to-create-links-in-large-scale-campaigns">API</Anchor> ou <Anchor target="_blank" href="/marketers/pt/docs/user-invite-attribution">SDK</Anchor>).
  * URLs longos:
    * Pode ser criado na interface do usuário da AppsFlyer ou fora da AppsFlyer.
    * Contenha os parâmetros desejados.
    * Pode ser usado para gerar um grande número de links personalizados do OneLink aplicando suas próprias fórmulas simples em uma planilha. **Observação:** Links criados em uma planilha não estão visíveis (e não podem ser editados) em nenhuma interface do usuário da AppsFlyer.
      * Links criados em uma planilha não estão visíveis (e não podem ser editados) em nenhuma interface do usuário da AppsFlyer.
      * Este método de planilha é diferente de <Anchor target="_blank" href="/marketers/pt/docs/perform-onelink-bulk-actions-via-csv">Executar ações em massa do OneLink via CSV</Anchor>, que cria URLs curtas em massa.
    * Não expirar, o que significa que não há limitação de tempo de vida (TTL).**Considerações sobre URLs longas:**
    * URLs longos são transparentes, o que significa que todos os parâmetros de link são visíveis para o público e podem ser potencialmente manipulados.
    * URLs longos podem não caber em navegadores, SMS ou outros locais com limitações de caracteres de URL.

<div id="advantages-of-a-short-onelink-url-compared-to-a-long-url" />

### URLs longos do OneLink

* A atualização dos parâmetros na URL curta do OneLink no dashboard da AppsFlyer não altera o ID do shortlink; portanto, não é necessário substituir ou redistribuir a URL nem quaisquer QR codes associados, mesmo que já estejam em uso.
* A AppsFlyer aplica os parâmetros atualizados de forma integrada para atribuição e reportar, garantindo que o QR code permaneça funcional e reflita automaticamente as alterações.

<div id="procedures" />

## Procedimentos

**Para criar um URL longo do OneLink fora da interface do usuário da AppsFlyer:**

1. Crie um template do OneLink
2. Registre o URL base do OneLink, ou seja, o domínio do modelo OneLink + ID do template.  
   Exemplo: 
   * Domínio do template do OneLink: `yourbrand.onelink.me`
   * ID do template: `1a6f`
   * URL base do OneLink: `yourbrand.onelink.me/1a6f`
   * Exemplo de domínio de marca: `yourbrand.com/1a6f`
3. Acrescentar um `?` para o URL, seguido por quaisquer parâmetros que você deseja adicionar.
   * Ver <Anchor target="_blank" href="/marketers/pt/docs/about-link-structure-and-parameters">lista de parâmetros da AppsFlyer</Anchor>.
   * Para adicionar mais de um parâmetro, use `&`.  
     Exemplo: `yourbrand.onelink.me/1a6f?pid=email&c=freestuff`

**Para obter os URLs longos para links personalizados do OneLink criados na interface do usuário da AppsFlyer:**

1. Na AppsFlyer, vá para **Links personalizados do OneLink**.  
   A lista de OneLinks é exibida.  
   [![](https://files.readme.io/53bd68c390389e48eb55802418c601e7523ab7d816d21c1ae672ed55d7ade365-360016243798.jpg)](https://files.readme.io/53bd68c390389e48eb55802418c601e7523ab7d816d21c1ae672ed55d7ade365-360016243798.jpg)
2. Vá para o link para o qual você deseja o URL longo e na coluna **Ações** , clique em **Obter URL**.  
   O URL longo é exibido.

<div data-zendesk-anchors="onelink-long-urls=links-personalizados-do-onelink 01JBXQENR6QHQ1HXQQQ5NBBMKN=links-personalizados-do-onelink advantages-of-a-short-onelink-url-compared-to-a-long-url=urls-longos-do-onelink h_01JGXTFWS509NW0ESM1CZZ1KZM=urls-longos-do-onelink procedures=procedimentos h_01JBXQTQ3DXPTP9BY06QKXN3NP=procedimentos" />
