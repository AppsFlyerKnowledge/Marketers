---
title: 'Boletín: Mejora de la seguridad para el tráfico gestionado por agencias'
metadata:
  keywords:
    - Advertisers
    - Agencies
    - Ad Networks
    - Marketers
    - Platform essentials
table_of_contents: false
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-negri
    - Marketers
    - Platform essentials
    - Agencies
    - Ad Networks
  created_at: '2024-06-09T14:08:35Z'
  edited_at: '2026-10-20T03:55:29Z'
  id: 25770412740369
  locale: es
  section: Bulletins
  section_id: 6551161473041
  url: https://support.appsflyer.com/hc/es/articles/25770412740369
---
| **Novedades** | Para proteger tus datos, garantizar su seguridad y reducir el fraude, estamos mejorando las medidas de seguridad para las agencias que administran el tráfico en nombre de los anunciantes que ejecutan campañas en redes de publicidad. A partir de la fecha de entrada en vigor, solo se registrará y medirá en AppsFlyer el tráfico de las agencias autorizadas por las ad network. Esto significa que las agencias no autorizadas no podrán configurar la integración (la ventana de configuración del partner aparecerá atenuada) y que el tráfico no autorizado de estas agencias dará lugar a una respuesta 403 (Prohibido) de AppsFlyer. Una vez que se añadan las agencias a la lista, la aprobación se aplicará a toda la cuenta, lo que les permitirá ejecutar campañas con todas las aplicaciones de tu red.<br /><br />**Nota:**<ul><li>Se aplica también a parámetros af\_prt vacíos en enlaces de atribución</li><li>No se aplica a las agencias que trabajan con <Anchor target="_blank" href="/marketers/es/docs/self-reporting-networks-srns">SRNs</Anchor></li></ul> |
| --- | --- |
| **Fecha de entrada en vigor** | 31 de julio de 2024 |
| **Donde** | <ul><li>**Agencia:** Página de integración</li><li>**Ad network:** Centro de seguridad</li></ul> |
| **Lo que debes saber** | <ul><li>**Agencia:** Ponte en contacto con el partner y asegúrate de que el ID de tu agencia (<Anchor target="_blank" href="/partners/es/docs/about-agency-accounts#parámetro-af_prt">el nombre af\_prt</Anchor>) esté añadido a su lista de agencias autorizadas.</li><li>**Partner:** Asegúrate de añadir todos los ID de agencia (af\_prt) en la <Anchor target="_blank" href="/partners/es/docs/set-up-your-list-of-authorized-agencies">nueva sección de agencias autorizadas</Anchor>.</li></ul> |
| **Implicaciones** | A partir de la fecha especificada, no se registrará ni medirá el tráfico de las agencias que no estén en la lista aprobada de la red de publicidad, ni podrán acceder a la página de integración de todas las aplicaciones que ejecuten campañas en la red de publicidad. |