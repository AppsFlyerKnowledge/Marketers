---
title: Soporte para la política de consentimiento de Google
metadata:
  keywords:
    - Agencies
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
    - Agencies
  created_at: '2024-02-07T07:28:17Z'
  edited_at: '2026-08-22T00:32:54Z'
  id: 22310731147153
  locale: es
  section: Preserve user privacy
  section_id: 6551440878097
  url: https://support.appsflyer.com/hc/es/articles/22310731147153
---
> **En resumen:** AppsFlyer ayuda a los marketers a cumplir la Ley de Mercados Digitales (DMA) y a mejorar el valor de sus anuncios en Google. Encuentra respuestas a las preguntas más frecuentes sobre el cumplimiento de la DMA y la optimización del valor de los anuncios.

<div id="overview" />

## Visión general

Google está actualizando su <Anchor target="_blank" href="https://www.google.com/about/company/user-consent-policy/?sjid=15416941068016224808-NA">política de consentimiento de usuarios de la UE</Anchor> en preparación para la aplicación de la <Anchor target="_blank" href="https://commission.europa.eu/strategy-and-policy/priorities-2019-2024/europe-fit-digital-age/digital-markets-act-ensuring-fair-and-open-digital-markets_en">Ley de Mercados Digitales</Anchor> (DMA). Como <Anchor target="_blank" href="https://ads.google.com/lp/appcampaigns/attribution/">App Attribution Partner</Anchor> de Google, AppsFlyer se está adaptando a los cambios de política al tiempo que permite a los anunciantes sacar el máximo partido de sus anuncios en Google. La política actualizada está en vigor desde el 6 de marzo de 2024.

<div id="relevant-integrations-and-continued-use-of-google-features" />

## Integraciones relevantes y uso continuo de las funciones de Google

<div id="which-integrations-are-involved" />

<Accordion title="¿De qué integraciones se trata?">

Las siguientes integraciones son relevantes para la nueva política de consentimiento de la UE de Google:

* Google Ads (`googleadwords_int`)
* GMP DV360 (`dv360_int`)

Si los usuarios finales de tus aplicaciones a través de estas integraciones se encuentran en el Espacio Económico Europeo (EEE), asegúrate de tomar las medidas necesarias para cumplir con la nueva política de consentimiento de la UE de Google.

<div id="note" />

> 📘 **Nota:**
>
> La integración [antigua] de Google Marketing Platform DV360/CM (`doubleclick_int`) quedará obsoleta y no será compatible con la nueva política de consentimiento de la UE de Google. Si estás utilizando esta integración, te recomendamos que <Anchor target="_blank" href="/marketers/es/docs/bulletin-google-marketing-platform-gmp-integration-transition">cambies a la nueva integración DV360 (dv360\_int)</Anchor>.

</Accordion>

<div id="what-must-i-do-to-continue-using-googles-features" />

<Accordion title="¿Qué se debe hacer para seguir utilizando las funciones de Google?">

Los marketers deben obtener el consentimiento de los usuarios finales en el EEE para seguir utilizando las funciones de Google Ads y GMP DV360 relacionadas con la medición, la personalización de anuncios y el remarketing.

</Accordion>

<div id="updating-the-appsflyer-sdk" />

## Actualización del SDK de AppsFlyer

<div id="what-steps-do-i-need-to-take-to-update-the-appsflyer-sdk" />

<Accordion title="Pasos necesarios para implementar datos de consentimiento a través del SDK de AppsFlyer">

El SDK de AppsFlyer (v6.13.0+) puede enviar los datos de consentimiento necesarios con cada evento para cumplir los requisitos de Google.

* <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/sdk-installation">Actualiza tu SDK</Anchor> a la última versión (Android - v6.13.0+, iOS - v6.13.1+). Aplicable a aplicaciones Android o iOS.
* Una vez actualizado el SDK, <Anchor target="_blank" href="/marketers/es/docs/additional-sdk-integration-guide#send-consent-for-dma-compliance">consulta aquí</Anchor> las instrucciones de implementación para admitir la DMA.

