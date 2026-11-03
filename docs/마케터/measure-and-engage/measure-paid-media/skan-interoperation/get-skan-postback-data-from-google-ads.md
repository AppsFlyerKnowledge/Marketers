---
title: Google Ads에서 SKAN 포스트백 데이터 가져오기
metadata:
  keywords:
    - Advertisers
    - Marketers
    - SKAdNetwork (SKAN)
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - SKAdNetwork (SKAN)
  created_at: '2021-06-28T19:34:39Z'
  edited_at: '2026-10-14T10:35:49Z'
  id: 4403215779857
  locale: ko
  section: SKAN interoperation
  section_id: 6552115163153
  url: https://support.appsflyer.com/hc/ko/articles/4403215779857
---
> **요약: 요약: Google에서 SKAdNewtork(SKAN) 앱 iOS 포스트백의 콘텐츠를 앱스플라이어와 공유할 수 있도록 설정합니다.**

## Google Ads에서 SKAN 포스트백 데이터 가져오기

다양한 애드 네트워크 파트너와 작업하는 경우 앱스플라이어 한 플랫폼에 연동하는 것이 효율적입니다. 이렇게 하면 비용과 같은 다른 지표로 강화된 모든 광고 네트워크 파트너에 대한 SKAN 성과 지표가 앱스플라이어 플랫폼을 통해 제공됩니다.

**Google Ads를 사용한 SKAN 리포트 범위**

* Google Ads는 iOS 앱 캠페인의 맥락에서 앱스플라이어를 통해 받은 집계된 iOS SKAN 포스트백을 공유합니다.
* 앱스플라이어는 포스트백을 디코딩한 다음 SKAN 대시보드 및 리포트(포스트백 로데이터 리포트 포함)를 업데이트합니다.
* <Anchor target="_blank" href="/marketers/ko/docs/self-reporting-networks-srns#ios-145-srn-attribution">iOS 14.5가 SRN 리포팅에 미치는 영향</Anchor>

**고려사항:**

iOS 포스트백을 수신하면 Google은 광고 게재 신호를 사용하여 마지막 클릭 시간을 결정합니다. 그러나 앱스플라이어는 클릭 시간을 인스톨 시간으로 간주합니다. 이로 인해 앱스플라이어와 Google 대시보드 간에 차이가 발생할 수 있습니다.

Google의 클릭 리포트 방법론과 매일 소급하는 데이터 업데이트로 인해 앱스플라이어는 이전 13일 동안의 데이터를 가져오고 인스톨 날짜 이전의 마지막 클릭 아래에 인스톨을 표시합니다.    예를 들어, 7월 1일 클릭은 8월 15일까지 앱스플라이어에 보고할 수 있습니다. 앱스플라이어는 Google에서 리포트한 클릭 날짜 아래에 이 인스톨을 표시합니다. 이는 <Anchor target="_blank" href="/marketers/ko/docs/skadnetwork-skan-solution-guide#reporting-options">리포트</Anchor>에 다음과 같은 영향을 줍니다.

* 집약형 리포트 및 대시보드는 소급하여 업데이트됩니다.
* <Anchor target="_blank" href="/marketers/ko/docs/skan-raw-data-reports">로데이터 리포트</Anchor>는 소급하여 변경되지 않습니다. 데이터(데이터 락커를 통해 제공)는 Google이 앱스플라이어에 데이터를 제공한 날짜(데이터 도착일)에 따라 폴더에 제공됩니다.

## 상호 연동 설정

Google Ads와의 상호 운용성을 설정하려면 다음 탭의 단계를 완료하십시오.

<div id="set-up-postbacks" />

<Accordion title="포스트백 설정">

**포스트백 전송 설정 방법:**

