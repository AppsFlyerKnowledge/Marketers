---
title: Gestión de Dev Key
metadata:
  keywords:
    - Marketers
    - Platform essentials
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-negri
    - Marketers
    - Platform essentials
  created_at: '2025-07-14T11:20:11Z'
  edited_at: '2026-10-09T00:07:47Z'
  id: 37139123425809
  locale: es
  section: Account security
  section_id: 6551173202065
  url: https://support.appsflyer.com/hc/es/articles/37139123425809
---
> **De un vistazo:** Controla y actualiza la Dev Key de tu aplicación directamente en la Configuración de la aplicación. Para ofrecerte una mayor flexibilidad y seguridad.

## ¿Qué es una Dev Key?

La Developer Key (Dev Key) es un identificador único de tu aplicación que se utiliza para autenticar los datos de eventos enviados desde el SDK y las integraciones de servidor a servidor (S2S) a AppsFlyer. Es esencial para habilitar la atribución, las sesiones y la medición de eventos in-app.  
De forma predeterminada, todas las aplicaciones de tu cuenta comparten la misma Dev Key. Pero, si lo necesitas, puedes crear una Dev Key única para cada aplicación.  
Para darte un mayor control, la pestaña Gestión de Dev Keys de la configuración de tu aplicación permite a los usuarios administradores ver y gestionar las Dev Keys, incluida la actualización o sustitución de una Dev Key existente.

## Dónde encontrar tus Dev Keys

En AppsFlyer, desde el menú lateral, selecciona **Configuración** > **Configuración de la aplicación** > **Gestión de Dev Key**.

## Gestión de Dev Keys

Los administradores pueden usar la pestaña Gestión de Dev Key para:

* Generar una Dev Key única para una aplicación concreta.
* Asignar una Dev Key ya en uso por otra aplicación de la cuenta.
* Habilitar la generación predeterminada de Dev Keys únicas para las aplicaciones nuevas.

### Por qué podrías necesitar cambiar tu Dev Key

Puede que quieras cambiar tu Dev Key por varios motivos:

* **Seguridad**: rota la clave si ha quedado expuesta para evitar accesos no autorizados.
* **Transferencias de cuenta**: Genera una nueva clave de desarrollador después de mover una aplicación a otra cuenta, para alinearla con la cuenta actual.
* **Granularidad**: asigna claves únicas por aplicación para simplificar la supervisión, la resolución de problemas o el control de acceso.

### Cómo configurar y cambiar una Dev Key

Después de generar o asignar una nueva Dev Key, es importante que:

* Actualices el SDK: sustituye la Dev Key en el código SDK de tu aplicación.
* Lances una nueva versión: envía una nueva versión de la aplicación con la clave actualizada a la tienda de aplicaciones.
* Activa la clave (obligatorio): activar la clave de desarrollador es un **paso obligatorio** para que el cambio surta efecto.
* Después de que tu desarrollador actualice el SDK con la nueva clave de desarrollador y la nueva versión de la aplicación esté publicada en la tienda de aplicaciones, vuelve a la sección **Gestión de claves de desarrollador** y haz clic en **Activar clave de desarrollador**.
* Hasta que actives la clave de desarrollador:
  * La clave de desarrollador actual permanecerá activa
  * La nueva clave de desarrollador permanecerá en estado *Pendiente*
  * No se aplicará ningún cambio a la recopilación de datos

> 🚧 **Dos puntos (:)**
>
> Activa la clave de desarrollador solo cuando la versión actualizada de la aplicación esté publicada. Si la activas demasiado pronto, puede que los eventos in-app y las sesiones de versiones anteriores de la aplicación dejen de registrarse.

