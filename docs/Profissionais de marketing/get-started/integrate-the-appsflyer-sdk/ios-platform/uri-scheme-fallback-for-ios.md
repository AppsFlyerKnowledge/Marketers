---
title: Fallback de esquemas URI para iOS
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
  edited_at: '2026-08-18T00:15:01Z'
  id: 115002366466
  locale: pt
  section: iOS platform
  section_id: 6551263106577
  url: https://support.appsflyer.com/hc/pt/articles/115002366466
---
> **Visão geral:** entenda o fluxo de usuários que usam dispositivos iOS e clicam em um link personalizado do OneLink, porém o Universal Link não consegue abrir o aplicativo.

<div id="about-uri-fallback-for-ios" />

## Fallback de URI para iOS

* A melhor forma de abrir um aplicativo em dispositivos iOS é usando Universal Links. Desde 2016, existem limitações consideráveis do sistema operacional quanto ao uso de esquemas URI como um método de fallback nos casos em que os Universal Links falham. Essas limitações não estão relacionadas com a AppsFlyer e também afetariam outros links com esquemas URI usados para abrir um aplicativo.
* Por padrão, os esquemas URI (enviados como o valor do parâmetro af\_dp) são usados apenas como um método de fallback em alguns navegadores/plataformas específicos no iOS.
* No Safari, você pode tentar usar esquemas URI como fallback configurando os seguintes parâmetros na URL do OneLink: 
  * `af_dp` (que inclui o esquema URI como o valor).
  * `af_force_deeplink=true` (que força o aplicativo a abrir usando o esquema URI af\_dp). Sem esse parâmetro, o aplicativo não abre usando esse esquema.
* Em outros navegadores, os esquemas URI atuam de forma imprevisível e, por isso, não são compatíveis por padrão. Os usuários que clicarem no link provavelmente serão redirecionados para a App Store (ou para a URL configurada no `af_ios_url` parâmetro).
* Consulte o fluxograma de cenários e os casos de uso a seguir para mais detalhes.

<div id="note" />

> 📘 **Atenção**
>
> O X (Twitter) não oferece suporte a esquemas de URI. Recomendamos usar uma página de destino de aplicativo social com configuração de link universal para evitar problemas ao abrir o aplicativo.

<div id="scenarios-flowchart" />

### Fluxograma de cenários

<Image alt="flowchartdoctored.png" src="https://files.readme.io/5917ad4d8a01010db16eb16dd4c9a5beca02e80797ec9d47999772a8d4433401-41284711408529.png" width="1564px" />

<div id="use-cases" />

## Casos de uso

<div id="browsers-that-can-use-uri-schemes-by-default" />

<Accordion title="Navegadores que podem usar esquemas URI por padrão">

Às vezes, os Universal Links não conseguem abrir o aplicativo, porque ele não foi baixado ou porque o link não inclui Universal Links configurados. Nesses casos,os seguintes navegadores/plataformas podem usar esquemas URI como um método de fallback para abrir o app:

* Chrome
* Kakaotalk
* Naver
* Never-Blog
* Weibo

<div id="flowchart" />

#### **Fluxograma**

<Image alt="fluxograma do caso de uso.png" src="https://files.readme.io/9b68ccc634b55d72a9be8f8b07d9744214a10b2f14f11bf97416fcb377b28963-41284872656401.png" width="75.41%" />

</Accordion>

<div id="safari" />

<Accordion title="Safari">

A seguir, descrevemos o fluxo de usuários quando os Universal Links não conseguem abrir o aplicativo e o link contém `af_dp` (que inclui o esquema URI como valor).

**Se o aplicativo não estiver instalado:**

