---
title: IP 차단
metadata:
  keywords:
    - IP masking
    - Advertisers
    - Marketers
    - Platform essentials
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-negri
    - Marketers
    - Platform essentials
  created_at: '2016-05-23T12:59:55Z'
  edited_at: '2026-10-14T10:37:29Z'
  id: 208879066
  locale: ko
  section: Preserve user privacy
  section_id: 6551440878097
  url: https://support.appsflyer.com/hc/ko/articles/208879066
---
> **한눈에 보기:**

<div id="ip-masking" />

## IP 차단

<div id="note" />

> 📘 **참고사항**
>
> * AEM 데이터 공유는 <Anchor target="_blank" href="/marketers/ko/docs/meta-ads-aggregate-event-measurement-aem-for-ios#aem-데이터-공유">IP 마스킹이 켜져 있는 경우</Anchor> 서버 간 및 SDK 이벤트 모두에 대해 지원되지 않습니다. 즉, 데이터는 메타 광고와 공유되지 않습니다.

<div id="ip-masking-in-raw-data-reports" />

<div id="example" />

> 📄 **예시**
>
> 앱 설치
>
>
>
> | 설치 날짜 | 사용자 ID | IP 주소 |
> | --- | --- | --- |
> | 1월 2일 | User\_A | 192.0.2.1 |
> | 1월 18일 | User\_B | 192.0.2.33 |
> | 1월 14일 | User\_C | 203.0.113.1 |
>
>
>
> | 날짜 |  | 로데이터 리포트 |
> | --- | --- | --- |
> | 1월 1일 | 꺼짐 | 유저 A |
> | 1월 2일 | 켜짐 | User\_A 192.0.2.1 |
> | 1월 18일 | 켜짐 | User\_A 192.0.2.1  <br />User\_B 1.1.1.1 |
> | 1월 18일 | 꺼짐 | User\_A 192.0.2.1  <br />User\_B 1.1.1.1 |
> | 1월 15일 | 꺼짐 | User\_A 192.0.2.1  <br />User\_B 1.1.1.1  <br />User\_C 203.0.113.1 |


1. **<span id="turn-on-ip-masking"></span><span id="enabling-ip-masking"></span>앱스플라이어의 사이드 메뉴에서**  설정 > 앱 설정을 선택합니다.


<Image align="center" alt="ip_masking.png" src="https://files.readme.io/e52f8bd698191f0b1ac08e595e539f15bda59567ed51ddda32a0d80db3bdf23c-360001962938.png" />

<div data-zendesk-anchors="ip-masking=ip-%EC%B0%A8%EB%8B%A8 h_01HA91HHADCTT7QS2K79TJEY2C=ip-%EC%B0%A8%EB%8B%A8 h_01HA92HF3ZYR2NBTXQ1S2AHCAA=%EC%B0%B8%EA%B3%A0%EC%82%AC%ED%95%AD h_01HA91HHAD7BCXRZW6AD9NRDBN=%EC%98%88%EC%8B%9C h_01HA91HHAEM220CE8805GFQYKR=enabling-ip-masking ip-masking-in-raw-data-reports=%EC%98%88%EC%8B%9C h_01HA91HHAE14D6ES1ERNK93VY9=%EC%98%88%EC%8B%9C" />
