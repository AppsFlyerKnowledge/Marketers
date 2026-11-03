---
title: Ativação/desativação de parceiros
metadata:
  keywords:
    - Advertisers
    - Agencies
    - Ad Networks
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
    - Agencies
    - Ad Networks
  created_at: '2019-01-29T08:53:31Z'
  edited_at: '2026-09-10T12:29:22Z'
  id: 360000844778
  locale: pt
  section: Media source configuration
  section_id: 6551067072785
  url: https://support.appsflyer.com/hc/pt/articles/360000844778
---
> **Resumo:** Ative ou desative as integrações de parceiros, permitindo ou impedindo-os de acessar seus dados e realizar ações.

## Resumo da ativação

As integrações de parceiros podem estar ativas ou inativas. Uma integração é inicialmente ativada através do botão **Ativar parceiro** na página principal da integração. Existem vários tipos de integrações. Uma integração também pode ser considerada ativa se qualquer outro [tipo de integração](#id) (ver tabela abaixo) estiver ativo, mesmo quando o botão **Ativar parceiro** estiver desativado.

> 🚧 **Importante!**
>
> Ao ativar uma integração de parceiro, certos dados, incluindo informações pessoais (por exemplo, Advertising ID, endereço IP), serão, por padrão, compartilhados com eles. Por favor, certifique-se de que você tem a base legal e os direitos apropriados para compartilhar esses dados. Você pode limitar o compartilhamento de dados com um parceiro seguindo as instruções fornecidas no <Anchor target="_blank" href="/marketers/pt/docs/apply-aggregated-advanced-privacy-framework">framework de Privacidade Avançada Agregada</Anchor> e nos artigos sobre <Anchor target="_blank" href="/marketers/pt/docs/apply-privacy-preserving-sdk-methods">métodos de proteção da privacidade no SDK</Anchor>.

**Para acessar a página de integração de parceiros do aplicativo selecionado:**

* Na AppsFlyer, no menu lateral, selecione **Colaborar** > **Integrações ativas** e escolha o parceiro.

As seções abaixo descrevem os vários tipos de integração e o impacto das configurações de ativação do parceiro nas integrações:

<div id="id" />

<Accordion title="Tipos de integração">

A integração principal (**Ativar parceiro**) é ativada na primeira aba de integração. Os tipos de integração adicionais (ver tabela abaixo) são ativados nas abas subsequentes. **Cada integração funciona de forma independente**. Para que uma integração seja considerada ativa, pelo menos um tipo de integração deve estar ativado, independentemente do status do botão Ativar parceiro.

| Tipo de integração | Descrição |
| --- | --- |
| **Integração principal (**<Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#a-activate-partner">**Ativar parceiro**</Anchor>) | Permite atribuir conversões e enviar postbacks aos parceiros |
| <Anchor target="_blank" href="/marketers/pt/docs/roi360-cost-aggregation-overview">**Custo**</Anchor> (quando aplicável) | Permite obter dados de custos, cliques e impressões para as suas campanhas, conjuntos de anúncios, anúncios e regiões geográficas/países |
| <Anchor target="_blank" href="/marketers/pt/docs/roi360-guide-ad-revenue-attribution">**Receita de anúncios**</Anchor> (quando aplicável) | Permite obter dados da receita gerada pelos seus anúncios |
| <Anchor target="_blank" href="/marketers/pt/docs/skan-integrated-partners-list">**SKAN**</Anchor> (quando aplicável) | Permite obter postbacks SKAN dos parceiros |
| <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#permissions-tab">**Authorization: Bearer**</Anchor> | Permite conceder permissões para que ad networks e agências acessem seus dados e façam ações na sua integração |

</Accordion>

<div id="effect-of-the-partner-activation-setting" />

<Accordion title="Efeito da configuração de ativação do parceiro">

A tabela abaixo apresenta o impacto das configurações de ativação do parceiro na atribuição e nos postbacks em diferentes cenários.

<table><thead><tr><th>Cenário</th><th>Ativar parceiro:<br/>Ligado</th><th>Ativar parceiro: Desligado</th></tr></thead><tbody><tr><td>Atribuição e postbacks para novas instalações, <span>reatribuições e reengajamentos</span> </td><td><p><strong>Atribuição:</strong> Sim</p><p><strong>Postbacks:</strong> Sim</p></td><td><p><strong>Atribuição:</strong> Não</p><p><strong>Postbacks:</strong> Não</p></td></tr><tr><td><span>O engajamento (clique) ocorre antes da desativação; a instalação/reatribuição/reengajamento ocorre após a desativação</span></td><td><p><span>Não aplicável</span></p></td><td><span>O parceiro desativado não é atribuído.</span></td></tr><tr><td>Cliques e impressões</td><td>Os cliques e impressões podem ser atribuídos e apresentados no dashboard.</td><td><ul><li>O clique redireciona para uma página 403 proibida.</li><li>Os cliques e impressões não podem ser atribuídos nem apresentados no dashboard.</li></ul></td></tr><tr><td>Atribuição SKAN</td><td colspan="2"><p>Não aplicável.</p><p>Quando a atribuição SKAN está configurada, os dados SKAN são registrados mesmo que <strong>Ativar parceiro</strong> esteja ativado ou não. </p></td></tr></tbody></table>

</Accordion>

## Ativar uma integração de parceiro

**Para ativar ou editar a integração principal (aba Integração) do aplicativo selecionado:**

1. **Para ativar:** Na AppsFlyer, no menu lateral, selecione a aba **Colaborar > Integrações de Parceiros > Marketplace**.  
   **Para editar:** Na AppsFlyer, no menu lateral, selecione a aba **Colaborar > Integrações de Parceiros > Integrações ativas** .
2. Pesquise o parceiro e selecione-o. Você será redirecionado para a página de configuração da integração.
3. Em **Integração**, ligue **Ativar parceiro**.
4. Clique em **Salvar Integração**.

Veja [outros tipos de integração](#id).

> ❗️ **Atenção**
>
> Certifique-se de não usar a configuração **Ativar parceiro** para pausar ou encerrar campanhas. Isso pode causar danos irreversíveis na mensuração das campanhas ativas.

#### Quem pode ativar uma integração?

As integrações de parceiros podem ser ativadas por profissionais de marketing e agências de acordo com a tabela seguinte.

| Ativado por | SRN | Não SRN |
| --- | --- | --- |
| Marketer | Ativada para uso próprio e em nome das agências | Ativada para uso próprio |
| Agência | Não é possível ativar | Ativada para não-SRN indicada pela agência |

## Desativar uma integração de parceiro

Você pode desativar uma integração de parceiro do seu app, desligando o toggle **Ativar parceiro**. Isso significa que os parceiros não recebem atribuição de conversão e os postbacks não são enviados para eles. Contudo, se algum dos outros [tipos de integração](#id) continuar ativo, eles continuarão operacionais mesmo após desativar o botão **Ativar parceiro**. Isso significa que a **integração ainda está ativa** e os dados podem continuar a ser coletados.

<span id="deactivating-a-partner"></span>**Para desativar uma integração de parceiro:**

1. Na AppsFlyer, no menu lateral, selecione a aba **Colaborar > Integrações de Parceiros > Integrações ativas**.
2. Pesquise o parceiro e selecione-o. Você será redirecionado para a página de configuração da integração.
3. Em **Integração**, desligue **Ativar parceiro**.
4. Clique em **Salvar Integração**.
5. Para desativar completamente o parceiro de todos os [outros tipos de integração](#id), visite cada aba na página de integração e desative-os.  
   **Atenção:** Para Google e Meta ads, para interromper a gravação de dados da SKAN, acesse a aba da SKAN e delete a conexão.
6. Clique em **Salvar Integração**.
7. [Opcional] Após salvar a integração, enquanto permanece na página de configuração, v**ocê pode desativar o parceiro a partir de outros aplicativos**:
   1. No canto superior esquerdo, embaixo do nome do parceiro, clique no nome do aplicativo para abrir a lista de apps.
   2. Selecione um aplicativo diferente a partir da lista suspensa.
   3. Repita os passos 2 a 4.

## Acesso a dashboards por parceiros e agências

Parceiros e agências têm diferentes visualizações de dashboards e opções de configuração, conforme as suas permissões.

### Visibilidade do parceiro

* Os parceiros visualizam a configuração **Ativar parceiro** somente no modo leitura. Isso acontece mesmo que o parceiro tenha permissão para configurar a integração.
* A visibilidade das configurações do parceiro depende se foi o profissional de marketing ou a agência que configurou a integração, conforme detalhado na tabela a seguir:

| Integração configurada por | Configuração visível para o parceiro |
| --- | --- |
| Marketer | Sim |
| Agência | Não |

### Permissões da agência

Você pode conceder permissão às agências para trabalhar com seu aplicativo e executar o tráfego em seu nome.

**Para conceder permissões de agência a um aplicativo:**

1. No AppsFlyer, no menu lateral, selecione **Colaborar** > **Integrações Ativas**.
2. Localize a agência e selecione-a.
3. Vá para **Permissões** e ative as **Permissões da agência.**
4. [Opcional] Conceda <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#permissões-da-agência">permissões</Anchor> adicionais à agência.

> 📘 **Nota**
>
> * Uma **agência** pode ativar ou desativar a definição **Ativar parceiro** para **parceiros não-SRN**.
> * Um **profissional de marketing** pode ativar ou desativar a definição **Ativar parceiro** para **SRNs**. Ao fazer isso, as instalações dessa SRN **não são atribuídas à agência**.

#### Permissões de agência desativadas

Quando as permissões estão desativadas para agências:

* A agência não pode acessar o aplicativo no dashboard da AppsFlyer.
* As novas instalações e eventos não são atribuídos à agência.
* Os postbacks não são enviados para as fontes de mídia usadas pela agência.
* Os novos eventos de conversões anteriores à desativação da agência são atribuídos e apresentados no dashboard do profissional de marketing, mas os postbacks não são enviados para as fontes de mídia.

**Atenção:** Se o profissional de marketing desativar as permissões da agência, os dados históricos da agência (como instalações e custos) passam a ser considerados não transparentes.

Os exemplos a seguir descrevem o que acontece com o tráfego que continua a ser enviado após um profissional de marketing remover as permissões da agência:

> 📄 **Exemplo 1**
>
> **Campanha da agência com um parceiro não-SRN (link de atribuição)**
>
> O tráfego é atribuído a orgânico, ou a um engajamento anterior, se ainda estiver dentro de sua janela de lookback. A agência não é atribuída.
>
> Este exemplo também se aplica a cenários em que a AppsFlyer recebe links de atribuição de cliques, assim como a consulta à API do parceiro

> 📄 **Exemplo 2**
>
> **Campanha da agência com SRN (parceiro de link de atribuição)**
>
> O tráfego é atribuído à SRN no dashboard do profissional de marketing, mas não atribuído à agência.

<div data-zendesk-anchors="overview=resumo-da-ativa%C3%A7%C3%A3o h_01HRA982WC3519NMGXV5WEY1AZ=resumo-da-ativa%C3%A7%C3%A3o 01JDM949M75Q3BAG6M65DYMHZT=importante %20id%3D=id integration-types=id h_01HRAERWRJ2SBRY9XQG983WP5M=effect-of-the-partner-activation-setting activating-a-partner=ativar-uma-integra%C3%A7%C3%A3o-de-parceiro h_01HJR1D6THJ9TNGZZV78SEVBZN=ativar-uma-integra%C3%A7%C3%A3o-de-parceiro h_01HJR1D6THSEA65CY71VWJYX1P=aten%C3%A7%C3%A3o who-can-activate-partners=quem-pode-ativar-uma-integra%C3%A7%C3%A3o h_01HJR1D6THRMF854SCSFVZFWM9=quem-pode-ativar-uma-integra%C3%A7%C3%A3o deactivated-partners=desativar-uma-integra%C3%A7%C3%A3o-de-parceiro h_01HJR1D6THE2QWSF971VQFXCBX=desativar-uma-integra%C3%A7%C3%A3o-de-parceiro h_01HJR1D6THS60X7VTDN2X6FT0K=deactivating-a-partner partner-and-agency-dashboards=acesso-a-dashboards-por-parceiros-e-ag%C3%AAncias h_01HJR1D6THB0N1C8XCC5YAMQQ3=acesso-a-dashboards-por-parceiros-e-ag%C3%AAncias partner-visibility=visibilidade-do-parceiro h_01HJR1D6TJ6D3TV2PCFWP4SEAR=visibilidade-do-parceiro agency-permissions=permiss%C3%B5es-da-ag%C3%AAncia h_01HJR1D6TJ9PHVG6GGQ2Z1KJRQ=permiss%C3%B5es-da-ag%C3%AAncia h_01HJR1D6TJ9T55PSPBRNW1XXS7=nota disabled-agency-permissions=permiss%C3%B5es-de-ag%C3%AAncia-desativadas h_01HJR1D6TJ1ABQM6HCPK277R0Z=permiss%C3%B5es-de-ag%C3%AAncia-desativadas h_01HJR1D6TJBT0D3G2KWKFKEW5S=exemplo-1 h_01HJR1D6TJTXF49JP3VJE6ZYC9=exemplo-2" />
