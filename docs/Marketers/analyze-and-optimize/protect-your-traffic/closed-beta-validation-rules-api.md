---
title: '[Beta cerrada] API de reglas de Validación'
metadata:
  keywords:
    - Marketers
    - Closed beta
    - Protect360
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-yanai
    - Marketers
    - Protect360
  created_at: '2026-07-02T09:03:27Z'
  edited_at: '2026-09-29T00:03:37Z'
  id: 48341412127249
  locale: es
  section: Protect your traffic
  section_id: 6551015912465
  url: https://support.appsflyer.com/hc/es/articles/48341412127249
---
<span class="af-tag af-tag--closed-beta">Closed beta</span>

> **At a glance:** Automatiza la creación y la gestión de reglas de validación a gran escala. La API de reglas de Validación permite a los equipos técnicos crear, actualizar, aplicar parches y eliminar reglas de forma programática, superando los límites de valor de la IU y eliminando la carga operativa de la gestión manual de reglas.

<div id="note" />

> 📘 **Advertencia**
>
> La API de reglas de validación está disponible para los clientes de Protect360. Actualmente está en beta cerrada, y el acceso es limitado y se habilita por cuenta. Ponte en contacto con tu responsable de Customer Success (CSM) para solicitar acceso.

<div id="about-the-validation-rules-api" />

## Acerca de la API de reglas de validación

Hasta ahora, las reglas de validación solo se podían gestionar a través de la IU de AppsFlyer. Esto generaba dos limitaciones:

* Un límite de aproximadamente 17.000 valores por regla. No es suficiente para listas de bloqueo a escala empresarial.
* Cada actualización requería trabajo manual en la IU. Esto consume mucho tiempo y supone un coste operativo elevado para los equipos que hacen cambios frecuentes.

La API de reglas de validación elimina ambas limitaciones. Ofrece a los equipos técnicos un control programático total sobre sus reglas, admite hasta 300.000 valores por regla en reglas grandes y permite automatizar actualizaciones de alta frecuencia sin usar la IU.

Las reglas creadas mediante la API se marcan como gestionadas por API y aparecen como de solo lectura en la IU de AppsFlyer. Las reglas existentes creadas en la IU no se ven afectadas. Las reglas gestionadas por la IU y las gestionadas por API coexisten en la misma cuenta.

<Accordion title="¿Es para ti?">

La API de reglas de validación está diseñada para casos de uso específicos. No está pensada para sustituir la IU para todos los clientes. Considera la API si:

* Gestionas una lista de bloqueo o lista de permitidos que supera, o está a punto de alcanzar, el límite de ~17.000 valores de la IU.
* Tu equipo quiere integrar la gestión de reglas en sus propios sistemas, scripts o canalizaciones de automatización.
* Tu lógica de fraude o de bloqueo de tráfico cambia con frecuencia, y las actualizaciones manuales en la IU se han convertido en un cuello de botella.

Si gestionas un número reducido de reglas que rara vez cambian, la interfaz de usuario de Reglas de validación sigue siendo la forma más sencilla de gestionarlas.

</Accordion>

<Accordion title="Acceso y elegibilidad">

La API de Reglas de validación está disponible para los clientes de Protect360. Actualmente está en beta cerrada y el acceso se habilita por cuenta.

* Requiere una suscripción a Protect360.
* Controlado mediante un indicador de funcionalidad. Contacta con tu gerente de Éxito del Cliente (CSM) para solicitar acceso y activación.
* Las reglas grandes (hasta 300.000 valores) requieren una habilitación especial adicional, además del Acceso a la API estándar. Contacta con tu CSM para activarlas.

</Accordion>

<div id="how-it-works" />

## Cómo funciona

<Accordion title="Autenticar">

La API utiliza la autenticación con token Bearer (JWT).

1. En tu cuenta de AppsFlyer, ve a **Centro de Seguridad** > **tokens de API**.
2. Genera un token.
3. Incluye el token en el encabezado **Authorization** de tus solicitudes a la API.

<div id="note-1" />

