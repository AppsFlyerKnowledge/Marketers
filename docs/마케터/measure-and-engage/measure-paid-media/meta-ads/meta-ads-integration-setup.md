---
title: Meta Ads 연동 설정
metadata:
  keywords:
    - iOS
    - Android
    - SDK
    - Facebook
    - App Install
    - View-Through
    - integrated partner
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
  created_at: '2013-01-24T20:13:58Z'
  edited_at: '2026-10-14T10:39:37Z'
  id: 207033826
  locale: ko
  section: Meta ads
  section_id: 6551109855761
  url: https://support.appsflyer.com/hc/ko/articles/207033826
---
> **한눈에 보기:** Meta Ads를 앱스플라이어와 연동하는 방법에 대해 알아보세요.

<div id="meta-ads-setup-guide" />

## Meta Ads 설정 가이드

앱스플라이어로 Meta 모바일 앱 광고를 어트리뷰션 하는 데에 소요되는 시간은 얼마인가요?

<Anchor target="_blank" href="/marketers/ko/docs/integrate-the-appsflyer-sdk">귀사의 앱에 앱스플라이어 SDK가 이미 연동되어 있고 Meta Ads에 앱이 정의되어 있다면, 1분도 채 걸리지 않습니다!</Anchor>

모바일 어트리뷰션에는 Facebook 로그인이나 Facebook SDK 연동이 필요하지 않습니다. 아래 [단계별 설정](#기본-meta-ads-어트리뷰션-설정) 지침을 따르세요. 이후 Meta Ads의 [고급 설정 옵션을](#고급-meta-ads-어트리뷰션-설정) 확인하세요.

<div id="basic-meta-ads-attribution-setup" />

## 기본 Meta Ads 어트리뷰션 설정

<div id="create-and-retreive-facebook-app-id" />

<Accordion title="Facebook 앱 ID를 생성하고 불러오세요.">

Meta Ads를 앱스플라이어와 연동하려면 먼저 <Anchor target="_blank" href="https://developers.facebook.com/docs/apps/register">Facebook 앱 ID</Anchor>를 생성한 후 불러오세요.

**Facebook 앱 ID 생성 방법**:

1. **Meta Ads**에서 <Anchor target="_blank" href="https://developers.facebook.com/apps">앱 대시보드</Anchor>로 이동합니다.
2. **앱**에서 **새 앱 생성**을 클릭하세요.
3. 앱 이름을 작성하고 고유한 네임스페이스를 입력하세요. 앱이 속한 플랫폼을 올바르게 추가해야 합니다. 그렇지 않으면 설치가 올바르게 측정되지 않을 수 있습니다.

**Facebook 앱 ID 확인 방법**:

1. **Meta Ads**에서 <Anchor target="_blank" href="https://developers.facebook.com/apps">앱 대시보드</Anchor>로 이동합니다.
2. 필요한 앱을 클릭하세요.
3. 화면 왼쪽 상단에 나오는 앱 ID를 클릭하여 복사하세요.

   [![](https://files.readme.io/86ef4cdfbb965a362c77527a532af2bb7e7eb2b39b477e4a93a2d2f22e19f377-30354101851793.jpg)](https://files.readme.io/86ef4cdfbb965a362c77527a532af2bb7e7eb2b39b477e4a93a2d2f22e19f377-30354101851793.jpg)

앱스플라이어는 앱 ID 당 데이터를 어트리뷰션합니다. 동일한 Facebok 앱 ID를 [안드로이드와 iOS 앱 모두에](https://developers.facebook.com/docs/app-ads/app-setup/) 사용할 수 있습니다. iOS 14 이상의 경우 Meta Ads는 계정을 앱 당 9개로 제한합니다.

</Accordion>

<div id="enable-meta-ads-device-level-data" />

<Accordion title="Meta Ads 장치 수준 데이터를 활성화하세요.">

2025년 6월 17일부터 Meta는 **고급 모바일 측정(AMM)** 리포팅을 다시 활성화했습니다. 수신 동의 시 다음을 받아보실 수 있습니다:

* 장치 수준 모바일 분석 정보
* Meta 캠페인에 대한 이벤트 수준 어트리뷰션 메트릭
* 기존 앱스플라이어 대시보드 및 내보내기 기능과의 완전한 연동

**AMM을 활성화하려면 다음 단계를 따르세요:**

1. <Anchor target="_blank" href="https://business.facebook.com/business/loginpage/?next=https%3A%2F%2Fdevelopers.facebook.com%2Fadvanced_mobile_measurement%2Fterms">Meta Ads</Anchor>를 방문하세요.
2. 관련 앱 ID를 선택하세요.
3. Meta의 고급 모바일 측정 약관에 동의하세요.

<div id="important" />

> 🚧 **중요 사항!**
>
> * Meta 개발자 앱의 관리자가 Meta의 AMM 약관에 동의해야 합니다.
> * 어트리뷰션 가시성이 확보된 장치 수준 데이터는 새롭게 어트리뷰션된 장치에 대해서만 제공되며, 이는 AMM 약관 동의 이후 가능합니다.
> * 인앱 이벤트는 어트리뷰션된 전환과 동일한 제한 상태 유지합니다. 이는 다음을 의미합니다:
>   * 고급 모바일 측정(AMM) 약관 동의 이전에 발생한 전환에 어트리뷰션된 인앱 이벤트는 계속해서 제한됩니다.
>   * AMM 약관에 동의한 이후 발생한 전환에 어트리뷰션된 인앱 이벤트는 로우 데이터 리포트에서 확인할 수 있습니다.

</Accordion>

<div id="set-the-meta-ads-active-integration" />

<Accordion title="Meta Ads 연동 활성화 설정">

1. 앱스플라이어에서의 사이드 메뉴에서 **협업** > **파트너 마켓플레이스**를 선택하세요.
2. Meta Ads를 검색한 다음 선택하세요.
3. **연동 설정**을 클릭하세요. 연동 설정 페이지로 이동합니다.
4. **연동 탭**에서, **파트너 활성화**를 클릭합니다.  
   **참고:** 파트너와 작업하는 동안에는 토글이 켜져 있어야 합니다(<Anchor target="_blank" href="/marketers/ko/docs/partner-activation-deactivation">활성화됨</Anchor>).
5. **일반 설정**에서:

   [![](https://files.readme.io/f03cc930c7242970294546ffbddb9c648d6eaeecc23b93aa1fadc945a6d777f8-30354101883281.png)](https://files.readme.io/f03cc930c7242970294546ffbddb9c648d6eaeecc23b93aa1fadc945a6d777f8-30354101883281.png)

   * [Facebook 앱 ID](#create-and-retreive-facebook-app-id) 필드에 [Facebook 앱 ID](#create-and-retreive-facebook-app-id)를 붙여넣으세요.
   * Meta Ads의 설치 리퍼러 [디크립션(decryption) 키](/docs/meta-ads-integration-setup#google-play-리퍼러-api-또는-meta-설치-리퍼러에서-불러오는-암호화된-데이터)를 붙여넣습니다.
6. **Advanced data sharing(고급 데이터 공유)** 을(를) 켜거나 끄고, 아래 [Advanced data sharing(고급 데이터 공유)](#advanced_data_sharing)를(을) 참조하세요. (2024년 10월 14일까지 모든 계정에 점진적으로 제공됩니다.)
7. **연동 저장**을 클릭합니다.

</Accordion>

<div id="optional--configure-recommended-settings" />

<Accordion title="[선택사항] 권장 설정 구성 방법:">

[![](https://files.readme.io/82b59d3460ea0487de932b7e49be7de10a8f4eaca151afaca281724f85d0c325-30354145601681.png)](https://files.readme.io/82b59d3460ea0487de932b7e49be7de10a8f4eaca151afaca281724f85d0c325-30354145601681.png)

* Meta Ads의 클릭-쓰루 룩백 윈도우와 일치시키려면 7일로 설정하세요.  
  ([기본값이 다른 몇 가지 특수한 사례](https://www.facebook.com/business/help/395050428485124?id=428636648170202)가 있음)
* Meta Ads의 뷰-쓰루 룩백 윈도우와 일치시키려면 1일로 설정하세요.
* <Anchor target="_blank" href="/marketers/ko/docs/set-up-re-attribution-window">리어트리뷰션 기간</Anchor>에 앱을 재설치하는 사용자를 어트리뷰션하려면 **재설치 어트리뷰션**을 켭니다.  
  재설치 어트리뷰션은 기존 설치 어트리뷰션 설정을 따르기 때문에 별도로 뷰-쓰루 어트리뷰션을 켜거나 룩백 윈도우를 구성하지 않아도 됩니다.

</Accordion>

<div id="advanced-meta-ads-attribution-setup" />

## 고급 Meta Ads 어트리뷰션 설정

Meta Ads의 기본 어트리뷰션 설정을 마쳤다면 이제 고급 어트리뷰션을 설정을 알아보겠습니다.

<div id="getting-userlevel-data-for-android-installs" />

<Accordion title="안드로이드 설치를 위한 장치 수준 데이터 가져오기">

<div id="google-play-install-referrer-api" />

#### Google Play 설치 리퍼러 API

Meta Ads는 Google Play 스토어로 사용자를 유도하는 안드로이드 앱 광고의 캠페인 메타데이터를 광고주와 공유합니다. 이 경우, 광고주는 Google Play 설치 리퍼러 API에서 어트리뷰션 필드를 확인할 수 있으며, 이를 사용하려면 <Anchor target="_blank" href="/marketers/ko/docs/basic-sdk-integration-guide#attribute-apps-published-on-google-play">앱에 API를 연동해야 합니다.</Anchor> Google Play 설치 리퍼러 API를 통해 제공되는 필드는 `gp_referrer` 매치 타입으로 앱스플라이어 로우 데이터 리포트에 반영됩니다. 이는 디크립션 키가 제출되고 설치가 Meta Ads에 어트리뷰션된 경우에만 볼 수 있습니다. 이를 통해 앱스플라이어는 광고 ID가 없는 사용자(LAT를 설정한 사용자)의 기여도를 분석할 수 있습니다.

<div id="meta-install-referrer" />

#### **Meta 설치 리퍼러**

<div id="note" />

> 📘 **참고**
>
> Meta 설치 리퍼러는 앱스플라이어가 디바이스의 로컬 저장소에서 광고 캠페인 메타데이터를 수신할 수 있도록 합니다. SDK를 활성화하여 Meta 설치 리퍼러에 접근할 수 있는 방법을 알아보려면 [개발자 허브](https://dev.appsflyer.com/hc/docs/install-android-sdk#meta-install-referrer)를 참고하십시오.

Google Play 설치 리퍼러 API 외에도, 앱스플라이어는 Meta 설치 리퍼러를 통해 디바이스의 로컬 스토리지에서 광고 캠페인 메타데이터를 수신할 수 있습니다. 이 데이터는 어트리뷰션 측정에 사용됩니다. Google Play 설치 리퍼러 API와 Meta 설치 리퍼러의 주요 차이점은 다음과 같습니다:

* Meta 설치 리퍼러는 임프레션 및 클릭 데이터를 포함할 수 있는 반면, Google Play 설치 리퍼러 API는 클릭 데이터만을 포함합니다.
* Meta 설치 리퍼러는 멀티 세션 데이터를 포함할 가능성이 있는 반면, Google Play 설치 리퍼러 API는 마지막 세션의 데이터만을 포함합니다(디바이스는 클릭이 발생한 세션과 동일한 세션에 앱을 설치해야 함)

결과적으로 Meta에 의해 어트리뷰션된 설치이 증가하는 것을 로우 데이터 리포트에서 확인할 수 있습니다. Google Play 설치 리퍼러 API 또는 Meta 설치 리퍼러를 통해 설치 어트리뷰션이 기록된 경우, 해당 데이터는 로우 데이터 리포트에서 확인할 수 있습니다. Meta 설치 리퍼러를 통한 어트리뷰션에 사용할 수 있는 필드는 앱스플라이어 로우 데이터 리포트에 Facebook 앱 어트리뷰션의 경우 `fb_referrer`으로, Instagram 앱 어트리뷰션의 경우 `ig_referrer`으로 매치 타입이 채워집니다. 이는 디크립션 키가 제출되고 설치이 Meta Ads에 어트리뷰션된 경우에만 볼 수 있습니다. Meta 설치 리퍼러 디크립션 키는 Google Play 설치 리퍼러에 사용된 것과 동일한 키이기 때문에 다시 제출할 필요 없습니다.

<div id="campaign-attribution-fields-available-via-the-referrer" />

#### **리퍼러를 통해 제공되는 캠페인 어트리뷰션 필드:**

* Ad ID
* Ad name
* Adset ID
* Adset name
* Campaign ID
* Campaign name
* Account ID
* Channel

<div id="note-1" />

> 📘 **참고**
>
> * **Google Play 설치 리퍼러 API의 경우:**
>   * 리퍼러 데이터를 제대로 전달하려면 앱스플라이어 SDK 버전이 **V5.4.0 이상**이어야 합니다. 리퍼러 데이터는 API가 제공하는 데이터 보다 우선시 되며, 별도의 제한을 받지 않습니다. 이 솔루션은 뷰-쓰루 어트리뷰션이 아닌 클릭-쓰루 어트리뷰션에 적용됩니다.
>   * 채널 필드는 Google Play 리퍼러 API로부터 수신된 채널 값(Meta가 Google Play에 전송한 값)에 의해 결정됩니다. 빈 문자열이 수신되면 채널 필드에 '없음'이 표시됩니다.
>
> * **Meta 설치 리퍼러의 경우:** 업데이트 공지에 설명된 **전제 조건 및 필요한 조치/strong>를 참고하십시오.**

<div id="meta-install-referrerfaq" />

#### Meta 설치 리퍼러—FAQ

**Meta 설치 리퍼러는 어떤 경우에 어트리뷰션에 사용되나요?**

* 설치 어트리뷰션의 경우:
  * 모든 캠페인에 대한 클릭-쓰루 어트리뷰션
  * 뷰-쓰루 어트리뷰션은 광범위하게 타겟팅(예: 연령 및 성별이 기본값으로 설정되어 있음) 하는 모든 Advantage+ 앱 캠페인 및 수동 앱 프로모션 캠페인에 대하여 지원됩니다.

* 호환성: Google Play 스토어 및 Google Play가 아닌 안드로이드 앱 스토어
* 제외: 여기에는 랜딩 페이지로 리디렉하는 캠페인은 포함되지 않습니다.

**Meta Ads에서 '광범위한 타겟팅'은 어떤 용도로 사용되나요?**

뷰-쓰루 설치 데이터를 수신하려면 광범위한 타겟팅이 필요합니다. 지원되는 캠페인 구성에는 다음이 포함됩니다.

* 연령: 기본 설정(18-65세 이상)이 적용됩니다.
* 성별: 기본 설정(모든 성별)이 적용됩니다.
* 지역: 국가 그룹 및 국가가 지원됩니다. **참고:** 도시나 우편번호 등을 특정하여 더욱 세밀하게 설정된 지역을 타겟팅하는 경우, 해당 지역을 포함하는 타겟팅 캠페인은 ‘완화됨’으로 설정해야 합니다.
* 세부 타겟팅: 관심 세그먼트, 행동 및 고급 인구 통계 설정은 완화됩니다.
* 커스텀 오디언스: 완화된 상태로 설정합니다.
* "완화된" 기법의 어트리뷰션을 적용하려면 광고 캠페인 설정 시 "어드밴티지 상세 타겟팅(Advantage detailed targeting)" 체크박스를 반드시 선택해야 합니다. [![](https://files.readme.io/58ad1f360c324a4e53290f2aa6bc18e30efea0a08f37012342f2811bbb022c6a-30354145604369.png)](https://files.readme.io/58ad1f360c324a4e53290f2aa6bc18e30efea0a08f37012342f2811bbb022c6a-30354145604369.png)

<div id="encrypted-data-from-google-play-referrer-api-or-meta-install-referrer" />

#### Google Play 리퍼러 API 또는 Meta 설치 리퍼러에서 불러오는 암호화된 데이터

Google Play 리퍼러 API 또는 Meta 설치 리퍼러에서 얻은 데이터는 Meta에 의해 암호화됩니다. 해당 데이터는 귀하의 메타 개발자 계정에서 제공되는 키를 사용하면 복호화 할 수 있습니다. “actions required(조치 필요)” 항목에 명시된 디크립션 키를 반드시 입력해야 합니다. 디크립션 키는 앱 당 한 번만 제출합니다.

키가 제공되지 않았거나 삭제된 경우, 위에서 언급한 캠페인 어트리뷰션 필드 없이도 리퍼러 정보만으로 설치가 Meta Ads로 어트리뷰션될 수 있습니다. 다음의 경우 발생할 수 있습니다:

* 설치가 Meta Ads의 성과로 기록되지 않은 경우
* Google Play 설치 리퍼러 API에서 데이터가 수신만 되고 디코딩 되지 않은 경우
* 마지막 클릭인 경우

**Meta에서 디크립션 키 얻는 방법:**

1. Meta 개발자 포털에 로그인하세요.
2. 오른쪽 상단의 **내 앱**로 이동합니다.
3. 디크립션 키에 접근하려는 앱을 선택하세요.
4. 페이지 왼쪽에 있는 **설정** > **기본**으로 이동합니다.
5. 안드로이드 섹션 Package Names 필드 아래에서 Install Referrer Decryption Key라고 표시된 디크립션 키를 확인할 수 있습니다. 참고: 패키지 이름과 Google Play 스토어를 설정했던 동일한 섹션입니다.

**앱스플라이어에서 디크립션 키 설정 방법:**

1. [필수] 앱에 앱스플라이어 SDK V5.4 이상이 적용되었는지 확인합니다. 이전 버전을 사용하지 마세요.
2. 앱스플라이어의 사이드 메뉴에서 **협업** > **활성화된 연동**을 선택합니다.
3. **Meta Ads**를 선택합니다.
4. **연동** 탭에서 **설치 리퍼러 디크립션 키**에 복사한 키를 붙여넣으세요. 이 과정은 앱 당 한 번만 수행합니다.
5. **연동 저장**을 클릭합니다.

</Accordion>

<div id="cost-clicks-and-impressions" />

<Accordion title="비용, 클릭 수, 노출 수">

[![meta_cost_tab.png](https://files.readme.io/5c840dbce9c019a8655e8b7b54b8d8e29f3128a8e7115065d0f4083b703b80c0-30354101895185.png)](https://files.readme.io/5c840dbce9c019a8655e8b7b54b8d8e29f3128a8e7115065d0f4083b703b80c0-30354101895185.png)

이 연동을 통해 캠페인, 애드 세트, 광고, 지역/국가에 대한 비용, 클릭 및 노출 수에 대한 집약형 데이터를 제공합니다. 지원되는 디멘션, 메트릭 및 기능에 대한 자세한 내용은 <Anchor target="_blank" href="/marketers/ko/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api">애드 네트워크 비용 연동 표</Anchor>를 참조하세요.

**참고:** 클릭 및 노출 수에 대한 데이터가 연동에 포함됩니다. 단, **비용 데이터를 받아보려면** <Anchor target="_blank" href="/marketers/ko/docs/roi360-cost-aggregation-overview?query=xpend">**ROI360**</Anchor> **구독**이 필요합니다.

**비용 API를 활성화하려면**:

1. Meta Ads 계정의 캠페인을 관리하려면, Meta Ads 사용자 계정으로 로그인되어 있어야 합니다. 로그인한 사용자는 반드시 Meta 비즈니스 관리자(Meta Business Manager)에서 모든 캠페인을 실행할 수 있는 권한이 있어야 합니다.
2. **비용** 탭으로 이동합니다.
3. **비용, 클릭 및 노출 데이터 가져오기**를 켭니다.
4. **f 로그인** 버튼을 클릭하면, Meta ads 비즈니스 또는 관리자 계정으로 로그인할 수 있습니다.
5. 창이 열리면, 앱스플라이어가 Meta ads 캠페인 데이터에 액세스할 수 있도록 허용합니다.  
   **참고**: 연동 후 첫 번째 데이터 동기화 및 후속 동기화에서 앱스플라이어는 최대 최근 7일 동안의 Meta Ads 비용 데이터를 수신합니다.

**연결된 Meta Ads 계정을 삭제하는 방법:** 작업 열에서 삭제를 원하는 계정에 마우스 커서를 이동하고 **연결 삭제**를 클릭합니다.

<div id="notes" />

> 📘 **참고**
>
> * Meta ads에 로그인된 경우 **f 로그인** 버튼을 클릭했을 때 창이 즉시 열렸다 닫힙니다. 이것은 정상적인 동작입니다.
> * Meta Ads에 권한을 가지고 있는 사용자가 여러 명이라면, <Anchor target="_blank" href="/marketers/ko/docs/meta-ads-faq#why-doesnt-cost-data-include-data-from-all-campaigns">전체 데이터를 얻기 위해서는</Anchor> 모든 사용자가 로그인하는 것이 좋습니다.

<div id="cost-data-sync-status" />

#### 비용 데이터 동기화 상태

<Anchor target="_blank" href="/marketers/ko/docs/set-up-roi360-cost-api-to-measure-cost-data#cost-api-status">비용 API 상태</Anchor>와 앱스플라이어가 마지막으로 일치하는 비용 데이터를 가져온 시점은, 비용(및 광고 수익) 연동 상태 대시보드 또는 개별 애드 네트워크 대시보드에서 확인할 수 있습니다.

여러 계정을 동기화하여 비용 데이터를 가져올 수 있습니다. 동기화된 각 계정에 대해, 앱스플라이어는 비용 연동 상태와 일치하는 비용 데이터를 마지막으로 불러온 시점을 표기합니다.

<Anchor target="_blank" href="/marketers/ko/docs/meta-ads-faq#meta-ads-비용-faq">비용, 클릭, 노출</Anchor> 정보를 추가해 데이터를 강화하세요.

</Accordion>

<div id="inapp-event-mapping" />

<Accordion title="인앱 이벤트 매핑">

[![meta_iae_postbacks.png](https://files.readme.io/8f2fd671a067684738964d245a9e80873bbb28f33a55c61ee0cb00a32ac9815e-30354145614865.png)](https://files.readme.io/8f2fd671a067684738964d245a9e80873bbb28f33a55c61ee0cb00a32ac9815e-30354145614865.png)

**인앱 이벤트를 매핑하려면:**

1. **인앱 이벤트 포스트백**을 켭니다.  
   앱에 Meta Ads 인앱 이벤트 매핑을 **최초로** 활성화할 때,**af\_app\_open**이 자동으로 **fb\_mobile\_activate\_app**에 매핑됩니다.
2. 다음 파라미터를 채웁니다.

| 파라미터 이름 | 설명 |
| --- | --- |
| **앱스플라이어 이벤트** | 이벤트의 이름은 앱스플라이어가 귀하의 앱에 연동된 SDK로부터 수신했거나 서버-투-서버 이벤트로부터 수신하여 나타나는 이름입니다.<br />**팁**: 찾고 있는 이벤트가 없나요?<ul><li>논오가닉 설치와 재점검으로 디바이스에 이벤트가 활성화되었는지 확인합니다.</li><li>**앱스플라이어 이벤트**에 입력한 다음 **커스텀 생성**을 클릭합니다. <Anchor target="_blank" href="/marketers/ko/docs/in-app-event-postback-configuration#커스텀-이벤트">커스텀 이벤트 매핑</Anchor>에 대해 더 알아보세요.</li></ul> |
| **파트너 이벤트에 매핑됨** | Meta Ads에 정의되어 있는 각 이벤트의 고유 이름 또는 ID. 사용할 수 있는 매핑 설정은 다음과 같습니다.<ul><li>**텍스트 필드:** Meta Ads에서 해당 이벤트 ID를 가져옵니다</li><li>**드롭다운 상자:** 사전 정의된 앱스플라이어 이벤트 중 가장 적합한 것을 선택합니다.</li><li>**변경 없이**: 이름 매핑 없이 이벤트를 있는 그대로 전송합니다.</li></ul> |
| **유입 출처** | 이벤트의 전송 옵션을 선택합니다.<ul><li>**이 파트너에게만 전송**: 이벤트가 Meta Ads에 어트리뷰션된 경우에만 포스트백을 전송합니다.</li><li>**오가닉을 포함한 모든 미디어 소스**: 파트너 및 오가닉 이벤트에 어트리뷰트된 이벤트에 대한 포스트백을 전송합니다.</li></ul> |
| **포함** | <ul><li>**데이터 없음(기본값)**: 이벤트 값 없이 이벤트 자체만 보냅니다.</li><li>**값 및 수익**: 매출 값(이벤트에 존재하는 경우)을 **포함하여** 모든 이벤트 파라미터를 전송합니다.</li><li>**수익이 없는 값**: 수익 값을 **제외한** 모든 파라미터를 전송합니다.</li></ul> |

3. 목록에 SDK 또는 서버-투-서버 이벤트를 추가하려면 **이벤트 추가**를 클릭합니다.

**이벤트 이름 관련 제한 사항:**

* 이벤트 이름 길이 제한: 2-40자
* 다음 문자는 사용할 수 없습니다.
  * 콜론(:)
  * 마침표(.)
  * 라틴어(영어) 이외의 문자 집합: 2020년 1월 12일부터 Meta Ads에서는 한자 사용이 제한됩니다. 앱스플라이어는 지원되는 문자 집합 외의 문자 세트는 테스트하지 않았으므로, 포스트백에서 해당 문자 세트 지원 여부를 Meta Ads에서 확인한 후에만 사용해야 합니다.
* 이벤트 이름은 대소문자를 구분합니다. 불일치를 방지하려면, 모든 미디어 소스와 앱 버전에서 이벤트 이름의 대소문자를 정확히 일치시켜 사용해야 합니다.

<div id="note-2" />

> 📘 **참고**
>
> Meta 광고는 <Anchor target="_blank" href="/marketers/ko/docs/meta-ads-in-app-event-mapping#mapping-ad-revenue-data-for-campaign-optimization">af\_ad\_revenue 이벤트를 올바른 Meta 광고 이벤트에 매핑</Anchor>하여 광고 수익 데이터를 기반으로 캠페인을 최적화할 수 있습니다.

</Accordion>

<div id="retargeting-attribution" />

<Accordion title="리타겟팅 어트리뷰션">

앱스플라이어의 Meta Ads 리타겟팅 어트리뷰션을 통해 광고주는 Facebook 광고에 대한 기존 사용자의 인게이지먼트를 어트리뷰션하고, 앱스플라이어 리포트를 이용하여 사용자 퀄리티 및 포스트 인게이지먼트를 측정 할 수 있습니다. 이 기능은 Facebook에서 기존 사용자를 타겟팅하는 캠페인을 활발히 운영 중인 경우에만 사용해야 합니다.

1. <Anchor target="_blank" href="/marketers/ko/docs/app-settings#reengagement-attribution">앱 설정 페이지에서 리타겟팅을 활성화</Anchor>합니다.
2. Meta Ads 파트너 페이지에서 **리인게이지먼트 어트리뷰션**을 설정합니다.
3. **리인게이지먼트 클릭-쓰루 룩백 윈도우**를 설정합니다.  
   리인게이지먼트 룩백 윈도우는 광고 클릭 후 앱이 실행되어 리인게이지먼트로 기록되는 기간입니다.   
   룩백 윈도우 단위(시간 혹은 날일)를 선택하고 슬라이더를 원하는 값으로 설정합니다.  
   [![](https://files.readme.io/86e0bb7d4dfa8e55720ed67d1ff8ea34f0e71df9df12382996bb7ea8817da4ba-30354101904785.png)](https://files.readme.io/86e0bb7d4dfa8e55720ed67d1ff8ea34f0e71df9df12382996bb7ea8817da4ba-30354101904785.png)
4. **리인게이지먼트 뷰-쓰루 어트리뷰션**을 활성화합니다.
5. **리인게이지먼트 뷰-쓰루 룩백 윈도우** 슬라이더를 원하는 값(최대 24시간)으로 설정합니다. 해당 윈도우는 광고 노출 시점부터 시작되며, 이 기간 내에 앱을 실행해야 노출이 리인게이지먼트로 기록됩니다.
6. **리인게이지먼트 윈도우**를 설정합니다.  
   해당 윈도우는 사용자의 인앱 이벤트가 리타겟팅 미디어 소스를 주요 출처로 하여 어트리뷰션되는 기간을 뜻합니다.  
   값을 일 단위(1&#126;90일), 시간 단위(최대 23시간) 또는 평생으로 설정할 수 있습니다. 기본 설정은 30일입니다.  
   [![](https://files.readme.io/6f589562cd6248697ffa8d5ebb4a72e2fdad118df6abf517e43b4fa23c3332ec-30354101914385.png)](https://files.readme.io/6f589562cd6248697ffa8d5ebb4a72e2fdad118df6abf517e43b4fa23c3332ec-30354101914385.png)

<Anchor target="_blank" href="/marketers/ko/docs/retargeting-attribution-guide">앱스플라이어 리타겟팅 어트리뷰션</Anchor>에 대해 더 알아보세요.

<Anchor target="_blank" href="/marketers/ko/docs/self-reporting-networks-srns#srn을-활용한-딥링킹">Meta Ads와 같이 SRN에서 사용자를 딥링크하는 방법</Anchor>에 대해 더 알아보세요.

<div id="whatsapp-retargeting-campaign-attribution" />

#### WhatsApp 리타겟팅 캠페인 어트리뷰션

앱스플라이어는 iOS와 Android 모두에서 딥링크 어트리뷰션을 통한 리엔게이지먼트용 WhatsApp 마케팅 메시지 캠페인의 측정을 지원합니다.

**연동 레벨**과 **앱 레벨** 모두에서 **리엔게이지먼트** 토글을 활성화하면 별도의 추가 설정 없이 해당 캠페인이 자동으로 측정됩니다.

어트리뷰션 데이터에서 이러한 캠페인 유형의 **채널** 필드에는 **"WhatsApp**"으로 표시됩니다.

</Accordion>

<div id="advanced_data_sharing" />

<Accordion title="고급 데이터 공유">

**고급 데이터 공유**가 활성화되면, Meta는 광고 ID(IDFA)를 제공하지 않은 디바이스를 포함하여 모든 디바이스에 대한 디바이스 수준 식별자가 포함된 포스트백 및 이벤트를 수신합니다.

또한, **고급 데이터 공유**가 활성화되면 앱스플라이어는 이러한 이벤트의 기여를 측정합니다. 비활성화된 경우, IDFA가 있는 디바이스에서 발생한 포스트백과 이벤트만 전송 및 어트리뷰션됩니다.

이 방법은 iOS 클릭-쓰루 및 뷰-쓰루 설치와 iOS 딥링크 리인게이지먼트를 단일 옵트아웃 기기와 이중 옵트아웃 기기에서도 어트리뷰션합니다. 어트리뷰션은 사용자의 마지막 터치를 기준으로 하며, 어트리뷰션 윈도우는 최대 24시간입니다.

<div id="use-deep-links-in-meta-ads-campaigns" />

<div id="advanced_matching_data_sharing" />

<div id="note-3" />

<div id="see-also" />

> 📘 **참고**
>
> 토글이 켜져 있고 Meta와 어트리뷰션 연결이 되지 않는다면, 공유된 이벤트가 Meta의 적격 기준을 충족하는지 확인하세요. **Meta 문서**를 참조하세요.

</Accordion>

<div id="comply-with-california-consumer-privacy-act-ccpa" />

<Accordion title="캘리포니아 소비자 개인 정보 보호법(CCPA) 준수">

CCPA 개인 정보 보호 규정으로 인해 미국 캘리포니아에 거주하는 Meta Ads 사용자 데이터는 제한적으로 제공됩니다.

**CCPA 준수를 활성화하는 방법:** **연동** 탭에서 **사용자 개인 정보(CCPA)의 Meta Ads 사용 제한**을 설정합니다.

<Anchor target="_blank" href="/marketers/ko/docs/send-opendsr-api-requests">데이터 보호법</Anchor>에 대해 더 알아보세요.

</Accordion>

<div id="ad-revenue-recording" />

<Accordion title="광고 수익 기록">

[![](https://files.readme.io/5c27f2adf0e4515a7ad0efac4776eb296874273e2af71e14c9be8bd65a983757-30354101917201.png)](https://files.readme.io/5c27f2adf0e4515a7ad0efac4776eb296874273e2af71e14c9be8bd65a983757-30354101917201.png)

앱에서 광고 수익화를 위해 Meta Audience Network Ad Revenue(Meta 잠재고객 네트워크 광고 수익)를 사용하고 있다면, 앱스플라이어의 Meta 광고 수익을 기록할 수 있습니다. 이에 따라 인앱 구매 수익 데이터 유무와 관계없이 **사용자 수익의 종합적인 현황을** 파악할 수 있습니다.

<div id="record-meta-audience-network-ad-revenue" />

#### Meta 오디언스 네트워크 광고 수익 기록

1. **광고 수익** 탭에서 **광고 수익 데이터 가져오기**를 설정합니다.
2. 수신을 원하는 집계된 광고 수익 데이터 유형을 선택합니다: **어트리뷰션 수익** 및/또는 **집계된 현금화 수익**:
   * **어트리뷰션 수익**: 사용자 유입 소스 기준 수익.  
     광고 수익 모델을 가장 잘 나타내는 이벤트를 **이벤트 소스**로 설정하세요. 예를 들어, 수익이 임프레션을 기반으로 하는 경우, ad\_viewed 이벤트를 앱스플라이어로 보내는 것을 권장합니다. 각각의 수익화 플랫폼에 대해 가장 적합한 이벤트를 개별적으로 설정할 수 있습니다. 하지만 `af_app_opened` 기본 설정된 이벤트를 사용할 수도 있습니다. 이 경우는 사용자가 앱을 열 때마다 광고 수익이 어트리뷰션됩니다.
   * **현금화 수익 집계**: 광고 출처 기준 수익
3. **광고 수익 이벤트**가 표시됩니다. 이것은 [source event]\_monetized 형식(예: Ad\_Watched\_Monetized)으로 광고 수익 이벤트를 표시하는 읽기 전용 필드입니다. 광고 수익 이벤트는 대시보드에서 추가 이벤트로 표시됩니다.
4. **Meta Ads 연결**을 클릭하여 Meta Ads에서 Meta Audience Network Ad Revenue 수집을 허용합니다. Meta ads으로 로그인하여 Meta Audience Network Ad Revenue를 승인합니다.
5. **Audience Network App ID(**[**Facebook App ID**](/docs/meta-ads-integration-setup#facebook-app-id))를 입력합니다. 이 정보는 Meta Audience Network에서 가져옵니다.
   * [Facebook 앱 ID](/docs/meta-ads-integration-setup#facebook-app-id)를 가져옵니다.
   * ID를 복사하여 앱스플라이어의 **Audience Network 앱 ID** 필드에 붙여넣습니다.
6. **광고 수익 저장**을 클릭하세요.

</Accordion>

<div id="permissions" />

<Accordion title="권한">

Meta Ads가 다양한 작업을 수행하고 사용 가능한 권한에 따라 데이터에 액세스할 수 있도록 설정합니다.

<Anchor target="_blank" href="/marketers/ko/docs/set-up-an-integrated-partner#permissions-tab">연동 파트너에게 권한 부여하기</Anchor>에 대해 더 알아보세요.

</Accordion>

<div id="aggregate-event-measurement-aem-for-ios" />

## iOS용 데이터 집약형 이벤트 측정(AEM)

앱스플라이어는 <Anchor target="_blank" href="/marketers/ko/docs/meta-ads-aggregate-event-measurement-aem-for-ios">Meta Ads 데이터 집약형 이벤트 측정(AEM)</Anchor> 솔루션을 지원합니다. 이 솔루션은 iOS 전환 및 인앱 이벤트를 최적화하며 Meta Ads에서 iOS 리인게이지먼트를 어트리뷰션하는데 도움이 됩니다.

<div id="meta-ads-integration-troubleshooting" />

## Meta Ads 연동 문제 해결

기본 연동을 완료했음에도 앱스플라이어 대시보드에서 Meta Ads의 결과가 보이지 않는 경우, 연동된 후에 Meta Ads에서 신규 설치가 있었는지 확인하세요.

그렇다면 아래의 주요 원인을 참고하여 문제를 해결하세요.

<div id="no-idfa-collection" />

<Accordion title="IDFA 수집되지 않음">

SDK 연동 가이드 – iOS에 명시된 바와 같이, IDFA 수집을 위해 프로젝트에 AdSupport.framework를 추가해야 합니다. 설치 로우 데이터 리포트를 통해 IDFA 열이 비어 있는지 확인하세요. iOS 앱의 경우 IDFA를, 안드로이드 앱의 경우 GAID를 수집할 수 있도록 앱을 설정하는 것이 좋습니다.  
iOS 14.5부터 IDFA를 수집하기 전에 Apple 앱 추적 투명성(ATT) 프롬프트를 표시하고 사용자 동의를 받아야 합니다.

**참고:** SKAdNetwork 어트리뷰션은 IDFA 유무에 영향을 받지 않습니다. 하지만 iOS 14 캠페인을 설정하는 동안 Meta Ads에서 iOS 14 캠페인 토글을 활성화해야 합니다.

</Accordion>

<div id="wrong-facebook-app-id" />

<Accordion title="잘못된 Facebook 앱 ID">

Facebook 앱 ID가 앱스플라이어에서 잘못 구성되었습니다.  
앱 ID가 올바르고 Meta Ads 대시보드의 값과 일치하는지 확인하세요.  

참고 - <Anchor target="_blank" href="https://developers.facebook.com/tools/explorer/?method=GET&path=&version=v6.0">Facebook의 Graph API</Anchor>를 사용하여 Facebook 앱 ID를 인증할 수 있습니다.

</Accordion>

<div id="app-status-on-meta-ads" />

<Accordion title="Meta Ads에서의 앱 상태">

어트리뷰션이 동작하기 위해서는 앱이 Meta Ads에서 **개발 중(In development)** 이 아닌 **라이브(Live)** 로 정의되어 있어야 합니다.

[![](https://files.readme.io/b982355eb0d3d858988866673d3f9ee4f081c43042221d11ebfb93afe05c36a4-30354101922577.png)](https://files.readme.io/b982355eb0d3d858988866673d3f9ee4f081c43042221d11ebfb93afe05c36a4-30354101922577.png)

</Accordion>

<div id="wrong-type-of-meta-ads-campaign" />

<Accordion title="잘못된 유형의 Meta Ads 캠페인">

Meta Ads 캠페인이 **모바일 앱 설치 광고** 또는 **모바일 앱 인게이지먼트**용인지 확인하세요. 다른 캠페인 목표에서 모바일 설치를 측정하려면 광고주는 Meta Ads 캠페인을 설정할 때 <Anchor target="_blank" href="/marketers/ko/docs/attributing-app-installs-to-non-mobile-ads-from-meta-ads">**앱 이벤트 기록** 옵션</Anchor>을 선택해야 합니다.

<div id="aem-attribution-is-not-working" />

<Accordion title="AEM 어트리뷰션이 작동하지 않습니다">

**고급 데이터 공유** 토글이 켜져 있고 Meta와 어트리뷰션 연결이 되지 않는다면, 공유된 이벤트가 Meta의 적격 기준을 충족하는지 확인하세요. [Meta 문서](https://www.facebook.com/business/help/716239976391518?id=1877298665783613)를 참조하세요.

</Accordion>

</Accordion>

<div id="meta-ads-app-install" />

<Accordion title="Meta Ads 앱 설치">

Meta 앱 설치 캠페인을 설정할 때는 드롭다운 목록에서 앱을 선택하거나 앱의 전체 스토어 URL을 입력할 수 있습니다. Meta Ads에서는 두 방법 모두 가능하지만, 앱스플라이어 어트리뷰션에서는 첫 번째 방법만 가능합니다.

올바른 설정 - 어트리뷰션 성공

[![](https://files.readme.io/5cb735144128035d752281f7d94e2015478c62049a2e96fc5a42400513f7fad3-30354101926033.png)](https://files.readme.io/5cb735144128035d752281f7d94e2015478c62049a2e96fc5a42400513f7fad3-30354101926033.png)

잘못된 설정 - 어트리뷰션 실패

[![](https://files.readme.io/77d508b62d5445cac071262cb35e4a89a6dfa5be439325254c0b8f6c5f51606c-30354145644561.png)](https://files.readme.io/77d508b62d5445cac071262cb35e4a89a6dfa5be439325254c0b8f6c5f51606c-30354145644561.png)

</Accordion>

<div id="ios-14-updates-relating-to-meta-ads" />

### Meta Ads와 관련된 iOS 14 업데이트

앱스플라이어는 Meta Ads와의 MMP 연동 시 *Advertiser Tracking Enabled* 플래그를 항상 적용되도록 합니다. 즉, 귀하가 앱스플라이어 계정에서 별도로 취해야 할 조치는 없습니다. 이 정보는 2021년 2월 게재된 Meta Ads 앱 가이드 iOS 14 체크리스트에 따라 구성되었습니다.

<div id="see-also-1" />

> 📄 **참고 항목**
>
> * iOS 14 관련 고려 사항은 <Anchor target="_blank" href="/marketers/ko/docs/skadnetwork-skan-interoperation-with-meta-ads">Meta Ads SKAN 상호 운영</Anchor> 항목을 참조하세요.
> * <Anchor target="_blank" href="/marketers/ko/docs/configuring-meta-campaign-management-partners">Meta 캠페인 관리 파트너 구성</Anchor> (<Anchor target="_blank" href="/marketers/ko/docs/bidalgo-meta-campaign-management-partner-configuration">Bidalgo</Anchor> ／ <Anchor target="_blank" href="/marketers/ko/docs/kenshoo-meta-campaign-management-partner-configuration">Kenshoo</Anchor> ／ <Anchor target="_blank" href="/marketers/ko/docs/adquant-meta-campaign-management-partner-configuration">Adquant</Anchor> ／ <Anchor target="_blank" href="/marketers/ko/docs/webpals-mobile-meta-campaign-management-partner-configuration">Webpals</Anchor>)

<div data-zendesk-anchors="facebook-ads-setup-guide=meta-ads-%EC%84%A4%EC%A0%95-%EA%B0%80%EC%9D%B4%EB%93%9C 01H7YJVNMSZ4WG4HWBZF648HZN=meta-ads-%EC%84%A4%EC%A0%95-%EA%B0%80%EC%9D%B4%EB%93%9C basic-facebook-attribution-setup=%EA%B8%B0%EB%B3%B8-meta-ads-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%EC%84%A4%EC%A0%95 01H7YJVNMTFW076FAJZGJWT4R9=%EA%B8%B0%EB%B3%B8-meta-ads-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%EC%84%A4%EC%A0%95 h_01JXYJW7AFB53PY7WHGM05HDMH=create-and-retreive-facebook-app-id h_01JKX03GC8ZSMGCSX84381QW0A=enable-meta-ads-device-level-data h_01JYPKG2RH3R08604V7B3NC5WQ=%EC%A4%91%EC%9A%94-%EC%82%AC%ED%95%AD h_01JXYHEFW19DJXXXRNN186E07B=set-the-meta-ads-active-integration %5Boptional%5D-configure-recommended-settings=optional--configure-recommended-settings h_01JXYHEFW15E6K39JY2VBCN79E=optional--configure-recommended-settings advanced-facebook-attribution-setup=%EA%B3%A0%EA%B8%89-meta-ads-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%EC%84%A4%EC%A0%95 01H7YJVNMTHF800PD5CEWPFS49=%EA%B3%A0%EA%B8%89-meta-ads-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%EC%84%A4%EC%A0%95 h_01JKX03GC8B4VKC6KJT4CZ9VT8=getting-userlevel-data-for-android-installs google-play-install-referrer-api=google-play-%EC%84%A4%EC%B9%98-%EB%A6%AC%ED%8D%BC%EB%9F%AC-api h_01JKX2BE00WYHMJ3RX1FK8DQV5=google-play-%EC%84%A4%EC%B9%98-%EB%A6%AC%ED%8D%BC%EB%9F%AC-api meta-install-referrer=meta-%EC%84%A4%EC%B9%98-%EB%A6%AC%ED%8D%BC%EB%9F%AC h_01JKX2BNRDHHNJCN257H3QBZ65=meta-%EC%84%A4%EC%B9%98-%EB%A6%AC%ED%8D%BC%EB%9F%AC h_01JKX03GC8JRZSD13TVDDM1MWE=%EC%B0%B8%EA%B3%A0 campaign-attribution-fields-available-via-the-referrer=%EB%A6%AC%ED%8D%BC%EB%9F%AC%EB%A5%BC-%ED%86%B5%ED%95%B4-%EC%A0%9C%EA%B3%B5%EB%90%98%EB%8A%94-%EC%BA%A0%ED%8E%98%EC%9D%B8-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%ED%95%84%EB%93%9C h_01JKX2CF8RE4T5R3V83FS1PBQR=%EB%A6%AC%ED%8D%BC%EB%9F%AC%EB%A5%BC-%ED%86%B5%ED%95%B4-%EC%A0%9C%EA%B3%B5%EB%90%98%EB%8A%94-%EC%BA%A0%ED%8E%98%EC%9D%B8-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%ED%95%84%EB%93%9C h_01JKX03GC9BG4GFDKR7JHG31BQ=%EC%B0%B8%EA%B3%A0-1 meta-install-referrer%E2%80%94faq=meta-%EC%84%A4%EC%B9%98-%EB%A6%AC%ED%8D%BC%EB%9F%ACfaq h_01JKX2DSY85X6570AHYKHM34KS=meta-%EC%84%A4%EC%B9%98-%EB%A6%AC%ED%8D%BC%EB%9F%ACfaq encrypted-data-from-google-play-referrer-api-or-meta-install-referrer=google-play-%EB%A6%AC%ED%8D%BC%EB%9F%AC-api-%EB%98%90%EB%8A%94-meta-%EC%84%A4%EC%B9%98-%EB%A6%AC%ED%8D%BC%EB%9F%AC%EC%97%90%EC%84%9C-%EB%B6%88%EB%9F%AC%EC%98%A4%EB%8A%94-%EC%95%94%ED%98%B8%ED%99%94%EB%90%9C-%EB%8D%B0%EC%9D%B4%ED%84%B0 h_01JKX2E4A44QHKADG4S8ZM9KC5=google-play-%EB%A6%AC%ED%8D%BC%EB%9F%AC-api-%EB%98%90%EB%8A%94-meta-%EC%84%A4%EC%B9%98-%EB%A6%AC%ED%8D%BC%EB%9F%AC%EC%97%90%EC%84%9C-%EB%B6%88%EB%9F%AC%EC%98%A4%EB%8A%94-%EC%95%94%ED%98%B8%ED%99%94%EB%90%9C-%EB%8D%B0%EC%9D%B4%ED%84%B0 01H7YJVNMTBN9RJ6Q7TJ1AJ0XX=cost-clicks-and-impressions 01H7YJVNMTGRBQG54DVMJDHDKS=%EC%B0%B8%EA%B3%A0-2 cost-data-sync-status=%EB%B9%84%EC%9A%A9-%EB%8D%B0%EC%9D%B4%ED%84%B0-%EB%8F%99%EA%B8%B0%ED%99%94-%EC%83%81%ED%83%9C 01H7YJVNMTRQAYG7TY29AX4MZS=%EB%B9%84%EC%9A%A9-%EB%8D%B0%EC%9D%B4%ED%84%B0-%EB%8F%99%EA%B8%B0%ED%99%94-%EC%83%81%ED%83%9C 01H7YJVNMTNRREKWY96CK9JJKV=inapp-event-mapping 01H7YJVNMT2DRVR26F8CDDTWHP=%EC%B0%B8%EA%B3%A0-3 01H7YJVNMV5AZ9G2KCKEFF1CSV=retargeting-attribution whatsapp-retargeting-campaign-attribution=whatsapp-%EB%A6%AC%ED%83%80%EA%B2%9F%ED%8C%85-%EC%BA%A0%ED%8E%98%EC%9D%B8-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98 h_01KBZ2CAGX18ZZPXQGMPTEPSCP=whatsapp-%EB%A6%AC%ED%83%80%EA%B2%9F%ED%8C%85-%EC%BA%A0%ED%8E%98%EC%9D%B8-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98 01H7YJVNMVSA4Y33MW6Q8Y777Y=advanced_data_sharing 01JDH9Y65409Y5E162NWJA25E3=%EC%B0%B8%EA%B3%A0-4 h_01JKTYRMD70ZGN31FSQ7BXF1HB=comply-with-california-consumer-privacy-act-ccpa 01H7YJVNMVWRG10SZY1B33H5EA=ad-revenue-recording record-meta-audience-network-ad-revenue=meta-%EC%98%A4%EB%94%94%EC%96%B8%EC%8A%A4-%EB%84%A4%ED%8A%B8%EC%9B%8C%ED%81%AC-%EA%B4%91%EA%B3%A0-%EC%88%98%EC%9D%B5-%EA%B8%B0%EB%A1%9D 01H7YJVNMV1TTHKMMX4TFB2BF3=meta-%EC%98%A4%EB%94%94%EC%96%B8%EC%8A%A4-%EB%84%A4%ED%8A%B8%EC%9B%8C%ED%81%AC-%EA%B4%91%EA%B3%A0-%EC%88%98%EC%9D%B5-%EA%B8%B0%EB%A1%9D 01H7YJVNMVMW5BXWEP8BPX4D7E=permissions aggregate-event-measurement-aem-for-ios=ios%EC%9A%A9-%EB%8D%B0%EC%9D%B4%ED%84%B0-%EC%A7%91%EC%95%BD%ED%98%95-%EC%9D%B4%EB%B2%A4%ED%8A%B8-%EC%B8%A1%EC%A0%95aem 01H7YJVNMVGFYMHE5FACTD9NS0=ios%EC%9A%A9-%EB%8D%B0%EC%9D%B4%ED%84%B0-%EC%A7%91%EC%95%BD%ED%98%95-%EC%9D%B4%EB%B2%A4%ED%8A%B8-%EC%B8%A1%EC%A0%95aem meta-ads-integration-troubleshooting=meta-ads-%EC%97%B0%EB%8F%99-%EB%AC%B8%EC%A0%9C-%ED%95%B4%EA%B2%B0 01H7YJVNMVCAQ6ETKBGCAM31B9=meta-ads-%EC%97%B0%EB%8F%99-%EB%AC%B8%EC%A0%9C-%ED%95%B4%EA%B2%B0 01H7YJVNMV3YRF59RX87TJCT8D=no-idfa-collection 01H7YJVNMVHCYVWKDW5WWPX1A5=wrong-facebook-app-id 01H7YJVNMVE9QJAXQBD4P14C88=app-status-on-meta-ads 01H7YJVNMVBRVTT9HH7KM8P33B=wrong-type-of-meta-ads-campaign h_01JKTYRMD7YPGJRZXR4Y66BAHG=aem-attribution-is-not-working 01H7YJVNMV4G3VP40E6VFD7SJD=meta-ads-app-install ios-14-updates-relating-to-facebook=meta-ads%EC%99%80-%EA%B4%80%EB%A0%A8%EB%90%9C-ios-14-%EC%97%85%EB%8D%B0%EC%9D%B4%ED%8A%B8 01H7YJVNMVQP5PR6XDHTCPXVDC=meta-ads%EC%99%80-%EA%B4%80%EB%A0%A8%EB%90%9C-ios-14-%EC%97%85%EB%8D%B0%EC%9D%B4%ED%8A%B8 h_01HDP0Y4CZBZEK5VZ6FG3T31JB=%EC%B0%B8%EA%B3%A0-%ED%95%AD%EB%AA%A9" />
