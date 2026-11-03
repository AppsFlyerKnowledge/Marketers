---
title: 유저 수준 데이터 리텐션
metadata:
  keywords:
    - Advertisers
    - Agencies
    - Ad Networks
    - SRN
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
    - Agencies
    - Ad Networks
  created_at: '2020-02-23T15:35:57Z'
  edited_at: '2026-10-14T10:25:57Z'
  id: 360006091197
  locale: ko
  section: Media source configuration
  section_id: 6551067072785
  url: https://support.appsflyer.com/hc/ko/articles/360006091197
---
> **한눈에 보기:** 요약: 리텐션 및 사용자 수준(로데이터) 사용 정책은 앱스플라이어, 관련 법률 및 SRN("**파트너**") 이용 약관에 의해 결정됩니다.

> ❗️ **주의**
>
> 앱스플라이어는 본 문서에서 정보 제공의 목적으로만 데이터를 제한하여 설명을 제공합니다.   여기에 명시된 내용은 법적 조언이 아닙니다. 정보와 편의를 위해 제공됩니다.

## 데이터 리텐션 및 삭제 의무

앱스플라이어는 앱, 파트너 및 기타 소스로부터 사용자 수준 데이터를 수신합니다.

### 광고주의 사용자 수준 데이터 가용성

일반적으로 사용자 수준의 데이터는 구독 패키지에 원시 데이터가 포함된 경우 90일 접근 기간 동안 원시 데이터 보고 도구를 통해 광고주에게 제공됩니다 (참조 <Anchor target="_blank" href="/marketers/ko/docs/data-availability-windows">데이터 가용성 창</Anchor>). 경우에 따라 로데이터 제한이 있습니다.

### 데이터 보존

AppsFlyer는 사용자 수준의 데이터를 제한된 기간 동안 보관합니다. 원시 데이터 보존 기간은 전달 방법 및 파트너 요구 사항에 따라 다릅니다. 일반적으로:

* **사용자 수준 원시 데이터** 보존 기간은 통합 유형 및 파트너 요구 사항에 따라 다릅니다.
* **집계된 데이터** 는 최대 25개월 동안 보관됩니다.

리텐션 기간이 끝나기 전에 사용자 이벤트는 사용자를 유치한 미디어 소스에 귀속됩니다. 리텐션 기간이 종료된 후 사용자 이벤트는 오가닉으로 어트리뷰트됩니다.

리텐션 기간은 다음에 따라 결정됩니다.

* <Anchor target="_blank" href="https://www.appsflyer.com/legal/processing-customer-data/">앱스플라이어 서비스 개인정보 보호정책</Anchor>
* 법에 의해 지시, 요구 또는 허용된 대로
* 다음 표에 나열된 파트너 이용 약관 및 리텐션 기간.

다음 사항을 고려하십시오.

* 액세스 기간 및 리텐션 기간이 다를 수 있습니다.
* 앱스플라이어는 경우에 따라 액세스 기간을 연장할 수 있습니다.
* 리텐션 기간은 사용자를 유치하는 파트너에 따라 다를 수 있습니다.
* 일부 사용자 수준 데이터는 <Anchor target="_blank" href="/marketers/ko/docs/about-raw-data-identifier-restrictions">제한된 미디어 소스</Anchor>에 어트리뷰트됩니다. 즉, 로데이터에는 어트리뷰션 데이터가 포함되지 않습니다. 이는 다음과 같은 경우에 발생할 수 있습니다.
  * 파트너 데이터 공유 정책
  * <Anchor target="_blank" href="/marketers/ko/docs/apply-aggregated-advanced-privacy-framework">집약형 프라이버시 강화 모드</Anchor>가 설정되어 있습니다.

#### 파트너 데이터 리텐션 기간

