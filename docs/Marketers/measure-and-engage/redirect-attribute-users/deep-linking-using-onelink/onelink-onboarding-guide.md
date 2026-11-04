---
title: 'Integración con OneLink: Guía para principiantes'
metadata:
  keywords:
    - Marketers
    - set up
    - Smart Banners and Scripts
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-asaf-mashiah
    - Marketers
    - Smart Banners and Scripts
  created_at: '2024-08-21T11:48:39Z'
  edited_at: '2026-08-12T12:24:12Z'
  id: 27699299657617
  locale: es
  section: Deep linking using OneLink
  section_id: 6551203111057
  url: https://support.appsflyer.com/hc/es/articles/27699299657617
---
> **De un vistazo**: Utiliza OneLink para redirección personalizada y efectiva de usuarios, enlaces profundos y atribución desde tus campañas, sin importar el dispositivo, sistema operativo, canal o plataforma del usuario, para maximizar la conversión y los ingresos.

## ![53010_Onelink.jpg](https://files.readme.io/c0d24ab87126bf765a89a25077b07d8678159cdb6f1b68eddc14a4cd2759b12a-30192941047185.jpg)

<div id="about-onelink" />

## Sobre OneLink

AppsFlyer <Anchor target="_blank" href="/marketers/es/docs/onelink-guide">OneLink</Anchor> te permite crear enlaces para tus campañas con capacidades de atribución, redirección y enlaces profundos que convierten a usuarios de medios propios en usuarios de aplicaciones y mantienen a los usuarios existentes comprometidos con experiencias contextuales fluidas, sin importar el dispositivo, sistema operativo, canal o plataforma. Usa OneLink para crear recorridos de usuario personalizados y contextuales que lleven a los usuarios a tu aplicación, logrando las tasas de conversión e ingresos más altas posibles. Las experiencias personalizadas que puedes crear incluyen:

* **De redes sociales a aplicación**: Interactúa con tus usuarios en redes sociales y envíalos desde los feeds de redes sociales a tu aplicación.
* **De aplicación a aplicación**: Lleva a los usuarios a tu aplicación desde otras aplicaciones.
* <Anchor target="_blank" href="/marketers/es/docs/convert-your-mobile-web-visitors-to-app-users">**De la web a la aplicación**</Anchor>: Convierte a los visitantes de tu sitio web móvil en nuevos usuarios de la aplicación móvil utilizando Smart Banners y Smart Script. **Incluye funciones pagadas**
* **De QR a aplicación**: Utiliza códigos QR para impulsar las instalaciones de aplicaciones haciendo que los usuarios escanéen un código QR en puntos clave durante su experiencia de cliente fuera de línea. También puedes colocar códigos QR en tu sitio de escritorio o en anuncios de TV y CTV para dirigir a los usuarios a tu aplicación.
* **De correo electrónico a aplicación**: Utiliza proveedores de servicios de correo electrónico (ESP) para interactuar con los usuarios mediante correo electrónico y envíalos desde su bandeja de entrada a tu aplicación. **Incluye funciones pagadas**
* **De texto a aplicación**: Crea enlaces para tus campañas de SMS y mensajería e interactúa con los usuarios a través de mensajes de texto.
* **De referencia a aplicación**: Crea enlaces de invitación que permiten a usuarios e influencers invitar a otros a tu aplicación o compartir contenido específico dentro de la aplicación, como un artículo. **Incluye funciones pagadas**
* **Personalizado**: Crea una experiencia personalizada con una amplia variedad de opciones para lograr la máxima personalización. No importa de dónde provengan tus usuarios, ya sea a través de ordenadores de escritorio o dispositivos móviles, en línea o fuera de línea, medios propios o pagados, utiliza OneLink para dirigirlos fácilmente al lugar adecuado.

**De texto a aplicación**: Crea enlaces para tus campañas de SMS y mensajería e interactúa con los usuarios a través de mensajes de texto. 

<div id="onelink-onboarding" />

## Incorporación a OneLink

**Para empezar a usar OneLink, siga los pasos a continuación:**

