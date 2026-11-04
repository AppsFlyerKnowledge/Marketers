---
title: 앱 시간대 설정 변경
metadata:
  keywords:
    - Time Zone
    - Existing Apps
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
  created_at: '2017-01-12T15:33:00Z'
  edited_at: '2026-10-14T10:38:53Z'
  id: 115000306786
  locale: ko
  section: Manage your apps
  section_id: 6551015977105
  url: https://support.appsflyer.com/hc/ko/articles/115000306786
---
> **한눈에 보기:** 요약: 앱 특정 시간대를 설정하거나 변경하여 앱의 데이터를 시간대나 광고 파트너와 보다 밀접하게 맞춰 보십시오. 앱스플라이어 플랫폼 내에서 데이터 리포트에 대한 시간대 변경의 영향을 찾으십시오.

<div id="why-change-the-time-zone" />

## 시간대를 바꾸는 이유는 무엇입니까?

새 앱의 기본 시간대는 UTC(UTC+0)입니다. 앱 시간대가 변경되면 플랫폼에 데이터가 표시되는 방식에 영향을 줍니다.

* **시나리오:** 시나리오: UTC가 아닌 시간대에서 작업합니다. 하지만, 사용자는 자신의 시간대나 페이스북이나 구글 같은 다른 파트너들과 함께 선택한 시간대에 맞춘 앱 데이터를 원하게 됩니다.
* 목표 목표: 앱스플라이어 및 기타 네트워크 간의 데이터 비교를 단순화합니다.
* **해결 방안:** 솔루션: 앱스플라이어 플랫폼의 시간대를 사용하는 다른 서비스 제공자와 맞추십시오. 정확한 데이라이트 절약 시간은 기본적으로 지원됩니다(설정 가능하지 않음).

**에이전시 및 광고 네트워크**:

* 에이전시: 앱 소유자가 설정한 시간대를 사용하여 데이터를 봅니다. 에이전시는 시간대를 설정할 수 없습니다.
* 광고 네트워크: 광고주가 설정한 시간대에 관계없이 항상 UTC를 사용하여 데이터를 봅니다.

<div id="changing-the-time-zone" />

## 시간대 변경

관리 사용자는 시간대 변경사항을 작성할 수 있습니다.

**앱 시간대를 변경하는 방법:**

1. 앱스플라이어의 사이드 메뉴에서 **설정** > **앱 설정을 선택합니다.**
2. **현지화** > **시간대**에서 **UTC**를 선택하십시오.
3. **설정 저장**을 클릭한 후 48시간을 기다리십시오.
4. **설정** > **앱 설정으로** 이동합니다.
5. **현지화** > **시간대**에서 시간대(도시/국가별)를 선택하십시오.
6. **설정 저장**을 클릭합니다.  
   변경은 다음 날 오전 00:00시에 적용됩니다.

<div id="example" />

> 📄 **예시**
>
> * 10월 25일 UTC 00시에 변경이 효력이 발생합니다.

시간대 변경 이후:

* 데이터 표시에 사용되는 시간대는 다음 테이블에 자세히 설명된 대로 리포트 기간 및 방법에 따라 다릅니다.
* 집약형 리포트에는 날짜에 일부 이상 항목이 있으며 시간대가 변경된 다음 날일 것입니다.

<div id="aggregate-data" />

#### 데이터 집계