> 📘 **Advertencia**
>
> El Acceso a la API debe estar habilitado por cuenta para que el token funcione. Contacta con tu CSM para activarlo.

</Accordion>

<Accordion title="Qué puedes hacer">

| Acción | Nota |
| --- | --- |
| Listar reglas | Recupera todas las reglas activas (habilitadas y deshabilitadas) de tu cuenta. |
| Crear una regla | Crea una regla nueva de forma programática. |
| Recuperar una regla | Obtén todos los detalles de la regla, incluidas todas las condiciones. |
| Actualizar una regla | Sobrescribe una regla existente con una nueva configuración. |
| Habilitar / deshabilitar una regla | Activa o desactiva una regla sin eliminarla. |
| Eliminar regla | Elimina una regla de forma permanente. |
| Aplicar un parche a una regla | Añade, elimina o sustituye valores de una única dimensión sin reescribir toda la regla. |

El endpoint de parche es especialmente útil para actualizaciones de alta frecuencia. Actualizas solo lo que ha cambiado, no toda la regla. Esto funciona bien para flujos de trabajo como las actualizaciones diarias de la lista de bloqueo de fuentes de fraude.

</Accordion>

<div id="scope-and-supported-configurations" />

## Alcance y configuraciones compatibles

La API de reglas de validación admite actualmente un subconjunto definido de lo que está disponible en el creador de reglas de la interfaz de usuario.

* Se aplica solo a eventos de instalación. Los eventos in-app no son compatibles con esta versión.
* Dimensiones admitidas:
  * Fuente de tráfico (población): ID del sitio, fuente de medios, agencia, campaña, ID de campaña, ID del conjunto de anuncios y ID del anuncio
  * Condiciones: geolocalización, plataforma
* Operadores compatibles: está en la lista, no está en la lista.
* Lógica entre dimensiones: solo AND. OR no es compatible.
* Tipos de regla: Match (bloquear el tráfico que coincide) o Do not match (bloquear el tráfico que no coincide).
* Tipos de fuente: todo el tráfico, todo el tráfico no orgánico o tráfico no orgánico de una agencia específica.
* Acciones de bloqueo compatibles:
  * Bloquear la atribución y corregirla a la última fuente de medios válida.
  * Bloquear la atribución y marcar las instalaciones como inválidas. Estas no aparecerán en el dashboard de Protect360.

<Accordion title="Tamaño y límites de la regla">

|  | Regla estándar | Regla grande |
| --- | --- | --- |
| Valores totales en todas las condiciones | Hasta un 17,000 | Hasta un 300,000 |
| Requiere una habilitación especial | Sí | Sí |
| Máx. de reglas por cuenta | 100 | Hasta un 5 |

Límites adicionales:

* Máx. 2.000 ID de app por regla.
* 2 MB por llamada a la API. Las solicitudes que superen este límite (aproximadamente 50.000 valores) deben dividirse entre varias llamadas.
* 300.000 valores por regla grande, en todas las dimensiones combinadas, independientemente del tipo de operación (crear, actualizar o aplicar parche).

Si superas cualquier límite, se devuelve un error que identifica qué límite se ha superado.

</Accordion>

<Accordion title="Acceso a los datos de tráfico bloqueado">

El tráfico bloqueado por reglas gestionadas por API se reporta de forma idéntica al tráfico bloqueado por reglas creadas en la IU.

| Informe | Ubicación |
| --- | --- |
| Exportación de raw data | Protect360 & Reglas de validación > Instalaciones |
| Casillero de datos | Reportes de Protect360 > reporte de blocked\_installs |
| API Pull | Exportación de raw data |

</Accordion>

<Accordion title="Documentación técnica">

Para consultar todos los detalles técnicos, incluidas las referencias de endpoints, los esquemas de solicitud y respuesta, y los códigos de error, consulta la <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/updaterule">referencia de la API de reglas de validación</Anchor>.

</Accordion>

<Accordion title="Especificaciones y limitaciones">

