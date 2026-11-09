---
title: 'Audiencias: usa eventos de Braze en la creación de audiencias'
metadata:
  keywords:
    - Advertisers
    - Premium Feature
    - Marketers
    - Audience Segmentation
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-neama-benhabib
    - Marketers
    - Audience Segmentation
  created_at: '2021-11-17T09:55:26Z'
  edited_at: '2026-10-06T00:17:55Z'
  id: 4411130243217
  locale: es
  section: Audiences
  section_id: 6551336428945
  url: https://support.appsflyer.com/hc/es/articles/4411130243217
---
> **At a glance:** Envía eventos de interacción de mensajes de Braze a AppsFlyer Audiences y utilízalos para definir con más precisión tus audiencias.

Al establecer una conexión entrante entre tu cuenta de Braze y AppsFlyer Audiences, traspasas los datos de eventos de participación de mensajes de Braze a Audiences. Luego puedes utilizar estos datos en <Anchor target="_blank" href="/marketers/es/docs/audiences-guide#todo-sobre-los-conjuntos-de-reglas">conjuntos de reglas</Anchor> al definir audiencias.

> 🚧 **Important**
>
> **Prerrequisitos**
>
> * Es necesario que los SDK de Braze y AppsFlyer estén integrados en tu aplicación.
> * Debes registrarte en la función **Currents** en Braze.

<div id="set-up-the-braze-incoming-connection" />

## Configurar la conexión entrante de Braze

Hay 3 pasos principales para configurar la conexión entrante de Braze:

