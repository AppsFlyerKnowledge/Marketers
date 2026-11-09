---
title: Data Clean Room - 소스 작업
metadata:
  keywords:
    - Advertisers
    - Premium
    - Marketers
    - Data Clean Room
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-inbar-agassi
    - Marketers
    - Data Clean Room
  created_at: '2022-03-27T10:58:23Z'
  edited_at: '2026-10-14T10:34:42Z'
  id: 5041487011601
  locale: ko
  section: Data Clean Room
  section_id: 4591191779217
  url: https://support.appsflyer.com/hc/ko/articles/5041487011601
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **한눈에 보기:** 요약: DCR(Data Clean Room)과 공유하는 사용자 지정 데이터 소스를 설정하여 어트리뷰션 데이터와 일치시키고 DCR 리포트를 생성합니다.

<div id="introduction" />

## 소개

많은 DCR 리포트는 **어트리뷰션 데이터**를 **커스텀 소스**의 데이터와 일치시키도록 설계되었습니다. 본 기사에는 다음 방법을 포함하여 사용자 지정 소스 작업에 대해 알아야 할 모든 것이 포함되어 있습니다.

* DCR 내에서 [소스 생성](/docs/data-clean-room-working-with-sources#소스-만들기)
  * [소스 이름 지정](/docs/data-clean-room-working-with-sources#1-name-the-source)
  * DCR에서 소스 데이터를 검색할 [위치 지정](/docs/data-clean-room-working-with-sources#2-specify-the-source-location)
  * 소스의 [구조 정의](/docs/data-clean-room-working-with-sources#3-define-the-source-structure) (지표, 기준 및 식별자로 필드에 라벨 지정)
  * [소스 저장](/docs/data-clean-room-working-with-sources#4-save-the-source)
* 리포트 데이터를 트리거하기 위해 정기적으로 [소스 데이터 업데이트](/docs/data-clean-room-working-with-sources#리포트-처리를-트리거하기-위한-소스-업데이트)
* [기존 소스 작업](/docs/data-clean-room-working-with-sources#기존-소스로-작업하기)

<div id="important" />

> 🚧 **시작하기 전에**
>
> 커스텀 소스를 만들기 전에 먼저 다음을 수행해야 합니다.
>
> * [필수] DCR이 데이터를 검색할 <Anchor target="_blank" href="/marketers/ko/docs/data-clean-room-setting-up-cloud-services">클라우드 서비스를 설정합니다</Anchor>. 다음 두 가지 유형의 클라우드 서비스가 지원됩니다.
> * [선택사항] 앱스플라이어 플랫폼에서 <Anchor target="_blank" href="/marketers/ko/docs/data-clean-room-working-with-connections#creating-inbound-connections">인바운드 연결을 생성하여</Anchor> 이러한 클라우드 서비스를 DCR에 연결합니다.
>   * 이러한 연결이 이전에 설정되지 않은 경우 소스를 생성하는 동안 설정하라는 메시지가 표시됩니다.


<span id="data-format"></span><span id="source-requirements"></span><span id="source-format"></span>소스는 소스 생성 및 리포트 처리에서 오류를 방지하기 위해 다음 요구 사항을 충족해야 합니다.

소스 내의 데이터는 다음 요구 사항을 충족해야 합니다.

* **날짜와 시간:**
  * **형식:** yyyy-MMM-dd hh:mm:ss (*예시*, `2023-APR-18 15:30:35`2023-APR-18 15:30:352023-APR-18>)
  * 시간대 UTC
* **숫자:** 소수점 이하 최대 2자리
* **문자열 길이:** 최대 256자
* **문자 제한:**
  * **필드 이름(열 머리글):** 공백 또는 특수 문자 없음
  * 기타 모든 데이터: 제한 없음(모든 문자가 유효함)


<div id="table-columns" />

<Accordion title="테이블 열 (데이터 웨어하우스의 원본에만 관련됨)">

처리를 위해 공유되는 데이터 외에도 BigQuery 또는 Snowflake의 소스 테이블에는 2개의 추가 열인 **날짜** 및 버전이 포함되어야 합니다.

* **날짜:**
  * 열 머리글
  * **열 유형:** 날짜
  * **데이터 형식:** yyyy-mm-dd (*예*, `2023-04-18`2023-04-182023-04-18)
  * **추가:** 추가 사항: BigQuery 테이블은 상기 열로 <Anchor target="_blank" href="https://cloud.google.com/bigquery/docs/partitioned-tables">분할</Anchor>되어야 합니다.
* **버전:**
  * 열 머리글
  * **열 유형:** 문자열
  * **데이터 형식:** 숫자(예, `1`11, `2`22, `3`33, `10`1010)
  * **중요!** DCR이 이 열에서 새 값을 검색할 때마다 새 버전의 리포트가 트리거됩니다. 리포트의 완전성을 보장하려면 열 값이 변경될 때마다 원본 테이블을 전체 데이터 집합으로 채워야 합니다.

</Accordion>

<div id="file-format" />

<Accordion title="파일 이름 및 형식 (Cloud Storage 버킷의 소스에만 관련됨)">

Amazon S3 또는 GCS에 저장된 소스 파일은 다음 파일 이름 및 형식 요구 사항을 충족해야 합니다.

* 파일 이름은 <Anchor target="_blank" href="/marketers/ko/docs/data-clean-room-setting-up-cloud-services#dcr-naming-requirements">DCR 이름 지정 요구 사항</Anchor>을 준수해야 합니다.
* CSV 또는 GZIP 형식
  * GZIP 압축의 기반 파일은 CSV 파일이어야 합니다.
* [데이터 폴더](/docs/data-clean-room-working-with-sources#nested-subfolders-for-each-date-and-version)당 데이터 소스 파일 수:
  * **CSV:**
  * GZIP GZIP: 최대 1개의 단일 파트 파일.

</Accordion>

<div id="creating-a-source" />

## 소스 만들기

소스 생성 프로세스는 **아래에 설명한 모든 단계**로 구성됩니다. 이 단계는 읽기 쉽도록 탭으로 구분되어 있습니다.

**소스를 생성하려면 다음 단계를 따르십시오.**

<div id="1-name-the-source" />

<Accordion title="#1: 소스 이름 지정">

1. **Data Clean Room**의 **소스** 탭으로 이동합니다.
2. **+ 새 소스** 버튼을 클릭합니다.  
   **새 소스** 페이지가 열립니다.
3. 왼쪽 상단 모서리에 소스 이름을 입력합니다.
   * 이것은 DCR 플랫폼 내에서 소스를 식별하는 데 도움이 되는 고유한 이름일 수 있습니다.
   * **중요!** 소스 이름이 계정의 다른 모든 소스와 다른지 확인하십시오. 그렇지 않으면 소스를 저장할 수 없습니다.
   * 소스 이름 요구 사항:
     * 길이: 2&#126;80자
     * 유효한 문자:

       * 숫자 `(0-9)`(0-9) (0-9), *이름의 첫 문자가 될 수 없습니다.*
     * 유효하지 않은 문자:
       * 공백
       * 기타 모든 기호 또는 특수 문자

</Accordion>

<div id="2-specify-the-source-location" />

<Accordion title="#2: #2: 소스 위치 지정">

1. 소스가 생성될 (또는 생성된) <Anchor target="_blank" href="/marketers/ko/docs/data-clean-room-setting-up-cloud-services#개요">연결</Anchor>을 선택합니다.
   * 계정에 정의된 연결이 없는 경우 **새 연결** 대화 상자가 열리고 연결을 만들라는 메시지가 표시됩니다. <Anchor target="_blank" href="/marketers/ko/docs/data-clean-room-working-with-connections#개요">상기 지침</Anchor>에 따라 만드십시오.
   * 상기 지침에 따라 만드십시오.
2. 소스에 대한 데이터가 있는 위치에 따라 아래의 관련 지침을 따라 계속 진행합니다.

<div id="source-locations-in-bigquery" />

#### BigQuery의 소스 위치

BigQuery 소스의 소스 위치 지정을 완료하려면 다음 안내를 따르십시오.

1. 소스 테이블이 있는 데이터 집합을 선택합니다.
2. 소스 데이터가 있는 테이블을 선택합니다.

이러한 선택 목록에는 연결을 만들 때 지정한 BigQuery 프로젝트에서 각각 사용 가능한 데이터 세트와 테이블이 포함됩니다.

<div id="source-locations-in-snowflake" />

#### Snowflake의 소스 위치

**Snowflake 소스에 대한 소스 위치 지정을 완료하려면:**

1. 소스 데이터가 포함된 공유를 선택합니다.
2. 소스 테이블이 있는 스키마를 선택합니다.
3. 소스 데이터가 있는 테이블을 선택합니다.

이러한 선택 목록에는 연결을 생성할 때 지정한 Snowflake 계정의 공유, 스키마 및 테이블이 각각 포함됩니다.

<div id="important-1" />

<div id="source-locations-in-cloud-storage-buckets" />

#### Cloud Storage 버킷의 소스 위치

Amazon S3 또는 GCS의 소스 위치는 연결에서 지정한 클라우드 스토리지 버킷과 DCR이 업데이트될 때마다 소스 파일을 읽는 기본 폴더 경로로 구성됩니다.

연결을 지정하면 앱스플라이어는 소스 생성 프로세스의 일부로 필요한 기본 폴더 경로를 자동으로 생성할 수 있습니다.

**Cloud Storage 버킷에서 소스 위치 지정을 완료하려면 소스 폴더 이름을 입력합니다.**

* 기본적으로 표시된 소스 폴더 이름은 다음과 같습니다.
  * [소스에 지정한 이름](/docs/data-clean-room-working-with-sources#1-name-the-source)을 기반으로 합니다. <Anchor target="_blank" href="/marketers/ko/docs/data-clean-room-setting-up-cloud-services#dcr-naming-requirements">DCR 이름지정 요구 사항</Anchor>을 준수하는 한 필요에 맞게 폴더 이름을 변경할 수 있습니다.
  * **입력**이라는 상위 폴더 내에서 생성됨을 나타냅니다. 이 폴더는 DCR에 업로드하는 모든 소스의 상위 폴더 역할을 합니다.
    * **입력** 폴더는 필요하지 않으며 <Anchor target="_blank" href="/marketers/ko/docs/data-clean-room-setting-up-cloud-services#dcr-naming-requirements">DCR 이름지정 요구 사항</Anchor>을 준수하는 한 제거하거나 다른 이름을 지정할 수 있습니다.
    * 이 폴더가 필수는 아니지만 입력 폴더(또는 다른 이름의 동등한 폴더)를 가지는 것이 가장 좋은 방법입니다. 이 방법은 데이터 파일 업로드(입력)와 리포트 수신(출력)에 동일한 클라우드 스토리지 버킷을 사용하는 경우 더욱 권장됩니다.

> 🚧 **중요!**
>
> 폴더 경로를 수동으로 만든 경우 **소스 위치** 섹션에 입력한 연결 및 경로가 수동으로 만든 경로와 일치하는지 확인하십시오.

</Accordion>

<div id="3-define-the-source-structure" />

<Accordion title="#3: #3: 소스 구조 정의하기">

처리를 위해 DCR와 공유하는 모든 소스에 대해 앱스플라이어는 리포트를 생성하기 위해 각 데이터 필드를 어떻게 사용해야 하는지 알아야 합니다. 소스 구조 정의는 다음과 같이 구성됩니다.

* [소스 필드 로드하기](/docs/data-clean-room-working-with-sources#소스-필드-로드하기)
* [각 필드](/docs/data-clean-room-working-with-sources#필드-분류) (열)를 다음 유형 중 하나로 분류:
  * \_identifier 식별자: 고유한 앱 사용자를 식별하는 필드(예에는 CUID, 앱스플라이어 ID 등이 포함될 수 있음)./span>
    * DCR의 컨텍스트에서 식별자의 주요 목적은 해당 사용자 수준 데이터가 일치될 수 있도록 데이터 소스를 결합하는 것입니다.
  * **\_데이터 기준** 기준: 앱 사용자를 분류하는 속성(예를 들어 지역, 인스톨 날짜, 캠페인 등)/span>
  * 지표 지표: 앱 사용자와 관련하여 수집한 수치 데이터(예로는 수익, 앱 열기 횟수, LTV 등이 포함될 수 있음.)
    * 지표로 식별된 데이터 필드에는 숫자 값만 포함될 수 있습니다.

<div id="important-2" />

<div id="loading-source-fields" />

#### 소스 필드 로드하기

아래의 관련 지침을 사용하여 소스 필드를 로드합니다.

**데이터 웨어하우스 소스**

> 🚧 **중요!**
>
> 선택한 소스 테이블에 필요한 [날짜 및 버전 열](/docs/data-clean-room-working-with-sources#table-columns)이 포함되어 있지 않으면 오류가 발생합니다.

**Cloud Storage 버킷 소스**

클라우드 스토리지 버킷(Amazon S3 또는 GCS)에 있는 소스에서 필드를 로드하려면 프로토타입 소스 파일을 업로드해야 합니다.

소스 구조를 정의하기 위해:

* 로컬 파일에서 소스의 프로토타입 버전을 업로드할 수 있습니다.
  * 이 옵션을 선택하면 앱스플라이어는 항상 소스 폴더 경로를 자동으로 생성합니다.

                                                                또는

* 해당 연결에서 직접 소스 파일의 프로토타입 버전을 업로드할 수 있습니다.
  * 이 옵션을 선택하면 다음을 추가로 선택할 수 있습니다.
    * 앱스플라이어가 소스 폴더 구조를 자동으로 생성하도록 허용하거나
    * 소스 폴더 구조를 수동으로 생성하도록 합니다

**프로토타입 소스 파일을 업로드하려면 아래 관련 탭의 지침을 따르십시오.**

<Tabs>
<Tab title="로컬 파일">

2. 열리는 창에서 **로컬 파일 업로드**를 선택합니다.
3. 업로드하려는 CSV 또는 GZIP 파일을 지정한 다음 확인을 클릭합니다.

</Tab>

<Tab title="연결(자동 생성)">

연결에서 파일을 로드하고 앱스플라이어가 소스 폴더 구조를 생성하도록 허용하려면:

2. 열린 창에서 **연결에서 로드**를 선택합니다.
3. **폴더 생성** 링크를 클릭합니다.
   * 앱스플라이어는 필요한 폴더 구조와 소스 폴더를 자동으로 생성합니다(지정한 소스 폴더 이름으로 지정한 연결에).
4. 소스 폴더 구조가 생성되면 소스 폴더에 대한 링크를 포함하여 확인 메시지가 표시됩니다. 제공된 링크를 클릭하여 소스 폴더에 프로토타입 파일을 업로드합니다.
5. 파일 업로드가 완료되면 **확인**을 클릭합니다.

</Tab>

<Tab title="연결(수동 생성)">

**수동으로 생성한 구조에서 소스 파일을 업로드하려면:**

2. 열린 창에서 **연결에서 로드**를 선택합니다.
3. **폴더 생성**을 클릭하지 **마십시오**. 대신 파일을 위해 만든 소스 폴더에 직접 파일을 업로드하십시오.
4. 파일 업로드가 완료되면 **확인**을 클릭합니다.

</Tab>
</Tabs>

<div id="note" />

<div id="categorize-fields" />

#### 필드 분류

필드를 로드하면 앱스플라이어가 파일을 분석하고 모든 데이터 필드(열)의 목록이 **사용 가능한 필드** 목록에 표시됩니다.

**필드 분류 방법:**

1. 왼쪽에 있는 **사용 가능한 필드** 목록에서 필드를 하나 이상 선택하고 화면 중앙에 있는 버튼을 사용하여 필드를 [식별자, 기준 또는 지표](/docs/data-clean-room-working-with-sources#3-define-the-source-structure)로 분류합니다.
   * 필드를 분류하면 결과가 화면 오른쪽의 해당 카테고리 목록에 표시됩니다.
   * 검색 창을 사용하여 목록에서 필드를 검색할 수 있습니다.
   * 할당된 카테고리에서 필드를 제거하려면 관련 카테고리 목록에서 필드를 선택하고 **제거** 버튼을 사용하여 **사용 가능한 필드** 목록으로 돌아갑니다.
2. DCR 리포트에 포함하려는 각 필드를 분류할 때까지 이 프로세스를 반복합니다.
   * **사용 가능한 필드** 목록의 모든 필드를 분류할 필요는 없습니다. 그러나 나중에 리포트에 사용하려면 필드를 분류해야 합니다.
3. [소스를 저장](/docs/data-clean-room-working-with-sources#4-save-the-source)하기 전에 소스를 편집하고 편집된 소스 데이터의 필드를 사용하려면 **사용 가능한 필드** 목록 아래에 있는 **필드 재로드** 링크를 클릭합니다.
   * 소스를 다시 로드하면 사용 가능 필드 목록에 필드 이름을 덮어쓴다는 것을 알아두십시오. 이전에 분류한 모든 필드는 **식별자,** **기준** 또는 **지표** 목록에 남아 있습니다.
   * 이전에 분류된 필드가 다시 로드된 소스 데이터에 없는 경우 관련 카테고리 목록에 계속 표시되지만 오류 아이콘과 함께 표시됩니다.

> 📘 **참고사항**
>
> 이 소스를 저장한 후 해당 추가 필드를 사용하기로 결정한 경우 [소스 구조를 편집](/docs/data-clean-room-working-with-sources#editing-the-source-structure)하여 사용할 수 있습니다.

</Accordion>

<div id="4-save-the-source" />

<Accordion title="#4: 소스 저장">

**소스 저장 방법:**

2. **저장**을 클릭하여 소스를 저장합니다.

   소스가 생성되고 확인 메시지가 표시됩니다.

   * 로컬 파일에서 소스를 업로드한 경우 소스를 저장하면 폴더 구조가 자동으로 생성되고 표시되는 확인 메시지에 소스 폴더에 대한 링크가 포함됩니다.

   새 소스는 Data Clean Room의 **소스** 탭에 있는 모든 기존 소스 목록에 표시됩니다.

</Accordion>

<div id="updating-sources-to-trigger-report-processing" />

## 리포트 처리를 트리거하기 위한 소스 업데이트

앱스플라이어가 데이터 소스 파일을 처리하고 이를 기반으로 리포트를 실행하도록 하려면 날짜 및 버전 번호를 나타내는 일련의 중첩 하위 폴더 내에서 새 버전의 파일을 소스 폴더로 업로드해야 합니다(앱스플라이어에 데이터 위치를 알려주는 하나의 하위 폴더 추가).

앱스플라이어는 **현재 날짜와 2일 전**에 대한 새 버전의 소스 파일을 지속적으로 검색합니다. 새 버전의 소스 파일이 발견될 때마다 새 버전의 리포트가 발생합니다([\_SUCCESS 파일](/docs/data-clean-room-working-with-sources#_success-files) 포함, 아래에 자세히 설명).

<div id="nested-subfolders-for-each-date-and-version" />

<Accordion title="각 날짜 및 버전에 대해 중첩된 하위 폴더">

중첩된 하위 폴더의 구조는 다음과 같습니다.

* 소스 폴더 내 --> 각 날짜에 대한 1개의 하위 폴더("날짜 폴더")
  * 형식
  * <strong>`dt=2022-12-15/` dt=2022-12-15/</strong>예시
* 각 날짜 폴더 내 --> 해당 날짜의 각 버전에 대한 1개의 하위 폴더("버전 폴더")
  * 형식
  * <strong>`v=1/` v=1/</strong>예시
  * **참고:** 일러두기: 하루에 한 번만 파일을 업로드하더라도 버전 폴더는 필수입니다.
* 각 버전 폴더 내 --> 데이터 위치를 나타내는 1개의 하위 폴더("데이터 폴더")
  * 형식
  * 데이터 폴더는 소스 파일이 업로드되는 위치입니다.

대부분의 경우 API 호출 또는 기타 사용 가능한 프로그래밍 방식을 사용하여 데이터 소스 파일이 업로드될 때마다 날짜/버전/데이터 폴더를 자동으로 생성합니다. 추가 정보는 클라우드 서비스에 대한 API 참조( AWS, GCS)를 참조하십시오.

</Accordion>

<div id="_success-files" />

<Accordion title="_SUCCESS 파일">

소스 파일을 데이터 폴더로 업로드하는 것이 완료되면 `_SUCCESS`\_SUCCESS\_SUCCESS라는 빈 파일을 **버전** 폴더에 업로드해야 합니다. 이를 통해 새 파일을 처리할 수 있음을 앱스플라이어에 알립니다. 대부분의 경우 API 스크립트를 사용하여 이 파일을 자동으로 생성하고 업로드하게 됩니다.

**중요!** \_SUCCESS 파일은 데이터 폴더 외부의 `_SUCCESS`버전\_SUCCESS 폴더에 업로드됩니다.

\_SUCCESS 파일의 파일 이름:

* 모두 대문자여야 합니다.
* 밑줄`(_)`(\_) (\_)이 앞에 와야 합니다.
* 파일 확장자가 없어야 합니다.

다중 파트 GZIP 파일의 경우:

* `_SUCCESS`\_SUCCESS\_SUCCESS 파일은 모든 파일 부분 업로드가 완료된 후에만 업로드해야 합니다.

</Accordion>

<div id="example-after-uploading-files" />

<Accordion title="예시(파일 업로드 후)">

2일 동안 소스 파일을 업로드하고 (프로그래밍 방식으로 날짜/버전/데이터 폴더 및 `_SUCCESS`\_SUCCESS\_SUCCESS 파일을 생성한 후) 버킷/폴더는 다음과 같은 구조를 가질 수 있습니다.

<Image align="center" alt="dcr_file_structure_after_uploads.png" src="https://files.readme.io/f6e753cdf8389c0b99cad9cbf1a06261473ef87ce6f840a21ab8d9ccea20aed4-11420299723665.png" width="308px" />

</Accordion>

<div id="important-3" />

<div id="working-with-existing-sources" />

## 기존 소스로 작업하기

기존 소스로 작업할 수 있는 방법에는 여러 가지가 있습니다. Data Clean Room의 **소스** 탭에서 다음 프로세스를 시작합니다.

* [소스 이름 편집](/docs/data-clean-room-working-with-sources#editing-the-source-name)
* [소스 구조 편집](/docs/data-clean-room-working-with-sources#editing-the-source-structure)
* [소스 삭제](/docs/data-clean-room-working-with-sources#deleting-a-source) (리포트에 사용되지 않는 경우)

<div id="editing-the-source-name" />

<Accordion title="소스 이름 편집">

소스 이름을 편집하는 방법:

1. **Data Clean Room**의 **소스** 탭으로 이동합니다.
2. 소스 목록에서 편집하려는 소스 행 위로 마우스를 가져갑니다.
4. **소스 편집** 페이지에서 소스 이름을 편집합니다.
5. **저장** 버튼을 클릭하여 소스를 새 이름으로 저장하거나 **취소**를 클릭하여 변경 사항을 취소합니다.

</Accordion>

<div id="editing-the-source-structure" />

<Accordion title="소스 구조 편집">

소스 구조를 편집하는 방법:

1. **Data Clean Room**의 **소스** 탭으로 이동합니다.
2. 소스 목록에서 편집하려는 소스 행 위로 마우스를 가져갑니다.
4. **소스 편집** 페이지의 화면 오른쪽의 관련 카테고리 목록에 이전에 [식별자, 기준 또는 지표](/docs/data-clean-room-working-with-sources#3-define-the-source-structure)로 분류되었던 필드가 표시됩니다.
5. 소스 파일에서 필드를 다시 로드하지 않고 이전에 분류된 필드를 다른 카테고리로 이동할 수 있습니다. 설정 방법:
   1. 먼저 관련 카테고리 목록에서 그것을 선택하고 **제거** 버튼을 사용하여 **사용 가능한 필드** 목록으로 되돌립니다.
   2. 다음으로 **사용 가능한 필드** 목록에서 그것을 선택하고 화면 중앙에 있는 버튼을 사용하여 식별자, 기준 또는 지표로 분류합니다.
6. 아직 분류되지 않은 소스 파일의 필드로 작업하려면 소스 위치 또는 로컬 파일에서 필드에서 다시 로드해야 합니다. **사용 가능한 필드** 목록 하단에 있는 **필드 재로드** 링크를 클릭하여 선택합니다.
7. 앱스플라이어는 파일을 분석하고 이전에 분류되지 않은 모든 데이터 필드(열) 목록이 **사용 가능한 필드** 목록에 표시됩니다.
   * 이전에 식별자, 기준 또는 지표로 분류된 필드는 화면 오른쪽의 관련 카테고리 목록에 계속 표시됩니다.
   * 이전에 분류된 필드가 다시 로드된 소스 파일에 없는 경우 관련 카테고리 목록에 계속 표시되지만 오류 아이콘과 함께 표시됩니다.
8. 왼쪽에 있는 **사용 가능한 필드** 목록에서 필드를 하나 이상 선택하고 화면 중앙에 있는 버튼을 사용하여 필드를 식별자, 기준 또는 지표로 분류합니다.
9. 필요한 사항을 모두 변경했으면 **저장** 버튼을 클릭하여 업데이트된 구조로 소스를 저장하거나 **취소**를 클릭하여 변경 사항을 취소합니다.

> 🚧 **중요!**
>
> 이 소스가 사용되는 리포트에서 새 소스 구조를 반영하여 해당 변경을 수행해야 합니다.
>
> * 제거되었거나 분류되지 않았거나 이전 카테고리에서 변경된 필드는 해당 필드가 사용된 모든 리포트에서 자동으로 제거됩니다.
> * 새로 추가되거나 분류된 필드는 포함하도록 리포트 정의를 편집할 때까지 기존 리포트에 자동으로 포함되지 않습니다.

</Accordion>

<div id="deleting-a-source" />

<Accordion title="소스 삭제">

1. **Data Clean Room**의 **소스** 탭으로 이동합니다.
2. 소스 목록에서 삭제하려는 소스 행 위로 마우스를 가져갑니다.
4. 대화 상자에서 소스를 삭제하려 한다는 것을 확인합니다.
   * 리포트에서 사용 중인 소스는 삭제할 수 없습니다. 이 경우 메시지에 소스를 사용하는 리포트가 나열됩니다. 소스를 삭제하려면 다음 중 한 가지를 수행할 수 있습니다.
     * 사용 중인 리포트를 삭제합니다. 또는
     * 사용되는 리포트의 정의에서 소스 필드를 제거하십시오.

</Accordion>

<div id="reference" />

## 참고

<div id="manually-creating-a-folder-structure" />

<Accordion title="수동으로 스토리지 버킷 폴더 구조 만들기 (그렇게 하도록 선택한 경우에만 관련됨)">

일반적으로 앱스플라이어가 소스 생성 프로세스의 일부로 필요한 폴더 구조를 자동으로 생성하도록 허용하는 것이 가장 쉽습니다. 그러나 이러한 폴더를 수동으로 만들려면 다음과 같이 해야 할 수 있습니다.

<div id="create-a-dcr-key-folder" />

#### DCR 키 폴더 만들기

최대 보안을 보장하려면 버킷 바로 아래에 있는 폴더("DCR 키 폴더")의 이름을 계정에 할당된 8자의 영숫자 **DCR 키**(예: `01bcc5fb`01bcc5fb01bcc5fb )로 지정해야 합니다. *이는 AppsFlyer 계정과 연결된 다른 비밀번호 또는 키와는 다릅니다.*

DCR 키 폴더는 일반적으로 선택한 클라우드 서비스의 인터페이스를 사용하여 수동으로 생성합니다.

**계정의 DCR 키를 얻으려면 기본 DCR 페이지 상단에 있는 DCR 키 버튼을 클릭하십시오.**

<Image align="center" alt="dcr_key_button.png" src="https://files.readme.io/8d02c129ce45b19b28523419e43ec8227a9179e3bafb2b84c0a523b247061c19-16571022734353.png" />

DCR 키 폴더를 생성한 후 버킷/폴더는 다음과 같은 구조를 가져야 합니다.

<Image align="center" alt="dcr_file_structure_dcr_key_folder.png" src="https://files.readme.io/a57ba8076a2af5ef1f5a8339ac6b24e1ab6f8ff60956013a0a6547320a13072f-16571304308497.png" width="308px" />

<div id="top-level-input-folder" />

#### 최상위 입력 폴더

필수 사항은 아니지만 가장 좋은 방법은 DCR 키 폴더 바로 아래에 최상위 입력 폴더를 만드는 것입니다. 이 폴더는 DCR에 업로드하는 파일을 위한 전용 폴더입니다.

최상위 입력 폴더는 일반적으로 선택한 클라우드 서비스의 인터페이스를 사용하여 수동으로 생성합니다.

* 이 방법은 데이터 파일 업로드(입력) 및 보고서 수신(출력)에 동일한 버킷을 사용하는 경우 더욱 강력히 권장됩니다.
* <Anchor target="_blank" href="/marketers/ko/docs/data-clean-room-setting-up-cloud-services#dcr-naming-requirements">DCR 이름 지정 요구 사항</Anchor>을 준수하는 조건에서는 이 폴더의 이름을 원하는 대로 지정할 수 있습니다. 쉽게 식별할 수 있도록 일반적으로 이름을 input/로 명명합니다.

최상위 입력 폴더를 만든 후 버킷/폴더는 다음과 같은 구조를 가질 수 있습니다.

<Image align="center" alt="dcr_file_structure_input_folder.png" src="https://files.readme.io/cb7249ee0cbc0b4721c701f7d735c73eb7acc0a2a9e73de102b5a5ec9a6a79fd-16571312292753.png" width="308px" />

<div id="second-level-folder-for-each-data-source" />

#### 각 데이터 소스의 두 번째 수준 폴더

다양한 데이터 소스 파일을 정기적으로 DCR에 업로드하여 처리할 수 있습니다. 이러한 각 데이터 소스에는 별도의 폴더("데이터 소스 폴더")가 할당되어야 합니다.

데이터 소스 폴더는 일반적으로 선택한 클라우드 서비스의 인터페이스를 사용하여 수동으로 생성합니다.

2개의 데이터 소스 폴더를 생성한 후 버킷/폴더는 다음과 같은 구조를 가질 수 있습니다.

<Image align="center" alt="dcr_file_structure_source_folders.png" src="https://files.readme.io/f4624a213b79978d8ec080551649fae72d04d2f58a78344fc9df74a859881549-16571312297361.png" width="307px" />

각 데이터 소스 폴더에서 소스가 업데이트될 때마다 [날짜 및 버전별로 중첩된 하위 폴더](/docs/data-clean-room-working-with-sources#nested-subfolders-for-each-date-and-version)를 만들어야 합니다.

</Accordion>

<div data-zendesk-anchors="introduction=%EC%86%8C%EA%B0%9C h_01HPKB2ERNRQG73AFA0X7XEDEF=%EC%86%8C%EA%B0%9C h_01HPKB2ERPGD2PS4JBSDGYW3MC=%EC%8B%9C%EC%9E%91%ED%95%98%EA%B8%B0-%EC%A0%84%EC%97%90 h_01HPKB2ERPANE0CAXFP9RG5YEH=source-format h_01HPKB2ERPJ5PVQ2QM5XCYZE0D=table-columns h_01HPKB2ERPWZFZN2DSCHWNXKXX=file-format creating-a-source=%EC%86%8C%EC%8A%A4-%EB%A7%8C%EB%93%A4%EA%B8%B0 h_01HPKB2ERPX2T413N3T93YBBZB=%EC%86%8C%EC%8A%A4-%EB%A7%8C%EB%93%A4%EA%B8%B0 h_01HPKB2ERPQMT0NKTE5NN40KG4=1-name-the-source h_01HPKB2ERQWDMYBEPDZY17T9PG=2-specify-the-source-location source-locations-in-bigquery=bigquery%EC%9D%98-%EC%86%8C%EC%8A%A4-%EC%9C%84%EC%B9%98 h_01HPKB2ERQ28JQ2CK16RYZ38G6=bigquery%EC%9D%98-%EC%86%8C%EC%8A%A4-%EC%9C%84%EC%B9%98 source-locations-in-snowflake=snowflake%EC%9D%98-%EC%86%8C%EC%8A%A4-%EC%9C%84%EC%B9%98 h_01HPKB2ERQWFGF8MN8ZYAXWC87=snowflake%EC%9D%98-%EC%86%8C%EC%8A%A4-%EC%9C%84%EC%B9%98 source-locations-in-cloud-storage-buckets=cloud-storage-%EB%B2%84%ED%82%B7%EC%9D%98-%EC%86%8C%EC%8A%A4-%EC%9C%84%EC%B9%98 h_01HPKB2ERQZT3Y6GNZ2WWWM0M7=cloud-storage-%EB%B2%84%ED%82%B7%EC%9D%98-%EC%86%8C%EC%8A%A4-%EC%9C%84%EC%B9%98 h_01HPKB2ERQK2HFDATGKV0X7GCG=%EC%A4%91%EC%9A%94 h_01HPKB2ERQ40VTVZA5DGNR907G=3-define-the-source-structure loading-source-fields=%EC%86%8C%EC%8A%A4-%ED%95%84%EB%93%9C-%EB%A1%9C%EB%93%9C%ED%95%98%EA%B8%B0 h_01HPKB2ERQTJPGG68FSEBHVVJA=%EC%86%8C%EC%8A%A4-%ED%95%84%EB%93%9C-%EB%A1%9C%EB%93%9C%ED%95%98%EA%B8%B0 h_01HPKB2ERRZNPYVVD8GHD7PBPE=%EC%A4%91%EC%9A%94-1 categorize-fields=%ED%95%84%EB%93%9C-%EB%B6%84%EB%A5%98 h_01HPKB2ERSYCFE1EYTCK550VTK=%ED%95%84%EB%93%9C-%EB%B6%84%EB%A5%98 h_01HPKB2ERSNT8Y9QPN03HJKHCD=%EC%B0%B8%EA%B3%A0%EC%82%AC%ED%95%AD h_01HPKB2ERS55YGWY3RMRPR02Y4=4-save-the-source uploading-source-files-to-trigger-report-processing=%EB%A6%AC%ED%8F%AC%ED%8A%B8-%EC%B2%98%EB%A6%AC%EB%A5%BC-%ED%8A%B8%EB%A6%AC%EA%B1%B0%ED%95%98%EA%B8%B0-%EC%9C%84%ED%95%9C-%EC%86%8C%EC%8A%A4-%EC%97%85%EB%8D%B0%EC%9D%B4%ED%8A%B8 h_01HPKB2ERSCPAPB6WE3354ECW9=%EB%A6%AC%ED%8F%AC%ED%8A%B8-%EC%B2%98%EB%A6%AC%EB%A5%BC-%ED%8A%B8%EB%A6%AC%EA%B1%B0%ED%95%98%EA%B8%B0-%EC%9C%84%ED%95%9C-%EC%86%8C%EC%8A%A4-%EC%97%85%EB%8D%B0%EC%9D%B4%ED%8A%B8 h_01HPKB2ERSEVBTS3DR2TB6Y1AQ=nested-subfolders-for-each-date-and-version h_01HPKB2ERSJ9KNDK6CEBRQB65C=_success-files h_01HPKB2ERSJKGVE61T6J9HXTCK=example-after-uploading-files working-with-existing-sources=%EA%B8%B0%EC%A1%B4-%EC%86%8C%EC%8A%A4%EB%A1%9C-%EC%9E%91%EC%97%85%ED%95%98%EA%B8%B0 h_01HPKB2ERS5PK2P2XTC4ZMPCMC=%EA%B8%B0%EC%A1%B4-%EC%86%8C%EC%8A%A4%EB%A1%9C-%EC%9E%91%EC%97%85%ED%95%98%EA%B8%B0 h_01HPKB2ERTC48MGS0BM5SDR6XV=editing-the-source-name h_01HPKB2ERTS6DEQX0KP0EQTGSP=editing-the-source-structure h_01HPKB2ERTYP6BFAESN3MHZSQG=%EC%A4%91%EC%9A%94-2 h_01HPKB2ERVGJYJ9KW1RGX24CGV=deleting-a-source reference=%EC%B0%B8%EA%B3%A0 h_01HPKB2ERV1KK3J8YX918GCF3M=%EC%B0%B8%EA%B3%A0 h_01HPKB2ERVZ88MJ35JC66YDPAB=manually-creating-a-folder-structure creating-a-dcr-key-folder=dcr-%ED%82%A4-%ED%8F%B4%EB%8D%94-%EB%A7%8C%EB%93%A4%EA%B8%B0 h_01HPKB2ERV7MQJ9CK44T92GK2G=dcr-%ED%82%A4-%ED%8F%B4%EB%8D%94-%EB%A7%8C%EB%93%A4%EA%B8%B0 toplevel-input-folder=%EC%B5%9C%EC%83%81%EC%9C%84-%EC%9E%85%EB%A0%A5-%ED%8F%B4%EB%8D%94 h_01HPKB2ERVPG4R9FHWZPQ8TCZQ=%EC%B5%9C%EC%83%81%EC%9C%84-%EC%9E%85%EB%A0%A5-%ED%8F%B4%EB%8D%94 secondlevel-folder-for-each-data-source=%EA%B0%81-%EB%8D%B0%EC%9D%B4%ED%84%B0-%EC%86%8C%EC%8A%A4%EC%9D%98-%EB%91%90-%EB%B2%88%EC%A7%B8-%EC%88%98%EC%A4%80-%ED%8F%B4%EB%8D%94 h_01HPKB2ERVVFMP81RE8ATZ6SZ8=%EA%B0%81-%EB%8D%B0%EC%9D%B4%ED%84%B0-%EC%86%8C%EC%8A%A4%EC%9D%98-%EB%91%90-%EB%B2%88%EC%A7%B8-%EC%88%98%EC%A4%80-%ED%8F%B4%EB%8D%94" />
