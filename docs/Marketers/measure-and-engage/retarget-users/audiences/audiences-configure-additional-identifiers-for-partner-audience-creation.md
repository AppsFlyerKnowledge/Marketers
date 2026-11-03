---
title: >-
  Audiencias: configura identificadores adicionales para la creación de
  audiencias de Partners
metadata:
  keywords:
    - Audiences
    - Advertisers
    - Developers
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
  created_at: '2021-02-14T16:23:45Z'
  edited_at: '2026-08-22T00:34:46Z'
  id: 360017807278
  locale: es
  section: Audiences
  section_id: 6551336428945
  url: https://support.appsflyer.com/hc/es/articles/360017807278
---
> **At a glance:** Configure identificadores de usuario adicionales para enviar audiencias personalizadas a socios publicitarios.

## Acerca de los identificadores adicionales

AppsFlyer Audiences admite automáticamente los siguientes identificadores de dispositivos al enviar audiencias personalizadas a <Anchor target="_blank" href="/marketers/es/docs/audiences-partner-connections">socios publicitarios</Anchor>:

* **iOS: IDFA**
* **Android (Google Play):** GAID
* **Android (tiendas de aplicaciones de terceros):** <Anchor target="_blank" href="/marketers/es/docs/android-oaid-implementation-in-the-sdk">OAID</Anchor> y IMEI

Algunos socios publicitarios también admiten la coincidencia de audiencias personalizadas basándose en identificadores de usuario adicionales. Audiences le ofrece la opción de utilizar estos identificadores si los configura específicamente a través del SDK de AppsFlyer o la API S2S-mobile.

