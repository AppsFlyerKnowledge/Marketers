---
title: Datos de palabras clave
metadata:
  keywords:
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-moran-davida
    - Marketers
    - Mobile Attribution
  created_at: '2023-07-25T08:19:25Z'
  edited_at: '2026-08-12T11:57:00Z'
  id: 17255366785553
  locale: es
  section: Attribution concepts
  section_id: 6551394235409
  url: https://support.appsflyer.com/hc/es/articles/17255366785553
---
> **En resumen:** Obtén datos detallados de palabras clave que te permiten ver qué términos de búsqueda son los más populares, para que puedas optimizar las conversiones orgánicas.

<div id="keyword-data" />

## Datos de palabras clave

La búsqueda orgánica es una fuente de tráfico valiosa para tus aplicaciones. Los usuarios orgánicos no incurren en costos de adquisición y suelen estar entre las cohortes más comprometidas.

Con algunos ajustes en la página de tu aplicación, es posible aumentar la cantidad de nuevas instalaciones orgánicas. Para optimizar las búsquedas orgánicas, necesitas obtener datos de palabras clave orgánicas para tu aplicación.

<div id="ios-keywords" />

### palabras clave de iOS

Si trabajas con Apple Search Ads, puedes obtener datos detallados de palabras clave para tus usuarios no orgánicos atribuidos a Apple Search Ads. En iOS, los datos de palabras clave orgánicas no están disponibles.

<div id="android-keywords" />

### Palabras clave de Android

Google comparte datos de palabras clave orgánicas (en la URL de referencia) para los usuarios que hacen lo siguiente:

* Usa dispositivos Android
* Usa el navegador Chrome
* Visita Google.com y realiza una búsqueda
* Instalar una aplicación desde la página de resultados de Google
* Inicie la aplicación.

El SDK extrae las palabras clave cuando son proporcionadas por Google en el parámetro &utm\_term del referente si es parte del enlace a Google Play. Los valores donde sea posible se encuentran en los siguientes campos de datos en bruto de AppsFlyer: http\_referrer, gp\_broadcast\_referrer, keywords.

Se espera que menos del 1% de los usuarios orgánicos de Android sigan este embudo y tengan datos de palabras clave orgánicas.

En otros escenarios, Google no comparte datos de palabras clave orgánicas. Por ejemplo, los usuarios que buscan en Google Play no tienen datos de palabras clave orgánicas.

<div id="note" />

> 📘 **Nota:**
>
> Esta limitación es aplicada por Google a todos los proveedores externos, incluidos todos los proveedores de atribución.

<div id="using-thekeyworddata" />

### Usando los datos de palabras clave

Los datos de palabras clave orgánicas se encuentran en lo siguiente:

* Informes de datos orgánicos en bruto  
  En AppsFlyer, desde el menú lateral, selecciona Informe > Exportación de Datos en Crudo para ver el desglose de las palabras clave orgánicas utilizadas.
* Informes avanzados   
  Ve a los informes de Pivot, Retención y Cohorte y agrupa por palabras clave.  
  Compara la calidad de los usuarios orgánicos según sus palabras clave.
* Mensajes de <Anchor target="_blank" href="/marketers/es/docs/push-api-streaming-raw-data">Push API</Anchor>

<div id="testing-organickeyworddata" />

### Pruebas de datos de palabras clave orgánicas

1. Usa un dispositivo Android <Anchor target="_blank" href="/marketers/es/docs/registering-test-devices">incluido en la lista de permitidos</Anchor>.
2. Abre el navegador Chrome y ve a Google.com.
3. Utiliza una palabra clave fuerte para buscar tu aplicación.   
   Este ejemplo utiliza "hoteles esta noche".  
     
   <Image align="center" alt="organic_keywords_search.jpg" src="https://files.readme.io/b06db96b53df1502939b86cefd7217991d842f1c7e736cab6ba2c6e0de691400-32966747169425.jpg" width="426px" />
4. Haga clic en Instalar para ser redirigido a Google Play Store.
5. Instala y lanza la aplicación.  
   <Image align="center" alt="Hotels_Tonight_3.png" src="https://files.readme.io/c455f8229ba7879157eec6782d0eb2d94a91e1080a3c081f5452cc7e92608047-205710046.png" width="373px" />
6. Busque la palabra clave en las fuentes de AppsFlyer descritas arriba.

<div data-zendesk-anchors="keyword-data=datos-de-palabras-clave h_01HKA1D1TW1R20X6K05Q9GX904=datos-de-palabras-clave ios-keywords=palabras-clave-de-ios h_01HKA1D1TW9YXBMGERHW4EHZZN=palabras-clave-de-ios android-keywords=palabras-clave-de-android h_01HKA1D1TWT1VQ6NZ789BTCZJX=palabras-clave-de-android h_01HKA1D1TW7E2RM7SXC9R5SA99=nota using-the%C2%A0keyword%C2%A0data=usando-los-datos-de-palabras-clave h_01HKA1D1TWRPGTNGJKF7T1R71B=usando-los-datos-de-palabras-clave testing-organic%C2%A0keyword%C2%A0data=pruebas-de-datos-de-palabras-clave-org%C3%A1nicas h_01HKA1D1TW5W9A72V2NMPX932H=pruebas-de-datos-de-palabras-clave-org%C3%A1nicas" />
