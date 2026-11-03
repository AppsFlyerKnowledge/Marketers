---
title: Medialyzer와 앱스플라이어의 연동
metadata:
  keywords:
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2023-05-01T11:43:34Z'
  edited_at: '2026-10-14T10:26:13Z'
  id: 14963611180689
  locale: ko
  section: 3rd-party platforms
  section_id: 6551199962257
  url: https://support.appsflyer.com/hc/ko/articles/14963611180689
---
> **한눈에 보기:**

> 🚧 **중요!**
>
> <Anchor target="_blank" href="/marketers/ko/docs/about-raw-data-identifier-restrictions#미디어-소스-제한">일부 미디어소스</Anchor>는 타사와의 데이터 공유를 제한합니다. 따라서 제한된 이벤트에 대한 포스트백은 포스트백을 보내기 위해 구성된 선택에 관계없이 이 파트너에게 전송되지 않습니다.

## Medialyzer 설정

**전제 조건:** 연동 설정 전에 <Anchor target="_blank" href="/marketers/ko/docs/partner-integrations#contact-details">파트너에게 연락</Anchor>하여 계정을 개설하세요.

**연동 활성화 또는 편집 방법:**

1. To activate:연동 활성화 방법: 앱스플라이어의 사이드 메뉴에서협업**>**파트너 마켓플레이스**를 선택합니다.  
   **편집 방법:** 앱스플라이어의 사이드 메뉴에서 **협업**> 활성화된 연동을 선택합니다.**
2. 파트너를 검색하고 선택합니다.
3. **연동 설정**을 클릭하십시오. 연동 설정 페이지로 이동합니다.
4. **연동** 탭에서 연동할 앱을 선택하고 **파트너 활성화**를 켭니다.  
   **참고: 파트너와의 작업 동안 토글이 활성화되어 있어야 합니다<Anchor target="_blank" href="/marketers/ko/docs/partner-activation-deactivation">(활성화됨)</Anchor>.**
5. 아래 설명된 대로 관련 탭을 사용하여 설정을 완료하십시오.

설정 창에서는 **연동** 탭만 활용합니다.

<Anchor target="_blank" href="/marketers/ko/docs/set-up-an-integrated-partner#about-the-integrated-partner-page">여기</Anchor>를 클릭하여 파트너 설정 창 헤더에 대한 자세한 설명을 확인하십시오.

<div id="integration-tab" />

<Accordion title="연동 탭">

#### 파트너 활성화

처음 방문 시에 **파트너 활성화** 토글을 켜서 연동을 설정해야 합니다. 토글은 Medialyzer로 작업하는 동안 켜져 있어야 합니다. <Anchor target="_blank" href="/marketers/ko/docs/partner-activation-deactivation">파트너 활성화</Anchor>에 대해 더 알아보십시오.

#### 프라이버시 강화 모드

iOS 앱의 경우 <Anchor target="_blank" href="/marketers/ko/docs/apply-aggregated-advanced-privacy-framework">고급 개인 정보 보호</Anchor> 토글이 나타납니다. 이 기능을 켜면 파트너와의 사용자 식별자 공유가 제한됩니다. 앱 설정에서 <Anchor target="_blank" href="/marketers/ko/docs/apply-aggregated-advanced-privacy-framework">집약형 프라이버시 강화</Anchor> 토글을 설정하면 **Advanced Privacy(iOS 14.5+ 이상의 경우)** 가 기본적으로 켜지고 잠깁니다.

#### 기본 포스트백

앱스플라이어는 사용자 인스톨 후 Medialyzer에 기본 포스트백을 보냅니다. 이 섹션을 사용하여 이러한 포스트백을 정의할 수 있습니다.

* **끄기**: 끄기: 인스톨 포스트백이 Medialyzer로 전송되지 않습니다.
* **오가닉을 포함한 모든 매체 소스**:

