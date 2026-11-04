---
title: Determinar la ubicación del usuario
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
  edited_at: '2025-06-04T14:34:49Z'
  id: 360000847378
  locale: es
  section: Attribution concepts
  section_id: 6551394235409
  url: https://support.appsflyer.com/hc/es/articles/360000847378
---
> **En resumen:** La ubicación del usuario se determina mediante la dirección IP del dispositivo, que se asigna a la ubicación general del usuario (ciudad, estado, país, etc.). La ubicación del usuario influye en la selección de creatividades, el costo de la campaña, la interacción y la calidad del usuario.

![5888ResolveIpAddress_us-en.png](https://files.readme.io/166e48fb0bb90b627bc51e29b53a556b71939749ab3e5eadff7d6edf0f0dfd25-360011758517.png)

<div id="determining-user-location" />

## Determinación de la ubicación del usuario

Las acciones del usuario en el dispositivo se reportan a AppsFlyer. Las acciones (eventos) contienen varios campos de datos, incluida la dirección IP del dispositivo.

En algunos casos, la verdadera IP del dispositivo está enmascarada por una VPN, un mecanismo como Private Relay de iOS 15 o servidores proxy de postback de SKAN. En consecuencia, la conversión de dirección IP a ubicación geográfica descrita en este artículo puede ser incorrecta o engañosa. AppsFlyer no tiene control sobre esto.

AppsFlyer convierte la dirección IP en información de geolocalización utilizando datos proporcionados por <Anchor target="_blank" href="http://www.digitalelement.com/">Elemento Digital</Anchor>, el líder mundial en ubicaciones IP.

* La información de geolocalización puede incluir:
  * Territorio (país): Códigos ISO 3166 (alpha-2), o UE (Europa) o AS (Asia) si no se dispone de información específica del territorio.
  * Ciudad: Esto puede correlacionarse con un vecindario o distrito dentro de la ciudad sin estar directamente relacionado con los límites reales de la ciudad.
  * DMA: área de mercado, regiones o áreas geográficas designadas de audiencia televisiva medida por la empresa <Anchor target="_blank" href="https://www.nielsen.com/us/en/solutions/nielsen-global-connect/">Nielsen</Anchor>. <Anchor target="_blank" href="https://support.appsflyer.com/hc/article_attachments/360012539677">Códigos Metro en archivo CSV.</Anchor>
  * Región: La región geográfica o continente.
  * Estado o provincia: Ver tabla de <Anchor target="_blank" href="https://support.appsflyer.com/hc/article_attachments/360012615238">nombres de estado localizados en un archivo CSV</Anchor>. Usamos el campo de región en esta tabla. Consta de hasta 3 letras o números.
  * Código postal.
* Las tablas de direcciones IP a geolocalización se actualizan a intervalos regulares, generalmente semanalmente.

**Ejemplo: Conversión de dirección IP a geolocalización**![IPTables_us-en.png](https://files.readme.io/0d7d4d4190face77e18476bdb9e47fdd26ed62ab91cd641f76f728d9a7c8d005-360011787798.png)

<div id="note-regarding-the-united-kingdom-uk" />

> 📘 **Nota sobre el Reino Unido (UK)**
>
> <Image alt="blobid0.png" src="https://files.readme.io/33ed45ea49e3308e17a237400ea6c6e9d33c495a9c83197041fdae282f9c65a4-360006637538.png" width="62px" />
>
> * En la plataforma, el Reino Unido se denota con el código UK.
> * El código ISO 3166 para el Reino Unido es GB. El Reino Unido está reservado, pero no asignado, por ISO para el Reino Unido.

<div id="location-discrepancies" />

### Discrepancias de ubicación

En algunos casos, puede haber diferencias en la ubicación derivada de los usuarios entre AppsFlyer y otras plataformas, incluso si otra plataforma utiliza Digital Element para resolver las direcciones IP. Las posibles razones de la discrepancia de ubicación son:

* **Actualizaciones de la base de datos:** para permitir la atribución rápida, AppsFlyer resuelve las direcciones IP en datos de ubicación internamente. AppsFlyer obtiene el mapa global de Digital Element periódicamente y no en tiempo real. Si AppsFlyer y la otra plataforma obtienen datos de Digital Element en diferentes momentos, esto puede explicar las diferencias.
* **Cambios en el ISP:** Las bases de datos de Digital Element cambian rápidamente a medida que los proveedores de servicios (ISP) cambian sus asignaciones de IP.
* **Diferentes planes/métodos:** Digital Element ofrece diferentes planes de paquetes basados en el nivel requerido de granularidad. Otras plataformas que utilizan diferentes paquetes de Digital Element o diferentes métodos para definir el ID de un dispositivo pueden proporcionar resultados diferentes.
* **Proxy o VPN:** Si un usuario implementa una VPN o un proxy, entonces no sabremos la verdadera dirección IP del usuario. La resolución de geolocalización estará en concordancia con la dirección VPN/proxy.
* **Para aprender más:** <Anchor target="_blank" href="https://www.digitalelement.com/blog/the-tricky-science-behind-ip-geolocation/">La ciencia complicada detrás de la geolocalización IP</Anchor>

<div data-zendesk-anchors="determining-user-location=determinaci%C3%B3n-de-la-ubicaci%C3%B3n-del-usuario h_01HDP1SA5YV96YMPPFGN9H6RGE=determinaci%C3%B3n-de-la-ubicaci%C3%B3n-del-usuario h_01HDP1SA5YR7JWDHX2BNXXTKT9=nota-sobre-el-reino-unido-uk location-discrepancies=discrepancias-de-ubicaci%C3%B3n h_01HDP1SA5YNA9N4P9AD4RHWS0J=discrepancias-de-ubicaci%C3%B3n" />
