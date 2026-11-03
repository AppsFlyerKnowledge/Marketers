---
title: Usar a página de teste do SDK web
metadata:
  keywords:
    - SDK Test
    - Web Attribution
    - Web Attribution SDK
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  created_at: '2026-08-23T16:04:12Z'
  edited_at: '2026-10-20T03:54:54Z'
  id: 50118956978577
  locale: pt
  section: AppsFlyer Web Attribution
  section_id: 43560690387729
  url: https://support.appsflyer.com/hc/pt/articles/50118956978577
---
> **At a glance:** Use a página de teste do SDK web para validar a instalação do SDK web e o registro de eventos em tempo real. Execute-o ao integrar o SDK pela primeira vez e sempre que adicionar ou alterar um evento.

## Retorna um objeto JSON com os dados brutos de consentimento do DMA conforme enviados do anunciante para a AppsFlyer

A página de teste do SDK web abre seu site em uma nova guia do navegador com uma sessão de teste dedicada. Toda a atividade do SDK web nessa guia, incluindo carregamentos de página, eventos e chamadas de identidade, é transmitida ao vivo para a página de teste, onde você pode inspecionar cada evento e suas propriedades. Isso permite verificar sua implementação em minutos, sem esperar que os dados apareçam nos relatórios.

Use-o para verificar se:

* O SDK web carrega nas páginas desejadas.
* Seus eventos são disparados com o nome, a receita e as propriedades corretos.
* O Customer User ID (CUID) é definido após o login ou cadastro.

Execute um teste sempre que integrar o SDK pela primeira vez ou alterar a configuração de eventos.

## Pré-requisitos

Antes de executar um teste, certifique-se de que tem:

* Um aplicativo web na AppsFlyer. Para mais informações, consulte <Anchor target="_blank" href="/marketers/pt/docs/adding-an-app-to-appsflyer#web">Criar um aplicativo web na AppsFlyer</Anchor> em Mensuração de performance web.
* O SDK web da AppsFlyer está implementado nas páginas que você quer testar. Para mais informações, consulte a seção <Anchor target="_blank" href="/marketers/pt/docs/integrate-appsflyer-web-sdk">Integrar o SDK web da AppsFlyer</Anchor>.

## Executar teste

Depois que os pré-requisitos estiverem em vigor, execute um teste da seguinte forma:

1. Na AppsFlyer, no menu lateral, acesse **Configurações** > **Testes de integração do SDK**.
2. Selecione **Teste do SDK web**.
3. Na caixa de diálogo **Teste seu SDK web**:
   * Selecione seu aplicativo web.
   * O campo **URL** vem preenchido automaticamente com a URL do site configurada para o aplicativo. O teste é executado nessa URL por padrão. Altere-a para testar uma página específica.
4. Clique em **Iniciar teste**. Seu site é aberto em uma nova aba do navegador com uma sessão de teste dedicada. Você não precisa fazer nada lá.
5. Volte para a página de teste do SDK web. Os eventos da aba de teste aparecem automaticamente na tabela **Eventos ao vivo** enquanto você navega e interage com seu site.

> 📘 **Note**
>
> O teste captura apenas a atividade da aba do navegador que ele abre. Visitar seu site diretamente sem iniciar um teste não exibe eventos nesta página.

## Ver a tabela de eventos ao vivo

Cada linha da tabela **Eventos ao vivo** mostra o timestamp, o tipo, o nome e o status de validação do evento.

| ID do produto | O que significa |
| --- | --- |
| `pageLoad` | O SDK web foi carregado e registrou uma visita em uma página. |
| `Definir ID de usuário cliente` | O SDK define o Customer User ID (CUID) do cliente. |
| `EVENT` | A AppsFlyer registrou um evento que você definiu. A coluna **Nome do evento** mostra o nome do evento, por exemplo, purchase. |

A tabela **Eventos ao vivo** também oferece suporte a:

* **Detalhes do evento:** Clique em uma linha para abrir o painel Detalhes do evento e ver todas as propriedades incluídas no evento, por exemplo, receita e valores do evento.
* **Pesquisar:** Use a caixa de pesquisa para encontrar um evento específico.
* **Exportar:** Clique em **Exportar CSV** para baixar os resultados.

## Reiniciar ou limpar um teste

Use uma destas opções para reiniciar ou limpar um teste:

* **Reiniciar teste:** Limpa a lista de eventos e abre uma nova aba do navegador com uma nova sessão de teste. Você pode usar isso para iniciar uma execução limpa.
* **Reiniciar com novo aplicativo / URL:** Reabre a caixa de diálogo de configuração para testar um aplicativo web ou uma página diferente.
* **Limpar logs:** Limpa apenas a lista de eventos. A sessão de teste atual e a aba do navegador permanecem ativas, então novos eventos continuam sendo transmitidos.

## Cenários comuns de teste

Você pode simplesmente executar um teste após cada alteração na configuração do SDK web ou nos eventos. Essa é a maneira mais rápida de identificar problemas antes que eles afetem seus dados. Os cenários comuns incluem:

* **Primeira integração do SDK web:** Navegue pelas páginas em que você instalou o SDK e verifique se um evento `pageLoad` aparece em cada uma delas.
* **Adicionar ou alterar um evento:** Acione o evento no seu site, por exemplo, conclua uma compra. Em seguida, verifique se uma linha EVENT aparece com o nome do evento, a receita e as propriedades corretos nos detalhes do evento.
* **Implementação do ID de usuário do cliente:** Cadastre-se ou faça login no seu site e verifique se um evento `setCustomerUserId` aparece. Definir o CUID melhora a precisão da atribuição e unifica as jornadas do usuário entre plataformas.

<div data-zendesk-anchors="h_01WSDKTP0000000000OVRVW=retorna-um-objeto-json-com-os-dados-brutos-de-consentimento-do-dma-conforme-enviados-do-anunciante-para-a-appsflyer overview=retorna-um-objeto-json-com-os-dados-brutos-de-consentimento-do-dma-conforme-enviados-do-anunciante-para-a-appsflyer h_01WSDKTP0000000000PREQ1=pr%C3%A9-requisitos prerequisites=pr%C3%A9-requisitos h_01WSDKTP0000000000RUNT1=executar-teste run-a-test=executar-teste h_01WSDKTP0000000000REVW1=ver-a-tabela-de-eventos-ao-vivo view-the-live-events-table=ver-a-tabela-de-eventos-ao-vivo h_01WSDKTP0000000000RSTR1=reiniciar-ou-limpar-um-teste restart-or-clear-a-test=reiniciar-ou-limpar-um-teste h_01WSDKTP0000000000WHEN1=cen%C3%A1rios-comuns-de-teste common-testing-scenarios=cen%C3%A1rios-comuns-de-teste" />