![default_postbacks.png](https://files.readme.io/d78c2e8335e80c3a1b18b57ba3b2974ffd5622a3728c85b6ecd89569b48e905b-14963640623505.png)

#### 인앱 이벤트 포스트백

이 섹션에서는 포스트백을 통해 앱스플라이어 이벤트를 파트너와 매핑할 수 있습니다.

[![app_event_postbacks.JPG](https://files.readme.io/a6a4aaa89c3eb5ba759a32312663b4c9855738eaea56366070ca9a8da3840a69-14963640866833.png)](https://files.readme.io/a6a4aaa89c3eb5ba759a32312663b4c9855738eaea56366070ca9a8da3840a69-14963640866833.png)

1. **인앱 이벤트 포스트백**을 활성화하세요.
2. **이벤트 추가**를 클릭하여 목록에 SDK 또는 서버-투-서버 이벤트를 추가합니다.
3. 다음 파라미터를 완성하세요. 

| 파라미터 이름 | 설명 |
| --- | --- |
| **앱스플라이어 이벤트** | 앱스플라이어가 앱에 연동된 SDK 또는 서버 간 이벤트에서 수신한 이벤트의 이름입니다.<br />**팁**: 찾고 있는 이벤트가 없나요?<ul><li>논오가닉 인스톨 및 재확인을 통해 디바이스에서 이벤트가 활성화되었는지 확인합니다.</li><li>**앱스플라이어 이벤트**에 입력한 다음 **사용자 지정 생성**을 클릭합니다. <Anchor target="_blank" href="/marketers/ko/docs/in-app-event-postback-configuration#커스텀-이벤트">커스텀 이벤트 매핑</Anchor>에 대해 더 알아보세요.</li></ul> |
| **파트너 이벤트에 매핑** | BPM에 정의된 대로 각 이벤트의 해당 이벤트 이름 또는 ID를 입력하거나 이름 매핑 없이 있는 그대로 이벤트를 전송하십시오. |
| **사용자용** | **오가닉을 포함한 모든 미디어소스**를 선택하여 모든 파트너에 어트리뷰트된 이벤트 및 오가닉 이벤트에 대한 포스트백을 전송합니다. |
| **포함** | <ul><li>**값 없음 및 수익 없음**: 파라미터 없이 이벤트 자체만 발송합니다 (값이나 수익).</li><li>**값 있음 및 수익 없음**: 수익 값을 **제외한** 모든 파라미터를 전송합니다.</li><li>**값 있음 & 수익 있음**: 수익 값이 있는 경우 이를 **포함**한 모든 이벤트 파라미터를 발송합니다.</li></ul> |

4. **연동 저장**을 클릭합니다.

</Accordion>

<div id="attribution-link-tab" />

<Accordion title="어트리뷰션 링크 탭">

어트리뷰션 링크는 Medialyzer에서 사용할 수 없습니다.

</Accordion>

<div id="cost-tab" />

<Accordion title="비용 탭">

비용 데이터는 Medialyzer와의 연동에서 지원되지 않습니다.

</Accordion>

<div id="ad-revenue-tab" />

<Accordion title="광고 수익 탭">

광고 수익 데이터는 Medialyzer와의 연동에서지원되지 않습니다.

</Accordion>

<div id="permissions-tab" />

<Accordion title="권한 탭">

Medialyzer에 대한 권한을 사용할 수 없습니다.

</Accordion>

<div data-zendesk-anchors="h_01H9FKEAV2225HM5CQAGWS2K99=%EC%A4%91%EC%9A%94 setting-up-spoteffects=medialyzer-%EC%84%A4%EC%A0%95 h_01H9FKEAV37AT3VTZ5WV1YMWC2=medialyzer-%EC%84%A4%EC%A0%95 h_01H9FKEAV3YQY124TSZ5Q7VHAY=integration-tab activate-partner=%ED%8C%8C%ED%8A%B8%EB%84%88-%ED%99%9C%EC%84%B1%ED%99%94 h_01H9FKEAV3DW2A6RQ1NS44FT5F=%ED%8C%8C%ED%8A%B8%EB%84%88-%ED%99%9C%EC%84%B1%ED%99%94 advanced-privacy=%ED%94%84%EB%9D%BC%EC%9D%B4%EB%B2%84%EC%8B%9C-%EA%B0%95%ED%99%94-%EB%AA%A8%EB%93%9C h_01H9FKEAV3T3YCPBYW70QVF540=%ED%94%84%EB%9D%BC%EC%9D%B4%EB%B2%84%EC%8B%9C-%EA%B0%95%ED%99%94-%EB%AA%A8%EB%93%9C default-postbacks=%EA%B8%B0%EB%B3%B8-%ED%8F%AC%EC%8A%A4%ED%8A%B8%EB%B0%B1 h_01H9FKEAV3Z1Y09P6E18J8AVX2=%EA%B8%B0%EB%B3%B8-%ED%8F%AC%EC%8A%A4%ED%8A%B8%EB%B0%B1 inapp-event-postbacks=%EC%9D%B8%EC%95%B1-%EC%9D%B4%EB%B2%A4%ED%8A%B8-%ED%8F%AC%EC%8A%A4%ED%8A%B8%EB%B0%B1 h_01H9FKEAV3GG6X17X3NCCSWJAS=%EC%9D%B8%EC%95%B1-%EC%9D%B4%EB%B2%A4%ED%8A%B8-%ED%8F%AC%EC%8A%A4%ED%8A%B8%EB%B0%B1 h_01H9FKEAV3ZEF1AHRTQGEGYFSJ=attribution-link-tab h_01H9FKEAV3ERXQ98BJGKBQRGP2=cost-tab h_01H9FKEAV32MB7M2Q1ASDAE6RM=ad-revenue-tab h_01H9FKEAV3ZNKMZSG76B61H2AS=permissions-tab" />
