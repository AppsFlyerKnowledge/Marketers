---
title: Unity Ads 캠페인 구성
metadata:
  keywords:
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
  created_at: '2023-01-04T10:14:20Z'
  edited_at: '2026-10-14T10:37:42Z'
  id: 11904659502737
  locale: ko
  section: Amazon Ads
  section_id: 28703975923729
  url: https://support.appsflyer.com/hc/ko/articles/11904659502737
---
> **한눈에 보기:** 요약: 앱스플라이어 연동 파트너인 아마존 DSP(amazondsp\_int)는 앱 소유자에게 TV, 태블릿 및 모바일 디바이스용 앱스플라이어를 사용하여 클릭 및 보기 기반 어트리뷰션을 측정할 수 있는 기능을 제공합니다.

![mceclip0.png](https://files.readme.io/0a4c9078bd683c51bad40408c894f6e2b7314d7c369bd46ac90c3e622f62f0a7-11927906589329.png)

## 파트너 활성화

**전제 조건:** 연동 설정 전에 <Anchor target="_blank" href="/marketers/ko/docs/partner-integrations#contact-details">파트너에게 연락</Anchor>하여 계정을 개설하세요.

**연동 활성화 또는 편집하려면:**

1. **활성화 방법:** 앱스플라이어에서, 측면 메뉴에서 **협업** > **파트너 마켓플레이스**를 선택하세요.  
   **편집 방법**: 앱스플라이어의 측면 메뉴에서 **협업** > **활성화된 연동**을 선택하세요.
2. "Amazon Ads" 통합을 검색하고 선택하십시오.  
   **중요:** amazondsp\_int를 선택했는지 확인하고 amazon\_int(구형 통합)은 선택하지 마십시오.
3. **연동 설정**을 클릭하세요. **활성화된 연동** 설정 페이지로 이동합니다.
4. **연동** 탭에서 **파트너 활성화**를 켭니다.  
   **참고: <Anchor target="_blank" href="/marketers/ko/docs/partner-activation-deactivation">파트너와 작업하는 동안에는 토글이 켜져 있어야 합니다(</Anchor><Anchor target="_blank" href="/marketers/ko/docs/partner-activation-deactivation">활성화됨</Anchor>).**
5. 다음 섹션에 설명된 대로 관련 탭을 사용하여 구성을 완료하세요.

## Amazon Ads에서 설정을 완료하십시오.

Amazon Ads에서 다음 단계를 완료하십시오:

1. 귀하의 앱이 Amazon Ads에 제대로 등록되었는지 확인하십시오. Amazon Ads 문서에서 <Anchor target="_blank" href="https://advertising.amazon.com/help/GF97FJUFXBDM32P4">앱 등록하기</Anchor>를 참조하십시오.
2. Amazon Ads에서 캠페인을 생성할 때 관련 전환을 캠페인과 연결해야 합니다. Amazon Ads 문서에서 <Anchor target="_blank" href="https://advertising.amazon.com/help/GMQBB4PRFK8C33AE">캠페인에 전환 정의 할당하기</Anchor>를 참조하십시오.

## Amazon Ads 설정

Amazon Ads와의 연동은 클릭 및 노출 어트리뷰션을 지원합니다. 구성 기간에는 다음과 같은 탭이 포함되어 있습니다: 연동, 어트리뷰션 링크, 비용, 광고 수익 및 권한. Amazon Ads에서 사용할 수 있는 탭은 연동과 권한입니다.

> 📘 **참고**
>
> 이 통합은 Android, iOS 또는 Fire 앱을 지원합니다. iOS는 SKAN을 통해서도 지원됩니다.

<div id="integration-tab" />

<Accordion title="연동 탭">

**연동** 탭에는 아래 설명된 여러 섹션이 포함되어 있습니다.

#### 파트너 활성화

연동을 구성하려면 먼저 **파트너 활성화** 토글을 [켜야](/docs/amazon-ads-campaign-configuration#파트너-활성화) 합니다. <Anchor target="_blank" href="/marketers/ko/docs/partner-activation-deactivation#파트너-연동-활성화">파트너 연동 활성화 및 비활성화</Anchor>에 대해 더 알아보세요.

#### 일반 설정

**Amazon 광고주 ID**

이는 Amazon이 광고주를 위해 발행한 고유한 키입니다. Amazon 광고주 ID는 연동을 완료하고 Amazon Ads에 대한 어트리뷰션을 허용하기 위해 필요합니다. Amazon 광고주 ID를 찾는 방법:

* **셀프 서비스 광고주를 위한 안내:** 광고주 ID는 Amazon Ads 리포팅 콘솔의 "Amazon DSP 캠페인 관리자"의 "광고주" 탭에서 귀사의 광고주 이름 아래에 있습니다.
* **관리 서비스 광고주의 경우:** Amazon 계정 관리자에게 귀사의 광고주 ID를 문의하세요.
* 같은 앱에 대해 여러 Amazon 광고 계정을 사용하는 경우(따라서 여러 Amazon 광고주 ID가 있는 경우), 통합을 다음과 같이 설정하십시오:
  1. Amazon Ads에서 하나의 광고 계정을 선택하고 이를 **소스 계정**으로 지정하십시오. 모든 다른 광고 계정을 **대상 계정**으로 지정하십시오.
  2. Amazon 계정 팀에 연락하여 백엔드에서 설정하십시오.
  3. AppsFlyer에서 소스 계정과 연결된 Amazon 광고주 ID를 입력하십시오. 이 설정은 모든 관련 대상 계정에 통합 구성을 적용합니다.

**Amazon 앱 ID**

* **안드로이드 앱의 경우:** 패키지 이름. 예를 들어: `com.example.app`
* **Fire TV 또는 Fire 태블릿 앱의 경우:** 제품 ASIN (Amazon Standard Item Number)
* iOS 앱의 경우. "`id`" 부분이 없는 앱 스토어 앱 ID(예: `12345678`).
* <Anchor target="_blank" href="/marketers/ko/docs/set-up-multi-store-android-attribution#단일-대시보드-대-스토어-대시보드">**단일 대시보드 앱**</Anchor> (구글 플레이와 Amazon 스토어의 데이터를 동일한 앱스플라이어 앱에서 결합한 대시보드): 번들 ID로 안드로이드 패키지 이름을 입력하세요.  
  **참고: <Anchor target="_blank" href="https://advertising.amazon.com/help/GF97FJUFXBDM32P4">앱이 Amazon Ads 계정에 안드로이드 앱으로</Anchor> <Anchor target="_blank" href="https://advertising.amazon.com/help/GF97FJUFXBDM32P4">등록</Anchor>되어 있는지 확인하세요.**

#### 인스톨 어트리뷰션

인스톨(첫 번째 실행)에 대한 클릭-쓰루 및 뷰-쓰루 어트리뷰션 기간을 설정합니다. 룩백 윈도우 내 인스톨만 Amazon Ads에 측정됩니다.

**참고:** 재설치(디바이스의 초기 설정이 아닌 모든 인스톨)에 대한 어트리뷰션은 지원되지 않습니다.

1. **설치 클릭-쓰루 룩백 윈도우**를 1&#126;24시간 또는 1&#126;14일로 설정하세요.  
   **참고:** Amazon Ads에서는 어트리뷰션 기간과 일치시키고 불일치를 피하기 위해 클릭-쓰루 룩백 윈도우를 14일로 설정할 것을 권장합니다.
2. [선택 사항] **뷰-쓰루 어트리뷰션**을 활성화하고 **뷰-쓰루 어트리뷰션 기간**을 1&#126;24시간으로 설정하세요.   
   **참고:** Amazon Ads에서는 뷰-쓰루 룩백 윈도우를 14일로 설정하여 어트리뷰션 기간과 일치시키고 불일치를 방지할 것을 권장합니다.

#### 리인게이지먼트 어트리뷰션

**리인게이지먼트 어트리뷰션**을 켜고 광고를 본, 클릭한, 또는 ***참여한*** 기존 사용자의 리인게이지먼트를 측정하기 위해 다양한 어트리뷰션 기간을 설정하세요. 룩백 윈도우 내의 리인게이지먼트만 Amazon Ads에 측정될 수 있습니다.

1. [선택 사항] **리인게이지먼트 어트리뷰션**을 활성화하고 룩백 윈도우를 설정하세요.
   * **리인게이지먼트 클릭-쓰루 룩백 윈도우**를 1&#126;23시간 또는 1&#126;14일로 설정하세요.
2. [선택 사항] **리인게이지먼트 뷰-쓰루 어트리뷰션**을 활성화하고 룩백 윈도우를 설정하세요.
   * **리인게이지먼트 뷰-쓰루 룩백 윈도우**를 1&#126;23시간 또는 1&#126;14일로 설정하세요.
3. **리인게이지먼트 기간**을 1-23시간, 1-90일, 또는 생애 중에서 설정하세요.

#### 리타겟팅 대상으로 활성 유저 무시

앱을 실행한 사용자들의 리인게이지먼트 및 리-어트리뷰션을 <Anchor target="_blank" href="/marketers/ko/docs/set-retargeting-inactivity-window#비활성-기간">무시할</Anchor> 시간대를 정하세요. 이는 지정된 시간대 동안의 사용자 활동이 앱스플라이어에 기록되지 않는다는 것을 의미합니다.

> 📘 **참고사항**
>
> 지정된 시간 동안 **활동하지 않았던** 사용자들의 재인게이지먼트 및 리-어트리뷰션 전환은 **기록됩니다**.

1. **리타겟팅 대상에서 활성 사용자 무시**를 켭니다.
2. **비활성 기간**을 1&#126;30일 사이로 설정하세요.  
   **참고:** Amazon Ads에서는 차이를 방지하기 위해 비활성 기간을 7일로 설정하는 것을 권장합니다.

#### 인앱 이벤트 포스트백

Amazon Ads 이벤트와 인앱 이벤트의 매핑을 구성하고 포스트백으로 전송하세요.

**인앱 이벤트 포스트백을 구성하려면:**

1. **인앱 이벤트 포스트백**을 켭니다.
2. **이벤트 추가**를 클릭하여 목록에 SDK 또는 서버-투-서버 이벤트를 추가하세요. 다음 표는 작성해야 할 필드를 설명합니다.

| 파라미터 이름 | 설명 |
| --- | --- |
| **앱스플라이어 이벤트** | 앱스플라이어가 앱에 연동된 SDK 또는 서버 간 이벤트에서 수신한 이벤트의 이름입니다.<br />**팁**: 찾고 있는 이벤트가 없나요?<ul><li>논오가닉 설치된 디바이스에서 이벤트를 활성화하고 다시 확인하세요.</li><li>**앱스플라이어 이벤트**에 입력한 다음 **사용자 지정 생성**을 클릭합니다. 커스텀 이벤트 매핑에 대해 더 알아보세요.</li></ul> |
| **파트너 이벤트에 매핑** | 파트너 측에서 정의한 각 이벤트의 고유 이름 또는 ID입니다. 미리 정의된 파트너 이벤트 목록에서 앱스플라이어 이벤트에 해당하는 이벤트를 선택하세요.<br /><br />**참고:**<ul><li>앱 이벤트와 직접적인 연관이 없는 이벤트에는 OTHER를 선택할 수 있습니다.</li><li>재참여 측정이 활성화되면 `af_app_opened` 이벤트를 전혀 매핑하지 않거나 `OTHER`에만 매핑하는 것을 권장합니다. 이렇게 하면 이 이벤트를 보낼 때 잠재적인 중복을 방지할 수 있습니다.</li></ul> |
| **사용자용** | 이벤트 전송 옵션을 선택하세요:<ul><li>**이 파트너만**: 이 이벤트가 이 파트너에게 어트리뷰션된 경우에만 포스트백을 보냅니다.</li><li>**오가닉을 포함한 모든 미디어 소스:** 어트리뷰션된 모든 파트너 이벤트 및 오가닉 이벤트에 대해서도 포스트백을 보냅니다.</li></ul> |
| **포함** | <ul><li>**데이터 없음(기본값)**: 이벤트 값 없이 이벤트 자체만 전송합니다.</li><li>**가치와 수익**: 수익 값(이벤트에 존재하는 경우)을 **포함한** 모든 이벤트 파라미터를 발송합니다.</li><li>**수익 없는 값**: 수익 값을 **제외한** 모든 파라미터를 전송합니다.</li></ul> |

   > 📘 **참고**
   >
   > S2S를 통해 AppsFlyer에 인앱 이벤트를 보낼 경우, Amazon은 IP 주소를 포함할 것을 권장합니다. 이것은 AppsFlyer가 이벤트의 지리적 위치의 국가 코드를 Amazon에 전송할 수 있게 하여 DMA 규제 분류에 도움이 됩니다. 이는 차례로 귀하의 인앱 이벤트의 최대 최적화를 보장합니다.

3. [선택 사항] 이벤트에 대한 <Anchor target="_blank" href="/marketers/ko/docs/in-app-event-postback-configuration#조건부-인앱-이벤트-포스트백">조건을 설정</Anchor>하려면 **조건 추가altconditional-iae-postbacks-icon.pngalt아이콘을 클릭하세요.**
4. **연동 저장**을 클릭합니다.
5. [선택 사항] 연동을 저장한 후 구성 페이지에 남아 있는 동안 파트너와 더 많은 귀사의 앱을 연동할 수 있습니다.
   1. 왼쪽 상단 모서리에서 파트너 이름 아래에 있는 앱 이름을 클릭하여 앱 목록을 엽니다.
   2. 드롭다운 목록에서 다른 앱을 선택하세요.
   3. 선택한 앱에 대해 [연동 단계](#integration-tab)를 반복합니다.

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="어트리뷰션 링크 탭">

Amazon Ads에는 어트리뷰션 링크가 적용되지 않습니다. 어트리뷰션은 [연동 탭](#integration-tab)에서 구성된 클릭-쓰루 및 뷰-쓰루 룩백 윈도우를 사용하여 Amazon Ads의 인게이지먼트 데이터를 앱스플라이어의 데이터와 결합하여 수행됩니다.

</Accordion>

<div id="cost-tab" />

<Accordion title="비용, 클릭 및 노출 탭">

Amazon Ads에서는 비용, 클릭, 노출 데이터를 사용할 수 없습니다.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="광고 수익 탭">

Amazon Ads에서는 광고 수익이 지원되지 않습니다.

</Accordion>

<div id="permissions-tab" />

<Accordion title="권한 탭">

Amazon Ads가 귀사의 데이터에 액세스하고 다양한 작업을 수행할 수 있도록 허용할 권한을 선택하세요.

> 📘 **참고**
>
> * 권한 토글이 켜진 상태에서 연동이 <Anchor target="_blank" href="/marketers/ko/docs/partner-activation-deactivation">비활성화</Anchor>되면 권한이 계속 부여됩니다.
> * <Anchor target="_blank" href="/marketers/ko/docs/set-up-an-integrated-partner#permissions-tab">권한 부여</Anchor>에 대해 더 알아보기.

</Accordion>

> 📄 **참고 항목**
>
> * <Anchor target="_blank" href="/marketers/ko/docs/setting-up-amazon-fire-tv-ad-attribution">Amazon Fire TV 광고 어트리뷰션 설정</Anchor>
> * <Anchor target="_blank" href="/marketers/ko/docs/attribution-discrepancies-between-amazon-ads-and-appsflyer">앱스플라이어와 Amazon Ads 간의 어트리뷰션 불일치</Anchor>

## 디퍼드 딥링킹

* Amazon Ads에서는 딥링크가 지원되지 않습니다.
* 지연된 딥 링크: AppsFlyer의 지연된 딥 링크에 대한 두 가지 방법은 Amazon Ads에서 사용할 수 없습니다:
  * [UDL](https://dev.appsflyer.com/hc/docs/dl_work_flow#implement-unified-deep-linking-udl) (통합 딥 링크) - SRN에 대해 지원되지 않습니다.
  * [GCD](https://dev.appsflyer.com/hc/docs/dl_work_flow#recommended-implement-extended-deferred-deep-linking) (전환 데이터 가져오기) - Amazon Ads에 대해 작동하지 않으며, Amazon Ads의 귀속 데이터는 [제한되어 있습니다](/docs/amazon-ads-campaign-configuration#로데이터-제한).

## 로데이터 제한

Amazon Ads의 로데이터는 <Anchor target="_blank" href="/marketers/ko/docs/about-raw-data-identifier-restrictions#미디어-소스-제한">앱스플라이어 플랫폼에서 제한됩니다</Anchor>. 결과적으로 미디어 소스는 "제한됨"으로 보고되며 캠페인 세부 정보는 null로 처리됩니다. X Ads의 클릭 및 노출은 로데이터 리포트에 포함되지 않습니다.

## CTV-모바일 귀속

Amazon은 모바일 앱 설치를 CTV(연결된 TV) 캠페인에 귀속시킬 수 있습니다. 예를 들어 Amazon Prime Video의 캠페인과 같은 경우입니다. 이는 CTV 광고를 보는 사용자가 모바일 장치에서 Amazon 앱에 로그인되어 있을 때 발생합니다.

**참고:** 캠페인을 CTV로 명시적으로 보여주는 **보고 지표가 없습니다**. 가시성과 측정을 개선하기 위해, 가능할 경우 캠페인 이름에 `CTV`를 포함할 것을 권장합니다.

## Amazon EU 동의 정책 지원

Google은 디지털 시장법(DMA) 시행에 대비하여 <Anchor target="_blank" href="https://commission.europa.eu/strategy-and-policy/priorities-2019-2024/europe-fit-digital-age/digital-markets-act-ensuring-fair-and-open-digital-markets_en">EU 사용자 동의 정책</Anchor>을 업데이트하고 있습니다. Amazon의 앱 어트리뷰션 파트너인 AppsFlyer는 광고주들이 Amazon 광고를 최대한 활용할 수 있도록 이러한 정책 변경에 적응하고 있습니다. 업데이트된 정책은 2026년 6월 30일에 발효됩니다.

> 📘 **참고**
>
> 업데이트된 EU 동의 정책은 EU, UK 또는 스위스(CH) 사용자의 데이터(설치, 재참여 및 인앱 이벤트)에만 적용됩니다.

준수를 위해 AppsFlyer DMA 동의 정보를 동일한 방법을 사용하여 보내십시오. <Anchor target="_blank" href="/marketers/ko/docs/support-google-eu-consent-policy">Google의 DMA 동의</Anchor>.

### DMA 동의 방법

AppsFlyer는 현재 DMA 동의 공유의 두 가지 방법을 지원합니다.

| 메서드 | 세부 정보 |
| --- | --- |
| **수작업** | Amazon에서 요구하는 유일한 필드는 `ad_user_data_enabled`. |
| <Anchor target="_blank" href="https://iabeurope.eu/transparency-consent-framework/">**TCF**</Anchor> **(투명성 및 동의 프레임워크)** | 동의 관리 플랫폼(CMP)을 사용하는 경우 Amazon Ads 벤더 ID(**)를 반드시 확인하십시오.** 793)**는 허용된 공급업체 목록에 포함되어 있습니다.** |

> 📘 **참고**
>
> Amazon은 또한 다음을 통해 동의 신호를 지원합니다. <Anchor target="_blank" href="https://iabtechlab.com/gpp/">글로벌 개인정보 보호 플랫폼(GPP)</Anchor>하지만 AppsFlyer는 현재 이 방법을 지원하지 않습니다.

> 📄 **참고 항목**
>
> * <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/send-consent-for-dma-compliance">AppsFlyer SDK를 통한 DMA 동의 보내기</Anchor>
> * <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/s2s-events-api3-overview">AppsFlyer S2S를 통해 DMA 동의 보내기</Anchor> (검색 결과 `consent_data`)

## 특징 및 제약 사항

| 특징 | 비고 |
| --- | --- |
| 대행사 | 현재 Amazon Ads 통합은 에이전시에서 지원되지 않으므로 광고주 계정에서만 관리할 수 있습니다. |
| 노출, 클릭 및 비용 | 이 통합에 대한 노출, 클릭 및 비용 데이터는 아직 제공되지 않습니다. |
| 딥링크: | [딥 링크는 이 통합에 대해 지원되지 않습니다](#디퍼드-딥링킹). |
| 재설치 및 재귀속 | 재설치 및 재귀속은 이 통합에 대해 지원되지 않습니다. |
| 프리로드 어트리뷰션 | 사전 로드 측정은 이 통합의 일부로 지원되지 않지만, 레거시 amazon\_int 통합을 통해 달성할 수 있습니다. |
| 포스트백 제한 | Android에서, `advertiserIdEnabled` `advertiserIdEnabled` 필드가 "false"로 설정되어 있으면 광고주 ID를 사용할 수 있어도 설치 또는 재참여 데이터가 Amazon으로 전송되지 않습니다. |

<div data-zendesk-anchors="activate-partner=%ED%8C%8C%ED%8A%B8%EB%84%88-%ED%99%9C%EC%84%B1%ED%99%94 01H88VAJH3B5ESK12D3ATMMVZ8=%ED%8C%8C%ED%8A%B8%EB%84%88-%ED%99%9C%EC%84%B1%ED%99%94 complete-the-setup-in-amazon-ads=amazon-ads%EC%97%90%EC%84%9C-%EC%84%A4%EC%A0%95%EC%9D%84-%EC%99%84%EB%A3%8C%ED%95%98%EC%8B%AD%EC%8B%9C%EC%98%A4 h_01KMG57HR62CC9TX495SG3WSRD=amazon-ads%EC%97%90%EC%84%9C-%EC%84%A4%EC%A0%95%EC%9D%84-%EC%99%84%EB%A3%8C%ED%95%98%EC%8B%AD%EC%8B%9C%EC%98%A4 setting-up-amazon-dsp-integration=amazon-ads-%EC%84%A4%EC%A0%95 01H88VAJH3VENKYVRQY5RXN63P=amazon-ads-%EC%84%A4%EC%A0%95 01H88VAJH3BYZSXQGGZZJQ9N0C=%EC%B0%B8%EA%B3%A0 01H88VAJH3VZ4GPVE7XXMKTZ2P=integration-tab activate-partner::b746d215=%ED%8C%8C%ED%8A%B8%EB%84%88-%ED%99%9C%EC%84%B1%ED%99%94-1 01H88VAJH34GP7FK1KTJGRDPM7=%ED%8C%8C%ED%8A%B8%EB%84%88-%ED%99%9C%EC%84%B1%ED%99%94-1 general-settings=%EC%9D%BC%EB%B0%98-%EC%84%A4%EC%A0%95 01H88VAJH3F2FJK5YP3M2V7RWD=%EC%9D%BC%EB%B0%98-%EC%84%A4%EC%A0%95 install-attribution=%EC%9D%B8%EC%8A%A4%ED%86%A8-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98 01H88VAJH3SSG6ZNV7XQ46W5CX=%EC%9D%B8%EC%8A%A4%ED%86%A8-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98 reengagement-attribution=%EB%A6%AC%EC%9D%B8%EA%B2%8C%EC%9D%B4%EC%A7%80%EB%A8%BC%ED%8A%B8-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98 h_01J4RC3GR8B04RNFSD61QK45C0=%EB%A6%AC%EC%9D%B8%EA%B2%8C%EC%9D%B4%EC%A7%80%EB%A8%BC%ED%8A%B8-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98 ignore-active-users-for-retargeting=%EB%A6%AC%ED%83%80%EA%B2%9F%ED%8C%85-%EB%8C%80%EC%83%81%EC%9C%BC%EB%A1%9C-%ED%99%9C%EC%84%B1-%EC%9C%A0%EC%A0%80-%EB%AC%B4%EC%8B%9C h_01HNWSTJZPFQVQ5C8M0JA1J0T5=%EB%A6%AC%ED%83%80%EA%B2%9F%ED%8C%85-%EB%8C%80%EC%83%81%EC%9C%BC%EB%A1%9C-%ED%99%9C%EC%84%B1-%EC%9C%A0%EC%A0%80-%EB%AC%B4%EC%8B%9C h_01HMXNJVHK9C3FT8E04RE0TH99=%EC%B0%B8%EA%B3%A0%EC%82%AC%ED%95%AD inapp-event-postbacks=%EC%9D%B8%EC%95%B1-%EC%9D%B4%EB%B2%A4%ED%8A%B8-%ED%8F%AC%EC%8A%A4%ED%8A%B8%EB%B0%B1 01H88VAJH3AS37MVF75GANWX4B=%EC%9D%B8%EC%95%B1-%EC%9D%B4%EB%B2%A4%ED%8A%B8-%ED%8F%AC%EC%8A%A4%ED%8A%B8%EB%B0%B1 01JEXXHXMEC5M7N1BDSGS3ZZ51=%EC%B0%B8%EA%B3%A0-1 01H88VAJH31GZ4KAY280ZRB8MA=attribution-link-tab 01H88VAJH3RM95V449B6DF8B4D=cost-tab 01H88VAJH3A2Q0CZXQQZMW6YRC=ad-revenue-tab 01H88VAJH30TCC574W2DH7R2A2=permissions-tab 01H88VAJH3XYP81GTFBWDBXECP=%EC%B0%B8%EA%B3%A0-2 h_01HDNZ59NQEDFC3D8JYGENR1NR=%EC%B0%B8%EA%B3%A0-%ED%95%AD%EB%AA%A9 deferred-deep-linking=%EB%94%94%ED%8D%BC%EB%93%9C-%EB%94%A5%EB%A7%81%ED%82%B9 01J9G5FQGB0219RGWVW06BQPG7=%EB%94%94%ED%8D%BC%EB%93%9C-%EB%94%A5%EB%A7%81%ED%82%B9 raw-data-restrictions=%EB%A1%9C%EB%8D%B0%EC%9D%B4%ED%84%B0-%EC%A0%9C%ED%95%9C 01JBY7HD39BA9ZNR2N2TYYPBW3=%EB%A1%9C%EB%8D%B0%EC%9D%B4%ED%84%B0-%EC%A0%9C%ED%95%9C ctvtomobile-attribution=ctv-%EB%AA%A8%EB%B0%94%EC%9D%BC-%EA%B7%80%EC%86%8D h_01JZG6S5TB1888XG9560MKEBF3=ctv-%EB%AA%A8%EB%B0%94%EC%9D%BC-%EA%B7%80%EC%86%8D support-amazon-eu-consent-policy=amazon-eu-%EB%8F%99%EC%9D%98-%EC%A0%95%EC%B1%85-%EC%A7%80%EC%9B%90 h_01KP0DJ73P9FRX51SR3RS4YWVP=amazon-eu-%EB%8F%99%EC%9D%98-%EC%A0%95%EC%B1%85-%EC%A7%80%EC%9B%90 h_01KP0DJ73PDB7FM1RG0VV99707=%EC%B0%B8%EA%B3%A0-3 dma-consent-methods=dma-%EB%8F%99%EC%9D%98-%EB%B0%A9%EB%B2%95 h_01KP0DJ73PG0JMWG3WAWCKXE1S=dma-%EB%8F%99%EC%9D%98-%EB%B0%A9%EB%B2%95 h_01KP0DJ73PNPYT0TRWF089VE9R=%EC%B0%B8%EA%B3%A0-4 h_01KP0DJ73PC4ABGRPRDAR7BW5B=%EC%B0%B8%EA%B3%A0-%ED%95%AD%EB%AA%A9-1 traits-and-limitations=%ED%8A%B9%EC%A7%95-%EB%B0%8F-%EC%A0%9C%EC%95%BD-%EC%82%AC%ED%95%AD h_01J6S6HS0H0M6GQ81WGZ3XT0P9=%ED%8A%B9%EC%A7%95-%EB%B0%8F-%EC%A0%9C%EC%95%BD-%EC%82%AC%ED%95%AD" />