Estos identificadores adicionales pueden incluir números de teléfono y correos electrónicos, pero **solo se pueden utilizar si están cifrados con el hash SHA256**.  El uso de dichos identificadores adicionales está sujeto a los [Términos de uso de identificadores adicionales](https://support.appsflyer.com/hc/article_attachments/16567368205201).

## Próximos pasos

1. Seleccione los identificadores adicionales que desea utilizar (si hay alguno) de la [tabla de identificadores disponibles](/docs/audiences-configure-additional-identifiers-for-partner-audience-creation#additional-identifiers%E2%80%94parameters-and-formatting). Tenga en cuenta que no todos los socios publicitarios admiten todos los identificadores.
2. Desarrolladores—Configuren los identificadores seleccionados, utilizando:
   * Parámetros y requisitos de formato según aparecen en la [tabla de identificadores disponibles](/docs/audiences-configure-additional-identifiers-for-partner-audience-creation#additional-identifiers%E2%80%94parameters-and-formatting).
   * La referencia y los ejemplos de código para [SDK](/docs/audiences-configure-additional-identifiers-for-partner-audience-creation#referencia-del-sdk-y-ejemplos-de-código) y [S2S](/docs/audiences-configure-additional-identifiers-for-partner-audience-creation#referencia-y-ejemplos-de-código-s2s).
3. En el panel de Audiencias:
   * Establezca su <Anchor target="_blank" href="/marketers/es/docs/audiences-user-identifier-policy">política de identificadores de usuario a nivel de cuenta</Anchor>.
   * Seleccione los identificadores que se cargarán en cada una de sus <Anchor target="_blank" href="/marketers/es/docs/audiences-guide#manage-connections">conexiones de socios</Anchor>.

## Identificadores disponibles

Puede optar por configurar uno o más identificadores, que se muestran en la siguiente tabla.

<Accordion title="Identificadores adicionales — parámetros y formato">

<table><tbody><tr><td>Identificador</td><td>Nombre del parámetro</td><td>Formato</td><td>Valor de ejemplo (antes del hash)</td></tr><tr><td>Correo electrónico</td><td>correo electrónico_sha256</td><td><p><strong>SDK v7.0.0 y versiones anteriores:</strong></p><ul><li>Minúsculas</li><li>Sin espacios en blanco</li><li>Con hash en el cliente (SHA256) antes de enviarlo</li></ul><p><strong>SDK v7.0.1 y versiones posteriores:</strong> Texto sin formato. El SDK lo normaliza y aplica Hashing automáticamente.</p></td><td>name@domain.com</td></tr><tr><td>Número de teléfono<br/>(ver nota a continuación)</td><td><p><strong>v7.0.0 y versiones anteriores (o S2S):</strong> phone_number_sha256</p><p><strong>v7.0.1 y versiones posteriores:</strong> phone_number_hashed</p></td><td><p><strong>v7.0.0 y versiones anteriores (o S2S):</strong></p><ul><li>Sin símbolos, letras ni ceros iniciales</li><li>Incluir código de país</li><li>Hash SHA256</li></ul><p><strong>v7.0.1 y versiones posteriores:</strong> Texto sin formato. El SDK concatena el código de país y el número, lo normaliza y aplica Hashing automáticamente.</p></td><td>442070313000</td></tr><tr><td><p>Número de teléfono E164</p><p>(ver nota a continuación)</p></td><td><p><strong>v7.0.0 y versiones anteriores (o S2S):</strong> phone_number_e164_sha256</p><p><strong>v7.0.1 y versiones posteriores:</strong> phone_number_e164_hashed</p></td><td><p><strong>v7.0.0 y versiones anteriores (o S2S):</strong></p><ul><li>Número de teléfono E164</li><li>Hash SHA256</li></ul><p><strong>v7.0.1 y versiones posteriores:</strong> Texto sin formato. El SDK concatena el código de país y el número, lo normaliza y aplica Hashing automáticamente.</p></td><td>+442070313000</td></tr><tr><td colspan="4"><p><br /><br /><strong>Note</strong><br /></p><p><strong><span id="h_01HNZNWZ9XSY47T58Z5YR7Q65S"></span>Nota</strong></p><p>Diferentes socios publicitarios admiten distintos formatos de números de teléfono. Por tanto, si eliges usar el número de teléfono, configura ambos identificadores: <em>Número de teléfono</em> y <em>Número de teléfono E164</em></p></td></tr></tbody></table>

</Accordion>

## Referencia del SDK y ejemplos de código

Al enviar identificadores para audiencias mediante el SDK:

* Para identificadores distintos de la dirección de correo electrónico codificada , use
* Para la dirección de correo electrónico codificada , use
  * SDK v7.0.1 y versiones posteriores: usa `setUserEmail`.
  * SDK v7.0.0 y versiones anteriores: usa `setUserEmails`.
* número de teléfono e164\_sha256
  * SDK v7.0.1 y versiones posteriores: usa `setUserPhone` (recomendado).
  * SDK v7.0.0 y versiones anteriores: usa `setAdditionalData` con datos personalizados.

> 📘 **Note**
>
> **Advertencia**
>
> Recuerda los siguientes cambios según la versión:
>
> * **Correo electrónico:** A partir del SDK v7.0.1, setUserEmails (iOS/Android) se ha eliminado por completo y se ha sustituido por setUserEmail. Este es un cambio incompatible, no una descontinuación. Las apps en v7.0.0 y anteriores deben seguir usando setUserEmails. Las apps en v7.0.1 y posteriores deben cambiar a setUserEmail. Comprueba qué versión del SDK tienes integrada antes de elegir qué ejemplo seguir.
> * **Teléfono:** A partir del SDK v7.0.1, hay disponible una API específica setUserPhone. Es la forma recomendada de enviar identificadores de número de teléfono para Advanced Matching. Este no es un cambio disruptivo: setAdditionalData sigue funcionando. Para las nuevas integraciones y para los clientes que actualicen a la versión 7.0.1 y posteriores, recomendamos migrar a setUserPhone. Las aplicaciones con la versión 7.0.0 y anteriores deben seguir usando setAdditionalData, porque setUserPhone no existe en esas versiones del SDK.

## Configuración del SDK para iOS

Para establecer el *número de teléfono* con hashing como identificador adicional de usuario:

### **SDK v7.0.0 y anteriores — setAdditionalData**

<Tabs>
<Tab title="Objective-C">

```objectivec
NSDictionary *customData = @{
  @"audiences": @{
    @"phone_number_sha256": @"6C91C4C640F6EF0162833260DB4F13DEC0DF2B683092F4DBA7E874BEF1ACEA37",
    @"phone_number_e164_sha256":@"F3D7E96C73FB0DE1B66ACFCE541D7AF758FBD4F3FA3AF0EA4E10110000D3625E"
  }
};
[[AppsFlyerLib shared] setAdditionalData:customData];
```

</Tab>

<Tab title="Swift">

```swift
número de teléfono_sha256
```

</Tab>
</Tabs>

> 📘 **Note**
>
> **Audiencias: identificadores adicionales**
>
> Debes aplicar un hash previo a ambos valores (SHA-256) antes de pasarlos.

### **SDK v7.0.1 y versiones posteriores — setUserPhone (recomendado)**

#### Firma del método

```objectivec
- (void)setUserPhone:(NSString *_Nonnull)countryCode
phoneNumber:(NSString *_Nonnull)phoneNumber;
```

#### Ejemplo de uso

<Tabs>
<Tab title="Objective-C">

```objectivec
[[AppsFlyerLib shared] setUserPhone:@"1" phoneNumber:@"(650) 555-1212"];
```

</Tab>

<Tab title="Swift">

```swift
AppsFlyerLib.shared().setUserPhone(countryCode: "1", phoneNumber: "(650) 555-1212")
```

</Tab>
</Tabs>

> 📘 **Note**
>
> **Hash SHA256**
>
> Pasa el prefijo telefónico del país y el número local como texto sin formato. Se permiten símbolos y espacios en el número local. El SDK concatena, normaliza y aplica hash a ambos valores localmente (SHA-256). No apliques hash previamente.

Para establecer una dirección de correo electrónico codificada como un identificador de usuario adicional:

### **SDK v7.0.0 y versiones anteriores**

#### Firma del método

```objectivec
- (void)setUserEmails:(NSArray<NSString *> *_Nullable)userEmails 
withCryptType: (EmailCryptType)type;
```

#### Ejemplo de uso

<Tabs>
<Tab title="Objective-C">

```objectivec
NSArray *emails = @[@"name@domain.com"];    
[[AppsFlyerLib shared] setUserEmails:emails withCryptType: EmailCryptTypeSHA256];
```

</Tab>

<Tab title="Swift">

```swift
let emails: Array = ["name@domain.com"]
AppsFlyerLib.shared().setUserEmails(emails, with: EmailCryptTypeSHA256)
```

</Tab>
</Tabs>

### **SDK v7.0.1 y versiones posteriores**

#### Firma del método

```objectivec
- (void)setUserEmail:(NSString *_Nonnull)email;
```

#### Ejemplo de uso

<Tabs>
<Tab title="Objective-C">

```objectivec
[[AppsFlyerLib shared] setUserEmail:@"name@domain.com"];
```

</Tab>

<Tab title="Swift">

```swift
AppsFlyerLib.shared().setUserEmail("name@domain.com")
```

</Tab>
</Tabs>

> 📘 **Note**
>
> **Advertencia**
>
> Pasa el correo electrónico en texto sin formato. El SDK lo normaliza y aplica hashing localmente (SHA-256). No apliques hashing previamente. Solo se acepta un único correo electrónico por llamada: si vuelves a llamar a setUserEmail, se sobrescribe el valor establecido anteriormente en lugar de añadirse.

## Configuración del SDK para Android

Para establecer un *número de teléfono* codificado como identificador de usuario adicional:

### **SDK v7.0.0 y versiones anteriores — setAdditionalData**

<Tabs>
<Tab title="Java">

```java
HashMap<String, Object> audiences = new HashMap<>();
audiences.put("phone_number_sha256", "6C91C4C640F6EF0162833260DB4F13DEC0DF2B683092F4DBA7E874BEF1ACEA37");
audiences.put("phone_number_e164_sha256", "F3D7E96C73FB0DE1B66ACFCE541D7AF758FBD4F3FA3AF0EA4E10110000D3625E");
HashMap<String, Object> customDataMap = new HashMap<>();
customDataMap.put("audiences", audiences);
AppsFlyerLib.getInstance().setAdditionalData(customDataMap);
```

</Tab>

<Tab title="Kotlin">

```kotlin
val audiences = hashMapOf<String, Any>(
   "phone_number_sha256" to "6C91C4C640F6EF0162833260DB4F13DEC0DF2B683092F4DBA7E874BEF1ACEA37",
   "phone_number_e164_sha256" to "F3D7E96C73FB0DE1B66ACFCE541D7AF758FBD4F3FA3AF0EA4E10110000D3625E"
)
val customDataMap = hashMapOf<String, Any>("audiences" to audiences)
AppsFlyerLib.getInstance().setAdditionalData(customDataMap)
```

</Tab>
</Tabs>

> 📘 **Note**
>
> **Advertencia**
>
> Debes aplicar hashing previamente a ambos valores (SHA-256) antes de pasarlos.

### **SDK v7.0.1 y versiones posteriores — setUserPhone (recomendado)**

#### Firma del método

```java
public abstract void setUserPhone(String countryCode, String phoneNumber);
```

#### Ejemplo de uso

<Tabs>
<Tab title="Java">

```java
AppsFlyerLib.getInstance().setUserPhone("1", "(650) 555-1212");
```

</Tab>

<Tab title="Kotlin">

```java
AppsFlyerLib.getInstance().setUserPhone("1", "(650) 555-1212")
```

</Tab>
</Tabs>

> 📘 **Note**
>
> **Nota:**
>
> Pasa el código de marcación del país y el número local en texto sin formato. El SDK concatena, normaliza y aplica hashing a ambos valores localmente (SHA-256). No les apliques hashing previamente.

Para establecer una dirección de correo electrónico codificada como un identificador de usuario adicional:

### **SDK v7.0.0 y versiones anteriores**

#### Firma del método

```java
public abstract void setUserEmails(
  AppsFlyerProperties. EmailsCryptType cryptMethod,
  String... emails
);
```

#### Ejemplo de uso

<Tabs>
<Tab title="Java">

```java
AppsFlyerLib.getInstance().setUserEmails(
  AppsFlyerProperties.EmailsCryptType.SHA256,
  "name@domain.com",
  "another_name@another_domain.com"
);
```

</Tab>

<Tab title="Kotlin">

```java
AppsFlyerLib.getInstance().setUserEmails(
  AppsFlyerProperties.EmailsCryptType.SHA256,
  "name@domain.com",
  "another_name@another_domain.com"
);
```

</Tab>
</Tabs>

### **SDK v7.0.1 y versiones posteriores**

#### Firma del método

```java
public abstract void setUserEmail(String email);
```

#### Ejemplo de uso

```java
AppsFlyerLib.getInstance().setUserEmail("name@domain.com");
```

> 📘 **Note**
>
> **Nota:**
>
> Solo se acepta un único correo electrónico por llamada en la versión 7.0.1 y posteriores. No se admiten varios correos electrónicos: si vuelves a llamar a setUserEmail, se sobrescribe el valor establecido anteriormente en lugar de añadirse.

## Referencia y ejemplos de código S2S

Al enviar identificadores para audiencias mediante <Anchor target="_blank" href="/marketers/es/docs/server-to-server-events-api-for-mobile-s2s-mobile">S2S</Anchor>, use el parámetro <Anchor target="_blank" href="/marketers/es/docs/server-to-server-events-api-for-mobile-s2s-mobile">para **todos los identificadores (incluyendo la dirección de correo electrónico codificada ).** Puede enviar uno o más identificadores.</Anchor>

<Accordion title="Envío de identificadores vía S2S">

Formato:

* JSON anidado
* El valor de la clave debe ser `audiences`
* Todos los valores deben estar en formato cadena, como se muestra en el siguiente ejemplo de código
* Los nombres de los parámetros deben coincidir con los listados en la [tabla de identificadores disponibles](/docs/audiences-configure-additional-identifiers-for-partner-audience-creation#additional-identifiers%E2%80%94parameters-and-formatting) indicada arriba

Formato genérico:

```json
"custom_data" : {   
      \"audiences\" : { 
          \"parameter_name_a\" : \"hashed_identifer_a\",
          \"parameter_name_a\" : \"hashed_identifer_b\",
          \"parameter_name_c\" : \"hashed_identifer_c\" 
       }
 }
```

Ejemplo con valores para el *número de teléfono* codificado y la *dirección de correo electrónico* codificada:

```json
"custom_data" : {  
     \"audiences\" : { 
         \"phone_number_sha256\" : \"6C91C4C640F6EF0162833260DB4F13DEC0DF2B683092F4DBA7E874BEF1ACEA37\",
         \"phone_number_e164_sha256\" : \"F3D7E96C73FB0DE1B66ACFCE541D7AF758FBD4F3FA3AF0EA4E10110000D3625E\",
         \"email_sha256\"         : \"34D31BE18022626DE6B311D6A76E791176D2691B6EEF406F524D8F56364C187A\"
     }
}
```

</Accordion>

> 📘 **Note**
>
> **Véase también**
>
> * Conexiones de partners de audiencias
> * Política de identificador de usuario de Audiencias

<div data-zendesk-anchors="background=acerca-de-los-identificadores-adicionales h_01HNZNWZ9WVH11NG94P5YX5CE0=acerca-de-los-identificadores-adicionales next-steps=pr%C3%B3ximos-pasos h_01HNZNWZ9WYWFE1TTS3CWEBS8N=pr%C3%B3ximos-pasos available-identifiers=identificadores-disponibles h_01HNZNWZ9XG5P67Y8P08JGFWFD=identificadores-disponibles sdk-reference-and-code-samples=referencia-del-sdk-y-ejemplos-de-c%C3%B3digo h_01HNZNWZ9X0N0D3EF9HJ76EVNJ=referencia-del-sdk-y-ejemplos-de-c%C3%B3digo ios-sdk-configuration=configuraci%C3%B3n-del-sdk-para-ios h_01HNZNWZ9XCZFWA7H8BN6J6485=configuraci%C3%B3n-del-sdk-para-ios sdk-v700-and-earlier-%E2%80%94-setadditionaldata=sdk-v700-y-anteriores--setadditionaldata h_01KZXZHJZCZ8XNS5Z5JQFGABEJ=sdk-v700-y-anteriores--setadditionaldata sdk-v701-and-later-%E2%80%94-setuserphone-recommended=sdk-v701-y-versiones-posteriores--setuserphone-recomendado h_01KZXZHSF8PCN9A4425217F4YP=sdk-v701-y-versiones-posteriores--setuserphone-recomendado method-signature=firma-del-m%C3%A9todo h_01KZXZF3GX0HSY4BFYX4N4BTHD=firma-del-m%C3%A9todo usage-example=ejemplo-de-uso h_01KZXZF3GXN55TJ078CJKMJGSY=ejemplo-de-uso sdk-v700-and-earlier=sdk-v700-y-versiones-anteriores h_01KZXZJ3MEQPEJ73798RY3S3R9=sdk-v700-y-versiones-anteriores method-signature::a8fd9cf9=firma-del-m%C3%A9todo-1 h_01KZXZF3GX62EV1TTA689CK59F=firma-del-m%C3%A9todo-1 usage-example::5a156aca=ejemplo-de-uso-1 h_01KZXZF3GXB5VHHYT3SJ60F94V=ejemplo-de-uso-1 sdk-v701-and-later=sdk-v701-y-versiones-posteriores h_01KZXZJ98R1274HPDM9T4RTYDP=sdk-v701-y-versiones-posteriores method-signature::6246e0dd=firma-del-m%C3%A9todo-2 h_01KZXZF3GX9R7J1VF0ZFMJKN4Q=firma-del-m%C3%A9todo-2 usage-example::b5bfcf61=ejemplo-de-uso-2 h_01KZXZF3GXQ22XRNRP1H0TX1HG=ejemplo-de-uso-2 android-sdk-configuration=configuraci%C3%B3n-del-sdk-para-android h_01HNZNWZ9XAF2K6213ZMMGKQ7T=configuraci%C3%B3n-del-sdk-para-android sdk-v700-and-earlier-%E2%80%94-setadditionaldata::6dbf5d0c=sdk-v700-y-versiones-anteriores--setadditionaldata h_01KZXZJGMVJQAH5XC1BPJS1DGD=sdk-v700-y-versiones-anteriores--setadditionaldata sdk-v701-and-later-%E2%80%94-setuserphone-recommended::1b63a185=sdk-v701-y-versiones-posteriores--setuserphone-recomendado-1 h_01KZXZJX109FSKCCRPVAA1W2Y2=sdk-v701-y-versiones-posteriores--setuserphone-recomendado-1 method-signature::bf39fa28=firma-del-m%C3%A9todo-3 h_01KZXZF3GX3Q6MZX5KXQJSANVK=firma-del-m%C3%A9todo-3 usage-example::1515fa60=ejemplo-de-uso-3 h_01KZXZF3GXSXDP4BBFWM7WZ74M=ejemplo-de-uso-3 sdk-v700-and-earlier::5989d839=sdk-v700-y-versiones-anteriores-1 h_01KZXZK2H50HJVZKF65H59XVXY=sdk-v700-y-versiones-anteriores-1 method-signature::9b0b0248=firma-del-m%C3%A9todo-4 h_01KZXZF3GXZXD09H3T922TGM7N=firma-del-m%C3%A9todo-4 usage-example::2bb38341=ejemplo-de-uso-4 h_01KZXZF3GXB7V1YK1584H0NW1G=ejemplo-de-uso-4 sdk-v701-and-later::16b1fdb1=sdk-v701-y-versiones-posteriores-1 h_01KZXZK8EXXVDY8P4TR2418FXH=sdk-v701-y-versiones-posteriores-1 method-signature::852458c4=firma-del-m%C3%A9todo-5 h_01KZXZF3GXX4S3P8SE4SBY6WZ2=firma-del-m%C3%A9todo-5 usage-example::11baa27a=ejemplo-de-uso-5 h_01KZXZF3GXM9Q0MQNX2ASEZ2BJ=ejemplo-de-uso-5 s2s-reference-and-code-samples=referencia-y-ejemplos-de-c%C3%B3digo-s2s h_01HNZNWZ9XKM53TJ9Z0FHWGCYC=referencia-y-ejemplos-de-c%C3%B3digo-s2s" />
