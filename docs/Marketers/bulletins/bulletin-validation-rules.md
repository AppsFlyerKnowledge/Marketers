---
title: 'Boletín: Reglas de validación'
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
  edited_at: '2026-10-20T03:57:06Z'
  id: 360015724037
  locale: es
  section: Bulletins
  section_id: 6551161473041
  url: https://support.appsflyer.com/hc/es/articles/360015724037
---

<Table>
  <tbody>
    <tr>
      <td>
        **¿Qué hay de nuevo?**
      </td>
      <td>
        La página Reglas de validación tiene un nuevo diseño y más funcionalidades.

        [![](https://files.readme.io/ed1bfe9c2d4a806bd1c00449f6245a965d2be4257a39076f1b33abd24ec8836a-360014789398.jpg)](https://files.readme.io/ed1bfe9c2d4a806bd1c00449f6245a965d2be4257a39076f1b33abd24ec8836a-360014789398.jpg)
      </td>
    </tr>
    <tr>
      <td>
        **Donde**
      </td>
      <td>
        * Página de Reglas de validación
        * Reportes de raw data
        * Postbacks de rechazo
      </td>
    </tr>
    <tr>
      <td>
        **Acciones requeridas**
      </td>
      <td>
        * **Quién:** Anunciantes
        * **Qué:**
          * Familiarízate con el nuevo diseño y las nuevas funciones.
          * **No tienes que hacer nada con las reglas existentes; se migran automáticamente.**
          * Los anunciantes con el plan Protect360 premium deben usar los reportes de fraude de Protect360 para instalaciones, eventos in-app y postbacks de instalación, en lugar de los reportes de reglas de validación de targeting.
      </td>
    </tr>
    <tr>
      <td>
        **Fecha de entrada en vigor**
      </td>
      <td>
        7 de diciembre de 2020
      </td>
    </tr>
    <tr>
      <td>
        **Destaques**
      </td>
      <td>
        A partir de la fecha de entrada en vigor, el nuevo diseño y la nueva funcionalidad estarán disponibles. 

        Cambios:

        * **Lista de reglas**: Las reglas página enumera todas las reglas contenidas en tu cuenta.
        * **Creador de reglas**: 
          * Se permiten varias combinaciones de reglas.
          * Las reglas se pueden aplicar a una o varias aplicaciones.
          * Las reglas se pueden aplicar a todas las fuentes de tráfico: orgánico, no orgánico, agencia, SRN, etc.
          * Un único creador de reglas para las reglas de targeting de campaña y las reglas de Protect360 (con opciones adicionales para los clientes de Protect360).
          * Los clientes de Protect360 también pueden crear reglas para bloquear eventos in-app.
          * Hay nuevas condiciones de reglas.
          * Nuevas opciones para que las reglas bloqueen instalaciones o la atribución.
          * Varias reglas pueden bloquear instalaciones o eventos in-app.
        * **Reportes de raw data**:  

        <table><thead><tr><th rowspan="2">Reportes de reglas de validación de targeting </th><th colspan="2">Dónde están disponibles ahora los datos</th></tr><tr><th>Con el plan Protect360 Premium</th><th>Sin el plan Protect360 Premium</th></tr></thead><tbody><tr><td>Instalaciones inválidas</td><td><p><span>Reporte de raw data de instalaciones de Protect360</span></p></td><td><p><span>Reporte de raw data de instalaciones de Protect360</span></p></td></tr><tr><td>Eventos in-app inválidos</td><td><p><span>Reporte de raw data de eventos in-app de Protect360</span></p></td><td>-</td></tr><tr><td>Postbacks de instalaciones inválidas</td><td><span>Reporte de postbacks de instalaciones bloqueadas de Protect360</span></td><td><span>Reporte de postbacks de instalaciones bloqueadas de Protect360</span></td></tr></tbody></table>

          * Los reportes de raw data contienen el nombre de la regla introducido por quien crea o edita la regla como blocked\_reason\_value; no el ID de la regla.
        * **Postbacks**: contienen el nombre de la regla introducido por quien crea o edita la regla como blocked\_reason\_value; no el ID de la regla.
      </td>
    </tr>
    <tr>
      <td>
        **Lo que debes saber**
      </td>
      <td>
        * Las ad networks y las agencias necesitan <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#permissions-tab">permisos</Anchor> para acceder a los reportes de raw data.
        * Las ad networks y las agencias de clientes que no usan Protect360 no pueden acceder a los dashboards de Protect360 para ver los datos de las reglas de validación.
        * Las reglas con una condición **CTIT**, se cambian durante la migración a **CTIT** AND **is\_preinstalled=no** AND **is\_deeplink=no**.
      </td>
    </tr>
  </tbody>
</Table>

> 📄 **Consulte también**
>
> * <Anchor target="_blank" href="/marketers/es/docs/implement-validation-rules-to-prevent-fraud">Reglas de validación para propietarios de aplicaciones</Anchor>
> * Novedades en AppsFlyer

<div data-zendesk-anchors="h_01HDPFM863RB69KWQ8NV0SQ5NK=consulte-tambi%C3%A9n" />
