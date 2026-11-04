---
title: 재설치
metadata:
  keywords:
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-moran-davida
    - Marketers
    - Mobile Attribution
  created_at: '2022-10-27T07:37:21Z'
  edited_at: '2026-10-14T10:39:36Z'
  id: 10164066030737
  locale: ko
  section: Attribution concepts
  section_id: 6551394235409
  url: https://support.appsflyer.com/hc/ko/articles/10164066030737
---
> **간단히 보기**: 재설치는 유저가 앱을 인스톨하고 삭제한 후, 다시 인스톨하는 경우에 발생합니다. 재설치는 논오가닉 재설치, 오가닉 재설치 또는 리어트리뷰션(리타게팅)과 같은 어트리뷰션 유형 중 하나가 됩니다. 재설치하면 유저가 제거했다가 다시 설치할 때 중복 청구되는 것을 방지할 수 있습니다.

<div id="what-is-a-reinstall" />

## 재설치란?

재설치는 앱 유저가 앱을 삭제한 다음 <Anchor target="_blank" href="/marketers/ko/docs/set-up-re-attribution-window#re-attribution-window">리어트리뷰션 윈도우</Anchor> 중에 앱을 다시 설치할 때 발생합니다.

재설치는 리타게팅 캠페인(리어트리뷰션), 오가닉 소스 또는 논오가닉 소스에서 발생할 수 있습니다.

오가닉 소스 또는 논오가닉 소스에서 발생하고 <Anchor target="_blank" href="/marketers/ko/docs/set-up-re-attribution-window#re-attribution-window">리어트리뷰션 윈도우</Anchor>에 있는 재설치를 재설치라고 합니다.

리타게팅 캠페인에서 발생하는 재설치는 리어트리뷰션이라고 합니다.

재설치 및 인앱이벤트가 어트리뷰트되는 방식에서 차이점이 있습니다.

<Anchor target="_blank" href="/marketers/ko/docs/set-up-re-attribution-window#re-attribution-window">리어트리뷰션 윈도우</Anchor> 외부에서 설치가 발생하는 경우 재설치를 <Anchor target="_blank" href="/marketers/ko/docs/set-up-re-attribution-window#new-install">신규 설치</Anchor>라고 합니다. 신규 설치는 미디어소스(또는 인게이지먼트가 기록되지 않은 경우 오가닉)로 어트리뷰트되고 새로운 리어트리뷰션 윈도우가 시작됩니다.

아래 표에서는 앱스플라이어가 다른 재설치라고 부르는 것을 보여줍니다.

| 소스 재설치 | 리어트리뷰션 윈도우가 유효한가요? | 유저가 다시 설치하기 전에 리타게팅 캠페인과 상호 작용했습니까? | 유저가 다시 설치하기 전에 UA 리타게팅 캠페인과 상호 작용했습니까? | 호칭 |
| --- | --- | --- | --- | --- |
| 리타게팅 캠페인에서 | 예 | 예 | 아니요 | 리어트리뷰션 |
| 오가닉 또는 논오가닉 소스에서 | 예 | 아니요 | 예 또는 아니요 | 재설치 |
| 오가닉 또는 논오가닉 소스에서 | 아니요 | 아니요 | 예 또는 아니요 | 신규 인스톨 (New install) |

<div id="why-are-reinstalls-important" />

## 재설치가 중요한 이유

유저가 앱을 다시 사용하고 캠페인이 작동하고 있다는 좋은 징후일 뿐만 아니라, 리어트리뷰션 윈도우 내에 앱을 삭제했다가 다시 설치하는 유저에게 요금이 여러 번 부과되지 않도록 해주는 적절한 재설치 어트리뷰션이 중요합니다

<div id="reinstall-flow-and-outcome" />

## 재설치 흐름 및 성과

<div id="reinstall" />

<Accordion title="재설치">

최초 앱 설치 이후 유저는 앱을 삭제했지만, 리어트리뷰션 윈도우 중에 재설치합니다. 재설치는 오가닉 또는 UA 캠페인에서 발생할 수 있습니다( 예시 참조).

그러면 다음이 일어납니다:

