---
title: 'Línea de producto: agrupa aplicaciones para la atribución multiplataforma'
metadata:
  keywords:
    - Marketers
    - Cross-Platform Measurement
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-moran-davida
    - Marketers
    - Cross-Platform Measurement
  created_at: '2025-09-30T07:06:57Z'
  edited_at: '2026-09-11T00:16:13Z'
  id: 39524780935185
  locale: es
  section: Manage your apps
  section_id: 6551015977105
  url: https://support.appsflyer.com/hc/es/articles/39524780935185
---
> **En resumen:** Agrupa aplicaciones específicas de cada plataforma bajo una sola marca con Product Line. Desbloquea la atribución multiplataforma y los insights sobre el viaje del usuario en aplicaciones móviles, web y CTV con un Customer User ID (CUID) unificado.

## Acerca de Product Line

Product Line te permite organizar distintas versiones para cada plataforma de la misma aplicación (como Android, iOS, web y CTV) bajo una misma marca. Esto simplifica la gestión de aplicaciones y permite una atribución multiplataforma fluida basada en un identificador de usuario del cliente (CUID).

Con Product Lines, puedes:

* Medir el Lifetime Value (LTV) del usuario en todos los dispositivos
* Analizar el comportamiento en todas las plataformas
* Agrupar internamente aplicaciones bajo la misma marca
* Activar la medición de re-engagement multiplataforma

  Nota: la medición de re-engagement multiplataforma es opcional. Cuando la activas, AppsFlyer puede atribuir la actividad apta de usuarios que regresan a la fuente de medios que volvió a captar al usuario en todas las plataformas. Para más información, consulta <Anchor target="_blank" href="/marketers/es/docs/beta-user-based-cross-platform-re-engagement-attribution">Medición de re-engagement multiplataforma</Anchor>.

Por ejemplo, si un usuario instala tu aplicación en iOS, inicia sesión en la aplicación de PlayStation y reproduce contenido a través de su Samsung TV, puedes ver todo su viaje como un solo usuario.

Para obtener una visión más completa de Product Lines, consulta <Anchor target="_blank" href="/marketers/es/docs/beta-user-based-cross-platform-attribution">Atribución multiplataforma basada en el usuario</Anchor>.

## Cómo configurar una Product Line

### Prerrequisitos