1. En AppsFlyer, en el menú lateral, selecciona Settings > App Settings > Autenticación del SDK.
2. Haz clic en Gestionar clave de desarrollador.
3. Revisa el impacto de cambiar tu clave de desarrollador antes de continuar.
4. Elige cómo configurar la nueva clave de desarrollador:
   1. **Selecciona una clave de desarrollador existente** - Elige una clave de desarrollador que ya exista en tu cuenta (por ejemplo, una clave de desarrollador usada por otra aplicación).
      1. La clave de desarrollador seleccionada se asignará a esta aplicación en estado *Pendiente*
      2. Tu clave de desarrollador actual seguirá activa hasta que actives la nueva
      3. **La activación es obligatoria** una vez que la versión actualizada de la aplicación esté publicada
   2. **Generar una nueva clave de desarrollador**: crea una clave de desarrollador totalmente nueva y única para esta aplicación.

      1. La nueva clave de desarrollador se creará en estado *Pendiente*
      2. Tu clave de desarrollador actual seguirá activa hasta la activación
      3. **La activación es obligatoria** una vez que la versión actualizada de la aplicación esté publicada

      > 🚧 **Dos puntos (:)**
      >
      > Independientemente de la opción que elijas, el cambio de clave de desarrollador solo surte efecto después de que actives manualmente la clave de desarrollador.

5. Haz clic en Next (Siguiente).
6. Copia y envía la clave de desarrollador a tu desarrollador para que pueda implementar los cambios en tu SDK y subir la nueva versión de tu aplicación a la tienda.
7. La clave de desarrollador pasará a un estado pendiente.
8. Haz clic en Activar clave de desarrollador.
9. La clave de desarrollador pasa de pendiente a activa.

> 📘 **Advertencia**
>
> * Hasta que los usuarios actualicen a la versión más reciente de la app, no se registrarán los eventos in-app ni las sesiones de versiones anteriores. Sin embargo, las instalaciones (atribución) se seguirán procesando correctamente.
> * Si usas la API S2S (API2), los cambios en la Dev Key pueden interrumpir los eventos de servidor a servidor.
> * Una vez activada la Dev Key, los datos pueden tardar hasta 30 minutos en empezar a fluir al sistema.

### Cómo establecer una clave Dev única para futuras apps (próximamente - T2 de 2026)

1. En AppsFlyer, en la barra lateral superior derecha, haz clic en **Account settings.**
2. Haz clic en la pestaña **Account**.
3. En **Security**, activa Create unique Dev key per app (para futuras referencias).
4. Nota: Al habilitar Dev Keys únicas para futuras aplicaciones, las aplicaciones existentes no se ven afectadas.

<div data-zendesk-anchors="what-is-a-dev-key=qu%C3%A9-es-una-dev-key h_01K04ARS7NRB6H9JVPAZNXE36H=qu%C3%A9-es-una-dev-key where-to-find-your-dev-keys=d%C3%B3nde-encontrar-tus-dev-keys h_01K0BS18HAZ2QK2ADHEZAH5QNF=d%C3%B3nde-encontrar-tus-dev-keys dev-key-management=gesti%C3%B3n-de-dev-keys h_01K04ASZEQHRAE4AVS88NMTTC4=gesti%C3%B3n-de-dev-keys why-you-might-need-to-change-your-dev-key=por-qu%C3%A9-podr%C3%ADas-necesitar-cambiar-tu-dev-key h_01K09HM57MXQY4R3MCVB4KCV1G=por-qu%C3%A9-podr%C3%ADas-necesitar-cambiar-tu-dev-key how-to-set-up-and-change-a-dev-key=c%C3%B3mo-configurar-y-cambiar-una-dev-key h_01K04AXYR6J4ETE8GF6K7B8NSY=c%C3%B3mo-configurar-y-cambiar-una-dev-key h_01KGY7X3KFAZM49FG8WE5R8VHB=dos-puntos- h_01KGY84Z53QW9QVNX4DJ2SR1QC=dos-puntos--1 h_01KGY12P0CJZR6FV9WEE6MNW0A=advertencia how-to-set-a-unique-dev-key-for-future-apps=c%C3%B3mo-establecer-una-clave-dev-%C3%BAnica-para-futuras-apps-pr%C3%B3ximamente---t2-de-2026 h_01K04AY1SF0FMHS4QJJDK6VZAK=c%C3%B3mo-establecer-una-clave-dev-%C3%BAnica-para-futuras-apps-pr%C3%B3ximamente---t2-de-2026" />
