---
title: Meta Ads — 웹사이트 및 앱용 웹 캠페인 생성
metadata:
  keywords:
    - Web Attribution
    - Web Attribution SDK
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
  created_at: '2026-04-28T14:18:14Z'
  edited_at: '2026-10-14T10:27:42Z'
  id: 46172666260241
  locale: ko
  section: Meta ads
  section_id: 6551109855761
  url: https://support.appsflyer.com/hc/ko/articles/46172666260241
---
> **한눈에 보기:** Meta가 광고 타겟팅을 최적화하고 캠페인 성과를 측정할 수 있도록, Conversions API(CAPI)를 통해 웹 전환 시그널을 Meta에 전송하는 웹사이트 앱용 Meta Ads 연동을 설정하세요.

## 개요

앱스플라이어는 웹사이트 앱 캠페인을 위해 Meta Ads(`metaweb_int`)와의 연동을 지원합니다. 이 연동을 통해 어트리뷰션 및 전환 데이터를 Meta의 Conversions API(CAPI)로 직접 보고할 수 있으며, Meta는 이를 활용하여 광고 타겟팅을 최적화하고 성과를 측정하며 맞춤 타겟을 생성합니다.

작동 방식은 다음과 같습니다. 사용자가 Meta 광고를 클릭하고 귀사의 웹사이트에 랜딩하면, 앱스플라이어는 구매 또는 회원가입과 같이 사용자가 완료한 모든 전환 이벤트를 캡처하여 CAPI를 통해 Meta에 해당 시그널을 전송합니다. Meta는 이 데이터를 활용하여 타겟팅을 개선하고 캠페인 결과를 평가합니다.

> 📄 **참고 항목**
>
> * <Anchor target="_blank" href="/marketers/ko/docs/web-performance-measurement-overview">앱스플라이어 웹 어트리뷰션 - 개요</Anchor>

> 📘 **참고**
>
> 현재 Meta Web 연동은 CAPI로 리인게이지먼트 포스트백을 전송하는 기능을 지원하지 않습니다.

### 필수 조건

Meta Ads 연동을 활성화하기 전에 다음 사항을 확인하세요.

* 앱스플라이어에 설정된 웹사이트 앱. 자세한 내용은 다음을 참조하세요.
  * <Anchor target="_blank" href="/marketers/ko/docs/adding-an-app-to-appsflyer#web">웹 앱 추가하기</Anchor>
  * <Anchor target="_blank" href="/marketers/ko/docs/configure-web-performance-measurement-settings">앱스플라이어 웹 어트리뷰션 설정 구성하기</Anchor>
* <Anchor target="_blank" href="https://www.facebook.com/business/help/1710077379203657?id=180505742745347">Meta 비즈니스 매니저의 비즈니스 계정</Anchor>.

## 웹사이트 및 앱을 위한 Meta Ads 웹 캠페인 설정하기

그리고 Meta 광고와 앱스플라이어 간의 통합을 정의하고 두 플랫폼 모두에서 캠페인 구성을 설정하는 작업이 포함됩니다. 두 부분을 순서대로 모두 완료하십시오.

* 2부: 앱스플라이어에서 Meta 웹 광고 연동 설정 (필수)
* 2부: Meta 광고에서 앱스플라이어 연동 설정하기 (필수)

## 1부: 앱스플라이어에서 Meta 웹 광고 연동 설정

먼저 Meta 광고 연동을 활성화하고 앱스플라이어가 CAPI에 보내는 포스트백을 설정합니다.

<div id="step-1-activate-the-meta-ads-integration" />

<Accordion title="1단계: Meta Ads 연동 활성화하기">

Meta 웹 광고 통합을 활성화하려면 다음 단계를 따르세요.

1. 앱스플라이어의 사이드 메뉴에서**협업**>**파트너 마켓플레이스**로 이동합니다.
2. Meta 광고를 검색하여 선택하세요.
3. **연동 설정**을 클릭하세요. 활성 **연동** 설정 페이지로 이동합니다.
4. **연동** 탭에서 **파트너 활성화**를 켭니다.

   > 📘 **참고**
   >
   > <Anchor target="_blank" href="/marketers/ko/docs/partner-activation-deactivation">파트너와 작업하는 동안에는 토글이 켜져(활성화) 있어야 합니다.</Anchor>

