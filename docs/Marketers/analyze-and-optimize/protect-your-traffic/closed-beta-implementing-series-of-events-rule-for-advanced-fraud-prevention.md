---
title: >-
  [Beta cerrada] Implementación de la regla de serie de eventos para la
  prevención avanzada del fraude
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
  created_at: '2024-07-10T09:41:19Z'
  edited_at: '2026-09-30T00:03:38Z'
  id: 26596474431761
  locale: es
  section: Protect your traffic
  section_id: 6551015912465
  url: https://support.appsflyer.com/hc/es/articles/26596474431761
---
<span class="af-tag af-tag--closed-beta">Closed beta</span>

> **At a glance:** La serie de eventos de las reglas de validación permite a los anunciantes definir una secuencia de eventos por la que debe pasar un usuario real. Cualquier desviación del orden definido, o del tiempo entre eventos, se detecta y se bloquea.

## Introducción

Los anunciantes pueden definir una secuencia de eventos por la que debe pasar un usuario real en tu aplicación. AppsFlyer evalúa esta secuencia mediante una ventana de evaluación que comienza el día en que se guarda la regla: crece cada día hasta los 30 días y, después, se convierte en una ventana móvil de 30 días que avanza diariamente. Los eventos activados antes de que se creara la regla no se evalúan nunca.

Si la secuencia se rompe, ya sea en el orden o en el tiempo, el usuario se considera falso y:

* Cualquier evento in-app, así como las sesiones, después de la interrupción se bloquean inmediatamente.
* La instalación se bloquea en post-attribution si entra dentro de la ventana de post-attribution (7 días)
* Los eventos in-app asociados dentro de la ventana de evaluación se bloquean como parte del proceso de post-attribution
* Otros eventos in-app que cumplen las condiciones de la regla en otras partes de la aplicación no se ven afectados

Nota: si editas la regla de cualquier forma, incluida la selección de la aplicación, las condiciones, la fuente de tráfico, la secuencia de eventos o la activación/desactivación, la ventana de evaluación se restablece al día 0.

## ¿A quién va dirigido?

Esta función solo es adecuada para:

* **Eventos del SDK**: aplicaciones que crearán reglas solo con eventos del SDK.
* **Eventos no repetitivos**: aplicaciones que tienen una secuencia de eventos en la que los eventos no se producirán más de una vez en la secuencia. Si el mismo evento se produce más de una vez en la secuencia (por ejemplo, el evento C se envía dos veces), se trata como una infracción y los eventos asociados se bloquean.
* **Tráfico NOI**: esta función solo está disponible para el tráfico NOI

## Cómo configurar una regla de serie de eventos

Sigue estas instrucciones para configurar una regla de serie de eventos:

1. Ve a **Configuración > Reglas de validación**
2. Haz clic en **+ Nueva regla**
3. Dale un nombre a la regla
4. Selecciona la pestaña **Post attribution**
5. Selecciona la aplicación para la que quieres configurar la regla  
   Nota: solo puedes seleccionar una aplicación para cada regla
6. Define la fuente de tráfico en la que se ejecutará la regla
7. Elige las condiciones. Actualmente, las opciones son:
   1. Geografía
   2. Modelo de dispositivo
8. Tu identificador único se configura automáticamente según la aplicación que hayas seleccionado: **IDFA** para iOS o **ID de anunciante** para Android. También puedes cambiarlo por **ID de usuario del cliente** en cualquiera de las dos plataformas.
9. Define la secuencia de eventos: añade al menos 2 eventos, en el orden en que un usuario real debería completarlos
10. Opcionalmente, establece un intervalo mínimo entre cada par de eventos. Si no lo estableces, se aplica de forma predeterminada un mínimo de 1 segundo
11. Revisa la sección **Resultado de la regla** para confirmar el estado de la ventana de evaluación y el tiempo total mínimo de la secuencia
12. Haz clic en **Save**

