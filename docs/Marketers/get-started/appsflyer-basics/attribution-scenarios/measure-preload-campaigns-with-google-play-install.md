---
title: Mide las campañas de precarga con Google Play Install
metadata:
  keywords:
    - Advertisers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-alina-koifman
    - Marketers
    - Mobile Attribution
  created_at: '2021-07-25T11:31:06Z'
  edited_at: '2026-08-12T11:57:37Z'
  id: 4404557237649
  locale: es
  section: Attribution scenarios
  section_id: 6551328497041
  url: https://support.appsflyer.com/hc/es/articles/4404557237649
---
> **De un vistazo:** AppsFlyer usa la instalación automática (PAI) de Google Play para atribuir las instalaciones a las campañas de precarga, en las que los marketers contratan a los operadores de telefonía móvil y a los partners de detección de aplicaciones para que precarguen su aplicación en el momento en que el usuario enciende el dispositivo por primera vez. **Nota**: Este método de atribución difiere de la atribución <Anchor target="_blank" href="/marketers/es/docs/appsflyer-factory-preinstall-using-manifest-android">previa a la instalación de APK</Anchor>.

<div id="pai-preload-attribution" />

## Atribución de precarga de PAI

En las campañas de precarga, los fabricantes de dispositivos originales (OEM), los operadores de telefonía móvil y los partners de detección de aplicaciones precargan las aplicaciones en los dispositivos que se descargan al activarse por primera vez.

Las campañas de precarga permiten a los anunciantes llegar a una audiencia potencialmente grande sin ejecutar campañas en línea.

La instalación automática (PAI) de Google Play (1 de los 3 métodos de atribución de precarga) ofrece a los marketers un mecanismo preciso y que preserva la privacidad para medir el rendimiento de las campañas de precarga. Este método proporciona a los marketers resultados de atribución deterministas, garantizando al mismo tiempo que se mantenga la privacidad del usuario, ya que la atribución se realiza a través de la coincidencia del referente con un referente generado independientemente del dispositivo y los identificadores de usuario.

AppsFlyer da la mayor prioridad a la atribución de precarga. Esto significa que si un usuario participa en otras campañas antes de abrir la aplicación por primera vez, la campaña de precarga recibe la atribución. Otros engagements se consideran instalaciones asistidas.

<div id="note" />

> 📘 **Nota:**
>
> La configuración de prioridad de atribución igual para precarga no se aplica a Google PAI.

<div id="flow" />

### Flujo

1. Un dispositivo nuevo se activa por primera vez y las aplicaciones predefinidas se instalan automáticamente en él desde Google Play de acuerdo con las reglas establecidas por el partner de precarga.
2. El usuario lanza una aplicación precargada por primera vez.
3. El SDK de AppsFlyer consulta la API de referencia de Google Play.
4. Los atributos de AppsFlyer se basan en los datos recuperados.

<Image align="center" alt="PAI-attribution-flow_en-us.png" src="https://files.readme.io/c7f02a0a6637e9c73e9a39f97e71d5d37d8d2712b458735cd87b4b245ad0fccb-small-4404791877649.png" />

<div id="data-availability" />

### Disponibilidad de datos

Los datos de rendimiento de precarga de la instalación automática de Google Play (PAI) están disponibles en:

* El panel de resumen general y los reportes agregados a nivel de partner de precarga (fuente de medios) y de campaña.
* Reportes de raw data

Los raw data incluyen los siguientes campos:

* media\_source = ID de partner
* Match\_type = preload\_pai
* Campaign\_name = precargar la campaña por `<preloadpartner ID>`

<div id="set-up-google-play-auto-install-pai-preload-attribution" />

### Configurar la atribución de precarga por instalación automática (PAI) de Google Play

**Para configurar la atribución de precarga de PAI:**

1. En AppsFlyer, en el menú lateral, selecciona **Colaborar** > **Integraciones activas**.
2. Selecciona el partner de precarga.
3. Activa la **Atribución de precarga**.
4. **Establece la duración de la ventana retrospectiva de precarga**.

   <div id="note-1" />

   > 📘 **Nota:**
   >
   > Google almacena los datos del referente durante un máximo de 90 días. Configura la ventana de lookback de PAI en 90 días o menos. Aunque la interfaz de usuario permite hasta 180 días, Google no ofrece datos de más de 90 días.

5. Haz clic en **Guardar integración**.
6. Informa al partner de precarga de que estás listo para atribuir sus campañas.

<div id="partners-supporting-google-play-auto-install-pai-preload-campaigns" />

### Partners que apoyan las campañas de precarga de instalación automática (PAI) de Google Play