<span id="h_01J5WC8Z4J352AHSDTRCEP2W9H"></span>**Requisitos previos**

* Una <Anchor target="_blank" href="https://www.appsflyer.com/sign-up/">cuenta</Anchor> de AppsFlyer con al menos una de sus aplicaciones añadidas.
* La mayoría de las funciones requieren un <Anchor target="_blank" href="/marketers/es/docs/account-management-plans-payments-and-billing#appsflyer-plans">plan de suscripción</Anchor> de pago de AppsFlyer. Si necesitas ayuda, contacta con [hello@appsflyer.com](mailto:hello@appslfyer.com)
* Para configurar OneLink, debe ser un usuario administrador de AppsFlyer o contar con <Anchor target="_blank" href="/marketers/es/docs/user-management">permisos</Anchor> para añadir/editar plantillas de OneLink.
* <Anchor target="_blank" href="/marketers/es/docs/integrate-the-appsflyer-sdk">SDK de AppsFlyer</Anchor> debe estar instalado en sus aplicaciones móviles para la atribución de instalaciones, eventos dentro de la aplicación y enlaces profundos.
  * Si el SDK aún no está instalado en sus aplicaciones, todavía es posible crear un enlace de redirección funcional, pero sin atribución.

| Tarea | Propósito | Acciones necesarias | ¿Quién participa? |
| --- | --- | --- | --- |
| 1. Crear una plantilla OneLink | Una plantilla OneLink es la base requerida de la lógica de redirección para todos los enlaces creados a partir de ella. | <ul><li>Responsable de marketing/gerente de producto: Configurar una <Anchor target="_blank" href="/marketers/es/docs/create-a-onelink-template">plantilla OneLink</Anchor> en AppsFlyer.</li><li>Desarrollador de Android: Configurar métodos de apertura de aplicaciones para usuarios existentes (enlaces de aplicaciones de Android y esquema URI).</li><li>Desarrollador de iOS: Configurar métodos de apertura de aplicaciones para usuarios existentes (enlaces universales de iOS y esquema URI).</li></ul><Anchor target="_blank" href="/marketers/es/docs/create-a-onelink-template#add-redirection-logic-for-existing-app-users">Instrucciones para desarrolladores</Anchor> | Responsable de marketing y desarrollador |
| 2. Crear un enlace OneLink | Cree un enlace OneLink a partir de su nueva plantilla para utilizar en su campaña. | <ul><li>Responsable de marketing/gerente de producto: Configurar un enlace <Anchor target="_blank" href="/marketers/es/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#crear-un-enlace-de-onelink">OneLink</Anchor> en AppsFlyer, incluyendo la selección de la experiencia del cliente y la adición de parámetros de atribución y enlaces profundos.</li><li><Anchor target="_blank" href="/marketers/es/docs/convert-your-mobile-web-visitors-to-app-users">**De la web a la aplicación**</Anchor>: Convierte a los visitantes de tu sitio web móvil en nuevos usuarios de la aplicación móvil utilizando Smart Banners y Smart Script.</li></ul> | Responsable de marketing y desarrollador |
| 3. Configurar la lista de permitidos de redireccionamiento de dominio | Por seguridad, los enlaces que cree en AppsFlyer solo redirigirán a los usuarios a URLs web cuyos dominios estén en su lista de permitidos. | Actualice la <Anchor target="_blank" href="/marketers/es/docs/set-up-your-domain-redirect-allowlist">lista de permitidos de redireccionamiento de dominios</Anchor> con todos los dominios a los que desea redirigir a los usuarios. | Comercializador |
| 4. Probar su nuevo enlace | Verifique que su enlace redirige con éxito:<ul><li>Nuevos usuarios sin su aplicación instalada</li><li>Usuarios existentes con su aplicación instalada</li></ul> | Puede <Anchor target="_blank" href="/marketers/es/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#testing">probar</Anchor> el enlace recién creado. | Comercializador |
| 5. Utilice el enlace con confianza en su campaña y luego mida los resultados |  | <ol><li>Añada el nuevo enlace a su campaña y preséntelo a su audiencia.</li><li>Vea los resultados de su campaña en el panel general de AppsFlyer (filtre por su campaña).</li></ol>¡Felicitaciones! ¡Felicidades! Ha completado la incorporación a OneLink. | Responsable de marketing, analista de datos |
| **Características opcionales** |  | Ahora que todo está configurado, puede explorar y descubrir funciones adicionales de OneLink, como:<ul><li>De la web a la aplicación: Convierta a los usuarios web en usuarios de aplicaciones y mida los flujos de conversión de web a aplicación.</li><li><Anchor target="_blank" href="/marketers/es/docs/use-onelink-api-to-create-links-in-large-scale-campaigns">API de OneLink</Anchor> y <Anchor target="_blank" href="/marketers/es/docs/perform-onelink-bulk-actions-via-csv">creación masiva de enlaces</Anchor>: Escale y ejecute múltiples campañas simultáneamente y cree miles de enlaces OneLink de forma rápida y sencilla.<br />*La API de OneLink requiere una suscripción Enterprise.</li><li><Anchor target="_blank" href="/marketers/es/docs/export-onelink-urls">Exportar URLs de OneLink</Anchor>: Descargue las URLs de OneLink que ha creado en AppsFlyer.</li><li><Anchor target="_blank" href="/marketers/es/docs/user-invite-attribution">Atribución de invitación de usuario</Anchor> - Crea engagement integrando enlaces de invitación de usuario creados directamente desde la app.</li><li><Anchor target="_blank" href="/marketers/es/docs/cross-promotion-attribution-for-marketers">Atribución de promoción cruzada</Anchor>: Los usuarios existentes de su aplicación son excelentes candidatos para instalar sus nuevas aplicaciones. Aprenda a utilizar los métodos SDK para crear y evaluar campañas de promoción cruzada.</li><li><Anchor target="_blank" href="/marketers/es/docs/understand-onelink-short-vs-long-urls">URLs extensas</Anchor>: Añada parámetros a sus enlaces personalizados de OneLink o genere numerosos enlaces personalizados de OneLink aplicando sus propias fórmulas simples en una hoja de cálculo.</li></ul>**Nota:** La mayoría de las funciones requieren un <Anchor target="_blank" href="/marketers/es/docs/account-management-plans-payments-and-billing#appsflyer-plans">plan de suscripción</Anchor> de pago de AppsFlyer. | Responsable de marketing y desarrollador |

