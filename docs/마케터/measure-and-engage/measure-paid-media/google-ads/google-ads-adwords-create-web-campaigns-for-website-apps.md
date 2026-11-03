---
title: 구글 광고(애드워즈) - 웹사이트 앱을 위한 웹 캠페인 생성
metadata:
  keywords:
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
  created_at: '2026-04-07T12:46:10Z'
  edited_at: '2026-10-14T10:27:43Z'
  id: 45498975339537
  locale: ko
  section: Google Ads
  section_id: 6551205645457
  url: https://support.appsflyer.com/hc/ko/articles/45498975339537
---
> **한눈에 보기:** 웹사이트 앱을 위한 구글 광고 통합을 설정하여 오프라인 전환 API(OCI)를 통해 구글에 웹 전환 신호를 전송합니다.

## 개요

앱스플라이어는 웹사이트 앱 캠페인을 위한 구글 광고(`googleads_int`)와의 통합을 지원하며, 구글 오프라인 전환 API(OCI)를 통해 전환 데이터를 보고합니다.

이 기사에서는 앱스플라이어와 구글 광고에서 웹 캠페인을 설정하는 방법을 배우게 되며, 구글 광고와 상호작용하고 귀하의 웹사이트에서 전환하는 사용자들을 타겟팅합니다.

캠페인 흐름은 사용자가 구글 광고를 클릭하고 귀하의 웹사이트에 도착할 때 시작됩니다. 사용자가 웹사이트 이벤트(예: 구매 또는 가입)를 완료하면, 앱스플라이어는 OCI를 통해 구글 광고에 전환 신호를 전송합니다. 구글은 이 데이터를 사용하여 광고 타겟팅을 최적화하고 캠페인 성과를 측정합니다.

> 📄 **참고 항목**
>
> * <Anchor target="_blank" href="/marketers/ko/docs/web-performance-measurement-overview">앱스플라이어 웹 귀속 - 개요</Anchor>

### 필수 조건

웹사이트 앱 캠페인을 위한 구글 광고 통합을 활성화하기 전에 다음 사항을 확인하십시오:

* 앱스플라이어에 설정된 웹사이트 앱
* 귀하의 웹사이트에 배포된 앱스플라이어 웹 SDK
* 적절한 역할 또는 권한이 있는 앱스플라이어 계정

### 구글 광고 웹 캠페인 설정 방법

설정은 두 부분으로 나뉩니다:

1. 앱스플라이어에서 Google Ads 연동 설정(필수)
2. 구글 광고에서 캠페인 설정(필수)

## 앱스플라이어에서 구글 광고 통합 설정

웹 캠페인을 위한 구글 광고 통합을 활성화하고 앱스플라이어가 OCI에 전송하는 포스트백을 설정하는 것으로 시작합니다.

<div id="step-1-activate-the-integration" />

<Accordion title="1단계: 연동 활성화 방법:">

1. 앱스플라이어의 사이드 메뉴에서**협업**>파트너 마켓플레이스로 이동합니다.
2. **Google Ads 웹**을 검색하여 선택합니다.
3. **연동 설정**을 클릭하세요. 활성 **연동** 설정 페이지로 이동합니다.
4. 앱 드롭다운에서 웹 앱을 선택합니다.
5. **연동** 탭에서 **파트너 활성화**를 켭니다.

   > 📘 **참고**
   >
   > 파트너와 작업하는 동안에는 토글이 켜져(활성화) 있어야 합니다.

6. **고객 ID**를 입력합니다. Google Ads Manager에서 불러올 수 있습니다.
   1. Google Ads 계정에 로그인합니다.
   2. 오른쪽 상단에서 Google 계정 아이콘을 클릭하고 고객 ID가 표시되는 위치까지 아래로 스크롤합니다.
   3. 다음 중 하나를 수행하십시오:
      * 앱 캠페인을 운영하는 여러 Google Ads 계정이 있는 경우, 계정 간 전환 추적을 위해 관리자 계정(MCC)의 고객 ID를 사용해야 합니다. 고객 ID 필드와 MCC 고객 ID 텍스트 상자에 MCC ID(특정 계정의 고객 ID가 아님)를 붙여넣고 두 상자에 동일한 ID를 입력합니다.  자세한 내용은 <Anchor target="_blank" href="https://support.google.com/google-ads/answer/3061730?sjid=4528491462900554442-NC">구글의 MCC 계정 구성에 대한 지침</Anchor>을 참조하십시오.
      * 광고를 실행하기 위해 단일 Google Ads 계정만 사용하는 경우, 고객 ID 텍스트 상자에 계정 ID를 붙여넣고 MCC 고객 ID 텍스트 상자는 비워 두십시오.