* 인스톨은 어트리뷰션 되지 않습니다 - 이것은 대시보드에도 데이터에도 표시되지 않습니다.
* 어떤 미디어 소스에도 아무런 인스톨 포스트백이 전송되지 않습니다.
* 인앱이벤트가 어트리뷰트되는 방식에 대한 자세한 내용은 [인앱이벤트](/docs/measure-reinstalls#인앱-이벤트)를 참조하세요.

</Accordion>

<div id="reattribution" />

<Accordion title="리어트리뷰션">

첫 번째 앱 설치 후 유저는 앱을 삭제한 다음 리타게팅 캠페인으로 인게이지하여 <Anchor target="_blank" href="/marketers/ko/docs/set-up-re-attribution-window#re-attribution-window">리어트리뷰션 윈도우</Anchor> 중에 재설치합니다.  

그러면 다음이 일어납니다:

* 인스톨은 개요 대시보드의 리타게팅 및 통합 보기에서 리타게팅 미디어소스로 어트리뷰트됩니다.
  * 유저 인입 보기에는 리어트리뷰션이 포함되지 않습니다.
* 다음의 모든 인앱이벤트는 리타게팅 미디어소스로 어트리뷰트됩니다(자세한 내용은 [인앱이벤트](/docs/measure-reinstalls#인앱-이벤트) 참조).
* 인스톨 포스트백이 리타겟팅 미디어 소스로 전송됩니다.

리타겟팅 어트리뷰션 관련 더 자세한 정보는 <Anchor target="_blank" href="/marketers/ko/docs/retargeting-attribution-guide">여기</Anchor>를 클릭하십시오.

</Accordion>

<div id="postreinstall-events-attribution-state" />

<div id="note" />

<div id="post-reinstall-in-app-events" />

## 인앱 이벤트

### 개요

[![](https://files.readme.io/2376efb764026f9cb3c585e8145ae6cf361c3e887c8478ec82709caea63feb1a-10485524792337.jpg)](https://files.readme.io/2376efb764026f9cb3c585e8145ae6cf361c3e887c8478ec82709caea63feb1a-10485524792337.jpg)

재설치 후 유저가 수행한 인앱이벤트는 재설치 후 이벤트 어트리뷰션 상태에 따라 어트리뷰트된 오가닉, 어트리뷰트된 않은 논오가닉 또는 어트리뷰트되지 않은 오가닉입니다(아래 참조).

인앱이벤트의 예로는 앱을 다시 설치한 다음 인앱 구매를 하는 유저를 들 수 있습니다.

#### 인앱이벤트와 인앱이벤트가 어트리뷰트되는 방식

<table><tbody><tr><th>재설치 후 이벤트 어트리뷰션 상태</th><th>재설치 후</th><th>리어트리뷰션 후</th></tr><tr><td><strong>오가닉 인앱으로 어트리뷰트됨</strong></td><td>어트리뷰트되지 않은 오가닉</td><td>리타겟팅</td></tr><tr><td> <strong>첫 번째 설치에 어트리뷰트됨</strong><span>(1)</span> </td><td>먼저 미디어소스를 설치함</td><td>리타게팅 <span>(2)</span> </td></tr><tr><td colspan="3"><p><span>(1) 아래 제한 사항 참조</span></p><p>(2) 기본 소스 필드에서. 첫 번째 설치 미디어소스는 보조 소스 필드에 나열됩니다(로데이터 형태로만 볼 수 있음).</p></td></tr></tbody></table>

<div id="unattributed-organic-inapps" />

<Accordion title="어트리뷰트되지 않은 오가닉 인앱">

재설치

* 모든 인앱이벤트는 대시보드에 따라 오가닉으로 계산되거나 완전히 무시됩니다.
* 인앱이벤트는 conversion\_type과 campaign\_type이 '알 수 없는' 상태로 리포트됩니다.
* 데이터를 집계하는 데 사용되는 날짜는 이벤트에 따라 다릅니다.
  * 대부분의 SDK 시작 인앱이벤트의 경우 재설치 날짜가 아니라 앱 다운로드 날짜가 데이터를 집계하는 데 사용됩니다.
  * SDK 커넥터에서 전송한 광고 수익 이벤트(af\_ad\_revenue)의 경우 리인스톨 날짜가 데이터를 집계하는 데 사용됩니다.

리어트리뷰션

* 모든 인앱이벤트는 리타게팅 미디어소스로 어트리뷰트됩니다.

</Accordion>

<div id="attributed-to-the-first-install" />

<Accordion title="첫 번째 설치에 어트리뷰트됨">

> 🚧 **필수 조건**
>
> 활성화해야 합니다. CSM에 연락하여 논의하십시오.

#### 목적

광고주가 유저의 인게이지 방식을 더 잘 파악할 수 있도록 합니다. UA 캠페인과 리타게팅 광고가 인앱이벤트를 오가닉이 아닌 원본 소스에 어트리뷰트함으로써 얼마나 효과적인지 보여줍니다.

#### 재설치

* 재설치에서 생성된 모든 인앱이벤트는 원래 설치 (1)에 어트리뷰트됩니다.

#### 리어트리뷰션

* 모든 인앱이벤트는 기본 소스의 리타게팅 광고와 보조 소스의 원래 설치에 어트리뷰트됩니다. (2) (2)

(1) 아래 제한 사항을 참조하세요.

(2) 로데이터로만 볼 수 있습니다.

<div id="note-1" />

> 📘 **참고사항**
>
> 이러한 숫자 중 일부는 이제 논오가닉 미디어소스에 어트리뷰트될 수 있으므로, 대시보드의 오가닉 KPI 데이터는 재설치 후 이벤트 어트리뷰션이 **첫 번째 설치에 어트리뷰트됨**으로 설정된 상태에서 더 낮은 값을 표시할 수 있습니다.

</Accordion>

<div id="examples" />

<Accordion title="예시">

<div id="confirm-inapps-are-attributed-to-the-original-install" />

<div id="examples-for-first-install-mode-attribution" />

#### **첫 번째 설치에 어트리뷰트됨**이 활성화된 경우.

**예시 1**

유저가 앱을 설치하고(0일 차) $10에 구매한 다음 앱을 삭제합니다.

다음 날(1일 차), 유저가 앱을 재설치하고 $5를 구매합니다.

![Reinstall_1.jpg](https://files.readme.io/7e8eccb3a6873b42a1d8503c0f027386728adb2eecbe457451d2e37c0a7b6774-10225445609873.jpg)

유저가 재설치하기 전에 이미 구매했으므로 고유 유저 수가 추가되지는 않습니다.

| 미디어 소스 | 사용자 | Af\_purchase:<br /><br />고유 유저<br /><br />0일 | Af\_purchase:<br /><br />고유 유저<br /><br />1일 차(누적) | 수익<br /><br />0일 | 수익<br /><br />1일 차(누적) |
| --- | --- | --- | --- | --- | --- |
| Media\_source\_A | 1 | 1 | 1 | $10 | 15달러 |

| Appsflyer\_id | 기기 식별자 | 미디어 소스 | 이벤트 이름 | 이벤트 날짜 |
| --- | --- | --- | --- | --- |
| 111 | XXX | media\_source\_A | 인스톨 | 0일 차 |
| 111 | XXX | media\_source\_A | af\_구매 | 0일 차 |
| 222 | XXX | organic | 재설치 (Reinstall) | 1일 차 |
| 222 | XXX | media\_source\_A | af\_구매 | 1일 차 |

**예시 2**

유저가 앱을 설치하고(0일 차) 구매한 다음 앱을 삭제합니다.

다음 날(1일 차) 유저가 UA 캠페인에서 앱을 재설치하고 구매합니다.

| 미디어 소스 | 이벤트 이름 | 이벤트 날짜 | 리인스톨 어트리뷰션 | 인앱 이벤트 어트리뷰션 |
| --- | --- | --- | --- | --- |
| media\_source\_A | 인스톨 | 0일 차 | media\_source\_A |  |
| media\_source\_A | af\_구매 | 0일 차 |  | media\_source\_A |
| media\_source\_B | 재설치 (Reinstall) | 1일 차 | media\_source\_B |  |
| media\_source\_B | af\_구매 | 1일 차 |  | media\_source\_A |

</Accordion>

<div id="limitations" />

<Accordion title="제한 사항">

* 설치 및 재설치 모두에 대해 디바이스 식별자(예: IDFA 또는 GAID)를 앱과 공유하는 데 동의한 유저만 원래 설치에 어트리뷰트된 인앱이벤트를 갖게 됩니다.
  * 첫 번째 설치와 재설치에서 디바이스 식별자가 일치해야 합니다.
* 리인스톨은 마지막으로 기록된 인스톨의<Anchor target="_blank" href="/marketers/ko/docs/retargeting-attribution-guide#reengagement-rules-and-windows">리어트리뷰션 기간 내에</Anchor>  이루어져야 합니다 .
* 각 설치 및 재설치는 여전히 고유한 appsflyer\_id가이 있습니다.
* 대시보드는 설치 또는 재설치 후 인앱이벤트를 구분하지 않습니다.
  * 로데이터를 통해 이를 볼 수 있습니다.

</Accordion>

<div id="how-does-the-data-appear-in-the-appsflyer-dashboards" />

## 앱스플라이어 대시보드에 데이터가 표시되는 방식

<table><tbody><tr><th colspan="2"> </th><th>논오가닉 재설치</th><th>오가닉 재설치  </th><th>리어트리뷰션</th></tr><tr><td colspan="2">재설치 자체</td><td>보이지 않음</td><td>보이지 않음</td><td><span>미디어소스 리타게팅\*</span></td></tr><tr><td rowspan="2">향후 인앱이벤트 어트리뷰션</td><td>재설치 후 이벤트가 <strong>오가닉 인앱으로 어트리뷰션됨</strong>으로 설정됨 </td><td>어트리뷰트되지 않은 오가닉</td><td>어트리뷰트되지 않은 오가닉</td><td><span>미디어소스 리타게팅</span></td></tr><tr><td> <strong>첫 번째 설치에 어트리뷰트됨</strong>으로 설정된 재설치 후 이벤트 </td><td>첫 번째 미디어 소스</td><td>첫 번째 미디어 소스</td><td>리타겟팅 캠페인</td></tr><tr><td colspan="5">\*개요 대시보드에서만 가능합니다.</td></tr></tbody></table>


<div id="prerequisites" />

<div id="reinstalls-raw-data-reports" />

> 🚧 **필수 조건**
>
> 활성화해야 합니다. 이와 관련하여 논의하려면 귀사의 CSM에 문의하세요.

* <Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vQtlerXtCVImurv-JyuG7JMPvLN6p2w79pmbMNBx6WBnLwnYq5bUqXiUuoy2l_UTzEjIr8UkDdclRxf/pub?output=csv">예제 리포트를 CSV 파일로 리인스톨</Anchor>

<div id="how-the-install-and-in-app-events-are-attributed" />

#### 설치 및 인앱이벤트의 어트리뷰션 방식

<table><tbody><tr><th colspan="2"> </th><th>논오가닉 재설치</th><th>오가닉 재설치  </th><th>리어트리뷰션</th><th>install-non-organic</th><th>오가닉 설치</th></tr><tr><td colspan="2">어트리뷰트 대상  </td><td>UA 캠페인</td><td>오가닉</td><td>리타겟팅 캠페인</td><td>UA 캠페인</td><td>오가닉</td></tr><tr><td rowspan="2">향후 이벤트 어트리뷰션</td><td>재설치 후 이벤트가 <strong>오가닉 인앱으로 어트리뷰션됨</strong>으로 설정됨 </td><td>오가닉</td><td>오가닉</td><td>리타겟팅 캠페인</td><td>UA 캠페인</td><td>오가닉</td></tr><tr><td> <strong>첫 번째 설치에 어트리뷰트됨</strong>으로 설정된 재설치 후 이벤트 </td><td>최초 인스톨 (First install)</td><td>최초 인스톨 (First install)</td><td>리타겟팅 캠페인</td><td>UA 캠페인</td><td>오가닉</td></tr></tbody></table>

<div id="availability-of-reinstall-reports" />

### 재설치 리포트의 가용성

* 재설치 로데이터 리포트는 다음 표에 자세히 설명된 전달 도구를 사용해 확인할 수 있습니다.
* 리포트는 동일한 구조를 가지며 다음과 같은 설치 리포트와 유사한 방식으로 채워집니다.
  * **미디어소스** 필드는 재설치 또는 오가닉을 가져온 미디어소스를 사용하여 채워집니다.
  * 설치 시간 설치 시간: 재설치 후 첫 번째 앱이 열리는 시간을 의미하는 재설치 시간으로 해석합니다.
  * 이벤트 이름 재설치

| 리포트 보고서 전달 방법 | 논오가닉 재설치 | 오가닉 재설치 |
| --- | --- | --- |
| 데이터 내보내기 | ✓ | ✓ |
| <Anchor target="_blank" href="/marketers/ko/docs/pull-api-aggregate-data">Pull API</Anchor> | ✓ | ✓ |
| <Anchor target="_blank" href="/marketers/ko/docs/data-locker-for-marketers">데이터 락커</Anchor> | ✓ | ✓ |
| Push API | ✓ | ✓ |

<div data-zendesk-anchors="what-is-a-reinstall=%EC%9E%AC%EC%84%A4%EC%B9%98%EB%9E%80 01H7SZVZPGHBQ7VM8TMWRD3CE4=%EC%9E%AC%EC%84%A4%EC%B9%98%EB%9E%80 why-are-reinstalls-important=%EC%9E%AC%EC%84%A4%EC%B9%98%EA%B0%80-%EC%A4%91%EC%9A%94%ED%95%9C-%EC%9D%B4%EC%9C%A0 01H7SZVZPG6T2AW9B3EMT29AQQ=%EC%9E%AC%EC%84%A4%EC%B9%98%EA%B0%80-%EC%A4%91%EC%9A%94%ED%95%9C-%EC%9D%B4%EC%9C%A0 reinstall-flow-and-outcome=%EC%9E%AC%EC%84%A4%EC%B9%98-%ED%9D%90%EB%A6%84-%EB%B0%8F-%EC%84%B1%EA%B3%BC 01H7SZVZPGVQCNCQ7TCZMYM33T=%EC%9E%AC%EC%84%A4%EC%B9%98-%ED%9D%90%EB%A6%84-%EB%B0%8F-%EC%84%B1%EA%B3%BC 01H7SZVZPGCDP3GRK1BWZ04MR6=reinstall 01H7SZVZPG8WNTK30YXNZ44VTS=reattribution inapp-events=%EC%9D%B8%EC%95%B1-%EC%9D%B4%EB%B2%A4%ED%8A%B8 01H7SZVZPGBYRWZGAZRT36EFGH=%EC%9D%B8%EC%95%B1-%EC%9D%B4%EB%B2%A4%ED%8A%B8 overview=%EA%B0%9C%EC%9A%94 01H7SZVZPGK7X1NXW467CZP1KJ=%EA%B0%9C%EC%9A%94 inapp-events-and-how-they-are-attributed=%EC%9D%B8%EC%95%B1%EC%9D%B4%EB%B2%A4%ED%8A%B8%EC%99%80-%EC%9D%B8%EC%95%B1%EC%9D%B4%EB%B2%A4%ED%8A%B8%EA%B0%80-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%ED%8A%B8%EB%90%98%EB%8A%94-%EB%B0%A9%EC%8B%9D 01H7SZVZPHW7E5WV9C643BG6YB=%EC%9D%B8%EC%95%B1%EC%9D%B4%EB%B2%A4%ED%8A%B8%EC%99%80-%EC%9D%B8%EC%95%B1%EC%9D%B4%EB%B2%A4%ED%8A%B8%EA%B0%80-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%ED%8A%B8%EB%90%98%EB%8A%94-%EB%B0%A9%EC%8B%9D 01H7SZVZPH4AE1PZK8V5JG6C6X=unattributed-organic-inapps 01H7SZVZPH7KPM7T42GHZ7N69S=attributed-to-the-first-install 01H7SZVZPHBQ7E3R107EB2KXES=%ED%95%84%EC%88%98-%EC%A1%B0%EA%B1%B4 purpose=%EB%AA%A9%EC%A0%81 01H7SZVZPHXBX6J2APBXS30CPX=%EB%AA%A9%EC%A0%81 reinstall::7f2d499b=%EC%9E%AC%EC%84%A4%EC%B9%98 01H7SZVZPHRJ9WPW3TCYECK50W=%EC%9E%AC%EC%84%A4%EC%B9%98 h_01J3FZXYG37R0QFB7BPH9F64GM=%EC%B0%B8%EA%B3%A0%EC%82%AC%ED%95%AD reattribution::bbb1aabb=%EB%A6%AC%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98 01H7SZVZPHZFY9ZDEQYP967C2D=%EB%A6%AC%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98 01H7SZVZPH5YGSMPGW7NPKXJAF=%EC%B0%B8%EA%B3%A0%EC%82%AC%ED%95%AD 01H7SZVZPHF3R44DTHCD9QHPR8=examples with-attributed-to-the-first-install-enabled=%EC%B2%AB-%EB%B2%88%EC%A7%B8-%EC%84%A4%EC%B9%98%EC%97%90-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%ED%8A%B8%EB%90%A8%EC%9D%B4-%ED%99%9C%EC%84%B1%ED%99%94%EB%90%9C-%EA%B2%BD%EC%9A%B0 01H7SZVZPHH3DS9J4VRD70VTX6=%EC%B2%AB-%EB%B2%88%EC%A7%B8-%EC%84%A4%EC%B9%98%EC%97%90-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%ED%8A%B8%EB%90%A8%EC%9D%B4-%ED%99%9C%EC%84%B1%ED%99%94%EB%90%9C-%EA%B2%BD%EC%9A%B0 01H7SZVZPH8MSBQ92XWFK0HWGQ=limitations how-does-the-data-appear-in-the-appsflyer-dashboards=%EC%95%B1%EC%8A%A4%ED%94%8C%EB%9D%BC%EC%9D%B4%EC%96%B4-%EB%8C%80%EC%8B%9C%EB%B3%B4%EB%93%9C%EC%97%90-%EB%8D%B0%EC%9D%B4%ED%84%B0%EA%B0%80-%ED%91%9C%EC%8B%9C%EB%90%98%EB%8A%94-%EB%B0%A9%EC%8B%9D 01H7SZVZPHHQS4NHEDATD7ZP9V=%EC%95%B1%EC%8A%A4%ED%94%8C%EB%9D%BC%EC%9D%B4%EC%96%B4-%EB%8C%80%EC%8B%9C%EB%B3%B4%EB%93%9C%EC%97%90-%EB%8D%B0%EC%9D%B4%ED%84%B0%EA%B0%80-%ED%91%9C%EC%8B%9C%EB%90%98%EB%8A%94-%EB%B0%A9%EC%8B%9D reinstalls-raw-data-reports=%ED%95%84%EC%88%98-%EC%A1%B0%EA%B1%B4-1 01H7SZVZPHPWN8REBQ5CWVFNJT=%ED%95%84%EC%88%98-%EC%A1%B0%EA%B1%B4-1 01H7SZVZPHCVDPDDYD6HHNFMMK=%ED%95%84%EC%88%98-%EC%A1%B0%EA%B1%B4-1 how-the-install-and-inapp-events-are-attributed=%EC%84%A4%EC%B9%98-%EB%B0%8F-%EC%9D%B8%EC%95%B1%EC%9D%B4%EB%B2%A4%ED%8A%B8%EC%9D%98-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%EB%B0%A9%EC%8B%9D 01H7SZVZPHQT8XS3ZBA4W682GB=%EC%84%A4%EC%B9%98-%EB%B0%8F-%EC%9D%B8%EC%95%B1%EC%9D%B4%EB%B2%A4%ED%8A%B8%EC%9D%98-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%EB%B0%A9%EC%8B%9D availability-of-reinstall-reports=%EC%9E%AC%EC%84%A4%EC%B9%98-%EB%A6%AC%ED%8F%AC%ED%8A%B8%EC%9D%98-%EA%B0%80%EC%9A%A9%EC%84%B1 01H7SZVZPH6NY7FMG9YHDBB95R=%EC%9E%AC%EC%84%A4%EC%B9%98-%EB%A6%AC%ED%8F%AC%ED%8A%B8%EC%9D%98-%EA%B0%80%EC%9A%A9%EC%84%B1" />
