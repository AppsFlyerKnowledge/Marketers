---
title: 데이터 가용성 기간
metadata:
  keywords:
    - Advertisers
    - Premium Feature
    - Marketers
    - Raw Reports
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-rona-einat
    - Marketers
    - Raw Reports
  created_at: '2022-01-04T03:33:13Z'
  edited_at: '2026-10-14T10:31:56Z'
  id: 4415473374865
  locale: ko
  section: Raw data reporting/APIs
  section_id: 6550930711057
  url: https://support.appsflyer.com/hc/ko/articles/4415473374865
---
> **한눈에 보기: 데이터의 제공 가능 여부는 리포트 유형과 정의된 사용 가능 기간에 따라 달라집니다.**

## 데이터 가용성 기간

* **사용 가능 기간**과  and **데이터 리텐션**은 각각 다른 의미를 가집니다. '데이터 리텐션'은 앱스플라이어 서버에서 로데이터를 보관하는 기간을 의미하며, 이는 ‘사용 가능 기간’보다 일반적으로 길게 설정됩니다.
* 사용 가능 기간은 귀사의 구독 패키지 유형에 따라 결정됩니다.
* 본 문서는 '데이터 락커'에는 적용되지 않습니다.

### 로데이터 사용 가능 기간 설정

Pull API와 로데이터 내보내기 페이지에서 제공되는 로데이터 한도는 사용 가능 기간에 의해 정해집니다. 제공 기간은 리포트 종류에 따라 변하며, 아래 표에서 자세히 설명하고 있습니다.

| 리포트의 이벤트 유형 | 리포트 유형 예시 | 기본적으로 제공되는 기간 |
| --- | --- | --- |
| 어트리뷰션 | 오가닉 인스톨, 논오가닉 인스톨, 리타겟팅 전환이 일어나는 행위, 언인스톨 | 최근 90일 중 60일 |
| 인앱 이벤트 | 오가닉 인앱 이벤트, 논오가닉 인앱 이벤트, 리타겟팅을 통한 인앱 이벤트 | 최근 90일 중 31일 |

### 집계 데이터의 사용 가능 기간

Pull API 및 집계 데이터 내보내기 페이지에서 제공되는 데이터는 사용 가능 기간에 따른 제한을 받습니다. 제공 기간은 리포트 종류에 따라 변하며, 아래 표에서 자세히 설명하고 있습니다.

| 리포트 | 사용가능 기간 |
| --- | --- |
| 종합 리포트 | <Anchor target="_blank" href="/marketers/ko/docs/bulletin-aggregated-ltv-data-availability">첫 앱 설치 시점부터</Anchor> 25개월(2년 1개월) 동안 유효합니다. |

> 📄 **참고 항목**
>
> * '리포트 생성 할당량'

<div data-zendesk-anchors="data-availability-windows=%EB%8D%B0%EC%9D%B4%ED%84%B0-%EA%B0%80%EC%9A%A9%EC%84%B1-%EA%B8%B0%EA%B0%84 h_01HE0FT9CNECNKYMVX9ZJJ9DNV=%EB%8D%B0%EC%9D%B4%ED%84%B0-%EA%B0%80%EC%9A%A9%EC%84%B1-%EA%B8%B0%EA%B0%84 raw-data-availability-window=%EB%A1%9C%EB%8D%B0%EC%9D%B4%ED%84%B0-%EC%82%AC%EC%9A%A9-%EA%B0%80%EB%8A%A5-%EA%B8%B0%EA%B0%84-%EC%84%A4%EC%A0%95 h_01HE0FT9CNS4N1GD1AYRBSRWPF=%EB%A1%9C%EB%8D%B0%EC%9D%B4%ED%84%B0-%EC%82%AC%EC%9A%A9-%EA%B0%80%EB%8A%A5-%EA%B8%B0%EA%B0%84-%EC%84%A4%EC%A0%95 aggregated-data-availability-window=%EC%A7%91%EA%B3%84-%EB%8D%B0%EC%9D%B4%ED%84%B0%EC%9D%98-%EC%82%AC%EC%9A%A9-%EA%B0%80%EB%8A%A5-%EA%B8%B0%EA%B0%84 h_01HE0FT9CPW91ASDH9MEW083ZH=%EC%A7%91%EA%B3%84-%EB%8D%B0%EC%9D%B4%ED%84%B0%EC%9D%98-%EC%82%AC%EC%9A%A9-%EA%B0%80%EB%8A%A5-%EA%B8%B0%EA%B0%84 h_01HE7S7VH4PC6FQAYKP6A0G4YY=%EC%B0%B8%EA%B3%A0-%ED%95%AD%EB%AA%A9" />
