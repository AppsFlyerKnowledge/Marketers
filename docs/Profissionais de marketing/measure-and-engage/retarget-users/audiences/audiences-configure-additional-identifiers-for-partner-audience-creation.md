---
title: >-
  Audiências – Configure identificadores adicionais para a criação de audiências
  de parceiros
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
  edited_at: '2026-08-19T00:35:05Z'
  id: 360017807278
  locale: pt
  section: Audiences
  section_id: 6551336428945
  url: https://support.appsflyer.com/hc/pt/articles/360017807278
---
> **At a glance:** **Visão geral:** Configure identificadores de utilizador adicionais para enviar audiências personalizadas aos seus parceiros de publicidade.

## Sobre os identificadores adicionais

O AppsFlyer Audiences suporta automaticamente os seguintes identificadores de dispositivos para envio de audiências personalizadas a <Anchor target="_blank" href="/marketers/pt/docs/audiences-partner-connections">parceiros de publicidade</Anchor>:

* **iOS: IDFA**
* **Android (Google Play):** GAID
* **Android (lojas de aplicações de terceiros):** <Anchor target="_blank" href="/marketers/pt/docs/android-oaid-implementation-in-the-sdk">OAID</Anchor> e IMEI

Alguns parceiros de publicidade também permitem a correspondência de audiências personalizadas com base em identificadores de utilizador adicionais. O Audiences oferece-lhe a opção de utilizar estes identificadores, se forem configurados especificamente através do SDK da AppsFlyer ou da API S2S-mobile.

