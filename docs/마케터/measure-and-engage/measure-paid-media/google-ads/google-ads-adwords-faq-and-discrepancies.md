---
title: Google Ads(AdWords)—자주 묻는 질문 및 불일치
metadata:
  keywords:
    - Advertisers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
  created_at: '2022-01-20T10:06:31Z'
  edited_at: '2026-10-14T10:33:22Z'
  id: 4417303339921
  locale: ko
  section: Google Ads
  section_id: 6551205645457
  url: https://support.appsflyer.com/hc/ko/articles/4417303339921
---
> **요약: 요약: Google Ads와 관련된 일반적인 문제 및 불일치를 해결합니다.**

## Google Ads FAQ

<div id="why-am-i-not-seeing-clicks-from-google-ads" />

<Accordion title="왜 구글 애즈 클릭 수를 볼 수 없습니까?">

집약 클릭 및 노출 데이터는 <Anchor target="_blank" href="/marketers/ko/docs/google-ads-adwords-integration-setup-for-advertisers#step-2-set-up-google-ads-on-appsflyer-mandatory">비용, 클릭 및 노출 데이터 연동</Anchor>을 **비용** 연동 탭에서 승인했을 때, Google Ads로부터 받을 수 있습니다.

구글 애즈의 클릭 수 및 노출 수 데이터는 2018년 8월에 안드로이드 앱 용으로 먼저 처음 사용되었으며 나중에 iOS 앱 용으로도 제공되었습니다. 따라서 2018년과 그 이전의 클릭 수 데이터를 분석할 때 구글 애즈 클릭 수 데이터가 누락되거나 불완전 할 수 있습니다.

</Accordion>

<div id="why-am-i-not-seeing-first_open-conversions-on-google-ads" />

<Accordion title="왜 구글 애즈에서 first_open 전환을 볼 수 없습니까?">

만약 아래 스크린샷처럼 구글 애즈에서 first\_open 전환을 볼 수 없다면:

![AW_13.png](https://files.readme.io/082f79266fced9fc012cdb373321a836129205992adbe29f7509321516e8f5ab-33743114088849.png)

구글 애즈로 전환을 가져와야 합니다. <Anchor target="_blank" href="/marketers/ko/docs/google-ads-adwords-integration-setup-for-advertisers#step-4-measure-your-app-conversions-mandatory">전환 가져오기</Anchor>에 대한 안내를 참고하십시오.

</Accordion>

<div id="why-don-t-i-see-installs-from-google-ads" />

<Accordion title="왜 Google Ads에서 설치가 보이지 않나요?">

누락된 설치 문제를 해결하기 위해 이 체크리스트를 따르세요:

#### 빠른 수정

1. **AppsFlyer에서 Google Ads 활성화**  
   AppsFlyer에서 사이드바에서 **협업 > 활성 통합**을 열고, **Google Ads**를 검색하여 통합이 활성화되어 있는지 확인하세요.
2. **Google Ads에서** `first_open`**전환 가져오기**  
   Google Ads에서 <Anchor target="_blank" href="https://ads.google.com/aw/conversions">전환 요약</Anchor> 페이지로 이동하여 `first_open` 전환 이벤트가 가져와졌는지 확인하세요. 자세한 내용은 앱 전환 가져오기를 참조하세요.

#### 아직도 작동하지 않나요?

1. **어떤 Google Ads 계정이 전환을 가져오는지 확인하세요**  
   어떤 **Google Ads MCC 계정 또는 하위 계정**이 전환 가져오기를 담당하는지 확인하세요:

   * **MCC(관리 계정)를 사용하는 경우:** MCC는 모든 연결된 하위 계정을 대신하여 `first_open` 전환을 가져와야 합니다.
   * **하위 계정을 사용하는 경우:**
     * MCC는 하위 계정과 **링크 ID**를 공유해야 합니다.
     * 하위 계정은 **전환을** `first_open`**직접 가져와야 합니다**.

   Google Ads MCC 계정에 대한 자세한 내용은 다음을 참조하세요: <Anchor target="_blank" href="/marketers/ko/docs/recording-multiple-agency-mcc-google-ads-accounts#mcc">MCC</Anchor>.
2. <strong>제거된</strong> `first_open`전환&lt;3> 확인하기  
   <Anchor target="_blank" href="https://ads.google.com/aw/conversions">전환 요약</Anchor> 페이지에서 `first_open` 전환 이벤트가 제거되었는지 확인하세요. 제거된 경우, 지원을 위해 Google 지원에 문의하세요.
3. **링크 ID 확인**  
   앱스플라이어의 링크 ID가 구글 광고의 링크 ID와 일치하는지 확인하세요.

</Accordion>

<div id="why-dont-i-see-inapp-events-in-the-google-ads-dashboard" />

<Accordion title="구글 광고 대시보드에서 인앱 이벤트가 보이지 않는 이유는 무엇인가요?">

이 체크리스트를 사용하여 앱스플라이어와 구글 광고 간에 인앱 이벤트가 올바르게 설정되고 동기화되었는지 확인하세요.

#### 빠른 수정 체크리스트

가장 일반적인 문제를 신속하게 해결하기 위해 다음 단계를 따르세요:

1. **앱스플라이어에서 이벤트 포스트백 확인** (단계별 지침은 <Anchor target="_blank" href="/marketers/ko/docs/google-ads-adwords-integration-setup-for-advertisers#step-3-map-your-inapp-events-recommended">앱스플라이어에서 구글 광고 설정하기.</Anchor>를 참조하세요.)
   1. 앱스플라이어의 **구글 광고 통합 탭**으로 이동하세요.
   2. 측정하려는 각 인앱 이벤트에 대해 포스트백이 올바르게 구성되었는지 확인하세요.
   3. <strong>사용자 출처</strong>에서 <em>모든 미디어 소스(유기적 포함)</em>를 선택하여 구글 광고가 이벤트 데이터를 수신하도록 하세요.
   4. (선택 사항) 초기 설정 후 필요에 따라 특정 이벤트에 대한 이 선택을 조정하세요.
2. **테스트 인앱 이벤트 트리거**
   1. 앱을 실행하세요.
   2. iOS 앱의 경우, 앱이 추적할 수 있도록 IDFA 수집이 활성화되어 있는지 확인하세요.
   3. 매핑된 인앱 이벤트를 수동으로 수행하세요(예: 구매 또는 가입).
3. **구글 광고에서 이벤트 가져오기**
   1. 구글 광고에서 **도구 변환**을 클릭하세요.
   2. **변환 작업 요약**을 확인하세요.
   3. 관련 인앱 이벤트를 가져오세요. 자세한 내용은 앱 변환 가져오기를 참조하세요.

      > 📘 **참고**
      >
      > 전환은 이벤트를 수행한 후 최대 6시간이 걸려 나타날 수 있습니다.


#### 아직도 작동하지 않나요?

Google Ads에서 파트너 이벤트 식별자를 수정한 경우(예: `CUSTOM`로 레이블이 지정된 경우) 및 AppsFlyer에서 해당 이벤트 이름을 변경한 경우, 이벤트를 Google Ads로 다시 가져와야 합니다.

</Accordion>

<div id="can-i-stop-google-cost-sync" />

<Accordion title="구글 비용 동기화를 중지할 수 있습니까?">

구글과 비용 동기화를 중지하려면:

1. <Anchor target="_blank" href="https://myaccount.google.com/permissions">구글 계정 액세스 권한</Anchor> 페이지로 이동합니다.
2. AppsFlyer Google Cost 옆의 제거 버튼을 클릭합니다.   
   ![remove_appsflyer_cost.png](https://files.readme.io/56840e708c98875c8db176c642dd324150a76aef9697fcc2756f524b2a6c0a16-33743128661137.png)

</Accordion>

<div id="do-i-need-to-create-and-then-import-session_start" />

<Accordion title="session_start를 생성하고 가져오기 해야합니까?">

운영중인 캠페인 유형에 따라 다릅니다. 재참여 캠페인을 운영하는 경우 `session_start`session\_startsession\_start 를 만들고 가져오기 하여 참여를 측정하는 편이 좋습니다.

유저 유입 캠페인의 경우, 필수는 아닙니다.

</Accordion>

<div id="can-i-send-uninstall-information-to-google-ads" />

<Accordion title="앱 삭제 정보를 구글 애즈에 보낼 수 있습니까?">

네.  
네. **구글로 앱 삭제 이벤트를 전송 시작하려면:**

1. Google Ads 파트너 연동 설정 창에서 af\_uninstall 이벤트를 CUSTOM 이벤트로 매핑합니다.
2. 구글에서 해당 전환을 가져오기 합니다.
3. 구글은 구글의 어트리뷰션 윈도우 내에 수신된 이벤트만 인식합니다. (광고 참여로 부터 시작해서 30-90일) 구글이 해당 기간 이후에 수신한 이벤트는 구글에 기록되지 않습니다.

</Accordion>

<div id="what-google-ads-data-does-appsflyer-display" />

<Accordion title="앱스플라이어가 표시하는 Google Ads 데이터는 무엇입니까?">

캠페인, 채널, 세트 및 지역 수준에서 데이터를 볼 수 있습니다.

</Accordion>

<div id="do-i-need-to-configure-anything-to-create-audience-lists-in-google-ads-based-on-appsflyer-data" />

<Accordion title="앱스플라이어 데이터를 기반으로 구글 애즈에서 잠재 고객 목록을 만들려면 무언가를 구성해야 합니까?">

아니오. 구글 API에서 이 정보는 이미 설정되어 있으며 인앱 이벤트 설정을 기반으로합니다.

</Accordion>

<div id="im-running-an-app-campaign-why-cant-i-see-data-or-conversion-events-in-the-appsflyer-or-google-ads-dashboard" />

<Accordion title="앱 캠페인을 운영하고 있습니다. 그런데 앱스플라이어 또는 구글 애즈 대시 보드에서 데이터나 전환 이벤트를 볼 수 없습니다.">

아직 이벤트 가져오기를 완료하지 않았을 가능성이 큽니다. 이벤트를 가져오는 방법에 대한 자세한 내용은 <Anchor target="_blank" href="/marketers/ko/docs/google-ads-adwords-integration-setup-for-advertisers#step-4-measure-your-app-conversions-mandatory">여기</Anchor>를 클릭하십시오.

</Accordion>

<div id="what-do-i-do-if-there-are-multiple-accounts" />

<Accordion title="계정이 여러 개인 경우 어떻게 해야합니까?">

앱스플라이어를 사용할 때, 구글 애즈에서 여러 계정을 운영하는 것은 아무 문제가 되지 않습니다. 앱스플라이어는 하나의 링크 ID로만 작동합니다. 그러므로 구글 애즈에서 오직 하나의 링크 ID만 생성하고, 여러 계정간에 공유합니다. 더 많은 정보를 원하신다면 <Anchor target="_blank" href="https://support.google.com/google-ads/answer/3030657">여기</Anchor>를 클릭하세요.

</Accordion>

<div id="what-happens-with-link-ids-created-at-mcc-level-vs-account-level" />

<Accordion title="MCC 수준에서 생성된 링크 ID는 계정 수준과 비교하여 어떻게 됩니까?">

MCC 수준 및 계정 수준의 링크 ID 모두 앱스플라이어에서 지원합니다. 계정 구조가 올바르게 구성되도록 구글 애즈 담당자와 긴밀하게 협력하는 것을 추천드립니다. 더 많은 정보를 원하신다면 <Anchor target="_blank" href="/marketers/ko/docs/recording-multiple-agency-mcc-google-ads-accounts">여기</Anchor>를 클릭하세요.

</Accordion>

<div id="what-is-parallel-tracking" />

<Accordion title="병렬 추적(parallel tracking)은 무엇입니까?">

구글 애즈의 병렬 추적을 사용하면 랜딩 페이지가 더 빠르게 로드되어, 사용자 이동 중 손실 문제가 줄어듭니다. 결과적으로 전환 수가 증가하고 광고 성과가 향상됩니다. 병렬 추적을 사용하면, 사용자를 어트리뷰션 링크로 전송하기 전에 광고에서 직접 최종 URL로 전송하며, 클릭 측정은 백그라운드에서 이루어집니다.

병렬 추적에 대한 전체 설명을 보려면 <Anchor target="_blank" href="https://support.google.com/google-ads/answer/7544674?hl=en">여기</Anchor>를 클릭하십시오.

#### 필요한 것은 무엇입니까?

병렬 추적이 의도한 대로 작동하려면 최종 URL이 캠페인 URL과 일치해야 하며 <Anchor target="_blank" href="https://support.google.com/google-ads/answer/6305348?hl=en">Google의 ValueTrack 파라미터</Anchor>에 입력해야 합니다.

수행 방식은 다음과 같습니다.

* 단일 플랫폼 어트리뷰션 링크 사용(권장하지 않음)
  * af\_r 파라미터를 URL에 사용해야 합니다.
* <Anchor target="_blank" href="/marketers/ko/docs/understand-onelink-short-vs-long-urls">원링크 롱 링크</Anchor> 사용(권장)
  * 캠페인 URL에 다음 URL 파라미터를 포함해야 합니다.
    * af\_android\_url
    * af\_ios\_url
    * af\_web\_dp
  * af\_dp를 사용해서는 안 됩니다.
  * 최종 URL(목적지 URL)을 Google의 ValueTrack 파라미터에 추가합니다. <Anchor target="_blank" href="https://support.google.com/google-ads/answer/6305348?hl=en#urlinsertion&zippy=%2Ctracking-template-only">더 알아보기</Anchor>

예를 들어,

```
https://subdomain.onelink.me/template_id?pid=xxx&af_ios_url={lpurl}
&af_android_url={lpurl}&af_web_dp={lpurl}
```

참고: [참고:](https://support.google.com/google-ads/answer/6305348?hl=en&sjid=12409212435602417786-AP#zippy=%2Cset-up-or-edit-a-tracking-template-with-valuetrack-parameters-at-the-campaign-level%2Cset-up-or-edit-a-tracking-template-with-valuetrack-parameters-at-the-ad-group-level%2Cfinal-url-tracking-template-or-custom-parameter) 지원되는 모든 파라미터를 보려면 본 기사를 참조하십시오.

병렬 추적으로 Google 광고 웹 캠페인을 구성하는 방법을 보려면 여기를 클릭하십시오.

</Accordion>

<div id="how-do-you-configure-a-campaign-with-android-or-ios-configuration" />

<Accordion title="안드로이드 또는 iOS 구성으로 캠페인을 설정하는 방법.">

> 🚧 **중요!**
>
> 앱스플라이어는 구글 애즈에서 사용하는 모든 앱 캠페인을 지원합니다.
>
> Google은 SRN(Self Reporting Network)입니다. 이 네트워크의 어트리뷰션 흐름이 어떻게 작동하는지 알아보려면, <Anchor target="_blank" href="/marketers/ko/docs/self-reporting-networks-srns">여기</Anchor>를 클릭하세요.
>
> 앱스플라이어는 Google에서 제공되는 모든 캠페인 정보를 제시할 수 있습니다. 캠페인 유형(검색, 동영상, 디스플레이 및 재참여)과 관련 정보는 구글에 의해 결정됩니다. 앱 캠페인을 구성하는 것이 추천됩니다. 다른 캠페인 유형에 대한 안내는 구글 담당자에게 문의하십시오. 이러한 캠페인에 대한 자세한 내용은, <Anchor target="_blank" href="https://developers.google.com/app-conversion-tracking/api/request-response-specs">여기</Anchor>를 클릭하십시오.

<div id="android-configuration-for-google-ads" />

<Accordion title="구글 애즈 안드로이드 설정">

안드로이드 어트리뷰션을 지원하려면, 앱이 GAID (구글 광고 ID) 수집하고, 광고 ID가 앱스플라이어 SDK를 통해 앱스플라이어로 전달되고 있는지 확인하십시오.

#### 인스톨 전환 기록 만들기

전환 기록을 생성하는 방법에 대한 자세한 내용을 보시려면 <Anchor target="_blank" href="/marketers/ko/docs/google-ads-adwords-integration-setup-for-advertisers#step-2-set-up-google-ads-on-appsflyer-mandatory">여기</Anchor>를 클릭하십시오.

<span id="inapp_events"></span>Google Ads - 안드로이드 설정 - 인앱 이벤트 보내기

구글의 모바일 앱 설치 캠페인의 성공 여부를 더 깊게 측정하기 원하신다면, 앱스플라이어 계정에서 구글 애즈 계정으로 인앱 이벤트를 보낼 수 있습니다.

#### 인앱 이벤트 전환 만들기

앱 전환을 측정하는 방법에 대한 자세한 정보는 <Anchor target="_blank" href="/marketers/ko/docs/google-ads-adwords-integration-setup-for-advertisers#step-4-measure-your-app-conversions-mandatory">여기</Anchor>를 클릭하십시오.

</Accordion>

<div id="ios-configuration-for-google-ads" />

<Accordion title="구글 애즈 iOS 설정">

#### 구글 애즈 - iOS 설정: 앱 캠페인

앱 캠페인을 사용하면 한번의 설정으로 구글 검색, 유튜브 및 디스플레이에서 iOS 앱을 홍보할 수 있습니다.

일반적으로, 구글 애즈는 검색 캠페인에서 iOS 인스톨을 자체 어트리뷰션 할 수 없습니다. 왜냐하면 클릭이 모바일 웹에서 발생하기 때문에 구글이 기기에서 IDFA를 가져 오지 못하고, ID 매칭을 수행할 수 없기 때문입니다.

반대로, **앱 캠페인에서 iOS 검색은**구글 애즈에 의해 어트리뷰션 될 수 있습니다. 광고가 구글 검색 앱에 게재되기 때문입니다.

#### 인스톨 전환 기록 생성

전환 기록을 생성하는 방법에 대한 자세한 내용을 보시려면 <Anchor target="_blank" href="/marketers/ko/docs/google-ads-adwords-integration-setup-for-advertisers#step-2-set-up-google-ads-on-appsflyer-mandatory">여기</Anchor>를 클릭하십시오.

#### 구글 애즈 - iOS 설정 - 인앱 이벤트 전송

구글의 모바일 앱 설치 캠페인의 성공 여부를 더 깊게 측정하기 원하신다면, 앱스플라이어 계정에서 구글 애즈 계정으로 인앱 이벤트를 보낼 수 있습니다.

#### 인앱 이벤트 전환 만들기

앱 전환을 측정하는 방법에 대한 자세한 정보는 <Anchor target="_blank" href="/marketers/ko/docs/google-ads-adwords-integration-setup-for-advertisers#step-4-measure-your-app-conversions-mandatory">여기</Anchor>를 클릭하십시오.

</Accordion>

</Accordion>

<div id="for-how-long-do-you-keep-google-ads--userlevel-data" />

<Accordion title="구글 애즈의 사용자 수준 데이터를 얼마나 오래 보유합니까?">

구글 애즈는 어트리뷰션 파트너에게 사용자 앱 설치 이후 6개월이 지나면, 사용자 레벨 데이터를 삭제하도록 요구합니다. 즉, 사용자가 앱을 설치한 후 6개월 이후에 수행한 이벤트는 오가닉으로 집계됩니다.

과거 종합 데이터는 동일하게 유지됩니다.

이는 모든 구글 애즈 채널에 해당됩니다.

</Accordion>

## Google Ads 불일치

구글 애즈 대시보드와 앱스플라이어 대시보드 간에 불일치가 생기는 경우가 있습니다.

이 차이를 줄이기 위해서 앱스플라이어는 구글 애즈와 긴밀히 협조하고 있지만, 광고주는 다음의 원인에 대해서 알고 있어야 합니다.

#### iOS와 안드로이드 모두

| **1. 일으키다. 2. 발생시키다.** | **Google Ads** | **앱스플라이어** |
| --- | --- | --- |
| **모델링된 전환 및 ICM 전환** | Google Ads는 Google의 내부 모델링에 의해 생성된 모델링된 설치를 표시하며, ICM 기반 모델링된 설치는 표시하지 않습니다. | AppsFlyer는 Google ICM(확률적 주장)에 의해 생성된 모델링된 설치를 표시하며, Google의 내부 모델링된 설치는 표시하지 않습니다. |
| **인스톨 어시스트 (일명, 멀티 터치 어트리뷰션)** | Self Reporting Network인 구글은, 구글 광고에 참여한 이후 구글의 어트리뷰션 윈도우 내에 일어난 모든 인스톨을, 구글 애즈로 어트리뷰션 합니다. | 앱스플라이어는 사용자의 여정에서 마지막 클릭에게 어트리뷰션 하고 해당 광고 참여는 <Anchor target="_blank" href="/marketers/ko/docs/measure-assisted-installs">어시스트</Anchor>로 처리합니다. |
| **인스톨 기록 시간** | 구글 애즈는 전환을 클릭 시점으로 어트리뷰션 합니다. | 앱스플라이어는 앱 첫 실행 시간 (앱 오픈)으로 전환을 어트리뷰션 합니다. |
| **시간대** | 위치에 따라 다릅니다. | 위치에 따라 다릅니다. |
| **어트리뷰션 기간** | 30일 | 구글 연동은 기본적으로 30일로 설정되어 있습니다. (수정 가능) |
| **뷰-쓰루 전환 (조회연결 전환)** | VT 전환은 구글 애즈에서 따로 설정하지 않는 한 **모든 전환** 열에만 표시되고 **전환** 열에는 표시되지 않습니다. | 앱스플라이어는 총 인스톨 수, 클릭-쓰루 인스톨 및 뷰-쓰루 인스톨을 보여줍니다. |
| **재설치** | Google Ads에서는 session\_start 전환으로 재설치를 표시합니다. | 앱스플라이어는 리타겟팅 데이터의 일부로 재설치(리어트리뷰션)를 표시합니다. |
| **인앱 이벤트** | 구글 애즈는 인앱 이벤트를 클릭 시점으로 어트리뷰션 합니다. | 앱스플라이어 대시보드에서 인앱 이벤트는 인스톨 시점으로 어트리뷰션 됩니다. 앱스플라이어 로데이터 보고서에서는 이벤트 시간을 기준으로 인앱 이벤트를 표시합니다. |
| **유효성 검증 규칙** | 구글은 유효성 검증 규칙에 관계없이 앱스플라이어로부터 모든 정보를받습니다. | 앱스플라이어는 유효성 검증 규칙에 따라, 몇개의 인스톨을 차감할 수도 있습니다. |
| **비용 - 구글 애즈 캠페인 채널** | 구글은 특정 캠페인의 모든 채널 (유튜브, 디스플레이 및 검색)에 대한 비용을 보고합니다. | 앱스플라이어는 캠페인의 모든 채널에 대해 구글에서 비용 데이터를 가져 오지만, iOS 앱 캠페인의 경우 유튜브 및 디스플레이 채널에서의 전환만 어트리뷰션 합니다. 결과적으로, 앱스플라이어의 종합 CPI가 더 높습니다. |
| **SKAN 인스톨** | Google Ads API V10+에서 Google Ads 대시보드는 did\_win=TRUE 및 did\_win=NULL의 설치를 구분하지 않습니다. 차별화는 원시 자료에만 있습니다. | Google Ads API V10+에서 앱스플라이어는 did\_win=TRUE인 포스트백의 설치만 표시합니다. 결과적으로 앱스플라이어의 설치 수가 더 적을 수 있습니다. |
| **첫 번째 열기 이벤트** | Google Ads는 DMA가 올바르게 구현된 Firebase에서 이벤트를 가져오고, 이후 DMA 동의된 이벤트가 청구됩니다. | Google Ads는 또한 AppsFlyer에서 잘못 구현된 DMA로 인해 모든 이벤트가 비 DMA 동의된 것으로 보고되고 Google이 이를 청구하지 않도록 하는 동일한 이벤트를 가져옵니다.<ul><li>DMA가 올바르게 구현되었는지 확인하려면 <Anchor target="_blank" href="/marketers/ko/docs/raw-data-export-page#download-report">원시 데이터 보고서 다운로드</Anchor>하고 <Anchor target="_blank" href="/marketers/ko/docs/bulletin-dma-support-in-raw-data-reports">이 게시물</Anchor>에 지정된 필드에 집중하세요.</li><li>DMA를 SDK에 구현하는 방법을 배우려면 [개발자 허브](https://dev.appsflyer.com/hc/docs/send-consent-for-dma-compliance)를 참조하세요.</li></ul> |
| **리타게팅 이벤트** | Google Ads는 응답에서 `ad_type=ClickToDownload`와의 재참여를 청구할 수 있습니다. | AppsFlyer는 `ad_type=ClickToDownload`을 재참여가 아닌 UA 전환 이벤트로 계산합니다. 그 결과, AppsFlyer의 재참여 수는 더 낮을 수 있습니다. |

> 📘 **참고**
>
> * Google Ads는 리타게팅 캠페인의 모든 설치를 동일한 위치에 표시하지만, 앱스플라이어 개요 대시보드에서 UA 보기는 신규 설치, 리타게팅 보기는 리어트리뷰션, 통합 보기는 둘 다 표시합니다.
> * 구글 애즈 대시보드와 앱스플라이어의 데이터를 비교할 때, 구글 애즈 대시보드의 데이터가 타사 앱 분석 서비스 제공업체(AppsFlyer)에서 가져온 데이터인지 확인하십시오. Firebase 또는 구글 플레이에서 가져온 데이터는 다르게 구성되며 앱스플라이어 데이터와 완전히 비교할 수 없습니다. 앱스플라이어에서 구글 애즈 대시보드로 데이터를 가져오는 방법을 알아 보려면 <Anchor target="_blank" href="/marketers/ko/docs/google-ads-adwords-integration-setup-for-advertisers#step-4-measure-your-app-conversions-mandatory">여기</Anchor>를 클릭하십시오.
> * 인스톨 이벤트 (구글 애즈 상, first\_open)를 비교하려면 구글 애즈의 전환 보고서에서 인스톨 이벤트까지 내려가십시오. Google Ads는 모든 전환(예: 설치, 구매, 구독)을 표시할 수 있으므로 모든 전환 이벤트 중에서 설치 이벤트만 선택하는 것이 중요합니다.

> 📄 **참고 항목**
>
> * iOS 14 관련 고려 사항은 <Anchor target="_blank" href="/marketers/ko/docs/get-skan-postback-data-from-google-ads">Google Ads SKAdNetwork와 앱스플라이어의 상호운용성</Anchor>을 참조하세요.

<div data-zendesk-anchors="h_01HA1SM7D91QPG17WH752FBAFT=google-ads-faq h_01HA1SM7D9JWBEPNE0E8FE665E=why-am-i-not-seeing-clicks-from-google-ads h_01HA1SM7DAW984PPRGHXA5BYSX=why-am-i-not-seeing-first_open-conversions-on-google-ads why-don%E2%80%99t-i-see-installs-from-google-ads=why-don-t-i-see-installs-from-google-ads h_01K5DZBDMS0D2S5XYDC22WQ19H=why-don-t-i-see-installs-from-google-ads quick-fix=%EB%B9%A0%EB%A5%B8-%EC%88%98%EC%A0%95 h_01K5DZBDMSBDKAFHVVPYD6YKRK=%EB%B9%A0%EB%A5%B8-%EC%88%98%EC%A0%95 still-not-working=%EC%95%84%EC%A7%81%EB%8F%84-%EC%9E%91%EB%8F%99%ED%95%98%EC%A7%80-%EC%95%8A%EB%82%98%EC%9A%94 h_01K5DZBDMSVTE6M2J235ST85DE=%EC%95%84%EC%A7%81%EB%8F%84-%EC%9E%91%EB%8F%99%ED%95%98%EC%A7%80-%EC%95%8A%EB%82%98%EC%9A%94 h_01K7NT8FVC3K3861WN9VKRZ2HB=why-dont-i-see-inapp-events-in-the-google-ads-dashboard quick-fix-checklist=%EB%B9%A0%EB%A5%B8-%EC%88%98%EC%A0%95-%EC%B2%B4%ED%81%AC%EB%A6%AC%EC%8A%A4%ED%8A%B8 h_01K7NT8FVC1T557GPG7ZCYX33J=%EB%B9%A0%EB%A5%B8-%EC%88%98%EC%A0%95-%EC%B2%B4%ED%81%AC%EB%A6%AC%EC%8A%A4%ED%8A%B8 h_01K7PAH7VDS7NGW6R6HERGXK9H=%EC%B0%B8%EA%B3%A0 still-not-working::77f3165b=%EC%95%84%EC%A7%81%EB%8F%84-%EC%9E%91%EB%8F%99%ED%95%98%EC%A7%80-%EC%95%8A%EB%82%98%EC%9A%94-1 h_01K7NT8FVCD4DNFKP3DS75ZKR0=%EC%95%84%EC%A7%81%EB%8F%84-%EC%9E%91%EB%8F%99%ED%95%98%EC%A7%80-%EC%95%8A%EB%82%98%EC%9A%94-1 h_01HA1SM7DACQDVGWGKV5MZ63D6=can-i-stop-google-cost-sync h_01HA1SM7DA415FQP3MFC09AE3Y=do-i-need-to-create-and-then-import-session_start h_01HA1SM7DAEKGVPDTX77RJ9Y37=can-i-send-uninstall-information-to-google-ads h_01HA1SM7DAKKVZ82WF6RVEDHE9=what-google-ads-data-does-appsflyer-display h_01HA1SM7DANYQ0DAY54CH4HPV4=do-i-need-to-configure-anything-to-create-audience-lists-in-google-ads-based-on-appsflyer-data h_01HA1SM7DA3XF8NBGYGZ0XTB69=im-running-an-app-campaign-why-cant-i-see-data-or-conversion-events-in-the-appsflyer-or-google-ads-dashboard h_01HA1SM7DAY7JNTFSG86A1QGKC=what-do-i-do-if-there-are-multiple-accounts h_01HA1SM7DAYSVMENT91T2BE26Z=what-happens-with-link-ids-created-at-mcc-level-vs-account-level h_01HA1SM7DAK186BRZN970PKPRM=what-is-parallel-tracking additional-information=%ED%95%84%EC%9A%94%ED%95%9C-%EA%B2%83%EC%9D%80-%EB%AC%B4%EC%97%87%EC%9E%85%EB%8B%88%EA%B9%8C h_01HA1SM7DAMNG8X22VNWMKBJ8R=%ED%95%84%EC%9A%94%ED%95%9C-%EA%B2%83%EC%9D%80-%EB%AC%B4%EC%97%87%EC%9E%85%EB%8B%88%EA%B9%8C h_01HA1SM7DBNAS6DP8G9D8KFHPW=how-do-you-configure-a-campaign-with-android-or-ios-configuration h_01HA1SM7DB16T3RGBVGT5Z9REW=%EC%A4%91%EC%9A%94 h_01HA1SM7DBC38CY8AN3EPMMJFW=android-configuration-for-google-ads creating-conversion-recording-installs=%EC%9D%B8%EC%8A%A4%ED%86%A8-%EC%A0%84%ED%99%98-%EA%B8%B0%EB%A1%9D-%EB%A7%8C%EB%93%A4%EA%B8%B0 h_01HA1SM7DBF9KDRNEV25KJHGHN=%EC%9D%B8%EC%8A%A4%ED%86%A8-%EC%A0%84%ED%99%98-%EA%B8%B0%EB%A1%9D-%EB%A7%8C%EB%93%A4%EA%B8%B0 create-a-conversion-inapp-events=%EC%9D%B8%EC%95%B1-%EC%9D%B4%EB%B2%A4%ED%8A%B8-%EC%A0%84%ED%99%98-%EB%A7%8C%EB%93%A4%EA%B8%B0 h_01HA1SM7DBDQVNDQ5GG7X2PJ8K=%EC%9D%B8%EC%95%B1-%EC%9D%B4%EB%B2%A4%ED%8A%B8-%EC%A0%84%ED%99%98-%EB%A7%8C%EB%93%A4%EA%B8%B0 h_01HA1SM7DBKKQ9R8MQMQT9GRXV=ios-configuration-for-google-ads google-ads-ios-configuration-app-campaigns=%EA%B5%AC%EA%B8%80-%EC%95%A0%EC%A6%88---ios-%EC%84%A4%EC%A0%95-%EC%95%B1-%EC%BA%A0%ED%8E%98%EC%9D%B8 h_01HA1SM7DBNSDFCJA5BP59MMQ2=%EA%B5%AC%EA%B8%80-%EC%95%A0%EC%A6%88---ios-%EC%84%A4%EC%A0%95-%EC%95%B1-%EC%BA%A0%ED%8E%98%EC%9D%B8 creating-conversion-recording-installs::6a56eb4b=%EC%9D%B8%EC%8A%A4%ED%86%A8-%EC%A0%84%ED%99%98-%EA%B8%B0%EB%A1%9D-%EC%83%9D%EC%84%B1 h_01HA1SM7DBXCT0NS4W50D4ZGEK=%EC%9D%B8%EC%8A%A4%ED%86%A8-%EC%A0%84%ED%99%98-%EA%B8%B0%EB%A1%9D-%EC%83%9D%EC%84%B1 google-ads-ios-configuration-sending-inapp-events=%EA%B5%AC%EA%B8%80-%EC%95%A0%EC%A6%88---ios-%EC%84%A4%EC%A0%95---%EC%9D%B8%EC%95%B1-%EC%9D%B4%EB%B2%A4%ED%8A%B8-%EC%A0%84%EC%86%A1 h_01HA1SM7DBEV9CJTAB5YHRJHYK=%EA%B5%AC%EA%B8%80-%EC%95%A0%EC%A6%88---ios-%EC%84%A4%EC%A0%95---%EC%9D%B8%EC%95%B1-%EC%9D%B4%EB%B2%A4%ED%8A%B8-%EC%A0%84%EC%86%A1 creating-a-conversion-inapp-events=%EC%9D%B8%EC%95%B1-%EC%9D%B4%EB%B2%A4%ED%8A%B8-%EC%A0%84%ED%99%98-%EB%A7%8C%EB%93%A4%EA%B8%B0-1 h_01HA1SM7DBCQYSJ3R67F0856QK=%EC%9D%B8%EC%95%B1-%EC%9D%B4%EB%B2%A4%ED%8A%B8-%EC%A0%84%ED%99%98-%EB%A7%8C%EB%93%A4%EA%B8%B0-1 for-how-long-do-you-keep-google-ads%E2%80%99-userlevel-data=for-how-long-do-you-keep-google-ads--userlevel-data h_01HA1SM7DBFAAV7C4ENA34B7JP=for-how-long-do-you-keep-google-ads--userlevel-data google-ads-discrepancies=google-ads-%EB%B6%88%EC%9D%BC%EC%B9%98 h_01HA1SM7DBA7KK1DXFCE2G0QTP=google-ads-%EB%B6%88%EC%9D%BC%EC%B9%98 both-ios-and-android=ios%EC%99%80-%EC%95%88%EB%93%9C%EB%A1%9C%EC%9D%B4%EB%93%9C-%EB%AA%A8%EB%91%90 h_01HA1SM7DB18BTDKK5BK4949HX=ios%EC%99%80-%EC%95%88%EB%93%9C%EB%A1%9C%EC%9D%B4%EB%93%9C-%EB%AA%A8%EB%91%90 h_01HA1SM7DBSTAREA36YWRRRG82=%EC%B0%B8%EA%B3%A0-1 h_01HDP2XBSEJVQ5G0MD0V5R05CM=%EC%B0%B8%EA%B3%A0-%ED%95%AD%EB%AA%A9" />
