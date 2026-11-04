---
title: 앱스플라이어와 타사 플랫폼 간의 수치 차이
metadata:
  keywords:
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2023-10-16T08:59:17Z'
  edited_at: '2026-10-14T10:30:31Z'
  id: 19384888063249
  locale: ko
  section: Integrate 3rd-party platforms
  section_id: 6551084534545
  url: https://support.appsflyer.com/hc/ko/articles/19384888063249
---
> **한눈에 보기:** 앱스플라이어와 타사 플랫폼 간의 어트리뷰션 결과가 다른 원인을 확인해 보세요.

<div id="overview" />

## 개요

미디어 소스의 데이터 공유 정책에 따라, 모든 유저 수준 <Anchor target="_blank" href="/marketers/ko/docs/about-raw-data-identifier-restrictions#미디어-소스-제한">데이터가 제3자 플랫폼</Anchor> (예: 애널리틱스 플랫폼 및 마케팅 플랫폼)<Anchor target="_blank" href="/marketers/ko/docs/about-raw-data-identifier-restrictions#미디어-소스-제한">과 공유되는 것은</Anchor> 아닙니다. 이러한 이유로, 제3자 플랫폼에 표시되는 데이터와 앱스플라이어의 데이터 간에 어트리뷰션 분석에 차이가 발생할 수 있습니다.

<div id="note" />

> 📘 **참고사항**
>
> 앱스플라이어 플랫폼의 집계 및 분석 데이터는 제한 없이 사용할 수 있습니다.

<div id="postback-restrictions-on-third-party-platforms" />

## 타사 플랫폼에 대한 포스트백 제한

타사 플랫폼으로 포스트백을 보낼 때 다양한 수준의 미디어소스 제한이 있습니다. 포스트백은 전혀 전송되지 않거나, 어트리뷰션 없이 전송되거나, 아무 제한 없이 전송될 수 있습니다.

<div id="types-of-postback-restrictions" />

#### 포스트백 제한의 유형

<div id="no-postbacks-sent" />

<Accordion title="포스트백이 전송되지 않습니다">

<Anchor target="_blank" href="/marketers/ko/docs/about-raw-data-identifier-restrictions#미디어-소스-제한">이 표</Anchor>에서 자세히 설명된 대로, 미디어소스에 의해 제한된 로데이터 이벤트에 대한 포스트백은 타사 플랫폼으로 전송되지 않습니다.  즉, 타사 플랫폼은 이러한 이벤트의 포스트백을 받지 않으며, 이는 앱스플라이어에 비해 해당 플랫폼에서의 어트리뷰션이 적다는 것을 의미합니다.

</Accordion>

<div id="postbacks-with-no-attribution" />

<Accordion title="포스트백이 어트리뷰션 없이 전송됩니다">

제한된 로데이터 이벤트 이외의 이벤트인 경우, 아래 나열된 광고 네트워크에서는 광고주가 타사 플랫폼에 포스트백을 공유할 때 미디어소스를 수정해야 합니다. 앱스플라이어는 **원본 미디어소스를 오가닉 어트리뷰션으로 대체하여** 이를 수행합니다. 즉, 타사 플랫폼으로 전송된 이러한 이벤트의 포스트백에는 미디어소스에 대한 어트리뷰션이 포함되지 않으며, 이는 앱스플라이어에 비해 해당 플랫폼에서의 어트리뷰션이 적다는 것을 의미합니다.

* Amazon
* Meta Ads
* 핀터레스트
* 스냅챗(<Anchor target="_blank" href="https://businesshelp.snapchat.com/en-US/article/attribution-terms">TOS</Anchor>)
* X Ads
* Bing
* 야후 (Oath: 광고 플랫폼 \/ Yahoo Gemini)

<div id="note-1" />

> 📘 **참고사항**
>
> 메타 광고의 경우, 포스트백 동작은 광고주가 AMM(Advanced Mobile Measurement) 약관에 동의했는지 여부에 따라 달라집니다:
>
> * **AMM 미지원:** 포스트백은 <Anchor target="_blank" href="/marketers/ko/docs/appsflyer-attribution-model#install-referrer-android-only">인스톨 리퍼러를 통해 어트리뷰션된</Anchor> 인스톨에 대해서만 전송됩니다. 포스트백에는 어트리뷰션 데이터가 포함되지 않습니다.
> * **AMM 승인됨:** <Anchor target="_blank" href="/marketers/ko/docs/appsflyer-attribution-model#어트리뷰션-메서드">모든 어트리뷰션 방식에</Anchor> 의해 기록된 인스톨 건에 대해 포스트백이 전송됩니다. 그러나 포스트백 데이터에는 어트리뷰션 데이터가 포함되어 있지 않으므로, 모든 포스트백은 어트리뷰션이 지정되지 않은(오가닉) 데이터로 제3자 플랫폼에 전송됩니다.

</Accordion>