1. A mensagem de erro do Safari é exibida.  
   [![](https://files.readme.io/d6b44169a7005fe7068b0692f71fac58bdd16bdca1424eb0a25499511c375caa-360016139237.jpg)](https://files.readme.io/d6b44169a7005fe7068b0692f71fac58bdd16bdca1424eb0a25499511c375caa-360016139237.jpg)
2. O usuário clica em **OK**. Uma landing page é carregada em segundo plano e, em 1 segundo, o usuário é redirecionado automaticamente para a App Store ou para o destino desejado de acordo com o parâmetro af\_ios\_url.

**Se o aplicativo estiver instalado:**

* Se o link não contiver `af_force_deeplink=true`, o usuário será redirecionado para a App Store ou para o destino desejado de acordo com o parâmetro af\_ios\_url.
* Se o link contiver `af_force_deeplink=true`:
  1. A notificação do Safari é exibida.  
     [![](https://files.readme.io/0f56dfa3c0c9ea65c1d28f7bb4ebc9a1b3fa25ec1a7e8e620dc013b869012386-360016209978.jpg)](https://files.readme.io/0f56dfa3c0c9ea65c1d28f7bb4ebc9a1b3fa25ec1a7e8e620dc013b869012386-360016209978.jpg)
  2. Se o usuário clicar em **Abrir**, o aplicativo será aberto.
  3. Se o usuário clicar em **Cancelar**:
     * Se o parâmetro af\_ios\_url estiver definido, o usuário será redirecionado de acordo.
     * Se o parâmetro af\_ios\_url não estiver definido, a mensagem de erro do Safari será exibida em segundo plano.  
       [![](https://files.readme.io/d6b44169a7005fe7068b0692f71fac58bdd16bdca1424eb0a25499511c375caa-360016139237.jpg)](https://files.readme.io/d6b44169a7005fe7068b0692f71fac58bdd16bdca1424eb0a25499511c375caa-360016139237.jpg)
  4. O usuário clica em **OK** e vê uma landing page com um call to action (CTA).
  5. O usuário clica no CTA e uma mensagem é exibida.  
     [![](https://files.readme.io/0f56dfa3c0c9ea65c1d28f7bb4ebc9a1b3fa25ec1a7e8e620dc013b869012386-360016209978.jpg)](https://files.readme.io/0f56dfa3c0c9ea65c1d28f7bb4ebc9a1b3fa25ec1a7e8e620dc013b869012386-360016209978.jpg)
  6. Se o usuário clicar em **Abrir**, o aplicativo será aberto.
  7. Se o usuário clicar em Cancelar , uma mensagem será exibida.  
     [![](https://files.readme.io/dd3aa8492bdf1883246bd740118e1b8d2f075a77a164e3ad55843f7c4d44d2b9-360016210038.jpg)](https://files.readme.io/dd3aa8492bdf1883246bd740118e1b8d2f075a77a164e3ad55843f7c4d44d2b9-360016210038.jpg)
  8. Se o usuário clicar em **OK**, ele será redirecionado para a App Store.
  9. Se o usuário clicar em **Cancelar**, ele permanecerá na landing page.

<div id="flowchart-1" />

#### **Fluxograma**

![Copy_of_Ios_fall_back_-_safari.png](https://files.readme.io/5e50eb558b23a849f02e1ffe5df3181ad7c8d9514f5813fbffcfa6160493de81-360016515318.png)

</Accordion>

<div id="facebook-post-unpaid" />

<Accordion title="Publicação no Facebook — não paga">

A seguir, descrevemos o fluxo de usuários para casos em que os Universal Links não conseguem abrir o aplicativo e o link contém`af_dp` (que inclui o esquema URI como valor).

**Se o aplicativo estiver instalado:**

* O aplicativo é aberto.

**Se o aplicativo não estiver instalado:**

1. Caso não haja nenhum aplicativo de rede social configurado, ou caso o usuário clique no CTA na landing page de uma rede social, uma mensagem será exibida em segundo plano.   
   [![](https://files.readme.io/200a0baef3755ab58c5385dac5fcb00ae3d72e762fbaa571c1735f7222d3b0b9-360016599277.jpg)](https://files.readme.io/200a0baef3755ab58c5385dac5fcb00ae3d72e762fbaa571c1735f7222d3b0b9-360016599277.jpg)
2. Clique em Abrir aplicativo. Em seguida, observamos um dos seguintes resultados:
   * Se o parâmetro `af_ios_url` estiver configurado, o usuário será redirecionado de acordo.
   * Se o parâmetro `af_ios_url` não estiver configurado e se `af_force_deeplink=true` não estiver no link, o usuário será redirecionado de acordo.
   * Se o parâmetro af\_ios\_url não estiver configurado e se `af_force_deeplink=true` for incluído no link, a mensagem será exibida novamente sobre a landing page em segundo plano.  
     [![](https://files.readme.io/200a0baef3755ab58c5385dac5fcb00ae3d72e762fbaa571c1735f7222d3b0b9-360016599277.jpg)](https://files.readme.io/200a0baef3755ab58c5385dac5fcb00ae3d72e762fbaa571c1735f7222d3b0b9-360016599277.jpg)
3. Se o usuário clicar em **Abrir**, ele será enviado para a App Store.
4. Se o usuário clicar em **Fechar**, a landing page será exibida.  
   [![](https://files.readme.io/98748f47f3f9df43addc9c871c8165ecf4f849b17bdcfd660b90d4b6ded6727d-360016668478.jpg)](https://files.readme.io/98748f47f3f9df43addc9c871c8165ecf4f849b17bdcfd660b90d4b6ded6727d-360016668478.jpg)
5. O usuário clica no selo da App Store e é redirecionado para lá.

<div id="flowchart-2" />

#### **Fluxograma**

![diagram-X.png](https://files.readme.io/0c8040d27bbf34fdf1374b4b40a8239b6af7b6c7719db9666f36dd2829bc3217-small-17710399441553.png)

</Accordion>

<div data-zendesk-anchors="about-uri-fallback-for-ios=fallback-de-uri-para-ios h_01HFV6PXS5401CCW6N2T04HGSM=fallback-de-uri-para-ios h_01KAXQDBSG2YCPBDYYPFHBXR91=aten%C3%A7%C3%A3o scenarios-flowchart=fluxograma-de-cen%C3%A1rios h_01HFV6PXS5WWS0B1VYF7RJAV1J=fluxograma-de-cen%C3%A1rios use-cases=casos-de-uso h_01HFV6PXS51B2W497TADRGBX7Y=casos-de-uso h_01HFV6PXS5HE462CJEE18CM5ZR=browsers-that-can-use-uri-schemes-by-default flowchart=fluxograma h_01HFV6PXS5N98MHJFYPSAB5XKZ=fluxograma h_01HFV6PXS521E3MTCHJ5QBQGJ2=safari flowchart::db5f50ee=fluxograma-1 h_01HFV6PXS57ZRSX2WAECS69XB4=fluxograma-1 facebook-post%E2%80%94unpaid=facebook-post-unpaid h_01HFV6PXS5K8YZPE2B82V3DNTV=facebook-post-unpaid flowchart::df1b7de0=fluxograma-2 h_01HFV6PXS504YQRDHZ1S1WS8CV=fluxograma-2" />