5. **'Pixel ID'** 필드를 입력하세요. Meta Ads Manager에서 픽셀 ID를 확인하려면:
   1. <Anchor target="_blank" href="https://www.facebook.com/ads/manager">광고 관리자</Anchor> 사이드 메뉴에서 **모든 도구** > **이벤트 관리자**로 이동합니다.

      > 📘 **참고**
      >
      > 오른쪽 상단의 드롭다운에서 올바른 비즈니스를 선택했는지 확인합니다.

   2. **이벤트 관리자** 사이드 메뉴에서 **데이터 소스**를 선택하면, 픽셀 목록이 표시됩니다. 선택한 비즈니스에 대한 픽셀이 없는 경우 동일한 화면에서 픽셀을 생성할 수 있습니다.
   3. 픽셀 이름 아래에 표시된 픽셀 ID를 복사한 다음, 앱스플라이어의 **‘픽셀 ID’** 필드에 붙여넣으세요.
6. **'액세스 토큰'** 필드를 입력하세요. 액세스 토큰을 검색하려면 다음 지침을 따르십시오.
7. **Meta 광고의 사용자 개인 정보 사용 제한(CCPA)** 을 켜면 <Anchor target="_blank" href="/marketers/ko/docs/send-opendsr-api-requests">데이터 보호법</Anchor> 준수할 수 있습니다.

   > 📘 **참고**
   >
   > CCPA 개인정보 보호 규정을 준수함으로써, 캘리포니아에 거주하는 Meta 광고 사용자로부터 수집되는 데이터가 제한됩니다.


</Accordion>

<div id="step-2-set-inapp-event-postbacks" />

<Accordion title="2단계: 인앱 이벤트 포스트백 설정">

앱스플라이어 이벤트를 Meta Ads 이벤트에 매핑하여, 앱스플라이어가 Meta Ads로 전송할 웹 전환 이벤트를 정의할 수 있습니다. 이러한 포스트백은 <Anchor target="_blank" href="https://www.facebook.com/business/help/1541268312717919?id=818859032317965">Meta Events Manager</Anchor>에서 확인할 수 있습니다. Meta는 매핑된 이벤트를 캠페인 최적화 및 리포팅에 사용합니다.

인앱 이벤트 포스트백 설정

1. **인앱 이벤트 포스트백**을 활성화하세요.
2. 필요한 경우, 인앱 이벤트 포스트백 창을 설정하십시오. 자세한 내용은 <Anchor target="_blank" href="/marketers/ko/docs/in-app-event-postback-configuration#인앱-이벤트-포스트백-기간">‘인앱 이벤트 포스트백 창 구성’을</Anchor> 참조하십시오.
3. **이벤트 추가**을 클릭하여 목록에 이벤트를 추가합니다.
4. **앱스플라이어 이벤트** 열의 드롭다운 상자에서 이벤트 이름을 선택합니다. 앱스플라이어는 귀사의 웹사이트에 연동된 웹 SDK 또는 귀사가 앱스플라이어로 전송하는 서버 간(S2S) 이벤트를 통해 이벤트 이름을 수신합니다.
5. **파트너 이벤트에 매핑됨** 열에서 드롭다운 상자에서 가장 적합한 사전 정의된 파트너 이벤트를 선택하거나 CUSTOM을 선택합니다.
6. **'유저'** 열에서 이벤트에 대한 발송 옵션을 선택하십시오:
   * **파트너만**: 이 이벤트가 GMP-DV360에 어트리뷰션되었을 때만 포스트백을 전송합니다.
   * **오가닉을 포함한 모든 미디어 소스** 파트너 매체와 오가닉 이벤트를 구분하지 않고, 성과가 발생한 모든 이벤트에 대해 포스트백 보내기.
7. **포함** 열에서 이벤트가 수익 값과 함께 전송될지 여부를 선택합니다. <Anchor target="_blank" href="/marketers/ko/docs/in-app-event-postback-configuration#포스트백에-포함할-데이터">포스트백에 포함할 데이터</Anchor> 참조

   > 🚧 **중요!**
   >
   > 구매 이벤트를 설정하는 경우, **포함** 열을 **값 및 수익**으로 설정합니다. 다른 옵션을 선택하면 포스트백이 실패합니다.