</Accordion>

<div id="sending-consent-data" />

## Enviando datos de consentimiento

<div id="how-do-i-send-consent-data-to-appsflyer" />

<Accordion title="Enviar los datos de consentimiento a AppsFlyer">

Los marketers tienen dos opciones para enviar los datos de consentimiento requeridos a AppsFlyer:

* [**Directamente a través del SDK**](#actualización-del-sdk-de-appsflyer) **o de una API S2S (servidor a servidor):** los marketers pueden enviar los datos de consentimiento directamente a AppsFlyer mediante el SDK. Aplicable a aplicaciones Android o iOS.
* **A través de cadenas TCF:** los marketers que actualmente utilizan o tienen previsto utilizar una plataforma de gestión del consentimiento (CMP) pueden enviar los campos de datos mediante las cadenas estándar del IAB (Interactive Advertising Bureau) Transparency and Consent Framework (TCF) (TCF V2.2/2.3). Asegúrate de incluir el ID de proveedor de Google (755) en la lista de proveedores autorizados.

A continuación, AppsFlyer permite a los clientes transmitir las señales de consentimiento a Google. Sin embargo, es importante señalar que AppsFlyer no recoge, altera ni controla el consentimiento del usuario final. Los marketers que trabajan con Google son responsables de recoger los campos de consentimiento necesarios.

Mira <Anchor target="_blank" href="https://appsflyer.wistia.com/medias/0tnlyre8ai">este video</Anchor> sobre cómo enviar datos de consentimiento a AppsFlyer.

</Accordion>

<div id="which-consent-values-does-appsflyer-send-to-google" />

<Accordion title="Valores de consentimiento que AppsFlyer envía a Google">

Los valores de consentimiento del usuario final se envían a Google para las integraciones relevantes de AppsFlyer (`googleadwords_int`y `dv360_int`) utilizando los siguientes campos:

| Campo AppsFlyer | Campo Google (1) | Valores | Explicación |
| --- | --- | --- | --- |
| <span id="gdpr_applies"></span>gdpr\_applies | eea | true/false (2) | ¿Se aplica la DMA a este usuario? |
| <span id="ad_personalization"></span>personalización de anuncios habilitada | personalización de anuncios | verdadero/falso | ¿El usuario ha dado su consentimiento a Google para usar sus datos con fines de personalización de anuncios? |
| <span id="ad_user_data"></span>datos de usuario de anuncios habilitados | datos\_de\_usuario\_de\_anuncios | verdadero/falso | ¿El usuario dio su consentimiento para enviar sus datos a Google? |

1. Consulta la <Anchor target="_blank" href="https://support.google.com/tagmanager/answer/13802165?hl=en">definición de Google para cada campo</Anchor>.
2. Cuando DMA no se aplica al usuario, AppsFlyer sugiere abstenerse de enviar campos de consentimiento que no sean `gdpr_applies=false`

</Accordion>

<div id="sending-consent-datafaq" />

### Enviando datos de consentimiento—FAQ

<div id="do-i-have-control-over-consent-data-for-nonue-users" />

<Accordion title="¿Existe alguna opción para no enviar datos de consentimiento a Google?">

AppsFlyer permite a los anunciantes que creen que los requisitos de la DMA no se aplican a sus usuarios finales (por ejemplo, cuando no pertenecen a la UE) evitar el envío de datos de consentimiento a Google. Esto se hará activando un interruptor en las páginas de integración relevantes.

<div id="important" />

> 🚧 **Importante:**
>
> Antes de utilizar esta opción, es recomendable que obtengan la aprobación de sus equipos jurídicos y de privacidad para asegurarse de que se ajusta a sus políticas. Consulta el <Anchor target="_blank" href="https://support.google.com/tagmanager/answer/13802165?hl=en">artículo sobre el modo de consentimiento</Anchor> de Google para obtener definiciones de referencia.

**No compartir los datos de consentimiento con Google:**

1. En AppsFlyer, desde el menú lateral, selecciona **Colaboración** > **Integración activa**.
2. Busca al partner y haz clic en **Gestionar integración**.
3. Desde la pestaña de configuración de integración, activa **Usuarios no pertenecientes a la UE**

<Image align="center" alt="Alternador de usuarios no pertenecientes a la UE en la pestaña de configuración de integración" src="https://files.readme.io/fb141c0bd8885facd6574f3e73c5ec8ae8beb596de7fdf3dd8aed9d4e82686dd-22352319155985.png" width="595px" />

</Accordion>

<div id="is-consent-needed-for-mobile-web-events" />

<Accordion title="¿Se necesita consentimiento para eventos de web móvil?">

En esta etapa, solo se comparten eventos de aplicaciones móviles con Google, por lo que no es necesario compartir con AppsFlyer el consentimiento para eventos web. Si los usuarios pasan de la web a tu aplicación, su consentimiento se seguirá recopilando dentro de la aplicación en una etapa posterior.

</Accordion>

<div id="which-countries-does-googles-eu-consent-policy-cover" />

<Accordion title="¿A qué países se aplica el consentimiento de DMA de Google?">

La Ley de Mercados Digitales (DMA) se aplica a los usuarios dentro de la UE y el EEE (Espacio Económico Europeo), y afecta a <Anchor target="_blank" href="https://www.gov.uk/eu-eea">estas regiones</Anchor>. Aunque **el Reino Unido y Suiza** no son parte de la UE, Google ha extendido unilateralmente su política de consentimiento para incluir también a esos países.

</Accordion>

<div id="whats-the-recommended-way-to-ask-for-user-consent-in-a-compliant-way" />

<Accordion title="¿Cuál es la forma recomendada de solicitar el consentimiento del usuario de manera conforme?">

AppsFlyer recomienda consultar con tu equipo legal para obtener el consentimiento de manera conforme a la DMA. Si bien <Anchor target="_blank" href="https://support.google.com/google-ads/answer/14009343?hl=en&sjid=3762335249108620505-NC#app-consent">Google proporciona instrucciones generales</Anchor>, no ofrece un lenguaje específico para los mensajes.

</Accordion>

<div id="how-is-appsflyer-translating-tcf-strings-to-google-dma-consent-flags" />

<Accordion title="¿Cómo está AppsFlyer traduciendo las cadenas TCF a las banderas de consentimiento del DMA de Google?">

Después de que AppsFlyer recibe las cadenas TCF de tu CMP (ya sea a través del SDK de AppsFlyer o S2S), se procesan y traducen en los servidores de AppsFlyer. La siguiente traducción se mapea y se envía a Google, como recomienda Google:

| Cadenas recopiladas por AppsFlyer | Banderas de consentimiento de Google | Descripción |
| --- | --- | --- |
| `gdpr_applies=1/0` | `eea=1/0` | Identifica si la DMA es aplicable o no para el usuario respectivo |
| `datos_de_usuario_de_anuncios` | `ad_user_data=1` | Cuando se da consentimiento a Google para el propósito 1, y se da consentimiento/interés legítimo a Google para el propósito 7 |
| `datos_de_usuario_de_anuncios` | `ad_user_data=0` | Cuando no se da consentimiento a Google para el propósito 1 **o** no se da consentimiento/interés legítimo a Google para el propósito 7 |
| `personalización de anuncios` | `ad_personalization=1` `ad_personalization=0` | Cuando se da consentimiento a Google para los propósitos 3 y 4 Cuando no se da consentimiento a Google para los propósitos 3 y 4 |

</Accordion>

<div id="if-consent-data-is-sent-via-the-firebase-sdk-do-i-still-need-to-update-the-appsflyer-sdk" />

<Accordion title="¿Necesito actualizar tanto los SDKs de AppsFlyer como de Firebase para enviar datos de consentimiento?">

Sí. Google requiere que los datos de consentimiento se incluyan en cada evento enviado desde AppsFlyer, ya que Google no fusiona los datos de consentimiento del usuario de Firebase con los datos enviados desde AppsFlyer. Por lo tanto, los datos de consentimiento deben enviarse a AppsFlyer, que los reenvía a Google. De manera similar, compartir datos de consentimiento solo con AppsFlyer no es suficiente para los requisitos del SDK de Firebase. Esto significa que debes enviar los datos tanto a AppsFlyer como a Firebase.

</Accordion>

<div id="preparing-for-the-upcoming-changes" />

## Preparándose para los próximos cambios

<div id="how-can-i-prepare-for-the-upcoming-changes" />

<Accordion title="Adopta las siguientes medidas preparatorias">

<div id="address-user-consent-in-the-european-economic-area-eea" />

#### Abordar el consentimiento del usuario en el Espacio Económico Europeo (EEE)

Colabora con el asesor jurídico de tu empresa. Pueden proporcionar insights sobre las implicaciones de las políticas europeas de consentimiento del usuario en los datos que compartes con partners como Google. Si es relevante, implementa indicaciones de privacidad como "Configuración de la Privacidad" o "Opciones de Privacidad" para recoger señales de consentimiento de usuario relacionadas con marketing y publicidad de los usuarios de tu aplicación.

<div id="verify-cmp-compliance-and-tcf-2223-support" />

#### Verifica el cumplimiento de la CMP y el soporte de TCF 2.2/2.3

Asegúrate de que tu plataforma de gestión del consentimiento (CMP) sea compatible con TCF 2.2/2.3, las versiones más recientes del Transparency and Consent Framework (TCF). Tu CMP también debe estar bien informada sobre los nuevos requisitos de consentimiento de Google en la UE y puede asesorarte sobre cómo darles soporte conforme al TCF.

<div id="implement-the-newest-sdkserver-to-server-s2s-apis" />

#### Implementa las nuevas APIs SDK/Server-to-server (S2S)

Considera las siguientes opciones para enviar los nuevos campos de consentimiento, ya sea utilizando el SDK o las llamadas a la API S2S:

* **Utilizando el SDK:**
  * Implementar la última versión del SDK de AppsFlyer (Android - v6.13.0+, iOS - v6.13.1+) para aplicaciones de iOS y Android
  * Elige cómo <Anchor target="_blank" href="/marketers/es/docs/additional-sdk-integration-guide#send-consent-for-dma-compliance">enviar los datos de consentimiento</Anchor>
* <strong>Utilizando las</strong> llamadas a la API <Anchor target="_blank" href="/marketers/es/docs/server-to-server-events-api-for-mobile-s2s-mobile?"><strong>S2S</strong></Anchor>:
  * Antes de enviar eventos in-app a AppsFlyer, actualiza tus llamadas a la API para incluir el objeto `consent_data` para cada evento. Descubre <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/s2s-events-api3-post">cómo hacerlo</Anchor>.

<div id="transition-from-the-legacy-gmp-integration-doubleclick" />

#### Transición desde la antigua integración GMP (DoubleClick)

Si todavía utilizas la antigua integración GMP de AppsFlyer (doubleclick\_int), pasa a la versión más reciente (dv360\_int), que ya está disponible. La integración antigua **no es compatible con el consentimiento de la UE** y quedará obsoleta pronto. Saber más <Anchor target="_blank" href="/marketers/es/docs/bulletin-google-marketing-platform-gmp-integration-transition">aquí</Anchor>.

</Accordion>

<div id="impact-on-advertising-activityfaq" />

## Impacto en la actividad publicitaria—Preguntas frecuentes

<div id="how-will-the-upcoming-change-impact-my-remarketing-campaigns" />

<Accordion title="¿Cómo afectará el próximo cambio a la atribución de mi campaña?">

En algunos casos, Google Ads y DV360 no reclamarán la atribución de los usuarios de la UE que opten por no permitir que Google use sus datos con fines publicitarios (`ad_user_data=0`). Esto significa que AppsFlyer no podrá atribuirlos.

Google y AppsFlyer aún pueden realizar la atribución en algunos casos cuando `ad_user_data=0`, según la interpretación de Google de la Ley de Mercados Digitales (DMA).

</Accordion>

<div id="how-will-the-upcoming-change-affect-my-audiences" />

<Accordion title="¿Cómo afectará el próximo cambio a Audiences?">

El cambio puede afectar al número de usuarios del EEE que aparecen en tus audiencias y están expuestos a campañas de remarketing en Google. Los usuarios del EEE y del Reino Unido deberán dar su consentimiento antes de compartir su información con Google. Aquellos que no den su consentimiento serán excluidos de las audiencias por parte de Google y no estarán expuestos a tus campañas. Esto plantea la cuestión de cómo obtener el consentimiento de tus usuarios y cuáles pueden ser las ramificaciones para tu negocio y tus esfuerzos publicitarios. <Anchor target="_blank" href="/marketers/es/docs/audiences-user-identifier-policy#eu-digital-markets-act">Saber más sobre los cambios en Audiences</Anchor>.

</Accordion>

<div id="further-information-and-contact-details" />

## Saber más y detalles de contacto

Si tienes alguna duda o pregunta, puedes ponerte en contacto con nosotros:

* Para conocer los requisitos de Google o cómo pueden afectar estas actualizaciones a tus datos de Google, consulta los <Anchor target="_blank" href="https://www.google.com/about/company/user-consent-policy-help/">artículos de ayuda de Google</Anchor> o ponte en contacto directamente con tu representante de Google.
* Si tienes preguntas sobre el soporte de AppsFlyer para los campos de consentimiento del usuario final de la UE, ponte en contacto con tu CSM de AppsFlyer o escribe a [hello@appsflyer.com](mailto:hello@appsflyer.com).
* Consulta el <Anchor target="_blank" href="https://support.google.com/tagmanager/answer/13802165?hl=en">artículo sobre el modo de consentimiento</Anchor> de Google para obtener definiciones de referencia.

<div id="see-also" />

> 📄 **Consulte también**
>
> * <Anchor target="_blank" href="/marketers/es/docs/additional-sdk-integration-guide">Guía adicional de integración del SDK</Anchor>
> * <Anchor target="_blank" href="/marketers/es/docs/bulletin-google-marketing-platform-gmp-integration-transition">Transición a la nueva integración de DV360</Anchor>
> * <Anchor target="_blank" href="/marketers/es/docs/audiences-user-identifier-policy">Política de identificador de usuario de Audiencias</Anchor>

<div data-zendesk-anchors="overview=visi%C3%B3n-general h_01HP195KV35FD6X67WTMXJWWSZ=visi%C3%B3n-general relevant-integrations-and-continued-use-of-google-features=integraciones-relevantes-y-uso-continuo-de-las-funciones-de-google h_01HP1M37V1CYW5T5E4K1ES3NQA=integraciones-relevantes-y-uso-continuo-de-las-funciones-de-google 01HP1KN2H7NTS2V1S2PGF0C41N=which-integrations-are-involved h_01HP2HRPJR72Z0R5VEG5N36CN2=nota h_01HP1K1088SJK60QRSTQF4WF6S=what-must-i-do-to-continue-using-googles-features updating-the-appsflyer-sdk=actualizaci%C3%B3n-del-sdk-de-appsflyer h_01HP1Z2G2M56DDQS9T47GMCFHJ=actualizaci%C3%B3n-del-sdk-de-appsflyer h_01HP1ZASRQGABCEFV67P961XAV=what-steps-do-i-need-to-take-to-update-the-appsflyer-sdk how-consent-data-is-sent=enviando-datos-de-consentimiento h_01HP1KPSMCH3EG373BWVQZM4ZT=enviando-datos-de-consentimiento h_01HP1JJ2AYHYJET9GYMXA93E86=how-do-i-send-consent-data-to-appsflyer h_01HP1JJ2AYWRBREW5GD0KPDF1R=which-consent-values-does-appsflyer-send-to-google sending-consent-data%E2%80%94faq=enviando-datos-de-consentimientofaq h_01HR1X08VZ5MEAV01E9X54KAQS=enviando-datos-de-consentimientofaq h_01HP1JJ2AYZ57G0GMR8QRDTEZ7=do-i-have-control-over-consent-data-for-nonue-users h_01HP2MRPFA2ECJGAZ93NQHVD2J=importante 01HVE9TVZWTRW3VQ8TSXWA13QM=is-consent-needed-for-mobile-web-events h_01JVYS49FCZT3Z91KNACNR6GET=which-countries-does-googles-eu-consent-policy-cover h_01HRXZYZJBDTP8CHJDHQ187CTN=whats-the-recommended-way-to-ask-for-user-consent-in-a-compliant-way 01HR6SD3PBWN5X9AHT66ZADQ3R=how-is-appsflyer-translating-tcf-strings-to-google-dma-consent-flags 01J2V4XRKRSEPA6KPJFMSTHE1F=if-consent-data-is-sent-via-the-firebase-sdk-do-i-still-need-to-update-the-appsflyer-sdk what-i-can-do-on-my-side=prepar%C3%A1ndose-para-los-pr%C3%B3ximos-cambios 01HR1XYXRDVEW6H9Q3WP17E2N3=prepar%C3%A1ndose-para-los-pr%C3%B3ximos-cambios h_01HP1JJ2AYFHRRDYZS8YFYE6WP=how-can-i-prepare-for-the-upcoming-changes address-user-consent-in-the-european-economic-area-eea-and-in-the-uk=abordar-el-consentimiento-del-usuario-en-el-espacio-econ%C3%B3mico-europeo-eee h_01HPGNBQCTJFVZR99BY6E5J2JF=abordar-el-consentimiento-del-usuario-en-el-espacio-econ%C3%B3mico-europeo-eee verify-cmp-compliance-and-tcf-22-support=verifica-el-cumplimiento-de-la-cmp-y-el-soporte-de-tcf-2223 h_01HPGNC0HAMA7Z0B4DNV2QSFYG=verifica-el-cumplimiento-de-la-cmp-y-el-soporte-de-tcf-2223 implement-the-newest-sdkservertoserver-s2s-apis=implementa-las-nuevas-apis-sdkserver-to-server-s2s h_01HPGNCAG3M9XPHDTP03WHQQ9F=implementa-las-nuevas-apis-sdkserver-to-server-s2s transition-from-the-legacy-gmp-integration-doubleclick=transici%C3%B3n-desde-la-antigua-integraci%C3%B3n-gmp-doubleclick h_01HPGNCHP6SSFCVZ3P4AG0N1FB=transici%C3%B3n-desde-la-antigua-integraci%C3%B3n-gmp-doubleclick impact-on-my-advertising-activity=impacto-en-la-actividad-publicitariapreguntas-frecuentes h_01HP1PKNZN32TQYHGJNNM3JFVZ=impacto-en-la-actividad-publicitariapreguntas-frecuentes h_01HP1PKNZN0VJGYAPFHR5JVV5H=how-will-the-upcoming-change-impact-my-remarketing-campaigns h_01HP4K2ZJW11BFSKNPRH7FA092=how-will-the-upcoming-change-affect-my-audiences further-information-and-contact-details=saber-m%C3%A1s-y-detalles-de-contacto h_01HQ2VJES04CYF4J8YBB4GQS73=saber-m%C3%A1s-y-detalles-de-contacto h_01KZZYSDB33GZ47RSDRP9ACAH0=consulte-tambi%C3%A9n" />
