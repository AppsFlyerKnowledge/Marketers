---
title: Meta Ads FAQ
metadata:
  keywords:
    - Facebook
    - Advertisers
    - Agencies
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
    - Agencies
  created_at: '2021-11-09T10:04:49Z'
  edited_at: '2026-10-14T10:26:32Z'
  id: 4410472805649
  locale: ko
  section: Meta ads
  section_id: 6551109855761
  url: https://support.appsflyer.com/hc/ko/articles/4410472805649
---
> **한눈에 보기:** 앱스플라이어에서 Meta Ads를 사용할 때 자주 묻는 질문에 대한 답을 확인해 보세요.

## Meta Ads FAQ

<div id="i-dont-see-facebook-campaign-clicks-in-appsflyers-dashboard" />

<Accordion title="앱스플라이어 대시보드에서 Meta Ads 캠페인 클릭수가 보이지 않습니다.">

기본적으로 Meta Ads는 전환 및 참여 데이터만 전송합니다. 하지만 <Anchor target="_blank" href="/marketers/ko/docs/meta-ads-integration-setup#cost-clicks-and-impressions">Meta Ads 캠페인의 클릭수, 노출수, 비용 데이터</Anchor>도 쉽게 수집을 시작할 수 있습니다.

</Accordion>

<div id="can-appsflyer-show-the-campaign-level-and-ad-groups" />

<Accordion title="앱스플라이어는 캠페인 수준 및 광고 그룹을 표시할 수 있나요?">

네. 실제로 앱스플라이어는 단일 광고 수준까지 보여주므로, Meta Ads 사용 시 캠페인 >> 광고 세트 >> 광고라는 3단계의 하위 탐색이 가능합니다.

</Accordion>

<div id="is-facebook-data-shown-in-realtime" />

<Accordion title="Meta Ads 데이터는 실시간으로 볼 수 있나요?">

네, 모든 앱 설치 및 이를 따르는 인앱 이벤트는 실시간으로 보여집니다. 하지만 앱스플라이어가 Meta Ads로부터 수신하는 종합한 형태의 클릭, 노출, 비용 데이터는 몇 시간 주기로 도착합니다.

</Accordion>

<div id="when-can-i-see-a-new-campaigns-data-on-appsflyer" />

<Accordion title="앱스플라이어에서 새 캠페인 데이터를 언제 쯤 볼 수 있나요?">

Meta Ads에서의 새로운 광고, 광고 세트, 캠페인 데이터를 보려면 한 번 이상의 설치가 발생해야 합니다.

예를 들어, 새 광고에서 클릭이 100번 발생했지만 설치가 발생하지 않았다면 앱스플라이어 대시보드 및 데이터에 나타나지 않습니다. 다른 광고에서 1번의 클릭과 1번의 설치를 발생했다면 앱스플라이어에 표시됩니다.

</Accordion>

<div id="how-can-i-get-more-installs-from-facebook" />

<Accordion title="어떻게 하면 Meta Ads에서 더 많은 설치 결과를 얻을 수 있나요?">

Meta Ads의 리타겟팅을 활성화하면 신규 사용자 유치(UA) 캠페인에서 최대 100% 더 많은 설치를 추가 비용 없이 확보할 수 있습니다.  
어떻게 하나요? <Anchor target="_blank" href="/marketers/ko/docs/self-reporting-networks-srns#what-is-srn-mistargeting">여기</Anchor>에서 자세히 알아보세요.

</Accordion>

<div id="how-can-i-get-device-level" />

<Accordion title="Google Play 및 Meta Install Referrers를 사용하여 기기 단위의 Android 설치 데이터를 확보하려면 어떻게 해야 하나요?">

#### Google Play Install Referrer API

Google Play Install Referrer API를 사용하면 광고주는 Google Play Store에서 발생한 설치의 캠페인 정보와 같은 기여 데이터를 확보할 수 있습니다. 이 API는 <Anchor target="_blank" href="/marketers/ko/docs/basic-sdk-integration-guide#attribute-apps-published-on-google-play">앱 내에 반드시 연동</Anchor>되어야 하며, 설치 후 앱을 처음 열 때 리퍼러 데이터를 전달하는 방식으로 작동합니다. 필수 복호화 키를 제출하면 앱스플라이어의 로우 데이터 리포트에서 매칭 타입 `gp_referrer`와(과) 함께 어트리뷰션 필드를 확인할 수 있습니다.

#### Google Play Install Referrer