<table><tbody><tr><th> </th><th colspan="3"><p>리포트 날짜 범위</p></th></tr><tr><th>리포트 메서드 </th><th>변경 <span>전에</span> 시작 및 종료 </th><th><p>변경 <span>후에</span> 시작 및 종료 </p></th><th>변경 전 및 후에 시작 및 종료</th></tr><tr><td>개요 대시보드</td><td>이전 시간대</td><td>현재 시간대</td><td><p>분할:</p><ul><li>변경 전: UTC</li><li>변경 후: 현재 시간대</li></ul></td></tr><tr><td>이벤트 및 커스텀 대시보드</td><td>UTC</td><td>현재 시간대</td><td><p>분할:</p><ul><li>변경 전: UTC</li><li>변경 후: 현재 시간대</li></ul></td></tr><tr><td><p>액티비티 대시보드</p></td><td>이전 시간대</td><td>현재 시간대</td><td>UTC</td></tr><tr><td><p>코호트, 리텐션, 피봇</p></td><td>UTC</td><td>현재 시간대(1)</td><td>UTC</td></tr><tr><td>마스터 API</td><td colspan="3"><ul><li>기본값: UTC </li><li>옵션 선택사항: <a href="./pull-api-aggregate-data" target="_blank">데이터를 가져올 때 시간대를 선택하십시오.</a>  </li></ul></td></tr><tr><td colspan="4">참고:<br/>일러두기:(1) 모든 앱은 지정된 리포트 기간 동안 동일한 앱 특정 시간대를 사용해야 합니다. 그렇지 않은 경우, 시간대는 UTC로 되돌아갑니다.</td></tr></tbody></table>

<div id="raw-data-reports" />

#### 로데이터(Raw data) 보고서

<table><tbody><tr><th> </th><th colspan="3">리포트 날짜 범위</th></tr><tr><th>리포트 메서드 </th><th>변경 <span>전에</span> 시작 및 종료</th><th>변경 <span>후에</span> 시작 및 종료</th><th>변경 전 및 후에 시작 및 종료</th></tr><tr><td>로데이터 내보내기 페이지</td><td>현재 시간대</td><td>현재 시간대</td><td>현재 시간대</td></tr><tr><td>Push API</td><td colspan="3"><p>이벤트 발생 시 선택한 시간대를 사용하여 계산된 UTC 및 앱 특정 시간대에 대한 별도의 필드.</p></td></tr><tr><td>Pull API</td><td colspan="3"><ul><li>기본값: UTC </li><li>옵션 선택사항: <a href="./pull-api-aggregate-data" target="_blank">데이터를 가져올 때 시간대 선택</a> </li></ul></td></tr><tr><td>데이터 락커</td><td colspan="3">영향 없음 - 날짜 필드는 UTC 날짜</td></tr></tbody></table>

<div data-zendesk-anchors="why-change-the-time-zone=%EC%8B%9C%EA%B0%84%EB%8C%80%EB%A5%BC-%EB%B0%94%EA%BE%B8%EB%8A%94-%EC%9D%B4%EC%9C%A0%EB%8A%94-%EB%AC%B4%EC%97%87%EC%9E%85%EB%8B%88%EA%B9%8C h_01HJR69P6Z44SZA5A684H82PNV=%EC%8B%9C%EA%B0%84%EB%8C%80%EB%A5%BC-%EB%B0%94%EA%BE%B8%EB%8A%94-%EC%9D%B4%EC%9C%A0%EB%8A%94-%EB%AC%B4%EC%97%87%EC%9E%85%EB%8B%88%EA%B9%8C changing-the-time-zone=%EC%8B%9C%EA%B0%84%EB%8C%80-%EB%B3%80%EA%B2%BD h_01HJR69P6ZWJQ47FQY2HATAAE3=%EC%8B%9C%EA%B0%84%EB%8C%80-%EB%B3%80%EA%B2%BD h_01HJR69P6Z6B0Q6E6996WXVZ0N=%EC%98%88%EC%8B%9C aggregate-data=%EB%8D%B0%EC%9D%B4%ED%84%B0-%EC%A7%91%EA%B3%84 h_01HJR69P6ZY8JJBCBSDZKN75N6=%EB%8D%B0%EC%9D%B4%ED%84%B0-%EC%A7%91%EA%B3%84 raw-data-reports=%EB%A1%9C%EB%8D%B0%EC%9D%B4%ED%84%B0raw-data-%EB%B3%B4%EA%B3%A0%EC%84%9C h_01HJR69P6ZDXXK8ZTKK3E774VJ=%EB%A1%9C%EB%8D%B0%EC%9D%B4%ED%84%B0raw-data-%EB%B3%B4%EA%B3%A0%EC%84%9C" />