8. [선택 사항] **조건 추가** 아이콘을 클릭하여 이벤트에 대한 <Anchor target="_blank" href="/marketers/ko/docs/in-app-event-postback-configuration#조건부-인앱-이벤트-포스트백">조건을 설정</Anchor>합니다.
9. **연동 저장**을 클릭하세요.

</Accordion>

## 2부: Meta 광고에서 앱스플라이어 연동 설정하기

Meta Ads Manager에서 다음 단계를 완료하세요.

<div id="step-1-set-the-campaign-type-objective-and-goals" />

<Accordion title="1단계: 캠페인 유형, 목적, 목표 설정">

1. Meta 광고에 로그인하고 캠페인을 만듭니다.
2. **캠페인 목표**에서 다음 중 하나를 선택합니다:
   * **매출**: 이를 통해 Meta는 특정 이벤트(주요 KPI)에 대해 최적화할 수 있습니다.
   * **트래픽**: 이를 통해 Meta는 광고 클릭에 대해 최적화할 수 있습니다. 다른 KPI가 없거나 다른 KPI 이벤트의 발생 빈도가 너무 낮은 경우에만 이 옵션을 사용하십시오.
3. [선택 사항] 커스텀 목표를 추가하려면 다음 단계를 따르세요:

   1. Meta 광고에서 캠페인 목표로 설정하려는 맞춤 이벤트를 선택하고 Meta 광고에서 전환 행동으로 표시합니다.
   2. 앱스플라이어 **Meta 웹 연동** 페이지 **인앱 이벤트 포스트백**탭에서 앱스플라이어 이벤트를 사용자 지정 파트너 이벤트에 매핑하고(**파트너 이벤트에 매핑** 열), Meta 광고의 전환 액션과 동일한 이름으로 지정합니다.

   > 📘 **참고**
   >
   > Meta 캠페인 목표에 대한 자세한 내용은 <Anchor target="_blank" href="https://www.facebook.com/business/help/175683976191028">Meta 문서</Anchor>를 참고하세요.

4. **전환 위치**에서 **웹 사이트**를 선택합니다.
5. **픽셀**에서 앱스플라이어 파트너 마켓플레이스에 `metaweb_int`에 입력한 것과 동일한 픽셀 ID를 입력합니다. Meta 픽셀에 대해 자세히 알아보려면 Meta 문서를 참조하세요(로그인 필요).
6. **다음**을 클릭합니다.

</Accordion>

<div id="step-2-set-destination-url" />

<Accordion title="2단계: 도착 URL 설정">

1. **목적지 아래의 웹사이트 URL필드에서, 광고의 목적지 역할을 하는 URL을 입력하세요. iOS: 다음 중 하나를 수행합니다.**

   * 웹사이트 URL 유저가 웹사이트로 바로 이동하여 구매나 가입과 같은 웹 전환 이벤트를 완료하도록 유도하고 싶을 때는 웹사이트 URL을 사용하세요.
   * **AF 어트리뷰션 링크 (원링크)**: 사용자를 모바일 앱으로 리디렉션하고, 앱이 설치되어 있지 않은 경우 웹사이트로 대체 이동시키려면 AF 어트리뷰션 링크를 사용하세요. 이 기능은 캠페인이 앱 사용자와 웹 사용자 모두를 타겟팅할 때 유용합니다. 자세한 내용은 <Anchor target="_blank" href="/marketers/ko/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink">원링크 링크 및 경험을</Anchor> 참조하십시오.

   > 🚧 **중요!**
   >
   > 경우에 따라 AF 어트리뷰션 링크를 사용하면 오류가 발생할 수 있습니다. 이러한 상황이 발생하면 Meta 담당자에게 솔루션을 문의하거나, 대신 웹사이트 URL을 대상 URL로 사용하십시오.

2. **‘URL 파라미터 생성’을** 클릭하여 대상 URL에 URL 파라미터를 추가하세요.
3. 아래의 **사용자 지정 매개 변수**에서 **매개 변수 추가**를 클릭합니다.
4. 아래 표에 표시된 대로 앱스플라이어 파라미터를 Meta 가치에 매핑하십시오:

| AF 매개변수 | 매핑된 Meta 값 |
| --- | --- |
| <Anchor target="_blank" href="/marketers/ko/docs/about-link-structure-and-parameters#pid">`pid`</Anchor> | `metaweb_int` |
| <Anchor target="_blank" href="/marketers/ko/docs/about-link-structure-and-parameters#c">`c`</Anchor> | `{{campaign.name}}` |
| <Anchor target="_blank" href="/marketers/ko/docs/about-link-structure-and-parameters#af_siteid">`af_siteid`</Anchor> | `{{site_source_name}}` |
| <Anchor target="_blank" href="/marketers/ko/docs/about-link-structure-and-parameters#af_c_id">`af_c_id`</Anchor> | `{{campaign.id}}` |
| <Anchor target="_blank" href="/marketers/ko/docs/about-link-structure-and-parameters#af_adset">`af_adset`</Anchor> | `{{adset.name}}` |
| <Anchor target="_blank" href="/marketers/ko/docs/about-link-structure-and-parameters#af_adset_id">`af_adset_id`</Anchor> | `{{adset.id}}` |
| <Anchor target="_blank" href="/marketers/ko/docs/about-link-structure-and-parameters#af_ad">`af_ad`</Anchor> | `{{ad.name}}` |
| <Anchor target="_blank" href="/marketers/ko/docs/about-link-structure-and-parameters#af_ad_id">`af_ad_id`</Anchor> | `{{ad.id}}` |

결과 URL의 예시:

```http
https://www.example.com?pid=metaweb_int&c={{campaign.name}}&af_siteid={{site_source_name}}&af_c_id={{campaign.id}}&af_adset={{adset.name}}&af_adset_id={{adset.id}}&af_ad={{ad.name}}&af_ad_id={{ad.id}}
```

> 📘 **참고**
>
> 광고가 클릭되면 Meta는 대상 URL 뒤에 자동으로 를 추가합니다`fbclid={{fbclid}}`.

> 👍 **팁**
>
> 캠페인 분석을 간편하게 하려면 캠페인 이름의 접두사나 접미사로 캠페인 유형(웹 또는 모바일)을 포함시키세요. 예를 들어, `campaign-name_web`.

> 📄 **참고 항목**
>
> * 모든 관련 파라미터를 포함하여 광고 URL을 구성하는 모범 사례에 대해서는 <Anchor target="_blank" href="/marketers/ko/docs/about-traffic-source-resolution">‘트래픽 소스 확인 정보’를</Anchor> 참조하세요.

</Accordion>

<div id="step-3-select-tracked-events" />

<Accordion title="3단계: 추적된 이벤트 선택">

**'추적'** 섹션을 사용하여 광고를 통해 홍보하는 전환 이벤트를 선택하세요. <Anchor target="_blank" href="https://www.facebook.com/business/help/898185560232180?id=1205376682832142">이벤트</Anchor> 관리자를 통해 이벤트를 설정합니다.

> 🚧 **중요!**
>
> 선택하지 마십시오. 이렇게 하면 Meta가 SRN API를 통해 해당 전환을 자신의 성과로 집계하게 되어, 리포팅 및 최적화 결과가 실제와 어긋날 가능성이 있습니다.

</Accordion>

## 웹 어트리뷰션 데이터 보기

설정을 마친 후 어트리뷰션 데이터를 검토할 때 다음과 같은 내용을 확인할 수 있습니다:

* **로데이터 내보내기 및 API 응답에는** 메타 웹 활동과 관련된 필드에`media_source` ‘메타 웹’이 포함됩니다.
* 웹 캠페인 설정 세부 정보를 확인하려면, 웹 캠페인 생성 시 사용된 PID가 로 표시된`facebook_int` 필드를`original_url` 확인하십시오.

> 📘 **참고**
>
> 웹사이트 앱 캠페인에 대한 대시보드 리포팅 기능은 아직 제공되지 않습니다. 향후 출시에서는 웹 캠페인 성과를 다른 채널과 함께 분석할 수 있는 통합 리포팅 화면이 제공될 예정입니다.

## 웹 비용과 연계하여 웹 어트리뷰션 데이터를 측정하세요