Estes identificadores adicionais podem incluir números de telefone e e-mails, sendo que só podem **ser usados se encriptados com hash SHA256**.  A utilização desses identificadores adicionais está sujeita aos [Termos de Utilização de Identificadores Adicionais](https://support.appsflyer.com/hc/article_attachments/16567368205201).

## Próximos passos

1. Selecione os identificadores adicionais que deseja usar (se houver) a partir da [tabela de identificadores disponíveis](/docs/audiences-configure-additional-identifiers-for-partner-audience-creation#additional-identifiers%E2%80%94parameters-and-formatting). Tenha em atenção que nem todos os parceiros de publicidade suportam todas as opções de identificadores.
2. Programadores—Configure os identificadores selecionados, utilizando:
   * Os parâmetros e requisitos de formatação apresentados na [tabela de identificadores disponíveis](/docs/audiences-configure-additional-identifiers-for-partner-audience-creation#additional-identifiers%E2%80%94parameters-and-formatting)
   * As referências e amostras de código para [SDK](/docs/audiences-configure-additional-identifiers-for-partner-audience-creation#referência-do-sdk-e-exemplos-de-código) e [S2S](/docs/audiences-configure-additional-identifiers-for-partner-audience-creation#referência-s2s-e-exemplos-de-código)
3. No painel de Audiências:
   * Defina a sua <Anchor target="_blank" href="/marketers/pt/docs/audiences-user-identifier-policy">política de identificadores de utilizador a nível da conta</Anchor>
   * Selecione os identificadores a serem carregados em cada uma das suas <Anchor target="_blank" href="/marketers/pt/docs/audiences-guide#manage-connections">conexões de parceiros</Anchor>

## Identificadores disponíveis

Pode optar por configurar um ou mais identificadores, listados na tabela abaixo.

<Accordion title="Identificadores adicionais — parâmetros e formatação">

<table><tbody><tr><td>Identificador</td><td>Nome do parâmetro</td><td>Formato</td><td>Valor de exemplo (antes da aplicação de hash)</td></tr><tr><td>Endereço de email</td><td>email_sha256</td><td><p><strong>SDK v7.0.0 e anteriores:</strong></p><ul><li>Minúscula</li><li>Sem espaços</li><li>Aplicar hash no cliente (SHA256) antes de enviar</li></ul><p><strong>SDK v7.0.1 e posteriores:</strong> Texto simples. O SDK normaliza e aplica hash automaticamente.</p></td><td>name@domain.com</td></tr><tr><td>Número de telefone<br/>(ver nota abaixo)</td><td><p><strong>v7.0.0 e anteriores (ou S2S):</strong> phone_number_sha256</p><p><strong>v7.0.1 e posteriores:</strong> phone_number_hashed</p></td><td><p><strong>v7.0.0 e anteriores (ou S2S):</strong></p><ul><li>Sem símbolos, letras ou zeros iniciais</li><li>Inclua o código do país</li><li>Com hash SHA256</li></ul><p><strong>v7.0.1 e posteriores:</strong> Texto simples. O SDK concatena o código do país e o número, normaliza e aplica hash automaticamente.</p></td><td>442070313000</td></tr><tr><td><p>Número de telefone E164</p><p>(ver nota abaixo)</p></td><td><p><strong>v7.0.0 e anteriores (ou S2S):</strong> phone_number_e164_sha256</p><p><strong>v7.0.1 e posteriores:</strong> phone_number_e164_hashed</p></td><td><p><strong>v7.0.0 e anteriores (ou S2S):</strong></p><ul><li>Número de telefone E164</li><li>Com hash SHA256</li></ul><p><strong>v7.0.1 e posteriores:</strong> Texto simples. O SDK concatena o código do país e o número, normaliza e aplica hash automaticamente.</p></td><td>+442070313000</td></tr><tr><td colspan="4"><p><br /><br /><strong>Note</strong><br /></p><p><strong><span id="h_01HNZNWZ9XSY47T58Z5YR7Q65S"></span>numero_telefone_sha256</strong></p><p>Diferentes parceiros de publicidade aceitam diferentes formatos de número de telefone. Portanto, se optar por usar o número de telefone, configure ambos os identificadores: <em>Número de telefone</em> e <em>Número de telefone E164.</em></p></td></tr></tbody></table>

</Accordion>

## Referência do SDK e exemplos de código

Ao enviar identificadores para Públicos através do SDK:

* Para identificadores que não sejam *Endereço de e-mail* com hash, utilize
* Para *Endereço de e-mail* com hash, use
  * SDK v7.0.1 e posteriores: use `setUserEmail`.
  * SDK v7.0.0 e anteriores: use `setUserEmails`.
* numero\_telefone\_e164\_sha256
  * SDK v7.0.1 e posteriores: use `setUserPhone` (recomendado).
  * SDK v7.0.0 e anteriores: use `setAdditionalData` com dados personalizados.

> 📘 **Note**
>
> **Atenção**
>
> Lembre-se das seguintes mudanças dependentes da versão:
>
> * **E-mail:** A partir do SDK v7.0.1, `setUserEmails` (iOS/Android) foi totalmente removido e substituído por `setUserEmail`. Esta é uma mudança incompatível, não uma descontinuação. Apps na v7.0.0 e anteriores devem continuar a usar `setUserEmails`. Apps na v7.0.1 e posteriores devem mudar para `setUserEmail`. Verifique a versão integrada do SDK antes de escolher qual exemplo seguir.
> * **Telefone:** A partir do SDK v7.0.1, está disponível uma API dedicada `setUserPhone`. Esta é a forma recomendada de enviar identificadores de números de telefone para Advanced Matching. Esta não é uma mudança incompatível: `setAdditionalData` ainda funciona. Para novas integrações e para clientes que atualizarem para v7.0.1 e posterior, recomendamos migrar para `setUserPhone`. Aplicativos na v7.0.0 e versões anteriores devem continuar usando `setAdditionalData`, porque `setUserPhone` não existe nessas versões do SDK.

## Configuração do SDK para iOS

Para definir o *Número de telefone* com hash como um identificador de utilizador adicional:

### **SDK v7.0.0 e anteriores — setAdditionalData**

<Tabs>
<Tab title="Objetivo-C">

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
SDK v7.0.0 e anteriores — setAdditionalData
```

</Tab>
</Tabs>

> 📘 **Note**
>
> **Atenção**
>
> Você deve aplicar hash previamente aos dois valores (SHA-256) antes de passá-los.

### **SDK v7.0.1 e posteriores — setUserPhone (recomendado)**

#### Audiências — identificadores adicionais

```objectivec
- (void)setUserPhone:(NSString *_Nonnull)countryCode
phoneNumber:(NSString *_Nonnull)phoneNumber;
```

#### Exemplo de utilização

<Tabs>
<Tab title="Objetivo-C">

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
> **Atenção**
>
> Passe o código de discagem do país e o número local como texto simples. Símbolos e espaços são permitidos no número local. O SDK concatena, normaliza e aplica hash aos dois valores localmente (SHA-256). Não aplique hash previamente.

Para definir um *Endereço de e-mail* com hash como um identificador de utilizador adicional:

### **SDK v7.0.0 and earlier**

#### Audiências — identificadores adicionais

```objectivec
- (void)setUserEmails:(NSArray<NSString *> *_Nullable)userEmails 
withCryptType:(EmailCryptType)type;
```

#### Exemplo de utilização

<Tabs>
<Tab title="Objetivo-C">

```objectivec
NSArray *emails = @[@"name@domain.com"];    
[[AppsFlyerLib shared] setUserEmails:emails withCryptType:EmailCryptTypeSHA256];
```

</Tab>

<Tab title="Swift">

```swift
let emails: Array = ["name@domain.com"]
AppsFlyerLib.shared().setUserEmails(emails, with: EmailCryptTypeSHA256)
```

</Tab>
</Tabs>

### **SDK v7.0.1 and later**

#### Assinatura de método

```objectivec
- (void)setUserEmail:(NSString *_Nonnull)email;
```

#### Exemplo de utilização

<Tabs>
<Tab title="Objetivo-C">

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
> **Nota**
>
> Passe o e-mail em texto simples. O SDK o normaliza e faz o hashing localmente (SHA-256). Não aplique hash previamente. Apenas um único e-mail é aceito por chamada: chamar `setUserEmail` novamente substitui o valor definido anteriormente em vez de adicioná-lo.

## Configuração do SDK para Android

Para definir o *Número de telefone* com hash como um identificador de utilizador adicional:

### **SDK v7.0.0 e anteriores — setAdditionalData**

<Tabs>
<Tab title="Java">

```java
HashMap<String, Object> audiences = new HashMap<>();
audiences.put("phone_number_sha256", "6C91C4C640F6EF0162833260DB4F13DEC0DF2B683092F4DBA7E874BEF1ACEA37");
audiences.put("phone_number_e164_sha256", "F3D7E96C73FB0DE1B66ACFCE541D7AF758FBD4F3FA3AF0EA4E10110000D3625E"); HashMap<String, Object> customDataMap = new HashMap<>();
customDataMap.put("audiences", audiences); AppsFlyerLib.getInstance().setAdditionalData(customDataMap);
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
> **Atenção**
>
> Você deve aplicar hash previamente aos dois valores (SHA-256) antes de passá-los.

### **SDK v7.0.1 and later — setUserPhone (recomendado)**

#### Assinatura de método

```java
public abstract void setUserPhone(String countryCode, String phoneNumber);
```

#### Exemplo de utilização

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
> **Nota**
>
> Passe o código de discagem do país e o número local como texto simples. O SDK concatena, normaliza e aplica hash aos dois valores localmente (SHA-256). Não aplique hash previamente.

Para definir um *Endereço de e-mail* com hash como um identificador de utilizador adicional:

### **SDK v7.0.0 e anteriores**

#### Com hash SHA256

```java
public abstract void setUserEmails(
  AppsFlyerProperties. EmailsCryptType cryptMethod,
  String... emails
);
```

#### Exemplo de utilização

<Tabs>
<Tab title="Java">

```java
AppsFlyerLib.getInstance().setUserEmails(
  AppsFlyerProperties. EmailsCryptType.SHA256,
  "name@domain.com",
  "another_name@another_domain.com"
);
```

</Tab>

<Tab title="Kotlin">

```java
AppsFlyerLib.getInstance().setUserEmails(
  AppsFlyerProperties. EmailsCryptType.SHA256,
  "name@domain.com",
  "another_name@another_domain.com"
);
```

</Tab>
</Tabs>

### **SDK v7.0.1 e posterior**

#### Todas as letras em minúscula

```java
public abstract void setUserEmail(String email);
```

#### Exemplo de utilização

```java
AppsFlyerLib.getInstance().setUserEmail("name@domain.com");
```

> 📘 **Note**
>
> **Nota**
>
> Apenas um único e-mail é aceito por chamada na v7.0.1 e posterior. Não há suporte para vários e-mails: chamar `setUserEmail` novamente substitui o valor definido anteriormente, em vez de adicioná-lo.

## Referência S2S e exemplos de código

Ao enviar identificadores para públicos-alvo por <Anchor target="_blank" href="/marketers/pt/docs/server-to-server-events-api-for-mobile-s2s-mobile">S2S</Anchor>, utilize o parâmetro <Anchor target="_blank" href="/marketers/pt/docs/server-to-server-events-api-for-mobile-s2s-mobile">para **todos os identificadores (inclusive *Endereço de e-mail* com hash).** Pode enviar um ou mais identificadores.</Anchor>

<Accordion title="Envio de identificadores através de S2S">

Formato:

* JSON aninhado
* O valor da chave deve ser `audiences`
* Todos os valores devem ser convertidos para string conforme mostrado no exemplo de código a seguir
* Os nomes dos parâmetros devem coincidir com os listados na [tabela de identificadores disponíveis](/docs/audiences-configure-additional-identifiers-for-partner-audience-creation#additional-identifiers%E2%80%94parameters-and-formatting) acima

Formato geral:

```json
"custom_data" : {   
      \"audiences\" : { 
          \"parameter_name_a\" : \"hashed_identifer_a\",
          \"parameter_name_a\" : \"hashed_identifer_b\",
          \"parameter_name_c\" : \"hashed_identifer_c\" 
       }
 }
```

Exemplo preenchido para *Número de telefone* e *Endereço de e-mail* com hash:

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
> **Consulte também**
>
> * Audiences — conexões de parceiros
> * Política de identificadores de utilizador para públicos-alvo

<div data-zendesk-anchors="background=sobre-os-identificadores-adicionais h_01HNZNWZ9WVH11NG94P5YX5CE0=sobre-os-identificadores-adicionais next-steps=pr%C3%B3ximos-passos h_01HNZNWZ9WYWFE1TTS3CWEBS8N=pr%C3%B3ximos-passos available-identifiers=identificadores-dispon%C3%ADveis h_01HNZNWZ9XG5P67Y8P08JGFWFD=identificadores-dispon%C3%ADveis sdk-reference-and-code-samples=refer%C3%AAncia-do-sdk-e-exemplos-de-c%C3%B3digo h_01HNZNWZ9X0N0D3EF9HJ76EVNJ=refer%C3%AAncia-do-sdk-e-exemplos-de-c%C3%B3digo ios-sdk-configuration=configura%C3%A7%C3%A3o-do-sdk-para-ios h_01HNZNWZ9XCZFWA7H8BN6J6485=configura%C3%A7%C3%A3o-do-sdk-para-ios sdk-v700-and-earlier-%E2%80%94-setadditionaldata=sdk-v700-e-anteriores--setadditionaldata h_01KZXZHJZCZ8XNS5Z5JQFGABEJ=sdk-v700-e-anteriores--setadditionaldata sdk-v701-and-later-%E2%80%94-setuserphone-recommended=sdk-v701-e-posteriores--setuserphone-recomendado h_01KZXZHSF8PCN9A4425217F4YP=sdk-v701-e-posteriores--setuserphone-recomendado method-signature=audi%C3%AAncias--identificadores-adicionais h_01KZXZF3GX0HSY4BFYX4N4BTHD=audi%C3%AAncias--identificadores-adicionais usage-example=exemplo-de-utiliza%C3%A7%C3%A3o h_01KZXZF3GXN55TJ078CJKMJGSY=exemplo-de-utiliza%C3%A7%C3%A3o h_01KZXZJ3MEQPEJ73798RY3S3R9=sdk-v700-and-earlier method-signature::a8fd9cf9=audi%C3%AAncias--identificadores-adicionais-1 h_01KZXZF3GX62EV1TTA689CK59F=audi%C3%AAncias--identificadores-adicionais-1 usage-example::5a156aca=exemplo-de-utiliza%C3%A7%C3%A3o-1 h_01KZXZF3GXB5VHHYT3SJ60F94V=exemplo-de-utiliza%C3%A7%C3%A3o-1 h_01KZXZJ98R1274HPDM9T4RTYDP=sdk-v701-and-later method-signature::6246e0dd=assinatura-de-m%C3%A9todo h_01KZXZF3GX9R7J1VF0ZFMJKN4Q=assinatura-de-m%C3%A9todo usage-example::b5bfcf61=exemplo-de-utiliza%C3%A7%C3%A3o-2 h_01KZXZF3GXQ22XRNRP1H0TX1HG=exemplo-de-utiliza%C3%A7%C3%A3o-2 android-sdk-configuration=configura%C3%A7%C3%A3o-do-sdk-para-android h_01HNZNWZ9XAF2K6213ZMMGKQ7T=configura%C3%A7%C3%A3o-do-sdk-para-android sdk-v700-and-earlier-%E2%80%94-setadditionaldata::6dbf5d0c=sdk-v700-e-anteriores--setadditionaldata-1 h_01KZXZJGMVJQAH5XC1BPJS1DGD=sdk-v700-e-anteriores--setadditionaldata-1 sdk-v701-and-later-%E2%80%94-setuserphone-recommended::1b63a185=sdk-v701-and-later--setuserphone-recomendado h_01KZXZJX109FSKCCRPVAA1W2Y2=sdk-v701-and-later--setuserphone-recomendado method-signature::bf39fa28=assinatura-de-m%C3%A9todo-1 h_01KZXZF3GX3Q6MZX5KXQJSANVK=assinatura-de-m%C3%A9todo-1 usage-example::1515fa60=exemplo-de-utiliza%C3%A7%C3%A3o-3 h_01KZXZF3GXSXDP4BBFWM7WZ74M=exemplo-de-utiliza%C3%A7%C3%A3o-3 sdk-v700-and-earlier::5989d839=sdk-v700-e-anteriores h_01KZXZK2H50HJVZKF65H59XVXY=sdk-v700-e-anteriores method-signature::9b0b0248=com-hash-sha256 h_01KZXZF3GXZXD09H3T922TGM7N=com-hash-sha256 usage-example::2bb38341=exemplo-de-utiliza%C3%A7%C3%A3o-4 h_01KZXZF3GXB7V1YK1584H0NW1G=exemplo-de-utiliza%C3%A7%C3%A3o-4 sdk-v701-and-later::16b1fdb1=sdk-v701-e-posterior h_01KZXZK8EXXVDY8P4TR2418FXH=sdk-v701-e-posterior method-signature::852458c4=todas-as-letras-em-min%C3%BAscula h_01KZXZF3GXX4S3P8SE4SBY6WZ2=todas-as-letras-em-min%C3%BAscula usage-example::11baa27a=exemplo-de-utiliza%C3%A7%C3%A3o-5 h_01KZXZF3GXM9Q0MQNX2ASEZ2BJ=exemplo-de-utiliza%C3%A7%C3%A3o-5 s2s-reference-and-code-samples=refer%C3%AAncia-s2s-e-exemplos-de-c%C3%B3digo h_01HNZNWZ9XKM53TJ9Z0FHWGCYC=refer%C3%AAncia-s2s-e-exemplos-de-c%C3%B3digo" />
