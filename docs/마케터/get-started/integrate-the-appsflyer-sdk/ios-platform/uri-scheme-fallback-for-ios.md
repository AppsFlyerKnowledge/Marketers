---
title: iOS용 URI 스키마 폴백
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
  edited_at: '2026-10-14T10:34:34Z'
  id: 115002366466
  locale: ko
  section: iOS platform
  section_id: 6551263106577
  url: https://support.appsflyer.com/hc/ko/articles/115002366466
---
> **한눈에 보기:** 요약: iOS 기기 사용자가 원링크 커스텀 링크를 클릭하고 유니버설 링크가 앱을 열지 못하는 경우의 흐름을 이해합니다.

<div id="about-uri-fallback-for-ios" />

## iOS용 URI 폴백 정보

* iOS 기기에서 앱을 실행하는 가장 좋은 방법은 유니버설 링크를 사용하는 것입니다. 2016년 이후 iOS 유니버설 링크가 앱을 열지 못하면 내장 OS에서 URI 스킴을 폴백 메서드로 사용하는 데 상당한 제약이 있습니다. 이러한 제한은 앱스플라이어와 관련이 없으며 앱을 여는 데 사용할 수 있는 URI 스키마가 있는 다른 링크에도 영향을 미칩니다.
* 기본적으로 URI 스키마(af\_dp 파라미터의 값으로 전달됨)은 몇 가지 특정 브라우저/플랫폼에서 iOS의 앱을 열기 위한 폴백 방법으로만 사용됩니다.
* Safari의 경우 원링크 URL에서 다음 파라미터를 설정하여 iOS에서 앱을 열기 위한 대체로 URI 스키마를 사용할 수 있습니다. 
  * `af_dp`af\_dp (URI 스키마를 값으로 전달).
  * 이 파라미터가 없으면 앱이 URI 스키마를 사용하여 열리지 않습니다.
* 다른 브라우저의 경우 URI 스키마는 예측할 수 없으므로 기본적으로 지원되지 않습니다. 링크를 클릭하는 사용자는 앱 스토어(또는 설정된 경우 af\_ios\_url 파라미터에 설정된 URL)로 리디렉션될 수 있습니다.
* 자세한 내용은 시나리오 순서도 및 사용 사례를 참조하십시오.

<div id="scenarios-flowchart" />

### 시나리오 흐름도

