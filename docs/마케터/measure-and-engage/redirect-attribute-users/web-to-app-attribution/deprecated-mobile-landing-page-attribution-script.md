---
title: '[사용 중단] 모바일 랜딩 페이지 어트리뷰션 스크립트'
deprecated: true
metadata:
  keywords:
    - Landing Page
    - Facebook
    - Adwords
    - Advertisers
    - Agencies
    - GCLID
    - Developers
    - Marketers
    - Smart Banners and Scripts
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-asaf-mashiah
    - Marketers
    - Agencies
    - Smart Banners and Scripts
  created_at: '2020-12-16T17:28:55Z'
  edited_at: '2026-10-14T10:37:32Z'
  id: 360016643258
  locale: ko
  section: Web-to-app attribution
  section_id: 6551240476177
  url: https://support.appsflyer.com/hc/ko/articles/360016643258
---
> **요약:** 이 스크립트는 2020년 12월 17일부터 더 이상 사용되지 않으며 <Anchor target="_blank" href="/marketers/ko/docs/onelink-smart-script-overview">원링크 스마트 스크립트</Anchor>로 바뀌었습니다. 이 버전은 계속 작동하지만 업데이트되거나 변경되지는 않습니다. 이 스크립트는 모바일 웹사이트의 버튼 뒤에 포함된 URL을 생성하고 방문자가 앱을 다운로드하도록 리디렉션합니다. URL은 설치 어트리뷰션과 딥링킹도 지원합니다.

