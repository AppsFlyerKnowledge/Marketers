---
title: 데이터 협업 플랫폼(Data Collaboration Platform, DCP) - 협업 측정 준비
metadata:
  keywords:
    - Marketers
    - Data Management
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-yael-sharabi
    - Marketers
    - Data Management
  created_at: '2025-01-27T08:47:05Z'
  edited_at: '2026-10-14T10:30:56Z'
  id: 32144170371985
  locale: ko
  section: Collaboration measurement
  section_id: 38034865098641
  url: https://support.appsflyer.com/hc/ko/articles/32144170371985
---
> **한눈에 보기:** 측정 데이터 소스를 생성하는 방법과, 이를 어트리뷰션 작업이 활용할 수 있는 형태로 제공하는 방법을 알아보세요.

<div id="overview" />

## 개요

측정 프로세스를 설정하는 첫 번째 단계는, 세 가지 입력값인 전환, 인게이지먼트, 캠페인 매핑을 준비하는 것입니다. 이러한 입력값은 데이터 제공 모드(인앱 이벤트 또는 사용자 정의 소스 파일)에 따라 사전 정의된 스키마 또는 이벤트 구조를 기반으로 준비되어야 합니다.

제공 모드가 사용자 지정 소스 파일일 경우, 필요한 변환 및 인게이지먼트 기록 폴더가 클라우드에 업로드되면 어트리뷰션 작업이 자동으로 트리거됩니다. 인앱 이벤트 모드의 경우, 관련 인앱 이벤트가 선택되면 작업이 트리거됩니다.

<div id="prepare-in-app-events" />

## 인앱 이벤트 준비

귀하의 앱에 연동된 앱스플라이어 SDK가 전송하는 인앱 이벤트를 통해 전환 및 인게이지먼트 데이터를 전송할 수 있습니다.

<div id="note" />

> 📘 **참고**
>
> SDK 또는 서버-to-서버 요청을 통해 앱스플라이어 인앱 이벤트를 이미 전달하고 있다면, 이 옵션이 사용자 정의 소스 파일 옵션보다 구현하기 더 쉬울 수 있습니다.

<div id="prepare-conversion-inapp-events" />

<Accordion title="전환 인앱 이벤트 준비">

전환 인앱 이벤트는 SKU 정보를 포함해야 합니다. 다음 예시에서는, `af_order_info` 키가 SKU 정보를 식별합니다:

```
"event_value": {
    "af_currency": "EUR",
    "af_content": "retail",
    "af_order_id": "637f7c400f0e3fddd9e5bcbc",
    "af_order_info": [
        {
            "sku": "a",
            "revenue": 1.1,
            "qty": 2
        },
        {
            "sku": "b",
            "revenue": 100.5,
            "qty": 1
        }
    ]
}
```

