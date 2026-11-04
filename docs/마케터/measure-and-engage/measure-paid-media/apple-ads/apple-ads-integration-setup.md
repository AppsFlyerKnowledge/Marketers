---
title: Apple Ads(검색 광고) 통합 설정
metadata:
  keywords:
    - cost
    - Advertisers
    - apple search ads
    - asa
    - apple ads
    - apple search advanced
    - apple search ads campaign group
    - apple keywords
    - apple searchads
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
  created_at: '2016-08-31T09:04:38Z'
  edited_at: '2026-10-14T10:40:07Z'
  id: 213747963
  locale: ko
  section: Apple Ads
  section_id: 6551310453393
  url: https://support.appsflyer.com/hc/ko/articles/213747963
---
> **한눈에 보기:** 앱스플라이어 SRN 파트너인 Apple Search Ads(ASA)는 사용자가 키워드를 통해 Apple의 앱 스토어에서 앱을 찾을 수 있도록 도와주는 광고 플랫폼입니다.

<Image alt="apple_search_ads.png" src="https://files.readme.io/cd589369bcfe75bc327d21b3a593a71d5b5b902e8b9cbc879bbebd30f28d4f79-51912992764049.png" width="217px" />

검색어에 대한 반응으로 어떤 광고가 노출될지는 앱의 연관성에 따라 결정되며, 사용자가 광고에 반응하는 정도는 광고의 연관성 신호로 간주됩니다. ASA는 이러한 사용자 반응을 기반으로 어떤 광고를 더 자주 노출할지 결정합니다.

> 📘 **참고**
>
> * 앱스플라이어는 Apple Search Ads 클릭 기반 모바일 어트리뷰션, 사용자 <Anchor target="_blank" href="/marketers/ko/docs/retargeting-attribution-guide">리타겟팅</Anchor>, 및 API를 통한 <Anchor target="_blank" href="/marketers/ko/docs/roi360-cost-aggregation-overview">비용</Anchor> 데이터(ROI360 구독 필요)를 지원합니다.
> * 2025년 3월 27일부터 앱스플라이어는 Apple Search Ads 노출 기반 모바일 어트리뷰션도 지원합니다.

## ASA 연동 설정

<Accordion title="시작하기">

**선행 조건**

* 최신 버전의 앱스플라이어 iOS SDK

**앱스플라이어에서 Apple Search Ads 설정 방법:**

설정은 **활성 연동** 페이지에서 진행할 수 있지만, 새로운 파트너를 찾으려면 먼저 <Anchor target="_blank" href="/marketers/ko/docs/partner-integrations">파트너 마켓플레이스</Anchor>로 이동해야 합니다. 아래 설명된 대로 관련 탭을 사용하여 설정을 완료하십시오.

<div id="note-1" />

> 📘 **참고**
>
> 연동을 설정하기 전에 <Anchor target="_blank" href="/marketers/ko/docs/partner-integrations#contact-details">파트너에게 연락하여</Anchor> 함께 계정을 개설해야 합니다.

</Accordion>

<Accordion title="연동 탭">

Apple Search Ads는 SRN으로 앱스플라이어와 API를 통해 연동되기 때문에, 별도의 포스트백 설정이 필요 없습니다. 귀하의 어트리뷰션 목표에 따라 다음 섹션을 완료하십시오.

