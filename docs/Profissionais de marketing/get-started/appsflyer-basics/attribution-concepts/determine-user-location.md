---
title: Determinar a localização do usuário
metadata:
  keywords:
    - IPs
    - Advertisers
    - Agencies
    - Ad Networks
    - ip
    - digital element
    - zip
    - dim
    - zip code
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-moran-davida
    - Marketers
    - Mobile Attribution
    - Agencies
    - Ad Networks
  created_at: '2019-01-29T12:52:11Z'
  edited_at: '2025-05-28T16:59:33Z'
  id: 360000847378
  locale: pt
  section: Attribution concepts
  section_id: 6551394235409
  url: https://support.appsflyer.com/hc/pt/articles/360000847378
---
> **Resumo:** A localização do usuário é determinada usando o endereço IP do dispositivo que é mapeado para a localização geral do usuário (cidade, estado, país e assim por diante). A localização do usuário afeta a seleção de criativos, o custo da campanha, o engajamento e a qualidade do usuário.

![5888ResolveIpAddress_us-en.png](https://files.readme.io/166e48fb0bb90b627bc51e29b53a556b71939749ab3e5eadff7d6edf0f0dfd25-360011758517.png)

<div id="determining-user-location" />

## Determinando a localização do usuário

As ações do usuário no dispositivo são reportadas à AppsFlyer. As ações (eventos) contêm vários campos de dados, incluindo o endereço IP do dispositivo.

Em alguns casos, o verdadeiro IP do dispositivo é mascarado por uma VPN, mecanismo como o iOS 15 Private Relay ou servidores proxy de postback da SKAN. Consequentemente, a conversão de endereço IP para geolocalização descrita neste artigo pode estar errada ou ser enganosa. A AppsFlyer não tem controle sobre isso.

O endereço IP é convertido pela AppsFlyer em informações de geolocalização usando dados fornecidos por <Anchor target="_blank" href="http://www.digitalelement.com/">Elemento digital</Anchor>, líder global em localização de IP.

* As informações de geolocalização podem incluir:
  * Território (país): Códigos ISO 3166 (alfa-2) ou EU (Europa) ou AS (Ásia) se nenhuma informação específica do território estiver disponível.
  * Cidade: Isso pode se correlacionar com um bairro ou distrito dentro da cidade sem estar diretamente relacionado aos limites reais da cidade.
  * DMA (área de mercado, regiões ou áreas geográficas designadas para visualização de televisão medidas pela empresa <Anchor target="_blank" href="https://www.nielsen.com/us/en/solutions/nielsen-global-connect/">Nielsen</Anchor>. <Anchor target="_blank" href="https://support.appsflyer.com/hc/article_attachments/360012539677">Códigos de metrô em arquivo CSV.</Anchor>
  * Região: A região geográfica ou continente.
  * Estado ou província: Veja a tabela de <Anchor target="_blank" href="https://support.appsflyer.com/hc/article_attachments/360012615238">nomes de estado localizados no arquivo CSV</Anchor>. Usamos o campo de região nesta tabela. Isso consiste em até 3 letras ou números.
  * Código postal.
* As tabelas de endereço IP para localização geográfica são atualizadas em intervalos regulares, geralmente semanalmente.

**Exemplo: Conversão de endereço IP para geolocalização**![IPTables_us-en.png](https://files.readme.io/0d7d4d4190face77e18476bdb9e47fdd26ed62ab91cd641f76f728d9a7c8d005-360011787798.png)

<div id="note-regarding-the-united-kingdom-uk" />

> 📘 **Nota sobre o Reino Unido (UK)**
>
> <Image alt="blobid0.png" src="https://files.readme.io/33ed45ea49e3308e17a237400ea6c6e9d33c495a9c83197041fdae282f9c65a4-360006637538.png" width="62px" />
>
> * Na plataforma, o Reino Unido é indicado usando o código UK.
> * O código ISO 3166 para o Reino Unido é GB. O Reino Unido é reservado, mas não alocado, pela ISO para o Reino Unido.

<div id="location-discrepancies" />

### Discrepâncias de localização

Em alguns casos, pode haver diferenças na localização derivada dos usuários entre a AppsFlyer e outras plataformas, mesmo que outra plataforma use a Digital Element para resolver endereços IP. Os possíveis motivos para a discrepância de localização são:

* **Atualizações do banco de dados:** para permitir a atribuição rápida, a AppsFlyer resolve os endereços IP em dados de localização internamente. A AppsFlyer busca o mapa global da Digital Element periodicamente e não em tempo real. Se a AppsFlyer e a outra plataforma buscarem dados do Digital Element em momentos diferentes, isso pode explicar as diferenças.
* **Alterações no ISP:** Os bancos de dados Digital Element mudam rapidamente à medida que os provedores de serviços (ISPs) alteram seus mapeamentos de IP.
* **Diferentes planos/métodos:** A Digital Element oferece diferentes planos de pacotes com base no nível de granularidade necessário. Outras plataformas que usam diferentes pacotes de elementos digitais ou métodos diferentes para definir o ID de um dispositivo podem fornecer resultados diferentes.
* **Proxy ou VPN:** Se um usuário implementar uma VPN ou proxy, não saberemos o verdadeiro endereço IP do usuário. A resolução geográfica será de acordo com o endereço VPN/proxy.
* **Para saber mais:** <Anchor target="_blank" href="https://www.digitalelement.com/blog/the-tricky-science-behind-ip-geolocation/">A ciência complexa por trás da geolocalização de IP</Anchor>

<div data-zendesk-anchors="determining-user-location=determinando-a-localiza%C3%A7%C3%A3o-do-usu%C3%A1rio h_01HDP1SA5YV96YMPPFGN9H6RGE=determinando-a-localiza%C3%A7%C3%A3o-do-usu%C3%A1rio h_01HDP1SA5YR7JWDHX2BNXXTKT9=nota-sobre-o-reino-unido-uk location-discrepancies=discrep%C3%A2ncias-de-localiza%C3%A7%C3%A3o h_01HDP1SA5YNA9N4P9AD4RHWS0J=discrep%C3%A2ncias-de-localiza%C3%A7%C3%A3o" />
