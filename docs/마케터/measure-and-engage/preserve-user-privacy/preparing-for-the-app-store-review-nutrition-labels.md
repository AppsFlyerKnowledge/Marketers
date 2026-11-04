---
title: 애플 앱 스토어 검토 준비—영양성분표
metadata:
  keywords:
    - iOS
    - iTunes
    - Apple
    - IDFA
    - Guidelines
    - IFA
    - Ad Tracking
    - Advertisers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-guy-sarfatty
    - Marketers
    - Mobile Attribution
  created_at: '2014-04-12T13:28:26Z'
  edited_at: '2026-10-14T10:39:58Z'
  id: 207032086
  locale: ko
  section: Preserve user privacy
  section_id: 6551440878097
  url: https://support.appsflyer.com/hc/ko/articles/207032086
---
> **한눈에 보기**:

 여기에 명시된 내용은 법적 조언이 아닙니다. 정보와 편의를 위해 제공됩니다.

<div id="nutrition-labels-and-the-app-store-review" />

## 영양 라벨 및 앱 스토어 검토

* 앱 개발자는 앱 스토어 Connect에 앱 제출시, 질문지에 응답하여 개인정보 보호 라벨을 생성해야 합니다. 제출해야 할 답변은 다음과 같습니다.
  * 수집 데이터 유형
  * [데이터 수집 목적](/docs/preparing-for-the-app-store-review-nutrition-labels#데이터-사용-목적)
  * [수집하는 데이터 유형이 식별자와 연결되는지 여부](/docs/preparing-for-the-app-store-review-nutrition-labels#사용자-id에-연결된-데이터)
  * 수집하는 데이터를 추적에 사용 여부(제3자나 앱에 포함된 SDK의 추적 활동 포함)
* 앱 개발사는
  * 앱스플라이어 소프트웨어를 설정하고 구현하는 방식에 대해 전적인 권한이 있으며, 앱스플라이어를 통해 어떤 데이터를 수집할지, 수집한 데이터를 어떤 방식으로 사용할지에 대해 관리합니다.
  * 앱스플라이어 소프트웨어를 설정하는 방식과 수집하려는 데이터 포인트에 따라 애플 앱스토어 질문지에 다르게 답변할 수 있습니다.
* 앱스플라이어의 Apple 정책 이해에 따르면 앱스플라이어는 추적하지 않습니다. 앱 개발사는 이 점을 고려하여 자사의 특정 용도와 파트너사 연동 구성에 따라 Apple 앱 스토어 질문지에 답해야 합니다.
* 추적 용도로 수집된 데이터를 사용하는 경우, ATT 프롬프트를 구현해야 합니다.
* 다음은 앱스플라이어 소프트웨어의 기본 설정을 기준으로 합니다. 앱 개발사는 그들의 특정 설정 및 용도에 따라 적절히 적응하도록 보장해야 할 책임이 있습니다.

<div id="data-types-collected" />

#### 수집 데이터 유형

| **데이터 유형** | **앱스플라이어의 데이터 수집 여부** | **비고** |
| --- | --- | --- |
| **연락처 정보**<ul><li>이름</li><li>이메일 주소(해시 포함)</li><li>전화번호(해시 포함)</li><li>우편주소</li><li>기타 앱 사용자 연락처 정보</li></ul> | 아니요 | 연락처 정보는 수집하면 안 됩니다. 하지만 해시가 있는 이메일이나 전화번호를 전송하도록 설정했다면 앱 스토어 질문지에 맞게 답변하십시오. |
| **피트니스** | 아니요 | 수집하지 않습니다. |
| **결제 정보**<ul><li>결제 정보(Payment Info)</li><li>신용 정보(예: 신용 점수)</li><li>기타 재무 정보(예: 월급, 수입, 자산, 부채)</li></ul> | 아니요 | 수집하지 않습니다. |
| **위치 정보**<ul><li>정확한 위치</li><li>대략적인 위치</li></ul> | /span>설명 참조 | <ul><li>정확한 위치 아니요</li><li>대략적인 위치 네. IP 주소가 수집되며 대략적인 위치에 매핑됩니다.</li></ul> |
| **민감 정보** | 아니요 | 수집하지 않습니다. |
| **연락처** | 아니요 | 수집하지 않습니다. |
| **사용자 콘텐츠**<ul><li>이메일 또는 문자 메시지</li><li>사진 또는 비디오</li><li>오디오 데이터</li></ul> | 아니요 | 수집하지 않습니다. |
| **방문 기록** | 아니요 | 수집하지 않습니다. |
| **검색 기록** | 아니요 | 수집하지 않습니다. |
| **식별자**<ul><li>사용자 ID</li><li>기기 ID (IDFA)</li></ul> | 선택 사항 | <ul><li>\_유저\_아이디 사용자 ID: 앱 개발자가 사용자 ID(CUID)를 설정하고 전송할 수 있습니다.</li><li>디바이스 ID 기기 ID: 기기의 광고식별자(IDFA: Identifier for Advertisers)는 접근이 가능할 경우에만 수집됩니다.</li></ul> |
| **구입 항목**<ul><li>구입 내역</li></ul> | 선택 사항 | 앱 개발사는 인앱구매를 측정하기 위해 특정 인앱구매 이벤트를 설정할 수 있습니다. |
| **앱 사용 데이터**<ul><li>앱 사용</li><li>광고 데이터</li><li>기타 사용 데이터</li></ul> | <ul><li>예</li><li>선택 사항</li><li>아니요</li></ul> | <ul><li>앱 사용 앱 사용 활동 데이터: 앱 실행 및 탭, 클릭, 인앱구매, 인앱광고 조회 증 앱 개발사가 미리 설정한 앱 사용 활동을 측정합니다.</li><li>광고 데이터: 앱 개발사가 앱스플라이어의 광고 수익 모듈을 사용하면 광고 데이터가 수신됩니다.</li></ul> |
| **진단 데이터**<ul><li>사고 데이터</li><li>성과 데이터</li><li>기타 진단 데이터</li></ul> | <ul><li>아니오</li><li>예</li><li>아니요</li></ul> | 프로드 탐지를 위해 앱 사용 시작 시간 및/또는 배터리 잔량이 수신될 수 있습니다. |
| **기타 데이터**<ul><li>기타 데이터 유형</li><li>IDFV</li></ul> | 예 | <ul><li>앱스플라이어가 기기 정보(예: OS, 기기 유형, 언어, 화면 크기 등) 또는 네트워크 정보(예: IP 주소, HTTP 사용자 에이전트)를 수신합니다.</li><li>앱스플라이어는 각 앱 설치에 AF ID(AppsFlyer ID)라고 불리는 인스톨 ID를 부여합니다.</li><li>IDFV가 수집됩니다.</li></ul> |

<div id="data-use-purposes" />

### 데이터 사용 목적

Google은 앱 개발자가 반드시 선택해야 하는 목적의 목록을 아래의 표에 자세하게 제공했습니다.

| 데이터 사용 목적 | 앱스플라이어의 데이터 사용방식에 기반한 선택 |
| --- | --- |
| 타사 광고 | 귀사의 앱에 타사의 광고를 게재할 목적으로 타사와 데이터 유형을 공유할 경우 선택하십시오. |
| 앱 개발사의 광고 또는 마케팅 | 귀사의 앱에 자사 광고를 게재하거나 기타 마케팅 목적으로 데이터를 사용하는 경우 선택하십시오. (귀사의 광고를 게재하기 위해 제3자와 데이터를 공유하는 경우도 포함됩니다.) |
| 분석 | 네 |
| 제품 개인 맞춤화 | 개인화 서비스를 제공하기 위해 데이터를 사용하는 경우 선택하십시오. |
| 앱 기능 | 예 |
| 기타 목적 | 열거되지 않은 기타 목적으로 데이터를 사용하는 경우 선택하십시오. |

<div id="data-linked-to-an-identity" />

### 사용자 ID에 연결된 데이터

앱스플라이어를 통해 수집된 데이터 유형은 일반적으로 기기 ID(수집 가능한 경우) 혹은 고객 기반 ID(미리 설정한 경우)와 같은 ID와 연결되어 있습니다.

그러므로 앱 개발사는 데이터가 사용자 ID와 연결되어 있냐는 질문에 예를 선택해야 합니다.

<div id="see-also" />

> 📄 **참고 항목**
>
> * <Anchor target="_blank" href="https://developer.apple.com/app-store/app-privacy-details/">Apple 앱 스토어 앱 개인정보 보호정책</Anchor>

<div data-zendesk-anchors="nutrition-labels-and-the-app-store-review=%EC%98%81%EC%96%91-%EB%9D%BC%EB%B2%A8-%EB%B0%8F-%EC%95%B1-%EC%8A%A4%ED%86%A0%EC%96%B4-%EA%B2%80%ED%86%A0 h_01HE7T7J409620K5KX5XKPEQVZ=%EC%98%81%EC%96%91-%EB%9D%BC%EB%B2%A8-%EB%B0%8F-%EC%95%B1-%EC%8A%A4%ED%86%A0%EC%96%B4-%EA%B2%80%ED%86%A0 data-types-collected=%EC%88%98%EC%A7%91-%EB%8D%B0%EC%9D%B4%ED%84%B0-%EC%9C%A0%ED%98%95 h_01HE7T7J4004XVJTMF6S964DVB=%EC%88%98%EC%A7%91-%EB%8D%B0%EC%9D%B4%ED%84%B0-%EC%9C%A0%ED%98%95 data-use-purposes=%EB%8D%B0%EC%9D%B4%ED%84%B0-%EC%82%AC%EC%9A%A9-%EB%AA%A9%EC%A0%81 h_01HE7T7J4098NNW8D0BCD3EFBJ=%EB%8D%B0%EC%9D%B4%ED%84%B0-%EC%82%AC%EC%9A%A9-%EB%AA%A9%EC%A0%81 data-linked-to-an-identity=%EC%82%AC%EC%9A%A9%EC%9E%90-id%EC%97%90-%EC%97%B0%EA%B2%B0%EB%90%9C-%EB%8D%B0%EC%9D%B4%ED%84%B0 h_01HE7T7J41BJG9GTBWMVKG7031=%EC%82%AC%EC%9A%A9%EC%9E%90-id%EC%97%90-%EC%97%B0%EA%B2%B0%EB%90%9C-%EB%8D%B0%EC%9D%B4%ED%84%B0 h_01HE7TES34MEF1XR4B6BDEMJW4=%EC%B0%B8%EA%B3%A0-%ED%95%AD%EB%AA%A9" />