<table><thead><tr><th>섹션 </th><th>세부 정보</th></tr></thead><tbody><tr><td>연동 활성화</td><td><p><strong>연동 활성화 또는 연동 편집 방법:</strong></p><ol><li> <strong>활성화 방법:</strong> 앱스플라이어에서, 측면 메뉴에서 <strong>협업</strong> &gt; <strong>파트너 마켓플레이스</strong>를 선택하세요.<br/><strong>편집 방법</strong>: 앱스플라이어의 사이드 메뉴에서 <strong>협업</strong> &gt; <strong>활성화된 연동</strong>을 선택하세요.</li><li>파트너를 검색하고 선택합니다.</li><li> <strong>연동 설정</strong>을 클릭합니다. 연동 설정 페이지로 이동합니다.</li><li> <strong>연동</strong> 탭에서 연동할 앱을 선택하고 <strong>파트너 활성화</strong>를 켭니다.<br/><strong>참고:</strong> 파트너와 협력하는 동안 토글은 반드시 켜져<a href="./partner-activation-deactivation" target="_blank">(활성화)</a> 있어야 합니다.</li><li>아래 설명된 대로 관련 탭을 사용하여 설정을 완료하십시오.</li></ol></td></tr><tr><td>인스톨 클릭-쓰루 어트리뷰션</td><td><ol><li><p><strong>설치 클릭-쓰루 룩백 윈도우 설정</strong><br/>광고 클릭에서 설치까지 최대 시간을 설정하세요. 이렇게 설정하면 앱스플라이어가 룩백 윈도우 내에 발생한 인스톨(최초 실행)을 ASA의 성과로 어트리뷰션할 수 있게 됩니다.</p><ul><li> <strong>범위:</strong> 1&#126;30일</li><li> <strong>기본값:</strong> 30일</li></ul><p>자세한 내용은 <a href="./set-up-lookback-windows" target="_blank">룩백 윈도우 설명</a>을 참조하세요.</p></li></ol><ol><li> <strong>사전 등록(사전 주문) 캠페인 측정</strong><br/>iOS 앱의 사전 등록 캠페인을 진행하는 경우, 사전 예약 캠페인의 룩백 윈도우를 설정하세요. <br/>이 슬라이더는 사전 등록 캠페인에 설치를 어트리뷰션하는 룩백 윈도우를 결정합니다.<br/>사전 등록 룩백 윈도우를 사용하면 사전 등록(사전 주문)된 앱이 출시될 때 발생하는 설치를 원래의 광고 참여와 연결하여 기여도를 측정할 수 있습니다. <ul><li> <strong>범위: 1–90일</strong> </li><li> <strong>기본값:</strong>  90일</li></ul></li></ol></td></tr><tr><td>인스톨 뷰-쓰루 어트리뷰션</td><td><ol><li><p><span><strong>뷰-쓰루 룩백 윈도우 설치 설정</strong></span><br/>광고 조회부터 설치까지의 최대 시간을 설정하세요. 앱스플라이어는 이 윈도우 기간 내에 발생하는 설치(최초 실행)를 ASA의 성과로 어트리뷰션합니다. <strong>참고:</strong> 인스톨 뷰-쓰루 룩백 윈도우 슬라이더는 시간 단위만 지원합니다 (최대: 24시간, 기본값: 24시간). </p><ul><li> <strong>범위:</strong> 1–24시간</li><li> <strong>기본값:</strong> 24시간</li></ul><p>자세한 내용은 <a href="./set-up-lookback-windows" target="_blank">룩백 윈도우 설명</a>을 참조하세요.</p></li><li> <strong>사전 등록(사전 주문) 캠페인 측정</strong><br/>iOS 앱의 사전 등록 캠페인을 진행하는 경우, 사전 예약 캠페인의 룩백 윈도우를 설정하세요.<br/>이 슬라이더는 사전 등록 캠페인에 설치를 어트리뷰션하는 룩백 윈도우를 결정합니다.<br/>사전 예약 룩백 윈도우를 사용하면 사전 등록(사전 주문)된 앱이 출시될 때 발생하는 설치를 원래의 광고 참여와 연결하여 기여도를 측정할 수 있습니다.<ul><li> <strong>범위:</strong> 1&#126;61일</li><li> <strong>기본값:</strong> 61일</li></ul></li></ol></td></tr><tr><td rowspan="2">재설치 </td><td><p><strong>리인스톨 어트리뷰션</strong></p><p><strong>리인스톨 어트리뷰션</strong>이 설정된 경우 앱스플라이어는 ASA에 리인스톨을 어트리뷰트할 수 있습니다.</p><p>리인스톨 어트리뷰션 룩백 윈도우 설정은 인스톨 어트리뷰션 설정을 따릅니다.</p><p>사용자가 최초 인스톨 후 <a href="./set-up-re-attribution-window" target="_blank">리어트리뷰션 기간 내</a>에 앱을 다시 인스톨하면, 해당 인스톨은 ASA에서 리인스톨로 간주되어 어트리뷰션됩니다.</p><p>리인스톨은 개요 대시보드의 리타겟팅 뷰에서 볼 수 있습니다.</p><p><strong>Store reinstall</strong> 로데이터 필드가 true로 설정됩니다. </p><p>현재 ASA 리타겟팅은 리인게이지먼트를 지원하지 않습니다.</p></td></tr><tr><td><p><strong>앱 미사용 기간</strong></p><p>리타겟팅 캠페인의 영향 범위를 조정하려면, 사용자의 <a href="./set-retargeting-inactivity-window" target="_blank">비활성화 기준 기간</a>(일 단위)을 설정하세요. </p></td></tr><tr><td>포스트백</td><td>현재 Apple Ads 연동은 포스트백을 지원하지 않습니다.  </td></tr></tbody></table>

</Accordion>

<Accordion title="비용 탭">

비용 연동은 다음의 집약형 데이터를 제공합니다.

* 캠페인, 광고 세트, 지역/국가, 키워드에 대한 비용 데이터 지원되는 디멘션, 지표 및 기능에 대한 자세한 내용은 <Anchor target="_blank" href="/marketers/ko/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api">애드 네트워크 비용 연동 표</Anchor>를 참조하세요.  
  **참고:** 비용 데이터를 확인하려면 ROI360을 구독해야 합니다.
* 클릭 수, 노출 수에 대한 데이터 및 보강된 데이터(키워드, 캠페인 이름, 광고 세트)

<div id="note-3" />

<div id="agency-actions" />

<div id="advertiser-actions" />

<div id="configuration-steps-checklist" />

<div id="configuring-agencies-and-marketing-partners" />

<div id="agency-vs-marketing-partner" />

<div id="set-up-agencies-and-apple-ads-marketing-partners" />

<div id="note-2" />

> 📘 **참고**
>
> * 여러 ASA 계정 사용이 지원됩니다. 즉, 동일한 앱에 대해 서로 다른 ASA 계정을 사용해 캠페인을 운영하더라도, 앱스플라이어는 모든 계정으로부터 해당 데이터를 수신할 수 있습니다.
> * “캠페인 그룹”에 대한 비용 데이터는 ASA 리포트 API에서 지원되지 않으므로 “캠페인 그룹” 데이터는 앱스플라이어에서 확인할 수 없습니다.
> * Apple로 로그인하려면 ASA **Campaign Group Manage** 권한(Account Read Only 또는 Account Read and Write 중 하나)이 필요합니다.
> * Apple로 로그인할 때 ASA 캠페인 그룹의 인증은 누적되지 않습니다. 즉, 새 앱을 연동할 때 이전 앱에 대해 선택한 캠페인 그룹에 대한 승인은 다시 선택하지 않는 한 취소됩니다.
> * Apple로 로그인할 때 <Anchor target="_blank" href="https://support.apple.com/en-il/guide/apple-business-manager/axmb19317543/web">외부 계정 로그인</Anchor>을 사용할 수 없습니다.

**비용, 클릭 수, 노출 수, 보강된 데이터를 활성화하는 방법:**

* <Anchor target="_blank" href="/marketers/ko/docs/set-up-roi360-cost-api-to-measure-cost-data#비용-api-활성화">다음 연동 지침</Anchor>을 따르십시오.

<Anchor target="_blank" href="/marketers/ko/docs/set-up-roi360-cost-api-to-measure-cost-data#cost-api-status">비용 API 상태</Anchor> 와 앱스플라이어가 마지막으로 일치하는 비용 데이터를 가져온 시간은 비용(및 광고 수익) 연동 상태 대시보드 또는 각 애드 네트워크별 대시보드에서 확인할 수 있습니다.

</Accordion>

<Accordion title="권한 탭">

<Anchor target="_blank" href="/marketers/ko/docs/set-up-an-integrated-partner#permissions-tab">애드 네트워크 및 에이전시 권한 설정.</Anchor>

