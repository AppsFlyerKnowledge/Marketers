---
title: Aplicar mascaramento de IP aos dados do usuário
metadata:
  keywords:
    - IP masking
    - Advertisers
    - Marketers
    - Platform essentials
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-negri
    - Marketers
    - Platform essentials
  created_at: '2016-05-23T12:59:55Z'
  edited_at: '2026-08-18T00:34:21Z'
  id: 208879066
  locale: pt
  section: Preserve user privacy
  section_id: 6551440878097
  url: https://support.appsflyer.com/hc/pt/articles/208879066
---
> **Resumo:** Como mascarar endereços IP de usuários de aplicativos nos Relatórios de dados brutos da AppsFlyer e em postbacks enviados aos parceiros.

<div id="ip-masking" />

## Mascaramento de IP

Ao ativar o mascaramento de IP:

* Os endereços IP dos usuários não são listados nos Relatórios de dados brutos nem fornecidos via postbacks aos parceiros
* O campo de endereço IP é preenchido com o valor 1.1.1.1

<div id="note" />

> 📘 **Nota**
>
> * As instalações ocorridas antes de o mascaramento de IP ser ativado não são mascaradas
> * O <Anchor target="_blank" href="/marketers/pt/docs/meta-ads-aggregate-event-measurement-aem-for-ios#compartilhamento-de-dados-da-aem">compartilhamento de dados de AEM</Anchor> para anúncios da Meta não é compatível com eventos de servidor para servidor nem com eventos de SDK quando o mascaramento de IP está ativado. Isso significa que os dados não são compartilhados com o Meta ads.

<div id="example" />

> 📄 **Exemplo**
>
> * A configuração de mascaramento de IP segue este caminho: desativado, ativado e depois desativado.
> * Três usuários instalam o aplicativo em datas diferentes, conforme mostrado na tabela de instalação do aplicativo
> * A tabela de mascaramento de IP e de Relatório de dados brutos abaixo mostra o status da configuração de mascaramento de IP e os respectivos dados brutos nas datas relevantes.
>
> Instalações do app:
>
>
>
> | Data de instalação | ID do usuário | Endereço IP |
> | --- | --- | --- |
> | 2 de janeiro | User\_A | 192.0.2.1 |
> | 7º de janeiro | User\_B | 192.0.2.33 |
> | 14 de janeiro | User\_C | 203.0.113.1 |
>
>
>
> Mascaramento de IP e dados brutos:
>
>
>
> | Date | Status da configuração de mascaramento de IP | Relatório de dados brutos |
> | --- | --- | --- |
> | 1 de janeiro | Desligado | Usuário A 192.0.2.1 |
> | 2 de janeiro | Ativado | User\_A 192.0.2.1 |
> | 8º de janeiro | Ativado | User\_A 192.0.2.1  <br />User\_B 1.1.1.1 |
> | 9º de janeiro | Desligado | User\_A 192.0.2.1  <br />User\_B 1.1.1.1 |
> | 15 de janeiro | Desligado | User\_A 192.0.2.1  <br />User\_B 1.1.1.1  <br />User\_C 203.0.113.1 |

<div id="turn-on-ip-masking" />

## Ativar mascaramento de IP

O mascaramento de IP é definido por aplicativo e afeta instalações de todas as fontes.

**Para ativar o mascaramento de IP:**

1. Na AppsFlyer, no menu lateral, selecione **Configurações** > **Configurações do Aplicativo.**
2. Role para baixo até **Configurações avançadas**.
3. Ative **Mascarar endereços IP**.

<div id="ip-masking-in-raw-data-reports" />

## Mascaramento de IP em relatórios de dados brutos

Quando o mascaramento de IP está ativado:

* Novas instalações e eventos in-app mostram um endereço IP de 1.1.1.1.
* Os <Anchor target="_blank" href="/marketers/pt/docs/determine-user-location">parâmetros relacionados à localização</Anchor>, como país e cidade, ainda aparecem nos relatórios de dados brutos.

**Exemplo de relatório de dados brutos**

![ip_masking.png](https://files.readme.io/e52f8bd698191f0b1ac08e595e539f15bda59567ed51ddda32a0d80db3bdf23c-360001962938.png)

<div data-zendesk-anchors="ip-masking=mascaramento-de-ip h_01HA91HHADCTT7QS2K79TJEY2C=mascaramento-de-ip h_01HA92HF3ZYR2NBTXQ1S2AHCAA=nota h_01HA91HHAD7BCXRZW6AD9NRDBN=exemplo enabling-ip-masking=ativar-mascaramento-de-ip h_01HA91HHAEM220CE8805GFQYKR=ativar-mascaramento-de-ip ip-masking-in-raw-data-reports=mascaramento-de-ip-em-relat%C3%B3rios-de-dados-brutos h_01HA91HHAE14D6ES1ERNK93VY9=mascaramento-de-ip-em-relat%C3%B3rios-de-dados-brutos" />
