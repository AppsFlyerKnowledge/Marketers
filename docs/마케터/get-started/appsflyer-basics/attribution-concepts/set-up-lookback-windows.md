---
title: 룩백 윈도우 설정하기
metadata:
  keywords:
    - Advertisers
    - look back
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-moran-davida
    - Marketers
    - Mobile Attribution
  created_at: '2016-03-07T09:27:55Z'
  edited_at: '2026-10-14T10:39:52Z'
  id: 208338403
  locale: ko
  section: Attribution concepts
  section_id: 6551394235409
  url: https://support.appsflyer.com/hc/ko/articles/208338403
---
> **한눈에 보기:** 미디어소스와의 협의에 따라 클릭-쓰루 및 뷰-쓰루 룩백 기간을 사용자 정의합니다.

## 룩백 윈도우

맞춤 설정 가능한 어트리뷰션 룩백 윈도우를 사용하면 미디어소스와의 협의에 따라 어트리뷰션 기간을 사용자 정의할 수 있습니다.

권한 조건에 따라 미디어소스당 어트리뷰션 룩백 윈도우를 설정하여 앱스플라이어 어트리뷰트를 설정합니다.

**룩백 윈도우 유형**:

* **클릭 룩백 윈도우**: 광고가 클릭된 이후, 앱 설치가 해당 광고에 어트리뷰션될 수 있는 최대 기간 룩백 기간 이후에 발생하는 인스톨은 오가닉으로 간주됩니다.
* **적극적 클릭 룩백 윈도우:** 적극적 클릭 이후 인스톨이 적극적 클릭으로 어트리뷰션될 수 있는 최대 기간입니다.  룩백 기간 이후에 발생하는 인스톨은 오가닉으로 간주됩니다.
* **적극적 조회 룩백 윈도우:** 적극적 조회 이후, 앱 설치가 해당 적극적 조회에 어트리뷰션될 수 있는 최대 기간.  룩백 기간 이후에 발생하는 인스톨은 오가닉으로 간주됩니다.
* **뷰-쓰루 룩백 윈도우**: 광고가 조회된 이후, 앱 설치가 해당 광고에 어트리뷰션될 수 있는 최대 기간 룩백 기간 이후에 발생하는 인스톨은 오가닉으로 간주됩니다.

#### 어트리뷰션 유형당 어트리뷰션 룩백 윈도우 설정 기능

<table><thead><tr><th rowspan="2"><p><strong>어트리뷰션 유형</strong></p></th><th rowspan="2"><p><strong>어트리뷰션 메서드</strong></p></th><th colspan="2"><strong>룩백 윈도우</strong></th></tr><tr><th><strong>범위</strong></th><th><strong>기본값</strong></th></tr></thead><tbody><tr><td rowspan="3"><p>클릭-쓰루</p><p>(모든 미디어 소스)</p></td><td>리퍼러, ID 매칭</td><td>1-30일 또는<br/>1-23시간</td><td>7일</td></tr><tr><td>확률적 모델링(모바일)</td><td><a href="./appsflyer-attribution-model#probabilistic-modeling" target="_blank">적응형</a></td><td>최대 24시간</td></tr><tr><td>확률적 모델링 (CTV, PC 및 콘솔 - 단일 플랫폼 링크)</td><td>최대 7일 (<code>af_lookback_window</code> 링크 파라미터에 설정)</td><td>7일</td></tr><tr><td rowspan="2"><p>적극적 클릭-쓰루</p><p>(비 SRN <a href="./about-enriched-engagement-types#allowed-networks" target="_blank">미디어소스</a> 선택\*)</p></td><td>ID 매칭</td><td>1–7 일 또는 1-23 시간</td><td>2일</td></tr><tr><td>확률적 모델링(모바일)</td><td><a href="./appsflyer-attribution-model#probabilistic-modeling" target="_blank">적응형</a></td><td>최대 24시간</td></tr><tr><td rowspan="2"><p>적극적 뷰-쓰루</p><p>(비 SRN <a href="./about-enriched-engagement-types#allowed-networks" target="_blank">미디어소스</a> 선택\*)</p></td><td>ID 매칭</td><td>1–7 일 또는 1-23 시간</td><td>2일</td></tr><tr><td>확률적 모델링(모바일)</td><td><a href="./appsflyer-attribution-model#probabilistic-modeling" target="_blank">적응형</a></td><td>최대 24시간</td></tr><tr><td rowspan="4"><p>뷰-쓰루</p><p>(선택한 <a href="./measure-view-through-engagements#view-vta-partner-list" target="_blank">미디어소스</a>)</p></td><td>ID 매칭</td><td><p>1-24시간</p><p>[2021년 12월 15일까지의 상한은 7일]</p></td><td>24시간</td></tr><tr><td>확률적 모델링(모바일)</td><td><a href="./appsflyer-attribution-model#probabilistic-modeling" target="_blank">적응형</a></td><td>최대 24시간</td></tr><tr><td>확률적 모델링 (CTV, PC 및 콘솔 - 단일 플랫폼 링크)</td><td>최대 7일 (<code>af_lookback_window</code> 링크 파라미터에 설정)</td><td>24시간</td></tr><tr><td>확률적 모델링 (CTV, PC 및 콘솔 - <a href="./set-up-cross-platform-links-for-multi-device-campaigns#traits-and-limitations" target="_blank">크로스 플랫폼 원링크 어트리뷰션 링크</a>)</td><td>최대 72시간 (<code>af_xplatform_vt_lookback</code> 링크 파라미터에 설정)</td><td>24시간</td></tr></tbody></table>