<table><thead><tr><th rowspan="2">Fuente de medios</th><th rowspan="2">PID no integrados.</th></tr></thead><tbody><tr><td><p>Xiaomi</p></td><td><span>xiaomipai_int</span></td></tr><tr><td><p>Transsion</p></td><td><span>shalltrypai_int</span></td></tr><tr><td><p>Oppo</p></td><td><span>oppopaipreinstall_int</span></td></tr><tr><td><p>Vivo</p></td><td><span>vivootapreload_int</span></td></tr><tr><td><p>TCL</p></td><td><span>tclpai_int</span></td></tr><tr><td><p>Motorola</p></td><td><span>motorola_int</span></td></tr><tr><td><p>MITV</p></td><td><span>mitvpai_int</span></td></tr><tr><td><p>ZTE</p></td><td><span>ztepai_int</span></td></tr><tr><td><p>Lenovotab</p></td><td><span>lenovotabpai4p_int</span></td></tr><tr><td><p>Preinstalación de KDDI</p></td><td><span>kddipai_int</span></td></tr></tbody></table>

<div id="note-2" />

> 📘 **Nota:**
>
> Las agencias no pueden habilitar campañas de precarga para sus clientes.

<div id="postbacks-for-preload-partners" />

## Postbacks para partners de precarga

Como parte de su integración con AppsFlyer, los partners de precarga definen el contenido y los puntos finales de los postbacks que AppsFlyer les envía.

Cuando se incluyen en un postback, las macros contienen datos relevantes para el usuario. Las macros admitidas se enumeran en la siguiente tabla:

* **Fuente**: indica de dónde provienen los datos:
  * **SDK**: el SDK de AppsFlyer incorporado en la aplicación o la API de servidor a servidor
  * **AppsFlyer**: tras el procesamiento por parte de AppsFlyer.

| Macro postbacks para partners de precarga (nombre del parámetro) | Fuente | Descripción |
| --- | --- | --- |
| nombre\_aplicación | SDK | Nombre de la aplicación configurado por el anunciante |
| código\_de\_país | AppsFlyer | Código de país con ISO 3166 (alfa-2) Ejemplo: US, CN |
| hora\_de\_instalación | SDK | Marca de tiempo de instalación |
| Indicador de atribución AF | SDK | Idioma (configuración regional) reportado por el dispositivo y establecido por el sistema operativo del dispositivo. |
| id\_aplicación | SDK | Identificador único de aplicación en Appsflyer. |
| version\_app | SDK | Versión de la aplicación establecida por el desarrollador de la aplicación en el código de la aplicación |
| tipo\_de\_dispositivo | SDK | Nombre del modelo comercial del dispositivo. Ejemplo: SM-GM284 o iPhone7 |
| versión\_sistema\_operativo | SDK | Versión del sistema operativo del dispositivo |

<div id="postback-example" />

#### Ejemplo de postback

```http
http://YourCompanyDomain.com?pid=(preinstall_partner)&app_name=(app-name)&app_id=(app-id)&install_time=(install-unix-ts)
```

<div data-zendesk-anchors="pai-preload-attribution=atribuci%C3%B3n-de-precarga-de-pai h_01HEJG4FHSGJDZ77Y281F7SG4R=atribuci%C3%B3n-de-precarga-de-pai h_01K8XBQ3YKJ8KBMPMAAMBZP25E=nota pai-preload-attribution-flow=flujo h_01HEJG4FHSF8X1TEMMNJBYP71Z=flujo campaign-performance-data-availability=disponibilidad-de-datos h_01HEJG4FHSCMPJM5TRNSPNDHVN=disponibilidad-de-datos run-preload-referrer-campaigns=configurar-la-atribuci%C3%B3n-de-precarga-por-instalaci%C3%B3n-autom%C3%A1tica-pai-de-google-play h_01HEJG4FHS7E5JZT2BBYG2BNEK=configurar-la-atribuci%C3%B3n-de-precarga-por-instalaci%C3%B3n-autom%C3%A1tica-pai-de-google-play h_01K8XBJ9EJ38ST3KAFF879ZQ1H=nota-1 partners-supporting-preload-referrer-campaigns=partners-que-apoyan-las-campa%C3%B1as-de-precarga-de-instalaci%C3%B3n-autom%C3%A1tica-pai-de-google-play h_01HEJG4FHSNEGR7R9VCSDT9TSZ=partners-que-apoyan-las-campa%C3%B1as-de-precarga-de-instalaci%C3%B3n-autom%C3%A1tica-pai-de-google-play h_01K8XBVZJGG59K3XJ8R346X9FH=nota-2 postbacks-for-preload-partners=postbacks-para-partners-de-precarga h_01HEJG4FHSKD7DY6W7W65YBMGN=postbacks-para-partners-de-precarga preload-postback-example=ejemplo-de-postback h_01HEJG4FHSBFB456Z752HFC8KN=ejemplo-de-postback" />
