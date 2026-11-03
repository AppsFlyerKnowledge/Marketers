---
title: TikTok for Business와 SKAN 측정 데이터 상호운용성
metadata:
  keywords:
    - Advertisers
    - ios14
    - Marketers
    - SKAdNetwork (SKAN)
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - SKAdNetwork (SKAN)
  created_at: '2021-03-14T12:05:58Z'
  edited_at: '2026-10-14T10:37:21Z'
  id: 360018499098
  locale: ko
  section: SKAN interoperation
  section_id: 6552115163153
  url: https://support.appsflyer.com/hc/ko/articles/360018499098
---
> **요약:** 틱톡과 앱스플라이어는 SKAN 데이터가 상호 호환되어 틱톡은 SKAN 포스트백을 앱스플라이어와 공유할 수 있고, 앱스플라이어는 앱 기업의 전환 값 매핑 정보를 틱톡과 공유할 수 있습니다.

## SKAN 상호운용성: 앱스플라이어 &lt;-> TikTok

다양한 애드 네트워크 파트너와 작업하는 경우 앱스플라이어 한 플랫폼에 연동하는 것이 효율적입니다. 이렇게 하면 비용 등의 다른 지표와 함께 향상된 SKAN 성능 지표를 앱스플라이어 플랫폼에서 확인할 수 있습니다.

### TikTok과의 SKAN 상호운용 범위

이 상호작용을 통해 앱스플라이어와 TikTok은 앱스플라이어에서 설정한 SKAN 전환 값 매핑 정보를 공유합니다. 이를 통해 양측 모두 성과 지표를 제공할 수 있습니다. 앱스플라이어에서 TikTok for Business 연동(기존 혹은 Advanced SRN 연동 포함)을 활성화하면, 앱스플라이어는 최적화 용도의 TikTok 이벤트를 제공합니다. TikTok에서 지원하는 <Anchor target="_blank" href="/marketers/ko/docs/skan-integrated-partners-list">데이터 보강 필드 목록</Anchor>을 확인하세요.

### TikTok for Business 가이드

TikTok for Business 캠페인 설정 시, TikTok의 <Anchor target="_blank" href="https://ads.tiktok.com/help/article?aid=10000858">iOS 14 영향 및 지침 개요</Anchor>를 읽고 다음 사항을 확인하세요.