<div id="regular-postbacks" />

<Accordion title="정기적인 포스트백">

다른 모든 제한되지 않은 이벤트 또는 수정되지 않은 미디어소스는 정기적인 포스트백으로 표시되어 전송됩니다. 여기에는 집약형 이벤트가 포함됩니다.

</Accordion>

<table><colgroup><col/><col/><col/><col/><col/><col/></colgroup><thead><tr><th colspan="6">포스트백 제한 사항은 앱스플라이어와 연동된 모든 제3자 플랫폼에 적용되며, 여기에는 다음이 포함됩니다:</th></tr></thead><tbody><tr><td><span id="airship"></span>Airship</td><td>Amplitude</td><td>Batch</td><td>Braze</td><td>CleverTap</td><td>클라우드</td></tr><tr><td><span id="convertro"></span>Convertro</td><td>deltaDNA</td><td>Eulerian</td><td>GameAnalytics</td><td>IBM UBX</td><td>Insider</td></tr><tr><td><span id="itunes"></span>iTunes</td><td>Kahuna</td><td>Leanplum</td><td>Liquid</td><td>Localytics</td><td>Luna labs</td></tr><tr><td><span id="Medialyzer"></span>Medialyzer</td><td>믹스패널</td><td>MoEngage</td><td>mParticle</td><td>원시그널</td><td>Rockerbox</td></tr><tr><td><span id="salesforce"></span>Salesforce</td><td>마케팅</td><td>모바일푸시</td><td>세그먼트</td><td>스폿 이펙트</td><td>Swrve</td></tr><tr><td><span id="tapcart"></span>탭카트</td><td>Tealium</td><td>웹인게이지(WebEngage)</td><td>Winclap 분석</td><td>Google Analytics 4</td><td> </td></tr></tbody></table>

<div id="examples-of-discrepancies" />

## 수치 차이 예시

<div id="example-1" />

<Accordion title="믹스패널에 대한 로데이터 제한">

<Tabs>
<Tab title="AMM 미지원">

<div id="note-2" />

> 📄 **예시 1**
>
> 광고주가 Meta 광고를 사용하여 광고를 게재합니다. 또한 사용자가 웹 사이트에서 어떻게 행동하고 상호 작용하는지 더 잘 이해하기 위해 Mixpanel을 사용하고 있습니다. 광고주는 지난달 Meta 광고로 인한 설치 수를 확인합니다.
>
>
>
> | 앱스플라이어에서 | Mixpanel에서 |
> | --- | --- |
> | 광고주는 Meta 광고로 인한 100개의 설치를 확인합니다.<br /><br />인스톨 중 30개는 gp\_referrer 파라미터를 사용하여 어트리뷰션되었습니다. 이러한 이벤트는 제한되지 않으며 로데이터 보고서에 표시됩니다. | 광고주는 Meta 광고로 인해 발생한 30개의 설치만 볼 수 있습니다.<br /><br />믹스패널은 70개의 제한된 이벤트에 대해서는 포스트백을 수신하지 않습니다. `gp_referrer` 파라미터를 통해 유입된 것으로 어트리뷰션된 30건의 인스톨에 대한 포스트백은 ‘오가닉’으로 전송됩니다. |

</Tab>

<Tab title="AMM 허용됨">

<div id="note-3" />

> 📄 **예시 1**
>
> 광고주는 메타 광고를 통해 광고를 게재하며, AMM 약관에 동의했습니다. 또한 사용자가 웹 사이트에서 어떻게 행동하고 상호 작용하는지 더 잘 이해하기 위해 Mixpanel을 사용하고 있습니다. 광고주는 지난달 Meta 광고로 인한 설치 수를 확인합니다.
>
>
>
> | 앱스플라이어에서 | Mixpanel에서 |
> | --- | --- |
> | 광고주는 Meta 광고로 인한 100개의 설치를 확인합니다.<br /><br />인스톨 로데이터 리포트에는 gp\_referrer 메서드를 통해 귀속된 인스톨 건뿐만 아니라 총 100건의 인스톨 건이 모두 포함됩니다. | 광고주는 Meta 광고로 인한 100개의 설치를 확인합니다.<br /><br />AMM이 승인되었기 때문에, 믹스패널은 100건의 인스톨 건 모두에 대한 포스트백을 수신합니다. 하지만 포스트백 데이터에는 어트리뷰션 데이터가 포함되어 있지 않아, 모든 인스톨이 자연 유입으로 표시됩니다. |

</Tab>
</Tabs>

</Accordion>

<div id="example-2" />

<Accordion title="MoEngage의 로데이터 제한 사항">

<div id="note-4" />