Meta Install Referrer는 디바이스 내부에 로컬로 저장된 추가 캠페인 메타데이터를 제공합니다. [앱스플라이어 SDK](https://dev.appsflyer.com/hc/docs/install-android-sdk#meta-install-referrer)를 통해 접근할 수 있습니다. 이는 클릭 및 임프레션 데이터를 모두 포함한 한층 더 풍부한 데이터를 확보할 수 있게 하고, 여러 세션에 걸친 유입까지 지원함으로써 Google Play Install Referrer를 보완합니다. Meta Install Referrer를 통한 귀속은 `fb_referrer` (Facebook) 및 `ig_referrer` (Instagram)과 같은 일치 유형을 사용합니다.

#### 캠페인 귀속 필드

* Ad ID
* Ad name
* Adset ID
* Adset name
* Campaign ID
* Campaign name
* Account ID
* Channel

#### SDK 및 설정 노트

* Google Play 추천자 데이터에는 앱스플라이어 SDK 버전 5.4.0+가 필요합니다.
* Meta 추천자 지원은 올바른 SDK 구성에 따라 달라집니다. 구현 세부정보는 <Anchor target="_blank" href="/marketers/ko/docs/bulletin-get-meta-ads-attribution-in-raw-data-reports-with-the-meta-install-refe">이 게시판</Anchor>을 참조하세요.

#### 복호화 키 제출

두 레퍼러 타입 모두 Meta 개발자 계정의 복호화 키가 필요합니다. 이 키는 앱당 한 번만 제공하면 됩니다. 단계는 다음과 같습니다:

1. Meta 개발자 포털에 로그인하세요.
2. **내 앱**으로 이동하여 관련 앱을 선택합니다.
3. **설정 > 기본**으로 가서 "설치 추천자 복호화 키"를 찾습니다.
4. 앱스플라이어에서 **협업 > 활성 통합 > Meta Ads**로 이동합니다.
5. 키를 **설치 리퍼러 복호화 키** 필드에 붙여넣고 저장합니다.

</Accordion>

<div id="do-you-make-facebook-raw-data-available-to-agencies" />

<Accordion title="에이전시에게도 Meta Ads 로우 데이터를 제공하나요?">

아닙니다. 에이전시에 Meta Ads 로우 데이터를 제공할 수 없습니다. 에이전시는 Meta 서비스 약관 측면에서 타사로 간주되기 때문입니다.

</Accordion>

<div id="i-dont-see-facebook-raw-data-in-the-installation-and-inapp-events-reports" />

<Accordion title="설치 및 인앱이벤트 리포트에서 Meta Ads 로우 데이터가 보이지 않습니다.">

기본적으로 Meta Ads는 제한 없는 귀속 정보와 함께 장치 수준 데이터를 배포하는 것을 허용하지 않습니다. 그러나 Meta 고급 모바일 측정(AMM) 약관에 동의하면 제한 없이 Meta Ads에 대한 장치 수준 귀속 데이터에 접근할 수 있습니다. <Anchor target="_blank" href="/marketers/ko/docs/meta-ads-integration-setup#enable-meta-ads-device-level-data">Meta Ads 장치 수준 데이터를 활성화</Anchor>를 참고하세요.

</Accordion>

<div id="any-specific-columns-for-facebook-in-appsflyers-performance-reports" />

<Accordion title="앱스플라이어 성과 리포트에서 Meta Ads를 위한 어떤 특정한 열이 있습니까?">

네. 성과 리포트는 선택한 미디어 소스의 어떠한 조합에서도 캠페인 레벨까지의 정보를 제공하는 고정된 컬럼 구조를 갖습니다.  
그러나 Meta Ads에 대해서만 성과 보고서를 다운로드하면 앱스플라이어가 4개의 열을 추가하여 단일 광고 수준까지 정보를 제공합니다! 추가된 열은 광고 세트 이름, 광고 세트 ID, 광고 그룹(즉, 단일 광고) 이름 및 광고 그룹 ID입니다.

[![](https://files.readme.io/fe0c08fc17a6060bfdfa0e9c8b21eee755a7a868ee1b4b60a16808e126281dc4-4411036714001.png)](https://files.readme.io/fe0c08fc17a6060bfdfa0e9c8b21eee755a7a868ee1b4b60a16808e126281dc4-4411036714001.png)

</Accordion>

<div id="can-i-work-with-facebook-fmps-and-measure-performance-with-appsflyer" />

<Accordion title="Meta 캠페인 관리 파트너와 협업하면서 앱스플라이어로 성과를 측정할 수 있나요?">

네. 예. 앱스플라이어는 수십 개의 Meta 캠페인 관리 파트너와 통합되어 있습니다. 이러한 파트너는 대시보드의 활성 연동 페이지에서 어트리뷰션으로 설정할 수 있습니다.

Meta 캠페인 관리 파트너와의 어트리뷰션 설정에 대한 자세한 내용은 <Anchor target="_blank" href="/marketers/ko/docs/configuring-meta-campaign-management-partners">여기</Anchor>를 클릭하세요.

</Accordion>

<div id="what-should-i-do-when-i-receive-the-following-warning" />

<Accordion title="다음과 같은 경고를 받았을 때 무엇을 해야하나요?">

[![](https://files.readme.io/ad1d07250ae23a0f4d5e145b615ac09a81990e6d46b50a2795c26b4e2be21297-4411045335185.png)](https://files.readme.io/ad1d07250ae23a0f4d5e145b615ac09a81990e6d46b50a2795c26b4e2be21297-4411045335185.png)

* Facebook App ID를 확인하고 해당 Facebook App ID에 국가나 연령 제한이 설정되어 있는지 검토하세요.
* 어트리뷰션이 이미 동작하고 있으면, 앱이 Meta 개발자 포털에서 공개적으로 사용할 수 있는 상태라는 것이고, 이 오류 메시지를 무시해도 됩니다.

</Accordion>

<div id="what-happens-with-different-lookback-windows-than-on-facebook" />

<Accordion title="Meta Ads와 다른 기여 기간을 적용하면 어떻게 되나요?">

클릭 후 7일, 조회 후 1일 기여 기간이 Meta Ads고의 최대 및 기본 기여 기간입니다.

앱스플라이어에서 짧은 윈도우를 구성하면 Meta Ads의 귀속이 감소합니다. 반대로, 앱스플라이어에서 긴 윈도우를 구성하면 Meta보다 앱스플라이어 측에서 더 많은 귀속이 발생합니다.

그러므로 차이를 최소화하기 위해서는, 앱스플라이어에서 Meta Ads 기여 기간 클릭 후 7일, 조회 후 1일로 설정하는 것을 권장합니다.

</Accordion>

<div id="what-are-the-facebook-api-parameters" />

<Accordion title="Meta API 파라미터는 무엇인가요?">

몇몇 앱스플라이어 API에서, Meta 파라미터가 이전 버전과의 호환성 문제로 대시보드에 나타나는 이름과 다릅니다. 아래 표를 참조하세요.

| 전환 데이터 | 앱스플라이어 로우 데이터 | Meta |
| --- | --- | --- |
| campaign | campaign | campaign\_group\_name |
| campaign\_id | Campaign ID | campaign\_group\_id |
| adgroup | Ad | adgroup\_name |
| adgroup\_id | Ad ID | adgroup\_id |
| adset | Adset | campaign\_name |
| adset\_id | Adset ID | campaign\_id |
| agency | Partner | N/A |
| is\_fb | Media Source | is\_fb |
| af\_channel | Channel | publisher\_platform |
| af\_siteid | Site ID | publisher\_platform when `publisher_platform` 값이 같지 않을 때 `facebook` 그렇지 않으면 `null`. |

</Accordion>

<div id="how-long-do-you-keep-facebook-s-userlevel-data" />

<Accordion title="Meta Ads의 사용자 수준 로우 데이터를 얼마나 오래 보유합니까?">

Meta Ads는 어트리뷰션 파트너에게 사용자 앱 설치 이후 6개월이 지나면, 사용자 레벨 데이터를 삭제하도록 요구합니다. 즉, 사용자가 앱을 설치한 후 6개월 이후에 수행한 이벤트는 오가닉으로 집계됩니다.  
과거 종합 데이터는 동일하게 유지됩니다.  
이는 모든 Meta Ads 채널 (Facebook 앱, Instagram, 메신저 및 오디언스 네트워크)에 해당됩니다.

</Accordion>

<div id="are-ios-universal-links-and-android-app-links-supported-in-meta-ads" />

<Accordion title="iOS 유니버설 링크와 Android 앱 링크가 Meta Ads에서 지원되나요?">

iOS 유니버설 링크 및 Android 앱 링크는 Meta Ads에서 지원되며 사용할 수 있습니다. 자세한 내용은 <Anchor target="_blank" href="https://www.facebook.com/business/help/1627795160837067?id=1858550721111595">Meta 고객 센터</Anchor>를 참조하세요.

* 정적 광고(카탈로그 아님)의 경우 iOS 유니버설 링크 및 Android 앱 링크는 **앱**이 대상으로 선택된 캠페인에서만 지원됩니다.
* 다이내믹 광고의 경우 iOS 유니버설 링크, Android 앱 링크, URI 스킴을 [여기](/docs/meta-ads-faq#can-onelink-links-be-used-for-app-opening-and-deep-linking-in-facebook-dynamic-product-ads)에 설명된 대로 사용할 수 있습니다.

**참고:** iOS 유니버설 링크 및 Android 앱 링크는 유료 광고에서만 지원됩니다.

</Accordion>

<div id="are-ios-universal-links-and-android-app-links-supported-in-metas-non-paid-content" />

<Accordion title="Meta의 비유료 콘텐츠에서 iOS 유니버설 링크와 Android 앱 링크가 지원되나요?">

iOS 유니버설 링크 및 Android 앱 링크는 유료 광고에서만 지원됩니다. 비유료 소셜 앱 콘텐츠에서는 사용자를 리디렉션하거나 딥 링크하기 위해 소셜 앱 랜딩 페이지 또는 URI 스킴을 설정해야 할 수 있습니다.

</Accordion>

<div id="aem-attribution-is-not-working" />

<Accordion title="AEM 어트리뷰션이 작동하지 않습니다">

**고급 데이터 공유** 토글이 켜져 있고 Meta와 어트리뷰션 연결이 되지 않는다면, 공유된 이벤트가 Meta의 적격 기준을 충족하는지 확인하세요. [Meta 문서](https://www.facebook.com/business/help/716239976391518?id=1877298665783613)를 참조하세요.

</Accordion>

<div id="can-onelink-links-be-used-for-app-opening-and-deep-linking-in-facebook-dynamic-product-ads" />

<Accordion title="OneLink 링크를 다이내믹 제품 광고에서 앱 열기 및 딥링킹에 사용할 수 있습니까?">

네. App Links, Universal Links 또는 URI 스킴이 구성된 OneLink 링크는 동적 제품 광고에서 지원됩니다. 동적 광고에 사용되는 카탈로그의 데이터 피드에서 **applink.ios\_url** 및 **applink.android\_url** 필드에 OneLink 링크를 사용할 수 있습니다.

</Accordion>

<div id="conversion-events-are-not-sent-to-meta-ads" />

<Accordion title="전환 이벤트는 Meta Ads에 전송되지 않습니다.">

귀속이 포함되지 않은 제로 패키지를 이용중일 수 있습니다.

</Accordion>

<div id="can-i-use-get" />

<Accordion title="Meta에서 전환 데이터를 검색하는 데 Get Conversion Data(GCD)를 사용할 수 있나요?">

**네.** 앱 설정 및 AMM 계약 상태에 따라 Meta에서 변환 데이터를 검색하는 데 계속해서 **GCD** 를 사용할 수 있습니다.

* **Facebook SDK가 앱에 통합된 경우:**

  설명한 바와 같이 <Anchor target="_blank" href="/marketers/ko/docs/self-reporting-networks-srns#deferred-deep-linking">DDL(Deferred Deep Linking) 문서</Anchor>, DDL 데이터를 검색하여 GCD를 통해 사용할 수 있습니다.
* **Facebook SDK가 앱에 통합되지 않은 경우:**

  여전히 검색할 수 있습니다 **캠페인, 광고 세트 및 광고 이름** GCD를 통해 - 제공되는 경우 <Anchor target="_blank" href="/marketers/ko/docs/about-raw-data-identifier-restrictions#meta-ads">Advanced Mobile Measurement (AMM)이 서명되었습니다</Anchor>. 이러한 경우, 해당 값들을 활용하여 자체 **커스텀 딥링크 로직**을 적용할 수 있습니다.

> 📘 **참고**
>
> Meta의 데이터 공유 정책은 GCD를 통해 사용 가능한 세부 수준에 영향을 줄 수 있습니다. 사용 가능한 캠페인 수준 데이터를 최대화하려면 AMM이 서명되어 있는지 확인하세요.

</Accordion>

## Meta Ads 비용 FAQ

<div id="getting-facebook-cost-data-in-the-appsflyer-dashboard" />

<Accordion title="앱스플라이어 대시보드에서 Meta Ads 데이터 가져오기">

지난 7일 동안 하나 이상의 앱 설치가 발생한 경우 앱스플라이어는 Meta Ads캠페인에서 비용 데이터(클릭 및 노출 포함)를 받습니다.

Meta Ads 캠페인이 여러 플랫폼 (Android, iOS, 데스크톱 등)에서 참여하는 경우, 대시보드의 비용은 Meta Ads에서 계산한대로 플랫폼 별로 보여집니다.

<Anchor target="_blank" href="/marketers/ko/docs/meta-ads-integration-setup#cost-clicks-and-impressions">Meta Ads 비용, 클릭 및 노출 데이터 가져오기</Anchor>.

</Accordion>

<div id="facebook-cost-example" />

<Accordion title="Meta Ads 비용 예시">

광고주가 Meta Ads를 사용하여 캠페인을 실행합니다. 앱스플라이어에서 광고주는 다음을 보게 됩니다.

![mceclip2.png](https://files.readme.io/a1aa5847db5c0b873b34b1d4de43ade7d4109608371e05a84342122e56d0ce08-4411031032081.png)

Meta Ads에서 비용 정보를 앱스플라이어에 제공합니다. **설치** 수는 앱스플라이어에서 앱스플라이어 어트리뷰션 규칙을 통해 계산합니다. 결과적으로, Meta Ads와 앱스플라이어에서 계산한 eCPI는 일반적으로 차이 나게 됩니다.

</Accordion>

<div id="i-cant-see-old-facebook-cost-data-in-the-appsflyer-dashboard" />

<Accordion title="앱스플라이어 대시보드에서 예전 Meta Ads 비용 데이터가 보이지 않습니다.">

위에서 설명한 첫 번째 Meta Ads 관리자 로그인을 실행하면, 는 기존앱스플라이어 캠페인에 대해서 소급적으로 최대 7일까지 Meta Ads 비용 데이터를 수신합니다. 그 이전의 비용 데이터는 확인할 수 없습니다.

다음 동기화부터 앱스플라이어는 최근 7일 동안의 데이터를 받습니다. 다시 말하면 비용, 클릭, 임프레션 데이터는 마지막 7일 동안 적어도 1번 이상의 전환이 있은 모든 캠페인에 대해서 수집됩니다.

</Accordion>

<div id="can-i-stop-cost-data-sync" />

<Accordion title="비용 데이터 동기화를 중지할 수 있나요?">

Meta Ads와의 비용 데이터 동기화를 중지하려면 <Anchor target="_blank" href="https://www.facebook.com/help/405094243235242">Meta Ads 계정의 비즈니스 연동에서 앱스플라이어를 제거하세요</Anchor>.

</Accordion>

<div id="cost-data-was-fine-for-a-few-months-but-it-stopped-displaying" />

<Accordion title="지난 몇 달간 비용 데이터가 잘 보였는데, 지금은 표시되지 않습니다.">

Meta Ads는 몇 달마다 비용 데이터 획득을 위한 권한을 재설정합니다. 대시보드에 비용 데이터가 표시되지 않으면, Meta Ads 관리자 로그인 과정을 다시 반복해야 합니다.

만약 Meta Ads 관리자 계정의 Meta Ads 비밀번호를 변경하는 경우에도 이 로그인 과정을 반복해야 합니다.

</Accordion>

<div id="i-clicked-on-my-facebook-ad-5-minutes-ago-why-dont-i-see-the-click-in-appsflyer" />

<Accordion title="5분 전에 Facebook 광고를 클릭했습니다. 그런데 왜 앱스플라이어에서 그 클릭을 확인할 수 없나요?">

앱스플라이어는 주기적으로 몇 시간마다 종합 클릭, 노출, 비용 데이터를 Meta Ads로부터 획득합니다. 따라서, 앱스플라이어 대시보드에 표시될 때까지 몇 시간 걸립니다.

</Accordion>

<div id="can-i-get-raw-data-on-clicks-and-impressions-from-facebook" />

<Accordion title="Meta Ads의 클릭과 노출에 대한 로우 데이터를 얻을 수 있습니까?">

앱스플라이어는 Meta Ads로부터 종합 클릭 및 노출 데이터만을 획득하므로 클릭 및 노출의 전체 로우 데이터는 이용할 수 없습니다. 로우 데이터 보고서에서 볼 수 있는 클릭 및 임프레션에 관한 로우 데이터는 설치로 이어진 결과값입니다.

</Accordion>

<div id="are-there-limitations-of-facebook-cost-data-by-geo" />

<Accordion title="지역별 Meta Ads 비용 데이터에 대한 제한 사항은 무엇입니까?">

앱스플라이어 대시보드에서 지역별로 필터링하면 Meta Ads 비용 데이터의 요약 및 상세를 볼 수 있습니다.

이 데이터는 Meta Ads의 "모바일 앱 설치 캠페인"에만 적용됩니다.

또한, 지역별 비용은 단일 플랫폼 캠페인에만 적용됩니다. 즉, Android 대상 광고 세트와 iOS 대상 광고 세트가 있는 캠페인에는 지역별 비용 데이터가 없습니다. **완벽한 비용 데이터를 받기 위해서는 각 플랫폼마다 전용 캠페인을 만들어야 합니다.**

</Accordion>

<div id="what-are-the-limitations-of-facebook-cost-data-in-master-api" />

<Accordion title="마스터 API에서의 Meta Ads 비용 데이터에 대한 제한 사항은 무엇인가요?">

<Anchor target="_blank" href="/marketers/ko/docs/master-api-user-acquisition-metrics-via-api">마스터 API 리포트에서</Anchor> Meta Ads는 비용 데이터를 동시에 지역과 채널로 그룹화하는 것을 지원하지 않습니다.

전체 비용 데이터가 포함된 보고서를 작성하려면, 이 기준 중 하나로만 그룹화하세요.

</Accordion>

<div id="the-total-cost-doesnt-match" />

<Accordion title="Meta와 앱스플라이어에 표시된 총 비용이 일치하지 않는 이유는 무엇인가요?">

Meta Ads와 앱스플라이어 어트리뷰션 모델에는 차이가 있습니다. 이러한 차이로 인해 Meta Ads 비용 데이터와 불일치가 발생할 수 있습니다.

* **Meta Ads의 기기 교차 어트리뷰션:** 어떤 플랫폼(iOS/Android)의 캠페인이 다른 플랫폼의 비용으로 설치 표시되는 문제가 발생할 수 있습니다.
* **모바일이 아닌 플랫폼의 Meta Ads 캠페인:** Meta Ads의 링크 클릭 캠페인과 같은 비-모바일 캠페인에서도 데스크톱 사용자는 결국 모바일 앱을 설치할 수 있습니다. 이러한 기기 간 캠페인에서 앱스플라이어는 비용을 표시하지 않습니다. 하지만, 앱을 설치한 같은 기기에서 링크 클릭이 실행되었다면 비용 데이터를 획득할 수 있습니다.  
  예를 들어, Facebook 사용자가 데스크톱 컴퓨터에서 광고주의 방문 페이지로 유도하는 광고를 클릭합니다. 일주일 뒤에 같은 Facebook 사용자가 아이폰 기기에 광고주의 iOS 앱을 설치합니다. 설치는 앱스플라이어 대시보드에서 어트리뷰션되고 표시되지만, 이 플랫폼 간 설치의 비용은 표시되지 않습니다.
* **최근 7일간 결과가 0인 캠페인** - 앱스플라이어는 최근 7일 이내에 앱 설치나 전환이 발생한 캠페인만 비용과 동기화됩니다. Meta Ads 비용이 막 설정되었고, 이전에 7일 이상 비활성화 상태였던 캠페인은 비용이 표시되지 않습니다.
* **삭제 및 보관된 광고**: 삭제 및 보관된 광고에 대한 비용은 Meta에서 앱스플라이어에 보고되지 않지만, 이 비용은 Meta 대시보드에 반영됩니다. 이는 캠페인 수준에서 데이터를 비교할 때 Meta와 앱스플라이어 보고서 간의 불일치를 초래할 수 있습니다.

</Accordion>

<div id="why-is-the-appsflyer-calculation-for-ecpi-different-from-the-cost-calculated-by-facebook-while-the-total-cost-is-identical" />

<Accordion title="eCPI에 대한 앱스플라이어 계산은 Meta Ads에서 계산한 비용과 다르지만 총 비용은 동일한 이유는 무엇인가요?">

설치당 비용은 총비용을 설치 횟수로 나눠서 계산합니다. <Anchor target="_blank" href="/marketers/ko/docs/meta-ads-discrepancies">앱스플라이어는 Meta Ads와 앱 설치 횟수를 다르게 집계</Anchor>하기 때문에, 일반적으로 eCPI가 달라집니다.

</Accordion>

<div id="why-doesnt-cost-data-include-data-from-all-campaigns" />

<Accordion title="비용 데이터에 모든 캠페인의 데이터가 포함되지 않는 이유는 무엇인가요?">

Meta Ads 로그인(위에서 설명함)을 수행하는 사용자가 실행 중인 캠페인 중 일부에 액세스할 수 없는 경우 앱스플라이어의 대시보드에 표시되지만 비용, 클릭 및 노출 데이터 중 일부가 없는 캠페인이 발생합니다.

**참고:** 여러 Meta Ads 사용자가 Meta Business Manager에서 캠페인을 실행할 수 있는 권한을 가질 수 있지만 Meta Ads 로그인을 수행하려면 한 명만 필요합니다.

</Accordion>

<div id="is-facebook-cost-data-displayed-for-retargeting-campaigns" />

<Accordion title="리타겟팅 캠페인에도 Meta Ads 비용 데이터가 표시되나요?">

리타겟팅 캠페인의   **<Anchor target="_blank" href="/marketers/ko/docs/cohort-and-retention-dashboard">코스트 및 ROI 데이터는 코호트 리포트의 통합 뷰</Anchor>에서 확인하실 수 있습니다.**

</Accordion>

<div id="why-does-the-facebook-cost-configuration-window-close-before-login" />

<Accordion title="로그인하기 전에 Meta Ads 비용 구성 창이 닫히는 이유는 무엇인가요?">

구성을 수행하는 브라우저와 동일한 브라우저에서 Meta Ads에 로그인한 경우 창에서 해당 사용자 인증 정보를 사용하여 Meta Ads에 자동으로 연결됩니다. 앱스플라이어에 대한 액세스 권한이 이미 부여된 경우, 할 일이 없으므로 창이 닫힙니다.

</Accordion>

<div id="why-is-there-a-discrepancy-in-cost-data-for-apps-in-the-amazon-app-store" />

<Accordion title="Amazon 앱 스토어의 앱에 대한 비용 데이터에 불일치가 있는 이유는 무엇인가요?">

앱스플라이어의 데이터와 달리 Meta Ads는 Android 기반 Amazon 앱과 달리 Android 앱의 비용 데이터를 구분하지 않습니다. 따라서, Amazon 사용자의 비용 데이터는 원래 Amazon 캠페인 대신에 다른 Android 사용자를 타게팅하는 캠페인으로 어트리뷰션됩니다.

</Accordion>

<div id="how-to-connect-cost-data-of-a-new-facebook-ad-account-while-my-old-account-is-linked" />

<Accordion title="이전 계정이 연결된 상태에서 새 Meta Ads 계정의 비용 데이터를 연결하는 방법은 무엇입니까?">

새 광고 계정으로 전환하고 싶지만 Meta Ads 비용이 이미 앱스플라이어를 통해 이전 광고 계정과 연결되어 있다면 Meta Ads를 통해 광고 계정을 분리하고 앱스플라이어에서 새 광고 계정을 연결해야 합니다.

1. Meta Ads에서 **설정** > **비즈니스 연동**으로 이동합니다.
2. **활성** 탭에서 앱스플라이어 연동을 제거합니다.  

   [![](https://files.readme.io/8dc7c577d4497aac2206dc46db683c2de9a48f4b23674f81560b04b82a3cf44f-4411031030033.png)](https://files.readme.io/8dc7c577d4497aac2206dc46db683c2de9a48f4b23674f81560b04b82a3cf44f-4411031030033.png)
3. 앱스플라이어 대시보드로 이동하여 새로운 광고 계정과 비용을 연결합니다.

</Accordion>

## Facebook SDK FAQ

<div id="who-needs-facebooks-sdk" />

<Accordion title="Facebook SDK는 누구에게 필요한가요?">

앱스플라이어 SDK를 연동하기 전에, 앱에 이미 Facebook SDK가 연동되어 있을 수 있습니다. 그렇지 않더라도, 앱스플라이어 SDK 외에 Facebook SDK가 정말로 필요한지 궁금할 수 있습니다. 그리고 만약 그렇다면, 중복되는 리포팅 없이 두 SDK가 공존할 수 있을까요?

앱은 다음에 대해 Facebook SDK를 필요로 하지 않습니다.

* **사용자 유입:** 앱스플라이어 SDK는 Meta Ads 사용자들의 모바일 유저 유입 어트리뷰션 목적의 모든 처리를 담당하며, 인게이지먼트, 앱 설치, 세션과 설치 후 이벤트도 포함합니다.
* **딥링킹**: 링크를 클릭했을 때 앱을 열고 앱 내 특정 페이지나 활동에 사용자를 딥링킹하려면 Facebook SDK 없이 OneLink만 사용하면 됩니다. iOS 유니버설 링크, Android 앱 링크 및 URI 스킴을 사용하여 이를 수행할 수 있습니다. 자세한 내용은 <Anchor target="_blank" href="https://www.facebook.com/business/help/1627795160837067?id=1858550721111595">Meta 고객 센터</Anchor>를 참조하세요.  

  **참고:**   
  정적 광고(카탈로그 아님)의 경우 iOS 유니버설 링크 및 Android 앱 링크는 앱**이 대상으로 선택된 캠페인에서만 지원됩니다.**  
  예를 들어, Meta에서 인지도 캠페인을 설정하면 이 캠페인은 **앱**을(를) 목적지로 선택할 수 없으므로 iOS 유니버설 링크와 Android 앱 링크가 지원되지 않습니다.  

  다이내믹 광고의 경우 iOS 유니버설 링크, Android 앱 링크, URI 스킴을 [여기](/docs/meta-ads-faq#can-onelink-links-be-used-for-app-opening-and-deep-linking-in-facebook-dynamic-product-ads)에 설명된 대로 사용할 수 있습니다.  

  Meta Ads는 원링크 URL을 폐기하고, 앱을 여는 Meta Ads 앱 링크를 만들어 사용자를 딥링킹합니다.

앱은 다음의 경우 앱스플라이어 SDK 외에 Facebook SDK를 필요로 합니다.

* **디퍼드 딥링킹**:  
  Meta Ads DDL 값은 전환 데이터에서 사용할 수 없습니다. 클라이언트는 Meta와 조정해야 하며, 일반적으로 이 데이터를 액세스하려면 Facebook SDK가 필요합니다.
* **다이나믹 제품 광고 캠페인 데이터**: 다이나믹 제품 광고에 대한 데이터는 Facebook SDK를 통해서만 얻을 수 있습니다.
* **기타 Meta Ads 기능**: 인증, 광고 수익화, 소셜 공유, 사용자 초대 등 어트리뷰션과 관련 없는 이유로 Facebook SDK가 필요할 수 있습니다.

> 📘 **참고**
>
> 딥링킹 및 디퍼트 딥링킹과 관련된 상기 정보와 권장 사항은 라이브 광고와는 다른 메커니즘을 사용하는 Meta Ads의 사용 가능한 데모/미리 보기 도구를 사용하여 수행한 철저한 테스트를 기반으로 합니다.

</Accordion>

<div id="avoiding-duplicates-with-facebook-sdk" />

<Accordion title="Facebook SDK와 중복 방지">

<Anchor target="_blank" href="https://developers.facebook.com/docs/app-events/faq#faq_593792547454717">앱에 앱스플라이어와 Facebook SDK</Anchor>가 모두 있는 경우, 설치 및 인앱이벤트는 Facebook SDK를 통해 리포트된 다음 앱스플라이어를 통해 Meta Ads 서버에 포스트백을 통해 리포트됩니다. 어떻게 중복 리포팅을 피할 수 있을까요?

* **설치의 경우** Meta는 설치를 중복 제거합니다. 즉, **중복이 없으며** 각 설치는 한 번만 계산된다는 뜻입니다.
* **인앱 이벤트의 경우**, Meta Ads는 인앱 이벤트를 중복 제거하지 않으므로 이로 인해 이중 집계 및 부정확한 인앱 이벤트 보고가 발생할 수 있습니다. Meta Ads에서 이러한 중복을 피하려면 다음 중 하나를 고려하세요.
  * Facebook SDK에서 이벤트를 설정하지 마세요.
  * Android의 경우 앱스플라이어에서 <Anchor target="_blank" href="/marketers/ko/docs/meta-ads-in-app-event-mapping">Meta Ads 인앱이벤트 매핑</Anchor>을 비활성화합니다.  
    iOS 14.5 이상에 대해 SKAN 어트리뷰션을 활성화하려면 <Anchor target="_blank" href="/marketers/ko/docs/skadnetwork-skan-interoperation-with-meta-ads#in-app-event-mapping">인앱이벤트를 Facebook Ads로 매핑</Anchor>해야 함을 알아두세요.

</Accordion>

## Meta Ads 어트리뷰션 FAQ

<div id="attributing-agencies-with-facebook" />

<Accordion title="Meta Ads로 대행사 어트리뷰션">

대행사 및 Meta 캠페인 관리 파트너는 앱스플라이어에서 광고주를 대신하여, 또는 광고주의 자체 Meta Ads 캠페인과 함께 Meta Ads 캠페인을 운영하고 어트리뷰션할 수 있습니다. 에이전시 캠페인을 에이전시로 어트리뷰션 측정하기 위해서는 캠페인 이름이 반드시 에이전시 이름으로 시작해야 합니다.

iOS 14 사용자의 경우 **하나의** 에이전시만 특정 광고 계정에 대한 캠페인을 실행할 수 있습니다. <Anchor target="_blank" href="/marketers/ko/docs/skadnetwork-skan-interoperation-with-meta-ads#skan-상호-운용성-앱스플라이어---meta-ads">Meta Ads와 앱스플라이어 SKAdNetwork 상호 운용성에</Anchor>대해 자세히 알아보세요.

대행사 및 Meta Ads 설치 어트리뷰션에 대한 더 자세한 내용은 <Anchor target="_blank" href="/partners/ko/docs/about-agency-accounts#srn-설정">여기</Anchor>를 참조하세요.

추가로, **대행사는 Meta Ads 기여 기간 및 리타겟팅 설정을 변경할 수 없습니다**. 변경이 필요한 경우는 광고주에게 요청해야 합니다.

또한 에이전시는 Meta Ads로 전송하는 인앱이벤트 포스트백을 수정할 수 없습니다. Meta Ads에서 어트리뷰션이 설정되지 않은 설치(에이전시가 발생시키지 않은 것)을 포함하여 모든 설치에 대한 정보를 요구하기 때문입니다.

아래 이미지는 에이전시가 Meta Ads 캠페인을 관리할 수 있도록 광고주가 설정해야 하는 모든 설정값을 보여줍니다.

[![advertiser-vs-agency-facebook-int-new.png](https://files.readme.io/c07ed13221c23223f99442a52a643004447361f1a7b48c2a2735507039ef350c-14238179231377.png)](https://files.readme.io/c07ed13221c23223f99442a52a643004447361f1a7b48c2a2735507039ef350c-14238179231377.png)

</Accordion>

<div id="attribution-for-facebook-for-outofstore-android-apps" />

<Accordion title="Google Play 외 앱 마켓 Android 앱에 대한 Meta Ads 어트리뷰션">

Meta Ads는 Google Play 외 다른 스토어, 예를 들어 바이두에 있는 Android 앱에 대해 모바일 앱 설치 캠페인 생성을 허용하지 않습니다.

하지만 다음 지시에 따라 Meta Ads에서 Google Play 외 앱 마켓 앱을 광고할 수 있고 설치 기록도 할 수 있습니다.

1. 개발자는 사용하는 Google Play 외 앱 마켓을 위해 각각 별도의 APK를 준비해야 합니다. 더 자세한 내용은 <Anchor target="_blank" href="/marketers/ko/docs/set-up-multi-store-android-attribution">여기</Anchor>에서 확인하세요.
2. Meta Ads에서 리드를 랜딩 페이지로 보낼 수 있는 **트래픽** 또는 **전환** 캠페인을 만들고, 모바일 어트리뷰션을 활성화해둡니다.
3. 랜딩 페이지에는 **앱 다운로드** 버튼을 꼭 포함해야 합니다. 이 버튼은 APK가 있는 Google와 앱스토어 외 앱 마켓으로 직접 연결합니다.
4. 리드가 버튼을 클릭하고 다른 스토어로 리디렉션됩니다. 앱 설치를 완료하면 앱스플라이어는 MMP API를 통해 해당 사용자를 Meta Ads에 어트리뷰트 합니다.

> 📘 **참고**
>
> Google와 앱스토어의 앱에 동일한 솔루션이 적용됩니다. 앱 마켓에 리디렉션하기 전에 <Anchor target="_blank" href="/marketers/ko/docs/set-up-smart-script-to-convert-web-visitors#facebook-click-id">랜딩 페이지가 필요합니다.</Anchor>

Amazon 앱 어트리뷰션과 관련된 자세한 안내는 <Anchor target="_blank" href="/marketers/ko/docs/set-up-multi-store-android-attribution#driving-users-to-the-amazon-app-store-from-facebook">여기</Anchor>에서 확인하세요.

</Accordion>

<div id="what-is-facebook-android-and-ios-crossattribution" />

<Accordion title="Meta Ads Android와 iOS 교차 어트리뷰션이란 무엇인가요?">

Meta Ads는 Meta Ads 계정을 기반으로 사용자를 식별합니다. 일부 사용자들은 동일한 Meta Ads 계정에 연동된 iOS 및 Android 기기를 가지고 있습니다.

이러한 사용자가 Android 기기에서는 앱 광고를 클릭하거나 보지만 iOS 기기에는 앱을 설치하는 경우 Meta Ads는 자신이 설치를 생성한 것으로 간주합니다. 결과적으로 Android 캠페인 이름이 iOS 대시보드에 표시됩니다.

> 📄 **예시**
>
> Andrew Josef는 Android 기기를 바쁘게 작동하고 있습니다. Andrew는 **Bubbles**라는 앱의 Android Meta 캠페인 광고를 클릭합니다. 앱은 다운로드하지 않습니다.
>
> 며칠 후 Andrew Josef는 iOS 기기에 **Bubbles** 앱을 오가닉으로 다운로드하고 실행합니다.
>
> 이러한 상황에서 앱스플라이어 어트리뷰션은 Meta Ads에서 Android Meta Ads 캠페인을 가져와 Andrew Josef가 다운로드하여 실행한 iOS 대시보드에 표시합니다.

</Accordion>

<div id="what-are-facebook-ads-channels" />

<Accordion title="Meta Ads 채널이란 무엇인가요?">

Meta Ads는 캠페인, 광고 세트 및 광고 뿐만 아니라 Meta Ads 채널 (Placement라고 불려짐) 별로 데이터를 구분할 수 있습니다.

* **Facebook** - Facebook 앱 사용자
* **Instagram** - Instagram 앱 사용자
* **Messenger** - Facebook 메신저 앱 사용자
* **AudienceNetwork** - Meta Ads 어필리에이트 또는 연관 앱 사용자
* **Threads** - Threads 앱 사용자
* **WhatsApp** - WhatsApp 앱 사용자

이 데이터를 사용하여 서로 다른 채널에서 얻게 되는 사용자 퀄리티를 비교할 수 있습니다.

![Facebook_channels.png](https://files.readme.io/f6b51baf3056f42ee32ac9709b1e4b3661580ce6148acfa36fc2bad102e7bfd8-4411036713745.png)

</Accordion>

<div data-zendesk-anchors="facebook-ads-faq=meta-ads-faq h_01HD1JTW2EP1MY3DD9136E9CHC=meta-ads-faq h_01HD1JTW2EN36V9SHH11283Y3A=i-dont-see-facebook-campaign-clicks-in-appsflyers-dashboard h_01HD1JTW2EJE0K034KSV8B3WZQ=can-appsflyer-show-the-campaign-level-and-ad-groups h_01HD1JTW2EFKCJMNBXBK2C55DN=is-facebook-data-shown-in-realtime h_01HD1JTW2E4SVC1Z9C3K6XJB2G=when-can-i-see-a-new-campaigns-data-on-appsflyer h_01HD1JTW2ECWSXFKQC1YBP1592=how-can-i-get-more-installs-from-facebook h_01K8B4YFDKKYP25V6NR12CE9RF=how-can-i-get-device-level h_google_play_referrer=google-play-install-referrer-api h_meta_install_referrer=google-play-install-referrer meta-install-referrer=google-play-install-referrer h_attribution_fields=%EC%BA%A0%ED%8E%98%EC%9D%B8-%EA%B7%80%EC%86%8D-%ED%95%84%EB%93%9C campaign-attribution-fields=%EC%BA%A0%ED%8E%98%EC%9D%B8-%EA%B7%80%EC%86%8D-%ED%95%84%EB%93%9C h_sdk_requirements=sdk-%EB%B0%8F-%EC%84%A4%EC%A0%95-%EB%85%B8%ED%8A%B8 sdk-requirements=sdk-%EB%B0%8F-%EC%84%A4%EC%A0%95-%EB%85%B8%ED%8A%B8 h_decryption=%EB%B3%B5%ED%98%B8%ED%99%94-%ED%82%A4-%EC%A0%9C%EC%B6%9C decryption-key=%EB%B3%B5%ED%98%B8%ED%99%94-%ED%82%A4-%EC%A0%9C%EC%B6%9C h_01HD1JTW2ED762B3K1QS6QC38M=do-you-make-facebook-raw-data-available-to-agencies h_01HD1JTW2EWQGK4QA9W8DFZTMH=i-dont-see-facebook-raw-data-in-the-installation-and-inapp-events-reports h_01HD1JTW2EYSBJ38WNS1HP5MCE=any-specific-columns-for-facebook-in-appsflyers-performance-reports h_01HD1JTW2ETTXQAP7ZSTMVGA8K=can-i-work-with-facebook-fmps-and-measure-performance-with-appsflyer h_01HD1JTW2EPY8W5Z84PBWSM86G=what-should-i-do-when-i-receive-the-following-warning h_01HD1JTW2ED2DNPTXAFYJTTGV3=what-happens-with-different-lookback-windows-than-on-facebook h_01HD1JTW2EXF1R0MA91ZSW7QG4=what-are-the-facebook-api-parameters how-long-do-you-keep-facebook%E2%80%99s-userlevel-data=how-long-do-you-keep-facebook-s-userlevel-data h_01HD1JTW2EPDNSY30J45JB443A=how-long-do-you-keep-facebook-s-userlevel-data h_01HD1JTW2EN8THFCRNZ0EBQ2M3=are-ios-universal-links-and-android-app-links-supported-in-meta-ads h_01JJVVX9NCSTVQKG2ENTGDRDK9=are-ios-universal-links-and-android-app-links-supported-in-metas-non-paid-content 01H7YJVNMVBRVTT9HH7KM8P33B=aem-attribution-is-not-working h_01HD1JTW2ETG739TWQVTKPCM2R=can-onelink-links-be-used-for-app-opening-and-deep-linking-in-facebook-dynamic-product-ads h_01JTG2474VHWAD8EK8ASPWZY0W=conversion-events-are-not-sent-to-meta-ads h_01K8B4AKSHSMP18MM0GAAZEQMF=can-i-use-get h_01K8B4AKSH7E8TBEG024NAV1A5=%EC%B0%B8%EA%B3%A0 facebook-ads-cost-faq=meta-ads-%EB%B9%84%EC%9A%A9-faq h_01HD1JTW2EEVD1PDPFW15K45CE=meta-ads-%EB%B9%84%EC%9A%A9-faq h_01HD1JTW2EE0WQ90J431Z8NQ8Q=getting-facebook-cost-data-in-the-appsflyer-dashboard h_01HD1JTW2ESVMMPK32W34PA54T=facebook-cost-example h_01HD1JTW2EVFXAET26WK2KSHTV=i-cant-see-old-facebook-cost-data-in-the-appsflyer-dashboard h_01HD1JTW2EJQHKVJF4XHWGVASJ=can-i-stop-cost-data-sync h_01HD1JTW2EYJTA2TRY7EE75KXA=cost-data-was-fine-for-a-few-months-but-it-stopped-displaying h_01HD1JTW2EYXZW2QCMQH5CRFSK=i-clicked-on-my-facebook-ad-5-minutes-ago-why-dont-i-see-the-click-in-appsflyer h_01HD1JTW2EYE2ZDNVRT5BCRXZJ=can-i-get-raw-data-on-clicks-and-impressions-from-facebook h_01HD1JTW2EG11RRBYHJ5BMJM5M=are-there-limitations-of-facebook-cost-data-by-geo h_01HD1JTW2E3RMV2TMPNZZ86HG5=what-are-the-limitations-of-facebook-cost-data-in-master-api h_01HD1JTW2EKVSAQ3706NC8JV9M=the-total-cost-doesnt-match h_01HD1JTW2EMJQJHBBB9SRJ6MZN=why-is-the-appsflyer-calculation-for-ecpi-different-from-the-cost-calculated-by-facebook-while-the-total-cost-is-identical h_01HD1JTW2E2S79FC9VAHA12X93=why-doesnt-cost-data-include-data-from-all-campaigns h_01HD1JTW2ET6Y2EHG29AQS09NA=is-facebook-cost-data-displayed-for-retargeting-campaigns h_01HD1JTW2EXTS1GDZHN8PAMV8C=why-does-the-facebook-cost-configuration-window-close-before-login h_01HD1JTW2FC0NJK00HZ76SFH30=why-is-there-a-discrepancy-in-cost-data-for-apps-in-the-amazon-app-store how-to-connect-cost-data-of%C2%A0a-new-facebook-ad-account-while-my-old-account-is-linked=how-to-connect-cost-data-of-a-new-facebook-ad-account-while-my-old-account-is-linked h_01HD1JTW2F401DA2NHBSPTKATB=how-to-connect-cost-data-of-a-new-facebook-ad-account-while-my-old-account-is-linked facebook-ads-sdk-faq=facebook-sdk-faq h_01HD1JTW2FPRCVGBF7CG7ZMKXF=facebook-sdk-faq h_01HD1JTW2F03XQSEVTFBW8JCX3=who-needs-facebooks-sdk h_01HD1JTW2FB09HM2CC83GMT901=%EC%B0%B8%EA%B3%A0-1 h_01HD1JTW2FNNHPZQARZNCCP7ER=avoiding-duplicates-with-facebook-sdk facebook-ads-attribution-faq=meta-ads-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-faq h_01HD1JTW2F2JV2BMDS40HFG6K0=meta-ads-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-faq h_01HD1JTW2FK1ZTPTA8B8A4N64Z=attributing-agencies-with-facebook h_01HD1JTW2F63AT1NGBY96Y6CCE=attribution-for-facebook-for-outofstore-android-apps h_01HD1JTW2FMKYDHNSM7G182EY0=%EC%B0%B8%EA%B3%A0-2 h_01HD1JTW2F8JT69CSN04GCZ91V=what-is-facebook-android-and-ios-crossattribution h_01HD1JTW2F5PY7A8T5NMHBZ87B=%EC%98%88%EC%8B%9C h_01HD1JTW2FX3QWC9BKWQ65E5B8=what-are-facebook-ads-channels" />
