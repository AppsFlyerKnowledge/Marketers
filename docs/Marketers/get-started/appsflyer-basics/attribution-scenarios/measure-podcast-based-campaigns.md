---
title: Medir campañas basadas en podcasts
metadata:
  keywords:
    - Advertisers
    - Agencies
    - audio
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-moran-davida
    - Marketers
    - Mobile Attribution
    - Agencies
  created_at: '2019-12-22T15:49:12Z'
  edited_at: '2026-08-12T11:57:34Z'
  id: 360004494318
  locale: es
  section: Attribution scenarios
  section_id: 6551328497041
  url: https://support.appsflyer.com/hc/es/articles/360004494318
---
> **En resumen:** Supera el reto de la atribución de la publicidad de aplicaciones móviles en podcasts utilizando una de las soluciones de AppsFlyer.

<div id="podcast-attribution-methods" />

## Métodos de atribución de podcasts

Los podcasts son una fuente de tráfico de usuarios móviles relativamente poco explotada. Los usuarios de podcasts pueden reaccionar favorablemente a los anuncios de aplicaciones móviles, pero la atribución supone un reto. Esto se debe a que los podcasts no tienen una interfaz visual que genere impresiones o clics de los usuarios.

Sin embargo, hay opciones que permiten superar estas limitaciones para realizar correctamente la atribución de podcasts:

* Página de aterrizaje específica
* Activación de un clic de OneLink desde una aplicación de podcast específica

<div id="dedicated-landing-page" />

### Página de aterrizaje específica

Una llamada a la acción (CTA) en un podcast, cuando anuncia una aplicación móvil, suele consistir en mencionar el nombre de una aplicación para que los usuarios puedan buscarla.

* En un escenario con una página de aterrizaje específica, la CTA es un destino web concreto dentro de una página de aterrizaje.
* Esta página incluye un elemento web (botón, banner, etc.) impulsado por OneLink. Para crear fácilmente banners dinámicos para páginas de aterrizaje sin necesidad de programar, recomendamos usar <Anchor target="_blank" href="/marketers/es/docs/smart-banners-mobile-web-to-app-for-marketers">Smart Banners</Anchor>.
* Los usuarios que interactúan con este elemento e instalan la aplicación móvil se atribuyen según los parámetros de OneLink.

<div id="example" />

> 📄 **Ejemplo**
>
> Decides promocionar tu aplicación en el podcast de Joe Rogan y utilizar una página de aterrizaje específica.
>
> Joe fuma, habla de tu aplicación y luego termina con «ve a www.greatapp.com/joe y consigue un 25% de descuento».
>
> La página de aterrizaje tiene un banner de **Descargar app** con una URL de OneLink. La URL incluye la fuente de medios «podcast» (&pid=podcast) y el nombre de la campaña «joe» (&c=joe).
>
> Los usuarios que hacen clic en la URL de OneLink e instalan la aplicación se atribuyen, en la plataforma de AppsFlyer, a la fuente de medios «podcast» y a la campaña «joe».

<div id="firing-onelink-click-from-a-podcast-app" />

### Activación de un clic de OneLink desde una aplicación de podcast

Este método supera la falta de interfaz visual y permite la atribución de usuarios sin visitar una página de aterrizaje específica.

* En un escenario de activación de un clic de OneLink, la aplicación de podcast activa un clic en una URL de OneLink (o una impresión) cuando un usuario está expuesto al anuncio.
* Normalmente esto ocurre al final de un anuncio, pero se puede programar de otra forma.
* Los usuarios que instalan una aplicación después de escuchar un anuncio de podcast se atribuyen según los parámetros de OneLink.

<div id="example-1" />

> 📄 **Ejemplo**
>
> Decides promocionar tu aplicación en el pódcast «Making history», que permite activar OneLink directamente después de que los usuarios escuchen el anuncio.
>
> La URL de OneLink contiene el ID de dispositivo, la fuente de medios «podcast» (&pid=podcast) y el nombre de la campaña «making history» (&c=making%20history).
>
> El anuncio menciona varias veces el nombre de tu aplicación, pero sin una URL específica. Sin embargo, en AppsFlyer, los usuarios que instalan la aplicación se atribuyen a la fuente de medios «podcast» y a la campaña «making history».

<div id="who-gets-the-attribution" />

#### ¿Quién obtiene la atribución?

En AppsFlyer, la fuente de medios «podcast» se considera una fuente de medios personalizada, y no un partner integrado. Sin embargo, al integrarse con AppsFlyer, los propietarios de aplicaciones de pódcast pueden recibir postbacks de las instalaciones que se les atribuyan. Los propietarios de aplicaciones de pódcast pueden <Anchor target="_blank" href="https://www.appsflyer.com/get-started/partners">ponerse en contacto</Anchor> con el grupo de desarrollo de partners de AppsFlyer.

<div data-zendesk-anchors="podcast-attribution-methods=m%C3%A9todos-de-atribuci%C3%B3n-de-podcasts 01JB9NB6DY4ZTS1VAK9S0QSM2R=m%C3%A9todos-de-atribuci%C3%B3n-de-podcasts dedicated-landing-page=p%C3%A1gina-de-aterrizaje-espec%C3%ADfica 01JB9NB6E5BHETTEY7Q0WD8JXE=p%C3%A1gina-de-aterrizaje-espec%C3%ADfica 01JB9NB6E9DZXTJTGDPT6HA3FS=ejemplo firing-onelink-click-from-a-podcast-app=activaci%C3%B3n-de-un-clic-de-onelink-desde-una-aplicaci%C3%B3n-de-podcast 01JB9NB6EANCCA0FG7ZQY48VSB=activaci%C3%B3n-de-un-clic-de-onelink-desde-una-aplicaci%C3%B3n-de-podcast 01JB9NB6EDW22XGAM2HCA3CY9Q=ejemplo-1 who-gets-the-attribution=qui%C3%A9n-obtiene-la-atribuci%C3%B3n 01JB9NB6EDFJ3YNP1JYKDGPHEX=qui%C3%A9n-obtiene-la-atribuci%C3%B3n" />
