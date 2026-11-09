---
title: Realiza un experimento de Incrementalidad
metadata:
  keywords:
    - Advertisers
    - Premium
    - Marketers
    - Incrementality
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-niv-klein
    - Marketers
    - Incrementality
  created_at: '2020-10-12T19:26:09Z'
  edited_at: '2026-08-12T12:26:26Z'
  id: 360014225577
  locale: es
  section: Incrementality for remarketing
  section_id: 6551378485649
  url: https://support.appsflyer.com/hc/es/articles/360014225577
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **Resumen:** Lleva a cabo un experimento de Incrementalidad para entender el verdadero impacto de tus campañas de remarketing.

<Image align="center" alt="KB_toggle_final.jpg" src="https://files.readme.io/4de8c3ff1edaaae77fc0571de6125b25c884bcc4e4ac67471fc90610298866e1-30780522054801.jpg" />

<div id="about-the-experiment" />

## Sobre el experimento

Las pruebas de <Anchor target="_blank" href="/marketers/es/docs/incrementality-for-remarketing-overview">Incrementalidad</Anchor> evalúan el impacto real de tus campañas mediante pruebas A/B, que miden con precisión el “impulso incremental”, es decir, la diferencia entre las conversiones que resultan de tus campañas de remarketing y las que habrían ocurrido de todas formas.

Los resultados son fundamentales para entender el valor real generado por tus inversiones en marketing. Con las pruebas de Incrementalidad, puedes ver de manera objetiva el impacto de canales y campañas específicas, lo que te permite tomar mejores decisiones sobre la asignación de presupuesto y la optimización de campañas.

AppsFlyer hace que las pruebas de Incrementalidad sean sencillas gracias a un proceso automatizado que comienza al crear la audiencia. La audiencia nueva se divide automáticamente entre los socios de medios conectados y un grupo de control mediante el interruptor habilitado “Medir el impacto incremental”. El grupo de control es la porción de la audiencia que se mantiene al margen de los socios y es esencial para las pruebas. Una vez que guardas la audiencia, se crea automáticamente un experimento de Incrementalidad. Después de lanzar tus campañas con los socios y asegurarte de que las campañas correctas estén enlazadas, podrás ver los resultados del experimento en el panel de Incrementalidad.

<div id="get-started" />

## Comienza

