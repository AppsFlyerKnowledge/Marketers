---
title: 'Boletín: actualización del desglose de Meta Ads por canal'
metadata:
  keywords:
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
  created_at: '2026-08-04T08:33:09Z'
  edited_at: '2026-10-20T03:54:07Z'
  id: 49465306965393
  locale: es
  section: Bulletins
  section_id: 6551161473041
  url: https://support.appsflyer.com/hc/es/articles/49465306965393
---
| Sección. | Detalles |
| --- | --- |
| **¿Qué hay de nuevo?** | Meta ahora requiere la activación por cuenta publicitaria del desglose `impression_device`, con efecto a partir del 6 de agosto de 2026. Como la API de informes de Meta no puede devolver datos de costo desglosados por geolocalización y canal en la misma consulta, las cuentas sin esta activación verán datos incompletos:<ul><li>Es posible que falten datos de costo por canal en la vista predeterminada de My Dashboards</li><li>Es posible que falten datos de Meta en Cost ETL</li></ul>La misma limitación también afecta a los datos de rendimiento de creatividades desglosados por canal. |
| **Fecha de entrada en vigor** | Agosto 6, 2026 |
| **Lo que debes saber:** | Meta aplica esta activación automáticamente en las cuentas de cliente de AppsFlyer. No necesitas hacer nada antes del 6 de agosto.<ul><li>Si después del 6 de agosto faltan tus datos de costo desglosados por canal o tus datos de rendimiento de creatividades desglosados por canal, la activación automática todavía no se ha aplicado a tu cuenta.</li></ul> |
| **Lo que debes hacer** | Sigue estos pasos:<ol><li>Después del 6 de agosto, revisa tus datos de costo desglosados por canal (My Dashboards) y tus datos de rendimiento de creatividades desglosados por canal.</li><li>Si observas un hueco, ponte en contacto directamente con Meta para que te orienten sobre cómo habilitar la activación, o contacta con tu representante de AppsFlyer para obtener ayuda.</li><li>Cuando la activación se aplique a tu cuenta, tus datos se completarán automáticamente poco después mediante backfill.</li><li>También puedes comprobar directamente en Ads Manager si Impression Device ya está habilitado para la cuenta. Consulta más abajo [Comprobar Impression Device en Ads Manager](#comprobar-impression-device-en-ads-manager) para ver los pasos.</li></ol> |

## Comprobar Impression Device en Ads Manager

Para comprobar si Impression Device ya está habilitado para una cuenta publicitaria:

1. Ve a <Anchor target="_blank" href="https://adsmanager.facebook.com/">Ads Manager</Anchor> y selecciona **Configuración**.

[![Barra de herramientas de Ads Manager con el botón Configuración](https://files.readme.io/64c9ac8d571e88bfd098b542456886cc64d6320bf3856721335a077c4f19e5b5-49469436208529.png)](https://files.readme.io/64c9ac8d571e88bfd098b542456886cc64d6320bf3856721335a077c4f19e5b5-49469436208529.png)

2. En el panel de la vista Crear, selecciona **Entrega**.
3. En Entrega, busca **Desgloses adicionales**.
4. En Desgloses adicionales, comprueba si el símbolo más situado junto a **Impression Device** (`impression_device`) ya está seleccionado. Si es así, la activación está activa en esta cuenta.

[![Panel de desgloses adicionales en Ads Manager con iconos de suma para Hora del día, Impression Device y Valor de frecuencia](https://files.readme.io/71eb7c75a3f49a82e98522fcf418acbc6ef378eeda5f093535a168aa8505ade1-49469462456081.png)](https://files.readme.io/71eb7c75a3f49a82e98522fcf418acbc6ef378eeda5f093535a168aa8505ade1-49469462456081.png)

<div data-zendesk-anchors="check-impression-device-in-ads-manager=comprobar-impression-device-en-ads-manager h_01KZ63J08GPADE2AH0KV9NNESC=comprobar-impression-device-en-ads-manager" />
