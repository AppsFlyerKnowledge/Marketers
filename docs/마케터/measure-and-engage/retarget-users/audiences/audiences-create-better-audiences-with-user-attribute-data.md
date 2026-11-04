---
title: 오디언스—사용자 속성
metadata:
  keywords:
    - Advertisers
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
  created_at: '2020-06-11T06:13:55Z'
  edited_at: '2026-10-14T10:36:04Z'
  id: 360009775517
  locale: ko
  section: Audiences
  section_id: 6551336428945
  url: https://support.appsflyer.com/hc/ko/articles/360009775517
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **한눈에 보기:** 사용자 특성에 대한 데이터를 오디언스에 추가하여 귀사의 사용자를 관련 그룹으로 세분화하는 능력을 향상시켜 보세요.

[altUserAttributionNavigationXL3\_us-en.pngalt](https://support.appsflyer.com/hc/article_attachments/30448659840785)

<div id="about-user-attributes" />

## 사용자 속성에 관하여

이벤트 기반 데이터와 달리  사용자 속성은 귀사의 사용자가 귀사와 공유하는 일반적인 특성입니다. 이 속성들은 성별, 나이, 생일, 국가처럼 정적일 수 있고, 게임의 사용자 점수처럼 동적일 수 있습니다.

유저 속성 데이터는 다음과 같습니다.

* CSV 파일 가져오기 또는 API를 통해 JSON을 사용하여 업데이트됩니다.
* 해시 형태로 저장됩니다.
* 모든 오디언스 규칙 세트에서 사용 가능합니다

유저 속성 데이터는 **광고 파트너와 공유되지 않습니다.**

사용자 속성은 이 문서에서 설명한 대로 앱 수준 또는 계정 수준에 보관됩니다. 앱 수준 속성을 사용하면 계정 사용자가 <Anchor target="_blank" href="/marketers/ko/docs/user-management#개요">앱 권한</Anchor>이 필요합니다 속성을 관리하고 사용하기 위해.

다음 시나리오는 사용자 속성에 대한 자세한 설명을 제공합니다.

<div id="scenario-app-marketer-requirements" />

<Accordion title="시나리오—앱 마케터 요구 사항">

앱 마케터인 귀사는 다음의 일로 바쁩니다:

* 2개의 게임 앱(game\_a와 game\_b)을 유지 관리합니다.
* 게임\_c 출시
* 다음 사용자 속성을 활용하여 현재 앱 사용자를 타겟팅합니다:
  * 좋아하는 스포츠: 크리켓
  * 현재 게임 점수: 현재 게임 중 하나에서 15점 이상

이 표는 귀사의 CRM에서 가져온 사용자 속성 데이터를 포함하고 있습니다. 오디언스 규칙 세트는 이 데이터에 액세스해야 합니다.   
![UserAttributuesExample_us-en.png](https://files.readme.io/6f86d8659ef089ac82bb8401b4af650fbc590d2293ac93de30e6f9b4fc2ceb86-33375683035281.png)

**규칙 세트에서 CRM 데이터 사용**

오디언스에서 사용자 속성(좋아하는 스포츠와 게임 점수)을 생성합니다. 이를 통해 규칙 세트가 CRM 데이터에 액세스할 수 있게 됩니다.

<div id="scenario-user-attributes" />

#### 시나리오 사용자 속성

| 이름 | 형식 | 수준 |
| --- | --- | --- |
| <span id="game-score"></span>게임 점수 | <strong>숫자</strong>: '<em>ScoreGameB는 29보다 큽니다'</em>와 같은 규칙을 설정할 수 있습니다. | <strong>앱 수준</strong>: 사용자의 점수는 각 게임마다 기록됩니다.<br /><br />의미: ScoreGameA, ScoreGameB. |
| <span id="favorite-sport"></span>좋아하는 스포츠 | **문자열:** '*가장 좋아하는 스포츠가 테니스인 사용자를 대상으로'* 규칙을 설정할 수 있습니다.<br /><br />주의! 값은 대소문자를 구분합니다. | **계정 수준**: 앱에 상관없이 유저가 가장 좋아하는 스포츠는 같습니다.<br /><br />주의! 유저는 계정 수준 속성과 연결된 값을 하나만 가질 수 있습니다. |

**규칙 세트의 유저 속성**

유저 속성은 오디언스 규칙 세트에서 필터로 작용합니다. 이 예시는 마케터가 설정한 기준(좋아하는 스포츠와 게임 점수)을 사용합니다.

[alt유저속성예.jpgalt](https://support.appsflyer.com/hc/article_attachments/30448652652561)

</Accordion>

<div id="implement-user-attributes" />

## 유저 속성 구현

유저 속성을 설정, 추가, 관리, 삭제합니다.

<div id="set-up" />

<Accordion title="설정">

**필수 조건**:

앱 수준 속성을 관리하려면 계정 유저가 앱 권한을 가지고 있어야 합니다.

**유저 속성을 설정하려면 다음을 따르세요:**

1. [유저 속성을 추가합니다.](/docs/audiences-create-better-audiences-with-user-attribute-data#add)
2. [다음 중 하나를 수행하세요.](/docs/audiences-create-better-audiences-with-user-attribute-data#import-data-by-csv)

   * [CSV로 유저 속성 데이터를 가져옵니다.](/docs/audiences-create-better-audiences-with-user-attribute-data#import-data-by-csv)
   * [API로 유저 속성 데이터를 가져옵니다.](/docs/audiences-create-better-audiences-with-user-attribute-data#import-data-by-api)
3. <Anchor target="_blank" href="/marketers/ko/docs/audiences-guide#user-attributes">규칙 세트에 유저 속성을 구현합니다.</Anchor>

</Accordion>

<div id="add" />

<Accordion title="추가">

**유저 속성을 추가하려면:**

1. 앱스플라이어의 사이드 메뉴에서 **(유저를 앱에) 참여시키다** > **오디언스**를 선택합니다.
2. 유저 속성 탭을 클릭합니다.
3. 클릭 **사용자 속성 추가**.  

   ![유저속성추가.png](https://files.readme.io/6c7f25bb23d47e67aaef34264029daa9ab058f08e218a441ab9dde8240b0b384-33375683046033.png)
4. 필드를 채우세요. 현재 특성은 다음 표에서 확인할 수 있습니다.   
   * **속성 이름**
   * **형식**
   * **수준**
5. **저장**을 클릭하세요.

| 필드 | 특성 |
| --- | --- |
| <span id="attribute-name"></span>속성 이름 | <ul><li>영문자만 사용 가능</li><li>구두점이나 특수문자 사용 불가</li><li>같은 이름은 앱 수준과 계정 수준에서 모두 사용할 수 없습니다.</li><li>동일한 이름 **을** 앱 수준에서 사용할 수 있습니다. 예를 들어 위 시나리오에서는 ScoreGameA와 ScoreGameB가 있습니다.</li></ul> |
| <span id="format"></span>형식 | <ul><li>텍스트: 속성 값**이** 지정된 규칙 값과 같거나 **같지 않은지**를 시험합니다. 예: 크리켓인가 아닌가.</li><li>숫자: 속성 값이 지정된 규칙 값보다 큰지, 작은지, 혹은 같은지를 시험합니다. 예: 점수가 15보다 큼</li></ul> |
| <span id="level"></span>수준 | <ul><li>계정 수준: 속성이 앱과 관련이 없습니다.<br />예시: 성별, 좋아하는 스포츠</li><li>앱 수준: 속성이 앱과 관련이 있습니다. 속성과 연결된 앱을 선택하세요.</li></ul> |

</Accordion>

<div id="manage" />

<Accordion title="관리">

유저 속성을 관리하려면 **오디언스** > **유저 속성** 탭으로 이동하세요.

[alt오디언스유저속성\_us-en.pngalt](https://support.appsflyer.com/hc/article_attachments/30448652658961)

| 기능 | 설명 |
| --- | --- |
| <span id="search-and-filter"></span>검색 및 필터 | 속성 이름, 앱 이름, 속성 수준별로. |
| <span id="sort-by"></span>정렬 기준 | 표 행을 정렬하려면 열 머리글을 클릭하세요. |
| <span id="zd-import-data"></span><span id="import-data"></span>데이터 가져오기 | <ul><li>[CSV로 데이터 가져오기](/docs/audiences-create-better-audiences-with-user-attribute-data#import-data-by-csv)</li><li>[API로 데이터 가져오기](/docs/audiences-create-better-audiences-with-user-attribute-data#import-data-by-api)</li></ul> |
| <span id="change-api-import-key"></span>API 가져오기 키 변경 | **API 가져오기 키를 변경하려면:**<ol><li>**데이터 가져오기**를 클릭합니다.</li><li>**API**를 선택하세요.</li><li>**가져오기 키y** *새로고침*을 클릭합니다.</li></ol>**참고!** 스크립트에 내장된 키가 있는 경우 새 키로 업데이트하세요. |

</Accordion>

<div id="delete" />

<Accordion title="삭제">

![AppsFlyerAdmin_us-en.png](https://files.readme.io/d67fdedd94c56e8da776e590b12883503f47d36f0d58b996c4c64cc5d0e9c675-16281491712785.png) 어드민 유저만 속성을 삭제할 수 있습니다.

**규칙 세트에 있는 속성을 삭제하려면:**

1. 규칙 세트에서 속성을 제거합니다.
2. 속성을 삭제합니다.

</Accordion>

## 데이터 가져오기

<div id="import-field-specifications" />

<Accordion title="데이터 가져오기 필드 사양">

| 필드 | 콘텐츠 | 형식 | 데이터 추가  <br />CSV로 | CSV로 데이터 제거 |
| --- | --- | --- | --- | --- |
| <span id="device_id"></span>device\_id | 다음 유저 ID 중 하나를 포함합니다:<ul><li>IDFA</li><li>GAID</li></ul> | 텍스트 | **device\_id** 또는 **customer\_id**는 필수입니다. | **device\_id** 또는 **customer\_id**는 필수입니다.<br /><br />기존 데이터를 제거하려면 발송하지 마세요. |
| <span id="customer_id"></span>customer\_id | <Anchor target="_blank" href="/marketers/ko/docs/customer-user-id-field-cuid">고객 유저 ID</Anchor> | 텍스트 | **device\_id** 또는 **customer\_id**는 필수입니다. | **device\_id** 또는 **customer\_id**는 필수입니다.<br /><br />기존 데이터를 제거하려면 발송하지 마세요. |
| <span id="app_id"></span>app\_id | **앱 수준 속성:** 대시보드에 표시되는 앱 ID입니다.<br /><br />iOS 앱의 경우 접두사 *ID*를 포함합니다.<br /><br />**계정 수준 속성**: 항상 *로 채워주세요 | 텍스트 | 필수 | 필수 |
| <span id="attribute_key"></span>속성\_키 | 유저 속성 이름은 유저 속성 탭에 표시되는 이름과 정확히 같습니다. | 텍스트 | 필수 | 필수 |
| <span id="attribute_value"></span>속성값 | 할당된 값<br /><br />[*제한 사항 참조](/docs/audiences-create-better-audiences-with-user-attribute-data#limitations) | 텍스트 또는 숫자 | 필수 | 발송하지 마세요 |

</Accordion>

<div id="import-data-by-csv" />

<Accordion title="CSV로 데이터 가져오기">

유저 속성 데이터는 CSV 파일을 통해 추가되거나 제거됩니다. 다음 그림과 CSV 파일 예시는 이 문서에서 설명하는 기능과 일치합니다.

<Anchor target="_blank" href="https://support.appsflyer.com/hc/article_attachments/360012423857">유저 속성 예제.csv</Anchor>

![속성파일.png](https://files.readme.io/2a9075ab7f900648aeebe3b5fca807c6b931ba5295f35708ee6c48d345f681b9-33375704847633.png)

**CSV 파일 요구 사항**

* 헤더 행이 없습니다.
* 이전 표에 나열된 모든 열을 포함합니다.

**CSV 파일을 가져오려면:**

1. **오디언스** > **유저 속성** 탭으로 이동합니다.
2. **데이터 가져오기**를 클릭합니다.
3. **CSV**를 선택하세요.
4. 중 하나를 선택하세요:
   * **데이터 추가**
   * **데이터 제거**
5. 가져올 CSV 파일을 선택하세요.
6. **업로드**를 클릭하면 업로드 상태 메시지가 나타납니다.

**참고:** 유저 속성을 가져올 때 고객 ID와 연결된 모든 디바이스에도 해당 속성이 할당됩니다. 예를 들어, 유저가 "게임 점수" 속성을 customer\_id로 10개의 디바이스에 가져왔고, customer\_id 중 하나가 2개의 디바이스(즉, 동일한 CUID를 가진 2개의 GAID)와 연결된 경우, 이 가져오기에는 11개의 유저 속성 레코드가 포함됩니다.

</Accordion>

<div id="import-data-by-api" />

<Accordion title="API를 통한 데이터 가져오기">

이 가져오기 메서드에는 요청 URL과 유저 속성 데이터가 포함된 JSON이 필요합니다.

1. 대시보드에서 준비된 API 요청 및 JSON 템플릿을 가져옵니다.
2. [필드 사양](/docs/audiences-create-better-audiences-with-user-attribute-data#import-field-specifications)에 따라 JSON 템플릿에 귀사의 데이터를 채웁니다.

**API 요청 URL과 JSON 템플릿을 생성하려면:**

1. **데이터 가져오기**를 클릭합니다.
2. **API**를 선택하세요.
3. 작업을 선택하세요:  
   * 유저 속성 업데이트: 덮어쓰거나 추가합니다.
   * 유저 속성을 제거합니다.
   * 유저 데이터 제거: 특정 유저와 관련된 모든 데이터를 삭제합니다. 유저는 앱스플라이어 ID로 식별됩니다.
   * 앱 데이터 제거: 앱 수준의 모든 데이터를 제거합니다.
4. 발생한 API 요청 URL을 복사합니다.
5. 발생한 API 요청 본문을 복사합니다.
6. 지정된 JSON 형식으로 JSON(유저 속성 데이터 포함)을 준비합니다. 계정 수준 속성의 경우 "app\_ids"를 ["*"]로 설정합니다.
7. URL과 요청 본문을 기준으로 API 호출을 준비합니다.
8. 요청을 프로그래밍 방식으로 발송합니다.

**예시 요청 및 JSON**  

```json
https://hq1.appsflyer.com/api/user-attributes-import-api/set-user-data
{
  "import_key": "c733e4d7-b538-4d12-a2ef-ffffffffffff",
  "attributes_values": [
    {
      "device_id": "",
      "customer_id": "",
      "app_ids": [],
      "attributes": [
        {
          "attribute_key": "",
          "attribute_value": ""
        }
      ]
    }
  ]
}
```

<div id="note-1" />

> 📘 **참고**
>
> <Anchor target="_blank" href="/marketers/ko/docs/managing-appsflyer-tokens#광고주">API 토큰 V2.0</Anchor>을 사용하여 Authorization Bearer 헤더로 요청을 인증해야 합니다.

**여러 디바이스 ID, 속성 키 및 속성 값이 포함된 예시**

```json
{
    "import_key": "c733e4d7-b538-4d12-a2ef-ffffffffffff",
    "attributes_values": [
        {
            "device_id": "0bcfc579-f1f3-4452-9111f",
            "customer_id": "2222222",
            "app_ids": ["game.a.demo"],
            "attributes": [
                {
                    "attribute_key": "score",
                    "attribute_value": 5
                }
                ,
                {
                    "attribute_key": "favorite_sport",
                    "attribute_value": "cricket"
                }
            ]
        }
        ,
        {
            "device_id": "555555-d1d1-d1d1-555-fffffffff",
            "customer_id": "111111",
            "app_ids": ["game.a.demo"],
            "attributes": [
                {
                    "attribute_key": "order",
                    "attribute_value": 7
                }
                ,
                {
                    "attribute_key": "number",
                    "attribute_value": 8
                }
            ]
        }]
}
```

**하나의 디바이스 ID와 여러 속성 키 및 값을 포함한 예시**

```json
{
    "import_key": "c733e4d7-b538-4d12-a2ef-ffffffffffff",
    "attributes_values": [
        {
            "device_id": "0bcfc579-f1f3-4452-9111f",
            "customer_id": "12345678",
            "app_ids": ["game.a.demo"],
            "attributes": [
                {
                    "attribute_key": "score",
                    "attribute_value": 90
                }
                ,
                {
                    "attribute_key": "favorite-sport",
                    "attribute_value": "cricket"
                }
                ,
                {
                    "attribute_key": "orderNumber",
                    "attribute_value": 93
                }
                ,
                {
                    "attribute_key": "netPromoterScore",
                    "attribute_value": 94
                }
            ]
        }
    ]
}
```

**참고:** 유저 속성을 가져올 때, 고객 ID와 관련된 모든 알려진 디바이스에도 해당 속성이 할당됩니다. 예를 들어, 유저가 "게임 점수" 속성을 customer\_id로 10개의 디바이스에 가져왔고, customer\_id 중 하나가 2개의 디바이스(즉, 동일한 CUID를 가진 2개의 GAID)와 연결된 경우, 이 가져오기에는 11개의 유저 속성 레코드가 포함됩니다. CSV 가져오기 제한 사항

</Accordion>

<div id="limitations" />

<Accordion title="제한 사항">

<div id="general-limitations" />

#### 일반 제한 사항

* CSV/ API 가져오기 데이터는 정수(완전한 숫자)만 지원됩니다. 실수형(소수점) 숫자는 지원되지 않습니다. **예시:** "점수" 속성 값은 90이 될 수 있지만 90.5는 될 수 없습니다.
* 유저 속성 데이터는 출력하거나 다운로드할 수 없습니다.
* #### <span id="attribute-value-limitations"></span>속성 값 제한:

  * 속성 값에 쉼표, 점 또는 기타 특수 문자를 사용할 수 없습니다.
  * 문자열 속성 값의 길이는 40자로 제한됩니다.
  * 속성 값은 0으로 시작할 수 없습니다.

<div id="api-import-limitations" />

#### API 가져오기 제한

* 분당 최대 350개의 API 요청, 단일 속성의 경우 1만 개 디바이스, 두 개 속성의 경우 5천 개 디바이스 등
* `device_id`와 `customer_id` 키는 각각의 가져오기 요청에 필수입니다. 이 식별자 중 하나만 사용해서 속성을 가져오려면 다른 식별자의 "헤더"를 빈 문자열로 포함해야 합니다. 예를 들어, `device_id`별로 속성을 가져오고 `customer_id`는 제외하려면 호출은 다음과 같습니다:

```json
"attributes_values": [
{
"device_id": "39e123.......",
"customer_id": "",
```

<div id="csv-import-limitations" />

#### CSV 가져오기 제한 사항

* 유저 속성 값을 추가할 때 CSV 파일당 최대 1천만 개의 행이 허용됩니다.

</Accordion>

<div data-zendesk-anchors="user-attributes=%EC%82%AC%EC%9A%A9%EC%9E%90-%EC%86%8D%EC%84%B1%EC%97%90-%EA%B4%80%ED%95%98%EC%97%AC h_01HDNZH1XVX5BYQBPG848M8QZM=%EC%82%AC%EC%9A%A9%EC%9E%90-%EC%86%8D%EC%84%B1%EC%97%90-%EA%B4%80%ED%95%98%EC%97%AC scenario%E2%80%94app-marketer-requirements=scenario-app-marketer-requirements h_01HDNZH1XV8AWVVGNYVA9G4PAG=scenario-app-marketer-requirements scenario-user-attributes=%EC%8B%9C%EB%82%98%EB%A6%AC%EC%98%A4-%EC%82%AC%EC%9A%A9%EC%9E%90-%EC%86%8D%EC%84%B1 h_01HDNZH1XW32ZJJRSANBQCTBV0=%EC%8B%9C%EB%82%98%EB%A6%AC%EC%98%A4-%EC%82%AC%EC%9A%A9%EC%9E%90-%EC%86%8D%EC%84%B1 implement-user-attributes=%EC%9C%A0%EC%A0%80-%EC%86%8D%EC%84%B1-%EA%B5%AC%ED%98%84 h_01HDNZH1XWPBVDHJ7AGPT5ZM9W=%EC%9C%A0%EC%A0%80-%EC%86%8D%EC%84%B1-%EA%B5%AC%ED%98%84 h_01HDNZH1XWYA9TQZ1B342A661R=set-up h_01HDNZH1XW0PPJF78EVFQTW3R7=add h_01HDNZH1XWGZ04TQXD5D50771A=manage h_01HDNZH1XWP8P1ZVJX11AXCS2P=delete import-data::b50dc884=%EB%8D%B0%EC%9D%B4%ED%84%B0-%EA%B0%80%EC%A0%B8%EC%98%A4%EA%B8%B0 h_01HDNZH1XWCXV89YJV7EBJXNK5=%EB%8D%B0%EC%9D%B4%ED%84%B0-%EA%B0%80%EC%A0%B8%EC%98%A4%EA%B8%B0 h_01HDNZH1XW87W1PV4C3PMY9QD6=import-field-specifications h_01HDNZH1XW3XC893Q8BQZQW2AG=import-data-by-csv h_01HDNZH1XX7PMGNTD683DD2B49=import-data-by-api h_01HDNZH1XXF6DSNKG19ZRZ01AZ=%EC%B0%B8%EA%B3%A0 h_01HDNZH1XX61DVGK96C2TDSYW9=limitations general-limitations=%EC%9D%BC%EB%B0%98-%EC%A0%9C%ED%95%9C-%EC%82%AC%ED%95%AD h_01HDNZH1XXZZFA3WHZEE5N24AB=%EC%9D%BC%EB%B0%98-%EC%A0%9C%ED%95%9C-%EC%82%AC%ED%95%AD attribute-value-limitations=%EC%86%8D%EC%84%B1-%EA%B0%92-%EC%A0%9C%ED%95%9C h_01GZTGPK2FTHTV4NQ2HKV1HK00=%EC%86%8D%EC%84%B1-%EA%B0%92-%EC%A0%9C%ED%95%9C api-import-limitations=api-%EA%B0%80%EC%A0%B8%EC%98%A4%EA%B8%B0-%EC%A0%9C%ED%95%9C h_01HDNZH1XX4JWSMSF4672ENWNS=api-%EA%B0%80%EC%A0%B8%EC%98%A4%EA%B8%B0-%EC%A0%9C%ED%95%9C csv-import-limitations=csv-%EA%B0%80%EC%A0%B8%EC%98%A4%EA%B8%B0-%EC%A0%9C%ED%95%9C-%EC%82%AC%ED%95%AD h_01J3APYQ8MXG1SGREVN638R75N=csv-%EA%B0%80%EC%A0%B8%EC%98%A4%EA%B8%B0-%EC%A0%9C%ED%95%9C-%EC%82%AC%ED%95%AD" />