* El **CUID (Customer User Identifier)** debe ser un identificador coherente (como un ID de login o un correo electrónico con hash) en todas las plataformas.
* Implementa la configuración de **CUID SDK o** [**s2s**](https://dev.appsflyer.com/hc/docs/set-customer-user-id).
* Asegúrate de que la aplicación establezca el CUID en cada inicio para reconocer al mismo usuario en todos los dispositivos y sesiones.

### Cómo crear una línea de producto

1. Ve a **My Apps**.
2. En la barra superior, haz clic en **Create Product Line**.
3. Selecciona hasta 30 aplicaciones para incluir -> **Crear**.
4. En la nueva ventana:
   1. Añade un **nombre de línea de producto.**
   2. Activa **Comienza a medir y analizar en varias plataformas.**  
      Nota: si esta opción no está activada, la atribución entre plataformas no funcionará.
   3. Selecciona la **ventana de inactividad.**
   4. Selecciona si quieres activar la medición de re-engagement entre plataformas.
      1. Selecciona la **ventana de re-engagement**.
      2. Selecciona la **ventana de inactividad para re-engagement.**
5. A la derecha verás todas las aplicaciones de la línea de productos.
6. Haz clic en **Crear**.
7. Envía las **instrucciones de implementación de CUID** a tu desarrollador.

**Nota:** La atribución de re-engagement entre plataformas funciona sobre la atribución entre plataformas. Antes de poder activar re-engagement, debes crear una línea de productos, activar la atribución entre plataformas y enviar eventos con un CUID válido. Para saber cómo funciona la atribución de re-engagement entre plataformas, consulta <Anchor target="_blank" href="/marketers/es/docs/beta-user-based-cross-platform-re-engagement-attribution">Atribución de re-engagement entre plataformas</Anchor>.

<div id="how-to-remove-an-app-from-a-product-line" />

<Accordion title="Cómo eliminar una aplicación de una línea de productos">

> 🚧 **Dos puntos (:)**
>
> No se recomienda eliminar una aplicación de una línea de productos. Cuando se elimina o se mueve una aplicación, su configuración de atribución entre plataformas se restablece y los eventos futuros no podrán optar a la atribución entre plataformas hasta que se cree una nueva asignación.

1. Ve a **My Apps**.
2. En la sección **Product Lines**, haz clic en la línea de producto que quieres editar.
3. A la derecha de la ventana verás todas las aplicaciones de la línea de productos.
4. Pasa el cursor sobre la aplicación que quieras eliminar y, a continuación, haz clic en la **X** de esa aplicación.
5. Después de eliminar la aplicación, haz clic en **Update** en la parte inferior de la ventana.

</Accordion>

<div id="how-to-add-an-app-to-a-product-line" />

<Accordion title="Cómo añadir una aplicación a una línea de productos">

1. Ve a **My Apps**
2. En la sección **All Apps**, pasa el cursor sobre la aplicación que quieras añadir y, a continuación, selecciona la casilla.
3. En la cinta del banner superior, selecciona **Add to Product Line**.
4. Selecciona la línea de productos a la que quieres añadir la aplicación.
5. Confirma que todo es correcto en la ventana de la línea de producto y, a continuación, haz clic en **Update** en la parte inferior de la ventana.

</Accordion>

<div id="how-to-delete-a-product-line" />

<Accordion title="Cómo eliminar una línea de producto">

> 🚧 **Dos puntos (:)**
>
> No se recomienda eliminar una línea de producto. Cuando se elimina una línea de producto, su configuración de atribución multiplataforma se restablece y los eventos futuros no podrán optar a la atribución multiplataforma hasta que se cree una nueva asignación.

1. Ve a **Mis aplicaciones**.
2. En la sección **Líneas de producto**, haz clic en los tres puntos de la línea de producto que quieres eliminar.
3. Selecciona **Eliminar línea de producto**.

</Accordion>

## Especificaciones y limitaciones

| Caducado | Nota |
| --- | --- |
| Agrupación de aplicaciones | Las aplicaciones deben pertenecer a la misma marca |
| Número máximo de aplicaciones | Hasta 30 aplicaciones por línea de producto |
| Solo una línea de producto | Una aplicación solo puede pertenecer a una línea de producto a la vez |
| Requisito de CUID | Obligatorio solo para la atribución multiplataforma |
| Ventana de restauración de inactividad | 14-390 días (predeterminado: 90 días) |
| Impacto de eliminar una aplicación | Eliminar una aplicación restablece la configuración de atribución<br /><br />Eliminar una aplicación de una línea de productos afecta a la atribución entre plataformas a partir de ese momento.<br /><br />• Los futuros eventos in-app de la aplicación eliminada no podrán optar a la atribución multiplataforma en esa línea de producto, porque los eventos deben proceder de aplicaciones que pertenezcan a la línea de producto.<br /><br />• Los resultados históricos no se reprocesan de forma retroactiva |

## Preguntas Frecuentes

**¿Puedo usar las líneas de productos solo para organizar aplicaciones?**  
Sí. Deja el interruptor multiplataforma **desactivado** para agrupar aplicaciones solo con fines de gestión.

**¿Qué ocurre si elimino una aplicación de una línea de producto?**  
No se recomienda eliminar una aplicación de una línea de producto. Cuando se elimina o se mueve una aplicación, su configuración de atribución multiplataforma se restablece y los eventos futuros no podrán optar a la atribución multiplataforma hasta que se cree una nueva asignación.

**¿Tiene algún impacto la creación de una Línea de Producto en los resultados clásicos de atribución de AppsFlyer?**

No, crear una Línea de Producto no afecta a los resultados clásicos de atribución de AppsFlyer a nivel de dispositivo

<div data-zendesk-anchors="about-product-line=acerca-de-product-line h_01K6CQ3YXD9QGGMM08WJWNKX65=acerca-de-product-line how-to-set-up-a-product-line=c%C3%B3mo-configurar-una-product-line h_01K6CQ3YXHBXVHE2V0WATR74T5=c%C3%B3mo-configurar-una-product-line prerequisites=prerrequisitos h_01K6CQ3YXHXXYXKKQ3Q7B6N9JQ=prerrequisitos how-to-create-a-product-line=c%C3%B3mo-crear-una-l%C3%ADnea-de-producto h_01K6CQ3YXKBMS7NZSH0GSJMTBM=c%C3%B3mo-crear-una-l%C3%ADnea-de-producto h_01K6CQ8MJFXS6WNWE0GPV18NPT=how-to-remove-an-app-from-a-product-line h_01K6CQPY31VW8BS7DR2TSKRPZZ=dos-puntos- h_01K6CQ8MJFRD9R9SNZ84D6QQB4=how-to-add-an-app-to-a-product-line h_01K6CQ8MJF61375RE001YMMS4E=how-to-delete-a-product-line h_01K6CQPY31DB9DKQJEBX1PXDPT=dos-puntos--1 traits-and-limitations=especificaciones-y-limitaciones h_01K6CQ3YXZM5F0DVGTAQNHHN9B=especificaciones-y-limitaciones faqs=preguntas-frecuentes h_01K6CQD81T4VNMMNVH0X9SZ1TT=preguntas-frecuentes" />