</Accordion>

## 에이전시 및 ASA 마케팅 파트너를 설정합니다.

<Accordion title="원칙">

**Apple Search Ads: 마케팅 파트너 vs 에이전시**

광고주와 대행사는 ASA에서 캠페인을 보고하고 최적화하기 위해 ASA 마케팅 파트너와 협업을 선택할 수 있습니다.

대행사와 마케팅 파트너 간의 차이점은 다음 표에 나열되어 있습니다.

#### 에이전시 vs 마케팅 파트너

|  | 에이전시 | 마케팅 파트너 |
| --- | --- | --- |
| 앱스플라이어가 포스트백 전송 | 아니요 | 예 |
| 기술 | 캠페인을 대신 운영합니다. | 캠페인을 최적화하기 위한 부가 기술 솔루션을 가지고 있습니다. |

#### 에이전시 및 마케팅 파트너 구성

다음 체크리스트를 사용하여 설정 절차에서 모든 작업을 완료했는지 확인하세요. 파트너 유형별 상세 안내는 다음 섹션에 포함되어 있습니다.

#### 구성 단계 체크리스트

| 구성 당사자 | 에이전시와의 연동 | 마케팅 파트너와의 연동 |
| --- | --- | --- |
| 광고주 | <ol><li>앱스플라이어 내 ASA 연동 탭에서 **파트너 활성화**를 켜세요.</li><li>대행사 권한 탭에서 대행사를 선택하고 **대행사 권한**을 사용 설정합니다.</li></ol> | <ol><li>ASA 연동에서 **파트너 활성화**를 사용 설정합니다.</li><li>ASA 대시보드에서 마케팅 파트너의 **캠페인 그룹 ID**를 가져옵니다.</li><li>마케팅 파트너 연동 탭에서:<ol><li>**파트너 활성화**를 설정합니다.</li><li>캠페인 그룹을 설정합니다.</li><li>인앱 이벤트 포스트백을 구성합니다.</li></ol></li></ol> |
| 에이전시 | ASA 연동 탭에서 **Apple Search Ads 캠페인 그룹**을 설정하세요. | <ol><li>ASA 연동에서 **파트너 활성화**를 사용 설정합니다.</li><li>ASA 대시보드에서 마케팅 파트너의 **캠페인 그룹 ID**를 가져옵니다.</li><li>마케팅 파트너 연동 탭에서:<ol><li>**파트너 활성화**를 설정합니다.</li><li>캠페인 그룹을 설정합니다.</li><li>인앱 이벤트 포스트백을 구성합니다.</li></ol></li></ol> |

</Accordion>

<Accordion title="마케팅 파트너 설정">

**마케팅 파트너 설정 방법:**

1. 필요할 경우, **Apple Search Ads 연동**을 활성화합니다.
   1. 앱스플라이어에서 **Configuration**> **Active integration partners** > **Apple Search Ads**로 이동하세요.
   2. **파트너 활성화**를 설정합니다.
   3. **저장**을 클릭하세요.
