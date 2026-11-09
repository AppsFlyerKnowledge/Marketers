---
title: Configuração de campanhas do Spotify
metadata:
  keywords:
    - Advertisers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2020-11-05T07:36:01Z'
  edited_at: '2026-08-19T00:26:00Z'
  id: 360015074677
  locale: pt
  section: Ad network configuration guides (R-Z)
  section_id: 6552025468305
  url: https://support.appsflyer.com/hc/pt/articles/360015074677
---
> **Visão geral:** o Spotify, um parceiro integrado de ad network da AppsFlyer, usa sua solução de anúncios mobile aprimorada para criar campanhas estratégicas, escaláveis e inteligentes que atendam às necessidades dos usuários mobile. No Spotify, os cliques são gerados quando um usuário clica em um botão de CTA enquanto assiste ou ouve um anúncio.

<Image align="center" alt="Spotify_Full_Logo_RGB_Black.png" src="https://files.readme.io/e3908e19ec71c506c2ff135652cea6529f128743d8284c02c1a481f24485b3a6-small-37818004235409.png" width="53.91%" />

<div id="setting-up-spotify" />

## Configurando o Spotify

**Pré-requisito:** antes de configurar a integração, certifique-se de [entrar em contato com o parceiro](#) e abrir uma conta com ele. Antes de criar uma integração, certifique-se de <Anchor target="_blank" href="/marketers/pt/docs/partner-integrations#contact-details">entrar em contato com o parceiro</Anchor> e abrir uma conta com ele.

**Para ativar a integração:**

1. Na aba **Integração**, habilite **Ativar parceiro**.  
   **Para editar**: **Na AppsFlyer, vá para o menu lateral e selecione** Colaborar **>** **Integrações ativas**.
2. Selecione o aplicativo correspondente.
3. Na aba **Integração** selecione **Ativar parceiro**.
4. No **Primeira visita** Aqui, você precisará ativar **Ativar parceiro** para habilitar a configuração dos parâmetros de integração. O botão deve permanecer ativado enquanto você trabalhar com o Medialyzer. Saiba mais sobre <Anchor target="_blank" href="/marketers/pt/docs/partner-activation-deactivation">a ativação de parceiros</Anchor>.
5. Complete a configuração utilizando as abas relevantes, conforme descrito abaixo.

Saiba mais sobre o <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#about-the-integrated-partner-page">cabeçalho da janela de configuração do parceiro</Anchor>.

Saiba mais sobre as <Anchor target="_blank" href="/marketers/pt/docs/partner-activation-deactivation#ativar-uma-integração-de-parceiro">regras de ativação de parceiros</Anchor>.

<div id="important" />

> 🚧 **Importante**
>
> * A etapa de <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#d-general-settings">configurações gerais</Anchor> na aba Integração é **obrigatória** para todos os parceiros.
> * O restante das etapas é descritivo ou **opcional**

<div id="integration-tab" />

<Accordion title="Aba Integração">

A aba Integração está dividida em diferentes seções, conforme descrito abaixo.

<div id="general-settings" />

### Configurações gerais

**Ative a atribuição de view-through**

Se você quiser atribuir instalações view-through do Spotify, ative este botão. Para definir a janela de lookback de view-through, vá para a aba do link de atribuição (descrita abaixo).

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="Separador de Links de Atribuição">

O Spotify tem uma integração server-to-server com a AppsFlyer, portanto os links de atribuição não são usados para a mensuração da campanha. Ao selecionar seu aplicativo como fonte de mensuração de conversão durante a configuração da campanha do Spotify, a integração da AppsFlyer será ativada automaticamente, e o Spotify enviará à AppsFlyer dados de impressões e cliques com os identificadores necessários para a atribuição.

</Accordion>

<div id="cost-tab" />

<Accordion title="Aba de Custos">

A integração de custo não está disponível para o Spotify.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="Receita de anúncios">

A receita de anúncios não está disponível para o Spotify.

</Accordion>

<div id="permissions-tab" />

<Accordion title="Aba permissões">

Nesta guia, você pode selecionar as permissões a serem concedidas ao Spotify, caso o parceiro atue como uma ad network, agência ou ambos. Observe que, mesmo que a atribuição esteja desativada para o Spotify, a aba de permissões está ativa e você pode conceder controle ao Spotify.

Depois de ativar a concessão de permissões ao Spotify, você pode adicionar membros da equipe e conceder a eles acesso aos dados de acordo com as permissões selecionadas.  
As permissões só podem ser concedidas a funcionários do Spotify que tenham uma conta de membro da equipe da ad network na AppsFlyer.  
**Para conceder permissões aos membros da equipe da ad network:**

1. Clique em **Adicionar membro da equipe.**
2. Insira o e-mail do membro da equipe da ad network
3. Clique em **Adicionar**.

<div id="important-1" />

> 🚧 **Importante!**
>
> * Ao permitir que o Spotify configure a integração e altere os postbacks de eventos in-app, você permite que ele potencialmente acesse todos os eventos de atribuição, incluindo o tráfego orgânico e não orgânico de todos os canais de mídia.
> * As alterações feitas pelo Spotify substituem a configuração atual, mesmo que tenham sido definidas pelo anunciante.

A seguir estão os tipos de permissões que os anunciantes podem conceder ao Spotify:

* **Permitir a configuração da integração** – permite que o parceiro configure a aba de integração (exceto postbacks de evento in-app).
* **Permitir a configuração de postbacks de evento in-app** - permite que o parceiro configure o mapeamento de postbacks de evento in-app para si mesmo na guia de integração.
* **Permitir o acesso ao relatório de retenção** – somente aos próprios dados de retenção do parceiro.
* **Permitir acesso aos seus dados agregados de usuário fidelizado** - apenas aos dados de usuário fidelizado do próprio parceiro.
* **Permitir acesso aos dados agregados de eventos in-app** — apenas aos dados de eventos in-app próprios do parceiro.
* **Permitir acesso aos dados agregados de receita** — apenas aos dados da receita atribuídos ao parceiro.
* **Permitir acesso ao seu dashboard do Protect360 & dados brutos via API** - apenas aos dados do Protect360 do próprio parceiro, desde que o recurso esteja habilitado para o anunciante.

Saiba mais sobre a concessão de <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#permissions-tab">permissões de ad networks</Anchor>.

</Accordion>

<div data-zendesk-anchors="setting-up-spotify=configurando-o-spotify h_01HJS1DB7YV8T6RNXH1JRNTGDN=configurando-o-spotify h_01HJS1DB7YKBY0Q7GY7QT9DHKZ=importante h_01HJS1DB7YQKM7DRR0MJGHX95G=integration-tab general-settings=configura%C3%A7%C3%B5es-gerais h_01HJS1DB7YEQZ7JQ0T2NWFBQBM=configura%C3%A7%C3%B5es-gerais h_01HJS1DB7YHN0PCMFWQ9SZKE27=attribution-link-tab h_01HJS1DB7ZVSQCYJZENWJ9G77H=cost-tab h_01HJS1DB7Z03PTQSQB0JVJEFY0=ad-revenue-tab h_01HJS1DB7Z6CBDQFVNC75X2Z6Z=permissions-tab h_01HJS1DB7ZPZET71JAZ8E4CZ7S=importante-1" />