Si necesita ayuda para iniciar con OneLink, póngase en contacto con su representante de ventas o escriba a [hello@appsflyer.com](mailto:hello@appsflyer.com)

<div id="traits-and-limitations" />

## Especificaciones y limitaciones

| El | Nota |
| --- | --- |
| Atribución de medios propios en Safari para iPad | Cuando los usuarios hacen clic en enlaces de medios propios en un iPad con el navegador Safari, es posible que el navegador reporte un **user agent similar al de Macintosh** en lugar del modelo de dispositivo de un iPad. Como resultado, AppsFlyer identifica el clic como procedente de un dispositivo Mac, mientras que la instalación de la app se identifica como procedente de un iPad. Dado que la atribución probabilística se basa en hacer coincidir las características del dispositivo entre el clic y la instalación, esta discrepancia impide la atribución y puede provocar instalaciones no atribuidas o fallos de Deferred deep linking. Esta limitación solo se aplica al tráfico de medios propios en dispositivos iPad que usan Safari. |

<div data-zendesk-anchors="overview=sobre-onelink h_01J2G7RMHSPPXCWJ60W9HZASXX=sobre-onelink h_01HKHGX9JJQQCKF9SDZRSCM1XJ=sobre-onelink xyz-onboarding=incorporaci%C3%B3n-a-onelink h_01J2RJFH0B4R815CWDQNEB2C1P=incorporaci%C3%B3n-a-onelink traits-and-limitations=especificaciones-y-limitaciones h_01KFAG3N0X0W0RCJXK00KX038E=especificaciones-y-limitaciones" />
