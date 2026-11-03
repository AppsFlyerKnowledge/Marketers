---
title: Utiliza la página de prueba del SDK web
metadata:
  keywords:
    - SDK Test
    - Web Attribution
    - Web Attribution SDK
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  created_at: '2026-08-23T16:04:12Z'
  edited_at: '2026-08-26T00:40:33Z'
  id: 50118956978577
  locale: es
  section: AppsFlyer Web Attribution
  section_id: 43560690387729
  url: https://support.appsflyer.com/hc/es/articles/50118956978577
---
> **At a glance:** Utiliza la página de prueba del SDK web para validar la instalación del SDK web y el registro de eventos en tiempo real. Ejecútala cuando integres el SDK por primera vez y cada vez que añadas o cambies un evento.

## Vista general

La página de prueba del SDK web abre tu sitio web en una nueva pestaña del navegador con una sesión de prueba específica. Toda la actividad del SDK web en esa pestaña, incluidas las cargas de página, los eventos y las llamadas de identidad, se transmite en directo a la página de prueba, donde puedes inspeccionar cada evento y sus propiedades. Esto te permite verificar tu implementación en cuestión de minutos, sin esperar a que los datos aparezcan en los reportes.

Úsala para comprobar que:

* El SDK web se carga en las páginas previstas.
* Tus eventos se activan con el nombre, los ingresos y las propiedades correctos.
* El ID de usuario del cliente (CUID) se establece después del login o del registro.

Ejecuta una prueba cada vez que integres el SDK por primera vez o cambies la configuración de eventos.

## Prerrequisitos

Antes de ejecutar una prueba, asegúrate de que tienes:

* Una aplicación web en AppsFlyer. Para obtener más información, consulta <Anchor target="_blank" href="/marketers/es/docs/adding-an-app-to-appsflyer#web">Crear una aplicación web en AppsFlyer</Anchor> en Onboard Web Performance Measurement.
* El SDK web de AppsFlyer está implementado en las páginas que quieres probar. Para obtener más información, consulta la sección <Anchor target="_blank" href="/marketers/es/docs/integrate-appsflyer-web-sdk">Integrar el SDK web de AppsFlyer</Anchor>.

## Ejecutar una prueba

Una vez que se cumplan los requisitos previos, ejecuta una prueba de la siguiente manera:

1. En AppsFlyer, en el menú lateral, ve a **Configuración** > **Pruebas de integración de SDK**.
2. Selecciona **Prueba del SDK web**.
3. En el cuadro de diálogo **Prueba tu SDK web**:
   * Selecciona tu aplicación web.
   * El campo **URL** se rellena automáticamente con la URL del sitio web configurada para la aplicación. La prueba se ejecuta en esta URL de forma predeterminada. Cámbiala para probar una página específica.
4. Haz clic en **Iniciar prueba**. Tu sitio web se abre en una nueva pestaña del navegador con una sesión de prueba dedicada. No tienes que hacer nada allí.
5. Vuelve a la página de prueba de Web SDK. Los eventos de la pestaña de prueba aparecen automáticamente en la tabla **Live events** mientras navegas e interactúas con tu sitio web.

> 📘 **Note**
>
> La prueba solo captura la actividad de la pestaña del navegador que abre. Si visitas tu sitio web directamente sin iniciar una prueba, no se mostrarán eventos en esta página.

## Ver la tabla de eventos en directo

Cada fila de la tabla **Live events** muestra la marca de tiempo del evento, el tipo, el nombre y el estado de validación.

| Tipo de evento | Qué significa |
| --- | --- |
| `pageLoad` | El Web SDK se cargó y registró una visita en una página. |
| `setCustomerUserId` | El SDK establece el ID de usuario del cliente (CUID). |
| `EVENT` | AppsFlyer registró un evento que definiste. La columna **Event name** muestra el nombre del evento; por ejemplo, purchase. |

La tabla **Live events** también admite lo siguiente:

* **Event details:** Haz clic en una fila para abrir el panel Event details y ver todas las propiedades que incluye el evento; por ejemplo, ingresos y valores del evento.
* **Search:** Usa el cuadro de búsqueda para encontrar un evento específico.
* **Export:** Haz clic en **Export CSV** para descargar los resultados.

## Reiniciar o borrar una prueba

Usa una de estas opciones para reiniciar o borrar una prueba:

* **Restart test:** Borra la lista de eventos y abre una nueva pestaña del navegador con una nueva sesión de prueba. Puedes usar esto para iniciar una ejecución limpia.
* **Restart with new app / URL:** Vuelve a abrir el cuadro de configuración para probar una aplicación web o una página diferente.
* **Clear logs:** Borra solo la lista de eventos. La sesión de prueba actual y la pestaña del navegador permanecen activas, por lo que los nuevos eventos siguen transmitiéndose.

## Escenarios de prueba habituales

Puedes ejecutar una prueba después de cada cambio en la configuración de tu Web SDK o en tus eventos. Es la forma más rápida de detectar problemas antes de que afecten a tus datos. Algunos escenarios habituales son:

* **Primera integración de Web SDK:** Navega por las páginas en las que has instalado el SDK y verifica que aparece un evento `pageLoad` en cada una.
* **Añadir o cambiar un evento:** Activa el evento en tu sitio web; por ejemplo, completa una compra. Después, verifica que aparece una fila de EVENT con el nombre del evento, los ingresos y las propiedades correctas en los detalles del evento.
* **Implementar el ID de usuario del cliente:** Regístrate o inicia sesión en tu sitio web y verifica que aparece un evento `setCustomerUserId`. Configurar el CUID mejora la precisión de la atribución y unifica los recorridos de usuario entre plataformas.

<div data-zendesk-anchors="h_01WSDKTP0000000000OVRVW=vista-general overview=vista-general h_01WSDKTP0000000000PREQ1=prerrequisitos prerequisites=prerrequisitos h_01WSDKTP0000000000RUNT1=ejecutar-una-prueba run-a-test=ejecutar-una-prueba h_01WSDKTP0000000000REVW1=ver-la-tabla-de-eventos-en-directo view-the-live-events-table=ver-la-tabla-de-eventos-en-directo h_01WSDKTP0000000000RSTR1=reiniciar-o-borrar-una-prueba restart-or-clear-a-test=reiniciar-o-borrar-una-prueba h_01WSDKTP0000000000WHEN1=escenarios-de-prueba-habituales common-testing-scenarios=escenarios-de-prueba-habituales" />
