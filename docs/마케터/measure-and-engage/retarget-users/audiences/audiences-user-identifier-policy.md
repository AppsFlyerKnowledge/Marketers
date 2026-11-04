---
title: 오디언스 유저 식별자 정책
metadata:
  keywords:
    - IDFA
    - Audiences
    - Advertisers
    - Premium Feature
    - Marketers
    - Audience Segmentation
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-neama-benhabib
    - Marketers
    - Audience Segmentation
  created_at: '2020-12-23T15:39:55Z'
  edited_at: '2026-10-14T10:39:17Z'
  id: 360016791118
  locale: ko
  section: Audiences
  section_id: 6551336428945
  url: https://support.appsflyer.com/hc/ko/articles/360016791118
---
> **한눈에 보기:** 오디언스가 파트너와 공유하는 데이터에 대한 **계정 수준** 제어를 위해 귀사의 유저 식별자 정책을 구성하세요.

<div id="about" />

## 소개

<Anchor target="_blank" href="/marketers/ko/docs/audiences-partner-connections">오디언스를 정의한 후, 앱스플라이어 오디언스가 해당 오디언스 구성원의 식별자를 귀사의</Anchor> 파트너에게 전송합니다. 이를 통해 귀사의 광고를 오직 이 유저에게만 제공할 수 있습니다.

iOS 14.5의 개인정보 보호 요구 사항 및 기타 사용자 개인정보 보호 고려 사항 준수를 위해, 오디언스는 파트너와 어떤 식별자를 공유할지 완전한 제어할 수 있는 기능을 제공합니다:

* 계정 수준에서
* 파트너 연결 수준에서

이 문서 는 계정 수준에서 귀사의 유저 식별자 정책을 관리하는 프로세스를 설명합니다. 파트너 연결 수준에서 공유되는 식별자 관리를 위한 자세한 내용은 오디언스 가이드의 <Anchor target="_blank" href="/marketers/ko/docs/audiences-guide#manage-connections">관리 연결</Anchor> 섹션을 참조하세요.

<div id="user-identifiers" />

## 유저 식별자

이 섹션은 파트너와 공유할 수 있는 식별자를 설명합니다.

<div id="shared-identifiers" />

<Accordion title="공유 식별자">

기본적으로 오디언스가 파트너와 공유하는 식별자는 다음과 같습니다:

* **iOS:** IDFA (iOS 14.5 이상에서, 유저가 이 식별자의 공유를 허용하는 경우에만 사용 가능)
* 안드로이드: GAID

일부 광고 파트너는 다음 식별자도 지원합니다:

* 이메일(해시됨)
* 전화번호 (해시됨)
* OAID 및 IMEI (둘 다 구글 플레이가 아닌 안드로이드 스토어에만 해당)

특정 추가 식별자는 귀사의 내부 프로세스(예: CRM 또는 분석)에 유용할 수 있습니다:

* CUID
* IDFV (iOS에만 해당)

추가 정보(특정 식별자를 앱스플라이어에서 사용하기 위한 요구 사항 포함)는 아래의 식별자 표를 참조하세요.

</Accordion>

<div id="identifiers-table" />

<Accordion title="식별자 표">

