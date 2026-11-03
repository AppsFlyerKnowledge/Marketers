---
title: 데이터 협업 플랫폼 — 소스를 생성하고 관리하세요
metadata:
  keywords:
    - Marketers
    - Audience Activation
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-yael-sharabi
    - Marketers
    - Audience Activation
  created_at: '2024-05-02T13:56:27Z'
  edited_at: '2026-10-14T10:27:36Z'
  id: 24740010687249
  locale: ko
  section: Data Collaboration Platform
  section_id: 26230608274065
  url: https://support.appsflyer.com/hc/ko/articles/24740010687249
---
> **한눈에 보기:** 다른 공동 작업자와 안전하게 자사 데이터를 공유할 수 있도록 소스를 생성하고 관리하세요.

## DCP 소스에 대하여

데이터 협업 플랫폼(DCP)에서 소스 데이터 세트를 의미하며, 일반적으로 클라우드 스토리지에서 앱스플라이어 로 업로드된 데이터 세트입니다. 이러한 자료들은 모든 협업의 기반을 형성하며, 협업자들이 잠재 고객을 발굴하고 활성화하는 데 사용할 수 있는 데이터를 제공합니다. 이 문서에는 소스를 생성하고 관리하는 데 필요한 모든 정보가 포함되어 있습니다.

