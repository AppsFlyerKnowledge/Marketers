---
title: Alertas de experimentos de incrementalidad
metadata:
  keywords:
    - Premium Feature
    - Marketers
    - Incrementality
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-niv-klein
    - Marketers
    - Incrementality
  created_at: '2023-03-05T12:31:35Z'
  edited_at: '2024-11-20T16:47:31Z'
  id: 13479545385489
  locale: es
  section: Incrementality for remarketing
  section_id: 6551378485649
  url: https://support.appsflyer.com/hc/es/articles/13479545385489
---
> **A simple vista:** Comprende las alertas y solucionalas para asegurar resultados precisos en los experimentos.

<Image align="center" alt="exp_alerts_modificado.jpg" src="https://files.readme.io/3981e4a4bd66206d9b5986cc1b573f67e1ab836042a1f73518f48a1ea17b6568-35266706078481.jpg" />

<div id="about-experiment-alerts" />

## Sobre las alertas de experimentos

Después de <Anchor target="_blank" href="/marketers/es/docs/run-an-incrementality-for-remarketing-experiment">configurar un experimento de Incrementalidad</Anchor>, es posible que veas alertas en el panel de Incrementalidad. Estas alertas están hechas para ayudarte a identificar problemas que pueden afectar la integridad y precisión de los resultados de tus experimentos. Brindan información específica sobre los problemas y sugieren acciones a tomar para solucionarlos, asegurando resultados precisos en los experimentos. Este artículo ofrece una visión completa de los distintos tipos de alertas, así como las acciones recomendadas para solucionarlas.

<div id="alert-types" />

## Tipos de alertas

Las alertas de experimentos se clasifican en las siguientes categorías:

<div id="experiment-setup" />

<Accordion title="Configuración del experimento">

<div id="audience-deletion-or-control-group-removal" />

#### Eliminación de audiencias o grupos de control

Experimentos cuyos públicos conectados han sido eliminados o cuyos grupos de control de audiencia dividida han sido eliminados. En ambos casos, al visitar la página del experimento, aparecerá un error 404.

**Para resolver esto y restablecer los resultados del experimento:**  
Si la **audiencia fue eliminada**, contacta a tu CSM, quien la restaurará manualmente.  
Si el **grupo de control fue eliminado**, divide de nuevo la audiencia y configura el grupo de control con el mismo porcentaje de antes.

<div id="more-suitable-campaign-srns-only" />

#### ¿Campaña más adecuada? (Solo SRN)

Esta alerta solo es relevante para las redes de autorreporte (SRN). Este aviso aparece cuando una campaña está vinculada a un experimento, pero los datos sugieren que puede haber otra campaña más adecuada para el público objetivo.  
Una "campaña más adecuada" es aquella que, durante el período del experimento, apunta al grupo de prueba de manera más efectiva que la campaña configurada (y no apunta al grupo de control).

**Acciones recomendadas:** Verifica si la campaña correcta está vinculada.

**Nota:** También es recomendable asegurarse de que la audiencia no esté incluida en la segmentación de otras campañas.

<div id="no-impressions-non-srns-only" />

#### Sin impresiones (solo para SRN no incluidos)

Cuando se realizan experimentos de incrementalidad en campañas que se ejecutan en redes publicitarias no SRN, AppsFlyer necesita impresiones de los usuarios para calcular con precisión el impacto incremental de dichas campañas. Sin impresiones, los resultados no se mostrarán en la página del experimento.

Esta alerta indica que, por algún motivo, no estamos recibiendo datos de impresiones de la campaña conectada.

**Acciones a tomar:** Compruebe que está recibiendo impresiones del socio de medios y que la campaña probada esté operativa y mostrando anuncios.

</Accordion>

<div id="experiment-background-environment" />

<Accordion title="Entorno de fondo del experimento">

<div id="background-campaign-one-or-multiple" />

#### Campaña en segundo plano (una o varias)

Esta alerta aparece cuando existen campañas muy grandes y no relacionadas que impactan significativamente más a la audiencia que la campaña configurada en el experimento.

