---
title: 'Boletín: Tipos de engagements'
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
  edited_at: '2026-10-20T03:55:53Z'
  id: 20161875390865
  locale: es
  section: Bulletins
  section_id: 6551161473041
  url: https://support.appsflyer.com/hc/es/articles/20161875390865
---

<Table>
  <tbody>
    <tr>
      <td>
        Sección.
      </td>
      <td>
        Description
      </td>
    </tr>
    <tr>
      <td>
        **¿Qué hay de nuevo?**
      </td>
      <td>
        Se han agregado nuevos campos a los reportes de raw data.

        * engagement\_type
        * contributor1\_engagement\_type
        * contributor2\_engagement\_type
        * contributor3\_engagement\_type

        Estos parámetros pueden devolver los siguientes valores: precarga, click\_to\_download, click\_to\_app, engaged\_click, engaged\_view, vista, listening, o si no se reporta, estará vacío

        | Tipo de engagement: | Description |
        | --- | --- |
        | Precarga | La app la precarga el OEM de fábrica o el proveedor la primera vez que se activa el dispositivo. Alternativamente, un asistente pide a los usuarios que descarguen la aplicación cuando el dispositivo se activa por primera vez. |
        | click\_to\_download | Cuando el usuario hace clic en un anuncio, la app se descarga e instala automáticamente en el dispositivo sin redireccionarlo a una app store. |
        | click\_to\_app | Un clic en un anuncio, el escaneo de un código QR, un deep link o cualquier otro clic que redireccione al usuario a la aplicación o a la tienda de aplicaciones correspondiente para descargar la aplicación. |
        | engaged\_click | Un clic que mantiene al usuario en el mismo contexto, interactuando con el anuncio, y NO lo envía a la tienda de aplicaciones o a abrir la aplicación. |
        | engaged\_view | Una vista comprometida es cuando se produce una vista significativa. Algunos ejemplos son cuando un usuario ve al menos 10 segundos o más de un anuncio de vídeo saltable o una finalización de vídeo |
        | Ver | Un ad view es cuando se muestra un anuncio y se produce una impresión. Algunos ejemplos son los banners, los anuncios intersticiales o los vídeos sin interacción. |
        | listening | El listening se produce cuando un usuario escucha un anuncio de audio, como un anuncio de podcast. |
      </td>
    </tr>
    <tr>
      <td>
        **Fecha de entrada en vigor**
      </td>
      <td>
        17 de enero de 2024
      </td>
    </tr>
    <tr>
      <td>
        **Esto afecta a**
      </td>
      <td>
        * Anunciantes y agencias con acceso a reportes de raw data que trabajan con redes publicitarias que reportan estos campos.
          * AppsFlyer completará preload y click\_to\_app para los deep links independientemente de si las ad networks reportan esos campos.
        * Los reportes de raw data a los que afecta son: Data Locker, Pull API, Export Page, and Push API.
          * Estos campos no están seleccionados de forma predeterminada (con la excepción de seleccionar todo en Push API), para usar estos campos debes seleccionarlos manualmente en el producto de raw data.
      </td>
    </tr>
  </tbody>
</Table>
