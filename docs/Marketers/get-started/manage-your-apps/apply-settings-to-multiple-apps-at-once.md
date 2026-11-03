---
title: Aplica la configuración a varias aplicaciones a la vez
deprecated: false
hidden: false
metadata:
  keywords:
    - App Settings
    - Advertisers
    - Agencies
    - Developers
    - Marketers
    - Platform essentials
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - Marketers
    - Platform essentials
    - Agencies
    - pm-guy-riesenberg
  created_at: '2026-09-09T09:10:13Z'
  edited_at: '2026-09-28T00:19:24Z'
  id: 50696362899089
  locale: es
  section: Manage your apps
  section_id: 6551015977105
  url: https://support.appsflyer.com/hc/es/articles/50696362899089
---
> **At a glance:** Aplica el mismo cambio de configuración a varias aplicaciones a la vez, en lugar de repetirlo para cada aplicación por separado.

## Acerca de la configuración masiva de aplicaciones

Ahora puedes aplicar los mismos cambios de configuración a varias aplicaciones a la vez usando la configuración masiva de aplicaciones en la página Configuración de la aplicación. Así puedes hacer un cambio una sola vez y aplicarlo a otras aplicaciones aptas en una sola operación.

Para acceder a Configuración de la aplicación, en el menú lateral, selecciona **Configuración** > **Configuración de la aplicación**. O bien, en **Mis aplicaciones**, selecciona una aplicación y abre su Configuración de la aplicación.

## Aplicar una configuración a varias aplicaciones

> 📘 **Nota:**
>
> Una aplicación puede incluirse en un cambio masivo si la configuración se aplica a la plataforma de esa aplicación, si todavía no tiene el valor que estás aplicando, si ya se cumple cualquier requisito previo necesario y si tienes acceso de gestión a su configuración de la aplicación. Consulta **Características y limitaciones** más abajo para ver los criterios completos de cada configuración.

**Para aplicar un cambio de configuración a varias aplicaciones:**

1. Abre la configuración de la aplicación de la aplicación cuyo ajuste quieres cambiar y cambia un ajuste (un interruptor, un menú desplegable o un control deslizante).

   <Image alt="Screenshot 2026-09-16 at 14.31.44.png" src="https://files.readme.io/8a1abce58e1e8da4af5899e2e03a2a7fe9e6e9b8e9a04c240585bfd3e7934126-50944987863825.png" width="2557px" />
2. Junto al campo modificado, haz clic en **Aplicar a aplicaciones adicionales**.

   <Image alt="aap.png" src="https://files.readme.io/0f2144ca43c6db7ffe9967df5c2b2f2fe3e8cffdbefa77167ed9262a61511774-50945027652113.png" width="612px" />
3. Busca por nombre de la aplicación o ID de la aplicación y selecciona las aplicaciones a las que quieras aplicar el mismo cambio. Las aplicaciones que no cumplan los requisitos para este cambio seguirán visibles, pero aparecerán atenuadas. Pasa el cursor por encima de una para ver el motivo.

   <Image alt="Screenshot 2026-09-16 at 14.32.32.png" src="https://files.readme.io/95c79ce8c176e4a0836661a119ca12b1268b8874181d4fd78c96113e5339d6c9-50945018039953.png" width="1304px" />
4. Haz clic fuera de la lista para cerrarla y confirmar tu selección. El botón **Aplicar a aplicaciones adicionales** se sustituye por una insignia que muestra el número de aplicaciones seleccionadas; haz clic en ella cuando quieras para cambiar tu selección.

   <Image alt="ssa.png" src="https://files.readme.io/b93174999053cdbbf5591eb215e6cd10becbd2d1bcb699ff286a8b1523f8a8f0-50944987865361.png" width="1238px" />
5. Repite estos pasos para tantas configuraciones como sea necesario.
6. Al final de la página, haz clic en **Guardar cambios** (si no has seleccionado ninguna aplicación adicional) o en **Revisar & Guardar** (una vez que hayas incluido aplicaciones en un cambio masivo). Ambos botones muestran el número total de cambios entre paréntesis.

   <Image alt="Screenshot 2026-09-16 at 14.33.32.png" src="https://files.readme.io/6dfb050b984932023455af9022364b37534af276d7bb117ddb05ad0fc25d936c-50945018041489.png" width="2269px" />
7. Si has incluido aplicaciones adicionales, revisa los valores anteriores y posteriores de cada aplicación en la pantalla **Revisar antes de guardar**. El valor actual de cada aplicación se usa como valor de referencia. Puedes quitar cualquier cambio del lote antes de confirmar.

   <Image alt="Screenshot 2026-09-16 at 14.33.38.png" src="https://files.readme.io/c22f67575fc8ac9cbd868c923b5addfe8c70529ee1183fa7231f080d1b54d18c-50945018042385.png" width="1286px" />