> 🚧 **Dos puntos (:)**
>
> No selecciones todos los eventos de tu aplicación. Selecciona solo los eventos en los que normalmente podría haber fraude

## Acceso a los datos

Cuando una regla de Serie de eventos bloquea una instalación o un evento in-app, los detalles se registran en tus reportes de raw data. Ve a **Raw Data > Protect360 & Validation Rules** para encontrar los eventos bloqueados y usa los campos siguientes para identificar cuáles ha bloqueado esta regla.

| Informe | Campos clave |
| --- | --- |
| Instalaciones posteriores a la atribución | <ul><li>Motivo del fraude = bots de validación</li><li>Submotivo del fraude = reglas de validación pa</li><li>Valor del motivo de bloqueo = nombre de la regla</li></ul> |
| Eventos in-app posteriores a la atribución | <ul><li>fraud\_reason = bots de validación</li><li>fraud\_sub\_reason = reglas de validación pa</li></ul> |
| Eventos in-app bloqueados | <ul><li>Motivo del bloqueo = bots de validación</li><li>Submotivo del bloqueo = reglas de validación pa</li><li>Valor del motivo de bloqueo = nombre de la regla</li></ul> |

## Ejemplos

A continuación, se muestran ejemplos de distintas series de eventos y si se considerarían fraudulentas o no.

<Accordion title="Ejemplo 1">

**Regla definida**

El usuario debe realizar los eventos en este orden:

* Evento A
* Evento B
* Evento C

**Realizado realmente**

El usuario realiza los eventos en este orden:

* Día 0: Se produjo la instalación
* Día 1: Se envió el evento A
* Día 2: Se envió el evento B
* Día 3: Se envió el evento C

**Resultado:**

No es fraude. El usuario realizó la serie de eventos en la secuencia definida.

</Accordion>

<Accordion title="Ejemplo 2">

**Regla definida**

El usuario debe realizar los eventos en este orden:

* Evento A
* Evento B
* Evento C

**Realizado realmente**

El usuario realiza los eventos en este orden:

* Día 0: se realizó la instalación
* Día 1: se envió el evento A
* Día 2: se envió el evento C
* Día 3: se envió el evento B

**Resultado:**

Fraude. El usuario realizó el evento C antes del evento B, lo que está fuera de la secuencia definida. Por ende:

* El evento A se bloqueará en la postatribución
* El evento B se bloqueará en tiempo real
* El evento C se bloqueará en tiempo real o en la postatribución, ya que este evento rompió la secuencia
* Todos los eventos siguientes se bloquearán en tiempo real

</Accordion>

<Accordion title="Ejemplo 3">

**Regla definida**  
 El usuario debe realizar los eventos en este orden:

* Evento A
* Evento B (tiempo mínimo respecto al evento anterior: 1 hora)
* Evento C (tiempo mínimo respecto al evento anterior: 2 horas)

**Realmente realizado**  
 El usuario realiza los eventos en este orden:

* Día 0: Se produjo la instalación
* Día 0: Se envió el evento A
* Día 0: Se envió el evento B 10 minutos después del evento A
* Día 0: Se envió el evento C 2 horas después del evento B

**Resultado:**  
 Fraude. El usuario realizó todos los eventos en el orden correcto, pero el intervalo entre el evento A y el evento B fue de solo 10 minutos, lo cual es inferior al mínimo configurado de 1 hora. Se incumplió la restricción de tiempo, independientemente de que el orden de la secuencia fuera el correcto. Por ende:

* El evento A se bloqueará en la postatribución
* El evento B se bloqueará en tiempo real porque incumplió la restricción de tiempo mínimo
* El evento C se bloqueará en tiempo real, ya que siguió a una secuencia incumplida
* Todos los eventos siguientes se bloquearán en tiempo real

</Accordion>

<Accordion title="Ejemplo 4">

