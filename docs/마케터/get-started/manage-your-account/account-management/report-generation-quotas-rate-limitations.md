---
title: 리포트 생성 할당량(비율 제한)
metadata:
  keywords:
    - Advertisers
    - Developers
    - Marketers
    - Platform essentials
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-negri
    - Marketers
    - Platform essentials
  created_at: '2014-05-01T12:55:30Z'
  edited_at: '2026-10-14T10:38:34Z'
  id: 207034366
  locale: ko
  section: Account management
  section_id: 6551191075473
  url: https://support.appsflyer.com/hc/ko/articles/207034366
---
> **한눈에 보기:** 요약: 할당량(속도 제한) 메커니즘은 Pull API 및 데이터 내보내기 페이지에서 하루에 생성할 수 있는 보고서 수를 제한합니다.

<div id="rate-limits-for-reports" />

## 리포트의 비율 제한

할당량은 리포트 유형별로 하루에 생성할 수 있는 리포트 수를 제한합니다. 할당량은 구독 계획에 따라 달라집니다.

**원리:**

* 대행사 에이전시 와 광고주는 각각 별도의 Pull API 할당량을 가지고 있습니다. 할당량은 리포트 별, 일별, 앱별로 동일하게 적용됩니다. 데이터 내보내기 페이지에서 생성한 리포트의 경우, 에이전시와 광고주는 별도의 할당량을 가지고 있습니다. 할당량 제한에 자주 도달하는 경우 어카운트 이그제큐티브에게 문의하십시오.
* **애드 네트워크**: 광고 네트워크: 광고 네트워크에서 생성된 리포트는 광고주 할당량의 일부로 계산되지 않습니다.
* 일 일: 할당량은 00:00 UTC에서 시작하는 역일당입니다.

<div id="aggregated-and-analytics-reports" />

### 종합 및 애널리틱스 리포트

| 데이터 전달 툴 | 견적 |
| --- | --- |
| Pull API 통합 | <ul><li>날짜 범위에서 최대 2일:<ul><li>리포트별로 앱당 1분에 최대 1개의 콜</li></ul></li><li>3일 이상 기간; 콜 수는 다음과 같이 제한됩니다.<ul><li>계정당 하루 최대 120개 콜</li><li>1 앱, 1 일 당 24개 콜</li></ul></li></ul> |
| 종합 데이터 내보내기 페이지 | 무제한 |
| 마스터 API | 무제한 |
| 코호트 API | 1 분, 1 계정 당 60개 콜 |
| SKAN 통합 리포트 | 1 분, 1 계정 당 10개 콜 |

<div id="note" />

<div id="pull-api-raw-data-daily-quota" />

<div id="raw-data" />

### 로데이터

* 각 리포트 도구에는 Pull API 및 로데이터 리포트 페이지라는 별도의 할당량이 적용됩니다.
* 에이전시 와 광고주는 각각 별도의 Pull API 할당량을 가지고 있습니다. 에이전시가 생성한 리포트는 광고주 할당량에 포함될 수 있습니다. 유일한 예외는 대행사가 자체 API 토큰 대신 광고주의 API 토큰을 사용하는 경우이며, 이 경우 요청은 광고주 요청과 구별할 수 없으며 광고주 할당량에 포함됩니다. 데이터 내보내기 페이지에서 생성한 리포트의 경우, 에이전시와 광고주는 별도의 할당량을 가지고 있습니다.
* API pull 할당량은 다음에 따라 적용됩니다.
  * 보고서
  * 일
  * 앱 수준
  * 계정 수준
* 광고주의 경우 할당량은 앱스플라이어 구독에 따라 달라집니다. **참고**: 참고: 할당량은 프리미엄 구독이 필요한 리포트에도 적용됩니다.
* 애드 네트워크 포스트백 보고서의 일일 할당량은 다음 표 와 같습니다.

이해를 쉽게 하기 위해 표 다음에 나오는 FAQ를 참조하십시오.

<div id="ad-network-postback-reports-daily-quota" />

#### 광고 네트워크 포스트백 보고서 일일 할당량

광고 네트워크는 다음과 같은 포스트백 리포트 유형을 가져올 수 있습니다.

| 포스트백 그룹 | 리포트 유형  <br />(각 리포트 유형별로 할당량이 다릅니다.) | 앱별 일일 할당량 | 계정별 일일 할당량 |
| --- | --- | --- | --- |
| 출처 표기를 위한 포스트백 | <ul><li>설치</li><li>리타게팅 전환</li></ul> | 24 | 120 |
| 인앱 이벤트에 대한 포스트백 | <ul><li>인앱 이벤트</li><li>리타겟팅 인앱 이벤트</li></ul> | 12 | 60 |