La incrementalidad es una función premium. Después de suscribirte, sigue estos pasos para empezar. Para obtener más información sobre cada paso, consulta [Configurar el experimento](/docs/run-an-incrementality-for-remarketing-experiment#configura-el-experimento) a continuación.

|  | Pasos |
| --- | --- |
| 1 | [**Conoce tus objetivos de prueba**](/docs/run-an-incrementality-for-remarketing-experiment#know-your-test-objectives)<br /><br />Maximiza la utilidad de los resultados de tu experimento definiendo objetivos de prueba claros y una hipótesis para el resultado. |
| 2 | [**Crea la audiencia objetivo y divide los grupos**](/docs/run-an-incrementality-for-remarketing-experiment#create-the-target-audience-and-split-groups)<br /><br />En <Anchor target="_blank" href="/marketers/es/docs/audiences-guide">Audiencias</Anchor>:<ul><li>Configura la audiencia.</li><li>Conéctala a redes publicitarias.</li><li>La audiencia se divide automáticamente en grupos de prueba y de control mediante un interruptor habilitado (para suscriptores de Incrementality, en audiencias creadas después del 11 de enero de 2023).AppsFlyer Audiences sube a los miembros del grupo de prueba a las redes publicitarias y reserva a los miembros del grupo de control.</li></ul> |
| 3 | [**Lanza la campaña y el experimento**](/docs/run-an-incrementality-for-remarketing-experiment#launch-the-campaign-and-experiment)<ul><li>En las redes publicitarias, crea y lanza una campaña dirigida a los usuarios de la audiencia.</li><li>El experimento de Incrementalidad se genera automáticamente (para suscriptores de Incrementalidad).</li></ul>Los participantes del grupo de prueba están expuestos a anuncios. El grupo de control no lo está. |
| 4 | [**Analiza los resultados**](/docs/run-an-incrementality-for-remarketing-experiment#analyze-the-results)<ul><li>El análisis de Incrementalidad se muestra en el <Anchor target="_blank" href="/marketers/es/docs/incrementality-for-remarketing-overview#dashboard-de-incrementality">panel de Incrementalidad</Anchor>.</li><li>Los datos de usuario a nivel de fila están disponibles en los <Anchor target="_blank" href="/marketers/es/docs/incrementality-for-remarketing-overview#reportes-de-raw-data">informes de datos sin procesar de Incrementalidad</Anchor> (a través de Data Locker).</li></ul>Los conocimientos adquiridos de experimentos de Incrementalidad bien realizados te permiten optimizar tus campañas de marketing para lograr un impacto positivo máximo. Por ejemplo, pueden ayudarte a identificar el mejor mensaje para una audiencia objetivo, el diseño más creativo o promoción, la fuente de medios más efectiva y más. |

<div id="set-up-the-experiment" />

## Configura el experimento

<div id="know-your-test-objectives" />

<Accordion title="Define los objetivos de tu prueba">

Como en cualquier experimento, es esencial definir exactamente qué estás evaluando (variables) y cuál es el resultado que esperas obtener (la hipótesis). La siguiente tabla proporciona pautas y mejores prácticas para diseñar tu experimento:

| Variables/Hipótesis | Pautas y mejores prácticas |
| --- | --- |
| Audiencia | Describe la audiencia que estás evaluando. Selecciona una audiencia que ya hayas configurado en Audiencias de AppsFlyer, o crea una nueva que cumpla con tus criterios de prueba. |
| Tamaño de la audiencia | Selecciona una audiencia con una amplia base de usuarios y un evento con altas tasas de conversión. Un tamaño de muestra grande tiene más probabilidades de producir <Anchor target="_blank" href="/marketers/es/docs/incrementality-for-remarketing-overview#statistical-significance">resultados estadísticamente significativos</Anchor>.<br /><br />**Mejor práctica:** Una audiencia de al menos 50.000 usuarios, divididos entre 1 y 3 redes publicitarias más el grupo de control. |
| Campaña | Describe la campaña (mensajes, incentivos, etc.). |
| Porcentaje del grupo de control | El grupo de control se establece automáticamente en el 15% del tamaño de la audiencia (la mejor práctica es entre el 15% y el 25%). |
| Grupo de prueba | Determina las redes publicitarias que deseas evaluar. El porcentaje se dividirá equitativamente entre ellas (pero puedes ajustar el porcentaje de audiencia que irá a cada una).<br /><br />**Mejor práctica:** 1-3 redes publicitarias |
| Hipótesis | Define el resultado esperado del experimento.<br /><br />Aunque puede parecer un poco contradictorio predecir el resultado antes de comenzar, establecer una hipótesis es una parte fundamental del diseño experimental; es lo que te ayuda a interpretar los resultados.<br /><br />**Mejor práctica:** Plantea una hipótesis que sea fácilmente comprobable utilizando porcentajes reales en lugar de estimaciones vagas. Por ejemplo:<ul><li>***Un 15% más de usuarios comprarán una actualización*** es una hipótesis fácilmente comprobable.</li><li>***Un número significativamente mayor de usuarios comprará una actualización*** es más difícil de probar.</li></ul> |

<div id="example" />

> 📄 **Ejemplo**
>
> Siguiendo las pautas mencionadas anteriormente, podrías definir un experimento similar al siguiente.
>
>
>
> | Variables/Hipótesis | Ejemplo |
> | --- | --- |
> | Audiencia | Usuarios que completaron el registro pero no realizaron una compra |
> | Tamaño de la audiencia | 100.000 |
> | Campaña | Una campaña que ofrece un vale de descuento a los usuarios que compran durante un periodo específico. |
> | Porcentaje del grupo de control | 15% del tamaño de la audiencia |
> | Grupo de prueba | Enviar al resto de los miembros de la audiencia a:<br /><br />* Red A (42% de la audiencia)<br />* Red B (43% de la audiencia) |
> | Hipótesis | La tasa de usuarios del grupo de prueba que interactúan con la campaña de remarketing y realizan una compra será un 10% mayor que la de los usuarios del grupo de control. |

</Accordion>

<div id="create-the-target-audience-and-split-groups" />

<Accordion title="Crea la audiencia objetivo y divide los grupos">

Una vez que hayas definido tus objetivos, el siguiente paso es configurar la audiencia que vas a probar:

1. En Audiencias de AppsFlyer, <Anchor target="_blank" href="/marketers/es/docs/audiences-guide#crear-y-gestionar-las-audiencias">crea una audiencia</Anchor> (o puedes dividir una audiencia existente que cumpla con los requisitos de tu diseño experimental).
2. En la pestaña **Conectar** de la audiencia seleccionada:
   * Conecta la audiencia con 1-3 socios de redes publicitarias.
   * Asegúrate de que el conmutador que <Anchor target="_blank" href="/marketers/es/docs/audiences-guide#audience-split-and-control-groups">divide la audiencia</Anchor> esté habilitado (se activa **automáticamente para los suscriptores de Incrementality, en audiencias creadas después del 11 de enero de 2023**). Si no es así, haz clic en el conmutador para habilitarlo.  

     <Image align="center" alt="Medir_impacto_inc_toggle.jpg" src="https://files.readme.io/a04b3be68fcc00d62e6a92391fbbea685ca2bfcbf83bd5678660c6a1b8c58fc2-30780493858065.jpg" />
   * El grupo de control se establece automáticamente al 15% (recomendado).
   * El resto de la audiencia se divide automáticamente de forma equitativa entre los socios de red publicitaria seleccionados.
     * El porcentaje total de división debe ser igual al 100% (incluyendo el grupo de control).

Una vez que hayas guardado tu audiencia con la división habilitada, se iniciará automáticamente un experimento de Incrementalidad (solo para suscriptores de Incrementalidad). Estos experimentos se pueden visualizar en el panel de Incrementalidad con el prefijo "[Auto]" delante del título.

<Image align="center" alt="Auto_antes_del_título.jpg" src="https://files.readme.io/fdab39eee29240ae0d9b907f7c6504a9e08e470454d5f8e43933512c65db15d4-30780522066833.jpg" />

**Notas importantes:**

* Mientras se esté ejecutando el experimento, no realices cambios en la configuración de la audiencia. Modificar socios, el nombre de la audiencia u otras configuraciones provocará inexactitudes en el análisis estadístico.  
  **Mejor práctica:** Incluso tras finalizar un experimento, si necesitas realizar cambios en la definición de una audiencia previamente probada, primero duplica la audiencia y aplica las modificaciones en la nueva copia. Esto garantiza la integridad continua de los datos históricos en el panel de Incrementalidad.
* Modificar la división y la configuración de socios de una audiencia existente finalizará el experimento de Incrementalidad actual y generará uno nuevo.
* #### <span id="check-for-audience-expansion-features"></span>Revisa las funciones de expansión de audiencia:

Tanto los anuncios de Meta como los de Google Ads tienen una función opcional que permite que las campañas apunten a audiencias fuera de una lista configurada para ampliar su alcance. Si esta función se mantiene activada, sesgará los experimentos de Incrementalidad y producirá resultados inexactos. **Por favor, verifica que esta función esté desactivada.**

En los anuncios de Meta, la función se llama “Audiencia personalizada de ventaja”. Se encuentra a nivel del conjunto de anuncios y está habilitada por defecto.

<Image align="center" alt="imagen__4_.png" src="https://files.readme.io/a0bee1bbb2c6521007146a5ac70de52ce821f459fd2aece127a97a2e0b75c93d-30780493862033.png" width="458px" />
En Google Ads, se denomina “Expansión de audiencia”.

<Image align="center" alt="Limitación_de_incrementalidad_de_Google_Ads_recortada.jpg" src="https://files.readme.io/042aac534d0a527753b643bb63a52f59889219ebda922cc04f8a61c5984afb80-30780493867409.jpg" width="436px" />

</Accordion>

<div id="launch-the-campaign-and-experiment" />

<Accordion title="Lanza la campaña y experimenta">

**Realiza las siguientes acciones:**

<div id="1-configure-campaigns-on-ad-networks" />

#### 1. Configura campañas en redes publicitarias

El primer paso es crear una campaña que apunte a los usuarios de tu audiencia y lanzarla en la red publicitaria correspondiente (para cada red donde se cargue la audiencia).

* **¡Importante!** Para obtener resultados de prueba precisos, configura la campaña para que se dirija **únicamente** a los usuarios de la audiencia en prueba; no incluyas usuarios de otras fuentes.
* Si la audiencia probada es nueva, puede tardar hasta 24 horas en estar disponible en la plataforma de la red publicitaria.

<div id="2-ensure-the-correct-campaign-is-linked-to-the-experiment" />

#### 2. Asegúrese de que la campaña correcta esté vinculada al experimento.

Se inicia automáticamente un nuevo experimento de Incrementalidad una vez que se crea una nueva audiencia con la opción "Medir impacto incremental" activada (o si se activa en una audiencia existente). La campaña más relevante se asocia automáticamente al experimento, pero puedes modificarla si lo deseas.

**Para vincular o modificar una campaña:**

1. Desde el **panel de Incrementalidad** > experimento específico > haz clic en **Editar experimento**

<Image align="center" alt="Editar_experimento.jpg" src="https://files.readme.io/f478737e2a8db560a5ea33b287fe8f41587ec1f743c1bc01ba15ab6ce72478e9-30780493873425.jpg" width="642px" />

O

Desde **Audiencias**, localiza la audiencia específica > haz clic en **+ Vincular campaña** en la columna Incrementalidad.

<Image align="center" alt="Link_campaign__audiences_status_.jpg" src="https://files.readme.io/5da762448fb731843fef0aec66ae826ed6922a5dd213a78ccd93f544b21fcfdc-small-30780522084625.jpg" width="768px" />

Se mostrará una ventana que te permitirá vincular campañas.

<Image align="center" alt="Vincular_campaña_a_experimento_ventana.jpg" src="https://files.readme.io/9492444847bfc6a26778624d72d5b468acc62b705530db66d0bd0fdff89f5e89-30780493883409.jpg" width="506px" />

2. Selecciona las campañas pertinentes para cada red publicitaria.

**Nota:** El menú desplegable se llenará con campañas de tus socios de medios. Cuando los datos estén disponibles, las campañas en el menú desplegable se ordenarán por probabilidad de uso para la audiencia específica. La mejor sugerencia estará preseleccionada.

3. Haz clic en **Guardar**.

La campaña ahora está asociada al experimento.

<div id="manually-create-an-experiment" />

#### Crear manualmente un experimento

Si eres suscriptor de Incrementalidad y creaste tu audiencia después del 11 de enero de 2023, no necesitas crear un experimento manualmente. Los experimentos se crean automáticamente para tus audiencias (y aparecen en el panel de Incrementalidad con "[Auto]" antes del título). Si deseas crear un experimento manual para una audiencia más antigua o por otra razón, sigue estos pasos.

**Para crear manualmente un nuevo experimento de Incrementalidad:**

* En AppsFlyer, desde el menú lateral, selecciona **Optimizar** > **Incrementalidad**.
* Desde la página **Experimentos de Incrementalidad**, haz clic en el botón **Nuevo experimento**.
* Siga los pasos del asistente para crear el experimento. Se proporcionan instrucciones detalladas a medida que avanza en cada paso.

  <div id="notes" />

  > 📘 **Notas**
  >
  > Paso 2 del asistente – Configurar audiencia
  >
  > <Image align="center" alt="" src="https://files.readme.io/e956b50df1931b190206f42b48a8f2f061937fe1f25c96801a416d287d7eb3f5-30780493888273.png" width="603px" />
  >
  > En el paso 2 del asistente, se le pide que escoja la **fecha a partir de la cual los miembros de la audiencia deben incluirse en el experimento.**
  >
  > Por defecto, esta es la fecha en la que la audiencia se dividió inicialmente con un grupo de control. Para garantizar resultados precisos, debe cambiar esta fecha si se da alguna de las siguientes situaciones:
  >
  > * Si has realizado cambios en la definición de la audiencia seleccionada (<Anchor target="_blank" href="/marketers/es/docs/audiences-guide#todo-sobre-los-conjuntos-de-reglas">conjuntos de reglas de segmentación de audiencias</Anchor>, <Anchor target="_blank" href="/marketers/es/docs/audiences-guide#user-identifier-device-id-vs-customer-id">identificador de usuario</Anchor>, etc.) → cambia esta fecha para que coincida con la última fecha en la que se realizaron estos cambios en la definición de la audiencia.
  > * Si está probando una nueva campaña en una audiencia ya existente →  cambie esta fecha a la fecha de lanzamiento de la nueva campaña.
  >
  > **Paso 3 del asistente: Establecer objetivos**
  >
  > <Image align="center" alt="Paso 3: Establecer objetivos.jpg" src="https://files.readme.io/9c58ad61463b1751f5ad8b2c5235d6d61b13baa156db56d5edeb156debbcfeaa-30780522104081.jpg" />
  >
  > Aquí es donde se selecciona la aplicación objetivo y los KPIs.
  >
  > **Nota:** Todos los demás KPIs estarán disponibles al finalizar el experimento, incluso si no han sido seleccionados.
  >
  > Paso 4 del asistente – Revisión
  >
  > <Image align="center" alt="" src="https://files.readme.io/75c90dc66cff6abc772a352d81b6b57498e5915da66efaa83a754d9a5a08be70-30780522113681.png" width="583px" />
  >
  > En el paso 4 del asistente, debe establecer el **período del experimento.**
  >
  > * Por defecto, un experimento está configurado para ejecutarse durante 30 días desde su creación. Este es el período mínimo recomendado.
  > * Seleccione la opción **Continuar el experimento indefinidamente** si desea que continúe ejecutándose hasta que decida finalizarlo.


</Accordion>

<div id="analyze-the-results" />

<Accordion title="Analizar los resultados">

Los resultados iniciales del experimento están disponibles en el <Anchor target="_blank" href="/marketers/es/docs/incrementality-for-remarketing-overview#dashboard-de-incrementality">panel de incrementabilidad</Anchor> aproximadamente 48 horas después del lanzamiento de las campañas conectadas en las redes publicitarias (actualizada <Anchor target="_blank" href="/marketers/es/docs/about-data-freshness-and-timezone-support#eod">diariamente</Anchor>). Podría ver <Anchor target="_blank" href="/marketers/es/docs/understand-incrementality-for-remarketing-experiment-alerts">alertas en la página del experimento</Anchor> que le ayuden a identificar problemas que comprometan la precisión de los resultados y sugieran acciones a tomar para resolverlos.

<Anchor target="_blank" href="/marketers/es/docs/incrementality-for-remarketing-overview#reportes-de-raw-data">Los informes de datos sin procesar de incrementabilidad</Anchor> están disponibles a través de Data Locker.

</Accordion>

<div id="see-also" />

> 📄 **Véase también**
>
> * <Anchor target="_blank" href="/marketers/es/docs/audiences-guide">Guía de audiencias</Anchor>

<div data-zendesk-anchors="overview=sobre-el-experimento h_01HARVCSMM80QXXXKJC8TX7CKC=sobre-el-experimento get-started=comienza h_01HARVCSMMYJVN6GJ3TB46P8AC=comienza set-up-the-experiment=configura-el-experimento h_01HARVCSMMMAJ6VTYHZ2ZJ5HNS=configura-el-experimento h_01HARVCSMM9P2HN5WA9C16PA5E=know-your-test-objectives h_01HARVCSMM2THH54JH58GM1K57=ejemplo h_01HARVCSMM77RV7NM9K7D5FJM5=create-the-target-audience-and-split-groups check-for-audience-expansion-features=revisa-las-funciones-de-expansi%C3%B3n-de-audiencia h_01HARVCSMMXNE4NCWSQZ9SHK1J=revisa-las-funciones-de-expansi%C3%B3n-de-audiencia h_01HARVCSMMH11D6RKDZQZ3WVZ6=launch-the-campaign-and-experiment 1-configure-campaigns-on-ad-networks=1-configura-campa%C3%B1as-en-redes-publicitarias h_01HARVCSMMVXJWCT2BX3CVC3VT=1-configura-campa%C3%B1as-en-redes-publicitarias 2-link-campaigns-to-experiment=2-aseg%C3%BArese-de-que-la-campa%C3%B1a-correcta-est%C3%A9-vinculada-al-experimento h_01HARVCSMNAWNYEY83NC6Y5XV4=2-aseg%C3%BArese-de-que-la-campa%C3%B1a-correcta-est%C3%A9-vinculada-al-experimento manually-create-an-experiment=crear-manualmente-un-experimento h_01HARVCSMNZVWK8Z36ER1HH10W=crear-manualmente-un-experimento h_01HARVCSMN5944HRD9N7YEKT3P=notas h_01HARVCSMNS961WKFX280J3R2X=analyze-the-results h_01HE7RBMSE1RHVSJC7B7FZG8SJ=v%C3%A9ase-tambi%C3%A9n" />