<table><thead><tr><th>식별자</th><th>운영 체제</th><th>기본적으로 공유되나요?</th><th>사용 요구 사항<br/>참고<br/><br/> </th></tr></thead><tbody><tr><td>IDFA</td><td>iOS</td><td>참고사항 참조<br/>(오른쪽)</td><td>기본적으로 <a href="./audiences-user-identifier-policy#ios">앱 추적 투명성(ATT, AppTrackingTransparency) 상태: 승인되었거나 결정되지 않은 사용자</a>에 한해 공유됩니다. </td></tr><tr><td>GAID</td><td>안드로이드</td><td>Y</td><td>없음</td></tr><tr><td>OAID</td><td>안드로이드<br/>(구글 플레이 제외)</td><td>N</td><td> 앱스플라이어 SDK에서 <a href="./android-oaid-implementation-in-the-sdk" target="_blank">구성되어야 함</a> </td></tr><tr><td>IMEI</td><td>안드로이드<br/>(구글 플레이 제외)</td><td>N</td><td> 앱스플라이어 SDK에서 <a href="./android-oaid-implementation-in-the-sdk" target="_blank">구성되어야 함</a> </td></tr><tr><td>CUID</td><td>iOS<br/>안드로이드</td><td>N</td><td><ul><li>광고주가 <a href="./customer-user-id-field-cuid" target="_blank">발생한 데이터를 앱스플라이어 API 또는 SDK를 통해 앱스플라이어</a>에 보고함</li><li>광고 파트너와 공유되지 않지만 귀사의 내부 용도로 유용할 수 있습니다.</li><li> <a href="https://support.appsflyer.com/hc/article_attachments/360017900558">추가 식별자 이용약관</a>에 따라 </li></ul></td></tr><tr><td>IDFV</td><td>iOS</td><td>N</td><td><ul><li>광고 파트너와 공유되지 않지만 귀사의 내부 용도로 유용할 수 있습니다.</li><li> <a href="https://support.appsflyer.com/hc/article_attachments/360017900558">추가 식별자 이용약관</a>에 따라 </li></ul></td></tr><tr><td>이메일 (해시됨)</td><td>iOS<br/>안드로이드</td><td>N</td><td rowspan="2"><ul><li> <a href="./audiences-configure-additional-identifiers-for-partner-audience-creation" target="_blank">구성해야 함</a> 앱스플라이어 SDK 또는 S2S-mobile API를 통해</li><li>SHA256 해싱으로 암호화해야 합니다.</li><li> <a href="https://support.appsflyer.com/hc/article_attachments/360017900558">추가 식별자 이용약관</a>에 따라 </li></ul></td></tr><tr><td>전화번호 (해시됨)</td><td>iOS<br/>안드로이드</td><td>N</td></tr></tbody></table>

</Accordion>

<div id="setting-account-level-user-identifier-policy" />

## 계정 수준 유저 식별자 정책 설정

유저 식별자 정책은 관리자 유저만 설정할 수 있습니다.

**정책을 설정하거나 수정하려면 다음 단계를 따르세요:**

