---
title: 'Boletín: transición de la integración de Google Marketing Platform (GMP)'
metadata:
  keywords:
    - Agencies
    - Marketers
    - Mobile Attribution
table_of_contents: false
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
    - Agencies
  created_at: '2023-12-18T11:43:04Z'
  edited_at: '2026-10-20T03:55:48Z'
  id: 21035061438737
  locale: es
  section: Bulletins
  section_id: 6551161473041
  url: https://support.appsflyer.com/hc/es/articles/21035061438737
---

<Table>
  <tbody>
    <tr>
      <td>
        **Novedades**
      </td>
      <td>
        Como parte de los preparativos para hacer cumplir la <Anchor target="_blank" href="https://commission.europa.eu/strategy-and-policy/priorities-2019-2024/europe-fit-digital-age/digital-markets-act-ensuring-fair-and-open-digital-markets_en">Ley de Marketing Digital</Anchor> (DMA), Google está actualizando su <Anchor target="_blank" href="https://www.google.com/about/company/user-consent-policy/?sjid=15416941068016224808-NA">política de consentimiento de usuarios de la UE</Anchor>. AppsFlyer está haciendo los cambios necesarios para respaldar los requisitos de la política de Google.

        Las siguientes integraciones de Google Marketing Platform (GMP) están disponibles actualmente:

        * [Heredado] CM360 (DoubleClick) `doubleclick_int`
        * <Anchor target="_blank" href="/marketers/es/docs/google-marketing-platform-display-video-360-dv360-integration">DV360 (nueva integración)</Anchor> `dv360_int`

        A partir del 9 de septiembre de 2025, la integración heredada `doubleclick_int` quedará obsoleta. Si estás usando esta integración, tendrás que hacer la transición a la nueva integración de DV360 para seguir ejecutando campañas y medirlas usando GMP.
      </td>
    </tr>
    <tr>
      <td>
        **Acción requerida**
      </td>
      <td>
        Pasa a la nueva integración de DV360 `dv360_int` lo antes posible y, como muy tarde, no más tarde del 30 de junio de 2025.
      </td>
    </tr>
    <tr>
      <td>
        **Pasos a seguir**
      </td>
      <td>
        Asegúrate de configurar ambas plataformas, GMP y AppsFlyer:

        **Configuración en GMP**

        1. Inicia sesión en tu cuenta de CM360 o DV360.   
           **Nota:** Si completas los pasos en CM360, no es necesario completarlos en DV360.
        2. Crea o reutiliza tu enlace de atribución de partner (Link ID) siguiendo <Anchor target="_blank" href="https://support.google.com/displayvideo/answer/10956727">estas instrucciones</Anchor>.

        **Configuración en AppsFlyer**

        1. Completa tu integración de DV360 en AppsFlyer siguiendo <Anchor target="_blank" href="/marketers/es/docs/google-marketing-platform-display-video-360-dv360-integration#integration-procedures">estas instrucciones</Anchor>.   
           **Nota:** Para mantener la consistencia de los datos, asegúrate de que la configuración sea similar a la de la integración heredada (ventanas de lookback, postbacks de eventos in-app, etc.).
        2. **Prueba la nueva integración:**   
           Espera aproximadamente un día para confirmar los datos de la nueva integración. Después podrás desactivar la integración heredada.
      </td>
    </tr>
    <tr>
      <td>
        **Lo que debes saber**
      </td>
      <td>

      </td>
    </tr>
    <tr>
      <td>

      </td>
      <td>
        <table><thead><tr><th><strong>Consideraciones</strong></th><th>Opciones disponibles</th></tr></thead><tbody><tr><td colspan="2"><span id="media-source-pid"></span><strong>PID de fuente de medios</strong></td></tr><tr><td><span id="after-completing-the-migration-the-dv360-media-source-pid-changes-from-doubleclick_int-to-dv360_int"></span>Después de completar la migración, el PID de la fuente de medios de DV360 cambia de <kbd>doubleclick_int</kbd> a <kbd>dv360_int</kbd>.</td><td>Si estás extrayendo raw data de AppsFlyer para llevarlos a tu BI o a cualquier herramienta de análisis de terceros, considera cambiar el nombre de la fuente de medios.</td></tr><tr><td colspan="2"><span id="outofstore-apps"></span><strong>Aplicaciones out-of-store</strong></td></tr><tr><td><span id="apps-from-unofficial-app-stores-arent-supported-in-the-dv360-integration-the-integration-relies-on-a-link-id-which-is-generated-for-apps-obtained-through-official-app-stores"></span>Las apps de tiendas de aplicaciones no oficiales no son compatibles con la integración de DV360. La integración se basa en un ID de enlace, que se genera para las apps obtenidas a través de tiendas de aplicaciones oficiales.</td><td>Si tu app se descarga desde fuentes ajenas a las tiendas de aplicaciones oficiales, ponte en contacto con tu CSM o con <a href="mailto:hello@appsflyer.com">hello@appsflyer.com</a>.</td></tr><tr><td colspan="2"><span id="attribution-data-duplication"></span><strong>Distribución de los datos de atribución</strong></td></tr><tr><td colspan="2"><span id="while-both-integrations-are-active-in-appsflyer-data-duplication-is-expected-inapp-events-for-installsreengagements-attributed-to-the-legacy-integration-remain-credited-accordingly"></span>Cuando ambas integraciones están activas y reclaman la atribución de instalaciones, <strong>la atribución se reparte aleatoriamente entre ellas</strong>: una actúa como fuente principal y la otra como colaboradora. Esto garantiza que los datos no se dupliquen. Por ejemplo, si DV360 es responsable de 100 instalaciones, puede que veas 70 instalaciones de la integración heredada y 30 de DV360, o 80 instalaciones de DV360 y 20 instalaciones de la integración heredada.</td></tr><tr><td colspan="2"><span id="inapp-events-for-installsreengagements-attributed-to-the-legacy-integration-remain-credited-accordingly"></span>Los eventos in-app para instalaciones/re-engagements atribuidos a la integración heredada permanecen acreditados en consecuencia.</td></tr><tr><td colspan="2"><span id="reengagement-reengagement-attribution-is-supported-in-the-dv360-integration"></span><p><strong>Reengagement</strong></p><p>La atribución de re-engagement es compatible con la integración de DV360.</p></td></tr></tbody></table>

        **Discrepancias entre campos**

        Debido a las diferencias entre los campos de datos disponibles en las API heredadas y actualizadas, puede que veas diferencias en algunos campos de AppsFlyer, como se muestra a continuación:

        | **Campo AppsFlyer** | **Campo heredado (doubleclick\_int)** | **Campo de DV360 (dv360\_int)** |
        | --- | --- | --- |
        | Nombre de la campaña | placement\_id | nombre del elemento de pedido |
        | Campaign ID | placement\_id | line\_item\_id |
        | Nombre del conjunto de anuncios | ad\_id | N/D (no compatible) |
        | ID de adset | ad\_id | N/D (no compatible) |
        | Nombre de anuncio | creative\_id | N/D (no compatible) |
        | Ad ID | creative\_id | creative\_id |
      </td>
    </tr>
  </tbody>
</Table>

<div data-zendesk-anchors="while-both-integrations-are-active-in-appsflyer-data-duplication-is-expected%0Ainapp-events-for-installsreengagements-attributed-to-the-legacy-integration-remain-credited-accordingly=while-both-integrations-are-active-in-appsflyer-data-duplication-is-expected-inapp-events-for-installsreengagements-attributed-to-the-legacy-integration-remain-credited-accordingly reengagement%0Areengagement-attribution-is-supported-in-the-dv360-integration=reengagement-reengagement-attribution-is-supported-in-the-dv360-integration" />
