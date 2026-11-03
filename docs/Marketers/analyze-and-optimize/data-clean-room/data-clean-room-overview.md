---
title: Dashboard General - Data Clean Room
metadata:
  keywords:
    - Premium
    - Marketers
    - Data Clean Room
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-inbar-agassi
    - Marketers
    - Data Clean Room
  created_at: '2022-03-08T14:47:36Z'
  edited_at: '2026-08-12T11:52:43Z'
  id: 4626852381713
  locale: es
  section: Data Clean Room
  section_id: 4591191779217
  url: https://support.appsflyer.com/hc/es/articles/4626852381713
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

**![privacy_cloud_logo.png](https://files.readme.io/5862beb63a4b22f68fc230f89c3faa260a15ab40e1defa70c59604d5a81e759d-5583061038225.png)**

> **En resumen:** Enriquece tus datos a nivel de usuario comparándolos con los datos de atribución a nivel de usuario de AppsFlyer para crear reportes agregados y obtener insights que aprovechen el valor de los datos combinados.

## Introducción

A lo largo de su historia, el ecosistema de marketing móvil ha utilizado datos a nivel de usuario para obtener insights y optimizar las campañas publicitarias:

1. Las fuentes de medios proporcionaron datos a nivel de usuario a los proveedores de medición de atribución (como AppsFlyer), quienes los usaron para proporcionar la atribución y luego los transmitieron a los anunciantes.
2. Los anunciantes compararon estos datos a nivel de usuario con sus propios datos a nivel de usuario (de sistemas de BI o CRM, por ejemplo) y, a continuación, los analizaron y agruparon según fuera necesario para obtener los insights agregados que necesitaban para optimizar sus campañas.

Con la llegada de la era de la privacidad de los usuarios, el acceso a los datos a nivel de usuario de las fuentes de medios se ha restringido significativamente:

1. Las fuentes de medios proporcionan datos a nivel de usuario a los proveedores de medición de la atribución (como AppsFlyer), que los utilizan para proporcionar la atribución; **sin embargo, ahora se les bloquea la posibilidad de transmitir estos datos a nivel de usuario a los anunciantes**.
2. Esto hace que los anunciantes no puedan hacer coincidir los datos de atribución a nivel de usuario con sus propios datos como lo hacían en el pasado, lo que les impide obtener los insights que necesitan.

Este es precisamente el "punto ciego de los datos" que la Data Clean Room (DCR) de AppsFlyer se encarga de corregir.

### ¿Cómo Funciona?

En lugar de pasar los datos de atribución a nivel de usuario al ***anunciante*** para que este pueda compararlos, ***DCR se encarga de hacerlos coincidir***, lo que básicamente transfiere esta responsabilidad a AppsFlyer. Luego, DCR analiza y agrupa estos datos y los transmite al anunciante de forma agregada, permitiendo obtener los insights agregados necesarios **mientras preserva la privacidad del usuario.**

### ¿Cómo obtener los datos el DCR?

DCR utiliza actualmente 2 tipos de datos diferentes:

* **Datos de origen personalizados:** datos a nivel de usuario cargados en el almacenamiento en la nube para que los utilice DCR. Estos datos provienen de los sistemas internos del anunciante (como los sistemas de BI o CRM).
* **Datos de atribución:** Datos a nivel de usuario proporcionados por las fuentes de medios a AppsFlyer para su atribución

### ¿Qué hace DCR con los datos?

Funciona de acuerdo con los principios estándar de las bases de datos. En otras palabras, hace coincidir los datos de diferentes tablas (o **"fuentes"**) en un único conjunto de datos. Este conjunto de datos único se usa luego para crear **reportes** que usan los datos combinados:

* Para hacer coincidir los datos de diferentes fuentes y combinarlos en un solo conjunto, cada fuente debe compartir al menos un campo que identifique a un usuario único de la aplicación **("identificador")** en común con otra fuente.
* Al usar identificadores para hacer coincidir tus datos a nivel de usuario con los datos de atribución a nivel de usuario, DCR crea un conjunto de datos combinado a nivel de usuario.
* Luego, para proporcionar insights y, al mismo tiempo, mantener la privacidad del usuario, DCR procesa estos datos para crear **reportes agregados,** agrupados según las características **("dimensiones")** que definas.

## Terminología DCR

Los siguientes son algunos de los términos DCR que se utilizan con frecuencia:

* **Conector:** Tu bucket de AWS o GCS (propiedad del anunciante) en el que se almacenan los datos DCR. Un conector puede incluir carpetas para los datos de origen que fluyen hacia el DCR y/o destinos para los reportes que salen. Puedes usar uno o varios conectores para los datos que entran y salen del DCR.
* **Fuentes:**
  * **Fuente del anunciante:** Tu archivo de datos de first-party que se incluye en el DCR (destinado a hacer coincidir y enriquecer los datos de atribución de AppsFlyer). Se pueden cargar nuevas versiones de los archivos fuente para su procesamiento con una frecuencia de hasta 6 horas. Cuando configuras una fuente en la plataforma DCR de AppsFlyer, defines su **estructura** y **ubicación**:
    * **Estructura de la fuente:** Una lista de los campos de datos de la fuente y la categoría que asignes a cada uno para ver cómo se usará en los reportes (identificador, dimensión o métrica).
    * **Ubicación de la fuente:** La carpeta del servicio en la nube de la que AppsFlyer obtiene el archivo fuente cada vez que lo actualizas. Esta carpeta se encuentra dentro de un depósito ("conector").
  * **Datos de atribución:** Datos de atribución a nivel de usuario de tu cuenta de AppsFlyer (se utilizan para hacer coincidir y enriquecer los datos de los anunciantes en el DCR)
* **Reporte:** Un archivo de datos que sale del DCR después del procesamiento. Los reportes se crean cada vez que se cargan nuevas versiones de los archivos fuente relacionados. Cuando configuras un reporte en la plataforma DCR de AppsFlyer, defines su **estructura** y **destino**:
  * **Estructura del reporte:** Especificación de las fuentes de los anunciantes y los datos de atribución que se utilizarán para crear el reporte, los identificadores por los que se unirán, las métricas que se incluirán y las dimensiones por las que se agrupará el reporte.
  * **Destino del reporte:** La carpeta del servicio en la nube a la que AppsFlyer envía el reporte cada vez que se procesa. Esta carpeta se encuentra dentro de un depósito ("conector").

## Trabajando con DCR (configuración del flujo de trabajo)

Data Clean Room (DCR) de AppsFlyer es muy flexible en cuanto a los tipos de datos que eliges cargar, los reportes que recibes, el tiempo y la frecuencia del procesamiento. Por este motivo, implica un proceso de planificación y configuración relativamente importante, que probablemente implique la colaboración de varias personas de la organización.

Sigue estos pasos para configurar DCR a fin de satisfacer las necesidades de tu organización:

1. Piensa los reportes que deseas recibir de DCR. Estos reportes son el resultado de enriquecer tus fuentes de anunciantes con datos de atribución de AppsFlyer. Determina las fuentes de datos propias que debes cargar en el DCR para crear estos reportes.
2. <Anchor target="_blank" href="/marketers/es/docs/data-clean-room-setting-up-cloud-services">Crea la estructura básica de almacenamiento en la nube</Anchor> para respaldar esas fuentes y reportes.
3. Define las queries que extraerán los datos y generarán los archivos de datos de origen; crea prototipos de los archivos de datos de origen.
4. Desarrolla las automatizaciones que extraerán los datos, crea las subcarpetas de origen y carga las fuentes y los <Anchor target="_blank" href="/marketers/es/docs/data-clean-room-working-with-sources#_success-files">archivos \_SUCCESS</Anchor> periódicamente.
5. Configura tus <Anchor target="_blank" href="/marketers/es/docs/data-clean-room-working-with-sources">fuentes</Anchor> en la plataforma DCR de AppsFlyer.
6. Configura tus <Anchor target="_blank" href="/marketers/es/docs/data-clean-room-working-with-reports">reportes</Anchor> en la plataforma DCR de AppsFlyer.
7. Desarrolla las automatizaciones que incorporarán los reportes una vez que el DCR los entregue a tu almacenamiento en la nube.

<div data-zendesk-anchors="introduction=introducci%C3%B3n h_01HE7SDH5PWCW6YG00GC12W4BS=introducci%C3%B3n how-does-it-work=c%C3%B3mo-funciona h_01HE7SDH5PW64CHNJVJJ30V5ZY=c%C3%B3mo-funciona how-does-the-dcr-obtain-data=c%C3%B3mo-obtener-los-datos-el-dcr h_01HE7SDH5P82HCEN52ZBPMQV16=c%C3%B3mo-obtener-los-datos-el-dcr what-does-the-dcr-do-with-the-data=qu%C3%A9-hace-dcr-con-los-datos h_01HE7SDH5PWDQ61389TT7V83F8=qu%C3%A9-hace-dcr-con-los-datos dcr-terminology=terminolog%C3%ADa-dcr h_01HE7SDH5P3QSG874XASXNH1YS=terminolog%C3%ADa-dcr working-with-the-dcr-setup-workflow=trabajando-con-dcr-configuraci%C3%B3n-del-flujo-de-trabajo h_01HE7SDH5P0S9542P2CB22KKVT=trabajando-con-dcr-configuraci%C3%B3n-del-flujo-de-trabajo" />