2. **Apple Search Ads 대시보드에서** 마케팅 파트너와 관련된 Apple Search Ads Campaign Group ID 파라미터를 가져옵니다. ID를 찾는 데 도움이 되도록 다음 스크린샷을 가이드로 활용하세요.  ![ASACGroupID.png](https://files.readme.io/722ab215c9a096628b42caefc6838dfe790d726524839c588d9e01c061620711-21589950935057.png)
3. **앱스플라이어에서 ASA 마케팅 파트너를 다음과 같이 설정합니다.**
   1. 앱스플라이어의 사이드 메뉴에서 **Collaboration** > **Active integrations**를 선택하세요.
   2. **Apple Search Ads** ***마케팅 파트너***를 검색합니다.  
      **마케팅 파트너 목록이 표시됩니다.**
   3. 마케팅 파트너를 선택합니다.
   4. **파트너 활성화**를 설정합니다.
   5. 이전 단계에서 가져온 파트너의 **Apple Search Ads Campaign Group ID**를 입력하세요. 숫자만 입력하세요 .
   6. **저장**을 클릭하세요.
4. [선택 사항] 인앱 이벤트 포스트백을 다음과 같이 구성합니다.
   1. **인앱 이벤트 포스트백**을 켭니다.
   2. 리스트에 SDK 이벤트를 추가하려면 **Add event**를 클릭하세요.
   3. 다음 파라미터를 채워 넣으세요.
      1. **SDK 이벤트 이름**: 앱에 연동된 SDK 또는 서버 간 이벤트를 통해 앱스플라이어가 수신한 이벤트의 이름입니다. **팁:** 목록에 원하는 이벤트가 표시되지 않는 경우 논오가닉 설치 기기에서 이벤트를 발생시킨 후 다시 점검하세요.
      2. **수익 전송:** 다음 중 하나를 선택하세요. 값 및 수익 없음, 값은 있으나 수익 없음, 값 및 수익이 있음.
5. **연동 저장을 클릭합니다**.

</Accordion>

<Accordion title="에이전시 설정">

광고주는 대행사가 자신을 대행하여 Apple Search Ads를 통해 캠페인을 집행할 수 있도록 권한을 부여합니다. 광고주와 대행사는 모두 이 섹션에 명시된 대로 앱스플라이어에서 설정 작업을 수행해야 합니다.

**선행 조건**

앱스플라이어에서 대행사를 설정하기 전에, 대행사와 광고주 모두 ASA 플랫폼에서 다음과 같은 단계를 진행해야 합니다.

* **에이전시:**
  1. 에이전시 계정 내에 별도의 캠페인 그룹을 만듭니다.
  2. 광고주의 App Store Connect 계정을 연결할 수 있도록 광고주를 Campaign Group Manager로 초대하거나 Link Accounts 역할을 통해 초대하세요.
* **광고주:** 계정 연결 초대를 수신한 후, 광고주는 해당 캠페인 그룹을 자신의 App Store Connect 계정에 연결해야 합니다.클라이언트의 <Anchor target="_blank" href="https://searchads.apple.com/help/get-started/0012-link-app-store-connect-accounts">App Store Connect 계정을 대행사 계정에 연결하는 방법</Anchor>에 대한 자세한 내용은 ASA 문서를 참조하세요.

**Apple Search Ads 캠페인 그룹**

* 그룹 이름에 특수 문자 및 공백을 사용하지 마십시오.
* Apple로 로그인할 때, ASA 캠페인의 권한 부여 그룹 누적되지 않습니다. 즉, 새 앱을 연동할 때 이전 앱에 대해 선택한 캠페인 그룹에 대한 승인은 다시 선택하지 않는 한 취소됩니다.  광고주와 연결할 앱과 관련된 캠페인 그룹 각각을 선택한 뒤, **Limited Access(제한된 접근 권한)** 를 선택해야 합니다.

#### **광고주가 취해야 할 조치**

**선행 조건**:

<Anchor target="_blank" href="/marketers/ko/docs/set-up-an-integrated-partner#에이전시-권한">에이전시에 권한을 부여합니다</Anchor>.

**Apple Search Ads의 어트리뷰선을 활성화하기 위해 광고주는 다음을 수행합니다.**

1. 앱스플라이어의 사이드 메뉴에서 **Collaboration(협업)** > **Active integrations(활성 연동)** 를 선택하세요.
2. **Apple Search Ads**를 선택합니다.
3. **통합** 탭으로 이동하여 **파트너 활성화**를 켭니다.
4. [선택 사항] 리어트리뷰션 윈도우 기간 내에 앱을 재설치한 사용자의 기여도를 측정하려면 토글을 켜십시오. **재설치 어트리뷰션**
5. **저장**을 클릭하세요.

#### **에이전시가 취해야 할 조치**

1. **Apple Search Ads 대시보드에서** 캠페인 그룹 ID를 확인하세요. 해당 ID의 위치를 찾으려면 다음 스크린샷을 가이드로 활용하세요. 숫자만 가져옵니다. ![ASACGroupID.png](https://files.readme.io/722ab215c9a096628b42caefc6838dfe790d726524839c588d9e01c061620711-21589950935057.png)
2. 앱스플라이어에서 앱을 선택합니다.
3. 측면 메뉴에서 **Collaboration(협업)** > **Active integrations(활성 연동)** 을 선택하세요.
4. **Apple Search Ads**를 선택합니다.
5. **Apple Search Ads 캠페인 ID** 파라미터를 입력합니다. 주의! 숫자만 입력합니다.
6. **저장**을 클릭하세요.

> 📘 **참고**
>
> 대행사가 Apple Search Ads 마케팅 파트너와 협업할 때는 Apple Search Ads 설정 페이지와 마케팅 파트너 설정 페이지 모두에 동일한 캠페인 그룹 ID를 구성해야 합니다.

<div id="before-september-1-2026" />

<div id="after-september-1-2026" />

<div id="additional-information" />

<div id="note-4" />

<div id="cost-clicks-and-impressions-data" />

### 비용, 클릭수 및 노출 데이터

비용 API를 활성화하면, 앱스플라이어는 API를 통해 ASA로부터 비용,클릭 수 및 노출 데이터를 수신합니다. 지원되는 디멘션, 메트릭 및 기능에 대한 전체 상세 내용은 <Anchor target="_blank" href="/marketers/ko/docs/roi360-cost-aggregation-overview#ad-networks-supporting-cost-api">광고 네트워크 비용 연동 테이블</Anchor>을 참조하십시오. **참고**: 비용 데이터를 확인하려면 ROI360을 구독해야 합니다. ROI360이 없으면 클릭 수와 노출 데이터만 수신됩니다.

**비용 API를 활성화 하려면**:

* <Anchor target="_blank" href="/marketers/ko/docs/set-up-roi360-cost-api-to-measure-cost-data#비용-api-활성화">이 연동 지침</Anchor>을 따르세요. **권한 선택** 단계에서 Apple Search Ads 계정에 로그인하라는 메시지가 표시되면 다음 중 하나를 선택해야 합니다.
  * **계정 읽기 및 쓰기**
  * **계정 읽기 전용**  
     **참고**: Limited Access(제한된 접근)와 특정 캠페인 그룹을 선택하는 경우 데이터 오류가 발생할 수 있습니다.

<Anchor target="_blank" href="/marketers/ko/docs/set-up-roi360-cost-api-to-measure-cost-data#cost-api-status">비용 API 상태</Anchor>, 그리고 앱스플라이어가 매칭되는 비용 데이터를 최근에 언제 가져왔는지는 비용(및 광고 수익) 연동 상태 대시보드나 개별 광고 네트워크 대시보드를 통해 조회 가능합니다.

> 📘 **참고**
>
> SKAN 포스트백에는 캠페인 수준의 데이터가 포함되지 않기 때문에, SKAN 대시보드 또는 SKAN Pull API에서는 Apple Search Ads 비용 데이터를 확인할 수 없습니다. 그러나 SSOT 보고서에서는 비용 데이터가 제공되며, 이는 SKAN 설치 데이터와 기존 Apple Search Ads 연동 방식으로 가져온 비용 정보를 결합한 것입니다.

</Accordion>

<Accordion title="에이전시 및 마케팅 파트너를 비활성화합니다.">

**에이전시 또는 마케팅 파트너가 생성한 Apple Search Ads 인스톨의 어트리뷰션 기록을 중지하는 방법:**

1. 앱스플라이어의 측면 메뉴에서 **Collaboration(협업)** > **Active integrations(활성 연동)** 를 선택하십시오.
2. 해당하는 에이전시 또는 마케팅 파트너를 선택합니다.
3. Apple Search Ads Campaign Group ID 필드의 내용을 삭제하세요.
4. **연동 저장**을 클릭합니다.

</Accordion>

## 추가 정보

<Accordion title="ASA 어트리뷰션">

Apple Search Ads는 SKAdNetwork를 사용하지 않으며, ATT 동의 여부와 관계없이 사용자를 정확하게 어트리뷰션합니다. 다시 말하면 ASA로 어트리뷰션된 사용자에 대해서는 <Anchor target="_blank" href="/marketers/ko/docs/appsflyer-attribution-model">LTV 어트리뷰션 모델</Anchor>이 제공하는 모든 기능과 측정 지표를 그대로 활용할 수 있습니다.

ASA 어트리뷰션은 IDFA에 의존하지 않으며, 디바이스에서 전달되는 토큰을 기반으로 한 확정적 어트리뷰션(deterministic attribution) 방식으로 처리됩니다. 다만, ATT 동의 여부에 따라 어트리뷰션 방식에 일부 차이가 있을 수 있습니다.

| **ATT 동의** | **클릭/노출 시간 사용 가능** | **클릭/노출 룩백 윈도우** | **비고** |
| --- | --- | --- | --- |
| 예 | 예 | 광고주가 설정 | 사용된 앱스플라이어 라스트 클릭 어트리뷰션 규칙 |
| 아니요 | 아니요 | 클릭 수: 30일  <br />(ASA에 의해 설정됨),  <br />노출: 24시간 | 클릭 또는 노출 시간이 제공되지 않습니다. 확정적인 후보에게 우선순위가 주어집니다. |

</Accordion>

<Accordion title="불일치">

앱스플라이어와 Apple Search Ads는 서로 다른 어트리뷰션 로직을 사용하므로, 두 플랫폼 간 차이가 있을 수 있습니다. SRN인 <Anchor target="_blank" href="/marketers/ko/docs/self-reporting-networks-srns#어트리뷰션">Apple Search Ads</Anchor>는 API를 통해 신규 인스톨을 리포트합니다.

**API를 통해 앱스플라이어와 연동된 Apple Search Ads 데이터 리포팅**

* 캠페인은 지역(Geo)에 따라 집계됩니다.
* 다음은 리포트되지 않습니다: 특정 캠페인에서 노출 수가 100회 미만인 노출 수, 탭 수, 또는 지역의 비용 데이터는 제공되지 않을 수 있습니다.
* 앱스플라이어에서 지역(Geo)을 기준으로 그룹화할 경우, 데이터가 부족한 지역들은 표시되지 않으며, 해당 누락된 데이터의 총합은 N/A로 나타납니다.

<div id="retargeting-related-discrepancies" />

### 리타겟팅 관련 불일치

앱스플라이어의 리타겟팅 어트리뷰션 메커니즘을 통해, 광고주는 유저 확보 캠페인뿐만 아니라 리타겟팅 캠페인도 측정하고 분석할 수 있습니다.

다음에 나오는 도표들은 Apple Search Ads에서 실행 중인 리타겟팅 캠페인과 (리타겟팅 설정 여부와 관계없이) 불일치가 발생하게 되는 원인들을 보여줍니다.

**리타겟팅 설정**

[![ASA R Enabled2.jpg](https://files.readme.io/0d26cc4844aa97adb793a266cb2a51961a1345e71a24eec305fcc16539d86027-31197524086801.jpg)](https://files.readme.io/0d26cc4844aa97adb793a266cb2a51961a1345e71a24eec305fcc16539d86027-31197524086801.jpg)

**리타겟팅 해제**

[![ASA_R_Disabled.png](https://files.readme.io/425a0e1e802482a00230d7ceaebdcaa7f74523fb6feb75d60168f94b56886201-31197514618001.png)](https://files.readme.io/425a0e1e802482a00230d7ceaebdcaa7f74523fb6feb75d60168f94b56886201-31197514618001.png)

<div id="20210215" />

<div id="20210307" />

<div id="20210407" />

<div id="20220216" />

<div id="20230207" />

<div id="20260901" />

<div id="target-redownloaders" />

<div id="find-the-best-performing-creative-set" />

<div id="pivot-example" />

<div id="cohort-example" />

<div id="h_01M0YZYCC5S0E3HA296KAA0SDZ" />

<div id="analyze-keyword-cost" />

<div id="compare-the-quality-of-users-based-on-keyword-data" />

<div id="get-keyword-data" />

<div id="missing-conversion-payload-for-gender-and-age-targeted-users" />

<div id="geo-locations" />

<div id="cost-data" />

<div id="conversion-data" />

<div id="time-zone" />

<div id="install-time" />

<div id="winning-click" />

<div id="preregistration-click-and-impression-lookback-window-discrepancy" />

<div id="impression-lookback-window" />

<div id="click-lookback-window" />

<div id="reinstall-a-user-after-installing-the-app-deletes-it-clicks-on-a-search-ad-then-installs-the-app-again" />

<div id="counting-users" />

<div id="limit-ad-tracking-lat-and-att" />

<div id="differences-related-to-appsflyer-sdk-versions" />

<div id="see-also" />

<div id="before-september-1-2026-1" />

<div id="after-september-1-2026-1" />

<div id="additional-reasons-for-discrepancies" />

### 불일치의 추가적인 원인

다음 표에는 불일치가 발생하는 주요 이유가 제시되어 있습니다.

| 불일치 | Apple Search Ads | 앱스플라이어 |
| --- | --- | --- |
| 앱스플라이어 SDK 버전로 인한 차이 | 앱스플라이어 SDK 버전과 관계없이 전환 수를 집계 | AdsServices의 경우, 정확한 어트리뷰션을 위해 SDK V6.1.3 이상이 필요합니다. |
| 광고 트래킹 제한(LAT) 및 ATT. | 항상 전환 집계<br /><br />캠페인이 연령 및 성별에 의해 제한되는 경우 LAT 사용자는 경우 캠페인에서 제외됩니다.<br /><br />18세 이하의 Apple 사용자는 항상 LAT의 제한을 받습니다. | LAT 전환은 오가닉으로 어트리뷰트됩니다.<br /><br />AdServices가 구현되고 iOS14.3 이상이 설치되어 있는 경우에는 비동의 사용자가 올바르게 어트리뷰선됩니다. |
| 유저 집계 방식 | 다운로드 수에 따라 사용자 수 집계 | 앱의 첫 실행에 따라 사용자 수 집계 |
| 재설치: 앱을 설치한 후 삭제하고, Search Ad를 클릭한 후 앱을 다시 인스톨한 사용자 | 전환(인스톨)으로 집계 | <ul><li>IDFA 사용: 앱스플라이어는 재설치를 식별하며, UA(유저 획득) 목적의 인스톨로는 집계하지 않습니다. 팁! 리타겟팅을 활성화하면 해당 재설치는 리타겟팅 인스톨(즉, 리어트리뷰션)로 기록됩니다.</li><li>IDFA 미사용: 앱스플라이어는 IDFV를 기반으로 해당 인스톨이 재설치인지 신규 설치인지를 판단할 수 있습니다.<ol><li>디바이스에 동일 벤더의 다른 앱이 하나 이상 설치되어 있는 경우, 앱스플라이어는 ASA를 리어트리뷰션으로 어트리뷰트합니다.</li><li>반대로, 다른 앱이 존재하지 않는 경우에는 신규 설치로 어트리뷰션합니다.</li></ol></li></ul> |
| 클릭 룩백 윈도우 | 30일 기간으로 고정 | 클릭 시간이 없는 AdServices에서 보낸 응답의 경우 클릭 룩백 기간이 30일로 고정됩니다. |
| 노출 룩백 윈도우 | 24시간 기간으로 고정 | 노출 시간이 포함되어 있지 않은 AdServices의 응답에 대해서는, 노출 룩백 윈도우가 24시간으로 고정됩니다. |
| 사전 등록 클릭 및 노출 룩백 윈도우의 차이 |  | 클릭 또는 노출 시간이 포함되지 않은 AdServices의 응답에 대해, 클릭 또는 노출 룩백 윈도우는 고정됩니다.<ul><li>**클릭**: 90일</li><li>**노출**: 61일</li></ul> |
| 기여 클릭 | 사용자가 광고에 반응하고 앱을 다운로드한 경우, 항상 해당 네트워크가 자사 성과로 어트리뷰션합니다 | 여러 광고 네트워크에 대한 가시성을 보유하고 있으며, 라스트 클릭 방식에 따라 어트리뷰션을 수행합니다. |
| 설치 시간 | 앱 다운로드 시간 | 첫 번째 앱 실행 |
| 시간대 | 앱 스토어 현지 시간대 | UTC 시간대 또는 앱스플라이어 설정에 따름 |
| 전환 데이터 | Search Ads로 인한 인스톨 정보가 앱스플라이어에 반영되기까지 5초 이상 걸릴 수 있습니다. | 5초 이내에 어트리뷰션이 완료되며, 이 시점에 전환 데이터 API가 응답합니다. 데이터를 받지 못한 경우, 해당 응답은 오가닉으로 간주됩니다. |
| 비용 데이터 | 모든 키워드에 대한 비용을 리포트 | 대시보드 또는 코호트 API에서 대문자가 포함된 키워드에 대해서는 비용 데이터가 보고되지 않습니다. |
| 지역 위치 | Apple Search Ads는 광고주가 국가와 지역에 따라 유저를 타겟팅하는 것을 허용합니다. Apple Search Ads가 지원하는 [**국가**](https://searchads.Apple.com/storefronts/) 수는 제한적입니다. | 앱스플라이어는 사용자의 IP 주소를 기반으로 정확한 지리적 위치를 인식하므로, Apple Search Ads에서는 제공되지 않는 지역 데이터도 보고할 수 있습니다.<br /><br />팁! 앱 스토어가 속한 실제 국가에서 설치한 사용자의 경우, 앱스플라이어와 Apple Search Ads에서 동일한 지역 데이터가 표시됩니다. |

</Accordion>

<Accordion title="팁">

Apple Search Ads를 활용하면 고가치의 마케팅 데이터를 수집할 수 있으며, 이는 iOS 앱의 모든 미디어 소스를 통한 유저 유입 활동에 긍정적인 영향을 줄 수 있습니다.

다음은 Apple Search Ads를 활용한 효과를 극대화하기 위한 팁입니다.

| 팁 | 세부 정보 |
| --- | --- |
| 키워드 데이터 가져오기 | Apple Search Ads는 앱스플라이어와 키워드 데이터를 공유합니다. 로데이터 및 피봇, 리텐션 및 코호트와 같은 분석 도구에서 키워드 데이터를 볼 수 있습니다.<br /><br />**참고:**<ul><li>키워드 데이터 가져오기가 8-12시간 동안 지연될 수 있으며 경우에 따라 키워드 용어 없이 키워드 ID만 포함할 수 있습니다.</li><li>키워드 데이터를 가져오려면 비용 토글을 켜야 합니다. 키워드 데이터는 [비용 연동](/docs/apple-ads-integration-setup#cost-tab)에 포함되어 제공되며, ROI360 구독 없이도 확인할 수 있습니다.</li></ul>키워드 데이터가 앱스플라이어에서 누락된 경우, 다음과 같은 상황이 원인일 수 있습니다.<ul><li>**패키지 유형:** 키워드 데이터는 Apple Search Ads의 [Advanced](https://searchads.Apple.com/advanced/) 패키지를 사용하는 광고주에게 제공됩니다.</li><li>**캠페인 유형** Apple Search Ads에서 다양한 캠페인 키워드 매칭 유형을 설정할 수 있습니다. 매칭 유형에 따라 Apple Search Ads는 키워드를 다음과 같이 공유합니다.<ul><li>**정확한 일치(Exact match)**: 사용자가 검색한 정확한 키워드</li><li>**확장 일치(Broad match)**: Apple이 검색을 수행하는 데 사용한 키워드. 유저의 실제 검색 용어와 유사합니다.</li><li>**검색 일치(Search match)**: Apple은 이 키워드를 광고주와 공유하지 **않습니다**.</li></ul></li></ul>완전한 키워드 데이터를 수신하려면, **정확한 일치(exact match) 또는 확장 일치(broad match) 검색 캠페인만 사용**하십시오. |
| 키워드 데이터에 기반한 유저 품질 비교하기 | 모든 키워드가 동일한 가치를 가지는 것은 아닙니다. 즉, 비용은 같더라도 각 키워드로 유입되는 사용자의 품질은 다를 수 있습니다. 리텐션 또는 <Anchor target="_blank" href="/marketers/ko/docs/pivot-table-user-metrics">피봇</Anchor> 리포트를 이용하여 ROI를 극대화하는 키워드를 파악하십시오. |
| 키워드 비용 분석 | 플랫폼에는 ASA 키워드 캠페인이 [정확한 일치(Exact Match) 또는 \*\*확장 일치(Broad Match)](/docs/apple-ads-integration-setup#get-keyword-data)로 설정된 경우, 키워드 비용의 집계 데이터가 포함되어 있습니다. 키워드 비용 데이터는 아래와 같은 특징을 가지고 있습니다.<ul><li>과거 데이터는 2019년 10월 13일부터 확인할 수 있습니다.</li><li>데이터 기준:<ul><li>날짜</li><li>캠페인</li><li>광고세트</li></ul></li><li>분석 툴:<ul><li><Anchor target="_blank" href="/marketers/ko/docs/cohort-and-retention-dashboard">코호트</Anchor></li><li><Anchor target="_blank" href="/marketers/ko/docs/pivot-table-user-metrics">피봇</Anchor></li><li><Anchor target="_blank" href="/marketers/ko/docs/master-api-user-acquisition-metrics-via-api">마스터 API</Anchor></li></ul></li></ul>**제한 사항**<ul><li>비용 데이터 쿼리를 필터하고 그룹화하려면 위에 표시된 데이터 기준만 사용하십시오. 예를 들어, 지역별로 필터하거나 그룹화 하지 마십시오.</li></ul>**코호트 예시**<br />다음 예시는 비용 및 ROI 정보를 보기 위해 코호트를 설정하는 방법을 보여줍니다.<br /><br />**코호트 설정**<br /><br />[<Image alt="CohortRequest.png" src="https://files.readme.io/73004ab25cfff029786ec4601e22a0ac4b02a146141787b51bda1a02d5412330-31197524095377.png" width="327px" />](https://files.readme.io/73004ab25cfff029786ec4601e22a0ac4b02a146141787b51bda1a02d5412330-31197524095377.png)<br /><br />**코호트 결과 표**<br /><br />다음 표에 총 비용 및 코호트 ROI가 표시됩니다.<br /><br />[<Image alt="CohortTable.png" src="https://files.readme.io/ebceedb82207bdbc7f58daafc0557630ac35a73a11b14d207a7283b93294073d-31197514633233.png" width="429px" />](https://files.readme.io/ebceedb82207bdbc7f58daafc0557630ac35a73a11b14d207a7283b93294073d-31197514633233.png)<br /><br />**피봇 예시**<br /><br />**피봇 설정**<br /><br />[<Image alt="Pivot_define.png" src="https://files.readme.io/29ad177a5ef681f8358968092005d8ba871f3dd06661a8dea6d186318c08a476-31197524107153.png" width="413px" />](https://files.readme.io/29ad177a5ef681f8358968092005d8ba871f3dd06661a8dea6d186318c08a476-31197524107153.png)<br /><br />**피봇 결과 표**<br /><br />[<Image alt="Pivot.png" src="https://files.readme.io/ef9766de2059d0608e8ae6dc063053f2926ffa296e7eca2e13a1bc4171921d2c-31197524111505.png" width="439px" />](https://files.readme.io/ef9766de2059d0608e8ae6dc063053f2926ffa296e7eca2e13a1bc4171921d2c-31197524111505.png) |
| 가장 좋은 성과를 낸 크리에이티브 조합 찾기 | ![creative_sets.png](https://files.readme.io/ef8e38d67121283742dcbd1faef11d94a8ea1c612dc258611e72cbf826d7ef8f-31197524112785.png)<br /><br />잠재 고객이 다양한 크리에이티브 조합에 어떻게 반응하는지 테스트해보는 것은 좋은 마케팅 전략입니다. 성과가 가장 좋은 크리에이티브 조합은 전환율이 가장 높습니다. 또한, 성과가 뛰어난 크리에이티브 조합은 인게이지먼트가 높은 사용자를 끌어들입니다.<br /><br />이는 ASA 잠재 고객 뿐 아니라, 앱 스토어의 앱 페이지에 도달하는 모든 iOS 잠재 고객에게 영향을 미칩니다. 하지만 ASA 인스톨의 경우, 앱스플라이어는 <Anchor target="_blank" href="/marketers/ko/docs/raw-data-field-dictionary">로데이터</Anchor>의 **Ad ID** 파라미터에 크리에이티브 세트 ID를 표시하므로, 서로 다른 크리에이티브 세트의 성과를 비교할 수 있습니다. |
| 재설치 유저(Re-Downloader) 타겟팅하기 | 과거에 앱을 사용했던 사용자들은 ASA를 활용한 타겟팅에서 가장 효과적인 오디언스가 될 수 있습니다.<br /><br />사용자가 앱을 삭제한 후, ASA 리타겟팅 캠페인을 통해 다시 설치하게 되면, ASA에서는 이러한 사용자를 Re-Downloader라고 부릅니다. 이 재설치가 <Anchor target="_blank" href="/marketers/ko/docs/set-up-re-attribution-window">리어트리뷰션 윈도우</Anchor> 내에 이루어진 경우, 앱스플라이어에서는 이를 리어트리뷰션(Re-Attribution)이라고 정의합니다. 다른 모든 경우에는 신규 인스톨로 처리됩니다.<br /><br />![ASACGroupID.png](https://files.readme.io/ebdc380f2abc3e9a3b134cd258d90ae32f75b3ee4d9eadde39adbc728daae523-31197514645265.png) |

</Accordion>

<Accordion title="ASA 업데이트 기록">

| 시행일 | 업데이트/변경 |
| --- | --- |
| 2023-02-07 | 상세 어트리뷰션 파라미터인 `캠페인 이름(Campaign name)`, `애드셋 이름(Adset name)`, 그리고 `키워드(Keywords)`는 구독 플랜과 관계없이 비용 탭이 활성화되어 있어야만 확인할 수 있습니다.  <br />**즉, 대시보드나 로데이터 리포트에서 캠페인 이름, 애드셋 이름, 또는 키워드를 확인하려면 비용 탭이 활성화되어 있어야 합니다.** |
| 2022-02-16 | 키워드는 비용 API를 통해 확인할 수 있습니다. Apple Search Ads 연동 페이지에서 API를 활성화해야 합니다. 참고! API는 귀하의 구독 플랜에 상관없이 모든 광고주가 이용할 수 있습니다. |
| 2021-04-07 | Apple Search Ads 연동: ASA는 SKAdNetwork와는 별도로 작동하며, 확정적으로 사용자를 어트리뷰션합니다. 즉, ASA로 어트리뷰션된 사용자에 대해서는 앱스플라이어 <Anchor target="_blank" href="/marketers/ko/docs/appsflyer-attribution-model">LTV 어트리뷰션 모델</Anchor>이 제공하는 모든 기능과 측정 항목을 온전히 활용할 수 있습니다. |
| 2021-03-07 | Apple Search Ads가 Campaign Management API V4.0을 출시하고 있습니다. 해당 API는 비용 및 기타 캠페인 관련 데이터와 관련되어 있습니다. 어트리뷰션에는 영향을 미치지 않습니다. 우리는 현재 업데이트된 API를 도입하는 중입니다. 귀하께서 추가적인 조치를 취할 필요는 없습니다. |
| 2021-02-15 | 해당 업데이트 날짜부터 ASA[Cost API](/docs/apple-ads-integration-setup#cost-tab)를 활성화하면 캠페인 이름 및 애드셋 이름 필드가 표시될 수 있습니다. API는 구독 플랜에 상관없이 모든 광고주가 이용할 수 있습니다. |

ASA 업데이트 및 변경

</Accordion>

<Accordion title="Apple Search Ads 캠페인 파라미터의 사용 가능 여부">

아래 표는 로데이터 리포트 또는 대시보드에서 어트리뷰션 파라미터의 사용 가능 여부를 보여줍니다.

| 로데이터 리포트 파라미터 | 사용 가능 여부 |
| --- | --- |
| 캠페인 이름 | 이 파라미터를 사용하려면 Apple Search Ads 연동 페이지에서 [비용](/docs/apple-ads-integration-setup#cost-tab) API를 활성화해야 합니다. API는 구독 플랜에 상관없이 모든 광고주가 이용할 수 있습니다. |
| 캠페인 ID | 항상 사용 가능 |
| 광고 세트 이름 | 이 파라미터를 사용하려면 Apple Search Ads 연동 페이지에서 [비용](/docs/apple-ads-integration-setup#cost-tab) API를 활성화해야 합니다. API는 구독 플랜에 상관없이 모든 광고주가 이용할 수 있습니다. |
| 광고세트 ID | 항상 사용 가능 |
| 광고 | 현재 사용 불가 |
| 광고 ID | 이 파라미터는 다음 조건이 모두 충족되는 경우에만 사용할 수 있습니다.<ul><li>사용자가 iOS 15.2 이상을 사용</li><li>해당 광고가 다음 중 하나의 광고 위치와 연결된 캠페인에 대해 <Anchor target="_blank" href="https://developer.apple.com/app-store/product-page/">커스텀 제품 페이지</Anchor>를 사용하는 경우<ul><li>`Today tab`</li><li>`Search results`</li></ul></li></ul> |
| 키워드 | 이 파라미터를 사용하려면 Apple Search Ads 연동 페이지에서 [비용](/docs/apple-ads-integration-setup#cost-tab) API를 활성화해야 합니다. API는 구독 플랜에 상관없이 모든 광고주가 이용할 수 있습니다. |
| 키워드 ID | 이 파라미터는 로데이터 리포트를 통해 사용할 수 있습니다. 그러나 데이터 락커, Push API 및 데이터 내보내기에서 명시적으로 선택해야 합니다. Pull API의 경,우 `keyword_id`를 `Push API 호출`의 <Anchor target="_blank" href="/marketers/ko/docs/pull-api-raw-data#additional-fields">&additional\_fields</Anchor> 파라미터에 추가합니다. |
| 키워드 매칭 유형 | 현재 사용 불가 |

</Accordion>

<Accordion title="집약형 프라이버시 강화 프레임워크의 영향">

iOS 14부터는 [ATTrackingManager(ATT)](https://developer.apple.com/documentation/apptrackingtransparency/attrackingmanager/authorizationstatus/)가 IDFA 사용 가능 여부를 관리하며, ASA는 ASA를 통해 유입된 인스톨의 사용자 수준 어트리뷰션 데이터를 제어합니다. 이와 같이, ASA에서 가져온 인스톨의 사용자 수준 데이터 가용 여부는 <Anchor target="_blank" href="/marketers/ko/docs/apply-aggregated-advanced-privacy-framework">집약형 프라이버시 강화 프레임워크</Anchor>의 영향을 받지 않습니다.

| **ATT 동의** | **클릭/노출 시간 사용 가능** | **클릭/노출 룩백 윈도우** | **비고** | **데이터 가용성** | **IDFA 사용 가능** |
| --- | --- | --- | --- | --- | --- |
| 동의하기 | 예 | 광고주가 설정 | 사용된 앱스플라이어 라스트 클릭 어트리뷰션 규칙 | 사용자 수준 어트리뷰션 데이터 | 예 |
| 비 동의 | 아니요 | 클릭 수: 30일  <br />(ASA에 의해 설정됨)<br /><br />노출 수: 24시간 | 확정적인 후보에게 우선순위가 주어집니다. | 클릭/노출 시간 없는 사용자 수준의 어트리뷰션 데이터 | 아니요 |

</Accordion>

> 📄 **참고 항목**
>
> * <Anchor target="_blank" href="/marketers/ko/docs/apply-aggregated-advanced-privacy-framework">집약형 프라이버시 강화(Aggregated Advanced Privacy, AAP) 프레임워크</Anchor>
> * <Anchor target="_blank" href="/marketers/ko/docs/set-up-lookback-windows">룩백 윈도우 설명</Anchor>