![Copy_of_Ios_fall_back_-_scenarios_flowchart__2_.png](https://files.readme.io/aec44d772261fb7461b3cfeb6331c93659206c6b7ad62f5914f26c0bd2cab407-51912778632465.png)

<div id="use-cases" />

## 활용 사례

<div id="browsers-that-can-use-uri-schemes-by-default" />

<Accordion title="기본적으로 URI 스키마를 사용할 수 있는 브라우저">

* Chrome
* X(구 트위터)  
  **참고**: 트위터 참고: 앱이 인스톨되지 않은 경우 사용자에게 오류 메시지가 표시되고 메시지를 닫은 후 앱 스토어로 리디렉션됩니다(또는 af\_ios\_url 파라미터에 따라).
* 카카오톡
* Naver
* 네이버 블로그
* Weibo

<div id="flowchart" />

#### **흐름도**

![Copy_of_Ios_fall_back_-_browsers_that_can_use_URI_schemes_by_default__2_.png](https://files.readme.io/32ac106ee5fdfc433d4b4cc4afb6063293b73dbc872834ec7a45a4e6d338e9b4-51912794392721.png)

</Accordion>

<div id="safari" />

<Accordion title="Safari">

다음은 유니버설 링크가 앱을 여는 데 실패하고 링크에 `af_dp`af\_dp (URI 스키마를 값으로 전달)가 포함된 경우 사용자의 흐름을 설명합니다.

**앱이 인스톨되지 않은 경우:**

1. Safari 오류 메시지 대화 상자가 표시됩니다.   
   [![](https://files.readme.io/d6b44169a7005fe7068b0692f71fac58bdd16bdca1424eb0a25499511c375caa-360016139237.jpg)](https://files.readme.io/d6b44169a7005fe7068b0692f71fac58bdd16bdca1424eb0a25499511c375caa-360016139237.jpg)
2. 사용자는 **확인**을 클릭하여 화 상자를 닫고 백그라운드에서 랜딩 페이지 로드를 잠시 확인한 다음 1초 이내에 앱 스토어 또는 af\_ios\_url 파라미터에 따라 자동으로 리디렉션됩니다.

**앱이 인스톨된 경우:**

* 1. Safari 대화 상자가 표시됩니다.  
     [![](https://files.readme.io/0f56dfa3c0c9ea65c1d28f7bb4ebc9a1b3fa25ec1a7e8e620dc013b869012386-360016209978.jpg)](https://files.readme.io/0f56dfa3c0c9ea65c1d28f7bb4ebc9a1b3fa25ec1a7e8e620dc013b869012386-360016209978.jpg)
  2. 사용자가 **열기**를 클릭하면 앱이 열립니다.
  3. 사용자가 **취소**를 클릭하는 경우:
     * af\_ios\_url 파라미터가 설정되면 그에 따라 사용자가 리디렉션됩니다.
     * [![](https://files.readme.io/d6b44169a7005fe7068b0692f71fac58bdd16bdca1424eb0a25499511c375caa-360016139237.jpg)](https://files.readme.io/d6b44169a7005fe7068b0692f71fac58bdd16bdca1424eb0a25499511c375caa-360016139237.jpg)
  4. 사용자가 **확인**을 클릭하면 콜투액션(CTA)이 포함된 랜딩 페이지가 표시됩니다.
  5. 사용자가 CTA를 클릭하면 대화 상자가 표시됩니다.  
     [![](https://files.readme.io/0f56dfa3c0c9ea65c1d28f7bb4ebc9a1b3fa25ec1a7e8e620dc013b869012386-360016209978.jpg)](https://files.readme.io/0f56dfa3c0c9ea65c1d28f7bb4ebc9a1b3fa25ec1a7e8e620dc013b869012386-360016209978.jpg)
  6. 사용자가 **열기**를 클릭하면 앱이 열립니다.
  7. 사용자가 **취소**를 클릭하면 대화 상자가 표시됩니다.  
     [![](https://files.readme.io/dd3aa8492bdf1883246bd740118e1b8d2f075a77a164e3ad55843f7c4d44d2b9-360016210038.jpg)](https://files.readme.io/dd3aa8492bdf1883246bd740118e1b8d2f075a77a164e3ad55843f7c4d44d2b9-360016210038.jpg)
  8. 사용자가 **확인**을 클릭하면 앱 스토어로 리디렉션됩니다.
  9. 사용자가 **취소**를 클릭하면 방문 페이지에 남아 있습니다.

<div id="flowchart-1" />

#### **흐름도**

![Copy_of_Ios_fall_back_-_safari.png](https://files.readme.io/5e50eb558b23a849f02e1ffe5df3181ad7c8d9514f5813fbffcfa6160493de81-360016515318.png)

</Accordion>

<div id="facebook-post-unpaid" />

<Accordion title="페이스북 게시물 -미지급">

다음은 유니버설 링크가 앱을 여는 데 실패하고 링크에 `af_dp`af\_dpaf\_dp (URI 스키마를 값으로 전달)가 포함된 경우 사용자의 흐름을 설명합니다.

**앱이 인스톨된 경우:**

* 앱이 열립니다.

**앱이 인스톨되지 않은 경우:**

1. 구성된 소셜 미디어 앱이 없거나 사용자가 SALP에서 CTA를 클릭하면 백그라운드에서 랜딩 페이지 위에 대화 상자가 표시됩니다.  
   [![](https://files.readme.io/200a0baef3755ab58c5385dac5fcb00ae3d72e762fbaa571c1735f7222d3b0b9-360016599277.jpg)](https://files.readme.io/200a0baef3755ab58c5385dac5fcb00ae3d72e762fbaa571c1735f7222d3b0b9-360016599277.jpg)
2. 앱 열기를 클릭합니다. 다음 결과 중 하나가 발생할 수 있습니다.

   * af\_ios\_url 매개변수가 설정되지 않은 경우 링크에 있는 경우 `af_force_deeplink=true`af\_force\_deeplink=trueaf\_force\_deeplink=true 백그라운드의 랜딩 페이지 위에 대화 상자가 다시 표시됩니다.  
     [![](https://files.readme.io/200a0baef3755ab58c5385dac5fcb00ae3d72e762fbaa571c1735f7222d3b0b9-360016599277.jpg)](https://files.readme.io/200a0baef3755ab58c5385dac5fcb00ae3d72e762fbaa571c1735f7222d3b0b9-360016599277.jpg)
3. 사용자가 **열기**를 클릭하면 앱 스토어로 전송됩니다.
4. 사용자가 **닫기**를 클릭하면 백그라운드에서 랜딩 페이지가 표시됩니다.  
   [![](https://files.readme.io/98748f47f3f9df43addc9c871c8165ecf4f849b17bdcfd660b90d4b6ded6727d-360016668478.jpg)](https://files.readme.io/98748f47f3f9df43addc9c871c8165ecf4f849b17bdcfd660b90d4b6ded6727d-360016668478.jpg)
5. 사용자가 앱 스토어 배지를 클릭하면 앱 스토어로 리디렉션됩니다.

<div id="flowchart-2" />

#### **흐름도**

![diagram-X.png](https://files.readme.io/0c8040d27bbf34fdf1374b4b40a8239b6af7b6c7719db9666f36dd2829bc3217-small-17710399441553.png)

</Accordion>

<div data-zendesk-anchors="about-uri-fallback-for-ios=ios%EC%9A%A9-uri-%ED%8F%B4%EB%B0%B1-%EC%A0%95%EB%B3%B4 h_01HFV6PXS5401CCW6N2T04HGSM=ios%EC%9A%A9-uri-%ED%8F%B4%EB%B0%B1-%EC%A0%95%EB%B3%B4 scenarios-flowchart=%EC%8B%9C%EB%82%98%EB%A6%AC%EC%98%A4-%ED%9D%90%EB%A6%84%EB%8F%84 h_01HFV6PXS5WWS0B1VYF7RJAV1J=%EC%8B%9C%EB%82%98%EB%A6%AC%EC%98%A4-%ED%9D%90%EB%A6%84%EB%8F%84 use-cases=%ED%99%9C%EC%9A%A9-%EC%82%AC%EB%A1%80 h_01HFV6PXS51B2W497TADRGBX7Y=%ED%99%9C%EC%9A%A9-%EC%82%AC%EB%A1%80 h_01HFV6PXS5HE462CJEE18CM5ZR=browsers-that-can-use-uri-schemes-by-default flowchart=%ED%9D%90%EB%A6%84%EB%8F%84 h_01HFV6PXS5N98MHJFYPSAB5XKZ=%ED%9D%90%EB%A6%84%EB%8F%84 h_01HFV6PXS521E3MTCHJ5QBQGJ2=safari flowchart::db5f50ee=%ED%9D%90%EB%A6%84%EB%8F%84-1 h_01HFV6PXS57ZRSX2WAECS69XB4=%ED%9D%90%EB%A6%84%EB%8F%84-1 facebook-post%E2%80%94unpaid=facebook-post-unpaid h_01HFV6PXS5K8YZPE2B82V3DNTV=facebook-post-unpaid flowchart::df1b7de0=%ED%9D%90%EB%A6%84%EB%8F%84-2 h_01HFV6PXS504YQRDHZ1S1WS8CV=%ED%9D%90%EB%A6%84%EB%8F%84-2" />