대시보드 및 <Anchor target="_blank" href="/marketers/ko/docs/set-up-and-use-roi360-cost-etl-reports#set-up-cost-etl">Cost ETL 리포트</Anchor>에서 Meta Ads의 웹 어트리뷰션 데이터와 웹 비용 데이터에 대한 종합적인 성과 현황을 확인하려면, <Anchor target="_blank" href="/marketers/ko/docs/roi360-onboarding-guide#roi360-소개">ROI360 패키지가</Anchor> 설치되어 있는지 확인하고 다음 설정을 완료해야 합니다.

1. `metaweb_int`**‘비용’** 탭이나 **‘비용 설정’** 페이지에서 (를 통해가 아닌`facebook_int`) 를 통해 비용을 웹사이트 앱에 연결하세요. 비용과 연동하는 방법에 대한 자세한 내용은 <Anchor target="_blank" href="/marketers/ko/docs/set-up-roi360-cost-api-to-measure-cost-data#enabling-cost-api">‘비용 데이터 측정을 위한 ROI360 비용 API 설정’을</Anchor> 참조하십시오.
2. 랜딩 페이지 URL에 캠페인 ID (`af_c_id`)를 포함시키세요. 웹 어트리뷰션과 연계된 비용, 클릭 수, 임프레션 수를 가장 세밀한 수준에서 확인하려면 URL에 캠페인 계층 구조 전체가 포함되어 있는지 확인하십시오.

## 특징 및 제약 사항

| 특징 | 비고 |
| --- | --- |
| 클릭과 노출 | 웹 캠페인의 클릭 수 및 임프레션을 <Anchor target="_blank" href="/marketers/ko/docs/roi360-onboarding-guide">확인하려면 ROI360</Anchor> 구독이 필요합니다. |