* <Anchor target="_blank" href="/marketers/ko/docs/sdk-integration-overview">앱스플라이어 SDK</Anchor>가 최신인지 확인하십시오.
* TikTok for Business에서 홍보하는 각 앱에 대해 [TikTok 앱 ID](https://ads.tiktok.com/help/article?aid=10001060)를 설정하세요.
  * TikTok 앱 ID는 TikTok Ads Manager에서 생성된 고유 코드로, 광고주가 앱의 소유권을 확인하는 데 사용됩니다.
  * 필수 사항은 아니지만, 모든 앱의 앱 ID를 입력하는 것이 추천됩니다.  
    이를 통해 TikTok for Business 데이터를 더욱 효과적으로 관리하고 추가 기능을 사용할 수 있습니다.
  * **여러 개의 TikTok 앱 ID를 추가하는 방법:**
    1. 첫 번째 TikTok 앱 ID를 입력하세요.
    2. **Enter**를 누릅니다.
    3. 다음 TikTok 앱 ID를 입력하세요.
  * TikTok 앱 ID를 구성하는 것은 앱스플라이어 내의 데이터에 영향을 끼치지 않습니다.
  * [iOS 14에 대한 TikTok 앱 ID 요건에 대해 자세히 알아보기](https://ads.tiktok.com/help/article?aid=10001070).
* bytedanceglobal\_int 및 tiktokglobal\_int에 대한 [전체 전환 이벤트 매핑](/docs/skan-interoperation-with-tiktok-for-business#3).
* 캠페인 제한 및 계정/캠페인 통합 지침을 검토하세요.

TikTok for Business 계정 관리자와 직접 협력하여 SKAN 구성 및 전략을 설정하세요.

TikTok은 다음과 같은 방식으로 SKAN을 지원합니다:

* 전환 측정 API를 통한 측정 및 최적화 지원.
* TikTok for Business에서 iOS 14 전용 캠페인 리포팅 지원.

### iOS 14 전용 캠페인의 캠페인 제한

SKAN API의 제한으로 인해, 틱톡 비즈니스는 iOS 14 전용 캠페인 생성 시 (앱 설치 광고 및 앱 타겟팅을 위한 다이내믹 상품 광고 포함) 아래 사항을 지원합니다:

* ​iOS 앱은 15개 캠페인으로 제한되며 각 캠페인당 5개 광고 그룹까지 가능합니다.
* iOS 14 전용 캠페인에 대하여:
  * 여러 광고 계정을 통해 생성할 수 있으나, 활성 캠페인의 총 개수는 15개로 제한됩니다.
  * 관련된 모든 목표들이 제한 수치(15)에 포함되며, 캠페인 제한에 도달한 후 광고주는 캠페인을 일시 정지하거나 종료, 삭제한 뒤 최소 72시간이 지나 새로운 캠페인을 개시하기 위한 여유 슬롯이 생기기를 기다려야 합니다.

### 상호운영성 활성화하기

상호운영성은 앱스플라이어와 틱톡 비즈니스 대시보드 내의 설정을 통해 이뤄집니다. 앱 자체에는 별도의 호환 조치나 변경 사항이 요구되지 않습니다.

**TikTok for Business**와 앱스플라이어 간 SKAN 데이터 호환을 활성화시키는 법:

| 단계 | 작업 | 세부 사항 |
| --- | --- | --- |
| <span id="1"></span>1 | 앱 시작 전 준비사항 | <ul><li>최신 앱스플라이어 SDK를 귀하의 앱에 통합하세요.</li></ul> |
| <span id="2"></span>2 | SKAN 설정 점검 | 앱스플라이어의 <Anchor target="_blank" href="/marketers/ko/docs/skadnetwork-skan-solution-guide">SKAN 솔루션</Anchor>을 설정하고 킨 다음 확인하세요.<br /><br />**SKAN 설정은 여기에서 확인하세요**:<ol><li>앱스플라이어에서 **설정** > **SKAN 컨버전 스튜디오**로 이동합니다.</li><li>클릭 옵션 (⋮), 그리고**SKAN 측정**이 활성화되어 있는지 확인하세요.</li></ol>![skan-settings.png](https://files.readme.io/5a5b9b8b8a809336055340a14e49dacc16c5c0e95cda62c6dfb2ca9a11618d71-27548444964497.png)<ol><li>선호하는 측정 모드를 선택해 주세요.<br /><Anchor target="_blank" href="/marketers/ko/docs/skan-conversion-studio">SKAN 컨버전 스튜디오</Anchor>에 대해 더 보기.</li><li>설정한 정확한 이벤트 이름들을 메모해 두세요. 다음 단계에 필요합니다.</li></ol> |
| <span id="3"></span>3 | 인앱 이벤트 맵핑하기 | TikTok for Business의 인앱 이벤트 맵핑을 검토하고 필요시 변경하세요.<br /><br />**인앱 이벤트 맵핑 설정 및 보기**:<ol><li>앱스플라이어에서 **설정** > **활성 연동**으로 이동합니다.</li><li>TikTok for Business를 검색하여 선택합니다.</li><li>**연동** 탭에서, TikTok for Business와의 연동이 활성화되고 설정되어 있는지 확인하세요.</li><li>**인앱 이벤트 포스트백 섹션에서:**<ol><li>[필수] 비활성인 경우, **인앱 이벤트 포스트백**을 활성화하세요.</li><li>TikTok for Business 이벤트 이름에 <Anchor target="_blank" href="/marketers/ko/docs/skan-conversion-studio">SKAN 컨버전 스튜디오</Anchor>에서 설정하신 인앱 이벤트들이 또는 유저가 설정한 <Anchor target="_blank" href="/marketers/ko/docs/skan-cv-decode-map-your-cv-to-events">커스텀 전환 값 맵</Anchor><Anchor target="_blank" href="/marketers/ko/docs/skan-cv-decode-map-your-cv-to-events">에 잘 매핑되었는지 확인하세요.<br />**참고:** `af_skad_revenue`을 TikTok의 이벤트 이름 `Purchase`로 매핑합니다.<br />[![](https://files.readme.io/a5b5f9cccacd4cc531a09413e4e5040a8214abc3a8a7f795fbec678e81ab603e-25706935571217.jpg)](https://files.readme.io/a5b5f9cccacd4cc531a09413e4e5040a8214abc3a8a7f795fbec678e81ab603e-25706935571217.jpg)</Anchor></li></ol></li><li>**연동 저장**을 클릭하세요.</li></ol> |

> 📄 **참고 항목**
>
> * <Anchor target="_blank" href="/marketers/ko/docs/skadnetwork-skan-solution-guide">앱스플라이어 SKAN 솔루션 안내서</Anchor>

<div data-zendesk-anchors="skan-interoperability-appsflyer-tiktok=skan-%EC%83%81%ED%98%B8%EC%9A%B4%EC%9A%A9%EC%84%B1-%EC%95%B1%EC%8A%A4%ED%94%8C%EB%9D%BC%EC%9D%B4%EC%96%B4---tiktok h_01HDNYZ0CT1MGCRSSP3MXTJK5V=skan-%EC%83%81%ED%98%B8%EC%9A%B4%EC%9A%A9%EC%84%B1-%EC%95%B1%EC%8A%A4%ED%94%8C%EB%9D%BC%EC%9D%B4%EC%96%B4---tiktok scope-of-skan-interoperability-with-tiktok=tiktok%EA%B3%BC%EC%9D%98-skan-%EC%83%81%ED%98%B8%EC%9A%B4%EC%9A%A9-%EB%B2%94%EC%9C%84 h_01HDNYZ0CT5NZHDHDBDSCFG911=tiktok%EA%B3%BC%EC%9D%98-skan-%EC%83%81%ED%98%B8%EC%9A%B4%EC%9A%A9-%EB%B2%94%EC%9C%84 tiktok-for-business-guidance=tiktok-for-business-%EA%B0%80%EC%9D%B4%EB%93%9C 01HR1TPFCSXRGYC610AR7KMTS5=tiktok-for-business-%EA%B0%80%EC%9D%B4%EB%93%9C campaign-limits-for-dedicated-ios-14-campaigns=ios-14-%EC%A0%84%EC%9A%A9-%EC%BA%A0%ED%8E%98%EC%9D%B8%EC%9D%98-%EC%BA%A0%ED%8E%98%EC%9D%B8-%EC%A0%9C%ED%95%9C h_01HDNYZ0CT7RNDAEWYKBHS6PET=ios-14-%EC%A0%84%EC%9A%A9-%EC%BA%A0%ED%8E%98%EC%9D%B8%EC%9D%98-%EC%BA%A0%ED%8E%98%EC%9D%B8-%EC%A0%9C%ED%95%9C enabling-interoperation=%EC%83%81%ED%98%B8%EC%9A%B4%EC%98%81%EC%84%B1-%ED%99%9C%EC%84%B1%ED%99%94%ED%95%98%EA%B8%B0 h_01HDNYZ0CTJGY3GPC9F907NEPT=%EC%83%81%ED%98%B8%EC%9A%B4%EC%98%81%EC%84%B1-%ED%99%9C%EC%84%B1%ED%99%94%ED%95%98%EA%B8%B0 h_01HDNZ1BW5EBP0JCX84MTYPQ6K=%EC%B0%B8%EA%B3%A0-%ED%95%AD%EB%AA%A9" />
