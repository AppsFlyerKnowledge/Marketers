---
title: '[레거시] OneLink Smart Script V1 설정'
deprecated: true
metadata:
  keywords:
    - OneLink
    - Advertisers
    - Developers
    - Marketers
    - Smart Banners and Scripts
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-asaf-mashiah
    - Marketers
    - Smart Banners and Scripts
  created_at: '2022-01-02T17:00:19Z'
  edited_at: '2026-10-14T10:37:34Z'
  id: 4415354290321
  locale: ko
  section: Web-to-app attribution
  section_id: 6551240476177
  url: https://support.appsflyer.com/hc/ko/articles/4415354290321
---
> **한눈에 보기:** 요약: 원링크 스마트 스크립트를 설정하여 모든 소스에서 온 모바일 웹 사이트 방문자를 모바일 앱 사용자로 전환하고 어트리뷰트합니다. **참고**: 일러두기: 필수 사항은 아니지만 OneLink Smart Script V2로 마이그레이션하는 것을 고려해 보십시오.

![7901_Smart_Script_flow_1920x1080_2__1_.png](https://files.readme.io/5181971c27e89974a86afeb83f48eb5c127b64765334bc3b5644ed47adb974e8-30193884510225.png)

<div id="setup" />

## 설정

OneLink Smart Script는 두 가지 버전이 있습니다.

개발자 작업 부분이 더 쉬우며 Google Tag Manager를 사용하여 설정할 수도 있습니다. **참고**: 일러두기: 필수 사항은 아니지만 V2로의 마이그레이션을 고려해 보십시오.

OneLink Smart Script V1(레거시) 설정

<div id="responsibilities" />

<Accordion title="책임">

| **담당자**<ul><li>**마케터**:<ul><li>나가는 URL에 포함할 내용을 결정합니다. 여기에는 링크에 추가할 어트리뷰트 데이터와 딥링킹에 필요한 데이터가 포함됩니다. 들어오는 URL을 조작하거나 특정 값을 강제로 적용합니다.</li><li>모바일 웹 사이트로 연결되는 모든 캠페인에 스크립트가 작동하는 파라미터를 포함한 들어오는 URL이 있는지 확인합니다.</li></ul></li><li>**웹 개발자**:<ul><li>스크립트를 초기화할 데이터를 설정합니다.</li><li>마케터가 제공한 들어오는 URL 파라미터를 기준으로 나가는 원링크 URL을 생성하는 데 필요한 설정자를 입력합니다. 여기에는 필수 및 선택적 파라미터가 포함됩니다.</li><li>웹 사이트 또는 특정 페이지에 스크립트를 내장합니다.</li></ul></li></ul> |
| --- |
| **필수 조건**<ul><li>최소 1개 이상의 앱이 있는 앱스플라이어 계정이 필요합니다.</li><li><Anchor target="_blank" href="/marketers/ko/docs/create-a-onelink-template#원링크-템플릿-만들기">원링크 템플릿</Anchor>은 [OneLinkURL 파라미터](/docs/legacy-onelink-smart-script-v1-setup#parameters)의 값으로 사용됩니다.</li></ul> |

**웹 페이지에서 스크립트를 구현하는 방법**:

1. 자동으로 생성된 나가는 원링크 URL에 포함할 파라미터/값을 결정합니다. 사용할 수 있는 [파라미터 목록](/docs/legacy-onelink-smart-script-v1-setup#parameters)을 참조하십시오.
   * 들어오는 URL이 있는 모든 캠페인에 스크립트가 적용되는 파라미터가 있는지 확인합니다(그리고 **pid** 및 **c** 파라미터로 배치 가능).
2. 웹 개발사에 [파라미터](/docs/legacy-onelink-smart-script-v1-setup#parameters) 목록을 제공합니다.
3. 개발사에 <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/onelink-smart-script">개발 지침</Anchor>을 따르고 스크립트를 구현하여 올바른 나가는 링크를 생성하도록 지시합니다.

</Accordion>

<div id="parameters" />

<Accordion title="파라미터">

<div id="parametersvalues-provided-to-the-developer-to-implement-the-smart-script" />

#### 스마트 스크립트를 구현하기 위해 개발사에게 제공하는 파라미터/값

| 파라미터/값 | 비고 | 응답(개발자가 사용할) 기록 |
| --- | --- | --- |
| 원링크 URL(필수) | <ul><li>원링크 템플릿 도메인 + 템플릿 ID를 제공합니다. **참고: 일러두기: 원링크 사용자정의 링크 URL이 아닙니다!**</li><li>예: **yourbrand.onelink.me/A1b2**</li><li>브랜드 도메인 예: **click.yourbrand.com/A1b2**</li></ul> |  |
| pidKeysList (미디어소스) | <ul><li>내보내는 URL에서 미디어소스(pid) 파라미터로 배치될 내보내는 URL의 모든 미디어소스 파라미터를 나열합니다.</li><li>예: ['af\_pid', 'utm\_source']</li></ul> |  |
| pidOverrideList | <ul><li>나가는 링크에서 변경하려는 미디어소스의 경우 미디어소스 값을 들어오는 URL에 대체할 미디어소스 값과 함께 나열합니다.</li><li>예시</li></ul><br />'some\_social\_net': 'some\_social\_net\_int'<br />} |  |
| pidStaticValue | <ul><li>"폴백" 미디어소스를 원하는 대로 설명합니다.</li><li>pidKeysList에서 미디어소스 파라미터를 찾을 수 없는 경우 나가는 URL에서 pidStaticValue가 미디어소스(pid)로 사용됩니다.</li><li>예: 'website' 또는 'landing\_page'</li></ul> |  |
| campaignKeysList(캠페인) | <ul><li>나가는 URL에서 캠페인(c) 파라미터로 배치될 들어오는 URL의 모든 캠페인 파라미터를 나열합니다.</li><li>예: ['af\_campaign', 'utm\_campaign']</li></ul> |  |
| campaignStaticValue | <ul><li>"폴백" 캠페인이 무엇이길 원하는지 설명하십시오.</li><li>campaignKeysList에서 캠페인 파라미터를 찾을 수 없는 경우 campaignStaticValue가 나가는 URL에서 캠페인(c)으로 사용됩니다.</li><li>예: 'website' 또는 'landing\_page'</li></ul> |  |
| gclIdParam | <ul><li><Anchor target="_blank" href="https://support.google.com/google-ads/answer/9744275?hl=en">GCLID</Anchor>를 전달하는 파라미터를 호출할 내용을 설명합니다.<br />**참고**! 앱스플라이어 로데이터 리포트에 표시하려면 파라미터가 **af\_sub[1-5]** 중 하나여야 합니다.</li></ul> |  |
| skipList | <ul><li>특정 클릭에 대해 스마트 스크립트를 비활성화하는 문자열을 HTTP 리퍼러에 나열합니다(예: 트위터 또는 페이스북). 문자열이 나타나면 스마트 스크립트가 실행되지 않습니다. 이런 기능은 클릭이 이미 리포트되는 트위터 및 페이스북과 같은 SRN에 유용할 수 있습니다.</li><li>SRN에서조차도 스마트 스크립트가 항상 실행되기를 원하는 경우, 개발자에게 빈 skiplist를 전달하라고 알려주십시오.</li></ul> |  |
| 다른 쿼리 파라미터 | <ul><li>어트리뷰션 또는 딥링킹을 위해 나가는 원링크 URL에 포함할 다른 파라미터를 나열합니다.</li><li>딥링킹을 위한 **deep\_link\_value**를 추가합니다.<ul><li>파라미터를 추가하는 것 외에도, 사용자와 개발자는 딥링킹 논리를 구현해야 합니다. <Anchor target="_blank" href="/marketers/ko/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#캠페인을-위한-원링크-링크-생성하기">더 알아보기</Anchor>.</li></ul></li><li>들어오는 URL의 파라미터를 사용하거나 정적 값을 강제 적용할 수 있습니다.</li></ul> |  |

</Accordion>

<div id="use-cases" />

## 활용 사례

다음 섹션에서는 일반적인 캠페인/미디어소스 시나리오에서 스마트 스크립트 사용 사례를 제공합니다.

<div id="facebook-ads-crossplatform-attribution" />

<Accordion title="메타 광고 : 크로스 플랫폼 기여">

메타 광고는 외부 기여 링크를 사용하지 않는 SRN입니다.

앱이 처음 실행되면, 앱스플라이어는 이 사용자가 이전에(최근 <Anchor target="_blank" href="/marketers/ko/docs/meta-ads-discrepancies#클릭-쓰루-및-뷰-쓰루-어트리뷰션">7일</Anchor> 이내) 앱 광고에 반응(클릭/조회)한 적이 있는지 페이스북에 문의합니다. 사용자가 광고주의 Facebook 광고에 참여한 경우 메타 광고는 자체 속성을 부여합니다. 메타 광고는 또한 크로스 플랫폼에 어트리뷰션하며, 이는 사용자가 모든 플랫폼에서 모바일이든 아니든 모든 유형의 캠페인과 상호작용하여 메타 광고에 의해 자체 어트리뷰션할 수 있음을 의미합니다.

작업 번호

**참고**: 일러두기: 2021년 기간에 iOS 14 사용자와 예상대로 사용자가 기기 ID를 공유하지 않을 경우 Facebook 크로스 플랫폼 어트리뷰션이 영향을 받을 수 있습니다.

</Accordion>

<div id="google-ads-gclid-and-utm-parameters" />

<Accordion title="Google 광고 — GCLID 및 UTM 파라미터">

Google 광고 캠페인의 인스톨 어트리뷰션(GCLID 파라미터를 포함하는)을 위한 일반적인 프로세스에서는 클릭할 때 앱 스토어 페이지 URL로 리디렉션해야 합니다.

이 경우 Google 광고에서 웹/랜딩 페이지로 리드를 리디렉션하므로 스크립트는 Google 광고 인스톨 캠페인 URL에서 GCLID 파라미터를 가져와서 출력 파라미터 **af\_sub[1-5]** 를 선택할 때 나가는 URL에 넣습니다. **참고!** 이것은 인스톨 캠페인에 적용됩니다. 리인게이지먼트 캠페인을 의미하는 비 ACI 검색 캠페인의 경우 스마트 스크립트 출력에도 불구하고 Google이 미디어소스로 어트리뷰트될 수 있습니다.

**선행 조건**: 

**Google 광고용 스크립트를 설정하는 방법**:

1. 들어오는 링크에 있는 미디어소스 및 캠페인의 파라미터 이름 목록을 만듭니다.  
   예를 들어: **utm\_source** 및 **utm\_campaign**.
2. 나가는 URL에서 GCLID를 포함할 파라미터를 선택합니다.  
   모범 사례: 모범 사례: 데이터가 앱스플라이어 로데이터 리포트에 표시되도록 **af\_sub[1-5]** 를 선택합니다.
3. [파라미터 목록](/docs/legacy-onelink-smart-script-v1-setup#parameters) 의 값들을 웹 개발자에게 제공합니다.

결과:

* 들어오는 링크의 미디어소스와 캠페인 파라미터(utm\_source 및 **utm\_campaign**)의 값은 내보내는 링크의 **pid** 및 **c** 파라미터 값을 채우는 데 사용됩니다.
* 나가는 URL에서 GCLID는 **af\_sub[1-5]** 파라미터의 값입니다.

**이러한 인스톨에 대해 Google 광고에 알리는 방법:**

1. 각 인스톨에 대해 CSV 또는 푸시 API를 통해 실시간으로 파라미터 af\_sub[1-5]에서 GCLID 데이터를 가져옵니다.
2. 수동으로 또는 <Anchor target="_blank" href="https://support.google.com/adwords/answer/7014069">Adwords API</Anchor>를 통해 GCLID 데이터를 Google에 업로드합니다.

<div id="note" />

> 📘 **참고사항**
>
> GCLID 솔루션은 구글이 공식적으로 지원하거나 권고하지 않습니다. 구글이 GCLID 파라미터를 삭제하는 경우, 앱스플라이어는 그에 따라 스크립트를 변경하겠습니다. 이 문서 헤더 부분 왼쪽에서 **팔로우**버튼을 클릭하여 이 문서를 팔로우하면 이 문서나 첨부 스크립트가 업데이트할 때 알림을 받으실 수 있습니다.

</Accordion>

<div id="srns-owned-media-and-other-media-source-links" />

<Accordion title="SRN, 온드 미디어 및 기타 미디어소스 링크">

Snapchat 또는 X Ads와 같은 <Anchor target="_blank" href="/marketers/ko/docs/self-reporting-networks-srns#앱스플라이어와-통합된-srn">SRN</Anchor> 은 Google Ads 또는 Meta 광고와 같은 크로스 플랫폼과 다르게 작동합니다. SRN에서 집행하는 캠페인으로부터 사용자가 웹/랜딩 페이지로 유입되면 앱을 실제로 설치한 사용자가 아니라 광고를 클릭해서 랜딩 페이지까지만 도달한 사람 기준으로 광고비가 발생합니다.

이러한 SRN의 경우 스크립트 설정은 온드 미디어 또는 사용할 수 있는 다른 미디어소스의 링크에 대한 설정과 동일합니다.

**스크립트 설정 방법**:

1. 들어오는 링크에 있는 미디어소스 및 캠페인의 파라미터 이름 목록을 만듭니다.
2. 파라미터 목록 [의 값들을 웹 개발자에게 제공합니다.](/docs/legacy-onelink-smart-script-v1-setup#parameters)  
    나가는 pid를 변경하려면 들어오는 미디어소스 값과 대체 pid 값을 pid 재지정 목록에 입력하십시오.

**결과**: 결과: 이러한 SRN/미디어소스의 경우 미디어소스의 값과 들어오는 링크의 캠페인 파라미터는 나가는 링크의 **pid** 및 **c** 파라미터의 값을 채우는 데 사용됩니다.

<div id="example" />

> 📄 **예시**
>
> **들어오는 URL**: https://hotel.me/af_pid=twitter&af_c=big_social
>
> **나가는 URL**: https://hotel.onelink.me/Ac4G?pid=twitter&c=big_social

</Accordion>

<div id="appsflyer-attribution-links" />

<Accordion title="앱스플라이어 어트리뷰션 링크">

앱스플라이어 어트리뷰션 링크는 미디어소스가 클릭 광고 네트워크일 때 사용할 수 있습니다. 앱스플라이어에서 이러한 링크를 설정할 때 웹 캠페인-앱 어트리뷰트를 위해 원하는 URL 경로가 포함된 **리디렉션 URL 경로(af\_r)** 파라미터를 모바일 웹 사이트에 추가할 수 있습니다.

결과: 결과: af\_r 및 **af\_redirect=true** 파라미터는 들어오는 링크에 있으며 랜딩 페이지 스크립트는 변경되지 않습니다. 웹/랜딩 페이지의 앱스토어 바로가기 링크를 그대로 둡니다.

<div id="example-1" />

> 📄 **예시**
>
> **들어오는 URL**: https://app.appsflyer.com/id123456789?pid=click_ad_network_int&c=orlando&af_redirect=true&af_r=hotel.me
>
> **나가는 URL**:

</Accordion>

<div id="desktop" />

<Accordion title="데스크톱">

그러나 데스크톱 사용자는 기기(데스크톱 또는 랩톱)가 모바일 앱 다운로드와 호환되지 않으므로 앱 스토어로 즉시 전송되지 않습니다.

**데스크톱 사용자용 스크립트 설정 방법**:

* <Anchor target="_blank" href="/marketers/ko/docs/create-a-onelink-template#원링크-템플릿-만들기">원링크 템플릿</Anchor>의 경우 **데스크톱에서 링크를 클릭하면** 대상 URL을 설정합니다. URL은 전용 웹/랜딩 페이지로 리디렉션되어야 합니다. 랜딩 페이지에는 세부 정보를 입력하여 SMS 또는 앱을 다운로드할 수 있는 링크가 포함된 이메일을 받을 수 있는 웹 양식이 포함될 수 있습니다. 스크립트에서 웹 양식을 사용하고 앱 다운로드 링크를 전송하는 것은 선택사항입니다.

**결과**: 스크립트는 사용자가 접속한 디바이스나 OS를 감지합니다. 데스크톱인 경우 스크립트는 사용자를 전용 웹/랜딩 페이지로 리디렉션하는 나가는 원링크 URL을 생성합니다.

<Anchor target="_blank" href="/marketers/ko/docs/qr-to-app-conversion">데스크톱 투 앱 전환</Anchor>을 참조하십시오.

</Accordion>

<div id="limitations" />

<Accordion title="제한 사항">

| 제한 사항 | 비고 |
| --- | --- |
| 태그 관리자 | 스마트 스크립트는 태그 관리자를 통해 구현할 수 없습니다. 웹-투-앱 어트리뷰션의 대체 솔루션으로 <Anchor target="_blank" href="/marketers/ko/docs/set-up-smart-script-to-convert-web-visitors">OneLink Smart Script V2</Anchor> 또는 <Anchor target="_blank" href="/marketers/ko/docs/smart-banners-mobile-web-to-app-for-marketers">Smart Banners</Anchor>를 참조하십시오. |

</Accordion>

<div data-zendesk-anchors="setup=%EC%84%A4%EC%A0%95 h_01HDNWHSY8HM30HV1PAF5C3M4E=%EC%84%A4%EC%A0%95 h_01HDNWHSY8J65EB1RZCFP1606H=responsibilities h_01HDNWHSY8CH29FQ2V5DCG2XSP=parameters parametersvalues-provided-to-the-developer-to-implement-the-smart-script=%EC%8A%A4%EB%A7%88%ED%8A%B8-%EC%8A%A4%ED%81%AC%EB%A6%BD%ED%8A%B8%EB%A5%BC-%EA%B5%AC%ED%98%84%ED%95%98%EA%B8%B0-%EC%9C%84%ED%95%B4-%EA%B0%9C%EB%B0%9C%EC%82%AC%EC%97%90%EA%B2%8C-%EC%A0%9C%EA%B3%B5%ED%95%98%EB%8A%94-%ED%8C%8C%EB%9D%BC%EB%AF%B8%ED%84%B0%EA%B0%92 h_01HDNWHSY8WSPX47VB43MC516Q=%EC%8A%A4%EB%A7%88%ED%8A%B8-%EC%8A%A4%ED%81%AC%EB%A6%BD%ED%8A%B8%EB%A5%BC-%EA%B5%AC%ED%98%84%ED%95%98%EA%B8%B0-%EC%9C%84%ED%95%B4-%EA%B0%9C%EB%B0%9C%EC%82%AC%EC%97%90%EA%B2%8C-%EC%A0%9C%EA%B3%B5%ED%95%98%EB%8A%94-%ED%8C%8C%EB%9D%BC%EB%AF%B8%ED%84%B0%EA%B0%92 use-cases=%ED%99%9C%EC%9A%A9-%EC%82%AC%EB%A1%80 h_01HDNWHSY8N77ZH4CK49ZQ2KZB=%ED%99%9C%EC%9A%A9-%EC%82%AC%EB%A1%80 facebook-ads%E2%80%94crossplatform-attribution=facebook-ads-crossplatform-attribution h_01HDNWHSY85QFABA6FAX1XTEPE=facebook-ads-crossplatform-attribution google-ads%E2%80%94gclid-and-utm-parameters=google-ads-gclid-and-utm-parameters h_01HDNWHSY878JTPZSN719KF1Y5=google-ads-gclid-and-utm-parameters h_01HDNWHSY8BJH39TAN46W7HE4G=%EC%B0%B8%EA%B3%A0%EC%82%AC%ED%95%AD h_01HDNWHSY8NER2M8X4DGHCWYPJ=srns-owned-media-and-other-media-source-links h_01HDNWHSY828Q587S28GYB85VR=%EC%98%88%EC%8B%9C h_01HDNWHSY8K1AFSEA1RY04KXJ9=appsflyer-attribution-links h_01HDNWHSY8DDTA6VATN0XXBEY5=%EC%98%88%EC%8B%9C-1 h_01HDNWHSY821DADGKATKH12PSJ=desktop h_01HDNWHSY80QA9CC4S2BPBTJYG=limitations" />
