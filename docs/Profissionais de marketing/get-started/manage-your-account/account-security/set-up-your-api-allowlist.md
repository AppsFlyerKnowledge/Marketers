---
title: Configure a lista de permissões da sua API
metadata:
  keywords:
    - OneLink
    - API Policy
    - fraud
    - Advertisers
    - Agencies
    - API access
    - attribution link
    - Marketers
    - Platform essentials
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-negri
    - Marketers
    - Platform essentials
    - Agencies
  created_at: '2021-08-22T13:50:14Z'
  edited_at: '2026-08-18T00:17:28Z'
  id: 4406016140817
  locale: pt
  section: Account security
  section_id: 6551173202065
  url: https://support.appsflyer.com/hc/pt/articles/4406016140817
---
> **Num relance:** Proteja a sua conta AppsFlyer definindo uma lista de permissões da API.

## [<Image alt="Lista de Permissões da API" src="https://files.readme.io/05f8c46f81b679e2881bf72255ae835a70d1cb3be1ea862b90053c2c259f25b6-4423224122385.png" width="609px" />](https://files.readme.io/05f8c46f81b679e2881bf72255ae835a70d1cb3be1ea862b90053c2c259f25b6-4423224122385.png)

<div id="overview" />

## Visão Geral

Proteja os seus dados de acessos não autorizados configurando uma lista de permissões da API que especifique os endereços IP autorizados a fazer chamadas API à sua conta AppsFlyer. Uma vez que a sua lista de permissões esteja ativa, apenas as chamadas API provenientes desses endereços IP serão permitidas enquanto as chamadas de todos os outros endereços IP serão negadas.

<div id="note" />

> 📘 **Observação**
>
> * Apenas administradores podem aceder e gerir a lista de permissões.
> * O uso da lista de permissões é opcional e está inativo por defeito.
> * A ativação da lista de permissões é feita ao nível da conta e aplica-se a todas as aplicações na conta.

<div id="set-up-your-api-allowlist" />

## Configure a sua lista de permissões da API

<div id="set-up-the-api-allowlist" />

<Accordion title="Configurar a lista de permissões">

**![AppsFlyerAdmin_us-en.png](https://files.readme.io/d67fdedd94c56e8da776e590b12883503f47d36f0d58b996c4c64cc5d0e9c675-16281491712785.png) altAppsFlyerAdmin\_us-en.pngaltPara configurar e ativar a lista de permissões da API:**

1. No topo da barra, abra o menu da conta (menu dropdown do endereço de email) > **Centro de Segurança**.
2. Na secção da lista de permissões da API, clique em **Gerir lista de permissões da API**.
3. Insira um endereço IP ou um intervalo de endereços IP no formato padrão:
   * Exemplos: `192.168.1.1`, `185.114.120.140`
   * Para introduzir um intervalo de endereços IP, use o seguinte formato: `185.114.120.1/32`(onde `185.114.120.1` é o primeiro endereço do intervalo e `185.114.120.32` é o último endereço do intervalo).
4. Clique em **Aplicar.**
5. [Opcional] Clique em **+ Adicionar** para adicionar um endereço IP adicional ou intervalo à lista.
6. Clique no botão **Guardar lista**.
7. Defina a lista de permissões como **Ativa.**

   **Nota:** A lista de permissões deve conter pelo menos um endereço IP ou intervalo antes de poder ser guardada e ativada.

</Accordion>

<div id="edit-the-api-allowlist" />

<Accordion title="Editar a lista de permissões">

Pode adicionar ou eliminar endereços IP da lista de permissões a qualquer momento (esteja a lista ativa ou não).

**![AppsFlyerAdmin_us-en.png](https://files.readme.io/d67fdedd94c56e8da776e590b12883503f47d36f0d58b996c4c64cc5d0e9c675-16281491712785.png) altAppsFlyerAdmin\_us-en.pngaltPara adicionar um endereço IP ou intervalo:**

1. No topo da barra, abra o menu da conta (menu dropdown do endereço de email) > **Centro de Segurança**.
2. Na secção da lista de permissões da API, clique em **Gerir lista de permissões da API**.
3. Clique em **+ Adicionar** para adicionar um endereço IP ou intervalo à lista.
4. Introduza um endereço IP ou intervalo.
5. Clique em **Aplicar.**
6. Certifique-se de guardar as suas alterações clicando no botão **Guardar lista**.

   **Nota:** O estado da lista (ativo ou inativo) não mudará quando você guardar a lista. Certifique-se de verificar o estado do alternador **Ativo** e ative/desative, se necessário.

**![AppsFlyerAdmin_us-en.png](https://files.readme.io/d67fdedd94c56e8da776e590b12883503f47d36f0d58b996c4c64cc5d0e9c675-16281491712785.png) altAppsFlyerAdmin\_us-en.pngaltPara excluir um endereço IP ou intervalo:**

1. No topo da barra, abra o menu da conta (menu dropdown do endereço de email) > **Centro de Segurança**.
2. Na secção da lista de permissões da API, clique em **Gerir lista de permissões da API**.
3. Clique no ícone de lixo ao lado do endereço IP que deseja excluir.
4. Na janela de confirmação, clique em **Eliminar.**
5. Certifique-se de guardar as suas alterações clicando no botão **Guardar lista**.

</Accordion>

<div id="api-allowlist-specifications" />

<Accordion title="Especificações da lista permitida">

* Para proteger a sua conta de chamadas API não autorizadas, a lista permitida deve ser configurada como **Ativa** e incluir pelo menos um endereço IP ou intervalo.
* A lista permitida aplica-se a todas as <Anchor target="_blank" href="/marketers/pt/docs/managing-appsflyer-tokens#aplicações-o-token-api-v2">APIs AppsFlyer que utilizam o token V2.0</Anchor><Anchor target="_blank" href="/marketers/pt/docs/managing-appsflyer-tokens#aplicações-o-token-api-v2">. Chamadas de APIs que utilizam o token API V1.0 serão permitidas de todos os endereços API.</Anchor>
* Até 20 endereços IP ou intervalos podem ser adicionados à lista permitida.

</Accordion>

<div data-zendesk-anchors="overview=vis%C3%A3o-geral overview::6f3684c7=vis%C3%A3o-geral h_01HZCCCTT52ZQB9VAF6Q7RRKES=vis%C3%A3o-geral h_01HZCD0681XNKR2HSNCN4GWGA0=vis%C3%A3o-geral h_01HJR00RGQX0CQEHDS9BHBGJD4=observa%C3%A7%C3%A3o set-up-your-api-allowlist=configure-a-sua-lista-de-permiss%C3%B5es-da-api h_01HZCCW4XYJ72Z6KKJPCXQB947=configure-a-sua-lista-de-permiss%C3%B5es-da-api h_01HJR00RGRQ54R71HY0ZBRM1PM=set-up-the-api-allowlist h_01HJR00RGRD7PK2HR5VS1JENWQ=edit-the-api-allowlist h_01HJR00RGRESGGEW3D6NHHF7VY=api-allowlist-specifications" />
