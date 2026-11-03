---
title: 'Boletín: migración de Digital Turbine a la integración unificada de AppsFlyer'
deprecated: false
hidden: false
metadata:
  keywords:
    - Marketers
table_of_contents: false
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  created_at: '2026-09-01T10:27:56Z'
  edited_at: '2026-10-20T03:53:59Z'
  id: 50419778565521
  locale: es
  section: Bulletins
  section_id: 6551161473041
  url: https://support.appsflyer.com/hc/es/articles/50419778565521
---
| **Sección.** | **Detalles** |
| --- | --- |
| **Novedades** | Digital Turbine (DT) está migrando a los anunciantes del PID heredado `digitalturbine_int` al nuevo PID unificado `onedigitalturbine_int`, como parte de la migración de DT a su plataforma de anuncios.<br /><br />La integración unificada te da acceso a las capacidades de aprendizaje automático de DT y a las señales de dispositivos propias. |
| **Fecha de entrada en vigor** | 1 de octubre de 2026 |
| **Lo que debes saber:** | **Nueva fuente de medios**<ul><li>La nueva fuente de medios es `onedigitalturbine_int`.</li></ul>**Dimensiones de informes de campaña**<ul><li>El reporte pasa de Campaña/ID de campaña a Adset/ID de Adset.</li><li>Esto afecta al reporte de cohorte y LTV.</li></ul>**Reporte durante la transición**<ul><li>Selecciona ambas fuentes de medios (`digitalturbine_int` y `onedigitalturbine_int`) al revisar los reportes durante el periodo de transición.</li><li>Revisa cualquier dashboard personalizado, integración de BI o reporte guardado que haga referencia al PID heredado, ya que no incorporarán automáticamente el nuevo PID.</li></ul> |
| **Lo que debes hacer** | <ol><li>Genera nuevos enlaces de atribución mediante la <Anchor target="_blank" href="https://docs.digitalturbine.com/measurement/mmp-guides/appsflyer">guía de integración DT&lt;>AppsFlyer</Anchor> y envíaselos a tu Account Manager de DT.</li><li>DT migrará tus campañas a los nuevos enlaces. No necesitas volver a crearlos manualmente.</li><li>Mantén activa tu integración heredada hasta que caduque tu ventana de lookback, para que las conversiones en curso sigan atribuyéndose correctamente. El día que hagas la transición, cambia el reporte de costos para usar solo la API de reportes unificados de DT. Hazlo en cuanto `onedigitalturbine_int`  esté activo y evita ejecutar ambos a la vez para no duplicar el gasto.</li></ol>**API de reportes y datos de costo**<ul><li>Pasa de la API de reportes heredada a la API de reportes unificados de DT para evitar datos duplicados.</li><li>InCost se configura a nivel de cuenta.</li><li>La pestaña Costo a nivel de aplicación se está eliminando gradualmente para las redes migradas.</li><li>Se requiere autenticación de API a nivel de cuenta en la configuración del partner `onedigitalturbine_int`.</li><li>No se necesita Client ID ni Secret para los datos de costo. AppsFlyer los recibe directamente de DT. Lo que ha cambiado es el flujo de configuración: antes, la integración de costos se habilitaba por aplicación, y ahora se configura una sola vez a nivel de cuenta para varias aplicaciones.</li></ul>**Fecha límite de migración**<ul><li>La **fecha límite es el 1 de octubre de 2026**. Genera tus nuevos enlaces lo antes posible.</li><li>DT supervisará los datos de entrega y los datos de costo después de la migración.</li><li>Si tienes algún problema, contacta con el soporte de AppsFlyer o con tu CSM, o ponte en contacto con tu account manager de DT.</li></ul> |