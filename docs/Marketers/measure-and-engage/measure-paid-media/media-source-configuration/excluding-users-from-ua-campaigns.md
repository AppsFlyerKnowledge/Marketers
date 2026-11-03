---
title: Excluir usuarios de las campañas de UA
metadata:
  keywords:
    - Advertisers
    - Agencies
    - Ad Networks
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
    - Agencies
    - Ad Networks
  created_at: '2020-05-03T10:11:31Z'
  edited_at: '2023-02-15T15:01:47Z'
  id: 360007949158
  locale: es
  section: Media source configuration
  section_id: 6551067072785
  url: https://support.appsflyer.com/hc/es/articles/360007949158
---
> **De un vistazo:** Excluye a los usuarios existentes de las campañas de adquisición de usuarios (UA) para obtener más instalaciones con el mismo presupuesto y mejorar el ROAS.

## Problemas y consecuencias

Si tu aplicación recibe tráfico de varias fuentes de medios, estas fuentes pueden **apuntar a tus usuarios existentes en sus campañas de UA**.

El rendimiento de la campaña puede verse afectado por los siguientes motivos:

* **Pagos dobles**: pagar por las impresiones/clics de usuarios que ya pagaste en el pasado.
* **Tasas de conversión distorsionadas**: las campañas de UA parecen menos exitosas. Hay menos instalaciones ya que las impresiones se desperdician en los usuarios existentes.
* **Pérdida de usuarios alternativos**: quienes no son usuarios podrían haber visto los anuncios y convertirse en tus usuarios móviles.

El <Anchor target="_blank" href="/marketers/es/docs/self-reporting-networks-srns#what-is-srn-mistargeting">error de targeting de SRN</Anchor> es un problema de rendimiento similar y común. Este problema significativo puede ocurrir si tanto tu UA como las campañas de retargeting tienen la misma SRN. <Anchor target="_blank" href="/marketers/es/docs/self-reporting-networks-srns#la-orientación-incorrecta-es-un-problema">Aprender más</Anchor> 

## Soluciones

Estas soluciones describen cómo actualizar las redes de publicidad para excluir a los usuarios existentes de las campañas de UA.

### Actualización manual

Recopila tu raw data de instalación a nivel de usuario de AppsFlyer para crear listas de ID de dispositivo. Luego, envía estas listas a las redes publicitarias para garantizar la exclusión del usuario.

Hay varias formas de agregar este raw data a tu sistema de Business Intelligence (BI):

* Descargar reportes de raw data
* Usar solicitudes periódicas de raw data de la Pull API
* Usar la Push API para implementar la recopilación en tiempo real
* Obtener datos de conversión del SDK

> 📘 **Nota**
>
> En el intervalo de tiempo entre el envío manual de la siguiente lista a las redes de publicidad, las campañas de UA pueden apuntar a los usuarios más nuevos de la aplicación.

### Audiencias

**<Anchor target="_blank" href="/marketers/es/docs/audiences-guide">Audiences</Anchor>** es una función premium de AppsFlyer. Todos los días, los segmentos seleccionados de tu base de usuarios se envían automáticamente a varias redes de publicidad, según lo elijas.

**Audiences** es muy útil para mantener listas de exclusión:

* **Bajo esfuerzo**: no requiere que tú o la red de publicidad realicen trabajos de desarrollo ni mantenimiento.
* **Fácil uso**: después de una breve configuración inicial, puedes comenzar a subir audiencias.
* **Eficiente**: los segmentos se envían automáticamente a las redes de publicidad cada 24 horas.

<div data-zendesk-anchors="issues-and-consequences=problemas-y-consecuencias solutions=soluciones manual-update=actualizaci%C3%B3n-manual audiences=audiencias" />
