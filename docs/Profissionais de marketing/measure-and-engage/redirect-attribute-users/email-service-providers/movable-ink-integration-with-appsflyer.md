---
title: Integração do Movable Ink com a AppsFlyer
metadata:
  keywords:
    - Marketers
    - OneLink
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-asaf-mashiah
    - Marketers
    - OneLink
  created_at: '2024-09-05T11:55:13Z'
  edited_at: '2026-08-19T00:33:57Z'
  id: 28109258392977
  locale: pt
  section: Email service providers
  section_id: 6551247620881
  url: https://support.appsflyer.com/hc/pt/articles/28109258392977
---
> **Em resumo:** configure uma integração com o Movable Ink para criar jornadas exclusivas de usuários com tecnologia de IA em suas campanhas de marketing e no conteúdo in-app.

## ![53374 imagem da KB do Movable Ink.png](https://files.readme.io/0f1a5d3d6b60cccdb8be113c9fd4f3603c7c3ed0ad8573a153709391d29b2c3b-28624891792401.png)

## Aba de integração

O Movable Ink é um parceiro de otimização de conteúdo dinâmico que oferece experiências personalizadas aos clientes em vários canais, como e-mails, notificações push e SMS. A integração entre a AppsFlyer e o Movable Ink permite criar jornadas exclusivas e personalizadas com tecnologia de IA em suas campanhas de marketing e no conteúdo in-app.

## Configurando o Amplitude

**Pré-requisitos**

* Para campanhas de e-mail, você precisará ter a integração com seu provedor de serviços de e-mail (ESP) implementada.  
  Uma lista de ESPs compatíveis com a AppsFlyer pode ser encontrada <Anchor target="_blank" href="/marketers/pt/docs/email-service-provider-esp-integration-guide">aqui.</Anchor>
* Integração do snippet de código do <Anchor target="_blank" href="https://github.com/AppsFlyerSDK/appsflyer-urlresolver-client">URL Resolver da AppsFlyer</Anchor> aos seus aplicativos móveis (responsável por resolver o link encapsulado do Movable Ink).
* O OneLink está configurado e oferece suporte a Universal Links/App Links. <Anchor target="_blank" href="/marketers/pt/docs/create-a-onelink-template#como-criar-templates-do-onelink">Saiba mais</Anchor>

**Para configurar a integração:**

1. **No Movable Ink:** faça login na sua conta do Movable Ink (para obter ajuda, entre em contato com seu representante do Movable Ink ou com a equipe de experiência do cliente).
2. Crie seu conteúdo no **Studio** e finalize a configuração da sua campanha.
3. Obtenha o link do Movable Ink para uso em campanhas de e-mail:
   * * Acesse a página **Finish & Export** .
     * Clique nos três pontos (“…”) Clique nos três pontos (“…”) na seção **Copy Creative Tag** e escolha **Copy Link URL**.   
       **Observação:** finalize a configuração da sua campanha antes de copiar o URL do link.
     * Copie o URL HREF do link copiado (destacado) e deixe-o de lado. Ele será usado como o valor do deep link no link final.   
       <Image alt="Imagem do Movableink destacada.png" src="https://files.readme.io/a2ccca4d6053e1448094dd83478610693b13a7f04a77aaaff7d12305533e8fbe-28405439389201.png" width="1130px" />
4. **Na AppsFlyer:** Acesse o <Anchor target="_blank" href="/marketers/pt/docs/create-a-onelink-template">template do OneLink</Anchor> específico que você usará na campanha e recupere os seguintes pontos de dados para a integração:
   * * **Domínio do OneLink:** o subdomínio para geração do OneLink na AppsFlyer.
     * **ID do template:** ID do template referenciado ou daquele criado para a campanha.
     * **PID**: a identificação exclusiva do canal de mídia.  
       O valor recomendado é o nome do ESP.
5. Monte seu link usando a estrutura de link abaixo. 

   **Estrutura do link:**

   `https://{{onelink.domain}}/{{template_id}}?pid={{pid_value}}&c={{link_name}}deep_link_value={{mi_link_from_creative_tag}}`

   **Exemplo:**

   Veja um exemplo de como fica um link depois de adicionar os parâmetros obrigatórios da tabela abaixo.

   https://link.movableink.com/oskuw854?pid=BRAZE&deep_link_value=https://www.movable-ink-2563.com/p/cp/ee0e28529389f573/c?url=https%3A%2F%2Fwww.movable-ink-2563.com%2Fp%2Frp%2F9011ea048ec4bf03%2Furl&url_sig=D4QtmtC8vqJhU7

   

| Parâmetro | A descrição | Valor de exemplo | Atenção | Obter de |
| --- | --- | --- | --- | --- |
| `{{onelink.domain}}` | Seu domínio da AppsFlyer | mink.onelink.com |  | Interface do usuário da AppsFlyer |
| `{{template_id}}` | ID do modelo de link configurado na AppsFlyer | 1a6f |  | Interface do usuário da AppsFlyer |
| `{{pid_value}}` | ID do ESP / canal de mídia | Nome do ESP |  | Interface do usuário da AppsFlyer |
| `{{mi_link_from_creative<br /><br />_tag}}` | O link clickthrough HREF da tag criativa da Movable Ink. Disponível na página Finish & Export (consulte a imagem na etapa 3.) | https://www.movable-ink-2563<br /><br />.com /p/cp /ee0e28529389f573<br /><br />/curl=https %3A%2 F%2Fwww.<br /><br />movableink2563 .com %2Fp%2<br /><br />Frp%2F9011ea048e c4b f03%2<br /><br />Furl&url \_sig=D4QtmtC8vqJhU7 | O link deve ser codificado. | Movable Ink |

   > 📘 **Atenção**
   >
   > Se os valores de `af_android_url`, `af_ios_url` e `af_web_dp` forem idênticos, você poderá encurtar o link usando `af_r`. Se houver outro parâmetro com o mesmo valor, peça ao gerente de sucesso do cliente da AppsFlyer para ativar o recurso de duplicação de parâmetros.

6. Use o novo link em sua campanha.  
   **Observação:** O link HREF do Movable Ink que você copiou e colou no seu link deve ser codificado. No entanto, **se você estiver usando o link em uma campanha de e-mail pelo seu ESP, os parâmetros do ESP não deverão ser codificados**.

## Especificações e limitações

Consulte <Anchor target="_blank" href="/marketers/pt/docs/about-link-structure-and-parameters#características-e-limitações">características e limitações adicionais do link de atribuição</Anchor>.

<div data-zendesk-anchors="about-the-integration=aba-de-integra%C3%A7%C3%A3o h_01J8HQFV2ZYYN7G1FDA1DH1GV3=aba-de-integra%C3%A7%C3%A3o h_01J8HX53FVT1N4MG2HPE743RTS=aba-de-integra%C3%A7%C3%A3o set-up-the-integration=configurando-o-amplitude h_01J710N8QBFHSX9BS6H0NFY918=configurando-o-amplitude 01J9GSWGHBA01N227MCEV91YMV=aten%C3%A7%C3%A3o traits-and-limitations=especifica%C3%A7%C3%B5es-e-limita%C3%A7%C3%B5es h_01J9GAS3T6STFKHD4C6Z6GYFMF=especifica%C3%A7%C3%B5es-e-limita%C3%A7%C3%B5es" />