* [소스 데이터 요구 사항](#소스-데이터-요구-사항)
* [소스 생성](#소스-생성하세요)
* [소스 관리하기](#소스를-관리하세요)

> 🚧 **시작하기 전에**
>
> 소스를 생성하기 전에 먼저 다음 사항을 확인해야 합니다.
>
> * 앱스플라이어 DCR이 소스 데이터를 가져올 <Anchor target="_blank" href="/marketers/ko/docs/data-collaboration-platform-dcp-set-up-your-cloud-services">클라우드 서비스를 설정하십시오</Anchor> . 이러한 연결이 설정되어 있지 않으면 소스 생성 중에 연결을 설정하라는 메시지가 표시됩니다.

## 소스 데이터 요구 사항

협업자 데이터 세트 간의 일치율을 극대화하고 협업 결과를 최적화하다 하려면 <Anchor target="_blank" href="/marketers/ko/docs/data-collaboration-platform-dcp-prepare-source-data-for-ingestion">소스 데이터를 준비하는</Anchor> 것이 좋습니다. 또한 모든 자료는 **다음 요건을 충족해야 합니다** .

<div id="data-format" />

<Accordion title="데이터 형식 (모든 소스와 관련됨)">

소스 내의 데이터는 다음 요구 사항을 충족해야 합니다.

* **날짜** (만) : yyyy-mm-dd (예:`2023-04-18` )
* **날짜와 시간:**
  * **형식:** yyyy-MMM-dd hh:mm:ss (*예시*, `2023-APR-18 15:30:35`2023-APR-18 15:30:352023-APR-18>)
  * 시간대: UTC
* **숫자:** 소수점 이하 최대 2자리
* **문자열 길이:** 최대 256자
* **문자 제한:**
  * **필드 이름(열 머리글):** 공백 또는 특수 문자 없음
  * **기타 모든 데이터:** 제한 없음(모든 문자가 유효함)

</Accordion>

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

* 파일 이름은 <Anchor target="_blank" href="/marketers/ko/docs/data-collaboration-platform-dcp-set-up-your-cloud-services#dcr-naming-requirements">DCR 이름 지정 요구 사항</Anchor>을 준수해야 합니다.
* CSV 또는 GZIP 형식
  * GZIP 압축의 기반 파일은 CSV 파일이어야 합니다.
* <Anchor target="_blank" href="/marketers/ko/docs/data-collaboration-platform-dcp-add-connections#snowflake-outbound">데이터 폴더</Anchor>당 데이터 소스 파일 수:
  * **CSV:** 최대 1개
  * **GZIP:** GZIP: 최대 1개의 단일 파트 파일. 다음과 같이 파일 이름이 지정된 경우 여러 부분으로 구성된 GZIP 파일이 지원됩니다.`filename_part01.csv.gz` ,`filename_part02.csv.gz` , 등.

</Accordion>

## 소스 생성하세요

DCP에서 소스 생성하려면 아래 단계를 따르세요.

<div id="step-1-set-source-name" />

<Accordion title="1단계: DCP 소스에 액세스">

1. 앱스플라이어 에서 측면 메뉴의 **공동 작업** > **데이터 \_x0008\_클린룸** 선택합니다.

   <Image alt="Click Data Clean Room.png" src="https://files.readme.io/2dc54e035b17aafa17b7eb4c526643284aa7979919f8caa0add13b7e6ae19e0c-41945704690065.png" width="34.12%" />
2. 메인 페이지 또는 **소스** 탭에서 **+ 새 소스** 클릭하세요.

   <Image alt="소스 빈 상태 잘린.png" src="https://files.readme.io/629d8c7c68bfbce7c2307306128b0d0cc430886dc2a58200cb635bc0044d2bd7-33193030142609.png" width="43.08%" />
3. **새 소스** 설치 절차를 진행하세요.

</Accordion>

<div id="h_01K1ZHNZEQWRP7ZBK7XJP5F9HA" />

<Accordion title="2단계: 소스 이름 설정">

소스 이름을 입력하세요. 소스 식별하는 데 돕다 되는 고유한 이름이면 어떤 것이든 가능합니다. 출처를 쉽게 식별 돕다 있도록 소스 에 대한 설명을 선택적으로 추가할 수도 있습니다(예: "2025년 이후 모든 구매 내역").

#### 요구 사항 및 지침

* 계정에 있는 다른 모든 소스 중에서 **소스 이름이** 고유한지 확인하십시오. 그렇지 않으면 소스 저장할 수 없습니다.
* 클라우드 통합의 경우, 이름이 파일 이름과 일치할 필요는 없습니다.
* 소스 이름 요구 사항:
  * 길이: 2&#126;80자
  * 유효한 문자:
    * 편지 `(A-Z, a-z)`
    * 숫자 `(0-9)`(0-9) (0-9), *이름의 첫 문자가 될 수 없습니다*
    * 밑줄,
  * 유효하지 않은 문자:
    * 공백
    * 기타 모든 기호 또는 특수 문자

</Accordion>

<div id="step-2-set-source-location" />

<Accordion title="3단계: 소스 위치 설정">

**소스 위치를 지정하는 방법:**

1. 소스가 생성될 (또는 생성된) <Anchor target="_blank" href="/marketers/ko/docs/data-collaboration-platform-dcp-set-up-your-cloud-services#overview">연결</Anchor>을 선택합니다.
   * 계정에 정의된 연결이 없는 경우 **새 연결** 대화 상자가 열리고 연결을 만들라는 메시지가 표시됩니다. <Anchor target="_blank" href="/marketers/ko/docs/data-collaboration-platform-dcp-add-connections">상기 지침</Anchor>에 따라 만드십시오.
   * 기존 연결이 있지만 새 연결을 사용하려면 **'+ 새 연결'을** 클릭 <Anchor target="_blank" href="/marketers/ko/docs/data-clean-room-working-with-connections">다음 지침에</Anchor> 따라 연결을 생성하세요.
2. 소스에 대한 데이터가 있는 위치에 따라 아래의 관련 지침을 따라 계속 진행합니다.

**참고:** 데이터 양이 많을 때 최상의 성과 위해 데이터의 일부를 별도로 저장할 수 있습니다. 이 데이터는 소스 업데이트될 때마다 업데이트되고 소스 삭제될 때 삭제됩니다.

#### BigQuery의 소스 위치

**BigQuery 소스의 소스 위치 지정을 완료하려면 다음 안내를 따르십시오.**

1. 소스 테이블이 있는 데이터 집합을 선택합니다.
2. 소스 데이터가 있는 테이블을 선택합니다.

이러한 선택 목록에는 연결을 만들 때 지정한 BigQuery 프로젝트에서 각각 사용 가능한 데이터 세트와 테이블이 포함됩니다.

#### Snowflake의 소스 위치

**Snowflake 소스에 대한 소스 위치 지정을 완료하려면:**

1. 소스 데이터가 포함된 공유를 선택합니다.
2. 소스 테이블이 있는 스키마를 선택합니다.
3. 소스 데이터가 있는 테이블을 선택합니다.

이러한 선택 목록에는 연결을 생성할 때 지정한 Snowflake 계정의 공유, 스키마 및 테이블이 각각 포함됩니다.

#### Cloud Storage 버킷의 소스 위치

Amazon S3 또는 GCS의 소스 위치는 연결에서 지정한 클라우드 스토리지 버킷과 DCR이 업데이트될 때마다 소스 파일을 읽는 기본 폴더 경로로 구성됩니다.

연결을 지정하면 앱스플라이어는 소스 생성 프로세스의 일부로 필요한 기본 폴더 경로를 자동으로 생성할 수 있습니다.

* 앱스플라이어 폴더를 생성하도록 허용하면 프로세스가 간편해집니다. 하지만 <Anchor target="_blank" href="/marketers/ko/docs/data-collaboration-platform-dcp-set-up-your-cloud-services">여기 자세히 설명된</Anchor> 지침에 따라 수동으로 생성하는 방법을 선택할 수도 있습니다.

앱스플라이어 폴더를 생성하는 경우, 추가로 필요한 정보는 **소스 폴더에 지정할 이름뿐입니다.** (이 폴더는 새 리포트 버전을 작동하는 때마다 소스 를 업데이트하는 최상위 폴더입니다.) 소스 폴더를 상위 폴더 ( 일반적으로 input이라는 이름) 아래에 생성할지 여부를 표시하다 수도 있습니다 .

**Cloud Storage 버킷에서 소스 위치 지정을 완료하려면 소스 폴더 이름을 입력합니다.**

* 기본적으로 표시된 소스 폴더 이름은 다음과 같습니다.
  * [소스에 지정한 이름](#1-name-the-source)을 기반으로 합니다. <Anchor target="_blank" href="/marketers/ko/docs/data-collaboration-platform-dcp-set-up-your-cloud-services#dcr-naming-requirements">DCR 이름지정 요구 사항</Anchor>을 준수하는 한 필요에 맞게 폴더 이름을 변경할 수 있습니다.
  * **입력**이라는 상위 폴더 내에서 생성됨을 나타냅니다. 이 폴더는 DCR에 업로드하는 모든 소스의 상위 폴더 역할을 합니다.
    * **입력** 폴더는 필요하지 않으며 <Anchor target="_blank" href="/marketers/ko/docs/data-collaboration-platform-dcp-set-up-your-cloud-services#dcr-naming-requirements">DCR 이름지정 요구 사항</Anchor>을 준수하는 한 제거하거나 다른 이름을 지정할 수 있습니다.
    * 이 폴더가 필수는 아니지만 **입력** 폴더(또는 다른 이름의 동등한 폴더)를 가지는 것이 가장 좋은 방법입니다. 이 방법은 데이터 파일 업로드(입력)와 리포트 수신(출력)에 동일한 클라우드 스토리지 버킷을 사용하는 경우 더욱 권장됩니다.

> 🚧 **중요!**
>
> 폴더 경로를 수동으로 만든 경우 **소스 위치** 섹션에 입력한 연결 및 경로가 수동으로 만든 경로와 일치하는지 확인하십시오.


#### 소스 위치는 로컬 파일입니다.

로컬 파일을 사용하여 소스 데이터를 업로드할 수도 있습니다. 하지만 **클라우드 서비스를 소스 위치로 설정하는 것이 강력히 권장됩니다** (대규모 데이터 세트 및 자동 업데이트에 필수적). 로컬 파일은 주로 테스트 목적으로 사용되며 플랫폼 기능을 익히는 데 도움이 됩니다.

**로컬 파일을 사용하여 소스 데이터를 업로드하려면 다음 단계를 따르세요.**

소스 위치를 선택할 때 **'로컬 파일 시스템'을** 클릭 하고 **'다음'을** 클릭하면 기기에서 로컬 파일을 업로드하는 옵션이 추가됩니다.

<Image alt="로컬 파일 시스템을 선택하세요.png" src="https://files.readme.io/08f4797196c915b73a543c7152b5090913287c61b12fefe893d3893ca76fc4d5-33193021989393.png" width="731px" />

> 📘 **참고사항**
>
> * 지원되는 파일 형식: CSV 및 .GZ 파일(최대 크기 5GB).
> * 로컬 파일에서 업로드된 데이터는 180일 동안 저장됩니다.
> * 업데이트는 수동으로 수행해야 합니다.

</Accordion>

<div id="step-3-set-source-update-method" />

<Accordion title="4단계: 소스 업데이트 방법을 설정합니다.">

데이터 협업 플랫폼(DCP)에서 소스 설정할 때 해당 소스 에 대한 업데이트를 처리하는 방법을 선택해야 합니다. DCP는 두 가지 동기화 방식을 지원합니다. **스냅샷** 및 **추가** . 각 방법은 서로 다른 사용 사례와 데이터 흐름에 적합합니다.

* **스냅샷** - 이 방법은 소스 업데이트될 때마다 전체 데이터 세트를 업로드하여 이전 데이터 세트를 새 데이터 세트로 완전히 대체합니다. 파일 업로드가 항상 전체 최신 데이터 세트를 포함하는 경우에만 선택하십시오.
* **추가** - 이 방법은 전체 데이터 세트가 아닌 새롭거나 변경된 데이터만 업로드합니다. 오래된 데이터 세트는 삭제되거나 업데이트되지 않습니다. 일일 또는 주간 보고서와 같은 반복 업로드에 이상적입니다. 이점으로는 업로드 용량 감소(클라우드 스토리지 비용 유도하다 가능성 있음), 데이터 업로드 성과 향상, 간편한 기록 관리 등이 있습니다.

<Image alt="Delta Generate folders.png" src="https://files.readme.io/105f55ff555565e97b82ecf86d58cfd2cf2a0340f83d6261fd3bd1c084b13889-38096875288977.png" width="637px" />

> 🚧 **중요!**
>
> 선택하기 전에 어떤 방법이 가장 적합한지 먼저 확인하십시오. 옵션을 선택하고 **'폴더 생성'을** 클릭된 하면 선택한 클라우드 서비스 내에 데이터 업로드 처리 방법에 대한 지침과 함께 파일 경로가 생성됩니다. 폴더 중복 및 오류를 방지하기 위해 최초 선택 후에는 **동기화 방법을 한 번만 변경할** 수 있습니다.


#### 스냅샷 업로드 요구 사항

이 방법을 사용하다 소스 업데이트될 때마다 이전 데이터 세트를 완전히 대체하는 완전하고 독립적인 파일을 업로드할 수 있습니다.

<span id="h_01K2A7MAWT05K506384QHYA0FN"></span>**지원되는 클라우드 서비스**

* Amazon S3
* Google 클라우드 스토리지
* BigQuery
* Snowflake

**<span id="h_01K2A7MAWTCYF3VAWJRRRJFNN5"></span>스냅샷 업데이트 방법을 사용하려면 다음 지침을 따르세요.**

1. **소스 폴더 경로**

   DCP에 클라우드 스토리지 소스 등록할 때 루트 경로(예:`input/my_source_folder/` )는 해당 소스 에 대해 정의됩니다. 데이터셋을 새로 고칠 때마다 현재 모든 행이 포함된 **전체 스냅샷** 파일(스냅샷)을 이 폴더에 업로드합니다. 이를 통해 DCP는 항상 최신의 완벽한 데이터 정보를 처리할 수 있습니다.
2. <span id="h_01K2A7MAWTPJ621MGBBG40N8H4"></span>**전체 스냅샷 파일 업로드 중**

| 지침 | 이번 업데이트가 중요한 이유: | 준수 방법 |
| --- | --- | --- |
| 전체 데이터: | DCP는 이전 상태를 완전히 대체해야 합니다. | 변경 내역뿐 아니라 모든 기록을 포함하는 내보내기 파일을 생성합니다. |
| **날짜별로 구분된 폴더 (**`dt=` ) | 날짜 범위 필터링 및 보존 관리 기능을 제공합니다. | 각 스냅샷을 아래에 놓으세요 `dt=YYYY‑MM‑DD/` |
| **버전 하위 폴더(**`v=` ) | 하루에 여러 장의 스냅샷을 찍을 수 있습니다. | 첫 번째 업로드`v=1/` ; 재시도 사용`v=2/` ,`v=3/` , 등. |
| `data/` **sub-folder** | 파일을 정리해줍니다 | Parquet/ CSV /Avro 파일을 이 폴더에 저장하세요. |
| `_SUCCESS` **채점자** | DCP 섭취 시작을 알립니다 | 빈 파일을 업로드하세요.`_SUCCESS` 안쪽`v=` 모든 데이터 파일이 저장된 폴더 |
| **지원되는 파일 형식 및 크기** |  | <ul><li>지원되는 파일 형식: .csv 또는 .gz</li><li>최대 파일 크기: GB</li></ul> |

> 🚧 **중요!**
>
> 전체 스냅샷 파일(아래 스크린샷의 BI-data.csv)은 다음 위치에 있어야 합니다.
>
> ```
> /v=1/data/
> ```
>
> 데이터 파일 업로드가 완료되면 빈 창을 띄우세요.`_SUCCESS` 파일 위치:
>
> ```
> /v=1/
> ```

**폴더 구조:**

```
s3://af-dcr-xyz/abcd9876/input/source_name1/dt=2025-mm-dd/v=1/data/
└ bucket ┘ └ tenant ┘ └ingestion┘ └source┘└snapshot date┘└ver┘└files┘
```

| Segment | 설명 | 목적 |
| --- | --- | --- |
| `af-dcr-xyz` | S3/GCS 버킷 | 모든 DCP 데이터를 담는 수준 컨테이너 |
| `abcd9876/` | 테넌트/워크스페이스 ID | 각 고객의 데이터를 격리하여 보관합니다. |
| `input/` | 섭취 부위 | 처리 전 원본 업로드 파일의 위치 |
| `source_name1/` | 소스 이름 | DCP에 등록된 논리적 데이터 세트 |
| `dt=2025-mm-dd/` | 스냅샷 날짜 | 해당 날짜의 데이터셋 전체 상태를 나타냅니다. |
| `v=1/` | 버전 (선택 사항) | 재시도 또는 추가 스냅샷을 지원합니다. |
| `data/` | 파일 | Parquet/ CSV /Avro 스냅샷 파일 |

<span id="h_01K2A7MAWTYFHBANCV9F2NKNCV"></span>**이틀간의 스냅샷 구조 예시:**

```
source_name1/
  dt=2025-08-10/
    v=1/
      data/
        snapshot.parquet
      _SUCCESS
  dt=2025-08-11/
    v=1/
      data/
        snapshot.parquet
      _SUCCESS
```

소스 파일의 전체 스냅샷을 2일 동안 업로드한 후(프로그램적으로 날짜/버전/데이터 폴더와 \_SUCCESS 파일을 생성한 후) 폴더 구조가 어떻게 보이는지 예시를 보여드리겠습니다. 버킷/폴더 구조는 다음과 같을 수 있습니다.

[<Image alt="스냅샷 예시 버킷.png" src="https://files.readme.io/a96762b43bbcae3d1265aa407e725ba885e27c3a83433d017aa30d7afaf31e37-38096860329233.png" width="219px" />](https://files.readme.io/a96762b43bbcae3d1265aa407e725ba885e27c3a83433d017aa30d7afaf31e37-38096860329233.png)


#### 업로드 요구 사항 추가

이 방법을 사용하다 이전 업로드 이후 변경되거나 추가된 데이터만 업로드할 수 있습니다.

왜 추가 기능을 사용해야 할까요?

* **효율성** – 업로드 용량 감소
* **데이터 무결성** – 시계열 분석을 위해 전체 변경 이력을 보존합니다.
* **개인정보 보호 정보보호법 준수** – 기록 삭제 및 동의 관리 간소화

지원되는 클라우드 서비스 AWS S3 및 구글 클라우드 스토리지(GCS)  
**참고:** BigQuery 및 Snowflake는 Append 메서드를 지원하지 않으며 Snapshot 메서드를 사용해야 합니다.

**추가 업데이트 방법을 사용할 때는 다음 지침을 따르세요.**

<span id="h_01K2A7MAWT8E6AX95VG86APXBB"></span>1. **소스 폴더 설정**

| 단계 | 설명 |
| --- | --- |
| **버킷 생성/할당** | 기존 S3/GCS 버킷을 사용하다 하거나 앱스플라이어 버킷을 프로비저닝하도록 하세요. |
| **루트 경로를 정의합니다** | 테넌트 범위 경로(예:`s3://af‑dcr‑xyz/abcd1234/` )는 입력 디렉터리로 구성됩니다. |
| **보안** | 서비스 사용자에게 이 경로에 대한 쓰기 권한만 부여하십시오. |

<span id="h_01K2A7MAWT86J2S65D99BC66PQ"></span>2. **추가(델타) 파일 업로드**

| 지침 | 이번 업데이트가 중요한 이유: | 준수 방법 |
| --- | --- | --- |
| **업로드 주기** | 이송 비용 및 운영 간접비를 낮게 유지합니다. | 매일 업로드하거나, 7일 분량의 폴더를 묶어서 매주 업로드하세요. |
| **하루에 폴더 하나씩** | 날짜 필터링 기능을 제공하여 대량 스캔 작업을 방지합니다. | 매일의 변화량을 입력하세요 `dt=YYYY‑MM‑DD/` |
| **고유한 파일 이름** | 실수로 덮어쓰기되는 것을 방지합니다. | 다음과 같은 형식으로 파일에 고유한 이름을 지정하세요.`events_2025‑08‑04.parquet` `events_2025‑08‑05.parquet` |
| **필수 열** | 변경 사항 추적 가능하게 합니다 | 파일에는 다음 내용이 포함되어야 합니다.<ul><li>리포팅 기간과 레코드를 연결하는 날짜 열입니다.<ul><li>데이터 수정 사항을 추적하다 하는 버전 열입니다.</li></ul></li></ul>**참고:** 이러한 열이 누락된 파일은 DCP에서 로드 오류를 결과 시킵니다. |

**폴더 구조:**

```
s3://af-dcr-xyz/abcd1234/input/source_name/dt=2025-08-10/
└ bucket ┘ └ tenant ┘ └ ingestion ┘ └ source ┘ └ day partition ┘
```

| Segment | 목적 |
| --- | --- |
| `af-dcr-xyz` | 고객의 S3/GCS 버킷 |
| `abcd1234/` | 테넌트 또는 워크스페이스 ID |
| `input/` | 처리 대기 중인 원본 업로드 파일 |
| `source_name/` | 논리적 DCP 소스 (예: CRM\_Events) |
| `dt=2025-08-10/` | 일일 파티션 폴더 |

<span id="h_01K2A7MAWTRSYFTTDKG4G0TPZR"></span>**주간 델타 폴더 구조 예시:**

```
source_name/
  dt=2025-08-04/
  dt=2025-08-05/
  dt=2025-08-06/
  dt=2025-08-07/
  dt=2025-08-08/
  dt=2025-08-09/
  dt=2025-08-10/
```

<span id="h_01K2A7MAWT5NDJQAYD16NRZSAQ"></span>**간편한 계산 요령 요약:**

| 요구 사항 | 이유 | 예시 |
| --- | --- | --- |
| **주간 배치 (선택 사항)** | 푸시 횟수는 줄이고, 정밀도는 그대로 유지 | 형제자매 7명이 포함된 일괄 파일을 업로드하세요.`dt=` 폴더 |
| **일별 구분** | 쿼리 및 UI 필터 속도 향상 | `s3://your‑bucket/source/ dt=2025‑08‑04/ ... dt=2025‑08‑10/` |

핵심 요약 매주 업로드하더라도 항상 데이터를 일별별로 정리하세요.`dt=YYYY‑MM‑DD` 폴더.

</Accordion>

<div id="step-5-map-source-fields" />

<Accordion title="5단계: 소스 필드 매핑">

소스 필드를 DCP 필드에 매핑하고, 테스트 후, 구성된 데이터를 저장합니다.

1. [소스 필드를 로드하세요](#1-소스-필드를-로드하세요)
2. [소스 필드를 구성합니다.](#2-소스-필드를-구성합니다)
3. [EU 사용자 포함 여부 확인](#3-eu-사용자-포함-여부-확인)
4. [소스 데이터를 테스트합니다](#4-소스-데이터를-테스트합니다)
5. [소스 저장](#5-소스-저장)

#### 1. 소스 필드를 로드하세요

소스 필드가 자동으로 로드됩니다. 수동 로딩이 필요한 경우, 소스 위치에 따라 아래 지침을 따르십시오.

**데이터 웨어하우스 소스**

데이터 웨어하우스(BigQuery 또는 Snowflake)에 있는 소스에서 필드를 로드하려면 **버튼을 클릭합니다.**

> 🚧 **중요!**
>
> 선택한 소스 테이블에 필요한 [날짜 및 버전 열](#table-columns)이 포함되어 있지 않으면 오류가 발생합니다.

**Cloud Storage 버킷 소스**

클라우드 스토리지 버킷(Amazon S3 또는 GCS)에 있는 소스에서 필드를 로드하려면 프로토타입 소스 파일을 업로드해야 합니다.

소스 필드를 DCP 필드에 매핑하기 위한 목적으로:

* 로컬 파일에서 소스의 프로토타입 버전을 업로드할 수 있습니다.
  * 이 옵션을 선택하면 앱스플라이어는 항상 소스 폴더 경로를 자동으로 생성합니다.

                                                                또는

* 연결된 클라우드 버킷에서 소스 파일의 프로토타입 버전을 직접 업로드할 수 있습니다.
  * 이 옵션을 선택하면 다음을 추가로 선택할 수 있습니다.
    * 앱스플라이어 소스 파일에 대한 클라우드 폴더를 자동으로 생성하도록 허용하거나,
    * [소스 파일용 클라우드 폴더를 수동으로 생성하세요.](#manually-creating-a-folder-structure)

**프로토타입 소스 파일을 업로드하려면 아래 관련 탭의 지침을 따르십시오.**

<Tabs>
<Tab title="로컬 파일">

1. **맵 소스 필드** 섹션에서 **소스 에서 필드 불러오기를** 클릭 .
2. 열리는 창에서 **로컬 파일 업로드**를 선택합니다.
3. 업로드하려는 CSV 또는 GZIP 파일을 지정한 다음 확인을 클릭합니다.

</Tab>

<Tab title="연결(자동 생성)">

**연결된 클라우드 버킷에서 파일을 로드하고 앱스플라이어 소스 파일에 대한 클라우드 폴더를 생성하도록 하려면 다음 단계를 따르세요.**

1. **맵 소스 필드** 섹션에서 **소스 에서 필드 불러오기를** 클릭 .
2. 열리는 1. 기간 2. 창 에서 **"클라우드 버킷에서 로드"를 선택합니다.**
3. **폴더 생성** 링크를 클릭합니다.
   * 앱스플라이어는 필요한 폴더 구조와 소스 폴더를 자동으로 생성합니다(지정한 소스 폴더 이름으로 지정한 연결에).
4. 소스 폴더 구조가 생성되면 소스 폴더에 대한 링크를 포함하여 확인 메시지가 표시됩니다. 제공된 링크를 클릭하여 소스 폴더에 프로토타입 파일을 업로드합니다.
5. 파일 업로드가 완료되면 **확인**을 클릭합니다.

</Tab>

<Tab title="연결(수동 생성)">

**수동으로 생성한 구조에서 소스 파일을 업로드하려면:**

1. **맵 소스 필드** 섹션에서 **소스 에서 필드 불러오기를** 클릭 .
2. 열리는 1. 기간 2. 창 에서 **"클라우드 버킷에서 로드"를 선택합니다.**
3. **폴더 생성**을 클릭하지 **마십시오**. 대신 파일을 위해 만든 소스 폴더에 직접 파일을 업로드하십시오.
4. 파일 업로드가 완료되면 **확인**을 클릭합니다.

</Tab>
</Tabs>

#### 2. 소스 필드를 구성합니다.

소스 필드를 불러온 후, 각 소스 필드(열)에는 DCP 필드가 표시됩니다. 각 소스 필드를 검토하고 옆에 있는 드롭다운 목록에서 적절한 DCP 필드에 매핑하십시오. 다음 사항을 고려하십시오.

> 📘 **고려사항:**
>
> * 양측이 소스 데이터를 공유하는 경우, 사용자 수준 데이터가 해당 원본 간에 일치하도록 하려면 **최소한 하나의 필드를 식별자로 설정해야 합니다** . 식별자는 앱 사용자를 고유하게 식별하는 필드입니다(예: CUID, 앱스플라이어 ID 또는 해시 처리된 이메일).
> * 업로드된 소스 필드(열) 각각을 구성하는 것이 필수 사항은 아니지만, 분류, 효과적인 데이터 해석, 잠재고객 생성 지원, 인사이트 도출 및 유효성 검사 효율화를 위해 중요합니다.

**필드를 삭제하려면:**

* 삭제하려는 필드의 오른쪽에 마우스 커서를 올리면 나타나는 휴지통 아이콘을 클릭 .

**필드를 수동으로 추가하려면:**

이 옵션을 사용하면 데이터 소스 에 현재 없는 필드를 대상 그룹에 포함할 수 있습니다.

1. **+ 새 필드를** 클릭하세요. 빈 필드가 추가되었습니다.
2. 필드 이름을 입력하고 유형을 선택하세요.

<Image alt="NewField.png" src="https://files.readme.io/8dfb70dcac2cc9a2257c6e092bc2185de74a3804bd608878eaaadf09cd903331-43749881081745.png" width="760px" />

**필드 유형은 다음과 같습니다.**

* 식별자
  * Android ID
  * 앱스플라이어 ID
  * CUID
  * 이메일
  * `{해시된_이메일}`
  * 해시 처리된 이메일 (점 없음)
  * IDFA
  * IP 주소
  * ID5 Id
  * MediaMath ID
  * 모바일 광고 ID
  * 전화번호
  * 해시된 전화 (플러스 없음)
  * 플랫폼 ID
  * SHA256 해싱 ID
  * SHA256 전화번호
  * ZIP+5 코드
  * ZIP+4 코드
  * LUID
  * 개인 ID
* 식별자 목록
  * 해시 처리된 이메일(점 없음)
  * 해시된 폰(플러스 없음)
  * `{해시된_이메일}`
  * 해시된 전화번호
  * 이메일
  * 전화번호
  * ID5 Ids
  * MediaMath ID
  * 모바일 광고 ID
  * IDFAs
  * Android ID
  * IP 주소
* 부울리언
* 날짜와 시간:
  * 날짜 시간
  * 날짜
* DMA
  * ad\_personalization\_enabled
  * ad\_user\_data\_enabled
  * EU DMA 적용
* 숫자
  * double
  * 번호 목록
  * 롱 링크
  * 숫자
* 텍스트
  * 텍스트
  * app\_id
  * 텍스트 목록

#### **식별자 vs. 식별자 목록**

식별자 유형은 행당 하나의 가치 저장합니다(예: 행당 하나의 이메일 또는 하나의 CUID). 식별자 유형 목록은 행당 값 배열을 저장합니다(예: 단일 행에 여러 개의 해시된 이메일 또는 장치 ID가 포함될 수 있음). 소스 에서 레코드당 둘 이상의 식별자를 일치시켜야 하는 경우에 사용합니다.

> 🚧 **중요!**
>
> 소스 에 **'목록'** 유형(식별자 목록, 숫자 목록 또는 텍스트 목록)에 매핑된 필드가 포함된 경우, 소스 파일은 Parquet 형식으로 업로드하거나 연결해야 합니다. CSV 및 GZ 파일은 배열 형식 열을 지원 하지 않으므로 해당 형식에서 목록 필드를 올바르게 가져오지 못할 수 있습니다.

#### 소스 필드 다시 로드

데이터 파일 중 하나의 구성이 변경된 경우, 소스 파일을 업데이트하여 변경 사항을 반영할 수 있습니다.

> 📘 **참고사항**
>
> 소스 을 다시 로드하면 소스 의 열 이름이 업데이트된 파일 이름과 일치하도록 재설정됩니다. 이렇게 하면 목록에 있는 필드 이름과 해당 필드 유형이 모두 덮어쓰여집니다.

**파일에서 업데이트된 필드를 다시 로드하려면 다음 단계를 따르세요.**

1. **필드 새로고침을** 클릭하세요.
2. 파일 위치를 선택하세요.
   * 로컬 파일의 경우: 파일을 업로드하세요.
   * 클라우드 서비스의 파일을 보려면: **"클라우드 버킷에서 로드"를** 클릭하고 지침을 따르세요.
3. **확인**을 클릭하세요. 업데이트된 파일이 이제 표시됩니다.

#### 3. EU 사용자 포함 여부 확인

* 질문에 대해 **'예'** 또는 **'아니오'를** 선택하세요. **귀하의 소스에 EU DMA 규정이 적용되는 유럽 사용자가 포함되어 있습니까?**

EU 디지털 시장법의 개인정보 보호 규정에 대해 더 알아보기 .

#### 4. 소스 데이터를 테스트합니다

* [선택사항] **을 클릭하여 소스 필드의 형식 또는 유효성 오류를 확인합니다.**

#### 5. 소스 저장

* **저장**을 클릭하여 소스를 저장합니다.

확인 후 새 소스 **가 소스** 탭에 추가됩니다.

> 📘 **참고사항**
>
> 로컬 파일에서 소스를 업로드한 경우 소스를 저장하면 폴더 구조가 자동으로 생성되고 표시되는 확인 메시지에 소스 폴더에 대한 링크가 포함됩니다.

</Accordion>

## 소스를 관리하세요

사용자가 생성한 소스는 **소스** 탭에 표시됩니다. 여기에서 소스 이름과 구조를 편집하고, 공동 작업자와 공유하고, 삭제할 수 있습니다. 단, 이미 다른 청중에서 사용 중인 경우는 제외합니다.

<div id="edit-a-source" />

<Accordion title="소스 편집하세요">

1. **Data Clean Room**의 **소스** 탭으로 이동합니다.
2. 출처 목록에서 편집하려는 소스 위에 마우스를 올리고 편집 아이콘을 클릭 .![edit_button.png가 있습니다](https://files.readme.io/4c3822661beac49fad247c7f5958a535e46031238e975a5323a5550722c89c8a-10753875375377.png) 행의 맨 끝에 .
3. **'소스 편집'** 페이지에서 아래에 자세히 설명된 대로 관련 필드를 편집하세요.
4. **저장**을 클릭하세요.

#### 소스 이름을 편집하는 방법:

소스 이름을 편집할 때는 [다음 명명 규칙을 준수](#요구-사항-및-지침) 해야 합니다.

#### 소스 위치를 편집하는 방법:

1. **[소스 편집]** 페이지 > **[소스 위치]** 에서 다른 데이터 연결을 선택하십시오.
2. 관련 위치 정보를 선택하세요.
3. [선택 사항] [소스 를 테스트합니다](#4-소스-데이터를-테스트합니다) .
4. **저장**을 클릭하세요.

#### 필드 매핑을 편집합니다.

1. 필드 매핑으로 이동하여 필요한 변경 사항을 적용하세요. 필드를 변경하거나 매핑된 DCP 필드를 업데이트합니다.
2. **저장**을 클릭하세요.

> 🚧 **중요!**
>
> 이 소스가 사용되는 리포트에서 새 소스 구조를 반영하여 해당 변경을 수행해야 합니다.
>
> * 삭제되거나, 매핑이 해제되거나, 이전 매핑에서 변경된 필드는 해당 필드가 사용되는 모든 보고서에서 자동으로 제거됩니다.
> * 새로 추가되거나 분류된 필드는 포함하도록 리포트 정의를 편집할 때까지 기존 리포트에 자동으로 포함되지 않습니다.

</Accordion>

<div id="deleting-a-source" />

<Accordion title="소스 삭제하세요">

청중에게 공개된 자료를 제외하고는 모든 소스 삭제할 수 있습니다. 이 경우, 알림에는 해당 소스 사용하는 오디언스 명시됩니다. 소스 를 삭제하려면 먼저 해당 소스에 연결된 잠재고객을 삭제해야 합니다. 공유받은 자료는 소스 소유자만이 삭제할 수 있습니다.

1. **Data Clean Room**의 **소스** 탭으로 이동합니다.
2. 소스 목록에서 삭제하려는 소스 행 위로 마우스를 가져갑니다.
3. 삭제 아이콘을 클릭하세요![delete_button.png 이미지가](https://files.readme.io/10fbd4d4f09ddb56823a2824629f8bb9362b34c95038b3d9e747ffcde7b30381-24740010666129.png) 행의 오른쪽에 표시됩니다.
4. 대화 상자에서 **삭제를** 클릭 확인합니다.

</Accordion>

## 공유 권한

공동 작업자가 소스 데이터를 보고 사용할 수 있도록 권한을 부여하는 작업은 <Anchor target="_blank" href="/marketers/ko/docs/data-collaboration-platform-dcp-create-a-collaboration">공동 작업을 생성할</Anchor> 때 수행됩니다. <Anchor target="_blank" href="/marketers/ko/docs/data-collaboration-platform-dcp-sharing-permissions">공유 권한</Anchor> 에 대해 더 알아보기 .

## 추가 정보

이 섹션에서는 몇 가지 추가 참고 자료와 유용한 정보를 제공합니다.

<div id="manually-creating-a-folder-structure" />

<Accordion title="스토리지 버킷 폴더 구조를 수동으로 생성합니다(선택 사항).">

일반적으로 앱스플라이어가 소스 생성 프로세스의 일부로 필요한 폴더 구조를 자동으로 생성하도록 허용하는 것이 가장 쉽습니다. 그러나 이러한 폴더를 수동으로 만들려면 다음과 같이 해야 할 수 있습니다.

#### DCR 키 폴더 만들기

최대 보안을 보장하려면 버킷 바로 아래에 있는 폴더("DCR 키 폴더")의 이름을 계정에 할당된 8자의 영숫자 **DCR 키**(예: `01bcc5fb`01bcc5fb01bcc5fb )로 지정해야 합니다. *이는 AppsFlyer 계정과 연결된 다른 비밀번호 또는 키와는 다릅니다.*

DCR 키 폴더는 일반적으로 선택한 클라우드 서비스의 인터페이스를 사용하여 수동으로 생성합니다.

**계정의 DCR 키를 받으려면 다음 단계를 따르세요.**

* 오른쪽 상단의 점 3개(작업) 메뉴를 클릭하고 **DCR 키를** 선택하세요.

[<Image alt="DCR key.png" src="https://files.readme.io/b892831ad68cffb5b8084949d759f402780536c7176aa27733c867aff6560684-43750165616657.png" width="1141px" />](https://support.appsflyer.com/hc/article_attachments/50117774720401)

DCR 키 폴더를 생성한 후 버킷/폴더는 다음과 같은 구조를 가져야 합니다.

<Image alt="dcr_file_structure_dcr_key_folder.png" src="https://files.readme.io/a57ba8076a2af5ef1f5a8339ac6b24e1ab6f8ff60956013a0a6547320a13072f-16571304308497.png" width="308px" />

#### 최상위 입력 폴더

필수 사항은 아니지만 가장 좋은 방법은 DCR 키 폴더 바로 아래에 최상위 입력 폴더를 만드는 것입니다. 이 폴더는 DCR에 업로드하는 파일을 위한 전용 폴더입니다.

최상위 입력 폴더는 일반적으로 선택한 클라우드 서비스의 인터페이스를 사용하여 수동으로 생성합니다.

* 이 방법은 데이터 파일 업로드(입력) 및 보고서 수신(출력)에 동일한 버킷을 사용하는 경우 더욱 강력히 권장됩니다.
* <Anchor target="_blank" href="/marketers/ko/docs/data-collaboration-platform-dcp-set-up-your-cloud-services#dcr-naming-requirements">DCR 이름 지정 요구 사항</Anchor>을 준수하는 조건에서는 이 폴더의 이름을 원하는 대로 지정할 수 있습니다. 쉽게 식별할 수 있도록 일반적으로 이름을 input/로 명명합니다.

최상위 입력 폴더를 만든 후 버킷/폴더는 다음과 같은 구조를 가질 수 있습니다.

<Image alt="dcr_file_structure_input_folder.png" src="https://files.readme.io/cb7249ee0cbc0b4721c701f7d735c73eb7acc0a2a9e73de102b5a5ec9a6a79fd-16571312292753.png" width="308px" />

#### 각 데이터 소스의 두 번째 수준 폴더

다양한 데이터 소스 파일을 정기적으로 DCR에 업로드하여 처리할 수 있습니다. 이러한 각 데이터 소스에는 별도의 폴더("데이터 소스 폴더")가 할당되어야 합니다.

예를 들어, 매일 DCR에 처리할 파일 2개를 업로드할 계획이라면 다음과 같습니다. *BI-data.csv* 그리고 *CRM-data.gzip과* 같은 파일 이름을 지정하면, 각 데이터 소스에 폴더를 할당할 수 있습니다. 이 폴더들에 원하는 이름을 붙일 수 있습니다.`BI-data/` 그리고`CRM-data/` .

데이터 소스 폴더는 일반적으로 선택한 클라우드 서비스의 인터페이스를 사용하여 수동으로 생성합니다.

2개의 데이터 소스 폴더를 생성한 후 버킷/폴더는 다음과 같은 구조를 가질 수 있습니다.

<Image alt="dcr_file_structure_source_folders.png" src="https://files.readme.io/f4624a213b79978d8ec080551649fae72d04d2f58a78344fc9df74a859881549-16571312297361.png" width="307px" />

각 데이터 소스 폴더에서 소스가 업데이트될 때마다 [날짜 및 버전별로 중첩된 하위 폴더](#nested-subfolders-for-each-date-and-version)를 만들어야 합니다.

</Accordion>

## 개인정보 보호 규정

이 섹션에서는 현행 개인정보 보호 규정에 관한 중요 정보를 간략하게 설명합니다.

<div id="understanding-googles-eu-user-consent-policy-and-its-imlications" />

<Accordion title="구글의 EU 사용자 동의 정책 및 그 의미 이해하기">

구글 은 디지털 시장법(DMA) 시행의 일환으로 2024년 3월 6일부로 EU 사용자 동의 정책을 업데이트했습니다. Google 앱 어트리뷰션 파트너인 앱스플라이어는 광고주가 Google Ads 마케팅 채널에서 가치를 극대화할 수 있도록 지원하며, Google의 정책 요구사항을 충족하기 위한 필요한 변경을 진행하고 있습니다.

> 📘 **참고사항**
>
> * 구글의 디지털 시장법(DMA) 시행은 모든 플랫폼에 적용됩니다.
> * 자세한 내용은 다음을 참조하세요.
>   * [디지털 마케터법에 대한 인사이트 과 리소스](https://www.appsflyer.com/hubs/dma/)
>   * [구글 FAQ](https://support.google.com/google-ads/answer/14310715)

#### 동의 입력란 추가

구글 에서 잠재고객 활성화를 위한 소스 설정하고 **"귀하의 소스 EU DMA 규정의 적용을 받는 유럽 사용자가 포함됩니까?"라는** 질문에 **"예"** 라고 답할 경우, 아래 표 에 있는 추가 동의 필드가 소스 파일에 포함되어 있는지 확인하십시오. 이를 통해 앱스플라이어 활성화 과정 중에 필요한 정보를 구글 에 전송할 수 있습니다.

**추가 동의 항목 및 응답 값:**

<table><thead><tr><th>필드 이름</th><th>응답 가치</th><th>필드 설명</th></tr></thead><tbody><tr><td><span id="eea"></span><code>eea</code></td><td>true/false</td><td>사용자가 DMA가 적용되는 유럽 경제 지역(EEA)에 거주하고 있습니까?</td></tr><tr><td><span id="ad_personalization"></span><code>ad_personalization</code></td><td>\*true/false</td><td>유저가 개인 맞춤 광고를 위해 구글에서 자신의 데이터를 사용하는 데 대해 동의했나요?</td></tr><tr><td><span id="ad_user_data"></span><code>ad_user_data</code></td><td>\*true/false</td><td>유저가 자신의 유저 데이터를 Google에 발송하는 데 동의했는지 여부 </td></tr><tr><td colspan="3"><span id="when--true--appsflyer-sends-user-identifiers-for-users-who-have-granted-consent-to-google--when--false--appsflyer-abstains-from-sending-them"></span>\* " <strong>true</strong> "로 설정하면 앱스플라이어 동의한 사용자에 대해 전송한 사용자 식별자를 포함합니다.<br/>   " <strong>거짓</strong> "일 경우: 앱스플라이어 해당 내용이 포함되지 않습니다. 앱스플라이어 로 전송되지 않았기 때문입니다.</td></tr></tbody></table>

#### 시청자 규모에 미칠 수 있는 잠재적 영향

구글 에 전송되는 실제 및 예상 잠재고객 규모는 동의 여부를 결정하는 사용자 수에 따라 달라질 수 있습니다.

</Accordion>

<div data-zendesk-anchors="introduction=dcp-%EC%86%8C%EC%8A%A4%EC%97%90-%EB%8C%80%ED%95%98%EC%97%AC h_01HPKB2ERNRQG73AFA0X7XEDEF=dcp-%EC%86%8C%EC%8A%A4%EC%97%90-%EB%8C%80%ED%95%98%EC%97%AC h_01HPKB2ERPGD2PS4JBSDGYW3MC=%EC%8B%9C%EC%9E%91%ED%95%98%EA%B8%B0-%EC%A0%84%EC%97%90 source-format=%EC%86%8C%EC%8A%A4-%EB%8D%B0%EC%9D%B4%ED%84%B0-%EC%9A%94%EA%B5%AC-%EC%82%AC%ED%95%AD h_01HPKB2ERPANE0CAXFP9RG5YEH=%EC%86%8C%EC%8A%A4-%EB%8D%B0%EC%9D%B4%ED%84%B0-%EC%9A%94%EA%B5%AC-%EC%82%AC%ED%95%AD h_01HPKB2ERPQ787V0PAABP7Q2YY=data-format h_01HPKB2ERPJ5PVQ2QM5XCYZE0D=table-columns h_01HPKB2ERPWZFZN2DSCHWNXKXX=file-format creating-a-source=%EC%86%8C%EC%8A%A4-%EC%83%9D%EC%84%B1%ED%95%98%EC%84%B8%EC%9A%94 h_01HPKB2ERPX2T413N3T93YBBZB=%EC%86%8C%EC%8A%A4-%EC%83%9D%EC%84%B1%ED%95%98%EC%84%B8%EC%9A%94 h_01HX4AF0PYFQ2E8T1JVSAP69BX=step-1-set-source-name requirements-and-guidelines=%EC%9A%94%EA%B5%AC-%EC%82%AC%ED%95%AD-%EB%B0%8F-%EC%A7%80%EC%B9%A8 h_01K1ZHNZEQ3NSN3V7NQ34G8VC8=%EC%9A%94%EA%B5%AC-%EC%82%AC%ED%95%AD-%EB%B0%8F-%EC%A7%80%EC%B9%A8 h_01HX4AF0PYR2RQFCEFNGQBEZ5J=step-2-set-source-location source-locations-in-bigquery=bigquery%EC%9D%98-%EC%86%8C%EC%8A%A4-%EC%9C%84%EC%B9%98 01HX49VY7D8KG5DCB82BP69BXV=bigquery%EC%9D%98-%EC%86%8C%EC%8A%A4-%EC%9C%84%EC%B9%98 source-locations-in-snowflake=snowflake%EC%9D%98-%EC%86%8C%EC%8A%A4-%EC%9C%84%EC%B9%98 01HX49VY7DXH5YN8FF0NFAJBC2=snowflake%EC%9D%98-%EC%86%8C%EC%8A%A4-%EC%9C%84%EC%B9%98 source-locations-in-cloud-storage-buckets=cloud-storage-%EB%B2%84%ED%82%B7%EC%9D%98-%EC%86%8C%EC%8A%A4-%EC%9C%84%EC%B9%98 01HX49VY7D3CSF4SQ79Q7CZKWX=cloud-storage-%EB%B2%84%ED%82%B7%EC%9D%98-%EC%86%8C%EC%8A%A4-%EC%9C%84%EC%B9%98 01HX49VY7D307DT5VTMGHPF3WA=%EC%A4%91%EC%9A%94 local-file-system=%EC%86%8C%EC%8A%A4-%EC%9C%84%EC%B9%98%EB%8A%94-%EB%A1%9C%EC%BB%AC-%ED%8C%8C%EC%9D%BC%EC%9E%85%EB%8B%88%EB%8B%A4 h_01HX4SKEGE9NVCA6VYSR77S2DK=%EC%86%8C%EC%8A%A4-%EC%9C%84%EC%B9%98%EB%8A%94-%EB%A1%9C%EC%BB%AC-%ED%8C%8C%EC%9D%BC%EC%9E%85%EB%8B%88%EB%8B%A4 h_01K1FW3AW2AW4TPDS0ZGPQCMX3=%EC%86%8C%EC%8A%A4-%EC%9C%84%EC%B9%98%EB%8A%94-%EB%A1%9C%EC%BB%AC-%ED%8C%8C%EC%9D%BC%EC%9E%85%EB%8B%88%EB%8B%A4 h_01HX4T0H6SFQJEWFETKFD1CY6S=%EC%B0%B8%EA%B3%A0%EC%82%AC%ED%95%AD h_01K1G4X359BKWJD6YGPGDJ0ZVQ=step-3-set-source-update-method h_01K29ETW94GQM9YYF5A4Y6DKB6=%EC%A4%91%EC%9A%94-1 overwrite-method-specifications=%EC%8A%A4%EB%83%85%EC%83%B7-%EC%97%85%EB%A1%9C%EB%93%9C-%EC%9A%94%EA%B5%AC-%EC%82%AC%ED%95%AD snapshot-upload-requirements=%EC%8A%A4%EB%83%85%EC%83%B7-%EC%97%85%EB%A1%9C%EB%93%9C-%EC%9A%94%EA%B5%AC-%EC%82%AC%ED%95%AD h_01K1G33RX95KP9TJ4002DDJBCE=%EC%8A%A4%EB%83%85%EC%83%B7-%EC%97%85%EB%A1%9C%EB%93%9C-%EC%9A%94%EA%B5%AC-%EC%82%AC%ED%95%AD h_01K2A7MAWS5KR16QV0Y8AE39GW=%EC%8A%A4%EB%83%85%EC%83%B7-%EC%97%85%EB%A1%9C%EB%93%9C-%EC%9A%94%EA%B5%AC-%EC%82%AC%ED%95%AD h_01K2CC62XGAVTD5JH5DYXP0947=%EC%A4%91%EC%9A%94-2 append-delta-upload-requirements=%EC%97%85%EB%A1%9C%EB%93%9C-%EC%9A%94%EA%B5%AC-%EC%82%AC%ED%95%AD-%EC%B6%94%EA%B0%80 h_01K2A7MAWT7CRHY1TV5J41MM0D=%EC%97%85%EB%A1%9C%EB%93%9C-%EC%9A%94%EA%B5%AC-%EC%82%AC%ED%95%AD-%EC%B6%94%EA%B0%80 h_01K2C6QNJSAH9D3M48T02JHQ3R=%EC%97%85%EB%A1%9C%EB%93%9C-%EC%9A%94%EA%B5%AC-%EC%82%AC%ED%95%AD-%EC%B6%94%EA%B0%80 h_01K2A7MAWTV3FY1GZSXQFNX4JS=%EC%97%85%EB%A1%9C%EB%93%9C-%EC%9A%94%EA%B5%AC-%EC%82%AC%ED%95%AD-%EC%B6%94%EA%B0%80 h_01HX4AF0PYWR9Q51ZHQ435PZ16=step-5-map-source-fields load-the-source-fields=1-%EC%86%8C%EC%8A%A4-%ED%95%84%EB%93%9C%EB%A5%BC-%EB%A1%9C%EB%93%9C%ED%95%98%EC%84%B8%EC%9A%94 h_01HPKB2ERQTJPGG68FSEBHVVJA=1-%EC%86%8C%EC%8A%A4-%ED%95%84%EB%93%9C%EB%A5%BC-%EB%A1%9C%EB%93%9C%ED%95%98%EC%84%B8%EC%9A%94 h_01HPKB2ERRZNPYVVD8GHD7PBPE=%EC%A4%91%EC%9A%94-3 configure-the-source-fields=2-%EC%86%8C%EC%8A%A4-%ED%95%84%EB%93%9C%EB%A5%BC-%EA%B5%AC%EC%84%B1%ED%95%A9%EB%8B%88%EB%8B%A4 h_01HX64YHGHMK352E3RXHBFV0B5=2-%EC%86%8C%EC%8A%A4-%ED%95%84%EB%93%9C%EB%A5%BC-%EA%B5%AC%EC%84%B1%ED%95%A9%EB%8B%88%EB%8B%A4 01HX6HVZ6DK2WH71JVB0J9WPBF=%EA%B3%A0%EB%A0%A4%EC%82%AC%ED%95%AD identifier-vs-list-of-identifiers=%EC%8B%9D%EB%B3%84%EC%9E%90-vs-%EC%8B%9D%EB%B3%84%EC%9E%90-%EB%AA%A9%EB%A1%9D h_01KYSMJKRA2E13PH2QS671BSKG=%EC%8B%9D%EB%B3%84%EC%9E%90-vs-%EC%8B%9D%EB%B3%84%EC%9E%90-%EB%AA%A9%EB%A1%9D h_01KYSJNEWS5QY5Q13Z11TNJHX1=%EC%A4%91%EC%9A%94-4 reload-source-fields=%EC%86%8C%EC%8A%A4-%ED%95%84%EB%93%9C-%EB%8B%A4%EC%8B%9C-%EB%A1%9C%EB%93%9C h_01HX6TDNEMJFQM5FA95Y3C1QHD=%EC%86%8C%EC%8A%A4-%ED%95%84%EB%93%9C-%EB%8B%A4%EC%8B%9C-%EB%A1%9C%EB%93%9C h_01HX6WF7YC014Z7ZX359RB5ZRZ=%EC%B0%B8%EA%B3%A0%EC%82%AC%ED%95%AD-1 verify-eu-user-inclusion=3-eu-%EC%82%AC%EC%9A%A9%EC%9E%90-%ED%8F%AC%ED%95%A8-%EC%97%AC%EB%B6%80-%ED%99%95%EC%9D%B8 01HZKZ2T33TYCQ8J59YGDYN7DK=3-eu-%EC%82%AC%EC%9A%A9%EC%9E%90-%ED%8F%AC%ED%95%A8-%EC%97%AC%EB%B6%80-%ED%99%95%EC%9D%B8 test-the-source-data=4-%EC%86%8C%EC%8A%A4-%EB%8D%B0%EC%9D%B4%ED%84%B0%EB%A5%BC-%ED%85%8C%EC%8A%A4%ED%8A%B8%ED%95%A9%EB%8B%88%EB%8B%A4 h_01HX6WGD421PCWEWTN5YJ7V42H=4-%EC%86%8C%EC%8A%A4-%EB%8D%B0%EC%9D%B4%ED%84%B0%EB%A5%BC-%ED%85%8C%EC%8A%A4%ED%8A%B8%ED%95%A9%EB%8B%88%EB%8B%A4 save-the-source=5-%EC%86%8C%EC%8A%A4-%EC%A0%80%EC%9E%A5 h_01HYX92EXSJNM5B2PDXEAEBNFS=5-%EC%86%8C%EC%8A%A4-%EC%A0%80%EC%9E%A5 h_01HYXC06K3ZWQE867NKBT95RFH=%EC%B0%B8%EA%B3%A0%EC%82%AC%ED%95%AD-2 working-with-existing-sources=%EC%86%8C%EC%8A%A4%EB%A5%BC-%EA%B4%80%EB%A6%AC%ED%95%98%EC%84%B8%EC%9A%94 h_01HPKB2ERS5PK2P2XTC4ZMPCMC=%EC%86%8C%EC%8A%A4%EB%A5%BC-%EA%B4%80%EB%A6%AC%ED%95%98%EC%84%B8%EC%9A%94 h_01HPKB2ERTC48MGS0BM5SDR6XV=edit-a-source edit-the-source-name=%EC%86%8C%EC%8A%A4-%EC%9D%B4%EB%A6%84%EC%9D%84-%ED%8E%B8%EC%A7%91%ED%95%98%EB%8A%94-%EB%B0%A9%EB%B2%95 01J1SMACQHFEVAR8ZC6W8T0BAV=%EC%86%8C%EC%8A%A4-%EC%9D%B4%EB%A6%84%EC%9D%84-%ED%8E%B8%EC%A7%91%ED%95%98%EB%8A%94-%EB%B0%A9%EB%B2%95 edit-the-source-location=%EC%86%8C%EC%8A%A4-%EC%9C%84%EC%B9%98%EB%A5%BC-%ED%8E%B8%EC%A7%91%ED%95%98%EB%8A%94-%EB%B0%A9%EB%B2%95 h_01J1SM789AFJBSD0NG826P98Q4=%EC%86%8C%EC%8A%A4-%EC%9C%84%EC%B9%98%EB%A5%BC-%ED%8E%B8%EC%A7%91%ED%95%98%EB%8A%94-%EB%B0%A9%EB%B2%95 edit-the-source-structure=%ED%95%84%EB%93%9C-%EB%A7%A4%ED%95%91%EC%9D%84-%ED%8E%B8%EC%A7%91%ED%95%A9%EB%8B%88%EB%8B%A4 h_01J1SNB66WQMBV1GQE4PDQ0NW4=%ED%95%84%EB%93%9C-%EB%A7%A4%ED%95%91%EC%9D%84-%ED%8E%B8%EC%A7%91%ED%95%A9%EB%8B%88%EB%8B%A4 h_01HPKB2ERTYP6BFAESN3MHZSQG=%EC%A4%91%EC%9A%94-5 h_01HPKB2ERVGJYJ9KW1RGX24CGV=deleting-a-source permissions=%EA%B3%B5%EC%9C%A0-%EA%B6%8C%ED%95%9C h_01HZHBDPZ8FFQCB9DZ2Q8XSC2R=%EA%B3%B5%EC%9C%A0-%EA%B6%8C%ED%95%9C reference=%EC%B6%94%EA%B0%80-%EC%A0%95%EB%B3%B4 h_01HPKB2ERV1KK3J8YX918GCF3M=%EC%B6%94%EA%B0%80-%EC%A0%95%EB%B3%B4 h_01HPKB2ERVZ88MJ35JC66YDPAB=manually-creating-a-folder-structure creating-a-dcr-key-folder=dcr-%ED%82%A4-%ED%8F%B4%EB%8D%94-%EB%A7%8C%EB%93%A4%EA%B8%B0 h_01HPKB2ERV7MQJ9CK44T92GK2G=dcr-%ED%82%A4-%ED%8F%B4%EB%8D%94-%EB%A7%8C%EB%93%A4%EA%B8%B0 toplevel-input-folder=%EC%B5%9C%EC%83%81%EC%9C%84-%EC%9E%85%EB%A0%A5-%ED%8F%B4%EB%8D%94 h_01HPKB2ERVPG4R9FHWZPQ8TCZQ=%EC%B5%9C%EC%83%81%EC%9C%84-%EC%9E%85%EB%A0%A5-%ED%8F%B4%EB%8D%94 secondlevel-folder-for-each-data-source=%EA%B0%81-%EB%8D%B0%EC%9D%B4%ED%84%B0-%EC%86%8C%EC%8A%A4%EC%9D%98-%EB%91%90-%EB%B2%88%EC%A7%B8-%EC%88%98%EC%A4%80-%ED%8F%B4%EB%8D%94 h_01HPKB2ERVVFMP81RE8ATZ6SZ8=%EA%B0%81-%EB%8D%B0%EC%9D%B4%ED%84%B0-%EC%86%8C%EC%8A%A4%EC%9D%98-%EB%91%90-%EB%B2%88%EC%A7%B8-%EC%88%98%EC%A4%80-%ED%8F%B4%EB%8D%94 privacy-regulations-eu-digital-markets-act=%EA%B0%9C%EC%9D%B8%EC%A0%95%EB%B3%B4-%EB%B3%B4%ED%98%B8-%EA%B7%9C%EC%A0%95 h_01HZHBF0NZDTXAA3MY1A0BPE5E=%EA%B0%9C%EC%9D%B8%EC%A0%95%EB%B3%B4-%EB%B3%B4%ED%98%B8-%EA%B7%9C%EC%A0%95 h_01HZP9NC1DMQ380JKWNBM33Z6W=understanding-googles-eu-user-consent-policy-and-its-imlications h_01HZM4EFRJD483NARKDPPPPXCY=%EC%B0%B8%EA%B3%A0%EC%82%AC%ED%95%AD-3 adding-consent-fields=%EB%8F%99%EC%9D%98-%EC%9E%85%EB%A0%A5%EB%9E%80-%EC%B6%94%EA%B0%80 h_01HZHBF0NZSDGDYG2ZWNW4KQYD=%EB%8F%99%EC%9D%98-%EC%9E%85%EB%A0%A5%EB%9E%80-%EC%B6%94%EA%B0%80 -when-%E2%80%9Ctrue%E2%80%9D-appsflyer-sends-user-identifiers-for-users-who-have-granted-consent-to-google%C2%A0-when-%E2%80%9Cfalse%E2%80%9D-appsflyer-abstains-from-sending-them=when--true--appsflyer-sends-user-identifiers-for-users-who-have-granted-consent-to-google--when--false--appsflyer-abstains-from-sending-them potential-impact-on-the-audience-size=%EC%8B%9C%EC%B2%AD%EC%9E%90-%EA%B7%9C%EB%AA%A8%EC%97%90-%EB%AF%B8%EC%B9%A0-%EC%88%98-%EC%9E%88%EB%8A%94-%EC%9E%A0%EC%9E%AC%EC%A0%81-%EC%98%81%ED%96%A5 h_01HZHBF0NZJBSXNBDFZH4YKNSH=%EC%8B%9C%EC%B2%AD%EC%9E%90-%EA%B7%9C%EB%AA%A8%EC%97%90-%EB%AF%B8%EC%B9%A0-%EC%88%98-%EC%9E%88%EB%8A%94-%EC%9E%A0%EC%9E%AC%EC%A0%81-%EC%98%81%ED%96%A5" />
