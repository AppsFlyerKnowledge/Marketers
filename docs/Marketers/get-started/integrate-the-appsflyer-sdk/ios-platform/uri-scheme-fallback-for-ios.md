---
title: Esquema URI alternativo para iOS
metadata:
  keywords:
    - Advertisers
    - Redirects
    - Developers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-guy-sarfatty
    - Marketers
    - Mobile Attribution
  created_at: '2017-05-10T12:50:00Z'
  edited_at: '2026-08-12T12:02:13Z'
  id: 115002366466
  locale: es
  section: iOS platform
  section_id: 6551263106577
  url: https://support.appsflyer.com/hc/es/articles/115002366466
---
> **En resumen:** Comprende el flujo cuando un usuario con un dispositivo iOS hace clic en un enlace personalizado de OneLink y Universal Links no puede abrir la aplicación.

<div id="about-uri-fallback-for-ios" />

## Sobre el URI alternativo para iOS

* La mejor manera de abrir aplicaciones en dispositivos iOS es usando los Universal Links. Desde 2016, existen importantes limitaciones del sistema operativo integradas en el uso de esquemas URI como opción alternativa para cuando los Universal Links de iOS no abren la aplicación. Estas limitaciones no están relacionadas con AppsFlyer y también afectarían a cualquier otro enlace con esquemas de URI que puedas usar para abrir la aplicación.
* De forma predeterminada, los esquemas de URI (que se llevan como el valor del parámetro af\_dp) solo se usan como método alternativo para abrir la aplicación en iOS en algunos navegadores o plataformas específicos.
* Para Safari, puedes intentar usar esquemas de URI como alternativa para abrir aplicaciones en iOS configurando los siguientes parámetros en tu URL de OneLink: 
  * `af_dp` (que lleva el esquema URI como valor).
  * `af_force_deeplink=true` (que obliga a la aplicación a abrirse con el esquema de URI af\_dp). Sin este parámetro, la aplicación no se abre con el esquema URI.
* Los esquemas URI son impredecibles y, por lo tanto, no son compatibles de forma predeterminada. Es probable que los usuarios que hagan clic en el enlace sean redireccionados a la App Store (o, si se establece, a la URL establecida en el `af_ios_url` parámetro).
* Consulta el diagrama de flujo de escenarios y los casos de uso que aparecen a continuación para obtener más información.

<div id="note" />

> 📘 **Advertencia**
>
> X (Twitter) no admite esquemas de URI. Recomendamos usar una página de destino de una app social con la configuración de Universal Links para evitar problemas al abrir la app.

<div id="scenarios-flowchart" />

### Diagrama de flujo de escenarios

<Image align="center" alt="flowchartdoctored.png" src="https://files.readme.io/5917ad4d8a01010db16eb16dd4c9a5beca02e80797ec9d47999772a8d4433401-41284711408529.png" width="1564px" />

<div id="use-cases" />

## Casos de uso

<div id="browsers-that-can-use-uri-schemes-by-default" />

<Accordion title="Navegadores que pueden usar esquemas URI de forma predeterminada">

A veces, los Universal Links no pueden abrir la aplicación, ya sea porque la aplicación no existe o porque el enlace no tiene Universal Links configurados. En esos casos, los siguientes navegadores/plataformas pueden usar esquemas URI como método alternativo para abrir la aplicación de forma predeterminada:

* Chrome
* Kakaotalk
* Naver
* Naver-Blog
* Weibo

#### **Flowchart**

<Image align="center" alt="diagrama de flujo de caso de uso.png" src="https://files.readme.io/9b68ccc634b55d72a9be8f8b07d9744214a10b2f14f11bf97416fcb377b28963-41284872656401.png" width="75.41%" />

</Accordion>

<div id="safari" />

<Accordion title="Safari">

A continuación, se describe el flujo para los usuarios cuando los Universal Links no pueden abrir la aplicación y el enlace está `af_dp` (es decir, que lleva el esquema URI como valor).

**Si la aplicación no está instalada:**

1. Aparece el mensaje de error de Safari.  
   <Image align="center" alt="" src="https://files.readme.io/d6b44169a7005fe7068b0692f71fac58bdd16bdca1424eb0a25499511c375caa-360016139237.jpg" />
2. El usuario hace clic en **OK** para cerrar el mensaje, ve brevemente la carga de una página de destino en segundo plano y, en 1 segundo, se redirecciona automáticamente a la App Store o según el parámetro af\_ios\_url.

**Si la aplicación está instalada:**