**Regla definida**  
 El usuario debe realizar los eventos en este orden:

* Evento A
* Evento B
* Evento C

**Realmente realizado**  
 El usuario realiza los eventos en este orden:

* Día 0: Se produjo la instalación
* Día 1: Se envió el evento A
* Día 2: Se envió el evento B
* No se envió el evento C

**Resultado:**  
 No es fraude. El usuario completó los eventos A y B en el orden correcto, pero nunca activó el evento C. Las secuencias incompletas no se marcan como infracciones. No se bloquea ningún evento. La regla sigue evaluando eventos futuros dentro de la ventana de evaluación de 30 días.

</Accordion>

<Accordion title="Ejemplo 5">

**Regla definida**

El usuario se identificó mediante el <Anchor target="_blank" href="/marketers/es/docs/customer-user-id-field-cuid">Customer User ID (CUID)</Anchor>.

El usuario debe realizar los eventos en este orden:

* Evento A
* Evento B
* Evento C

**Realmente realizado**

El usuario realiza los eventos en este orden:

* Día 0: Se produjo la instalación
* Día 1: Se envió el evento A
* Día 1: Se produjo la desinstalación
* Día 1: Se produjo la instalación
* Día 2: Se envió el evento B
* Día 3: Se envió el evento C

**Resultado:**

No es fraude. Como el usuario se identificó mediante el <Anchor target="_blank" href="/marketers/es/docs/customer-user-id-field-cuid">Customer User ID (CUID)</Anchor> y los eventos se realizaron en orden.

</Accordion>

<Accordion title="Ejemplo 6">

**Regla definida**

El usuario debe realizar los eventos en este orden:

* Evento A
* Evento B
* Evento C

**Realizado realmente**

El Usuario fue identificado por el ID del anunciante

El usuario realiza los eventos en este orden:

* Día 0: Se produjo la instalación
* Día 1: Se envió el evento A
* Día 1: Se produjo la desinstalación
* Día 1: Se produjo la instalación
* Día 2: Se envió el evento B
* Día 3: Se envió el evento C

**Resultado:**

No es fraude. Dado que el Usuario fue identificado por el ID del anunciante y los eventos se realizaron en orden.

</Accordion>

<Accordion title="Ejemplo 7">

**Regla definida**  
 El usuario debe realizar los eventos en este orden:

* Evento A
* Evento B
* Evento C

Regla creada el 1 de enero.

**Realizado realmente:**

* 1 de enero (día 0): Se creó la regla. La ventana de evaluación comienza. Los eventos activados antes de esta fecha se ignoran.
* 15 de enero (día 14): se envió el evento A. La ventana se amplía y ahora evalúa los últimos 14 días.
* 30 de enero (día 29): se envió el evento B. La ventana se amplía y ahora evalúa los últimos 29 días.
* 31 de enero (día 30): la ventana alcanza los 30 días y se convierte en una ventana móvil de 30 días, que avanza un día cada día.
* 20 de febrero: se envió el evento C. La ventana móvil ahora retrocede 30 días, hasta el 21 de enero. El evento A (activado el 15 de enero) queda fuera de la ventana y ya no se evalúa.

**Resultado:**  
 No es fraude. A fecha de 20 de febrero, la ventana móvil retrocede hasta el 21 de enero, por lo que el evento A (15 de enero) queda fuera de la ventana de evaluación. Solo se evalúan los eventos B y C; ambos en el orden correcto, sin que se marque ninguna infracción.

</Accordion>

<Accordion title="Ejemplo 8">

**Regla definida**

El usuario debe realizar los eventos en este orden:

* Evento A
* Evento B
* Evento C

**Realmente realizado**

El usuario realiza los eventos en este orden:

* Día 0: se produjo la instalación
* Día 1: se envió el evento A
* Día 2: se envió el evento B
* Día 3: se envió el evento B
* Day4: se envió el evento C

**Resultado:**