![5648_Sunset_and_deprecation-01.png](https://files.readme.io/f2a154145e26577b698d00c4c3719be3eea7298576e6883bd47e6fb42897c71a-360015062398.png)

**<Anchor target="_blank" href="/marketers/ko/docs/onelink-smart-script-overview">원링크 스마트 스크립트로 마이그레이션</Anchor>**

방문자의 정보를 입력하도록 하는 랜딩 페이지는 디지털 마케팅에서 흔히 사용되는 마케팅 전략입니다. 방문자가 처음에 전환하지 않더라도, 마케터는 랜딩 페이지에서 수집한 리드(lead), 즉 가망고객정보를 활용하여 추후 마케팅에 활용할 수 있습니다.

그런데, 모바일 사용자 유입(UA) 마케팅에서 랜딩 페이지는 장단점이 있습니다.

#### 장점:

* 결과적으로 앱을 설치한 리드(lead)는 앱을 더 많이 사용하게 됩니다.
* 앱이 제공하는 서비스가 복잡할수록(예: 금융 서비스), 랜딩 페이지에서 방문자가 쉽게 전환할 수 있도록 자세히 설명할 수 있습니다.

#### 단점:

* 전환에 이르는 절차가 복잡할수록 전환율이 낮아집니다.
* 어트리뷰션하기가 기술적으로 까다롭습니다.

## 모바일 랜딩 페이지 어트리뷰션이 어려운 이유

* **매체별 랜딩 페이지 어트리뷰션 측정 방식이 다릅니다.**
* 랜딩 페이지에 랜딩 페이지 어트리뷰션 링크가 있으면, **라스트 클릭 어트리뷰션 방식**으로는 정확히 어트리뷰션을 할 수 없습니다.
* 랜딩 페이지에 랜딩 페이지 어트리뷰션 링크가 없으면, **웹사이트 URL을 주소창에 바로 입력해서 들어온 다이렉트 웹사이트 방문자가 오가닉으로 기록됩니다.**
* 랜딩 페이지에서 모바일 앱 설치로의 전환을 기록하는 장치가 없으면, **데스트톱 방문자는 오가닉으로 기록됩니다.**

## 솔루션

위에 언급한 랜딩 페이지 어트리뷰션 문제를 해결하려면, 랜딩 페이지에 자바스크립트 플로우를 구현해야 합니다. 이 문서에서 샘플 스크립트를 제공해 드립니다. 귀사의 요건에 맞게 스크립트를 편집하세요.

경우에 따라, 캠페인을 변경해야 할 수도 있습니다.

다음은 모든 매체별 랜딩 페이지 어트리뷰션 시나리오를 정리했습니다.

## 매체별 랜딩 페이지 어트리뷰션 시나리오

랜딩 페이지로 리드(lead)를 유입시키는 **모든 미디어소스에 대해** 아래 구현 지침을 따르세요.

<div id="facebook-ads-crossplatform-attribution" />

<Accordion title="메타 광고: 크로스 플랫폼 어트리뷰션">

#### 설명:

메타 광고는 외부 어트리뷰션 링크를 사용하지 않는 SRN(Self Reporting Network)입니다.

앱이 처음 실행되면, 앱스플라이어는 해당 사용자가 이전에(최근 28일 이내) 페이스북 앱에서 광고주 광고와의 인게이지먼트가 있는지 메타 광고 측에 문의합니다. 그런 적이 있다면 메타 광고가 스스로 어트리뷰션합니다.

메타 광고는 또한 크로스 플랫폼에 어트리뷰션하며, 이는 사용자가 모든 플랫폼에서 모바일이든 아니든 모든 유형의 캠페인과 상호작용하여 메타 광고에 의해 자체 어트리뷰션할 수 있음을 의미합니다.

#### 결론:

사용 가능한 기기 ID가 있는 잠재 고객이 페이스북 앱에서 랜딩 페이지로 이동하면 메타 광고에 올바르게 어트리뷰션됩니다. 이는 랜딩 페이지에 기록된 새로운 클릭과 관계없이 발생합니다.  
그러나 2021년 기간에 iOS 14 사용자와 예상대로 사용자가 기기 ID를 공유하지 않을 경우 메타 광고의 크로스 플랫폼 어트리뷰션이 더 이상 작동하지 않을 수 있습니다.

**기기 ID 공유가 선택 사항이 되면 메타 광고에 대해 [다른 SRN 방법](/docs/deprecated-mobile-landing-page-attribution-script#other-srns-add-parameter)을 선택하세요.**

* 기기 ID를 공유하는 신규 사용자는 메타 광고에 올바르게 어트리뷰션됩니다.
* 기기 ID를 공유하지 않는 신규 사용자는 "Facebook\_LP"에 어트리뷰션됩니다.

#### 지침:

1. 메타 광고 계정에서 랜딩 페이지로의 전환에 대해 모바일 어트리뷰션을 하는 **'트래픽'이나 '전환' 캠페인**을 설정하세요.
2. 랜딩 페이지 안드로이드 다운로드 버튼: 구글 플레이 바로가기 링크
3. 랜딩 페이지 iOS 다운로드 버튼- iTunes 바로가기 링크 (혹은 **디바이스 ID 없는** 어트리뷰션 링크)

#### 스크립트 동작

랜딩 페이지 스크립트는 아무 변경사항을 만들지 않습니다. 랜딩 페이지 스크립트는 사용자가 페이스북 앱으로부터 유입되었다는 사실을 감지하도록 짜여져 있습니다. 페이스북으로부터 유입된 사용자를 감지한 후에는 아무것도 하지 않습니다. 랜딩 페이지의 앱스토어 바로가기 링크를 그대로 둡니다. 추가 클릭이 발생하지 않도록 하여, CTR(Click-Through Rate: 클릭 전환) 데이터에 영향을 주지 않습니다.

스크립트에서  ***isFacebook()*** 메서드를 찾아 사용자가 페이스북 앱에서 유입된 경우 스크립트가 어떻게 동작하는지 더 자세히 알아보세요.

</Accordion>

<div id="google-ads-gclid-offline-conversion-upload" />

<Accordion title="Google 광고: GCLID + 오프라인 전환 업로드">

#### 설명:

구글 애즈 캠페인의 앱 설치 어트리뷰션 방식은 클릭하는 리드를 앱스토어 페이지 URL로 보내는 것입니다.

그래서 구글 애즈에서 랜딩 페이지로 리드를 보낼 때 , 모바일 앱 설치와 모바일이 아닌 구글 애즈 캠페인 클릭을 연결하는 중계자(mediator)를 사용하세요.

#### 결론:

구글 애즈 어트리뷰션 솔루션은 두 부분으로 나뉩니다.

첫 번째 부분은 **앱스플라이어에서 어트리뷰션**하는 것입니다. 구글에서 랜딩 페이지로 들어와 앱을 설치한 모바일 사용자를 구글로 어트리뷰션합니다. 이를 위해 구글의 클릭 URL을 태그하여 구글로부터 랜딩 페이지에서 유입된 리드를 확인하고, 이 URL에 있는 데이터로 동적 원링크를 생성해야 합니다.

두 번째 부분은 **구글 애즈에 앱 인스톨에 대해 알리는 것**입니다. 구글의 오프라인 전환 업로드 메서드를 이용하여 알립니다.

> 📘 **참고**
>
> GCLID 솔루션은 구글이 공식적으로 지원하거나 권고하지 않습니다.
> 구글이 GCLID 파라미터를 삭제하는 경우, 앱스플라이어는 그에 따라 스크립트를 변경하겠습니다.
> 이 문서 헤더 부분 왼쪽에서 ***팔로우***버튼을 클릭하시면 이 문서나 첨부 스크립트가 업데이트할 때 알림을 받으실 수 있습니다.

#### 지침:

Part 1 - 앱스플라이어에서 구글 애즈 어트리뷰션하기

구글의 대시보드에서 **자동 태그 추가**를 켜세요(<Anchor target="_blank" href="https://support.google.com/analytics/answer/1033981?hl=en">방법 보기</Anchor>).

자동 태그 추가를 켜면, **랜딩 페이지로연결되는 URL에 GCLID *파라미터가* 추가됩니다**.

URL 예: `http://www.yoursite.com/yourlandingpage?gclid={USER_GCLID}`

랜딩 페이지 로드에서

1. ***generateUrl*** 자바스크립트 함수를 활성화하세요.
2. 이 함수(아래 참조)는 ***GCLID***파라미터를 찾고 긴원링크 URL을 생성합니다. 이 긴 원링크 URL은 af\_sub1 파라미터 아래 값을 포함합니다. (af\_sub1에서 af\_sub5까지 어떤 <Anchor target="_blank" href="/marketers/ko/docs/about-link-structure-and-parameters#what-are-subscriber-parameters-good-for">subscriber 파라미터</Anchor>든 사용할 수 있습니다)
3. 랜딩 페이지의 앱 다운로드 버튼은 이렇게 생성된 원링크 URL을 사용합니다.  
   원링크 URL 예시: `https://yourapp.onelink.me/abcd?pid=google_lp&c={CAMPAIGN_NAME}&af_sub1={USER_PARSED_GCLID}`
4. 신규 모바일 앱 사용자는 미디어소스명:**google\_lp**, 캠페인명: CAMPAIGN\_NAME(선택사항)으로 어트리뷰션됩니다.
5. 미디어소스에 포스트백이 전송되지 않습니다.

이 시점에서, 인스톨이 앱스플라이어에 미디어소스명:***google\_lp***로 GCLID와 함께 보고됩니다. 그러나 구글 애즈에는 보고되지 않습니다.

Part 2 - 구글에 오프라인 전환으로 인스톨을 업로드하기

**이 부분은 전환을 구글 애즈 플랫폼에 기록하기를 원할 때만 필요한 작업입니다.**

google\_lp이 어트리뷰션한 신규 사용자에 대해, 앱스플라이어는 **af\_sub1** 컬럼에 GCLID 값을 표기합니다. GCLID은 구글 애즈에 오프라인 전환을 업로드하기 위해 필요합니다. 상세 프로세스는 <Anchor target="_blank" href="https://support.google.com/adwords/answer/7014069">여기</Anchor>에서 확인하십시오.

전환은 수작업 혹은 애드워즈(Adwords) API(API <Anchor target="_blank" href="https://developers.google.com/adwords/api/docs/guides/conversion-tracking#importing_conversions">상세 정보</Anchor>)로 업로드할 수 있습니다.

앱스플라이어 계정에서 구글 전환 정보를 CSV로 내보거나 푸시 API를 통해 매 인스톨마다 실시간으로 이 데이터를 얻을 수 있습니다.

> 👍 **팁**
>
> GCLID를 얻는 방식과 비슷하게 앱스플라이어 로데이터에서 사용자가 검색한 키워드를 확인할 수 있습니다.
>
> 1. 키워드 기록을 위해 Google Ads에서 랜딩 페이지로 연결되는 최종 URL에 키워드 <Anchor target="_blank" href="https://support.google.com/google-ads/answer/2375447">ValueTrack 파라미터</Anchor>를 포함해야 합니다.
>    URL 예: `http://www.yoursite.com/yourlandingpage?gclid={USER_GCLID}&keyword={USER_KEYWORD}`
> 2. 자바스크립트 함수(아래)가 ***키워드***파라미터를 찾습니다.
> 3. 이 값은 af\_keywords 아래에 생성된 원링크 URL에 추가됩니다.
>    원링크 URL 예시: `https://yourapp.onelink.me/abcd?pid=google_lp&c={CAMPAIGN_NAME}&af_sub1={USER_PARSED_GCLID}&af_keywords={USER_PARSED_KEYWORD}`
>
> 아래 자바스크립트 함수는 키워드 파라미터를 파싱(parsing)하는 코드를 포함하고 있습니다.

#### 스크립트 동작

구글 애즈에는  gclid 파라미터가 있습니다. 스크립트는 랜딩 페이지 URL에서 이 파라미터를 검색합니다. 파라미터를 찾으면, 사용자가 구글 애즈에서 유입되었다는 사실을 반영하는 원링크를 생성합니다. 그런다음 랜딩 페이지에 있는 다운로드 버튼 뒤에 생성된 원링크를 넣습니다.

스크립트에서  **gclidValue**를 찾아 스크립트가 어떻게 구글 애즈에서 유입되는 사용자를 감지하고 이에 따라 원링크를 생성하는지 확인하십시오.

</Accordion>

<div id="other-srns-add-parameter" />

<Accordion title="기타 SRN: 파라미터 추가">

#### 설명:

예들 들어 스냅챗이나 트위터 같은 다른 <Anchor target="_blank" href="/marketers/ko/docs/self-reporting-networks-srns#앱스플라이어와-통합된-srn">SRN</Anchor>은 메타 광고와 달리 크로스 플랫폼이 아니어서 앱 설치 사용자를 어트리뷰션하려면 약간의 작업을 해야 합니다.

타 SRN에서 집행하는 캠페인으로부터 사용자가 랜딩 페이지로 유입되면 앱을 실제로 설치한 사용자가 아니라 광고를 클릭해서 랜딩 페이지까지만 도달한 사람 기준으로 광고비가 발생합니다.

#### 결론:

메타 광고와 구글 애즈를 제외한 SRN에 집행하는 캠페인을 어트리뷰션 하기 위해서는 랜딩 페이지 URL을 정의할 때, 광고 성과 어트리뷰션 SRN을 알려주는 파트너 ID 파라미터를 추가합니다.  
랜딩 페이지는 자바 스크립트(아래)를 실행시켜 이 파트너 ID 파라미터를 파싱(parsing: 분석)하고 파트너 ID 값이 들어간 원링크 URL을 생성합니다. 모바일 사용자가 원링크를 클릭하고 앱을 설치하면 파트너 ID 파라미터 값으로 알 수 있는 매체에 어트리뷰션이 기록됩니다.

#### 지침:

SRN 광고 계정에서

1. 비 모바일 캠페인을 생성하세요.
2. 랜딩 페이지 URL을 정의할 때, 파트너 ID + 랜딩 페이지 파라미터를 추가하세요. (랜딩 페이지 URL은 앱스플라이어 어트리뷰션 링크가 아닙니다.) 형식은 "***&af\_pid=srn\_lp***"입니다. (아래 예 참조)

랜딩 페이지 로드에서

1. ***generateUrl*** 자바스크립트 함수를 활성화하세요.
2. 이 함수는 ***af\_pid*** 파라미터를 찾고 ***pid*** 파라미터 값을 포함하여 원링크 URL을 생성합니다.
3. 랜딩 페이지의 앱 다운로드 버튼은 이렇게 생성된 원링크 URL을 사용합니다.
4. 신규 앱 사용자 획득에 대해 이렇게 광고주가 정의한 "파트너 ID + 랜딩 페이지" 미디어소스를 어트리뷰션으로 기록합니다.
5. 미디어소스에 포스트백이 전송되지 않습니다.

예를 들어 twitter\_int와 같이 실제 SRN 이름을 지정하면 이 SRN으로 포스트백이 전송될 수 있습니다. 이로 인해 이중 비용이 발생할 수 있습니다. 대체 이름은 아래의 Note 부분을 참조하십시오.

스크립트 자체에 이러한 이름을 사용하지 않도록 하는 로직이 있습니다. 스크립트에서 `var SRNs`를 찾습니다. SRN 이름 목록과 `pidValue`가 이 이름들을 체크하는 조건을 확인하실 수 있습니다. 스크립트 테스트를 완료한 후에 이 로직을 제거하십시오.

> 📘 **참고**
>
> 사용자를 광고 매체에서 랜딩 페이지에 보낼 때, 각 매체마다 랜딩 페이지 URL에 다음 파라미터를 넣으세요.
>
> * 트위터: “***&af\_pid=twitter\_lp***” 사용
> * 스냅챗: “***&af\_pid=snapchat\_lp***” 사용
> * 더블클릭: “***&af\_pid=doubleclick\_lp***” 사용
> * 메타 광고 포스트(무료): "***&af\_pid=fbpost\_lp***" 사용
> * Oath(구 Yahoo Gemini): "***&af\_pid=oath\_lp***" 사용

#### 스크립트 동작

스크립트는 랜딩 페이지 URL에서 af\_pid 파라미터를 보고 사용자가 SRN이나 다른 사전 정의된 네트워크에서 유입되었음을 인지합니다. 스크립트는 이에 따라 원링크를 생성하여 랜딩 페이지 앱 다운로드 버튼 뒤에 설정합니다.

스크립트 동작에 대한 상세한 사항은 스크립트에서 **pidValue**를 검색하세요.

</Accordion>

<div id="attribution-links-redirect-with-af_r" />

<Accordion title="어트리뷰션 링크: af_r로 리디렉션">

#### 설명:

어트리뷰션 링크는 SRN이 아닌 모든 미디어소스(매체)에 사용됩니다. 어트리뷰션하고자 하는 수천 연동 파트너사와 온드 미디어에 사용됩니다.

다행히, 앱스플라이어 어트리뷰션 링크를 사용하여 랜딩 페이지 어트리뷰션을 하는 솔루션은 간단합니다. (메타 광고 어트리뷰션 방식과 유사함)

#### 결론:

어트리뷰션 링크는 리드(lead)를 랜딩 페이지로 리디렉션하여, 리디렉션 후 앱 설치가 발생하면 정확히 어트리뷰션을 합니다.

새로운 라스크 클릭으로 정확한 어트리뷰션을 막지 않도록 하기만 하면 됩니다.

#### 지침:

1. 어트리뷰션할 미디어소스에 대한 <Anchor target="_blank" href="/marketers/ko/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#캠페인을-위한-원링크-링크-생성하기">어트리뷰션 링크를 생성</Anchor>하십시오.
2. 생성된 어트리뷰션 링크에 랜딩 페이지로 연결하는<Anchor target="_blank" href="/marketers/ko/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#redirection">랜딩 페이지 파라미터</Anchor>를 추가하십시오.
3. 어트리뷰션 링크에 있는 **리디렉션 파라미터**의 랜딩 페이지 값(즉, af\_r, af\_ios\_url 및 af\_android\_url)에 `&af_redirect=true`를 추가하십시오.  
   예: `https://yourapp.onelink.me/abcd?pid=email&c={CAMPAIGN_NAME}&af_r=http://www.yoursite.com/yourlandingpage?af_redirect=true`
4. **선택사항** - 디바이스 ID(GAID / IDFA)를 어트리뷰션 링크에 추가하면 확률적 모델링 대신 ID 매칭을 할 수 있습니다.
5. 랜딩 페이지 안드로이드 앱 다운로드 버튼 - 구글 플레이 바로가기 연결
6. 랜딩 페이지 iOS 앱 다운로드 버튼 - iTunes 바로가기 연결  

   > 📘 **참고**
   >
   > 스크립트와 HTML 샘플 페이지는 안드로이드와 iOS 모두 지원하는 하나의 다운로드 버튼을 설정하는 옵션을 제공합니다. 스크립트의 주석을 읽고 구현하는 방법을 학습하십시오.


#### 스크립트 동작

스크립트는 랜딩 페이지 URL에서 **af\_redirect** 파라미터를 찾습니다. 발견하면, 랜딩 페이지의 앱 다운로드 버튼에 아무런 변경을 하지 않습니다. af\_redirect 파라미터는 사용자가 클릭 후 랜딩 페이지에 도달한다는 것을 의미하기 때문입니다. 그러므로, 추가 어트리뷰션 링크가 필요하지 않습니다.

사용자가 어트리뷰션 링크 클릭 후 랜딩 페이지에 도달하는 경우, 스크립트가 어떻게 동작하는지에 대한 상세한 내용은 스크립트 내 **isAFLink()** 를 찾아 보세요.

</Accordion>

<div id="links-with-utm-parameters-dynamic-onelink" />

<Accordion title="파라미터가 있는 링크: 동적 원링크">

#### 설명

UTM 파라미터가 있는 링크를 사용하여 랜딩 페이지로 사용자를 리디렉션하는 트래픽 소스가 있습니다.

#### 결론:

원래 URL이 앱스플라이어 어트리뷰션 링크가 아니면, 스크립트는 그 링크에서  ***utm\_source***와 ***utm\_campaign*** 파라미터를 찾습니다. 이 파라미터들이 존재하면, 스크립트는 원링크 URL을 준비하고 원링크 URL에서 이들이 각각 미디어소스명(pid), 캠페인 이름(c)가 됩니다.

앱스플라이어 어트리뷰션 링크는 UTM 파라미터를 포함하기 때문에 UTM파라미터가 아니라 앱스플라이어 파라미터가 사용됩니다.

#### 지침:

미디어소스에서 하는 작업:

1. 링크에 ***utm\_source***가 존재하는지 확인하십시오.
2. ***utm\_campaign*** 파라미터는 선택사항이지만 있는 것이 훨씬 좋습니다.

랜딩 페이지 로드에서

1. ***generateUrl*** 자바스크립트 함수를 활성화하세요.
2. 함수가  ***utm\_source***와 ***utm\_campaign***파라미터를 검색하고 이 파라미터들의 값을 포함하는 원링크 URL을 생성합니다.
3. 랜딩 페이지의 앱 다운로드 버튼은 이렇게 생성된 원링크 URL을 사용합니다.
4. 신규 모바일 앱 사용자에 대해   ***utm\_source*** 파라미터의 값이 미디어소스로서 어트리뷰션으로 기록됩니다.
5. 미디어소스에 포스트백이 전송되지 않습니다.

#### 스크립트 동작

스크립트는 랜딩 페이지 URL에서 UTM 파라미터를 검색합니다. UTM 파라미터를 발견하면, 이를 원링크 파라미터로 변환합니다. 이런 식으로, 캠페인 정보가 최종 어트리뷰션으로 전달됩니다.

</Accordion>

<div id="mobile-organic-visitors-onelink-with-pidwebsite" />

<Accordion title="모바일 오가닉 방문자: pid=website인 원링크">

#### 설명

모바일 오가닉 사용자는 '알려지지 않은 소스에서 유입된 모바일 웹 리드(lead)'로 정의됩니다. 랜딩 페이지를 바로 방문하는 경우는 드물지만 모바일 앱을 설치하는 모바일 오가닉 사용자는 대부분 광고주의 웹사이트에서 유입될 수 있습니다.

#### 결론:

광고주의 웹사이트에서 모바일 앱으로 유입되는 오가닉 트래픽이 상당히 많은 경우에는, 어트리뷰션 데이터를 광고주 자사의 트래픽으로 기록하는 것이 좋습니다.

#### 지침:

모바일 오가닉 사용자를 어트리뷰션하려면, 웹사이트에 원링크 어트리뷰션 링크를 설정한 ***다운로드 버튼***이나 ***앱 설치*** 버튼이 있어야 합니다. 원링크는 디바이스 종류를 감지하여 감지된 디바이스에 따라 리드(lead)를 적절한 앱스토어로 안내합니다.

원링크 URL 설정 방법은 <Anchor target="_blank" href="/marketers/ko/docs/create-a-onelink-template">여기</Anchor>를 참조하십시오.

> 👍 **팁**
>
> "&pid=website"를 어트리뷰션 링크에 추가해 모든 모바일 오가닉 사용자를 귀사의 웹사이트로 어트리뷰션하십시오.
> 어트리뷰션 링크가 걸린 다운로드/앱 설치 버튼이 있는 모든 웹사이트 페이지에 "&c=`{PAGE NAME}`"를 추가하십시오. 그러면 웹사이트에서 전환율이 가장 높은 페이지와 가장 낮은 페이지를 찾을 수 있습니다.

#### 스크립트 동작

스크립트는 먼저 다른 어트리뷰션 방식들을 다 적용해서 검토한 후에, 신규 사용자가 캠페인으로 유입되지 않은 오가닉 사용자임을 확정합니다. 스크립트는 원링크를 생성하여 이 사실을 반영하고 랜딩 페이지의 다운로드 버튼 뒤에 생성된 원링크를 넣습니다.

</Accordion>

<div id="desktop-visitors-telephoneemail-form" />

<Accordion title="데스크톱 방문자: 전화/이메일 입력 양식">

#### 설명

위 모든 방식은 사용자가 캠페인과 랜딩 페이지에 반응하여 행동할 때, 모바일 디바이스를 이용한다는 전제 하에 가능합니다.

그러면 데시크톱 사용자는 어떻게 어트리뷰션할까요?

데스크톱 사용자는 랜딩페이지/웹사이트에 도착한 후 '독립적으로' 모바일 디바이스로 앱스토어를 방문하여 모바일 앱을 설치합니다. 모바일 디바이스로 참여하지 않는 사용자들을 어트리뷰션하기는 불가능합니다. 그래서 이들은 '오가닉'으로 분류됩니다.

#### 결론:

이러한 문제는 데스크톱 사용자일 경우, 랜딩 페이지에서 **앱 다운로드 메시지를 위한 양식** 을 사용하여 해결할 수 있습니다. 모바일 디바이스로 원링크 URL이 들어있는 SMS 문자메시지나 이메일을 보내는 방식입니다.

#### 지침:

1. 우선, 방문자가 데스크톱 사용자임을 인식합니다.
2. 사용자가 전화번호를 입력하면, 앱을 설치할 수 있는 원링크 숏링크 URL을 문자 메시지로 보냅니다. 랜딩 페이지에 이메일 주소를 입력하도록 하여 앱 다운로드 메시지를 이메일로 전송할 수도 있습니다.
3. 원링크를 사용하는 것이 여기에서 매우 중요합니다. 메시지 전송 시점에서는 모바일 디바이스 OS를 알 수 없기 때문입니다. 원링크는 자동으로 모바일 디바이스 OS를 감지하고 OS에 따라 알맞은 앱스토어로 리디렉션합니다.
4. 이 소스를 확인할 수 있도록 "&pid=desktop\_website" 를 원링크 URL에 추가하십시오.
5. "&c=`{PAGE NAME}`"을 추가하여 웹사이트에서 데스트톱 사용자의 전환율이 가장 높은 페이지와 가장 낮은 페이지를 확인하십시오.

#### 스크립트 동작

스크립트는 사용자가 접속한 디바이스나 OS를 감지합니다. 데스크톱이면, 스크립트는 웹 형식 URL로 이어지는 링크를 리턴하고, 이 링크를 다운로드 버튼 뒤에 놓습니다. 사용자가 다운로드 버튼을 클릭하면 개인 정보를 입력할 수 있는 웹 양식으로 이동하고, 여기에 입력한 정보, 즉, 핸드폰 번호나 이메일 주소로 앱 다운로드 링크가 전송됩니다.

스크립트에서 웹 양식을 사용하고 앱 다운로드 링크를 전송하는 것은 선택사항입니다. 상세 내용은 스크립트에서  **isMobileDevice()** 를 찾아 확인하십시오.

</Accordion>

## 랜딩 페이지 자바스크립트

각 랜딩 페이지 시나리오에서 미디어소스와 캠페인을 어트리뷰션하는 자바스크립트 코드 구현 방식을 아래에서 확인하십시오. **adset과 ad id같은 데이터를 추가하시려면, 스크립트를 필요에 맞춰 조정하십시오.**

첨부 랜딩 페이지 예시를 다운로드하실 수도 있습니다.

아래 코드 예시와 가이드를 보시고 귀사의 랜딩 페이지에 맞게 응용하십시오.

<div id="the-script" />

<Accordion title="스크립트">

스크립트를 구현하기 전 다음 사항을 숙지하십시오.

* 이 스크립트는 예시일 뿐입니다. 이 스크립트는 일반적인 랜딩 페이지 어트리뷰션 과정을 다룹니다. 이 스크립트를 귀사의 요건에 따라 응용하십시오.
* 이 스크립트는 랜딩 패이지 URL에서 미디어소스, 캠페인, 키워드 같은 특정 파라미터를 검색합니다. site ID나 ad set같은 파라미터를 추가하시려면, 이 스크립트를 그에 따라 변경해야 합니다.

```javascript
//Returns the value of a parameter existing in the page's URL or ' ' if not exists.
function getParameterFromURL(name, url) {
  if (!url) url = window.location.href;
  name = name.replace(/[\[\]]/g, '\\$&');
  var regex = new RegExp('[?&]' + name + '(=([^&#]*)|&|#|$)'),
    results = regex.exec(url);
  if (!results) return null;
  if (!results[2]) return '';
  return decodeURIComponent(results[2].replace(/\+/g, ' '));
}

function isMobileDevice() {
  return (typeof window.orientation !== "undefined") || (navigator.userAgent.indexOf('IEMobile') !== -1);
}

function getMobileOperatingSystem() {
  var userAgent = navigator.userAgent || navigator.vendor || window.opera;
  if (userAgent) {
    if (/android/i.test(userAgent)) {
      return "Android";
    }

    // iOS detection from: http://stackoverflow.com/a/9039885/177710
    if (/iPad|iPhone|iPod/.test(userAgent) && !window.MSStream) {
      return "iOS";
    }
  }
  return "unknown";
}

function isAFLink() {
  return getParameterFromURL('af_redirect');
}

// Note - when device ID sharing becomes optional stop calling this method (or always return false)
function isFacebook() {
  if (document.referrer && document.referrer != "") {
    return document.referrer.toLowerCase().includes('facebook');
  } else {
    return false;
  }
}

// generateUrl returns the URL to use behind the iOS and Android "Download" buttons on a landing page, based on the source of the page visitor.
// By default these buttons should direct to the apps' pages on iTunes and Google Play.
// If these links should be kept with no change, generateUrl returns ' '.
// Otherwise, generateUrl returns the URL to be used under BOTH buttons (a single app download button could also be used in this case).
// Parameters: isDebug - if true, alerts are issued for each of the cases, otherwise not.  	 
function generateUrl(isDebug) {
  var oneLinkURL = 'https://yourapp.onelink.me/abcd';   // **** Replace with your own basic OneLink URL ****
  var webFormURL = 'https://yoursite.com/webform.html'; // **** Replace with your own web form URL for getting the user's email or SMS ****
  var finalURL = "";
  var partnerIDParam = '?pid=';

  var campaignValue;
  if (getParameterFromURL('c')) {
    campaignValue = getParameterFromURL('c');
  } else if (getParameterFromURL('utm_campaign')) {
    campaignValue = getParameterFromURL('utm_campaign');
  } else if (document.getElementsByTagName('title')[0]) {
    campaignValue = document.getElementsByTagName('title')[0].innerText;
  } else {
    campaignValue = 'unknown';
  }
  var campaignParam = '&c=';
  var gclidParam = '&af_sub1=';
  var gclidValue = getParameterFromURL('gclid');
  var kwParam = '&af_keywords=';
  var pidValue;
  var kwValue = getParameterFromURL('keyword');

  if (getParameterFromURL('af_pid')) {
    pidValue = getParameterFromURL('af_pid');
  } else if (getParameterFromURL('utm_source')) {
    pidValue = getParameterFromURL('utm_source');
  }

  // Prevent the use of real SRN names. Remove this part after you are done testing the script.
    var SRNs = [
    'twitter_int',
    'facebook_int',
    'snapchat_int',
    'doubleclick_int',
    'yahoogemini_int',
    'yahoojapan_int',
  ];

  if (SRNs.includes(pidValue)) {
  	alert("DO NOT USE NAMES OF SRNS IN af_pid or utm_source - use the names listed in Other SRNs: Add Parameter section in the landing page article\nhttps://support.appsflyer.com/hc/en-us/articles/360000677217#other-srns-add-parameter");
    return;
  }

  // Desktop user
  if (!isMobileDevice()) {
    return webFormURL;
  }

  // User was redirected using af_r parameter on an AppsFlyer attribution link
  if (isAFLink()) {
    if (isDebug) {
      alert("This user comes from AppsFlyer by redirection and is ready to be attributed. \nKeep direct app store links.");
    }
    return; // in this case, the original store links in the install buttons stay the same

    /*
    If you want one install button in the landing page that serves both iOS and Android, uncomment the code below
    The code identifies the operating system and returns the relevant direct link to Google Play or iTunes

    if (getMobileOperatingSystem() === 'Android') {
      return 'direct link to Google Play';
    } 

    if (getMobileOperatingSystem() === 'iOS') {
      return 'direct link to iTunes';
    }
    */
  }

  // Google Ads
  if (gclidValue) {
    partnerIDParam += 'google_lp';
    campaignParam += campaignValue;
    gclidParam += gclidValue
    if (!kwValue) {
      finalURL = oneLinkURL + partnerIDParam + campaignParam + gclidParam;
      if (isDebug) {
        alert("This user comes from Google AdWords\n " + finalURL);
      }
      return finalURL;

    } else { // Google Ads with KW
      kwParam += kwValue;
      finalURL = oneLinkURL + partnerIDParam + campaignParam + gclidParam + kwParam;
      if (isDebug) {
        alert("This user comes from Google AdWords - there is a keyword associated with the ad\n " + finalURL);
      }
      return finalURL;
    }

  // Other SRNs and custom networks  
  } else if (pidValue) {
    campaignParam += campaignValue;
    partnerIDParam += pidValue;
    finalURL = oneLinkURL + partnerIDParam + campaignParam;
    if (isDebug) {
      alert("This user comes the SRN or custom network " + pidValue + "\n" + finalURL);
    }
    return finalURL;
  } else if (isFacebook()) {
    if (isDebug) {
      alert("This user comes from a paid Facebook ad - don't do anything. \nKeep direct app store links.");
    }
    return ' ';

  } else { // organic mobile user
    campaignParam += campaignValue;
    partnerIDParam += 'website'; //**** Replace value if you wish organic users to be attributed to another media source than 'website' ****
    finalURL = oneLinkURL + partnerIDParam + campaignParam;
    if (isDebug) {
      alert("This user comes from an unknown mobile source.\n The user would be attributed to media source 'website' and to the campaign " + campaignParam + "\n" + finalURL);
    }
    return finalURL;
  }
}
```

</Accordion>

<div id="html-sample-for-landing-page" />

<Accordion title="랜딩 페이지 HTML 예시">

```html Markup
<html>
<head>
  <title>Landing Page</title>
</head>
<body>
  <h1>Landing Page</h1>
  <!-- By default, the install buttons should have direct links to the stores -->
  <div>
    <a id="andrd_link" href="https://play.google.com/store/apps/details?id=com.appsflyer.sampleapp"><img src="/images/andrd.png"alt=""></a>
  </div>
  <div>
    <a id="ios_link" href="https://itunes.apple.com/us/app/id3********"><img src="/images/ios.png" alt=""></a>
  </div>
  <!-- If you want one button to serve both Android and iOS, use the code below instead
  <a id="store_link" href=""><img src="download.png" alt=""></a>
  -->
  <script type="text/javascript" src="/landing-page-test.js"></script>
  <script type="text/javascript">
    window.onload = function () {
      var url = generateUrl(true);

      // onelink is generated
      if (url) {
        document.getElementById('andrd_link').setAttribute('href', url);
        document.getElementById('ios_link').setAttribute('href', url);
      }

      //otherwise, if onelink is not generated it means that the user is redirected
      // and the store links in the buttons stay the same

      /* for the one button solution for both Android and iOS, use the code below instead

      document.getElementById('store_link').setAttribute('href', url);

      */

    };
  </script>
</body>

</html>
```

</Accordion>

> 👍 **팁**
>
> 구글 태그 매니저(Google Tag Manager)를 사용하여 자바스크립트 스니펫을 구현하세요. 구글 태그 매니저로 랜딩 페이지 자바스크립트가 언제 어디에서 사용될지 쉽게 컨트롤할 수 있습니다.

### 지침

1. 사용자가 바로 볼 수 있고 모바일 앱 ***다운로드*** 버튼이 있는 랜딩 페이지의 페이지 로드 시 ***generateUrl*** 스크립트를 활성화합니다.  

   > 🚧 **중요!**
   >
   > **기본적으로 *다운로드* 버튼이 iTunes와 구글 플레이로 리디렉션합니다.** 이러한 링크가 변경 없이 유지되는 경우(즉, AF 어트리뷰션 링크 또는 메타 광고의 방문자) ***generateUrl***에서 ' '를 반환합니다. 그렇지 않으면,이 URL이 두 다운로드 버튼(***원링크***를 사용하면 두 OS를 지원하는 하나의 다운로드 버튼)에 사용되는 URL을 리턴합니다.

2. ***oneLinkURL*** 파라미터 값을 자리 표시자 `https://yourapp.onelink.me/abcd`와 정확히 동일한 형식으로 기본 원링크 URL로 바꿉니다.  
   메타 광고 유료 광고를 제외한 모든 SRN으로부터 유입되는 방문자와 모바일 오가닉 사용자 어트리뷰션은 필수입니다.
3. ***webFormURL*** 파라미터 값을 귀사의 웹 양식 링크로 대체하세요. 웹 양식은 앱 다운로드용 원링크 URL을 담은 메시지를 사용자의 모바일 디바이스에 보낼 수 있도록 핸드폰 번호나 이메일 주소를 얻을 수 있도록 구성되어야 합니다.  
   데스크톱 접속자 어트리뷰션은 필수입니다.
4. 모바일 오가닉 사용자를 '웹사이트'가 아닌 다른 미디어소스에 어트리뷰션하기를 원한다면, ***partnerIDParam*** 파라미터 값을 변경하세요.
5. 기본적으로 사용자가 ***다운로드*** 버튼을 클릭하면 그 사용자가 있는 웹페이지가 어트리뷰션으로 기록됩니다. 랜딩 페이지 URL(`&c={CAMPAIGN_NAME}`)에 다른 캠페인 명이 명시되지 않으면, 기본 설정에 따라 웹사이트가 어트리뷰션 미디어소스로 기록됩니다. 이 기본 설정을 변경하려면, ***campaignParam*** 파라미터 값을 변경하십시오.  
   메타 광고 유료 광고를 제외한 모든 시나리오의 선택 사항입니다.

## 어트리뷰션 결과 조회하기

[![dashboard_landing_page_results.png](https://files.readme.io/29d7b6b096687a1f106efa4dcfc65ab1f550976516c87c3ffafde29f852855bb-360001342158.png)](https://files.readme.io/29d7b6b096687a1f106efa4dcfc65ab1f550976516c87c3ffafde29f852855bb-360001342158.png)

미디어소스에 따른 랜딩 페이지 어트리뷰션 결과를 앱 대시보드, 로데이터, 혹은 앱스플라이어 API로 확인하실 수 있습니다.

귀사의 마케팅 퍼널이 항상 랜딩 페이지에 이른다면, 각 미디어소스가 어트리뷰션으로 기록되는 신규 획득 사용자는 다음과 같습니다.

| **소스** | **설명** |
| --- | --- |
| **오가닉** | 랜딩 페이지를 거치지 않았거나, 랜딩 페이지에 반응하지 않은 사용자. 또는 참여했지만 다양한 이유로 어트리뷰션되지 않은 사용자(예: 앱을 실행하기 전에 어트리뷰션 룩백 윈도우 전달). |
| **웹사이트** | 랜딩 페이지/웹사이트를 방문한 후 앱을 설치한 오가닉 모바일 사용자 |
| **메타 광고** | 유료 메타 광고 사용자 |
| **fbpost\_lp** | 바이럴 무료 메타 광고 게시물의 사용자 |
| **google\_lp** | 구글 애즈로부터 유입된 사용자 |
| **[SRN]\_lp** | 타 SRN에서 유입된 사용자, 예: Twitter(twitter\_lp), Snapchat(snapchat\_lp), Doubleclick(doubleclick\_lp) 또는 Oath(oath\_lp) |
| **연동된 파트너 ID** | 앱스플라이어 어트리뷰션 링크를 사용하는 앱스플라이어와 연동된 파트너의 광고로부터 유입되는 사용자. 예: inmobi\_int, tapjoy\_int |
| **데스크톱** | 웹사이트 양식을 기입한 후 모바일로 받은 SMS 문자메시지나 모바일로 확인한 이메일에서 링크를 클릭하여 앱을 설치한 데스크톱 사용자 |
| **기타 소스** | 앱스플라이어 어트리뷰션 링크를 사용하는 온드 미디어(owned media) 소스에서 유입된 사용자. 예: 이메일, SMS 문자메시지, 블로그 포스트 등 |

## 랜딩 페이지에 원링크 활용하기

원링크(OneLink™)는 앱스플라이어 고유의 어트리뷰션 링크입니다. 디바이스 탐지와 리디렉션, 혹은 딥링킹에 사용하실 수 있습니다.

<Anchor target="_blank" href="/marketers/ko/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#social-app-landing-page">소셜 앱 랜딩 페이지</Anchor>를 사용하려면, 기본 원링크 URL이 있어야 합니다.  사용자가 소셜 미디어 앱에서 광고를 클릭하면, 앱스플라이어에서 만든 랜딩 페이지로 이동합니다. 사용자는 이 랜딩 페이지에서 딥링킹이 되거나 앱 설치를 계속할 수 있습니다.

앱스플라이어는 다양한 소셜미디어 앱 랜딩 페이지 템플릿을 제공합니다. 템플릿 구성 요소 위치는 고정되어 있지만, 배경 이미지 또는 색상, 제목, 텍스트, 이미지, 버튼, 태그 등을 포함하여 구성 요소 자체는 사용자 지정할 수 있습니다.

앱에 대한 원링크를 구현하지 않았다면,

1. <Anchor target="_blank" href="/marketers/ko/docs/create-a-onelink-template#원링크-템플릿-만들기">원링크 템플릿</Anchor>을 구성합니다.
2. 원링크 템플릿을 사용하여<Anchor target="_blank" href="/marketers/ko/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#캠페인을-위한-원링크-링크-생성하기">원링크 URL</Anchor>을 만드십시오.
3. 스크립트에서 [https://yourapp.onelink.me/abcd](https://yourapp.onelink.me/abcd)를 귀사의 원링크 URL로 대체하십시오.

<div data-zendesk-anchors="the-upsides=%EC%9E%A5%EC%A0%90 the-downsides=%EB%8B%A8%EC%A0%90 the-challenges-of-mobile-attribution-on-landing-pages=%EB%AA%A8%EB%B0%94%EC%9D%BC-%EB%9E%9C%EB%94%A9-%ED%8E%98%EC%9D%B4%EC%A7%80-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98%EC%9D%B4-%EC%96%B4%EB%A0%A4%EC%9A%B4-%EC%9D%B4%EC%9C%A0 the-solution=%EC%86%94%EB%A3%A8%EC%85%98 landing-page-scenarios=%EB%A7%A4%EC%B2%B4%EB%B3%84-%EB%9E%9C%EB%94%A9-%ED%8E%98%EC%9D%B4%EC%A7%80-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%EC%8B%9C%EB%82%98%EB%A6%AC%EC%98%A4 description=%EC%84%A4%EB%AA%85 conclusion=%EA%B2%B0%EB%A1%A0 instructions=%EC%A7%80%EC%B9%A8 what-the-script-does=%EC%8A%A4%ED%81%AC%EB%A6%BD%ED%8A%B8-%EB%8F%99%EC%9E%91 description::7888dd9d=%EC%84%A4%EB%AA%85-1 conclusion::11bed45=%EA%B2%B0%EB%A1%A0-1 instructions::5aa3290f=%EC%A7%80%EC%B9%A8-1 what-the-script-does::2a675257=%EC%8A%A4%ED%81%AC%EB%A6%BD%ED%8A%B8-%EB%8F%99%EC%9E%91-1 description::650e3f28=%EC%84%A4%EB%AA%85-2 conclusion::a982e4bd=%EA%B2%B0%EB%A1%A0-2 instructions::afffc83f=%EC%A7%80%EC%B9%A8-2 what-the-script-does::3fd4ce35=%EC%8A%A4%ED%81%AC%EB%A6%BD%ED%8A%B8-%EB%8F%99%EC%9E%91-2 description::9c3fcdaa=%EC%84%A4%EB%AA%85-3 conclusion::bf993a93=%EA%B2%B0%EB%A1%A0-3 instructions::350b4cb1=%EC%A7%80%EC%B9%A8-3 what-the-script-does::3dda504d=%EC%8A%A4%ED%81%AC%EB%A6%BD%ED%8A%B8-%EB%8F%99%EC%9E%91-3 description::5150e1b5=%EC%84%A4%EB%AA%85-4 conclusion::d51c1aec=%EA%B2%B0%EB%A1%A0-4 instructions::e083609=%EC%A7%80%EC%B9%A8-4 what-the-script-does::85ffec6c=%EC%8A%A4%ED%81%AC%EB%A6%BD%ED%8A%B8-%EB%8F%99%EC%9E%91-4 description::f5a2038b=%EC%84%A4%EB%AA%85-5 conclusion::4593a93c=%EA%B2%B0%EB%A1%A0-5 instructions::2e4dd2ee=%EC%A7%80%EC%B9%A8-5 what-the-script-does::d6370587=%EC%8A%A4%ED%81%AC%EB%A6%BD%ED%8A%B8-%EB%8F%99%EC%9E%91-5 description::e20640cf=%EC%84%A4%EB%AA%85-6 conclusion::c818491=%EA%B2%B0%EB%A1%A0-6 instructions::ba61ae3e=%EC%A7%80%EC%B9%A8-6 what-the-script-does::3668d917=%EC%8A%A4%ED%81%AC%EB%A6%BD%ED%8A%B8-%EB%8F%99%EC%9E%91-6 landing-page-javascript=%EB%9E%9C%EB%94%A9-%ED%8E%98%EC%9D%B4%EC%A7%80-%EC%9E%90%EB%B0%94%EC%8A%A4%ED%81%AC%EB%A6%BD%ED%8A%B8 instructions::10da52a9=%EC%A7%80%EC%B9%A8-7 viewing-the-results=%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%EA%B2%B0%EA%B3%BC-%EC%A1%B0%ED%9A%8C%ED%95%98%EA%B8%B0 onelink-for-landing-page-solution=%EB%9E%9C%EB%94%A9-%ED%8E%98%EC%9D%B4%EC%A7%80%EC%97%90-%EC%9B%90%EB%A7%81%ED%81%AC-%ED%99%9C%EC%9A%A9%ED%95%98%EA%B8%B0" />