* Si no tiene un enlace `af_force_deeplink=true`, el usuario es enviado a la App Store o según el parámetro af\_ios\_url.
* Si tiene un enlace`af_force_deeplink=true`:
  1. Aparece el cuadro de mensaje de Safari.  
     <Image align="center" alt="" src="https://files.readme.io/0f56dfa3c0c9ea65c1d28f7bb4ebc9a1b3fa25ec1a7e8e620dc013b869012386-360016209978.jpg" />
  2. Si el usuario hace clic en **Abrir**, se abre la aplicación.
  3. Si el usuario hace clic en **Cancelar:**
     * Si se establece el parámetro af\_ios\_url, se envía al usuario conforme el parámetro.
     * Si no se establece el parámetro af\_ios\_url, el cuadro del mensaje de error de Safari se muestra sobre una landing page en segundo plano.  
       <Image align="center" alt="" src="https://files.readme.io/d6b44169a7005fe7068b0692f71fac58bdd16bdca1424eb0a25499511c375caa-360016139237.jpg" />
  4. El usuario hace clic en Aceptar y ve una página de destino con una llamada a la acción (CTA).
  5. El usuario hace clic en el CTA y se muestra un mensaje.  
     <Image align="center" alt="" src="https://files.readme.io/0f56dfa3c0c9ea65c1d28f7bb4ebc9a1b3fa25ec1a7e8e620dc013b869012386-360016209978.jpg" />
  6. Si el usuario hace clic en **Abrir**, se abre la aplicación.
  7. Si el usuario hace clic en **Cancelar**, aparece un mensaje.  
     <Image align="center" alt="" src="https://files.readme.io/dd3aa8492bdf1883246bd740118e1b8d2f075a77a164e3ad55843f7c4d44d2b9-360016210038.jpg" />
  8. Si el usuario hace clic en **Aceptar**, se le envía a la App Store.
  9. Si el usuario hace clic en **Cancelar**, permanece en la landing page.

#### **Flowchart**

<Image align="center" alt="Copy_of_Ios_fall_back_-_safari.png" src="https://files.readme.io/5e50eb558b23a849f02e1ffe5df3181ad7c8d9514f5813fbffcfa6160493de81-360016515318.png" />

</Accordion>

<div id="facebook-post-unpaid" />

<Accordion title="Publicación en Facebook: no remunerada">

A continuación, se describe el flujo para los usuarios cuando los Universal Links no pueden abrir la aplicación y contiene el enlace `af_dp` (es decir, que lleva el esquema URI como valor).

**Si la aplicación está instalada:**

* Se abre la aplicación.

**Si la aplicación no está instalada:**

1. Si no hay ninguna aplicación de redes sociales configurada, o después de que el usuario haga clic en el CTA en el SALP, se muestra un mensaje sobre una landing page en segundo plano.  
   <Image align="center" alt="" src="https://files.readme.io/200a0baef3755ab58c5385dac5fcb00ae3d72e762fbaa571c1735f7222d3b0b9-360016599277.jpg" />
2. Haz clic en Abrir aplicación. Puede producirse uno de los siguientes resultados:
   * Si se establece el `af_ios_url` parámetro, se envía al usuario conforme el parámetro.
   * Si el parámetro no está establecido y si `af_force_deeplink=true` no está en el enlace, el `af_ios_url` usuario se redirecciona en consecuencia.
   * Si el parámetro af\_ios\_url no está establecido y sí `af_force_deeplink=true` está en el enlace, el mensaje se muestra de nuevo sobre la landing page en segundo plano.  
     <Image align="center" alt="" src="https://files.readme.io/200a0baef3755ab58c5385dac5fcb00ae3d72e762fbaa571c1735f7222d3b0b9-360016599277.jpg" />
3. Si el usuario hace clic en **Abrir**, se le envía a la App Store.
4. Si el usuario hace clic en **Cerrar**, se muestra la landing page en segundo plano.  
   <Image align="center" alt="" src="https://files.readme.io/98748f47f3f9df43addc9c871c8165ecf4f849b17bdcfd660b90d4b6ded6727d-360016668478.jpg" />
5. El usuario hace clic en el logo de la App Store y es redireccionado a la App Store.

#### **Flowchart**

<Image align="center" alt="diagram-X.png" src="https://files.readme.io/0c8040d27bbf34fdf1374b4b40a8239b6af7b6c7719db9666f36dd2829bc3217-small-17710399441553.png" />

</Accordion>

<div data-zendesk-anchors="about-uri-fallback-for-ios=sobre-el-uri-alternativo-para-ios h_01HFV6PXS5401CCW6N2T04HGSM=sobre-el-uri-alternativo-para-ios h_01KAXQDBSG2YCPBDYYPFHBXR91=advertencia scenarios-flowchart=diagrama-de-flujo-de-escenarios h_01HFV6PXS5WWS0B1VYF7RJAV1J=diagrama-de-flujo-de-escenarios use-cases=casos-de-uso h_01HFV6PXS51B2W497TADRGBX7Y=casos-de-uso h_01HFV6PXS5HE462CJEE18CM5ZR=browsers-that-can-use-uri-schemes-by-default h_01HFV6PXS5N98MHJFYPSAB5XKZ=flowchart h_01HFV6PXS521E3MTCHJ5QBQGJ2=safari flowchart::db5f50ee=flowchart-1 h_01HFV6PXS57ZRSX2WAECS69XB4=flowchart-1 facebook-post%E2%80%94unpaid=facebook-post-unpaid h_01HFV6PXS5K8YZPE2B82V3DNTV=facebook-post-unpaid flowchart::df1b7de0=flowchart-2 h_01HFV6PXS504YQRDHZ1S1WS8CV=flowchart-2" />