Fraude. Dado que el mismo evento (evento B) se produjo dos veces, presumimos fraude, ya que no puedes tener el mismo evento dos veces en una secuencia.

</Accordion>

<Accordion title="Ejemplo 9">

**Regla definida**  
 El usuario se identificó mediante Customer User ID (CUID).  
 El usuario debe realizar los eventos en este orden:

* Evento A
* Evento B
* Evento C

**Realmente realizado**  
 El usuario activa eventos en dos dispositivos con el mismo CUID:

* Día 0: la instalación se produjo en el dispositivo 1
* Día 0: la instalación se produjo en el dispositivo 2
* Día 1: el evento A se envió desde el dispositivo 1
* Día 2: el evento B se envió desde el dispositivo 2
* Día 3: el evento C se envió desde el dispositivo 1

**Resultado:**  
 No es fraude. Dado que el usuario se identificó mediante CUID, la evaluación de la secuencia abarca todos los ID de AppsFlyer asociados al mismo CUID y al ID de la regla. Los eventos A, B y C se realizaron en el orden correcto, independientemente del dispositivo que los activó.

</Accordion>

<Accordion title="Características y limitaciones">

* Se pueden definir hasta 100 eventos en cada regla.
* Al llegar a 80 eventos, se muestra una advertencia. Al llegar a 100 eventos, se alcanza el límite y la regla debe dividirse para añadir más.
* El tiempo mínimo que se puede establecer entre eventos consecutivos es de 1 segundo. Si no se configura el tiempo para un par, el valor predeterminado de 1 segundo se aplica automáticamente.
* El intervalo de tiempo máximo Configurable entre eventos es de 30 días, en línea con la ventana de evaluación.
* La ventana de evaluación comienza el día 0 (fecha de creación de la regla) y crece cada día hasta alcanzar los 30 días; después, pasa a ser una ventana móvil de 30 días que avanza cada día. Los eventos activados antes de la fecha de creación de la regla nunca se evalúan.
* Cualquier edición de una regla restablece la ventana de evaluación al día 0.
* Se pueden configurar hasta 10 reglas activas por cuenta.
* Las reglas de las series de eventos solo se pueden usar para tráfico no orgánico.
* Solo se admite el tráfico del SDK. El tráfico S2S queda fuera del alcance de la fase 1.
* Las secuencias incompletas no se marcan como infracciones.
* El mismo evento no puede aparecer dos veces en una misma secuencia.
* Solo se admite la lógica AND entre condiciones. La lógica OR no es compatible.

</Accordion>

## Preguntas frecuentes

<Accordion title="¿Qué ocurre después de una reinstalación?">

Si la reinstalación restablece eventos que el usuario ya había completado, se considera una infracción. Si el usuario retoma el proceso desde donde lo dejó, no se marca ninguna infracción.

</Accordion>

<div data-zendesk-anchors="intro=introducci%C3%B3n h_01J2DZP5DWZ0V52PA0RGQ4PNHN=introducci%C3%B3n who-is-this-for=a-qui%C3%A9n-va-dirigido h_01J2E0CYHW4TBK6TQHMHYEVGEM=a-qui%C3%A9n-va-dirigido how-to-set-up-a-series-of-event-rule=c%C3%B3mo-configurar-una-regla-de-serie-de-eventos h_01J2E0MZYM7GZ2N6Z0NDRQQPTF=c%C3%B3mo-configurar-una-regla-de-serie-de-eventos h_01J2ED6016XRPDVJBJ0X388THJ=dos-puntos- accessing-data=acceso-a-los-datos h_01KWSHAXG3K8PQV334JHGC8A0G=acceso-a-los-datos examples=ejemplos h_01J2E0XXG85150ZBSSFVF98W83=ejemplos faq=preguntas-frecuentes h_01KWSHAXG4PFT77C0FWCXTF3AH=preguntas-frecuentes" />