*`engaged_click` 및 `engaged_view`의 룩백 윈도우는 비 SRN 네트워크에서만 설정할 수 있습니다. SRN의 경우, `engaged_click` 및 `engaged_view` 파라미터는 클릭수와 동일한 룩백 윈도우를 공유하므로, `engaged_click`인스톨 클릭-쓰루 어트리뷰션 룩백engaged\_click 슬라이더에 의해 설정됩니다.

### 확률적 모델링 룩백 윈도우

어트리뷰션 정확도를 유지하는 데 사용되는 확률적 모델링 룩백 기간에는 다음과 같은 특성이 있습니다.

* 클릭수와 노출수 모두에 적용
* 최대 24시간의 적응 기간이 있음
* 어트리뷰션 링크에서 보낸 룩백 지속 기간 설정을 무시합니다.
* 결정적 모델에서 사용하는 기간보다 지속 기간이 짧습니다.

더 자세한 내용은 <Anchor target="_blank" href="/marketers/ko/docs/appsflyer-attribution-model#probabilistic-modeling">앱스플라이어 확률적 모델링 메서드</Anchor>를 참조하십시오.

## 룩백 윈도우 설정하기

다음은 SRN(Self Reporting Network) 및 어트리뷰션 링크에 대한 룩백 윈도우 설정 절차를 설명합니다.

<Tabs>
<Tab title="SRN 룩백 윈도우">

### SRN(Self Reporting Network)의 어트리뷰션 룩백 윈도우