| SRN/파트너 | 파트너 ID(PID) | 인스톨한 다음 [x]개월 후에 데이터 삭제 |
| --- | --- | --- |
| 아마존 광고 | amazondsp\_int | 12 |
| Apple Search Ads | Apple Search Ads | 제한 없음 |
| Discord |  | 3 |
| DV360 시리즈 | dv360\_int, doubleclick\_int | 6 |
| Google Ads | googleadwords\_int (모든 채널) | 6 |
| Hotstar | hotstar\_int | 6 |
| Meta ads* | facebook\_int(모든 채널) | 6 |
| Microsoft | microsoftdisplay\_int and bingsearch\_int | 13 |
| 핀터레스트 | pinterest\_int | 6 |
| 삼성 DSP | samsungdsp\_int | 3 |
| Snapchat (<Anchor target="_blank" href="https://businesshelp.snapchat.com/en-US/article/attribution-terms">TOS</Anchor>) * | snapchat\_int | 6 |
| TikTok for Business | tiktokglobal\_int | 13 |
| X Ads(이전의 트위터) | twitter\_int | 3 |

> 📘 **참고:**
>
> SRN의 경우, 이 표의 보존 기간은 SRN이 직접 제공한 데이터에만 적용됩니다. 그들은 AppsFlyer W2A 어트리뷰션 링크를 통해 이루어진 어트리뷰션에는 적용되지 않습니다 (`googleads_int`, `metaweb_int`, `tiktokweb_int`, `snapweb_int`).

> 📄 **참고 항목**
>
> <Anchor target="_blank" href="/marketers/ko/docs/about-raw-data-identifier-restrictions">로데이터 콘텐츠 제한 – 미디어 소스 또는 유저 식별자</Anchor>

<div data-zendesk-anchors="h_01H95FY07TRAAD3K0A0TSG3RB6=%EC%A3%BC%EC%9D%98 data-retention-and-deletion-obligations=%EB%8D%B0%EC%9D%B4%ED%84%B0-%EB%A6%AC%ED%85%90%EC%85%98-%EB%B0%8F-%EC%82%AD%EC%A0%9C-%EC%9D%98%EB%AC%B4 h_01H95FY07TABPC769R7TYGY5DD=%EB%8D%B0%EC%9D%B4%ED%84%B0-%EB%A6%AC%ED%85%90%EC%85%98-%EB%B0%8F-%EC%82%AD%EC%A0%9C-%EC%9D%98%EB%AC%B4 availability-of-userlevel-data-to-advertisers=%EA%B4%91%EA%B3%A0%EC%A3%BC%EC%9D%98-%EC%82%AC%EC%9A%A9%EC%9E%90-%EC%88%98%EC%A4%80-%EB%8D%B0%EC%9D%B4%ED%84%B0-%EA%B0%80%EC%9A%A9%EC%84%B1 h_01H95FY07T2Q9QAGW5A5S6KP6J=%EA%B4%91%EA%B3%A0%EC%A3%BC%EC%9D%98-%EC%82%AC%EC%9A%A9%EC%9E%90-%EC%88%98%EC%A4%80-%EB%8D%B0%EC%9D%B4%ED%84%B0-%EA%B0%80%EC%9A%A9%EC%84%B1 data-retention=%EB%8D%B0%EC%9D%B4%ED%84%B0-%EB%B3%B4%EC%A1%B4 h_01H95FY07TXS63FVDJC2NEFXYC=%EB%8D%B0%EC%9D%B4%ED%84%B0-%EB%B3%B4%EC%A1%B4 partner-data-retention-periods=%ED%8C%8C%ED%8A%B8%EB%84%88-%EB%8D%B0%EC%9D%B4%ED%84%B0-%EB%A6%AC%ED%85%90%EC%85%98-%EA%B8%B0%EA%B0%84 h_01H95FY07TZ4N0RRJRGJ6FN2EK=%ED%8C%8C%ED%8A%B8%EB%84%88-%EB%8D%B0%EC%9D%B4%ED%84%B0-%EB%A6%AC%ED%85%90%EC%85%98-%EA%B8%B0%EA%B0%84 h_01KRKAWSHH2WFZT9Q5M0FSBBAB=%EC%B0%B8%EA%B3%A0 h_01HE7S5A2Q8GFEKD8M7C2RZ40W=%EC%B0%B8%EA%B3%A0-%ED%95%AD%EB%AA%A9" />
