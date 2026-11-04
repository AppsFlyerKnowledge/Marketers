---
title: 오디언스 - 오디언스 가져오기
metadata:
  keywords:
    - Developers
    - Premium
    - Marketers
    - Audience Segmentation
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-neama-benhabib
    - Marketers
    - Audience Segmentation
  created_at: '2020-09-15T10:45:43Z'
  edited_at: '2026-10-14T10:37:20Z'
  id: 360013291857
  locale: ko
  section: Audiences
  section_id: 6551336428945
  url: https://support.appsflyer.com/hc/ko/articles/360013291857
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **요약: 내부 시스템(예: BI 및 CRM)에서 미리 정의된 오디언스 세그먼트를 앱스플라이어 오디언스로 가져오면, 오디언스를 통해 이러한 세그먼트를 광고 파트너와 연결하고 유지할 수 있습니다.**

<div id="why-import-audiences" />

## 오디언스를 가져오는 이유는 무엇인가요?

특정 상황에서는 내부 시스템에 미리 정의된 오디언스 세그먼트가 있을 수 있습니다. 이러한 오디언스(디바이스 및\/또는 사용자 식별자 목록)를 앱스플라이어로 가져오면, 모든 오디언스 세그먼트와 광고 파트너를 연결하고 유지 관리하는 중심점으로 오디언스를 사용할 수 있습니다. 또한 식별자 매칭\/데이터 보강 및 연결된 캠페인 지표 등의 오디언스 기능을 최대한 활용할 수 있습니다.

다음 예시를 생각해 보세요.

<div id="examples" />

> 📄 **예시**
>
> 생일이 있는 달에 사용자에게 프로모션 혜택을 제공하려고 합니다.
>
> 오디언스를 사용하는 방법은 다음과 같습니다.
>
> 1. 내부 CRM을 사용하여 생일이 포함된 사용자 목록을 만드세요.
> 2. 생일 월에 따라 목록을 세분화하고, 개별 광고 ID 목록으로 내보내세요.
> 3. 해당 목록을 앱스플라이어에 오디언스로 가져와서 프로모션 캠페인을 진행할 파트너와 연결하세요.
> 4. 관련 파트너와 함께 캠페인을 설정하여 해당 오디언스를 적절히 타겟팅하세요.
>
> **추가 사용자 확보**앱 개발 스튜디오가 다른 스튜디오를 인수했습니다. 인수한 스튜디오에는 이전에 앱을 설치한 사용자의 디바이스 ID가 있으며, 이 사용자들에게 기존 앱을 설치하도록 목적하고 있습니다.
>
> 오디언스를 사용하는 방법은 다음과 같습니다.
>
> 1. 인수한 스튜디오에서 디바이스 ID 목록을 얻어 앱스플라이어에 오디언스로 가져옵니다.
> 2. 캠페인을 진행할 파트너와 오디언스를 연결하세요.
> 3. 관련 파트너와 함께 캠페인을 설정해 해당 사용자를 목표로 하세요.

<div id="audiences-import-v20" />

## 오디언스 가져오기 V2.0

이 문서에서는 새로운 오디언스 가져오기 기능 V2.0(CSV 및 API로 가져오기 옵션 포함)과 관련된 개념과 절차를 설명합니다.

<div id="imported-audience-types" />

## 가져온 오디언스 유형

오디언스를 가져올 때 두 가지 유형 중 하나로 지정하면, 앱스플라이어가 업로드된 오디언스를 처리하고 파트너에게 업로드하는 방식을 결정합니다. **지정은 오디언스를 처음 가져올 때 이루어지며 추후에 변경할 수 없습니다.**

**표준으로 가져온 오디언스:**

* 식별자 매칭 및 데이터 보강을 거칩니다—이는 오디언스가 가져온 식별자를 오디언스 데이터베이스의 기존 식별자(동일 앱의 동일 사용자에 대한)를 매칭하여 파트너에게 업로드된 오디언스 데이터를 보강하는 프로세스입니다.
* 귀사의 계정의 사용자 식별자 정책에 따라 파트너에게 업로드됩니다.
* 이 문서에서 설명된 V2.0 가져오기 기능을 사용하여 가져와야 합니다.