<div data-zendesk-anchors="overview=%EA%B0%9C%EC%9A%94 h_01KQA78RE9FRENQAK31Q641C0N=%EA%B0%9C%EC%9A%94 h_01KQC27K5KWP3A6HMM2W7N3MVB=%EC%B0%B8%EA%B3%A0-%ED%95%AD%EB%AA%A9 h_01KQA78RE9F82ZBVF4YZHZTEEX=%EC%B0%B8%EA%B3%A0 prerequisites=%ED%95%84%EC%88%98-%EC%A1%B0%EA%B1%B4 h_01KQA78RE93B09A9YH2FRB3XRR=%ED%95%84%EC%88%98-%EC%A1%B0%EA%B1%B4 set-up-meta-ads-web-campaigns=%EC%9B%B9%EC%82%AC%EC%9D%B4%ED%8A%B8-%EB%B0%8F-%EC%95%B1%EC%9D%84-%EC%9C%84%ED%95%9C-meta-ads-%EC%9B%B9-%EC%BA%A0%ED%8E%98%EC%9D%B8-%EC%84%A4%EC%A0%95%ED%95%98%EA%B8%B0 h_01KQA78RE9J681CJ8DQNWJC37H=%EC%9B%B9%EC%82%AC%EC%9D%B4%ED%8A%B8-%EB%B0%8F-%EC%95%B1%EC%9D%84-%EC%9C%84%ED%95%9C-meta-ads-%EC%9B%B9-%EC%BA%A0%ED%8E%98%EC%9D%B8-%EC%84%A4%EC%A0%95%ED%95%98%EA%B8%B0 part-1-set-up-meta-ads-integration-in-appsflyer=1%EB%B6%80-%EC%95%B1%EC%8A%A4%ED%94%8C%EB%9D%BC%EC%9D%B4%EC%96%B4%EC%97%90%EC%84%9C-meta-%EC%9B%B9-%EA%B4%91%EA%B3%A0-%EC%97%B0%EB%8F%99-%EC%84%A4%EC%A0%95 h_01KQA78RE93JYCV2P0DDZC0A4B=1%EB%B6%80-%EC%95%B1%EC%8A%A4%ED%94%8C%EB%9D%BC%EC%9D%B4%EC%96%B4%EC%97%90%EC%84%9C-meta-%EC%9B%B9-%EA%B4%91%EA%B3%A0-%EC%97%B0%EB%8F%99-%EC%84%A4%EC%A0%95 h_01KQA78RE94B1JSVJFWR1V9QE5=step-1-activate-the-meta-ads-integration h_01KQA78REA5VN1229F2J3QH794=%EC%B0%B8%EA%B3%A0-1 h_01KQA78REANHAQ88N4MXWM832D=%EC%B0%B8%EA%B3%A0-2 h_01KQA78REA08SNB0BKCJDJZ2R0=%EC%B0%B8%EA%B3%A0-3 h_01KQA78REACR7QTMQWJMV6VJSF=step-2-set-inapp-event-postbacks h_01KQA78REA1EB5ZHX4HKJSW7ZD=%EC%A4%91%EC%9A%94 part-2-set-up-appsflyer-integration-in-meta-ads=2%EB%B6%80-meta-%EA%B4%91%EA%B3%A0%EC%97%90%EC%84%9C-%EC%95%B1%EC%8A%A4%ED%94%8C%EB%9D%BC%EC%9D%B4%EC%96%B4-%EC%97%B0%EB%8F%99-%EC%84%A4%EC%A0%95%ED%95%98%EA%B8%B0 h_01KQA78REAEZQPDSKZ0GRNKEJJ=2%EB%B6%80-meta-%EA%B4%91%EA%B3%A0%EC%97%90%EC%84%9C-%EC%95%B1%EC%8A%A4%ED%94%8C%EB%9D%BC%EC%9D%B4%EC%96%B4-%EC%97%B0%EB%8F%99-%EC%84%A4%EC%A0%95%ED%95%98%EA%B8%B0 h_01KQA78REASX8JX1H37075WT82=step-1-set-the-campaign-type-objective-and-goals h_01KQA78REA5JZ44C4BE77JCHG8=%EC%B0%B8%EA%B3%A0-4 h_01KQA78REAKBGQRC713FZ3J02P=step-2-set-destination-url h_01KQA78REAXZ1BFGC5BR75ZB5X=%EC%A4%91%EC%9A%94-1 h_01KQA78REARWGQDCJ4KN3FM120=%EC%B0%B8%EA%B3%A0-5 h_01KQA78REA7MZSG5JZ1XX2C65P=%ED%8C%81 h_01KQA78REA3ZW7W9M3VFSQASB6=%EC%B0%B8%EA%B3%A0-%ED%95%AD%EB%AA%A9-1 h_01KQA78REASTZH19CM58M5Z43R=step-3-select-tracked-events h_01KQA78REBHCR1AHA254BTFZC6=%EC%A4%91%EC%9A%94-2 view-web-attribution-data=%EC%9B%B9-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%EB%8D%B0%EC%9D%B4%ED%84%B0-%EB%B3%B4%EA%B8%B0 h_01KQA78REBK1PWXNA1PM9118TA=%EC%9B%B9-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%EB%8D%B0%EC%9D%B4%ED%84%B0-%EB%B3%B4%EA%B8%B0 h_01KQA78REBAW2SM5DRD68DP8W1=%EC%B0%B8%EA%B3%A0-6 measure-web-attribution-data-with-web-cost=%EC%9B%B9-%EB%B9%84%EC%9A%A9%EA%B3%BC-%EC%97%B0%EA%B3%84%ED%95%98%EC%97%AC-%EC%9B%B9-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%EB%8D%B0%EC%9D%B4%ED%84%B0%EB%A5%BC-%EC%B8%A1%EC%A0%95%ED%95%98%EC%84%B8%EC%9A%94 h_01KNM00RR9TF8JRTJXWN23MF1S=%EC%9B%B9-%EB%B9%84%EC%9A%A9%EA%B3%BC-%EC%97%B0%EA%B3%84%ED%95%98%EC%97%AC-%EC%9B%B9-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%EB%8D%B0%EC%9D%B4%ED%84%B0%EB%A5%BC-%EC%B8%A1%EC%A0%95%ED%95%98%EC%84%B8%EC%9A%94 traits-and-limitations=%ED%8A%B9%EC%A7%95-%EB%B0%8F-%EC%A0%9C%EC%95%BD-%EC%82%AC%ED%95%AD h_01KQAE3JKMQ6ZEATDAEXBC4PT6=%ED%8A%B9%EC%A7%95-%EB%B0%8F-%EC%A0%9C%EC%95%BD-%EC%82%AC%ED%95%AD" />