> 📄 **예시 2**
>
> 광고주가 Pinterest를 사용하여 광고를 게재합니다. 또한 MoEngage와 협력하여 고객 참여에 대한 인사이트를 얻고 있습니다. 광고주는 지난달에 Pinterest에 기여한 '위시리스트에 추가' 이벤트 수를 확인합니다.
>
>
>
> | 앱스플라이어에서 | On MoEngage |
> | --- | --- |
> | 광고주는 Pinterest에 기여한 97개의 '위시리스트에 추가' 이벤트를 확인합니다. | 광고주는 Pinterest에 기여한 '위시리스트에 추가' 이벤트를 볼 수 없습니다. MoEngage는 Pinterest에서 클릭스루 및 뷰스루 이벤트 포스트백을 받지 않았는데, 이는 제한된 이벤트이기 때문입니다. |

</Accordion>

<div id="example-3" />

<Accordion title="비행선에 대한 제한 사항">

<div id="note-5" />

> 📄 **예시 3**
>
> 광고주가 Bing을 사용하여 광고를 게재합니다. 또한 모바일 앱에서 사용자 여정을 최적화하기 위해 Airship과 협력하고 있습니다. 광고주는 지난 달에 Bing에 기인한 구매 이벤트 수를 확인합니다.
>
>
>
> | 앱스플라이어에서 | 비행선에서 |
> | --- | --- |
> | 광고주는 Bing에 기인한 35개의 구매 이벤트를 확인합니다. | 광고주는 오가닉 소스에서 84개의 구매 이벤트를 확인합니다. 그 중 35개는 Bing에서 왔지만 이러한 구매 이벤트가 유기적으로 표시되기 때문에 알 수 없습니다. |

</Accordion>

<div id="note-6" />

> 📄 **참고 항목**
>
> <Anchor target="_blank" href="/marketers/ko/docs/about-raw-data-identifier-restrictions#자주-묻는-질문">로데이터 콘텐츠 제한</Anchor>에 대한 FAQ.

<div data-zendesk-anchors="Overview=%EA%B0%9C%EC%9A%94 h_01HCVTKD7ZH991A8JF7XCNNE91=%EA%B0%9C%EC%9A%94 h_01HE05K6FD3GFGWHDFAZ9R4GJ9=%EC%B0%B8%EA%B3%A0%EC%82%AC%ED%95%AD postback-restrictions=%ED%83%80%EC%82%AC-%ED%94%8C%EB%9E%AB%ED%8F%BC%EC%97%90-%EB%8C%80%ED%95%9C-%ED%8F%AC%EC%8A%A4%ED%8A%B8%EB%B0%B1-%EC%A0%9C%ED%95%9C h_01HDDR9JG5303R38QCAB2ZF6CW=%ED%83%80%EC%82%AC-%ED%94%8C%EB%9E%AB%ED%8F%BC%EC%97%90-%EB%8C%80%ED%95%9C-%ED%8F%AC%EC%8A%A4%ED%8A%B8%EB%B0%B1-%EC%A0%9C%ED%95%9C types-of-postback-restrictions=%ED%8F%AC%EC%8A%A4%ED%8A%B8%EB%B0%B1-%EC%A0%9C%ED%95%9C%EC%9D%98-%EC%9C%A0%ED%98%95 h_01HE05EXEFJF6SGYTKZ78FPP7Z=%ED%8F%AC%EC%8A%A4%ED%8A%B8%EB%B0%B1-%EC%A0%9C%ED%95%9C%EC%9D%98-%EC%9C%A0%ED%98%95 h_01HDDRVF8J36N3J9AB3YRD8TZP=no-postbacks-sent h_01HDDRVF8JP2FWCA7PH58TZDBY=postbacks-with-no-attribution h_01H9JCS8H0TQBPBVWS8KCJT296=%EC%B0%B8%EA%B3%A0%EC%82%AC%ED%95%AD-1 h_01HDDRVF8J9QRWN8MCKXRV0J3M=regular-postbacks examples=%EC%88%98%EC%B9%98-%EC%B0%A8%EC%9D%B4-%EC%98%88%EC%8B%9C h_01HCW4HS35ZTAEWPXB9JKCR725=%EC%88%98%EC%B9%98-%EC%B0%A8%EC%9D%B4-%EC%98%88%EC%8B%9C h_01HDDS499QJTX5RJY6CR98BDFB=example-1 01H8BXG7YBP4SSQGQ04N9VXWE9=%EC%98%88%EC%8B%9C-1 h_01KQZ1FQASP81EX4JGBQPKK38Q=%EC%98%88%EC%8B%9C-1 h_01HDDS499QG48D1AFR3Z59J1HP=example-2 h_01HD3Y812D0ABR3XYCGP9W42J7=%EC%98%88%EC%8B%9C-2 h_01KQZ0Q440XSG96Q3W65RYVYAG=example-3 h_01HD3YVXFJZN8MY4RWP3A8MMS8=%EC%98%88%EC%8B%9C-3 h_01HDXK7W3JD3FM3ST6S459F3QS=%EC%B0%B8%EA%B3%A0-%ED%95%AD%EB%AA%A9" />