> 🚧 **중요!**
>
> 각 SRN은 자체의 기본 룩백을 가지고 있습니다. 수치 차이를 최소화하기 위해, 앱스플라이어 상의 룩백 윈도우를 SRN의 값과 일치시키는 것을 추천합니다. 값을 변경하면 수치 차이가 발생할 수 있습니다. 더 자세한 내용은 [SRN 수치 차이 예시](#시나리오-및-예시)를 참고하십시오.

1. 앱스플라이어에서의 사이드 메뉴에서 **협업** > **파트너 마켓플레이스**를 선택하세요.
2. SRN을 검색하고 선택합니다. - <Anchor target="_blank" href="/marketers/ko/docs/self-reporting-networks-srns#앱스플라이어와-통합된-srn">지원되는 SRN 목록</Anchor> 참고
3. 기본 설정으로 뷰-쓰루 어트리뷰션이 활성화되어 있습니다.
4. **연동** 탭에서, 스크롤을 내려 **클릭-쓰루 어트리뷰션**과 **뷰-쓰루 어트리뷰션** 설정을 찾습니다.
5. 슬라이더를 사용하여 어트리뷰션 기간을 설정합니다.

아래에 정리된, 각 SRN의 룩백 기간을 참조하십시오.

| SRN | 기본 클릭-쓰루 룩백 윈도우(일) | 기본 뷰-쓰루 룩백 윈도우(시간) |
| --- | --- | --- |
| Google | 30 | 24 |
| Meta Ads | 7 | 24 |
| 스냅챗 | 28 | 24 |
| X Ads | 14 | 24 |
| Apple Search Ads | 30 | 24 |
| Oath (YahooGemini) | 7 | 24 |

</Tab>

<Tab title="비 SRN 룩백 윈도우">

<div id="attribution-lookback-window-with-attribution-links" />

<div id="h_01JKWVQB6TTA24VAZ9WVJMGY4X" />

### 클릭-쓰루 및 뷰-쓰루를 위한 비 SRN 어트리뷰션 룩백 윈도우

1. 앱스플라이어의 사이드 메뉴에서 **협업** > **활성화된 연동**을 선택하세요.
2. 파트너를 검색하고 선택합니다.
3. 기본 설정으로 뷰-쓰루 어트리뷰션이 활성화되어 있습니다.
4. **어트리뷰션 링크** 탭을 클릭합니다.
5. 기간을 일자 단위 또는 시간 단위로 설정할지 선택합니다.
6. **클릭쓰루 어트리뷰션**(`af_click_lookback` 파라미터) 및 **뷰쓰루 어트리뷰션**(`af_viewthrough_lookback` 파라미터) 아래의 슬라이더를 사용하여 어트리뷰션 윈도우를 설정합니다.  
   선택한 시간이 자동으로 어트리뷰션 링크에 반영됩니다.
7. 캠페인 관련 파라미터를 선택합니다. (예, 캠페인 이름, 애드 세트 등)
8. 링크를 복사하여 저장해둡니다 - 애드 네트워크에 제공해야 하는 링크입니다.

### 클릭-쓰루 및 뷰-쓰루를 위한 비 SRN 어트리뷰션 룩백 윈도우

1. 앱스플라이어의 사이드 메뉴에서 **협업** > **활성화된 연동**을 선택하세요.
2. 파트너를 검색하고 선택합니다.
3. 연동 탭에서 **인스톨 적극적 클릭-쓰루 룩백 윈도우** 슬라이더 또는 **인스톨 적극적 조회 룩백 윈도우** 슬라이더로 스크롤을 내립니다.
4. 슬라이더를 사용하여 룩백 윈도우를 설정합니다.

> 👍 **팁**
>
> * 룩백 기간 설정에 대한 팁과 요령이 궁금하신가요? 앱스플라이어 학습 포털에서 제공하는 <Anchor target="_blank" href="https://elevate.appsflyer.com/learn/course/7768/play/18612/attribution-102-tips-and-tricks">짧고 유익한 강의 코스</Anchor>를 확인해 보세요.
> * 어떤 경우에 어트리뷰션 기간을 시간 단위로 설정해야하는지 알아보려면 [여기](/docs/set-up-lookback-windows#lookback-in-hours-for-flash-campaigns)를 클릭하십시오.

<div id="lookback-window-in-onelink" />

### 원링크(OneLink™)의 룩백 윈도우

원링크에서도 룩백 윈도우를 설정할 수 있습니다.

1. <Anchor target="_blank" href="/marketers/ko/docs/create-a-onelink-template">원링크를 설정합니다.</Anchor>
2. <Anchor target="_blank" href="/marketers/ko/docs/create-deep-linking-and-redirection-links-for-your-campaigns-with-onelink#캠페인을-위한-원링크-링크-생성하기">커스텀 어트리뷰션 링크를 생성합니다.</Anchor>
3. **고급** 메뉴 아래, **사용자 지정 룩백 윈도우** 토글을 켜고, 룩백 윈도우를 설정합니다.

</Tab>
</Tabs>

## 최초 앱 실행 분포도

아래는 인게이지먼트 일로부터 최초 앱 실행 시점의 분포를 보여주는 그래프입니다.

[![](https://files.readme.io/8fdc8b23ba9a1b78bdea7bacad99d6ed5e59d57de32f395cb2fd9e5451483962-360001666918.png)](https://files.readme.io/8fdc8b23ba9a1b78bdea7bacad99d6ed5e59d57de32f395cb2fd9e5451483962-360001666918.png)

이 그래프를 통해 룩백 윈도우의 기능과 더불어 앱 설치 사용자 수를 더 잘 이해할 수 있습니다.

앱을 실행한 사용자의 97%를 약간 상회하는 대다수는 광고에 참여한지 7일 이내에 앱을 실행합니다. 남은 2%는 7일 차와 룩백 윈도우의 종료(30일 차) 사이에 앱을 실행합니다.

실제로, 앱을 실행한 사용자의 약 62%는 광고에 참여한지 15분 이내에 앱을 실행합니다. 72%의 사용자는 처음 한시간 이내에 앱을 실행합니다.

## 시나리오 및 예시

아래는 룩백 윈도우 사용 관련 가능한 시나리오와 예시 목록입니다.

<div id="srn-discrepancy-srn-lookback-longer-than-appsflyer" />

<Accordion title="SRN 수치 차이: SRN 룩백이 앱스플라이어보다 더 길 때">

X Ads에서 캠페인을 설정하고 클릭쓰루 룩백 기간을 7일로 설정합니다. 반면 X Ads의 기본 룩백 기간은 14일입니다.

[![srn-discrepancy-srn-lookback-larger-than-appsflyer.png](https://files.readme.io/a0a60df2c1b142c9b2871c2083168ef5d88922001f1e5ab6a95c7ffbdcc178a5-360001586637.png)](https://files.readme.io/a0a60df2c1b142c9b2871c2083168ef5d88922001f1e5ab6a95c7ffbdcc178a5-360001586637.png)

</Accordion>

<div id="srn-lookback-smaller-than-appsflyer" />

<Accordion title="SRN 룩백이 앱스플라이어보다 더 짧을 때">

X Ads에서 캠페인을 설정하고 클릭쓰루 룩백 기간을 28일로 설정합니다. 반면 X Ads의 기본 룩백 기간은 14일입니다.

[![srn-lookback-smaller-than-appsflyer.png](https://files.readme.io/9111035d903bfb35be2ab4bff27c16e527b401b12225b71316a7e36ed68ffb0c-360001586697.png)](https://files.readme.io/9111035d903bfb35be2ab4bff27c16e527b401b12225b71316a7e36ed68ffb0c-360001586697.png)

</Accordion>

<div id="attribution-link-without-a-lookback-window-parameter" />

<Accordion title="룩백 윈도우 파라미터가 없는 어트리뷰션 링크">

룩백 윈도우 파라미터가 없는 어트리뷰션 링크도 사용할 수 있습니다. 이런 경우, 앱스플라이어는 클릭 7일 룩백 윈도우, 노출 1일 룩백 윈도우를 기본으로 합니다.

</Accordion>

<div id="lookback-in-hours-for-flash-campaigns" />

<Accordion title="플래시 캠페인(flash campaign)을 위한 시간 단위 룩백">

플래시 캠페인은 짧은 프로모션 기간 동안, 사용자들이 앱을 가능한 빠르게 설치하도록 유도하는 캠페인입니다.

SuperShopping이라는 이커머스 앱은 플래시 캠페인을 운영합니다. 이 캠페인을 통해 한 시간 이내에 앱을 설치한 사용자는 특별 할인 혜택을 받습니다.

SuperShopping의 마케팅 책임자 Johnny는 어트리뷰션 링크를 생성하고 룩백 윈도우를 1시간으로 설정했습니다. 이를 통해 Johnny는 얼마나 많은 사용자가 캠페인에 반응하는지 알 수 있습니다.

또한 이를 통해, 앱의 개발자도 플래시 캠페인을 통해 유입된 사용자를 구별할 수 있고, 캠페인이 광고한 특별 할인을 전달할 수 있습니다.

</Accordion>

> 👍 **팁**
>
> 룩백 기간과 어트리뷰션에 대한 팁과 요령을 알고 싶으신가요? <Anchor target="_blank" href="https://elevate.appsflyer.com/learn/course/7768/play/18612/attribution-102-tips-and-tricks">앱스플라이어 학습 포털에서 제공하는 짧고 유익한 강의 코스</Anchor>를 확인해 보세요.

<div data-zendesk-anchors="lookback-windows=%EB%A3%A9%EB%B0%B1-%EC%9C%88%EB%8F%84%EC%9A%B0 h_01HGFQVP7QZACJ3EGSWEP4HPFV=%EB%A3%A9%EB%B0%B1-%EC%9C%88%EB%8F%84%EC%9A%B0 configurable-lookback-windows-per-attribution-type=%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%EC%9C%A0%ED%98%95%EB%8B%B9-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%EB%A3%A9%EB%B0%B1-%EC%9C%88%EB%8F%84%EC%9A%B0-%EC%84%A4%EC%A0%95-%EA%B8%B0%EB%8A%A5 h_01HGFQVP7QM0J507CFQ753YS5X=%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%EC%9C%A0%ED%98%95%EB%8B%B9-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%EB%A3%A9%EB%B0%B1-%EC%9C%88%EB%8F%84%EC%9A%B0-%EC%84%A4%EC%A0%95-%EA%B8%B0%EB%8A%A5 probabilistic-modeling-lookback-window=%ED%99%95%EB%A5%A0%EC%A0%81-%EB%AA%A8%EB%8D%B8%EB%A7%81-%EB%A3%A9%EB%B0%B1-%EC%9C%88%EB%8F%84%EC%9A%B0 h_01JKWV7S7J5B4YA84VGEB478TT=%ED%99%95%EB%A5%A0%EC%A0%81-%EB%AA%A8%EB%8D%B8%EB%A7%81-%EB%A3%A9%EB%B0%B1-%EC%9C%88%EB%8F%84%EC%9A%B0 lookback-window-setup=%EB%A3%A9%EB%B0%B1-%EC%9C%88%EB%8F%84%EC%9A%B0-%EC%84%A4%EC%A0%95%ED%95%98%EA%B8%B0 h_01HGFQVP7QCCN7CHRCAFSNJVHA=%EB%A3%A9%EB%B0%B1-%EC%9C%88%EB%8F%84%EC%9A%B0-%EC%84%A4%EC%A0%95%ED%95%98%EA%B8%B0 attribution-lookback-window-for-srns=srnself-reporting-network%EC%9D%98-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%EB%A3%A9%EB%B0%B1-%EC%9C%88%EB%8F%84%EC%9A%B0 h_01HGFQVP7QP61C2K0P7C7YM56Z=srnself-reporting-network%EC%9D%98-%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%EB%A3%A9%EB%B0%B1-%EC%9C%88%EB%8F%84%EC%9A%B0 h_01HGFQVP7QXTQKGVQJEZ0NEW0M=%EC%A4%91%EC%9A%94 h_01HGFQVP7QDBFP85A9DJFZE38S=attribution-lookback-window-with-attribution-links h_01HGFQVP7Q69H5621GXMYZ441N=%ED%8C%81-1 lookback-window-in-onelink%E2%84%A2=lookback-window-in-onelink h_01HGFQVP7QSJEE8D7TCWZMSXGK=lookback-window-in-onelink distribution-of-first-app-launches=%EC%B5%9C%EC%B4%88-%EC%95%B1-%EC%8B%A4%ED%96%89-%EB%B6%84%ED%8F%AC%EB%8F%84 h_01HGFQVP7Q96827N7Q9Q0363SR=%EC%B5%9C%EC%B4%88-%EC%95%B1-%EC%8B%A4%ED%96%89-%EB%B6%84%ED%8F%AC%EB%8F%84 scenarios-and-examples=%EC%8B%9C%EB%82%98%EB%A6%AC%EC%98%A4-%EB%B0%8F-%EC%98%88%EC%8B%9C h_01HGFQVP7Q02NS8MXF7WKYQ8V1=%EC%8B%9C%EB%82%98%EB%A6%AC%EC%98%A4-%EB%B0%8F-%EC%98%88%EC%8B%9C h_01HGFQVP7Q1CYRAHAKY3WK8BK0=srn-discrepancy-srn-lookback-longer-than-appsflyer h_01HGFQVP7QAWDP40H89YBN66GV=srn-lookback-smaller-than-appsflyer h_01HGFQVP7QYE3V2DKW7T4171MX=attribution-link-without-a-lookback-window-parameter h_01HGFQVP7Q7CXSK5G8A0937H5Z=lookback-in-hours-for-flash-campaigns h_01HGFQVP7QM3R973QS99661VPG=%ED%8C%81-1" />