**"있는 그대로" 가져온 오디언스:**

* 식별자 매칭이나 데이터 보강을 거치지 않습니다.
* 귀사의 사용자 식별자 정책을 참조하지 않고 파트너에게 업로드됩니다(즉, 가져온 모든 식별자가 파트너에게 업로드됨).
* V2.0 가져오기 기능을 사용하여 가져올 수 있습니다(이 문서에서 설명됨).

<div id="important" />

> 🚧 **중요!**
>
> * 2021년 11월 23일 현재 존재하는 모든 오디언스는 **있는 그대로의 오디언스로 지정되며 표준 오디언스로 변경될 수 없습니다.** 필요에 따라 V2.0 가져오기 기능(이 문서에서 설명됨)을 사용하여 이러한 오디언스를 계속 업데이트할 수 있습니다.
> * 한 번에 최대 500개의 활성 오디언스를 가져올 수 있습니다.
> * 관리자만이 새로 가져온 오디언스를 있는 그대로의 오디언스로 지정할 수 있습니다.
> * CUID를 식별자로 사용하여 오디언스를 가져올 때, 관련 디바이스와의 완전한 연결과 디바이스 식별자(예: GAID, IDFA)를 통한 성공적인 보강을 위해 인스톨 시(앱 설치 후 이벤트가 아닌) 앱스플라이어가 CUID 연결을 수신해야 합니다. <Anchor target="_blank" href="/marketers/ko/docs/customer-user-id-field-cuid#cuid-설정방법">더 보기</Anchor>

<div id="audience-import-procedures" />

## 오디언스 가져오기 절차

CSV 파일을 업로드하거나 오디언스 가져오기 API를 사용하여 오디언스를 가져옵니다.

<div id="import-a-csv-file" />

<Accordion title="CSV 파일 가져오기">

다음 사양에 따라 CSV 파일을 준비하세요.

**형식**

* 업로드되는 각 유저 식별자에 대한 하나의 열
* 각 열의 식별자 이름이 있는 헤더 행(모두 소문자)
* 빈 행 없음
* 최대 행 수: 1,000만
* Excel을 사용하여 파일을 준비할 경우, 다음 이미지와 같이 **CSV (쉼표로 구분) (\*.csv)** 파일로 저장합니다.

  <Image alt="CSV.jpg" src="https://support.appsflyer.com/hc/article_attachments/18502652300561" width="339px" />

<div id="identifier-hash" />

#### 식별자 해시

**열 및 식별자**

* 데이터는 헤더 행을 사용하여 각 열의 데이터를 식별합니다. 따라서:
  * 열이 특정 순서로 표시될 필요는 없습니다.
  * 업로드되지 않는 식별자에 대한 열을 포함할 필요는 없습니다.
  * 각 행에 필수 식별자가 포함되어 있는 한, 하나의 CSV 파일에서 원하는 만큼 식별자를 가져올 수 있습니다. 아래에서 자세히 설명합니다.
* 사용 가능한 식별자:
  * app\_id
  * idfv
  * idfa
  * gaid
  * oaid
  * imei
  * cuid
  * 이메일
  * 전화번호
  * 전화\_e164
  * braze\_id
  * amplitude\_id
* 필수 식별자:  
  * 안드로이드 오디언스: **app\_id** + 다음 중 하나: **gaid**, **oiad**, **imei**, **cuid**, **braze\_id** 또는 **amplitude\_id**
  * iOS 오디언스: **app\_id** + 다음 중 하나: **idfv**, **cuid**, **braze\_id** 또는 **amplitude\_id**
* 2024년 3월 6일 Google에서 <Anchor target="_blank" href="/marketers/ko/docs/audiences-user-identifier-policy#eu-digital-markets-act">디지털 시장법(DMA)</Anchor>을 준수하기 위해, '있는 그대로' 오디언스를 가져올 때에는 앱스플라이어 동의 열 두 개를 추가해야 합니다. 다음과 같습니다:

| 앱스플라이어 동의 열 | Google 필드 | 값 | 필드 설명 |
| --- | --- | --- | --- |
| <span id="ad_personalization"></span>ad\_personalization\_enabled | ad\_personalization | true\/false | 유저가 개인 광고를 위해 자신의 데이터를 Google에 사용하는 것에 동의했는지 여부 |
| <span id="ad_user_data"></span>ad\_user\_data\_enabled | ad\_user\_data | true\/false | 유저가 자신의 유저 데이터를 Google에 발송하는 데 동의했는지 여부 |

동의 필드에 값이 입력되지 않으면 Google에 "지정되지 않음"으로 전송되며, Google 측 오디언스에 포함되지 않을 가능성이 큽니다. 이러한 필드를 채우면 Google 오디언스에 <Anchor target="_blank" href="https://ec.europa.eu/eurostat/statistics-explained/index.php?title=Glossary:European_Economic_Area_(EEA)">유럽 경제 지역(EEA)</Anchor>의 유저를 최대한 포함할 수 있습니다.

**CSV 파일 예시:**

<Anchor target="_blank" href="https://support.appsflyer.com/hc/article_attachments/4413851475729">new-import-android-example.csv</Anchor>  
<Anchor target="_blank" href="https://support.appsflyer.com/hc/article_attachments/4413840980497">new-import-ios-example.csv</Anchor>

<span id="01ECF4ZD0RB90HZC6ZFNTKMDSG"></span>**CSV 파일을 사용하여 새 오디언스를 만들고 가져오기:**

1. 앱스플라이어 왼쪽 패널에서 **(유저를 앱에) 참여시키다** > **오디언스**로 이동합니다.
2. **New 오디언스**를 클릭합니다.
3. **오디언스 가져오기**를 선택합니다.  
   **오디언스 가져오기** 기간이 열립니다.
