---
title: Integración de TUNE con AppsFlyer
metadata:
  keywords:
    - Advertisers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2021-08-25T08:58:17Z'
  edited_at: '2026-08-12T12:16:22Z'
  id: 4406153487505
  locale: es
  section: Ad network configuration guides (R-Z)
  section_id: 6552025468305
  url: https://support.appsflyer.com/hc/es/articles/4406153487505
---
> **Resumen:** TUNE, un partner integrado de AppsFlyer, es una plataforma de marketing para partners.  
> Intégrate con TUNE para medir el tráfico entrante y habilitar el Deep Linking en tu aplicación.

<Image alt="" src="https://cdn.appsflyer.com/marketplace/static/logo/hasoffers.png" width="79px" />

## Configuración de la integración con TUNE

La integración de AppsFlyer con TUNE ofrece atribución de clic.

**Requisito previo:** Antes de configurar la integración, asegúrate de ponerte en contacto con el partner y abrir una cuenta con ellos.

**Configura la integración:**

1. En la pestaña de **Integración** selecciona la aplicación para la integración y haz clic en **Activar partner**  
   **Nota:** El selector debe estar encendido <Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">(activado) mientras</Anchor> trabajes con el partner.
2. Selecciona la aplicación correspondiente.
3. Busca Tune y selecciona **Integrar**.
4. En la pestaña de **Integración** selecciona la aplicación para la integración y haz clic en **Activar partner**  
   **Nota:** El selector debe estar encendido<Anchor target="_blank" href="/marketers/es/docs/partner-activation-deactivation">(activado) mientras</Anchor> trabajes con el partner. Mantenlo activado mientras trabajes con Tune.
5. Configura las pestañas restantes según sea necesario a continuación.

| Pestaña de configuración | Nota |
| --- | --- |
| **Integración** | Configura la <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner">integración</Anchor> con opciones adicionales según sea necesario.<br /><br />El campo Custom\_TUNE\_tracking\_domain se usa para crear la URL de endpoint específica. Por ejemplo, si introduces "**greatapp**", tu URL de endpoint será:  <br />https://greatapp.go2cloud.org/aff_Isr?<br /><br />Usa el mismo nombre para el dominio de tracking personalizado de los eventos in-app. |
| **Enlace de atribución** | Genera <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#attribution-link-tab">enlaces de atribución.</Anchor> |
| **Coste** | Obtén <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#cost-tab">datos de costo</Anchor>. |
| **Cadena** | No disponible para este partner |
| **Permisos** | Configura los <Anchor target="_blank" href="/marketers/es/docs/set-up-an-integrated-partner#permissions-tab">permisos</Anchor> de la ad network según sea necesario. |

**Para activar o editar la integración:**

Busca al partner y selecciónalo.

## Habilitar el Deep Linking en tu aplicación

Usa <Anchor target="_blank" href="/marketers/es/docs/brand-onelink-with-your-domain">enlaces de marca de OneLink</Anchor> generados en AppsFlyer para medir clics en TUNE. El siguiente proceso permite hacer Deep Linking de los usuarios a una página específica de tu aplicación.

### Requisitos previos

Verifica  las versiones del SDK móvil de AppsFlyer:

* iOS: V4.9.0 o posterior
* Android: V4.9.0 o posterior

### Paso 1: Configura enlaces para tus campañas

* Crea una <Anchor target="_blank" href="/marketers/es/docs/create-a-onelink-template#crear-una-plantilla-de-onelink">plantilla de OneLink</Anchor> para tus campañas de correo electrónico.
* <Anchor target="_blank" href="/marketers/es/docs/brand-onelink-with-your-domain">Crea un enlace de marca.</Anchor>  
  Cuando se te pida que añadas un CNAME a tu dominio, usa `yourdomain.esplinks.appsflyer.com` en lugar de la URL que se ofrece en la página de creación del enlace de marca.  
  **Ejemplo:**
  * **Subdominio:** `click.example.com`
  * **CNAME:** `example.appsflyer.com`

    ![enlace-de-marca-esp-nuevo-es_es.png](https://files.readme.io/a7433ac0e3b343195bac9b4be49d22c18534ec1c145189198c5ec467fea510bb-21323417936145.png)

    Ten en cuenta que, al hacer clic en **Verificar** para verificar el dominio de marca, se muestra un mensaje de error relacionado con el CNAME de AppsFlyer.

    ![enlace-de-marca-esp-mensaje-error-cname.png](https://files.readme.io/94f159a089152437111fc6e4308464bc48512ee18f5e249460006bfda05252c2-21323447961105.png)

    Ignora este mensaje y cambia el CNAME tal como se indica arriba.

### Paso 2: Configura el enlace de atribución

1. Ve a la pestaña Enlace de atribución y copia únicamente los parámetros del enlace en **Click attribution link** , tal como se resalta a continuación.[![](https://files.readme.io/51bb21c2fe4bd82965f30909fe5ed4ae6c5b906972789b143755982ea8b73f6e-4406164987537.png)](https://files.readme.io/51bb21c2fe4bd82965f30909fe5ed4ae6c5b906972789b143755982ea8b73f6e-4406164987537.png)
2. Añade los parámetros copiados a tu enlace de marca.

   > 📄 **Ejemplo:**
   >
   > ![TUNE-enlace-ejemplo2-es_es.png](https://files.readme.io/58f38eb0bb724b66d0c958454651e0950a54f6fd990220f2ac24f93ca89ba344-small-4410086650769.png)

3. Para completar la configuración, ve a la <Anchor target="_blank" href="https://support.tune.com/hc/en-us/articles/1500008336641-Managing-Mobile-Offers-with-Appsflyer">guía Managing Mobile Offers with AppsFlyer</Anchor> en el centro de ayuda de TUNE, desplázate hacia abajo hasta Universal Links via OneLink y sigue las instrucciones.

<div data-zendesk-anchors="setting-up-tune-integration=configuraci%C3%B3n-de-la-integraci%C3%B3n-con-tune h_01HJZRGVZ1VQF4N93THDRT5YCJ=configuraci%C3%B3n-de-la-integraci%C3%B3n-con-tune enabling-deep-linking-into-your-app=habilitar-el-deep-linking-en-tu-aplicaci%C3%B3n h_01HJZRGVZ1KJ80ZA1THKFZ535P=habilitar-el-deep-linking-en-tu-aplicaci%C3%B3n prerequisite=requisitos-previos h_01HJZRGVZ1ZC9G7M72V2HW4XDS=requisitos-previos step-1-configure-links-for-your-campaigns=paso-1-configura-enlaces-para-tus-campa%C3%B1as h_01HJZRGVZ1GPR3NQQAXRBXV09Z=paso-1-configura-enlaces-para-tus-campa%C3%B1as step-2-set-up-the-attribution-link=paso-2-configura-el-enlace-de-atribuci%C3%B3n h_01HJZRGVZ2F83PHABEWJXMMJ22=paso-2-configura-el-enlace-de-atribuci%C3%B3n h_01HJZRGVZ2435CGWY4FZ5FKKHV=ejemplo" />
