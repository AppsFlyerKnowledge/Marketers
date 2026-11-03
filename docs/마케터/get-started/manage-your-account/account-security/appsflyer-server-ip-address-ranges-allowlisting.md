---
title: 앱스플라이어 서버 IP 주소 범위(allowlisting)
metadata:
  keywords:
    - whitelisting
    - AppsFlyer
    - IPs
    - Advertisers
    - Ad Networks
    - Marketers
    - Platform essentials
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-negri
    - Marketers
    - Platform essentials
    - Ad Networks
  created_at: '2015-12-24T11:30:11Z'
  edited_at: '2026-10-14T10:34:32Z'
  id: 207447093
  locale: ko
  section: Account security
  section_id: 6551173202065
  url: https://support.appsflyer.com/hc/ko/articles/207447093
---
> **한눈에 보기:** 요약: 나가는 API 요청에 사용되는 앱스플라이어 IP 주소입니다.

## 앱스플라이어 서버 IP 주소 범위

나열된 IP 주소는 앱스플라이어에서 앱스플라이어를 사용하기 위해 제어됩니다. 이 목록은 당사의 능력 및 운영 요구사항에 따라 수시로 변경됩니다. 우리는 이 목록을 적게 수정하기 위해 모든 노력을 기울입니다.

앱스플라이어 API는 광고주와 파트너에게 어트리뷰션 및 리포트 서비스를 제공합니다. 상기 서비스에는 다음이 포함됩니다.

* 포스트백 보내기
* 푸시 API 메시지 보내기

방화벽 및 프록시 서버와 같은 네트워크 경계 기기를 사용하는 경우 보안 팀에 이 <Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vTzJqwOhIkSV0Mbnu4DZOx2eWKAd8OPRUNCu2REjz9z9qonI5ZDlHl6kGd1KAXopaDbf1MzuNXjeVj-/pub?gid=0&single=true&output=csv">IP 허용 목록</Anchor>에 나열된 앱스플라이어 IP 주소를 허용하도록 요청해야 합니다.

2022년 2월 16일부터 레거시 IP 주소는 더는 사용하지 않으며 허용 목록에서 삭제했습니다.

허용 목록에 기재된 주소는 다음 CIDR 차단을 사용합니다.

* [45.92.116.0/22]
* [194.28.46.0/23]

### 잠재 고객 업로딩

방화벽 및 프록시 서버와 같은 네트워크 경계 디바이스를 사용하는 경우 보안팀에 [잠재 고객용 IP 허용 목록](https://support.appsflyer.com/hc/article_attachments/16888953497617)에 나열된 앱스플라이어 IP 주소를 허용하도록 요청해야 합니다.

<Anchor target="_blank" href="/marketers/ko/docs/audiences-guide">잠재고객</Anchor>에 대해 자세히 알아보세요.

### Pull API 및 서버 간 통신(S2S)

Pull API 및 S2S는 본 기사에 기재된 주소의 영향을 받지 않습니다. 그러나 *\*.appsflyer.com* 도메인이 허용 목록에 있고 어떤 식으로든 차단되지 않았는지 확인해야 합니다.

<div data-zendesk-anchors="appsflyer-server-ip-address-ranges=%EC%95%B1%EC%8A%A4%ED%94%8C%EB%9D%BC%EC%9D%B4%EC%96%B4-%EC%84%9C%EB%B2%84-ip-%EC%A3%BC%EC%86%8C-%EB%B2%94%EC%9C%84 uploading-audiences=%EC%9E%A0%EC%9E%AC-%EA%B3%A0%EA%B0%9D-%EC%97%85%EB%A1%9C%EB%94%A9 pull-api-and-servertoserver-s2s=pull-api-%EB%B0%8F-%EC%84%9C%EB%B2%84-%EA%B0%84-%ED%86%B5%EC%8B%A0s2s" />