<div id="faq" />

#### **자주 묻는 질문**

* Q: 질문: 특정 앱에 대해 Pull API를 사용하여 24개의 오가닉 인스톨 리포트를 생성하고 로데이터 내보내기 페이지를 사용하여 24개의 리포트를 생성할 수 있습니까?답변: 네.  
  A: 네. 리포트 도구당 할당량은 분리됩니다.
* Q: 질문: 특정 앱에 대해 로데이터 내보내기 페이지를 사용하여 24개의 오가닉 인스톨 리포트, 24개의 논오가닉 인스톨 리포트 및 24개의 리타게팅 전환 리포트를 생성할 수 있습니까?  
  A: 네. 리포트 유형당 할당량은 분리됩니다.
* Q: 질문: 저의 계정에 25개 앱이 있습니다. 앱별로 오가닉 인스톨 보고서를 10개씩 생성할 수 있나요?  
  A: 아니요. 이로 인해 총 250건의 보고서가 생성되어 계정별 할당량인 120건을 초과하게 됩니다.
* Q: 대행사에서 생성한 Pull API 보고서는 광고주의 할당량에 포함되나요?  
  A: 아니요. 에이전시 와 광고주는 각각 별도의 Pull API 할당량을 가지고 있습니다. 에이전시가 생성한 리포트는 광고주 할당량에 포함될 수 있습니다. 유일한 예외는 대행사가 자체 API 토큰 대신 광고주의 API 토큰을 사용하는 경우이며, 이 경우 해당 요청은 광고주 요청으로 간주됩니다.

<div id="see-also" />

> 📄 **참고 항목**
>
> * <Anchor target="_blank" href="/marketers/ko/docs/data-availability-windows">데이터 가용성 기간</Anchor>

<div data-zendesk-anchors="rate-limits-for-reports=%EB%A6%AC%ED%8F%AC%ED%8A%B8%EC%9D%98-%EB%B9%84%EC%9C%A8-%EC%A0%9C%ED%95%9C h_01H9JNZFPSVXPKMEVR1ZR6PSYG=%EB%A6%AC%ED%8F%AC%ED%8A%B8%EC%9D%98-%EB%B9%84%EC%9C%A8-%EC%A0%9C%ED%95%9C aggregated-and-analytics-reports=%EC%A2%85%ED%95%A9-%EB%B0%8F-%EC%95%A0%EB%84%90%EB%A6%AC%ED%8B%B1%EC%8A%A4-%EB%A6%AC%ED%8F%AC%ED%8A%B8 h_01H9JNZFPS62A5CFWSXVPN8XM5=%EC%A2%85%ED%95%A9-%EB%B0%8F-%EC%95%A0%EB%84%90%EB%A6%AC%ED%8B%B1%EC%8A%A4-%EB%A6%AC%ED%8F%AC%ED%8A%B8 raw-data=%EB%A1%9C%EB%8D%B0%EC%9D%B4%ED%84%B0 h_01H9JNZFPSPYWBB2MCZV2R2KX1=%EB%A1%9C%EB%8D%B0%EC%9D%B4%ED%84%B0 ad-network-raw-data-daily-quota=%EA%B4%91%EA%B3%A0-%EB%84%A4%ED%8A%B8%EC%9B%8C%ED%81%AC-%ED%8F%AC%EC%8A%A4%ED%8A%B8%EB%B0%B1-%EB%B3%B4%EA%B3%A0%EC%84%9C-%EC%9D%BC%EC%9D%BC-%ED%95%A0%EB%8B%B9%EB%9F%89 h_01H9JNZFPSYXZNW81BZTRDS576=%EA%B4%91%EA%B3%A0-%EB%84%A4%ED%8A%B8%EC%9B%8C%ED%81%AC-%ED%8F%AC%EC%8A%A4%ED%8A%B8%EB%B0%B1-%EB%B3%B4%EA%B3%A0%EC%84%9C-%EC%9D%BC%EC%9D%BC-%ED%95%A0%EB%8B%B9%EB%9F%89 faq=%EC%9E%90%EC%A3%BC-%EB%AC%BB%EB%8A%94-%EC%A7%88%EB%AC%B8 h_01H9JNZFPT76RAV8JBTY2K75V4=%EC%9E%90%EC%A3%BC-%EB%AC%BB%EB%8A%94-%EC%A7%88%EB%AC%B8 h_01HE7SW3VWRNVY1WFB4YCSAVY6=%EC%B0%B8%EA%B3%A0-%ED%95%AD%EB%AA%A9" />
