---
title: 'Boletim: Regras de validação'
metadata:
  keywords:
    - Advertisers
    - Protect360
    - Validation Rules
    - Marketers
table_of_contents: false
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-yanai
    - Marketers
    - Protect360
  created_at: '2020-11-22T09:00:27Z'
  edited_at: '2026-10-20T03:57:10Z'
  id: 360015724037
  locale: pt
  section: Bulletins
  section_id: 6551161473041
  url: https://support.appsflyer.com/hc/pt/articles/360015724037
---

<Table>
  <tbody>
    <tr>
      <td>
        **Novidade**
      </td>
      <td>
        A página Regras de validação tem um novo layout e funcionalidade ampliada.

        [![](https://files.readme.io/ed1bfe9c2d4a806bd1c00449f6245a965d2be4257a39076f1b33abd24ec8836a-360014789398.jpg)](https://files.readme.io/ed1bfe9c2d4a806bd1c00449f6245a965d2be4257a39076f1b33abd24ec8836a-360014789398.jpg)
      </td>
    </tr>
    <tr>
      <td>
        **Onde:**
      </td>
      <td>
        * Página de Regras de validação
        * Relatório Retargeting
        * Postbacks de rejeição
      </td>
    </tr>
    <tr>
      <td>
        **Ações necessárias**
      </td>
      <td>
        * **Quem:** Anunciantes
        * **O quê:**
          * Familiarize-se com o novo layout e os novos recursos.
          * **Nenhuma ação é necessária para as regras existentes; elas são migradas automaticamente.**
          * Os anunciantes com o plano Protect360 premium devem usar os relatórios de fraude do Protect360 para instalações, eventos in-app e postbacks de instalação, em vez dos relatórios das regras de validação de segmentação.
      </td>
    </tr>
    <tr>
      <td>
        **Data de início**
      </td>
      <td>
        7 de dezembro de 2020
      </td>
    </tr>
    <tr>
      <td>
        **Destaques**
      </td>
      <td>
        A partir da data de vigência, o novo layout e a nova funcionalidade ficam disponíveis. 

        Alterações:

        * **Lista de regras**: A página de regras lista todas as regras contidas na sua conta.
        * **Builder de regras**: 
          * São permitidas várias combinações de regras.
          * As regras podem ser aplicadas a um ou vários aplicativos.
          * As regras podem ser aplicadas a todas as fontes de tráfego: orgânico, não orgânico, agência, SRN etc.
          * Um builder de regras para regras de segmentação de campanha e regras do Protect360 (opções adicionais disponíveis para clientes do Protect360).
          * Os clientes do Protect360 também podem criar regras para bloquear eventos in-app.
          * Novas condições de regras estão disponíveis.
          * Novas opções para as regras bloquearem instalações ou a atribuição.
          * Instalações/eventos in-app podem ser bloqueados por várias regras.
        * **Relatórios de dados brutos**:  

        <table><thead><tr><th rowspan="2">Relatórios de regras de validação de direcionamento </th><th colspan="2">Onde os dados estão disponíveis agora</th></tr><tr><th>Com o Protect360 Premium</th><th>Sem o plano Protect360 Premium</th></tr></thead><tbody><tr><td>Instalações inválidas</td><td><p><span>Relatório de dados brutos de instalações do Protect360</span></p></td><td><p><span>Relatório de dados brutos de instalações do Protect360</span></p></td></tr><tr><td>Eventos in-app inválidos</td><td><p><span>Relatório de dados brutos de eventos in-app do Protect360</span></p></td><td>-</td></tr><tr><td>Postbacks de instalação inválidos</td><td><span>Relatório de postback de instalação bloqueada do Protect360</span></td><td><span>Relatório de postback de instalação bloqueada do Protect360</span></td></tr></tbody></table>

          * Os relatórios de dados brutos contêm o nome da regra inserido pelo criador/editor da regra como blocked\_reason\_value; não o ID da regra.
        * **Postbacks**: contêm o nome da regra inserido pelo criador/editor da regra como blocked\_reason\_value; não o ID da regra.
      </td>
    </tr>
    <tr>
      <td>
        **O que você precisa saber**
      </td>
      <td>
        * As ad networks e agências precisam de <Anchor target="_blank" href="/marketers/pt/docs/set-up-an-integrated-partner#permissions-tab">permissões</Anchor> para acessar relatórios de dados brutos.
        * As ad networks e agências de clientes que não usam o Protect360 não conseguem acessar os dashboards do Protect360 para visualizar dados das regras de validação.
        * As regras com uma condição **CTIT**, são alteradas durante a migração para **CTIT** AND **is\_preinstalled=no** AND **is\_deeplink=no**.
      </td>
    </tr>
  </tbody>
</Table>

<div id="see-also" />

> 📄 **Consulte também**
>
> * <Anchor target="_blank" href="/marketers/pt/docs/implement-validation-rules-to-prevent-fraud">Regras de validação para proprietários de aplicativos</Anchor>
> * Novidades na AppsFlyer

<div data-zendesk-anchors="h_01HDPFM863RB69KWQ8NV0SQ5NK=consulte-tamb%C3%A9m" />