| 단계 | 작업 | 세부 사항 |
| --- | --- | --- |
| <span id="1"></span>1 | SKAN 설정 검토 | 앱스플라이어 <Anchor target="_blank" href="/marketers/ko/docs/skadnetwork-skan-solution-guide">SKAN 솔루션</Anchor>이 설치되고 사용으로 설정되어 있는지 확인합니다. 그렇게 하면 앱스플라이어 SDK가 SKAN API를 호출하고 전환 가치를 설정할 수 있습니다.<br /><br />**SKAN 설정 검토 방법**:<ol><li>앱스플라이어에서 **설정** > **SKAN 컨버전 스튜디오**로 이동합니다.</li><li>옵션(⋮)을 클릭하고 **SKAN 측정**이 설정되어 있는지 확인합니다.</li></ol>![skan-settings.png](https://files.readme.io/5a5b9b8b8a809336055340a14e49dacc16c5c0e95cda62c6dfb2ca9a11618d71-27548444964497.png)<ol><li>선호하는 측정 모드를 선택해 주세요.<br /><Anchor target="_blank" href="/marketers/ko/docs/skan-conversion-studio">SKAN 컨버전 스튜디오</Anchor>에 대해 더 보기.</li><li>정확한 이벤트 이름을 기록해 두세요. 다음 단계에서 필요하게 됩니다. **참고**! 이름은 대소문자를 구분합니다.</li></ol> |
| <span id="2"></span>2 | 앱스플라이어에서 인앱이벤트 매핑 | **인앱이벤트 매핑을 보고 설정하는 방법**:<ol><li>앱스플라이어에서 **협업** > **활성화된 연동**으로 이동합니다.</li><li>**Google Ads**를 선택합니다.</li><li>**연동** 탭에서 **파트너 활성화**가 설정되어 있는지 검증합니다. 그렇지 않은 경우 먼저 Google Ads와의 연동을 완료해야 합니다.</li><li>**인앱이벤트 포스트백 섹션**에서:<ol><li>설정되어 있지 않으면 **인앱이벤트 포스트백**을 설정합니다.</li><li>가장 좋은 방법은 현재 선택한 측정 유형과 관련된 이벤트를 매핑하는 것입니다. 참고! 수익 측정의 경우 af\_skad\_revenue를 적절한 Google 수익 이벤트에 매핑합니다.</li></ol></li><li>페이지 맨 아래로 스크롤합니다.</li><li>**연동 저장**을 클릭하세요.</li></ol> |

</Accordion>

<div id="allow-google-ads-to-share-skan-data-with-appsflyer" />

<Accordion title="Google Ads에서 SKAN 데이터를 앱스플라이어와 공유하도록 설정">

앱스플라이어 SKAN 대시보드에서 Google Ads로 인한 SKAN 인스톨을 보려면 Google Ads가 앱스플라이어와 SKAN 데이터를 공유하도록 허용해야 합니다.

**Google Ads에 SKAN 데이터를 앱스플라이어와 공유할 권한을 부여하는 방법:**

1. 다음 절차는 광고주, 에이전시 또는 둘 모두에서 수행해야 합니다.
2. 앱스플라이어에서 **협업** > **활성화된 연동**으로 이동합니다.
3. **Google Ads**를 검색하여 선택합니다.
4. **SKAN** 탭으로 이동합니다.

   <Image alt="mceclip0.png" src="https://files.readme.io/ba8d881ca8430bfdcf67a37e862ad3e31a9af522f2f877d3fba30bc2e13006a6-4404428381457.png" width="309px" />
5. **일시적으로 사용할 수 없다는 메시지가 표시**되면 대부분 광고 차단기가 활성 상태임을 의미합니다. 그렇다면 광고 차단기를 비활성화하고 페이지를 새로 고치십시오. 그렇게 할 수 없는 경우 앱스플라이어 지원팀에 문의하십시오.

   ![mceclip1.png](https://files.readme.io/e86b868f71e11ad347ff7557a793090d9d6adb8fe4df4f9010c8d770b373ac6a-4404428420497.png)
6. **Google Ads 로그인**을 클릭합니다.
   * 계정에 대한 어드민 사용자 역할을 사용하여 Google Ads에 로그인해야 합니다.
   * Google 계정이 여러 앱과 연결되어 있는 경우 한 번 로그인하면 모든 앱에 로그인한 것으로 간주됩니다. 다시 말하면, 앱별로 권한을 부여할 필요가 없습니다.
   * 앱스플라이어는 앱의 활성화 파트너 설정과 상관없이 귀하의 Google 계정이 연결된 모든 앱스플라이어 iOS 앱에 대한 데이터를 가져옵니다.
7. 사용자 인터페이스에서 지시를 따르세요.
8. 경우에 따라 앱스플라이어에 **AdWords 캠페인 관리 권한을 부여하라는 메시지가 표시될 수 있습니다.**  그렇다면 권한을 활성화해야 합니다. 걱정하지 마십시오. 캠페인 설정은 변경되지 않습니다.

   [<Image alt="GoogleManageAdWords.png" src="https://files.readme.io/bf327f152f937cdbea0b71cca72cc989aa83de6cef83677fca1f687b71aa8606-4405185007121.png" width="182px" />](https://files.readme.io/bf327f152f937cdbea0b71cca72cc989aa83de6cef83677fca1f687b71aa8606-4405185007121.png)
9. 계정 상태가 **동기화 대기 중**으로 표시되는지 확인합니다.  
   이 메시지는 Google Ads에서 데이터를 가져올 때까지 그대로 표시됩니다(최대 24시간).
10. 다음 날 02:00 UTC 이후까지 기다린 다음 상태가 활성으로 변경되는지 확인합니다 .  
    SKAN 대시보드의 데이터는 매일 08:00 UTC에 업데이트됩니다. **일러두기**! 일러두기! 고려 사항 섹션에 설명된 대로 Google은 45일 동안 소급하여 데이터를 업데이트할 수 있습니다.
11. [측정 차이](/docs/get-skan-postback-data-from-google-ads#measurement-and-timing-differences-between-appsflyer-and-google-ads)에 대해 읽어보십시오.

</Accordion>

## 추가 정보

<div id="turning-off-the-skan-integration" />

<Accordion title="SKAN 연동 해제">

Google Ads 연동을 끌 때 **파트너 활성화** 토글을 끄는 것만으로는 충분하지 않으며 SKAN 데이터 기록을 중지하려면 SKAN 연결을 별도로 제거해야 합니다.

**SKAN 연동을 끄려면:**

1. 앱스플라이어에서 **협업** > **활성화된 연동**으로 이동합니다.
2. Google Ads를 검색하여 선택합니다.
3. **SKAN** 탭으로 이동합니다.
4. 제거하려는 계정의 삭제 아이콘을 클릭하세요.

</Accordion>

<div id="measurement-and-timing-differences-between-appsflyer-and-google-ads" />

<Accordion title="앱스플라이어와 Google Ads 간의 측정 및 타이밍 차이">

| 항목 | 세부 정보 |
| --- | --- |
| <span id="earliest-data-availability"></span>데이터 가용성 시작 시점 | UTC 시간에 따라 연동을 활성화한 날짜부터 데이터를 사용할 수 있습니다. Google은 클릭 시간을 사용하기 때문에 시작 날짜 이전의 인스톨은 소급하여 표시될 수 있습니다. |
| <span id="install-date"></span>설치 날짜 | Google은 인스톨 시간을 인스톨 전 예상 마지막 클릭 시간으로 설정합니다. 광고 게재 신호를 사용하여 클릭 시간을 결정하는 것은 Google입니다.<br /><br />앱스플라이어에서 미디어소스와 대시보드를 비교할 때 다음 사항을 고려해야 합니다.<ul><li>앱스플라이어는 앱 시간대 또는 Google Ads 광고 계정 시간대를 고려하지 않습니다.</li><li>Google은 설치일로부터 45일 동안 설치를 소급하여 보고할 수 있습니다.</li><li>다른 미디어소스의 경우 포스트백 도착 시간을 사용하여 인스톨 시간을 얻어냅니다.</li></ul> |
| <span id="installs"></span>인스톨 | Google Ads API V10+에서 앱스플라이어는 did\_win=TRUE인 포스트백의 설치만 표시합니다. 따라서 앱스플라이어의 설치 수가 Google Ads 대시보드 보다 낮을 수 있습니다. |

</Accordion>

<div id="troubleshooting-and-faq" />

<Accordion title="문제 해결 및 FAQ">

| 항목 | 세부 정보 |
| --- | --- |
| <span id="sending-events-to-google-ads"></span>이벤트를 Google Ads로 보내기 | **질문**: 질문: 전환 값 측정 옵션에서 선택되지 않은 이벤트에 대해 추가 이벤트 포스트백을 Google Ads로 보내는 것이 의미가 있습니까?<br /><br />**답변**: 답변: 동의한 사용자의 경우 Google Ads의 최적화 기능을 최대화하기 위해 모든 이벤트를 보냅니다. |
| <span id="map-multiple-events-to-the-same-google-ads-event"></span>다중 이벤트를 동일한 Google Ads 이벤트에 매핑하기 | **질문**: 질문: 다중 인앱이벤트를 하나의 Google Ads 이벤트에 매핑할 수 있습니까?<br /><br />**답변**: 답변: 다중 이벤트가 하나의 Google Ads 표준 이벤트에 매핑되면 Google Ads에서 이벤트를 구분할 수 없습니다. 따라서 Google Ads는 자신이 인식하는 하나의 이벤트에 대해 최적화합니다. |
| <span id="campaign-types-supported"></span>지원되는 캠페인 유형 | **질문: 질문: 어떤 유형의 Google Ads 캠페인이 지원됩니까?**<br /><br />**답변**: A: 웹-투-앱(Web-to-app) 및 앱-투-앱(App-to-app) iOS 캠페인(검색, 비디오 등) |
| <span id="no-data-to-pull"></span>가져올 데이터가 없습니다 | **질문:** 연결 상태가 "가져올 데이터가 없습니다"로 표시되는 이유는 무엇입니까?<br /><br />**답변**: 답변: 아직 SKAN 데이터가 없거나 계정의 관리자 사용자 역할을 사용하여 Google Ads에 로그인해야 합니다. |

</Accordion>

<div id="specifications-and-limitations" />

<Accordion title="사양 및 제한 사항">

| 사양 | 설명 |
| --- | --- |
| <span id="engaged-views"></span>인게이지드 뷰 | 인게이지드 뷰는 클릭 수로 계산되며 포스트백은 클릭된 어트리뷰션에 대한 것과 마찬가지로 전송됩니다. |
| <span id="data-freshness"></span>데이터 최신성 | <ul><li>매일 01:00 UTC부터 Google Ads에서 SKAN 데이터를 수집합니다.</li><li>대시보드와 집계 데이터는 7시간 후에 업데이트됩니다.</li></ul> |
| <span id="reports-available"></span>사용 가능한 리포트 | Google Ads 데이터는 SKAN 대시보드, 집계 및 로데이터 보고서에서 사용할 수 있습니다. SKAN 리포트 옵션을 참조하십시오. |
| <span id="agencies"></span>대행사 | 에이전시에 광고주의 Google Ads 계정에서 관리자 사용자 역할이 있는 경우 에이전시는 이 문서에서 제시된 절차를 수행하여 광고주를 대신하여 SKAN 상호 운용을 활성화할 수 있습니다. 광고주는 Google Ads에도 로그인할 필요가 없습니다. 에이전시 로그인이 광고주의 계정에 표시됩니다. |

</Accordion>

> 📄 **참고 항목**
>
> * <Anchor target="_blank" href="/marketers/ko/docs/skadnetwork-skan-solution-guide">AppsFlyer SKAN 솔루션 가이드</Anchor>

<div data-zendesk-anchors="get-skan-postback-data-from-google-ads=google-ads%EC%97%90%EC%84%9C-skan-%ED%8F%AC%EC%8A%A4%ED%8A%B8%EB%B0%B1-%EB%8D%B0%EC%9D%B4%ED%84%B0-%EA%B0%80%EC%A0%B8%EC%98%A4%EA%B8%B0 h_01HCHYGCVJA3C8WJS8JH7BG0CD=google-ads%EC%97%90%EC%84%9C-skan-%ED%8F%AC%EC%8A%A4%ED%8A%B8%EB%B0%B1-%EB%8D%B0%EC%9D%B4%ED%84%B0-%EA%B0%80%EC%A0%B8%EC%98%A4%EA%B8%B0 set-up-interoperation=%EC%83%81%ED%98%B8-%EC%97%B0%EB%8F%99-%EC%84%A4%EC%A0%95 h_01HCHYGCVJY5KT4J6RQS0BJ90G=%EC%83%81%ED%98%B8-%EC%97%B0%EB%8F%99-%EC%84%A4%EC%A0%95 h_01HCHYGCVJKHF0NFJSAZMMKZ7Z=set-up-postbacks h_01HCHYGCVJEA39W87MWXF7P018=allow-google-ads-to-share-skan-data-with-appsflyer additional-information=%EC%B6%94%EA%B0%80-%EC%A0%95%EB%B3%B4 h_01HCHYGCVJTS53PCGK21BEZB2T=%EC%B6%94%EA%B0%80-%EC%A0%95%EB%B3%B4 h_01HCHYGCVJCSGKYQD3EH0GKZVS=turning-off-the-skan-integration h_01HCHYGCVJE80JX9BKE8NFMA45=measurement-and-timing-differences-between-appsflyer-and-google-ads h_01HCHYGCVJX832CCX87JHGD50W=troubleshooting-and-faq h_01HCHYGCVJ1D32JW8G9YSR27PN=specifications-and-limitations h_01HE7RMSECNDW9VD9XY6H01H55=%EC%B0%B8%EA%B3%A0-%ED%95%AD%EB%AA%A9" />