8. Haz clic en **Confirmar & Guardar**. Esto guarda la aplicación desde la que empezaste junto con todas las aplicaciones adicionales del lote, en una sola operación.

> 📘 **Nota:**
>
> En Aggregated Advanced Privacy, siempre verás un paso de confirmación antes de que el cambio se aplique. En la atribución de re-engagement, verás este paso de confirmación solo cuando apliques el cambio de forma masiva.

> 🚧 **Importante**
>
> Todas las aplicaciones del lote se actualizan a la vez. El resultado será uno de estos:
>
> 1. Se actualizan correctamente todas las aplicaciones.
> 2. Se produce un error y no se actualiza ninguna aplicación.
>    1. Si se produce un error al guardar, puedes volver a intentarlo.

## Características y limitaciones

| Rasgo | Description |
| --- | --- |
| <span id="supported-settings-ships-first"></span>Configuraciones compatibles (ya disponibles) | <ul><li>Privacidad Avanzada Agregada (solo iOS)</li><li>Atribución de re-engagement (iOS, Android)</li><li>Tiempo mínimo entre conversiones de re-engagement (iOS, Android)</li><li>Atribución SEO (iOS y Android para activar; cualquier plataforma para desactivar)</li><li>Ocultar direcciones IP (todas las plataformas excepto Web)</li><li>Evento de usuario fiel (iOS, Android)</li><li>Tiempo mínimo entre sesiones (iOS, Android)</li></ul> |
| <span id="supported-settings-coming-soon"></span>Configuraciones compatibles (Próximamente) | Estas configuraciones todavía no admiten cambios masivos. En breve:<ul><li>Ventana de reatribución (móvil, en días; sitio web, en segundos — no se combinan en una sola acción)</li><li>Modelado probabilístico (todas las plataformas; requiere que fingerprinting ya esté activado)</li><li>Zona horaria (todas las plataformas)</li><li>Moneda (todas las plataformas)</li><li>Medición de desinstalaciones (iOS requiere que ya se haya subido un certificado P12; Android requiere que Firebase ya esté configurado)</li><li>Detección de reinstalaciones (iOS, Android)</li></ul> |
| <span id="not-supported"></span>No es compatible | Autenticación del SDK (clave de desarrollador), país de la tienda de aplicaciones, cambio del nombre de la aplicación, carga del certificado de desinstalación de iOS, ID del proyecto de Firebase y configuración de puestos de agencia y partner. |
| <span id="why-an-app-might-be-grayed-out"></span>Por qué una aplicación puede aparecer atenuada | Una aplicación atenuada no cumple los requisitos para este cambio en este intento concreto. Se mostrará uno de los siguientes motivos:<ul><li>**Incompatibilidad de plataforma:** la configuración no existe en la plataforma de esa aplicación.</li><li>**Ya configurado:** la aplicación ya tiene el valor que estás aplicando.</li><li>**Falta un requisito previo:** por ejemplo, el modelado probabilístico requiere que fingerprinting ya esté activado.</li><li>**Periodo de espera:** la zona horaria no se puede volver a cambiar en los dos días posteriores a un cambio anterior. La descripción emergente muestra la fecha en la que vuelve a estar disponible.</li><li>**Sin permisos:** no tienes acceso de gestión a la configuración de la app.</li></ul> |
| <span id="limits"></span>Límites | No hay ningún límite práctico en el número de aplicaciones que puedes incluir en un cambio masivo. |

> 📄 **Consulte también**
>
> * <Anchor target="_blank" href="/marketers/es/docs/app-settings">Configuración del app</Anchor>

<div data-zendesk-anchors="about-bulk-app-settings=acerca-de-la-configuraci%C3%B3n-masiva-de-aplicaciones h_01N1A2B3C4D5E6F7G8H9J0K1L2=acerca-de-la-configuraci%C3%B3n-masiva-de-aplicaciones apply-a-setting-to-multiple-apps=aplicar-una-configuraci%C3%B3n-a-varias-aplicaciones h_02N1A2B3C4D5E6F7G8H9J0K1L2=aplicar-una-configuraci%C3%B3n-a-varias-aplicaciones h_01M25MDHN4Q2TDAZHPGSXQFQKR=nota h_01M22PVGBQT0V9BSE1Y37V0KB8=nota-1 h_01M22PVGBQQAFHMR7XDYB2BMXN=importante traits-and-limitations=caracter%C3%ADsticas-y-limitaciones h_03N1A2B3C4D5E6F7G8H9J0K1L2=caracter%C3%ADsticas-y-limitaciones h_01M22PVGBQ8BZN09TZ2S4A70SW=consulte-tambi%C3%A9n" />