1. 앱스플라이어의 사이드 메뉴에서 **인게이지** > **오디언스**를 선택합니다.
2. 오른쪽 상단의 설정(기어) 아이콘을 클릭하세요.
3. **유저 식별자 정책 창에서 귀사의 개인정보 보호정책을 준수하는 설정을 선택합니다.**
   * [IDFA, GAID, OAID 및 IMEI 이외의 식별자 공유를 허용하려면 먼저 추가 식별자 이용약관을 검토하고 수락해야 합니다.](https://support.appsflyer.com/hc/article_attachments/360017900558)
   * 기존 파트너 연결에서 업로드된 식별자를 허용하지 않기로 선택하면 이러한 식별자 업로드를 중지할지를 확인하는 메시지가 표시됩니다.
4. **저장**을 클릭하세요.

귀사의 IDFA 정책 변경 사항은 Apple의 iOS 14.5 출시부터 적용됩니다. 유저 식별자 정책의 기타 변경 사항은 다음 파트너 데이터 업로드 시부터 적용됩니다.

<div id="privacy-regulations" />

## 개인정보 보호 규정

이 섹션에서는 유저 식별자가 어떻게 공유되는지에 영향을 미치는 개인정보 보호 규정을 설명합니다.

<div id="ios" />

<Accordion title="iOS">

iOS 14.5버전부터 모든 앱은 광고 목적으로 IDFA 디바이스 식별자 공유를 허용\거부할 수 있는 옵션을 사용자에게 제공해야 합니다 (앱 추적 투명성). 사용자가 이 옵션(앱 추적 투명성 동의 대화 상자)을 보고 응답했는지 여부에 따라 사용자의 <Anchor target="_blank" href="/marketers/ko/docs/att-implications-ios-14-and-deprecation-of-lat">앱 추적 투명성 상태</Anchor>가 결정됩니다.

iOS에서 식별자를 공유하기 위한 오디언스 정책 옵션은 사용자의 가장 최근 앱 추적 투명성 상태를 기반으로 합니다. 귀사의 공유 옵션은 다음과 같습니다.

| 유저 정책 옵션 | 해당 앱 추적 투명성(ATT) 상태 |
| --- | --- |
| 절대로 업로드하지 않기 | 이 식별자는 파트너에게 업로드되지 않습니다. |
| 앱 추적 투명성(ATT) 상태: 승인됨만 | 가장 최근의 앱 추적 투명성(ATT) 상태가 **authorized** 또는 **af\_authorized**인 경우 식별자가 업로드됩니다. |
| 앱 추적 투명성(ATT) 상태: 승인되었거나 결정되지 않음 | 가장 최근의 앱 추적 투명성(ATT) 상태가 \*\*authorized\*\*, \*\*af\_authorized\*\*, \*\*not\_determined\*\* 또는 \*\*af\_unavailable일 경우 식별자가 업로드됩니다.  <br />  <br />*Apple의 iOS 14.5 출시부터 IDFA에 대한 기본 옵션\*\** |
| 항상 업로드하기 | 식별자는 앱 추적 투명성(ATT) 상태와 관계없이 업로드됩니다. 귀사의 앱의 이용약관을 준수하십시오.  <br />  <br />*IDFA에 사용할 수 없는 옵션* |

**참고:** 오디언스에서 새 사용자의 앱 추적 투명성(ATT) 상태는 ATT 동의 대화 상자를 보고 응답할 때까지 결정되지 않음으로 처리됩니다.

자세한 앱 추적 투명성(ATT) 상태 정의는 다음을 참조하세요.

* <Anchor target="_blank" href="https://developer.apple.com/documentation/apptrackingtransparency/attrackingmanager/authorizationstatus/">Apple 앱 추적 투명성(ATT) 상태 정의</Anchor>
* <Anchor target="_blank" href="/marketers/ko/docs/att-implications-ios-14-and-deprecation-of-lat#att-값">앱스플라이어 앱 추적 투명성(ATT) 상태 정의</Anchor> (af\_authorized, af\_unavailable)

또한, 유럽 경제 지역(EEA) 모든 사용자는 Google의 [디지털 시장법(DMA)](/docs/audiences-user-identifier-policy#eu-digital-markets-act) 시행을 준수해야 합니다.

</Accordion>

<div id="android" />

<Accordion title="안드로이드">

유럽 경제 지역(EEA) 안드로이드 사용자는 Google의 [디지털 시장법(DMA)](/docs/audiences-user-identifier-policy#eu-digital-markets-act) 시행을 준수해야 합니다.

</Accordion>

<div id="eu-digital-markets-act" />

<Accordion title="EU 디지털 시장법">

Google은 디지털 시장법(DMA) 시행의 일환으로 2024년 3월 6일 EU 사용자 동의 정책을 업데이트하고 있습니다. Google 앱 어트리뷰션 파트너인 앱스플라이어는 광고주가 Google Ads 마케팅 채널에서 가치를 극대화할 수 있도록 지원하며, Google의 정책 요구사항을 충족하기 위한 필요한 변경을 진행하고 있습니다. <Anchor target="_blank" href="https://www.appsflyer.com/hubs/dma/">더 보기</Anchor>

**이러한 변경 사항이 오디언스에 미치는 영향:**

* **New 앱스플라이어 SDK**  
  최신 앱스플라이어 SDK는 <Anchor target="_blank" href="https://ec.europa.eu/eurostat/statistics-explained/index.php?title=Glossary:European_Economic_Area_(EEA)">유럽 경제 지역(EEA)</Anchor>의 앱 소유자로부터 사용자 동의를 수집하여 해당 데이터를 Google과 공유할 수 있도록 합니다. 앱스플라이어에서 생성된 오디언스(예: 커스텀 및 제안된 오디언스)에 대해서는 SDK에서 수집된 동의 정보가 자동으로 오디언스와 공유된 후 Google과 공유됩니다. 최신 SDK로 업데이트하면 이 프로세스가 자동으로 진행됩니다.
* **Google에 연결된 오디언스**
  * **동의 승인** - 앱스플라이어는 Google과의 정보 공유에 동의한 EEA 사용자의 디바이스를 Google에 발송합니다.
  * **동의 거부** - 앱스플라이어는 Google과의 정보 공유에 대한 동의를 거부한 EEA 사용자의 디바이스에 데이터를 발송하지 않습니다.
  * **동의 불명** - 앱스플라이어는 동의를 하거나 거부하지 않은 EEA 사용자의 디바이스를 '지정되지 않음'으로 발송합니다. Google 측에서 이들을 오디언스에 포함시키는 것은 허용되지 않을 가능성이 큽니다.  

    자세한 내용은 Google의 <Anchor target="_blank" href="https://support.google.com/google-ads/answer/14310715">FAQ</Anchor>를 참조하세요.
* **기존 오디언스**  
  2024년 3월 6일 이전에 이미 Google의 오디언스에 속해 있던 모든 디바이스는 영향을 받지 않으며 계속해서 오디언스의 일부로 유지됩니다. 기존 오디언스에 New 오디언스나 새로운 EEA 디바이스가 추가된 경우에만 동의를 받아 Google에 업로드됩니다.
* **오디언스 업로드 크기**  
  사용자가 동의하거나 거부하는 수에 따라 예상 오디언스 크기와 실제 업로드 크기가 영향을 받을 수 있습니다.
* #### <span id="importing-audiences"></span>**오디언스 가져오기**

  * **표준 오디언스 가져오기** - 앱스플라이어는 앱스플라이어 SDK에서 수집한 동의 데이터를 추가하고, Google에 전송하기 전에 동의하지 않거나 지정되지 않은 디바이스를 오디언스에서 제거합니다.
  * **있는 그대로의 오디언스 가져오기** - <Anchor target="_blank" href="/marketers/ko/docs/audiences-import-audience-segments-from-internal-systems#import-a-csv-file">CSV</Anchor> 또는 <Anchor target="_blank" href="/marketers/ko/docs/audiences-import-audience-segments-from-internal-systems#use-the-import-audience-api">API</Anchor>를 통해 있는 그대로의 오디언스를 가져올 때 두 개의 추가 동의 필드를 추가해야 합니다. 이러한 필드는 다음과 같습니다.

| 앱스플라이어 필드 (1) | Google 필드 (2) | 값 | 필드 설명 |
| --- | --- | --- | --- |
| <span id="ad_personalization"></span>ad\_personalization\_enabled | ad\_personalization | true\/false | 유저가 개인 광고를 위해 자신의 데이터를 Google에 사용하는 것에 동의했는지 여부 |
| <span id="ad_user_data"></span>ad\_user\_data\_enabled | ad\_user\_data | true\/false | 유저가 자신의 유저 데이터를 Google에 발송하는 데 동의했나요? |

동의 필드에 값이 입력되지 않으면 '지정되지 않음'으로 Google에 전송됩니다.

<div id="note" />

> 📘 **참고**
>
> Google의 디지털 시장법(DMA) 시행은 안드로이드와 iOS 플랫폼 모두에 적용됩니다.

</Accordion>

<div data-zendesk-anchors="background=%EC%86%8C%EA%B0%9C h_01HKA2FS9VBCSV8FP8FH79H4R0=%EC%86%8C%EA%B0%9C user-identifiers=%EC%9C%A0%EC%A0%80-%EC%8B%9D%EB%B3%84%EC%9E%90 h_01HKA2FS9VSVJD54R14GC7G0P4=%EC%9C%A0%EC%A0%80-%EC%8B%9D%EB%B3%84%EC%9E%90 h_01HNZH99Z8NA9607VHSYH5XVW0=shared-identifiers h_01HKA2FS9V1KBK9BJAJ63FP6CV=identifiers-table setting-accountlevel-user-identifier-policy=%EA%B3%84%EC%A0%95-%EC%88%98%EC%A4%80-%EC%9C%A0%EC%A0%80-%EC%8B%9D%EB%B3%84%EC%9E%90-%EC%A0%95%EC%B1%85-%EC%84%A4%EC%A0%95 h_01HKA2FS9WNGGRP3NX5NKV15SK=%EA%B3%84%EC%A0%95-%EC%88%98%EC%A4%80-%EC%9C%A0%EC%A0%80-%EC%8B%9D%EB%B3%84%EC%9E%90-%EC%A0%95%EC%B1%85-%EC%84%A4%EC%A0%95 user-identifier-policy-options=%EA%B0%9C%EC%9D%B8%EC%A0%95%EB%B3%B4-%EB%B3%B4%ED%98%B8-%EA%B7%9C%EC%A0%95 h_01HKA2FS9W5NSKKRK2VCZARG15=%EA%B0%9C%EC%9D%B8%EC%A0%95%EB%B3%B4-%EB%B3%B4%ED%98%B8-%EA%B7%9C%EC%A0%95 h_01HNZJ1ET6F87AHHVQK17QHZDD=ios h_01HNZJ1ET67JQQCPYSM3H6Y9VW=android h_01HNZN8MWETDCMGWKJ0MMM8JK4=eu-digital-markets-act importing-audiences=%EC%98%A4%EB%94%94%EC%96%B8%EC%8A%A4-%EA%B0%80%EC%A0%B8%EC%98%A4%EA%B8%B0 h_01HPGV1GYT8DW0GYWTC031TNVH=%EC%98%A4%EB%94%94%EC%96%B8%EC%8A%A4-%EA%B0%80%EC%A0%B8%EC%98%A4%EA%B8%B0 h_01HNZEAJT00KKEBDPR7FD0TJNR=%EC%B0%B8%EA%B3%A0" />