인앱 이벤트를 준비하는 방법에 대한 자세한 내용은 아래의 [인앱 이벤트 생성하기](#create-inapp-events) 섹션을 참조하세요.

</Accordion>

<div id="prepare-engagement-inapp-events" />

<Accordion title="리인게이지먼트 인앱 이벤트">

<Anchor target="_blank" href="/marketers/ko/docs/data-collaboration-platform-dcp-collaboration-measurement-overview#온사이트-및-오프사이트-캠페인-측정">현장 캠페인은</Anchor> 인앱 이벤트를 통해 인게이지먼트를 유도할 수 있습니다. 인앱 이벤트 인게이지먼트는 `event_value` 키 내에 어트리뷰션 데이터를 포함해야 합니다. 다음의 `event_value` JSON 구조를 살펴보세요:

```
"event_value": {
    "media_source": "onsite",
    "campaign_name": "winter_bags",
    "campaign_id": "637f7c400f0e3fddsdfaafe33",
    "engagement_type": "click"
}
```

아래 필드를`evant_value` JSON 키에 사용할 수 있습니다:

| **필드** | **설명** | **필수** | **인앱 이벤트 체계 내에서 사용 가능** | **유형** |
| --- | --- | --- | --- | --- |
| `campaign_id` | 캠페인 ID | 예 | 아니요 | `string` |
| `campaign_name` | 캠페인 이름 | 아니요 | 아니요 | `string` |
| `engagement_type` | 클릭과 노출 구분 | 예 | 아니요 | `string` |
| `media_source` | 이벤트에 어트리뷰션되거나 제한된 미디어 소스(<Anchor target="_blank" href="/marketers/ko/docs/about-raw-data-identifier-restrictions#미디어-소스-제한">자세히 보기</Anchor>) | 예 | 아니요 | `string` |
| `ad_id` | 광고 ID | 아니요 | 아니요 | `string` |
| `ad_name` | 광고 이름 | 아니요 | 아니요 | `string` |
| `ad_type` | 예: 배너, 꼬리말(footer) | 아니요 | 아니요 | `string` |
| `adset_id` | 하나 이상의 광고가 포함된 그룹을 식별하는 광고 세트 ID | 아니요 | 아니요 | `string` |
| `adset_name` | 하나 이상의 광고가 포함된 그룹을 식별하는 광고 세트 이름 | 아니요 | 아니요 | `string` |
| `channel` | 미디어 소스 채널 예시: Google의 YouTube, Meta Ads의 인스타그램 | 아니요 | 아니요 | `string` |

인앱 이벤트를 준비하는 방법에 대한 자세한 내용은 아래의 인앱 이벤트 생성하기 섹션을 참조하세요.

</Accordion>

<div id="create-inapp-events" />

<Accordion title="인앱 이벤트 생성하기">

인앱 이벤트를 통해 전환 및 인게이지먼트 데이터를 제공하려면 앱에 연동된 AppsFlyer SDK를 설정하십시오. 인앱 이벤트 생성에 대한 자세한 내용은 다음을 참조하세요:

* <Anchor target="_blank" href="/marketers/ko/docs/in-app-events-overview">인앱 이벤트 개요</Anchor>
* <Anchor target="_blank" href="http://dev.appsflyer.com/hc/docs/in-app-events-sdk">개발자를 위한 앱스플라이어 SDK 내 인앱 이벤트 구현</Anchor>

</Accordion>

<div id="background-colors" />

<div id="media-partners" />

<div id="prepare-custom-source-files" />

## 커스텀 소스 파일 준비

[현장 캠페인](#onsite-and-offsite-campaign-measurement)을 운영 중인 경우, 아래 표에 명시된 방식을 사용하여 전환 및 인게이지먼트의 소스로 사용자 정의 소스 파일을 활용할 수 있습니다.

<div id="the-conversion-source-scheme" />

<Accordion title="전환 소스 스킴">

아래 표의 방식을 사용하여 변환 사용자 정의 소스 파일을 생성하십시오:

| **필드** | **설명** | **사용자 정의 데이터 소스에 반드시 필요** | **기대값 유형** | **데이터 유효성 검사** |
| --- | --- | --- | --- | --- |
| `appsflyer_id` | 앱이 디바이스에 설치될 때 SDK에 의해 생성된 고유 ID입니다. 이 ID는 인앱 이벤트를 추적하고, 전환 데이터를 수집하며, 인앱 이벤트를 연계하는 데 사용됩니다. 앱을 삭제하고 다시 설치하면 새로운 ID가 생성됩니다. iCloud 백업에서 앱을 복원하는 것은 설치로 간주되지 않습니다. CTV의 경우, 이 필드는 광고주가 관리하는`custom_device_id`로 채워집니다. | 선택적 PII 필드 PII 필드 중 하나는 필수입니다. | 문자열 | 없음 |
| `advertising_id` | 사용자가 재설정 가능한 디바이스 ID, 일명 GAID CTV의 경우, 예를 들어, RIDA 또는 VIDA가 CTV ID입니다. | 선택적 PII 필드 PII 필드 중 하나는 필수입니다. | 문자열 | 없음 |
| `cuid` | 앱 소유주가 설정한 고유한 앱 유저 ID입니다. | 선택적 PII 필드 PII 필드 중 하나는 필수입니다. | 문자열 | 없음 |
| `android_id` | 영구 디바이스 ID | 선택적 PII 필드 PII 필드 중 하나는 필수입니다. | 문자열 | 없음 |
| `idfa` | iOS 디바이스에서 유저가 재설정할 수 있는 광고 ID. `idfa` 가 사용 불가능한 경우, 일반적으로 0으로 채워집니다. | 선택적 PII 필드 PII 필드 중 하나는 필수입니다. | 문자열 | 없음 |
| `idfv` | iOS가 제공하는 공급업체 ID | 선택적 PII 필드 PII 필드 중 하나는 필수입니다. | 문자열 | 없음 |
| `event_name` | 앱에서 전송한 어트리뷰션 이벤트 유형 또는 인앱 이벤트 이름 예시 이벤트 유형: 인스톨, 리인게이지먼트 등. 리타깃팅 리포트의 데이터 로커인 경우: 리타깃팅은 리인게이지먼트를 의미하며, 인스톨은 리어트리뷰션을 의미합니다. SKAN의 경우, 인앱 이벤트 이름은 앱스플라이어혹은 Meta Ads에 설정된 이름입니다. | 필수 | 문자열 | 없음 |
| `event_time` | 이벤트 시간은 가장 가까운 시간으로 반올림됨 | 필수 | 날짜 및 시간 | 없음 |
| `sku` | 전환 이벤트에 포함된 항목 중 하나의 스톡 키핑 유닛(SKU) ID | 필수 | 문자열 | 없음 |
| `sku_quantity` | 전환 이벤트에 포함된 SKU 단위 수. | 필수 | 정수 | 없음 |
| `app_id` | 앱스플라이어의 고유한 앱 식별자. 예: iOS: id123456789, 안드로이드: com.appsflyer.referrersender | 선택 사항 | 문자열 | 없음 |
| `app_name` | 광고주가 설정 | 선택 사항 | 문자열 | 없음 |
| `app_version` | 광고주가 설정 | 선택 사항 | 문자열 | 없음 |
| `city` | 디바이스 IP를 기반으로 한 유저의 가장 정밀한 위치 일반적으로 도시명을 포함하지만, 구나 자치구도 포함될 수 있음. | 선택 사항 | 문자열 | 없음 |
| `country_code` | ISO 3166 (alpha-2)를 사용하는 국가 코드입니다. 예시: 미국, 중국 참고: 영국은 GB가 아닌 UK로 표시됨. | 선택 사항 | 문자열 | 없음 |
| `device_category` | 가능한 값: phone, tablet, other | 선택 사항 | 문자열 | 없음 |
| `event_currency` | SDK에 보고된 이벤트 수익 통화 코드입니다. | 선택 사항 | 문자열 | DCR 포멧 요건에 부합하는 시간, 날짜 구성 |
| `event_revenue` | 이벤트 수익 통화를 사용한 수익값 $-10,000에서 $+10,000(또는 이에 상응하는 금액) 범위를 벗어난 금액은 로데이터에는 표시되지만 집계 보고서에는 표시되지 않습니다. | 선택 사항 | decimal | 없음 |
| `platform` | 기기 플랫폼: iOS, 안드로이드, 또는 Windows Mobile | 선택 사항 | 문자열 | 없음 |
| `region` | SDK에 의해 리포트된 디바이스 IP 주소 기반. SKAN의 경우,`country_code`에 의해 결정됩니다. | 선택 사항 | 문자열 | 없음 |
| `sku_revenue` | 해당 `event_revenue_currency` 필드에 지정된 통화로 표시된 SKU 관련 매출액 | 선택 사항 | decimal | 없음 |
| `state` | SDK에 의해 리포트된 디바이스 IP 주소 기반. | 선택 사항 | 문자열 | 없음 |

</Accordion>

<div id="the-engagement-source-scheme" />

<Accordion title="인게이지먼트 소스 스킴">

아래 스키마를 사용하여 인게이지먼트 데이터 소스를 생성하십시오.

<div id="note-1" />

> 📘 **참고**
>
> 인게이지먼트 소스 스키마에 매핑된 개인 식별 정보(PII) 필드는 위의 전환 소스 스키마에 매핑된 PII와 교집합을 가져야 합니다.

| **필드** | **설명** | 필수 | **기대값 유형** |
| --- | --- | --- | --- |
| `appsflyer_id` | 앱 설치 시 SDK에서 생성된 고유 ID | 선택적 PII 필드 PII 필드 중 하나는 필수입니다. | `string` |
| `cuid` | 앱 소유주가 설정한 고유한 앱 유저 ID입니다. | 선택적 PII 필드 PII 필드 중 하나는 필수입니다. | `string` |
| `idfa` | iOS 디바이스에서 유저가 재설정할 수 있는 광고 ID. 사용 불가능한 경우, 0으로 채워집니다. | 선택적 PII 필드 PII 필드 중 하나는 필수입니다. | `string` |
| `idfv` | iOS가 제공하는 공급업체 ID | 선택적 PII 필드 PII 필드 중 하나는 필수입니다. | `string` |
| `app_id` | 앱스플라이어의 고유한 앱 식별자. 예시: iOS: `id123456789`, 안드로이드: `com.appsflyer.referrersender` | 선택 사항 | `string` |
| `campaign_id` | 캠페인 ID | 필수 | `string` |
| `campaign_name` | 캠페인 이름 | 선택 사항 | `string` |
| `media_source` | 이벤트에 어트리뷰션되거나 제한된 미디어 소스(<Anchor target="_blank" href="/marketers/ko/docs/about-raw-data-identifier-restrictions#미디어-소스-제한">자세히 보기</Anchor>) | 필수 | `string` |
| `engagement_type` | 클릭과 노출 구분 | 필수 | `string` |
| `event_name` | 광고주가 설정 | 필수 | `string` |
| `event_time` | 이벤트 시간은 가장 가까운 시간으로 반올림됨 | 필수 | `datetime` |
| `app_name` | 광고주가 설정 | 선택 사항 | `string` |
| `app_version` | 광고주가 설정 | 선택 사항 | `string` |
| `ad_id` | 광고 ID | 선택 사항 | `string` |
| `ad_name` | 광고 이름 | 선택 사항 | `string` |
| `ad_type` | 예: 배너, 꼬리말(footer) | 선택 사항 | `string` |
| `adset_id` | 하나 이상의 광고가 포함된 그룹을 식별하는 광고 세트 ID | 선택 사항 | `string` |
| `adset_name` | 하나 이상의 광고가 포함된 그룹을 식별하는 광고 세트 이름 | 선택 사항 | `string` |
| `channel` | 미디어 소스 채널 예시: Google의 YouTube, Meta Ads의 인스타그램 | 선택 사항 | `string` |
| `platform` | 기기 플랫폼: iOS, 안드로이드, 또는 Windows Mobile | 선택 사항 | `string` |

</Accordion>

소스를 준비하고 클라우드 서비스에 업로드하는 방법에 대한 자세한 내용은 본 문서의 [사용자 지정 데이터 소스 생성 및 연결](#커스텀-데이터-소스-생성-및-연결) 섹션을 참조하십시오.

<div id="prepare-campaign-mapping-source" />

## 캠페인 매핑 소스 준비

캠페인 매핑 데이터의 출처는 아래 표에 설명된 스키마를 가진 사용자 지정 데이터 소스 파일입니다.

<div id="note-2" />

> 📘 **참고**
>
> 모든 협업에 단일 매핑 파일을 사용하는 것을 권장합니다. 이는 유지 관리 및 업데이트가 더 쉽기 때문입니다.

<div id="the-campaign-mapping-scheme" />

<Accordion title="캠페인 매핑 스킴">

아래 스키마를 사용하여 인게이지먼트 데이터 소스를 생성하십시오.

| **필드 유형** | **필수** | **기대값 유형** | **설명** |
| --- | --- | --- | --- |
| collaborator\_name | 예 | 문자열 | 협업자의 이름 |
| collaborator\_id | 예 | 문자열 | 협업자에 대한 고유 식별자 |
| campaign\_id | 예 | 문자열 | 캠페인에 대한 고유 식별자 |
| conversion\_targets | 예 | 문자열 배열 | 캠페인 대상 SKU를 쉼표로 구분한 목록을 받는 매개변수입니다. (예: sku1, sku2 등) |

</Accordion>

소스를 생성하고 클라우드 서비스에 업로드하는 방법에 대한 자세한 내용은 본 문서의 [사용자 지정 데이터 소스 생성 및 연결](#커스텀-데이터-소스-생성-및-연결) 섹션을 참조하십시오.

<div id="attribution-job-ingestion-flow" />

## 어트리뷰션 작업 수집 흐름

각 어트리뷰션 작업은 단 하루로 할당되며 해당 날짜가 종료된 후 실행됩니다. 이 프로세스의 시작 단계에서, 작업은 클라우드 서비스 또는 인앱 이벤트로부터 관련 전환, 인게이지먼트 및 캠페인 매핑 데이터를 수집합니다.

<div id="campaign-mapping-source-ingestion" />

<Accordion title="캠페인 매핑 소스 수집">

각 어트리뷰션 실행 전에 DCP는 사용자 지정 소스에서 캠페인 매핑 레코드를 로드합니다. 해당 기록을 불러오는 데는 두 가지 모드 중에서 선택할 수 있습니다:

* **최신 전략**: DCP는 레코드 업로드 날짜를 기준으로 가장 최근의 레코드를 가져옵니다.

  예를 들어, 소스 데이터에 업로드 날짜가 1월 18일, 1월 17일 또는 12월 29일인 레코드가 포함된 경우, 시스템은 1월 18일 날짜를 가진 레코드를 선택합니다.
* **일일 전략**: DCP는 업로드 날짜가 어트리뷰션 실행 날짜와 일치하는 레코드만 처리합니다. 예를 들어, 실행이 1월 19일 자정에 발생하면 시스템은 업로드 날짜가 1월 19일인 캠페인 레코드만 선택합니다.

</Accordion>

<div id="conversion-source-ingestion" />

<Accordion title="전환 소스 수집">

매일 종료 시점에 DCP는 해당 날짜 전용 폴더와 그 안의 전환 기록에 접근할 수 있는 경우에만 해당 일자의 어트리뷰션 분석 작업을 실행합니다. 그러나 특정 날짜의 폴더는 나중에 업로드할 수 있습니다. 예를 들어, 1월 17일 폴더를 1월 22일에 업로드할 수 있습니다.

* 매일 종료 시점에 DCP는 해당 일자의 어트리뷰션을 실행합니다. 해당 작업은 **DCP가 해당 날짜의 폴더를 찾을 수 있을 때만 실행됩니다**. 폴더 이름은 해당 일자와 동일합니다.
* 해당 일자 폴더에는 폴더 생성일로부터 30일 전까지의 이벤트 기록이 포함될 수 있습니다. 예를 들어, 1월 17일 폴더에서는 작업이 12월 18일부터 1월 17일까지의 기록을 처리합니다.
* 특정 날짜의 폴더 업로드를 건너뛰면, 30일 이내에 업로드할 수 있습니다. 예를 들어, 1월 17일 폴더 업로드를 건너뛴 경우 2월 17일까지 업로드할 수 있습니다. 그러나 폴더 날짜에 최대한 가깝게 업로드하는 것을 권장합니다.
* DCP가 당일 폴더를 찾지 못하면, 이후 7일간 매 10분마다 해당 폴더를 계속 검색합니다.

</Accordion>

<div id="engagement-source-ingestion" />

<Accordion title="인게이지먼트 소스 수집">

각 전환 레코드에 대해 DCP는 해당 전환을 유발한 인게이지먼트 이벤트를 검색합니다.

* 인게이지먼트 기록은 날짜가 기재된 폴더에 포함되어 있습니다. 그러나 매일 인게이지먼트 폴더를 업로드할 필요는 없습니다. 예를 들어, 1월 14일 폴더를 업로드하지 않고 1월 13일과 1월 15일 폴더만 업로드할 수 있습니다. 이 예시에서는 1월 14일의 기록을 1월 15일 폴더에서 가져옵니다.
* **주어진 전환 폴더에 대한 어트리뷰션은 전환 폴더와 동일한 날짜 또는 이후 날짜를 가진 인게이지먼트 폴더가 존재할 경우에만 시작됩니다.** 예를 들어, 1월 17일 **전환** 폴더에 대한 어트리뷰션은 1월 17일 인게이지먼트 폴더 또는 1월 18일과 같이 17일 이후 날짜의 폴더가 존재할 경우에만 시작됩니다.
* 어트리뷰션 작업은 어트리뷰션 룩백 기간 내에 발생한 모든 인게이지먼트 이벤트를 수집합니다.

</Accordion>

<div id="inapp-data-ingestion" />

<Accordion title="인앱 데이터 수집">

전환 및 인게이지먼트 데이터는 인앱 이벤트, 맞춤 소스 또는 둘의 조합에서 비롯될 수 있습니다. DCP를 사용하면 단일 모드를 사용할지 혼합할지 선택할 수 있어, 전환은 인앱 이벤트에서 발생하고, 인게이지먼트는 사용자 정의 파일에서 가져오거나 그 반대의 방식으로 설정할 수 있습니다.

전환, 인게이지먼트 또는 둘 다에 대한 인앱 이벤트를 구성할 때는 앱 ID와 전환 또는 인게이지먼트 이벤트 이름을 반드시 지정해야 합니다. 결국 어트리뷰션 작업은 지정된 이름과 앱 ID를 가지며 전환일과 동일한 이벤트 날짜를 가진 모든 이벤트를 선택합니다.

</Accordion>

<div id="create-and-connect-custom-data-sources" />

## 커스텀 데이터 소스 생성 및 연결

사용자 지정 소스를 통해 데이터를 연결하려면 다음의 DCP 지식 기반 문서 지침을 따라야 합니다:

* <Anchor target="_blank" href="/marketers/ko/docs/data-collaboration-platform-dcp-set-up-your-cloud-services">데이터 협업 플랫폼 — 클라우드 서비스를 설정하세요</Anchor>
* <Anchor target="_blank" href="/marketers/ko/docs/data-collaboration-platform-dcp-add-connections">데이터 협업 플랫폼 — 연결을 추가하세요</Anchor>
* <Anchor target="_blank" href="/marketers/ko/docs/data-collaboration-platform-dcp-create-and-manage-sources">데이터 협업 플랫폼 — 소스를 생성하고 관리하세요</Anchor>

<div data-zendesk-anchors="overview=%EA%B0%9C%EC%9A%94 h_01JJKFW5Z2D7Y1MM5A7YR0TY0T=%EA%B0%9C%EC%9A%94 prepare-inapp-events-for-conversions-and-engagements=%EC%9D%B8%EC%95%B1-%EC%9D%B4%EB%B2%A4%ED%8A%B8-%EC%A4%80%EB%B9%84 h_01JJKFW5Z22DG4CKFMXPGR3BW0=%EC%9D%B8%EC%95%B1-%EC%9D%B4%EB%B2%A4%ED%8A%B8-%EC%A4%80%EB%B9%84 h_01JJKFW5Z2NP9187GYHS0YEXED=%EC%B0%B8%EA%B3%A0 h_01JJKFW5Z2AX7SHHZ23P0KDQJY=prepare-conversion-inapp-events h_01JJKFW5Z2YD0B151VSR3TG6SP=prepare-engagement-inapp-events h_01JJKFW5Z3QES9BAZX7KNSPCM8=create-inapp-events prepare-custom-source-files-for-engagements-and-conversions=%EC%BB%A4%EC%8A%A4%ED%85%80-%EC%86%8C%EC%8A%A4-%ED%8C%8C%EC%9D%BC-%EC%A4%80%EB%B9%84 h_01JJKFW5Z3QX33NK3XP452AAFB=%EC%BB%A4%EC%8A%A4%ED%85%80-%EC%86%8C%EC%8A%A4-%ED%8C%8C%EC%9D%BC-%EC%A4%80%EB%B9%84 h_01JK3QFQCK30A7SSPWXSH3VP0D=the-conversion-source-scheme h_01JK3QFQCKD1TV5G4N0KP85AWS=the-engagement-source-scheme h_01JK3QFQCK6C16SCW8EYQNS47F=%EC%B0%B8%EA%B3%A0-1 prepare-campaign-mapping-source=%EC%BA%A0%ED%8E%98%EC%9D%B8-%EB%A7%A4%ED%95%91-%EC%86%8C%EC%8A%A4-%EC%A4%80%EB%B9%84 h_01JJKFW5Z3QR107P3M111P4STG=%EC%BA%A0%ED%8E%98%EC%9D%B8-%EB%A7%A4%ED%95%91-%EC%86%8C%EC%8A%A4-%EC%A4%80%EB%B9%84 h_01JJKFW5Z3ZSYET4HMWD7TWSD8=%EC%B0%B8%EA%B3%A0-2 h_01JJKFW5Z3Q6F3DP0EMTNQRD8R=the-campaign-mapping-scheme prepare-data-for-attribution-job-ingestion=%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%EC%9E%91%EC%97%85-%EC%88%98%EC%A7%91-%ED%9D%90%EB%A6%84 h_01JJKFW5Z38W581F4CBW3T4CPZ=%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%EC%9E%91%EC%97%85-%EC%88%98%EC%A7%91-%ED%9D%90%EB%A6%84 h_01JK5R1VPJ0WAF3WX4R1ECE0R7=campaign-mapping-source-ingestion h_01JK5R1VPJT41RF2EN8806ZY5C=conversion-source-ingestion h_01JK5R1VPJN8KTFTN21DA3619Y=engagement-source-ingestion h_01JK5R1VPJV6F5Y5JB3Q45R89B=inapp-data-ingestion create-and-connect-custom-data-sources=%EC%BB%A4%EC%8A%A4%ED%85%80-%EB%8D%B0%EC%9D%B4%ED%84%B0-%EC%86%8C%EC%8A%A4-%EC%83%9D%EC%84%B1-%EB%B0%8F-%EC%97%B0%EA%B2%B0 h_01JJKFW5Z3NKB0MB7GN2FC87H5=%EC%BB%A4%EC%8A%A4%ED%85%80-%EB%8D%B0%EC%9D%B4%ED%84%B0-%EC%86%8C%EC%8A%A4-%EC%83%9D%EC%84%B1-%EB%B0%8F-%EC%97%B0%EA%B2%B0" />
