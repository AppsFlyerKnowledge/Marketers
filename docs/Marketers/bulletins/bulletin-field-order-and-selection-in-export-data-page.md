---
title: 'Boletín: orden y selección de campos en la página de exportación de datos'
metadata:
  keywords:
    - Advertisers
    - Ad Networks
    - Marketers
    - Raw Reports
table_of_contents: false
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-rona-einat
    - Marketers
    - Raw Reports
    - Ad Networks
  created_at: '2021-05-31T19:26:41Z'
  edited_at: '2026-10-20T03:56:54Z'
  id: 360021043718
  locale: es
  section: Bulletins
  section_id: 6551161473041
  url: https://support.appsflyer.com/hc/es/articles/360021043718
---

<Table>
  <tbody>
    <tr>
      <td>
        **Qué ha cambiado**
      </td>
      <td>
        En la <Anchor target="_blank" href="/marketers/es/docs/raw-data-export-page">página Export Data</Anchor>, ahora también puedes definir la secuencia de columnas del reporte, además de la opción existente de selección de campos.
      </td>
    </tr>
    <tr>
      <td>
        **Fecha de entrada en vigor**
      </td>
      <td>
        16 de junio, 2021
      </td>
    </tr>
    <tr>
      <td>
        **Donde**
      </td>
      <td>
        Página de datos exportados
      </td>
    </tr>
    <tr>
      <td>
        **Qué ha cambiado**
      </td>
      <td>
        Usa la opción **Report (CSV) field order** para especificar la secuencia de columnas en los reportes.

        | Configuración | Selección de campos permitida | Comentarios |
        | --- | --- | --- |
        | Por defecto | Sí | * Los campos seleccionados se ordenan según una plantilla de AppsFlyer.<br />* A partir de ahora, la secuencia se mantendrá. Los campos futuros se anexarán a la derecha de los campos existentes. |
        | Alfabético (A-Z) | Sí | Los campos seleccionados se ordenan alfabéticamente (orden ascendente). |
        | Alfabético (Z-A) | Sí | Los campos seleccionados se ordenan en orden inverso alfabéticamente (orden descendente). |
        | Heredado | No | * Los campos se ordenan según la secuencia de las columnas en los reportes elaborados utilizando la versión anterior de la página de datos exportados.<br />* La selección de campos es fija y no se puede cambiar.<br />* Existen variaciones en los informes por campo según el informe específico. |

        La [hoja de cálculo del orden de campos](https://docs.google.com/spreadsheets/d/e/2PACX-1vRGYcMOgC5yy_82yn3DWd3ucLE5KtuTA72eJfvu5KVB9fFH_mYwzM3KpR_inQOnat-KzgVjuuvXa6_g/pub?output=xlsx) contiene una pestaña predeterminada y otra heredada, ambas con la lista del orden de campos correspondiente.
      </td>
    </tr>
    <tr>
      <td>
        **Procedimiento**
      </td>
      <td>
        ![FeldOrder.png](https://files.readme.io/d81e8d0494cbf3a8ee959990200da10889bb7a581c6018711b7163d8fedcd2d8-360020954138.png)

        **Para cambiar el orden de los campos:**

        1. En la pestaña **Report fields**, selecciona una opción de **Report (CSV) field order**.
        2. Si es necesario, cambia los campos seleccionados seleccionando o deseleccionando los campos que necesites.
        3. Haz clic en **Descargar**.
      </td>
    </tr>
  </tbody>
</Table>