7. 앱스플라이어가 Google Ads에 전환을 업로드할 수 있도록 하려면 **Google로 로그인합니다**.
8. Google에서, 고객 ID를 불러온 MCC 계정의 관리자 계정을 선택하세요.
9. **허용**을 클릭합니다.

   > 📘 **참고**
   >
   > Google에 로그인하고 아래 단계에서 앱스플라이어가 토큰을 가져오도록 허용하면 *누락된 토큰* 오류 메시지가 더 이상 나타나지 않습니다. 로그인 후에도 오류가 지속되면 토큰에 필요한 권한이 있는지 확인하세요.


</Accordion>

<div id="step-2-set-inapp-event-postbacks" />

<Accordion title="2단계: 인앱 이벤트 포스트백 설정">

웹사이트 이벤트를 Google Ads 전환 작업에 매핑하십시오. AppsFlyer는 이러한 이벤트를 OCI를 통해 Google에 전송하여 전환 기반 최적화를 지원합니다.

> 📘 **참고**
>
> 웹사이트 앱의 경우 모든 이벤트는 웹 이벤트이며 설치 이벤트는 없습니다. Google이 최적화할 각 이벤트는 해당 Google Ads 전환 작업 ID에 매핑되어야 합니다.

1. **인앱 이벤트 포스트백**을 활성화하세요.
2. 필요한 경우 **앱 내 이벤트 포스트백 창**을 설정하십시오. 창은 사용자의 첫 번째 웹사이트 전환 이벤트 발생 시 열립니다(모바일 설치 날짜의 웹 버전).
3. **이벤트 추가**를 클릭하세요.
4. **AppsFlyer 이벤트** 열에서 전송할 웹사이트 이벤트를 선택하십시오(예: `purchase`, `sign_up`).

   > 📘 **참고**
   >
   > 방문 이벤트는 제외됩니다. 이 드롭다운에는 사용자 정의 웹 이벤트만 사용할 수 있습니다.

5. **파트너 이벤트에 매핑됨** 열에서 Google Ads **전환 작업 ID**를 입력하십시오. 이 작업을 수행하기 전에 Google Ads에서 전환 작업을 생성해야 합니다(아래 2부의 2단계 참조). 전환 작업 ID를 찾으려면:
   * Google Ads에서 전환 작업 페이지를 엽니다.
   * 세부정보 탭을 엽니다.
   * 페이지 URL에서 `ctid=*` 쿼리 매개변수의 값을 복사합니다. 예를 들어, `ctid=123456789`인 경우 `123456789`을 입력하십시오.
6. **사용자 출처** 열에서 **이 파트너 전용**를 선택하여 Google Ads에만 귀속된 이벤트를 전송하십시오.
7. **포함** 열에서 포스트백에 수익 값을 포함할지 여부를 선택하십시오.
8. **연동 저장**을 클릭하세요.

</Accordion>

## Google Ads에서 웹 전환 캠페인 설정하기

<div id="step-1-set-the-campaign-type-objective-and-goals" />

<Accordion title="1단계: 캠페인 유형, 목적, 목표 설정">

1. Google Ads에 로그인하여 캠페인을 만듭니다.
2. 캠페인 목표를 선택합니다.
   * 모든 목표는 적용 가능하지만 **앱 프로모션**은 모바일 앱 캠페인에만 해당됩니다.
   * 특정 웹사이트 전환 이벤트에 따라 최적화를 위해 **판매** 또는 **리드**를 추천합니다.
3. 귀하의 **전환 목표**를 선택하십시오. 기본적으로 계정 수준의 목표가 표시됩니다. 그것들을 유지하거나 관련 없는 항목을 제거할 수 있습니다.
   * 최적화하려는 목표가 목록에 없으면 사용자 정의 전환 작업을 생성하십시오(아래 2단계 참조).
