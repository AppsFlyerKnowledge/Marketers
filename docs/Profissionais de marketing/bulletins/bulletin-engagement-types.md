---
title: 'Boletim: tipos de engajamento'
metadata:
  keywords:
    - Marketers
    - Mobile Attribution
table_of_contents: false
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-moran-davida
    - Marketers
    - Mobile Attribution
  created_at: '2023-11-15T10:50:04Z'
  edited_at: '2026-10-20T03:55:57Z'
  id: 20161875390865
  locale: pt
  section: Bulletins
  section_id: 6551161473041
  url: https://support.appsflyer.com/hc/pt/articles/20161875390865
---

<Table>
  <tbody>
    <tr>
      <td>
        Secção
      </td>
      <td>
        A descrição
      </td>
    </tr>
    <tr>
      <td>
        **Novidades**
      </td>
      <td>
        Novos campos foram adicionados aos relatórios de dados brutos.

        * engagement\_type
        * contributor1\_engagement\_type
        * contributor2\_engagement\_type
        * contributor3\_engagement\_type

        Esses parâmetros podem retornar os seguintes valores: preload, click\_to\_download, click\_to\_app, engaged\_click, engaged\_view, view, listening. Caso eles não sejam relatados, os parâmetros retornarão vazios.

        | /docs/ctv-pc-and-console-platform-attribution-concepts | A descrição |
        | --- | --- |
        | preload | O aplicativo é pré-carregado pelo fabricante do dispositivo ou por seu fornecedor na primeira vez em que ele é ativado. Ou então, um assistente sugere que os usuários façam o download do aplicativo quando o dispositivo é ativado pela primeira vez. |
        | click\_to\_download | Quando o usuário se engaja com um anúncio, o aplicativo é automaticamente baixado e instalado no dispositivo, sem o redirecionamento para uma loja de aplicativos. |
        | click\_to\_app | Um clique em anúncio, leitura de QR code, deep link ou qualquer outro tipo de clique que redireciona o usuário para o app ou para a loja de aplicativos relevante, incentivando-o a baixar o aplicativo. |
        | engaged\_click | Um clique que mantém o usuário engajado com o anúncio dentro de um mesmo contexto, e NÃO o direciona para uma loja de aplicativos ou para o aplicativo em si. |
        | engaged\_view | Uma visualização ativa (engaged view) ocorre quando uma interação significativa é identificada. Por exemplo, quando um usuário assiste a um mínimo de 10 segundos ou mais de um anúncio que pode ser pulado, ou quando ele assiste a um vídeo completo. |
        | view | Uma visualização (view) de um anúncio ocorre quando um anúncio é renderizado e uma impressão é identificada. Alguns exemplos são anúncios em banners, intersticiais ou vídeos não engajados. |
        | listening | Essa ação ocorre quando um usuário ouve um anúncio em áudio, como um anúncio em um podcast. |
      </td>
    </tr>
    <tr>
      <td>
        **Data de entrada em vigor**
      </td>
      <td>
        17 de janeiro de 2024
      </td>
    </tr>
    <tr>
      <td>
        **O que isso afeta**
      </td>
      <td>
        * Anunciantes e agências com acesso aos relatórios de dados brutos e que trabalham com ad networks que relatam esses campos.
          * Preload e click\_to\_app para deep links serão preenchidos pela AppsFlyer, mesmo que as ad networks também relatem esses campos.
        * Relatórios de dados brutos do Data Locker, Pull API, Export Page e Push API.
          * Esses campos não são selecionados por padrão (com exceção da opção de selecionar tudo na Push API). Para usá-los, você deve selecioná-los manualmente no produto de dados brutos.
      </td>
    </tr>
  </tbody>
</Table>