¿Cómo puede suceder esto?  
No es raro que haya campañas no relacionadas en segundo plano, pero si tienen un presupuesto mayor o se ejecutan con más intensidad, pueden eclipsar la campaña configurada y afectar los resultados del experimento.

**Acciones a tomar:**

* Aumente el impacto de su campaña ampliando el presupuesto.
* Compruebe si la audiencia probada se solapa con la audiencia a la que apunta la campaña en segundo plano (puede verificarse con la función de superposición de audiencias de socios).
* Verifique si la audiencia probada se solapa con la campaña de fondo no relacionada.
* Refuerce la segmentación de la audiencia probada.
* Si ha tomado medidas para minimizar el impacto de campañas en segundo plano, establezca la fecha de inicio del experimento después de realizar estos cambios.

**Nota:** **Es recomendable minimizar la segmentación de la audiencia probada con otras campañas.**

</Accordion>

<div id="linked-campaign-performance" />

<Accordion title="Rendimiento de la campaña vinculada">

<div id="audience-overlap" />

#### Superposición de audiencias

La campaña conectada está dirigida a audiencias que se solapan. Esto significa que la configuración de segmentación de la campaña vinculada incluye más de una audiencia.  
Además, las múltiples audiencias en la configuración de la campaña probada se solapan. Esto provocará una segmentación fuera del público evaluado, incluyendo la segmentación del grupo de control del público evaluado.

**Acciones a tomar:**  
Actualice la segmentación de la campaña para incluir solo al público probado y elimine cualquier otro público adicional.

<div id="control-group-is-targeted" />

#### El grupo de control está siendo objetivo

Esta advertencia indica que la campaña configurada está apuntando al grupo de control aunque debería solo dirigirse al grupo de prueba.

**¿Cómo puede ocurrir esto?**

* El experimento fue vinculado a la campaña incorrecta.
* La campaña del lado del socio de medios se configuró para dirigirse a usuarios fuera del público (obtenga información sobre las <Anchor target="_blank" href="/marketers/es/docs/run-an-incrementality-for-remarketing-experiment#revisa-las-funciones-de-expansión-de-audiencia">funciones de expansión de audiencia</Anchor> en Facebook y Google).
* La red no está aplicando la configuración de segmentación.

**Acciones a tomar:**  
Revise los escenarios comunes listados anteriormente y contacte con su CSM si tiene dudas. En ciertos casos, dependiendo de la importancia de la exposición a la campaña por parte de los usuarios del grupo de control, no hay solución para esto y se debe crear un nuevo experimento de Incrementalidad.

Si la infracción es relativamente pequeña, basta con asegurarse de que la orientación al grupo de control se haya detenido. Haga un seguimiento de la advertencia en la interfaz de usuario del experimento y compruebe si la alerta aún aparece después de unos días.

<div id="detailed-targeting-toggle-is-enabled" />

#### La opción de segmentación detallada está activada

La segmentación detallada es una característica de ciertas redes publicitarias que permite afinar quién ve sus anuncios. Esta alerta aparecerá si la opción de segmentación detallada de la campaña está activada. Cuando está activada, permitirá a la campaña dirigirse fuera del público configurado.

**Acciones recomendadas:**  
Verifique que la opción de segmentación detallada esté desactivada en la configuración de la campaña del lado del socio.

<div id="low-activity" />

#### Poca actividad

La campaña no está entregando anuncios o está entregando muy pocos anuncios al público objetivo.

**Acciones a tomar:** Investigue el problema en el lado del socio de medios para entender por qué la campaña no está entregando anuncios.

<div id="multiple-audiences-connected" />

#### Múltiples públicos conectados

La configuración de segmentación de la campaña incluye múltiples públicos. Esto puede provocar que se dirija fuera del público evaluado o del grupo de control, lo que afectará finalmente los resultados de la prueba.

**Acciones a tomar:**  
Una buena práctica para las pruebas de incrementalidad es que la campaña probada se dirija únicamente a una audiencia.

<div id="out-of-audience-targeting" />

#### Segmentación fuera de la audiencia