4. 캠페인 유형을 선택합니다.
   * 제품 카탈로그와 검증된 도메인이 필요한 **쇼핑**을 제외한 모든 유형이 적용 가능합니다.

</Accordion>

<div id="step-2-create-conversion-actions" />

<Accordion title="2단계: 전환 작업 생성">

AppsFlyer에서 매핑한 각 웹사이트 이벤트에 대해 Google Ads에서 해당 전환 작업을 생성하십시오. 생성한 후, 전환 작업 ID를 복사하여 이전 섹션의 AppsFlyer 이벤트 매핑에 붙여넣으십시오.

1. Google Ads에서 사이드 메뉴에서 **목표 > 전환 > 요약**을 엽니다.
2. **+ 새 전환 작업**을 클릭합니다.
3. 전환 데이터 소스로 **가져오기**를 선택한 다음, 다음 중 하나를 선택하십시오:
   * **API 또는 업로드를 사용한 수동 가져오기 > 클릭을 통한 전환 추적**
   * **CRM, 파일 또는 기타 데이터 소스 > 클릭으로 인한 전환 추적**을 선택하고 데이터 소스에서 *‘이 단계를 건너뛰고 나중에 데이터 소스 설정’*을 선택합니다.
4. **계속**을 클릭하세요.
5. **전환 목표**에서 전환 동작 카테고리를 선택합니다.
6. **전환 이름**을 입력합니다.

   > 🚧 **중요!**
   >
   > GBRAID/WBRAID(GCLID 외 추가로)와 함께 오프라인 전환 API를 사용하려면 전환 작업의 **Count** 필드가 **‘매번’** (기본값)으로 설정되어 있고 *‘한 번’*으로 설정되어 있지 않은지 확인하십시오.

7. **전환 이름**을 입력하고 **추가**를 클릭하십시오.

   > 📘 **참고**
   >
   > 캠페인을 단일 동작에만 최적화하려는 경우 해당 동작만 이 카테고리에 포함하세요. 예를 들어, 첫 번째 열기 전환 동작에 맞춰 캠페인을 최적화하려면 해당 캠페인이 해당 카테고리에서 유일한 캠페인이어야 합니다. 그러면 캠페인 생성 시 성과 최적화를 위한 전환 목표로 이 카테고리를 선택할 수 있습니다.

8. **저장 후 계속**을 클릭한 다음 데이터 소스를 설정하지 않고 **완료**를 클릭합니다. 새로운 전환 작업은 처음에 "비활성"으로 표시될 수 있지만, 실제 데이터가 전송되면 "활성"으로 변경됩니다.
9. 새 전환 동작을 앱스플라이어 포스트백 이벤트에 매핑하려면 새 전환 동작 ID를 검색하세요. 전환 목표 **요약 페이지**에서 생성한 전환 동작을 클릭하고 전환 동작 페이지 URL에서 `ctid=*` 쿼리 파라미터의 값을 복사합니다.
10. 앱스플라이어에서 구글에서 최적화하도록 하려는 포스트백 이벤트의 **파트너에 매핑됨 이벤트** 열에 `ctid` 값을 붙여넣습니다. 다음을 참조하세요. 인앱 이벤트 포스트백 설정

</Accordion>

<div id="step-3-set-the-campaigns-final-url" />

<Accordion title="3단계: 캠페인의 최종 URL 설정">

Google은 <Anchor target="_blank" href="https://support.google.com/google-ads/answer/6080568?sjid=9660882197247124000-EU">최종 URL</Anchor>을 "사람들이 광고를 클릭한 후 도달하는 웹사이트의 웹페이지 URL 주소, 즉 '랜딩 페이지'로 알려져 있습니다."라고 정의합니다.