4. 고유한 **오디언스 이름**을 입력합니다.
5. 오디언스 플랫폼을 선택하세요: **안드로이드** 또는 **iOS.**
6. 이 오디언스가 [**표준** 오디언스인지 아니면 **있는 그대로의** 오디언스인지](/docs/audiences-import-audience-segments-from-internal-systems#가져온-오디언스-유형) 표시하세요.
7. 표준 오디언스의 경우 상자를 체크하지 않습니다.
8. 있는 그대로의 오디언스의 경우 상자를 체크합니다. (**참고:** 이 옵션은 관리자만 사용할 수 있습니다.)
9. 오디언스를 저장하고 계속을 클릭하세요.  
   가져오기 탭이 표시됩니다.
10. **CSV 사용하여 가져오기** 섹션에서 기본값인 **새로운 디바이스/사용자 추가**를 그대로 유지합니다 (새로운 오디언스이기 때문입니다).
11. 업로드할 CSV 파일을 선택합니다.  
    **성공적으로 업로드되었습니다.** 라는 확인 메시지가 표시될 때까지 기다립니다.
12. 다음을 클릭하세요.  
    연결 탭이 표시됩니다.
13. **(선택 사항)** <Anchor target="_blank" href="/marketers/ko/docs/audiences-guide#connect-an-audience-to-media-partners">오디언스를 파트너와 연결</Anchor>하는 방법에 대한 지침을 따르세요.
14. **완료**를 클릭합니다.

이제 오디언스가 오디언스 대시보드에 표시되며, 가져오기 및 파트너와 연결되었습니다. 그러나 새로 가져온 오디언스 목록은 아직 파트너에게 업로드할 수 없습니다. 이는 가져온 오디언스가 <Anchor target="_blank" href="/marketers/ko/docs/about-data-freshness-and-timezone-support#eod">데이터 최신성</Anchor>으로 처리되기 때문입니다.

**CSV 파일을 사용하여 기존 오디언스를 업데이트하려면:**

1. 앱스플라이어 왼쪽 패널에서 **(유저를 앱에) 참여시키다** > **오디언스**로 이동합니다.
2. 업데이트하려는 오디언스의 이름을 클릭하세요.  
   **오디언스 편집** 화면이 열리며, **정의** 탭이 표시됩니다.
3. 오디언스 이름을 편집하려면 여기에서 가능합니다. 그렇지 않으면 **가져오기** 탭을 선택하여 새 CSV 파일을 업로드하세요.
4. **CSV 사용하여 가져오기** 섹션에서 업로드된 목록을 어떻게 처리할지 선택합니다.
5. **새로운 디바이스/사용자 추가:** 기존 오디언스에 디바이스/사용자 식별자를 추가합니다.
6. **기존 오디언스에서 디바이스/사용자 제거:** 업로드된 목록에서 디바이스/사용자 식별자를 오디언스에서 제거합니다.
7. **기존 오디언스를 새 디바이스/사용자로 덮어쓰기:** 업로드된 목록으로 전체 오디언스를 교체합니다.
8. 업로드할 CSV 파일을 선택합니다.  
   **성공적으로 업로드되었습니다.** 라는 확인 메시지가 표시될 때까지 기다립니다.
9. 다음을 클릭하세요.  
   연결 탭이 표시됩니다.
10. 필요한 경우 이 오디언스에 대한 <Anchor target="_blank" href="/marketers/ko/docs/audiences-guide#connect-an-audience-to-media-partners">파트너 연결</Anchor>을 변경하세요.
11. **완료**를 클릭합니다.

오디언스가 CSV 파일을 사용하여 업데이트되었습니다. 하지만 가져온 오디언스는 <Anchor target="_blank" href="/marketers/ko/docs/about-data-freshness-and-timezone-support#eod">일일 데이터 최신성</Anchor>으로 처리되므로 수정된 오디언스 목록은 아직 파트너에게 업로드되지 않았습니다.

<div id="error-messages" />

### 오류 메시지

| 메시지 | 1. 일으키다. 2. 발생시키다. | 수행할 작업 |
| --- | --- | --- |
| 디바이스 목록에 문제가 있습니다 | 디바이스 목록에 하나 이상의 문제가 있습니다 | CSV 파일을 확인하세요.<ul><li>디바이스와 GAID\/IDFA 식별자가 올바른 형식으로 채워져 있는지</li><li>필수 식별자가 포함되어 있는지</li><li>올바른 형식의 헤더 행이 포함되어 있는지</li><li>빈 행이 없는지</li><li>app\_id가 오디언스에 사용하는 올바른 앱으로 채워져 있는지</li></ul> |
| 디바이스 목록이 비어 있는 것 같습니다. 디바이스 ID를 추가하고 다시 시도하세요. | CSV 파일이 비어 있습니다 | CSV에 최소한 하나의 디바이스 ID가 포함되어 있는지 확인하세요. |
| 하나 이상의 디바이스 ID를 이해하지 못했습니다. | <ul><li>CSV 형식이 올바르지 않습니다.</li><li>업로드하신 파일은 CSV 파일이 아닙니다.</li><li>CSV 파일이 유효한 CSV 편집기(예: Microsoft Excel)가 아닌 다른 프로그램에서 편집 및 저장되었습니다.</li><li>하나 이상의 디바이스 ID가 잘못된 형식입니다.</li></ul> | <ul><li>CSV가 필수 형식인지 확인하세요.</li><li>모든 디바이스 ID가 올바른 형식인지 확인하세요.</li><li>Excel을 사용한 경우 파일을 위에 설명한 CSV 형식으로 저장하세요.</li></ul> |
| 오디언스에 사용자 계정 정책을 적용하는 동안 v1 가져오기를 사용할 수 없습니다. | V1.0 가져오기 구조를 사용하여 [표준 오디언스](/docs/audiences-import-audience-segments-from-internal-systems#가져온-오디언스-유형)에 대한 CSV 파일을 업로드했습니다. 표준 오디언스는 V2.0 구조의 CSV를 사용하여 업로드해야 합니다. | 위에 설명된 형식, 열 및 식별자를 사용하도록 업로드할 CSV 파일을 편집하세요. |
| 일시적인 연결 문제로 파일을 업로드할 수 없었습니다. 지금 다시 시도하세요. | 네트워크 오류일 수 있습니다 | CSV 파일을 다시 업로드해 보세요. |

</Accordion>

<div id="use-the-import-audience-api" />

<Accordion title="오디언스 가져오기 API 사용">

오디언스 가져오기 API는 오디언스에 디바이스를 추가하거나 제거하는 데 사용됩니다.

**API를 사용하여 New 오디언스를 가져오려면:**

1. 앱스플라이어 왼쪽 패널에서 **(유저를 앱에) 참여시키다** > **오디언스**로 이동합니다.
2. **New 오디언스**를 클릭합니다.
3. **오디언스 가져오기**를 선택합니다.  
   **오디언스 가져오기** 기간이 열립니다.
4. 고유한 **오디언스 이름**을 입력합니다.
5. 오디언스 플랫폼을 선택하세요: **안드로이드** 또는 **iOS.**
6. 이 오디언스가 [**표준** 오디언스인지 아니면 **있는 그대로의** 오디언스인지](/docs/audiences-import-audience-segments-from-internal-systems#가져온-오디언스-유형) 표시하세요.
   * **표준 오디언스**의 경우 박스를 선택하지 않고 둡니다.
   * **있는 그대로의 오디언스**의 경우 박스를 선택합니다(이 옵션은 관리자만 사용할 수 있습니다). Google의 디지털 시장법(DMA) 시행에 따라 2024년 3월 6일부터 "있는 그대로" 오디언스를 가져올 때 <Anchor target="_blank" href="/marketers/ko/docs/audiences-user-identifier-policy#오디언스-가져오기">두 가지 추가 동의 필드</Anchor>가 필요합니다. 이 필드를 채우면 Google 오디언스에 <Anchor target="_blank" href="https://ec.europa.eu/eurostat/statistics-explained/index.php?title=Glossary:European_Economic_Area_(EEA)">유럽 경제 지역(EEA)</Anchor>의 사용자가 최대한 포함될 수 있습니다.
7. **저장**을 클릭합니다.  
   가져오기 페이지가 표시됩니다.
8. **API를 사용하여 가져오기** 섹션에서 기본값인 **새 디바이스\/사용자 추가**를 유지합니다(이는 New 오디언스이기 때문입니다).
9. <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/audience-import-post">New 오디언스 API 가져오기</Anchor> 페이지에서 API 요청 URL을 복사합니다(API 토큰은 이미 포함되어 있습니다).
10. 그런 다음 API 요청 본문을 복사하여 붙여넣습니다.
11. **완료**를 클릭합니다. **연결** 탭이 표시됩니다.
12. **(선택 사항)** <Anchor target="_blank" href="/marketers/ko/docs/audiences-guide#connect-an-audience-to-media-partners">오디언스를 파트너와 연결</Anchor>하는 방법에 대한 지침을 따르세요.
13. **완료**를 클릭합니다.
14. 사용자\/디바이스 식별자를 포함한 API 요청을 준비하고 앱스플라이어에 POST합니다.

**API를 사용하여 기존 오디언스를 업데이트하려면:**

1. 앱스플라이어 왼쪽 패널에서 **(유저를 앱에) 참여시키다** > **오디언스**로 이동합니다.
2. 업데이트하려는 오디언스의 이름을 클릭하세요.  
   **오디언스 편집** 화면이 열리며, **정의** 탭이 표시됩니다.
3. 오디언스 이름을 편집하려면 여기에서 가능합니다. 그 외에는 **가져오기** 탭을 선택합니다.
4. **API를 사용하여 가져오기** 섹션에서 업로드된 목록으로 수행할 작업을 선택합니다.
5. **새 디바이스\/사용자 추가: 기존 오디언스에 디바이스\/사용자 식별자를 추가합니다.**
6. **기존 오디언스에서 디바이스\/사용자 제거:** 기존 오디언스에서 디바이스\/사용자 식별자를 제거합니다.
7. <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/audience-import-post">New 오디언스 API 가져오기</Anchor> 페이지에서 **API 요청 URL**을 복사합니다(API 토큰은 이미 포함되어 있습니다). **참고:** 이 옵션을 변경하면 복사할 코드의 엔드포인트 경로가 변경됩니다. 이번 및 향후 API 요청에서 수행하려는 작업에 대해 올바른 엔드포인트를 사용해야 합니다.
8. 그런 다음 **API 요청 본문**을 복사합니다.
9. 다음을 클릭하세요.  
   연결 탭이 표시됩니다.
10. 필요한 경우 이 오디언스에 대한 <Anchor target="_blank" href="/marketers/ko/docs/audiences-guide#connect-an-audience-to-media-partners">파트너 연결</Anchor>을 변경하세요.
11. **완료**를 클릭합니다.
12. 사용자\/디바이스 식별자를 포함한 API 요청을 준비하고 앱스플라이어에 POST합니다.

**참고:** API를 통해 가져오는 경우, 오디언스가 업데이트되는 데 24시간이 소요됩니다.

<div id="response-codes" />

### 응답 코드

| 코드 | 메시지 | 설명 |
| --- | --- | --- |
| 200 | 요청이 성공적으로 완료되었습니다. | 오디언스 가져오기에 성공했습니다. |
| 400 | 유효하지 않은 오디언스 플랫폼입니다. 이 오디언스는 이미 안드로이드\/iOS에 설정되어 있습니다. 다른 플랫폼을 사용하려면 UI에서 New 오디언스를 생성하십시오. | 요청 본문에서 지정된 플랫폼이 오디언스를 작성할 때 지정한 플랫폼과 일치하지 않습니다. |
| 400 | X 개 이상의 행에 앱 ID가 포함되어 있지 않습니다. 각 행에 앱 ID를 첨부해야 합니다. | 각 행에는 **app\_id**가 포함되어야 합니다.<ul><li>**참고:** V1.0 기존 가져오기 기능을 사용하여 가져온 [있는 그대로의 오디언스](/docs/audiences-import-audience-segments-from-internal-systems#가져온-오디언스-유형)에는 app\_id가 필요하지 않습니다.</li></ul> |
| 400 | X 개 이상의 행에 유효한 고유 식별자가 포함되어 있지 않습니다. | 전체 또는 일부 행에 다음 식별자 중 하나 이상이 유효한 형식으로 포함되어 있지 않습니다.<ul><li>안드로이드 오디언스의 경우: **gaid** 또는 **oiad** 또는 **imei** 또는 **cuid** 또는 **braze\_id** 또는 **amplitude\_id**</li><li>iOS 오디언스의 경우: **idfv** 또는 **cuid** 또는 **braze\_id** 또는 **amplitude\_id**</li></ul> |
| 400 | 요청당 Y개 이상의 디바이스를 처리할 수 없습니다 (이 요청에 포함된 디바이스 수: n) | 요청 본문에 10,000개가 넘는 디바이스 ID 목록이 포함되어 있습니다. |
| 400 | 디바이스 목록은 비워둘 수 없습니다. | 요청 본문에 빈 디바이스 목록이 포함되어 있습니다.<br /><br />요청당 최소한 하나의 디바이스 ID를 제공해야 합니다. |
| 400 | 귀사의 디바이스 ID 중 하나 이상을 이해할 수 없습니다. | 전체 또는 일부 디바이스 ID가 유효한 형식이 아닙니다. |
| 400 | 제거할 디바이스 중 X개 이상이 디바이스당 두 개 이상의 식별자를 포함하고 있습니다. | 디바이스당 여러 식별자와 함께 제거 요청이 전송되었습니다. |
| 403 | 금지됨 | 승인되지 않은 요청: 가져오기 키가 잘못되었거나 누락되었습니다. |
| 429 | 요청이 너무 많습니다 | 요청은 분당 350건으로 제한됩니다. |
| 500 | 요청을 해석할 수 없습니다. | 잘못된 요청 본문 형식 (예상된 JSON 구조가 아니거나 JSON이 아님)<br /><br />위의 샘플 요청을 참조하세요. |

**API 제한 사항**

* 요청당 하나의 오디언스에만 디바이스를 추가할 수 있습니다.
* 요청당 하나의 오디언스에서만 디바이스를 제거할 수 있습니다.
* 요청당 최대 20,000개의 디바이스 ID를 발송할 수 있습니다.
* 분당 최대 350건의 요청을 발송할 수 있습니다.

</Accordion>

<div id="imported-audience-management-api" />

<Accordion title="가져온 오디언스 관리 API">

<Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/overview-2">가져온 오디언스 관리 API</Anchor>를 사용하면 광고주가 가져온 오디언스를 생성 및 구성하고, 파트너와 연결하고, 파트너에 업로드할 수 있습니다.

</Accordion>

<div data-zendesk-anchors="why-import-audiences=%EC%98%A4%EB%94%94%EC%96%B8%EC%8A%A4%EB%A5%BC-%EA%B0%80%EC%A0%B8%EC%98%A4%EB%8A%94-%EC%9D%B4%EC%9C%A0%EB%8A%94-%EB%AC%B4%EC%97%87%EC%9D%B8%EA%B0%80%EC%9A%94 h_01HA4M61P4H5AVXQFA5ETABA67=%EC%98%A4%EB%94%94%EC%96%B8%EC%8A%A4%EB%A5%BC-%EA%B0%80%EC%A0%B8%EC%98%A4%EB%8A%94-%EC%9D%B4%EC%9C%A0%EB%8A%94-%EB%AC%B4%EC%97%87%EC%9D%B8%EA%B0%80%EC%9A%94 01ECF4ZD0QQ5JJNH624D0E9WRF=%EC%98%88%EC%8B%9C audiences-import-v20=%EC%98%A4%EB%94%94%EC%96%B8%EC%8A%A4-%EA%B0%80%EC%A0%B8%EC%98%A4%EA%B8%B0-v20 h_01HA4M61P41RSJMKSJ2V9WJH8W=%EC%98%A4%EB%94%94%EC%96%B8%EC%8A%A4-%EA%B0%80%EC%A0%B8%EC%98%A4%EA%B8%B0-v20 imported-audience-types=%EA%B0%80%EC%A0%B8%EC%98%A8-%EC%98%A4%EB%94%94%EC%96%B8%EC%8A%A4-%EC%9C%A0%ED%98%95 h_01HA4M61P4TEBNF264RNFC57YP=%EA%B0%80%EC%A0%B8%EC%98%A8-%EC%98%A4%EB%94%94%EC%96%B8%EC%8A%A4-%EC%9C%A0%ED%98%95 h_01HA4M61P4NVDJ393HA4V75PQV=%EC%A4%91%EC%9A%94 audience-import-procedures=%EC%98%A4%EB%94%94%EC%96%B8%EC%8A%A4-%EA%B0%80%EC%A0%B8%EC%98%A4%EA%B8%B0-%EC%A0%88%EC%B0%A8 h_01HA4M61P4EEYGJNZ3N2D0KXS5=%EC%98%A4%EB%94%94%EC%96%B8%EC%8A%A4-%EA%B0%80%EC%A0%B8%EC%98%A4%EA%B8%B0-%EC%A0%88%EC%B0%A8 01ECF4ZD0RHJAQ31NKFCX8QEWW=import-a-csv-file identifier-hash=%EC%8B%9D%EB%B3%84%EC%9E%90-%ED%95%B4%EC%8B%9C h_01HA4M61P4BJZKN97ZTT8TKRBK=%EC%8B%9D%EB%B3%84%EC%9E%90-%ED%95%B4%EC%8B%9C confirmation-messages=%EC%98%A4%EB%A5%98-%EB%A9%94%EC%8B%9C%EC%A7%80 h_01HA4M61P57TMZRK4XX7ARK896=%EC%98%A4%EB%A5%98-%EB%A9%94%EC%8B%9C%EC%A7%80 h_01HA4M61P5XZR7C20Y5D3XX4K9=use-the-import-audience-api response-codes=%EC%9D%91%EB%8B%B5-%EC%BD%94%EB%93%9C h_01HA4M61P5YGX4QP2PDSVW7D3G=%EC%9D%91%EB%8B%B5-%EC%BD%94%EB%93%9C h_01HA4M61P6CE4RBCVTA3KE15VN=imported-audience-management-api" />