| Caducado | Descripción |
| --- | --- |
| Soporte de eventos | Solo eventos de instalación. Los eventos in-app no son compatibles en esta versión. |
| Lógica | Solo se admite la lógica AND entre dimensiones. OR no es compatible. |
| Interacción con la IU | Las reglas creadas mediante la API aparecen como de solo lectura en la IU. Edítalas mediante la API. |
| Tamaño de la llamada | 2 MB por llamada a la API (aproximadamente 50.000 valores). Las actualizaciones más grandes deben dividirse en varias llamadas. |

</Accordion>

<div id="faq" />

## Preguntas frecuentes

<Accordion title="¿Quién puede usar la API de reglas de validación?">

La API de reglas de validación está disponible para los clientes de Protect360. Actualmente está en beta cerrada y el acceso se habilita por cuenta. Contacta con tu CSM para solicitar acceso.

</Accordion>

<Accordion title="¿Las reglas gestionadas mediante la API aparecen en la interfaz de usuario?">

Sí. Las reglas creadas mediante la API son visibles en la interfaz de usuario de AppsFlyer, pero se marcan como gestionadas mediante la API y aparecen como de solo lectura.

</Accordion>

<Accordion title="¿Puedo gestionar algunas reglas mediante la API y otras mediante la interfaz de usuario?">

Sí. Las reglas gestionadas mediante la API y las creadas en la interfaz de usuario coexisten en la misma cuenta. Las reglas gestionadas mediante la API aparecen como de solo lectura en la interfaz de usuario. No se puede acceder a las reglas creadas en la interfaz de usuario a través de la API.

</Accordion>

<Accordion title="¿Puedo editar una regla gestionada mediante la API en la interfaz de usuario?">

No, la regla aparece como de solo lectura. En su lugar, debes usar la API para actualizarla.

</Accordion>

<Accordion title="¿Cuál es la diferencia entre Update y Patch?">

Update sobrescribe la regla completa. Patch actualiza solo una dimensión, añadiendo, eliminando o sustituyendo valores sin reescribir toda la regla. Usa Patch para actualizaciones frecuentes y específicas.

</Accordion>

<Accordion title="¿Qué sucede si supero un límite?">

La API devuelve un error que identifica qué límite se ha superado. Divide las actualizaciones grandes en varias llamadas a la API para mantenerte dentro del límite de 2 MB por llamada.

</Accordion>

<Accordion title="¿Cuántas reglas puedo tener?">

Hasta 100 reglas estándar por cuenta y hasta 5 reglas grandes por cuenta. Tanto las reglas estándar como las grandes requieren una activación especial. Contacta con tu CSM para activarlas.

</Accordion>

<Accordion title="¿Se admite la lógica 'OR'?">

N.º Solo se admite la lógica "AND" entre dimensiones.

</Accordion>

<Accordion title="¿Qué tipos de eventos tienen soporte?">

Solo eventos de instalación. Los eventos in-app no tienen soporte en esta versión.

</Accordion>

<div id="see-also" />

> 📄 **Véase también**
>
> * Implementa reglas de validación para evitar el fraude

<div data-zendesk-anchors="h_01KWH1NW583T8SPZFF5REMQC6V=advertencia about-the-validation-rules-api=acerca-de-la-api-de-reglas-de-validaci%C3%B3n h_01KWH1NW58A3YK7FKR1C4WBRF3=acerca-de-la-api-de-reglas-de-validaci%C3%B3n how-it-works=c%C3%B3mo-funciona h_01KWH1NW58P5AB47847E99YG6G=c%C3%B3mo-funciona h_01KWH1NW594YT5S9FT8VWX77SG=advertencia-1 scope-and-supported-configurations=alcance-y-configuraciones-compatibles h_01KWH1NW594XM03VQKNJPY37B7=alcance-y-configuraciones-compatibles faq=preguntas-frecuentes h_01KWH1NW59J9QHP37KMMK18JBG=preguntas-frecuentes h_01KWH1NW59G3WG3KHVRGY9TMV4=v%C3%A9ase-tambi%C3%A9n" />