1. Google Ads에서 **캠페인** > 광고 페이지를 엽니다.
2. 광고 행에서 수정 아이콘을 클릭합니다.
3. **최종 URL 필드**에 랜딩 페이지의 URL을 입력하십시오.

   > 🚧 **중요!**
   >
   > 최종 URL은 앱스플라이어 URL(원링크 또는 단일 플랫폼 어트리뷰션 URL)이 될 수 없습니다. 그럴 경우 캠페인이 거부될 수 있습니다. 리디렉션이 없는 직접 웹 주소만 사용하십시오.
   >
   > 최종 URL에 AF 어트리뷰션 파라미터를 추가하고 Google ValueTrack 파라미터에 매핑할 수 있습니다(예: `af_c_id={campaignid}`). Google 광고가 클릭되고 랜딩 페이지가 로드되면 이러한 매개변수가 페이지에서 사용 가능합니다. 사용 가능한 ValueTrack 파라미터에 대해 알아보려면 <Anchor target="_blank" href="https://support.google.com/google-ads/answer/6305348">Google 문서</Anchor>를 참조하세요.
   >
   > 예시:
   >
   > ```http
   > https://example.com?product=1234&af_c_id={campaignid}
   > ```


> 📘 **참고**
>
> Google 웹 광고 캠페인은 참여당 두 개의 URL을 사용할 수 있습니다: 최종 URL과 추적 템플릿 URL. 그러나 광고 목적지가 웹사이트인 웹사이트 앱 캠페인에서는 추적 템플릿 URL이 필요하지 않습니다. 캠페인 목표가 웹에서 모바일로 전환될 때만 추적 템플릿 URL이 필요할 수 있습니다. 자세한 내용은 <Anchor target="_blank" href="/marketers/ko/docs/google-ads-adwords-create-web-based-campaigns">Google Ads 웹-앱 캠페인 기사</Anchor>를 참조하십시오.

</Accordion>

## 웹 귀속 데이터 보기

Google Ads 캠페인에 대한 웹 귀속 데이터는 크로스 플랫폼 대시보드와 원시 데이터 내보내기에서 사용할 수 있습니다:

* **대시보드** <Anchor target="_blank" href="/marketers/ko/docs/my-dashboards#crossplatform-dashboard">크로스 플랫폼 대시보드</Anchor>에서 웹 및 앱 데이터가 나란히 표시되어 플랫폼 전반에 걸친 캠페인 성과를 통합적으로 볼 수 있습니다.
* 로데이터 내보내기   웹 귀속 데이터는 <Anchor target="_blank" href="/marketers/ko/docs/raw-data-export-page">원시 데이터 내보내기 페이지</Anchor>에서도 사용할 수 있습니다.
  * `media_source` 필드는 Google Ads에 귀속된 웹 이벤트에 대한 `googleadwords_int`를 보여줍니다.

> 📘 **참고**
>
> 이 통합 보고 뷰를 통해 웹과 앱 캠페인 성과를 한 곳에서 분석할 수 있으며, 전체 모바일 및 웹 비용 보고도 포함됩니다.

## 웹 비용으로 웹 귀속 데이터 측정하기

Google Ads의 웹 귀속 데이터와 웹 비용 데이터에 대한 완전한 성과 뷰를 얻으려면 대시보드와 <Anchor target="_blank" href="/marketers/ko/docs/set-up-and-use-roi360-cost-etl-reports#set-up-cost-etl">비용 ETL 보고서</Anchor>에서 <Anchor target="_blank" href="/marketers/ko/docs/roi360-onboarding-guide#roi360-소개">ROI360 패키지</Anchor>를 보유하고 다음 설정을 완료해야 합니다:

1. `googleadwords_int` ( `googleads_int`를 통해서가 아니라)에서 **비용** 탭 또는 **비용 설정** 페이지를 통해 웹사이트 앱에 비용을 연결하십시오. 비용 연결 방법에 대한 자세한 내용은 <Anchor target="_blank" href="/marketers/ko/docs/set-up-roi360-cost-api-to-measure-cost-data#enabling-cost-api">비용 데이터 측정을 위한 ROI360 비용 API 설정</Anchor>을 참조하십시오.
2. 랜딩 페이지 URL에 캠페인 ID (`af_c_id`)를 포함하십시오. URL에 비용, 클릭 및 노출을 웹 귀속에 가장 세분화된 수준으로 보기 위해 전체 캠페인 계층이 포함되어 있는지 확인하십시오.

## 인앱 이벤트 포스트백 문제 해결

이벤트 데이터가 Google Ads에 나타나지 않는 경우, 지원팀에 연락하기 전에 다음 사항을 확인하십시오.

<div id="set-token-permissions" />

<Accordion title="토큰 권한 설정">

Google Ads에서 액세스 토큰이 오프라인 전환을 업로드하는 데 필요한 권한을 가지고 있는지 확인하십시오:

1. Google 개발자 콘솔로 이동하십시오.
2. `uploadClickConversions`에 다음 OAuth 범위가 포함되어 있는지 확인하십시오: `https://www.googleapis.com/auth/adwords`https://www.googleapis.com/auth/adwords
3. 앱스플라이어의 연동 탭에서 **Google로 로그인** 클릭.
4. MCC 계정의 관리자 계정을 선택하십시오.
5. **허용**을 클릭합니다.

</Accordion>

<div id="mcc-customer-id" />

<Accordion title="MCC 고객 ID">

앱을 위한 캠페인을 실행하는 여러 Google Ads 계정이 있는 경우, MCC 계정의 고객 ID를 사용해야 합니다. <Anchor target="_blank" href="https://support.google.com/google-ads/answer/6139186">MCC 계정 구성에 대한 Google 지침</Anchor>을 참조하세요.

</Accordion>

<div id="conversion-action-id" />

<Accordion title="전환 작업 ID">

포스트백 인앱 이벤트가 올바른 전환 작업 ID에 매핑되어 있는지 확인하십시오. Google Ads에서 전환 작업 ID를 찾으려면 [여기](#step-2-create-conversion-actions)를 참조하세요. 전환 작업을 생성하십시오.

</Accordion>

## 특징 및 제약 사항

| 특징 | 비고 |
| --- | --- |
| 클릭과 노출 | 웹 캠페인에 대한 클릭 및 노출은 <Anchor target="_blank" href="/marketers/ko/docs/roi360-onboarding-guide">ROI360 구독</Anchor>이 필요합니다. |

<div data-zendesk-anchors="overview=%EA%B0%9C%EC%9A%94 h_01KNM00RR7V9BAA2BSPDECHC9F=%EA%B0%9C%EC%9A%94 h_01KQC2B644Y44631ZQKC1HPEF4=%EC%B0%B8%EA%B3%A0-%ED%95%AD%EB%AA%A9 prerequisites=%ED%95%84%EC%88%98-%EC%A1%B0%EA%B1%B4 h_01KNM00RR7H7A9CE06APEZSXKR=%ED%95%84%EC%88%98-%EC%A1%B0%EA%B1%B4 how-to-set-up-a-google-ads-web-campaign=%EA%B5%AC%EA%B8%80-%EA%B4%91%EA%B3%A0-%EC%9B%B9-%EC%BA%A0%ED%8E%98%EC%9D%B8-%EC%84%A4%EC%A0%95-%EB%B0%A9%EB%B2%95 h_01KNM00RR77P8VD2YJ2R7DZBVX=%EA%B5%AC%EA%B8%80-%EA%B4%91%EA%B3%A0-%EC%9B%B9-%EC%BA%A0%ED%8E%98%EC%9D%B8-%EC%84%A4%EC%A0%95-%EB%B0%A9%EB%B2%95 set-up-the-google-ads-integration-in-appsflyer=%EC%95%B1%EC%8A%A4%ED%94%8C%EB%9D%BC%EC%9D%B4%EC%96%B4%EC%97%90%EC%84%9C-%EA%B5%AC%EA%B8%80-%EA%B4%91%EA%B3%A0-%ED%86%B5%ED%95%A9-%EC%84%A4%EC%A0%95 h_01KNM00RR7E8MFSTGYKFEJDS1C=%EC%95%B1%EC%8A%A4%ED%94%8C%EB%9D%BC%EC%9D%B4%EC%96%B4%EC%97%90%EC%84%9C-%EA%B5%AC%EA%B8%80-%EA%B4%91%EA%B3%A0-%ED%86%B5%ED%95%A9-%EC%84%A4%EC%A0%95 h_01KNM00RR71ZXB72H8X1YXWKED=step-1-activate-the-integration h_01KNM00RR84CCGBR3T5WG7C5VW=%EC%B0%B8%EA%B3%A0 h_01KNM00RR86C5VKBVTA9X6QRAS=%EC%B0%B8%EA%B3%A0-1 h_01KNM00RR8BCJTMPZ29C841BY1=step-2-set-inapp-event-postbacks h_01KNM00RR8PSJ7FEAP7MMEJ1XG=%EC%B0%B8%EA%B3%A0-2 h_01KNM00RR89XJ0BZKFDXVC4860=%EC%B0%B8%EA%B3%A0-3 set-up-a-web-conversion-campaign-in-google-ads=google-ads%EC%97%90%EC%84%9C-%EC%9B%B9-%EC%A0%84%ED%99%98-%EC%BA%A0%ED%8E%98%EC%9D%B8-%EC%84%A4%EC%A0%95%ED%95%98%EA%B8%B0 h_01KNM00RR8SAS3TM1NG5DC58TF=google-ads%EC%97%90%EC%84%9C-%EC%9B%B9-%EC%A0%84%ED%99%98-%EC%BA%A0%ED%8E%98%EC%9D%B8-%EC%84%A4%EC%A0%95%ED%95%98%EA%B8%B0 h_01KNM00RR8S24AG7FMN6067PZ2=step-1-set-the-campaign-type-objective-and-goals h_01KNM00RR8H1ZFSHFT0DVB11GN=step-2-create-conversion-actions h_01KNM00RR8EV8XY02YJFV5XSX8=%EC%A4%91%EC%9A%94 h_01KNM00RR8N96SNP1YK0CTN6YZ=%EC%B0%B8%EA%B3%A0-4 h_01KNM00RR82NZSKB7K06HCP1VE=step-3-set-the-campaigns-final-url h_01KNM00RR8EP6J43G29Q8VVA5B=%EC%A4%91%EC%9A%94-1 h_01KNM00RR8A704MKGVVC6MQ2KN=%EC%B0%B8%EA%B3%A0-5 view-web-attribution-data=%EC%9B%B9-%EA%B7%80%EC%86%8D-%EB%8D%B0%EC%9D%B4%ED%84%B0-%EB%B3%B4%EA%B8%B0 h_01KNM00RR8EYJAX2KRGCM65E9M=%EC%9B%B9-%EA%B7%80%EC%86%8D-%EB%8D%B0%EC%9D%B4%ED%84%B0-%EB%B3%B4%EA%B8%B0 h_01KNM00RR86Q2GTHVNC505KCXZ=%EC%B0%B8%EA%B3%A0-6 measure-web-attribution-data-with-web-cost=%EC%9B%B9-%EB%B9%84%EC%9A%A9%EC%9C%BC%EB%A1%9C-%EC%9B%B9-%EA%B7%80%EC%86%8D-%EB%8D%B0%EC%9D%B4%ED%84%B0-%EC%B8%A1%EC%A0%95%ED%95%98%EA%B8%B0 h_01KNM00RR9TF8JRTJXWN23MF1S=%EC%9B%B9-%EB%B9%84%EC%9A%A9%EC%9C%BC%EB%A1%9C-%EC%9B%B9-%EA%B7%80%EC%86%8D-%EB%8D%B0%EC%9D%B4%ED%84%B0-%EC%B8%A1%EC%A0%95%ED%95%98%EA%B8%B0 troubleshooting-in-app-event-postbacks=%EC%9D%B8%EC%95%B1-%EC%9D%B4%EB%B2%A4%ED%8A%B8-%ED%8F%AC%EC%8A%A4%ED%8A%B8%EB%B0%B1-%EB%AC%B8%EC%A0%9C-%ED%95%B4%EA%B2%B0 h_01KNM00RR9Z0BM5EE62M17EE0F=%EC%9D%B8%EC%95%B1-%EC%9D%B4%EB%B2%A4%ED%8A%B8-%ED%8F%AC%EC%8A%A4%ED%8A%B8%EB%B0%B1-%EB%AC%B8%EC%A0%9C-%ED%95%B4%EA%B2%B0 h_01KNM00RR9CJJQAP4GAXZ9KK8N=set-token-permissions h_01KNM00RR9215H3KB024BBFZX2=mcc-customer-id h_01KNM00RR9DBR5979GA0FVD5AK=conversion-action-id traits-and-limitations=%ED%8A%B9%EC%A7%95-%EB%B0%8F-%EC%A0%9C%EC%95%BD-%EC%82%AC%ED%95%AD h_01KQAE3JKMQ6ZEATDAEXBC4PT6=%ED%8A%B9%EC%A7%95-%EB%B0%8F-%EC%A0%9C%EC%95%BD-%EC%82%AC%ED%95%AD" />