1. [Configurar el SDK de AppsFlyer](/docs/audiences-use-braze-events-in-audience-creation#set-up-the-appsflyer-sdk)
2. [Crear una conexión entrante en AppsFlyer](/docs/audiences-use-braze-events-in-audience-creation#create-an-incoming-braze-connection-in-appsflyer)
3. [Crear una Current en Braze](/docs/audiences-use-braze-events-in-audience-creation#create-a-current-in-braze)

<Accordion title="Configurar el SDK de AppsFlyer">

Para crear una conexión entrante desde Braze, el SDK de AppsFlyer en tus aplicaciones debe estar configurado para pasar el **ID Externo de Braze** de cada usuario a AppsFlyer. Puedes hacerlo utilizando cualquiera de las dos opciones siguientes:

* Parámetro ID externo de Braze
* Campo CUID

<div id="using-a-braze-external-id-parameter" />

#### **Uso de un parámetro ID Externo de Braze**

Puedes configurar un parámetro específico para pasar el ID Externo de Braze a AppsFlyer con la función `setPartnerData` del SDK de AppsFlyer. A continuación, ejemplos de uso:

<Tabs>
<Tab title="Android">

```java
Map<String, Object> brazeData = new HashMap<>();
brazeData.put("external_user_id", "some-braze-external-id-value");
AppsFlyerLib.getInstance().setPartnerData("braze_int", brazeData);
```

</Tab>

<Tab title="apps de iOS,">

```objectivec
NSDictionary *brazeInfo = @{
@"external_user_id":@"some-braze-external-id-value"
};
[[AppsFlyerLib shared] setPartnerDataWithPartnerId:@"braze_int"
partnerInfo:brazeInfo];
```

</Tab>
</Tabs>

<div id="using-the-cuid-field" />

#### **Uso del campo CUID**

No es necesario configurar un parámetro dedicado para el ID Externo de Braze si:

* Has configurado el SDK para enviar a AppsFlyer un <Anchor target="_blank" href="/marketers/es/docs/customer-user-id-field-cuid">CUID</Anchor> para cada usuario
* El CUID tiene el mismo valor que el ID externo de Braze External.

En este caso, simplemente puedes seleccionar la **opción CUID** como parámetro del SDK al [crear tu conexión entrante de Braze](/docs/audiences-use-braze-events-in-audience-creation#create-an-incoming-braze-connection-in-appsflyer).

</Accordion>

<Accordion title="Crear una conexión entrante de Braze en AppsFlyer">

**Sigue estos pasos para crear una conexión entrante en AppsFlyer:**

1. En AppsFlyer, en el menú lateral, selecciona **Engage** > **Audiencias**
2. En la página de Audiencias, ve a la **pestaña** **Conexiones > Entrantes**.
3. Haz clic en el botón **Nueva conexión entrante**.
4. Selecciona Braze de la lista de socios disponibles.
5. Haz clic en el botón **Guardar** para crear la conexión.  
   Se abre el cuadro de diálogo **Credenciales de conexión**.
6. Copia las credenciales de conexión para usarlas al configurar la conexión a AppsFlyer Audiences en la plataforma de Braze:
   * ID de clave de acceso
   * Clave de acceso secreta
   * Nombre del bucket
   * Ruta de la carpeta
7. Selecciona el parámetro SDK que usas para enviar el ID externo de Braze:
   * ID externo de Braze
   * CUID

</Accordion>

<Accordion title="Crear una Current en Braze">

**Sigue estos pasos para crear un Current en Braze:**

1. Ve a la sección **Integración** en la barra de menú lateral izquierda.
2. Haz clic en **Currents.**
3. Haz clic en el botón **Crear Current**.
4. Selecciona **Exportación de datos de Amazon S3.**
5. En la sección **Crear integración de Currents**:
   1. Introduce un nombre para el Current (por ejemplo, AppsFlyer Audiences).
   2. Introduce el correo electrónico de un miembro de tu equipo para que Braze le notifique en caso de problemas con las credenciales del Current.
6. En la sección de **Credenciales**:
   1. Mantén seleccionada la opción **Clave de acceso secreta de AWS** (es el valor predeterminado).
   2. Ingresa las credenciales que copiaste de AppsFlyer en los campos correspondientes.
   3. Deja desmarcada la opción **Habilitar cifrado**.
7. En **Configuración general**, mantén marcada la opción **Incluir eventos de usuarios anónimos**.
8. En la sección **Eventos de engagement de mensajes**, selecciona los eventos que quieres que Braze envíe a AppsFlyer. Consulta la lista de eventos compatibles [a continuación](/docs/audiences-use-braze-events-in-audience-creation#eventos-admitidos).
9. En la sección Comportamiento del cliente y eventos del usuario, mantén desactivada la opción **Track Customer Behavior and User Events**.
10. Haz clic en el botón **Launch Current** para guardar la configuración y empezar a enviar eventos de engagement de mensajes de Braze a audiencias.

<div id="supported-events" />

#### eventos admitidos

> 📘 **Note**
>
> **Eventos de Braze compatibles**
>
> * Cambio de Estado del Grupo de Suscripción
> * Clic en Email
> * Apertura de Email
> * Envío de Email
> * Entrega de Email
> * Marcar Email como Spam
> * Cancelar Suscripción de Email
> * Rebote de Email
> * Rebote Suave de Email
> * Apertura de Push
> * Envío de Push
> * Rebote de Push
> * Push en Primer Plano de iOS
> * Envío de SMS/MMS

</Accordion>

<div id="using-braze-data-in-audiences" />

## Uso de Datos de Braze en Audiencias

Una vez que se configure la conexión entrante de Braze, los eventos de engagement que hayas definido aparecerán como opciones en los <Anchor target="_blank" href="/marketers/es/docs/audiences-guide#ruleset-filters">filtros del conjunto de reglas</Anchor> para definir audiencias.

<Image align="center" alt="audiences_braze_ruleset.png" src="https://files.readme.io/766a5ec25de3cf82c1411ce25864a5c8ce6c77ac338c20699e61be1c45ae3d98-33375723752337.png" />

**Nota:** Los eventos de engagement de mensajes de Braze tardan aproximadamente 24 horas en estar disponibles en AppsFlyer después de lanzar el current en Braze.

<div data-zendesk-anchors="set-up-the-braze-incoming-connection=configurar-la-conexi%C3%B3n-entrante-de-braze h_01HKW0BS5H1ANWAJZTVBWDQHJH=configurar-la-conexi%C3%B3n-entrante-de-braze using-a-braze-external-id-parameter=uso-de-un-par%C3%A1metro-id-externo-de-braze h_01HKW0BS5HGB2RYGWNXT1M163C=uso-de-un-par%C3%A1metro-id-externo-de-braze using-the-cuid-field=uso-del-campo-cuid h_01HKW0BS5HQJZRR60VKBCWGHQB=uso-del-campo-cuid supported-events=eventos-admitidos h_01HKW0BS5JM8A9XFVX22KWFE3H=eventos-admitidos using-braze-data-in-audiences=uso-de-datos-de-braze-en-audiencias h_01HKW0BS5JTZQ71HFE305ZT1CS=uso-de-datos-de-braze-en-audiencias" />
