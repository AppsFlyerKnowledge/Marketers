---
title: Integración de Adobe Experience Platform (AEP) con AppsFlyer Data Locker
metadata:
  keywords:
    - Advertisers
    - Marketers
    - Data Locker
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-rona-einat
    - Marketers
    - Data Locker
  created_at: '2023-03-19T06:54:23Z'
  edited_at: '2026-08-12T12:12:24Z'
  id: 13856826626321
  locale: es
  section: Adobe
  section_id: 6551419728657
  url: https://support.appsflyer.com/hc/es/articles/13856826626321
---
> **De un vistazo:** configura una solución integrada con Adobe Experience Platform (AEP) para enviar datos de eventos sin procesar al lago de datos de Adobe. AEP es la capa de datos para todos los clientes, ya que centraliza los datos en Adobe, una plataforma de datos de clientes que captura los viajes del cliente, los analiza y los proporciona.

<div id="overview" />

## Visión general

La integración de Data Locker con AEP te permite usar los datos de AppsFlyer dentro de Adobe Experience Platform. La integración usa el componente listo para usar (OOTB), respaldado por la plataforma de datos de clientes en tiempo real (RTCDP). Para subir datos de AppsFlyer a Adobe Experience Platform (AEP), los clientes primero deben configurar una conexión del bucket de Data Locker (GCS y AWS) y después configurar AEP para cargar los datos desde el bucket en un conjunto de datos existente o nuevo.

<div id="setting-up-the-integration" />

## Configuración de la integración

<span id="prerequisites"></span>**Requisitos previos**:

* Una suscripción de <Anchor target="_blank" href="/marketers/es/docs/data-locker">Data Locker</Anchor>
* Una cuenta de <Anchor target="_blank" href="https://business.adobe.com/products/experience-platform/adobe-experience-platform.html">Experience Platform</Anchor> con permisos de administrador

**Para configurar la integración**:

1. <span id="step-1-aws-create-an-aws-iam-user-with-bucket-access"></span>Crea un bucket con permisos para Data Locker. Sigue las instrucciones para el almacenamiento de <Anchor target="_blank" href="/marketers/es/docs/data-locker-cloud-service-setup#gcs-storage">GCS</Anchor> o <Anchor target="_blank" href="/marketers/es/docs/data-locker-cloud-service-setup#aws-storage">AWS</Anchor>.
2. Configurar Data Locker. Sigue las <Anchor target="_blank" href="/marketers/es/docs/data-locker-for-marketers#set-up-data-locker">instrucciones de configuración de Data Locker</Anchor> y, cuando selecciones tu bucket de GCS o AWS, asegúrate de seleccionar **Make this connection compatible with Adobe Experience Platform**.
3. Configura el esquema de Data Locker en AEP.
   1. Inicia sesión en AEP con tus credenciales de administrador.
   2. Crea una [clase de evento de experiencia](https://experienceleague.adobe.com/docs/experience-platform/xdm/classes/experienceevent.html?lang=en#) de Adobe XDM.
   3. Añade un nuevo grupo de campos para los campos de AppsFlyer.
   4. Crea el primer campo como un campo de objeto llamado AppsFlyer.  
      Este es el campo principal. Todos los demás campos que se creen serán campos secundarios de este campo de objeto.
   5. Añade los demás campos del esquema de Data Locker. Si usas Adobe CJA, marca customer\_user\_id como identificador empresarial.
4. Configura la fuente del bucket en AEP.
   1. En AEP, añade un conector de bucket (el mismo bucket de AWS o GCS que usaste en Data Locker).
   2. Completa los datos de autenticación obligatorios.
   3. Haz clic en **Connect to source**.
5. Configura el flujo de datos en AEP.
   1. En **AEP Select data**, selecciona los reportes relevantes de AppsFlyer Data Locker en la lista de carpetas del bucket.
   2. Set:
      * Formato de datos: delimitado.
      * Delimitador: ",".
      * Tipo de compresión: Gzip.
   3. Después de la implementación, regresa al **Inicio de sesión único (SSO)** , haz clic en **Confirmar implementación del certificado**y confirma que ha actualizado el último certificado de AppsFlyer.
   4. En **Dataflow details**, completa los detalles del conjunto de datos y del flujo de datos.
   5. Después de la implementación, regresa al **Inicio de sesión único (SSO)** , haz clic en **Confirmar implementación del certificado**y confirma que ha actualizado el último certificado de AppsFlyer.
   6. En **Scheduling**, establece la frecuencia en 60 minutos.
   7. Repite el proceso para cada reporte de Data Locker que desees.

<div id="see-also" />

> 📄 **Véase también**
>
> * <Anchor target="_blank" href="/marketers/es/docs/adobe-launch-sdk-extension?query=adobe">Extensión del SDK de Adobe Launch</Anchor>
> * <Anchor target="_blank" href="/marketers/es/docs/adobe-air-plugin?query=adobe">Plugin de Adobe Air</Anchor>

<div data-zendesk-anchors="overview=visi%C3%B3n-general h_01HDNYXDFCQQBNBB6ZQQTJS189=visi%C3%B3n-general setting-up-the-integration=configuraci%C3%B3n-de-la-integraci%C3%B3n h_01HDNYXDFCEVVDS5RANQMP6K3G=configuraci%C3%B3n-de-la-integraci%C3%B3n h_01HDNZ1AS5YTK6N26PD7S7C0XF=v%C3%A9ase-tambi%C3%A9n" />