La campaña evaluada también se está dirigiendo a usuarios que no forman parte del grupo de prueba de la audiencia objetivo. Parte del coste de la campaña se está destinando a mostrar anuncios a usuarios que no están relacionados con la audiencia de prueba y que no se consideran en la prueba de incrementalidad.

Por lo tanto, al invertir en usuarios no relacionados, las métricas que incluyen el coste de la campaña, como iROAS y CPiA, estarán distorsionadas. Tendrán en cuenta el coste total de la campaña, incluyendo el coste de mostrar anuncios a usuarios fuera de la audiencia, pero no contabilizarán sus conversiones.

**¿Cómo puede ocurrir esto?**

* El experimento fue vinculado a la campaña incorrecta.
* La campaña del lado del socio de medios se configuró para dirigirse a usuarios fuera del público (obtenga información sobre las <Anchor target="_blank" href="/marketers/es/docs/run-an-incrementality-for-remarketing-experiment#revisa-las-funciones-de-expansión-de-audiencia">funciones de expansión de audiencia</Anchor> en Facebook y Google).
* La red no está aplicando la configuración de segmentación.

**Acciones a tomar:**  
Asegúrese de que la configuración de segmentación de la campaña incluya solo la audiencia probada y que no permita dirigirse fuera de esa audiencia.

</Accordion>

<div data-zendesk-anchors="about-experiment-alerts=sobre-las-alertas-de-experimentos h_01HNZPQJDA5D7Q04CDKMYCW763=sobre-las-alertas-de-experimentos types-of-alerts=tipos-de-alertas h_01HE7R6CQ5R9HAYG83B3903AY8=tipos-de-alertas h_01HE7R6CQ5SNX6VYFD18501JYT=experiment-setup audience-deletion-or-control-group-removal=eliminaci%C3%B3n-de-audiencias-o-grupos-de-control h_01HE7R6CQ5DM1QNN1E55TGDKKH=eliminaci%C3%B3n-de-audiencias-o-grupos-de-control more-suitable-campaigns-srns-only=campa%C3%B1a-m%C3%A1s-adecuada-solo-srn h_01HE7R6CQ518RS50X87243M7BV=campa%C3%B1a-m%C3%A1s-adecuada-solo-srn no-impressions-received-nonsrns-only=sin-impresiones-solo-para-srn-no-incluidos h_01HE7R6CQ57DV8D642APE01JV0=sin-impresiones-solo-para-srn-no-incluidos h_01HE7R6CQ5XFAE56PTX6RRZD5J=experiment-background-environment background-campaign-one-or-multiple=campa%C3%B1a-en-segundo-plano-una-o-varias h_01HE7R6CQ5AZW1RB7XJH4GEEBT=campa%C3%B1a-en-segundo-plano-una-o-varias h_01HE7R6CQ5C6009QZK6TQS6QGC=linked-campaign-performance audience-overlap=superposici%C3%B3n-de-audiencias h_01HE7R6CQ6X5C0D4E519W535PH=superposici%C3%B3n-de-audiencias control-group-is-targeted=el-grupo-de-control-est%C3%A1-siendo-objetivo h_01HE7R6CQ5NFH58H8ZNRG6E4MG=el-grupo-de-control-est%C3%A1-siendo-objetivo detailed-targeting-toggle-is-enabled=la-opci%C3%B3n-de-segmentaci%C3%B3n-detallada-est%C3%A1-activada h_01HKSTD08WK37RHM5DM922GGWF=la-opci%C3%B3n-de-segmentaci%C3%B3n-detallada-est%C3%A1-activada low-activity=poca-actividad h_01HE7R6CQ6C76SZEAN0R93H9QN=poca-actividad multiple-audiences-connected=m%C3%BAltiples-p%C3%BAblicos-conectados h_01HKSTFSKDTD2Z8HKCCX2MWBJQ=m%C3%BAltiples-p%C3%BAblicos-conectados outofaudience-targeting=segmentaci%C3%B3n-fuera-de-la-audiencia h_01HE7R6CQ6TVCGW5X8GBX0AJKS=segmentaci%C3%B3n-fuera-de-la-audiencia" />
