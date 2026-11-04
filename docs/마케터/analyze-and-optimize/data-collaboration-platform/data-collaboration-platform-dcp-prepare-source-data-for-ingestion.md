---
title: 데이터 협업 플랫폼(DCP) - 데이터 수집을 위한 소스 데이터 준비
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
  created_at: '2026-01-26T12:08:32Z'
  edited_at: '2026-10-14T10:27:21Z'
  id: 43205325114897
  locale: ko
  section: Data Collaboration Platform
  section_id: 26230608274065
  url: https://support.appsflyer.com/hc/ko/articles/43205325114897
---
> **한눈에 보기:** 공동 작업자 데이터 세트 간의 일치율을 극대화하고 협업 결과를 최적화하다 하려면 소스 데이터를 준비하십시오.

<div id="about-data-preparation" />

## 데이터 준비에 관하여

앱스플라이어 <Anchor target="_blank" href="/marketers/ko/docs/data-collaboration-platform-dcp-guide">데이터 협업 플랫폼(DCP)</Anchor> 은 여러 협업자로부터 대규모 거래 데이터, 사용자 수준 데이터 또는 이 둘의 조합을 수집하고 처리하도록 설계되었습니다. 일단 데이터가 수집되면 DCP는 공유 식별자(예: 해시 처리된 이메일 또는 해시 처리된 전화번호)를 사용하여 데이터 세트 간 사용자를 일치시키고 해당 데이터를 기반으로 협업 워크플로를 활성화할 수 있습니다.

이 글에서는 다음 내용을 간략하게 설명합니다.

* DCP가 처리할 수 있는 데이터 유형(거래 데이터, 사용자 수준 데이터 또는 이들의 조합)
* 협력자 간 매칭률을 극대화하고, 활성화 파트너별 최적의 매칭을 위해 데이터를 어떻게 구조화해야 할까요?
* 어떤 데이터 구조가 권장되고 어떤 데이터 구조는 권장되지 않는가?
* CSV 파일을 사용할 때 다중 값 식별자를 처리하는 방법

<div id="understand-data-types" />

## 데이터 유형을 이해하세요

협업에 사용되는 대부분의 소스는 다음 데이터 유형 중 하나 또는 둘 다를 포함합니다.

* **사용자 수준(신원) 데이터**
  * 목표 각 사용자와 매칭에 ​​사용되는 식별자를 나타냅니다.
  * **권장 구조:** 사용자당 한 줄씩
* **거래(이벤트) 데이터**
  * 목표 사용자 활동(구매, 방문, 거래)을 나타냅니다.
  * **일반적인 구조:** 사용자당 여러 행이 표시됩니다 (사용자 한 명이 여러 거래를 할 수 있기 때문입니다).

<div id="data-structuring-guidelines" />

## 데이터 구조화 지침

이 섹션에서는 DCP 데이터 구조화 지침 및 모범 사례를 설명합니다.

<div id="workflow-and-structuring-guidelines" />

<Accordion title="권장 데이터 구조">

**DCP에서 최적의 데이터 수집과 최대의 결과를 얻으려면 소스 데이터를 다음과 같이 구성하십시오.**

1. <Anchor target="_blank" href="/marketers/ko/docs/data-collaboration-platform-dcp-create-and-manage-sources#소스-데이터-요구-사항">소스 데이터 형식 요구 사항을 충족하는지</Anchor> 확인하십시오.
2. 최상의 결과를 얻으려면, **사용자 식별 데이터를 사용자별로 한 행씩 구성하고 해당 사용자에 대해 사용 가능한 모든 식별자를 포함하십시오.** [권장 식별자 구조를](#권장-식별자-구조) 참조하십시오.
   * 사용자가 여러 개의 이메일 주소나 전화번호를 가지고 있는 경우, Parquet, BigQuery 또는 Snowflake와 같은 배열 기반 형식을 사용하십시오.
3. [해싱 가이드라인을](/docs/data-collaboration-platform-dcp-prepare-source-data-for-ingestion#appendix-e-hashed-data-formatting-guidelines-by-media-partner) 준수했는지 확인하십시오.
4. 거래 데이터 세트(및 해당되는 경우 기타 데이터 유형)의 경우 **DCP 데이터 보기 도구를 사용하여** 협업에 최적화된 비즈니스 지향적이고 개인 정보 보호가 안전한 데이터 하위 집합을 생성하고 원시 테이블 대신 공유하세요. [데이터 뷰를 사용하는 것이 권장되는 이유](/docs/data-collaboration-platform-dcp-prepare-source-data-for-ingestion#appendix-c-why-dataviews-matter-and-recommended) .

다른 구조를 사용할 수도 있지만, DCP를 최대한 활용하는 데에는 이상적이지 않을 수 있습니다. [권장하지 않는 데이터 구조를](#data-structures-that-arent-recommended) 참조하세요.

<div id="recommended-identifier-structures" />

#### 권장 식별자 구조

매칭률을 극대화하려면 가능한 한 사용자 수준의 신원 데이터를 사용자별로 단일 행으로 전송하고, 사용 가능한 모든 식별자를 사용자를 정확하게 표현하는 구조에 포함하는 것이 좋습니다.

옵션 3 사용자당 한 행, 식별자 유형당 하나의 가치

**간단하고 효과적입니다.**

각 사용자가 최대 하나의 해시된 이메일 주소, 하나의 해시된 전화번호 등을 보유할 때 이 방법을 사용하다 .

**예시**

| 사용자 ID | 해시된 이메일 | 해시된 전화번호 |
| --- | --- | --- |
| 123 | 5d41402 | 152d234b70 |
| 456 | 7d793037 |  |
| 789 |  | 0e6e5414 |

**추천되는 이유**

* 가장 간편하게 준비하고 섭취할 수 있습니다.
* 검증 및 문제 해결이 용이합니다.
* 식별자가 완전하고 일관적일 경우 뛰어난 매칭 성과 (협력업체 데이터 세트와의 매칭 및 활성화 미디어 파트너 매칭 기준).

**가장 적합한**

* CSV 기반 업로드에 적합합니다.
* Parquet/BigQuery/Snowflake에서도 잘 작동합니다.

옵션 3 다중값 필드에 대한 식별자 배열(목록)

**사용자가 여러 개의 이메일 주소와 전화번호를 가지고 있을 때 정확도가 가장 높습니다.**

사용자가 동일한 식별자 유형에 대해 여러 값을 가질 수 있는 경우(예:)에 사용하다 .

* 여러 개의 해시된 이메일
* 여러 개의 해시된 휴대폰

이 구조는 **네이티브 배열** 로 표현되어야 합니다.

**예시**

| 사용자 ID | 해시된\_이메일 | 해시된 전화번호 | MAID |
| --- | --- | --- | --- |
| u\_0001 | [a1b2 · c3d4 · e5f6] | [p1q2 · r3s4] | m001 |
| u\_0002 | [z9y8 · x7w6] |  | m002 |
| u\_0003 |  | [t1u2 · v3w4 · x5y6] |  |

**선호되는 이유**

* 이는 신원 정보가 내부적으로 저장되는 방식을 반영합니다.
* "이메일 열"이 몇 개나 필요할지 추측할 필요가 없습니다.
* 지속적인 스키마 변경을 방지합니다.
* 사용자당 여러 식별자를 허용하여 (협력업체 데이터 세트 및 활성화 미디어 파트너 매칭을 위한) 매칭 가능성을 극대화합니다.

**가장 적합한**

* Parquet (S3/GCS)
* BigQuery
* Snowflake

</Accordion>

<div id="practical-checklist-for-dcp-collaborators" />

<Accordion title="데이터 구조화를 위한 실용적인 체크리스트">

<div id="identity-user-level-dataset-checklist" />

#### 신원(사용자 수준) 데이터 세트 체크리스트

* 한 행은 한 명의 사용자를 나타냅니다.
* 사용 가능한 모든 식별자(해시 처리된 이메일, 해시 처리된 전화번호, MAID 등)를 포함하십시오.
* 여러 값이 존재하는 경우(예: 여러 이메일 주소) 가능한 한 네이티브 배열을 사용하십시오.
* 셀에 목록을 넣지 마세요. 예를 들어 "email\_1/email\_2/email\_3"과 같은 형식을 사용하지 말고, 여러 행에 걸쳐 동일한 주소를 사용하는 구조도 피하세요.

<div id="transactional-events-dataset-checklist" />

#### 거래(이벤트) 데이터 세트 체크리스트

* 이벤트/트랜잭션 행은 그대로 유지하세요. [거래 데이터 예시를](#appendix-a-transactional-data-examples) 참조하세요.
* 필요에 따라 [데이터 뷰를](#appendix-c-why-dataviews-matter-and-recommended) 사용하다 공동 작업에 적합한 사용자 수준 요약을 생성하세요.

<div id="data-views-checklist" />

#### 데이터 보기 체크리스트

* 비즈니스에 최적화된 [데이터 보기](#appendix-c-why-dataviews-matter-and-recommended) (대상 고객이 바로 이해할 수 있도록 요약되고 표준화된 형태)를 구축하세요.
* 가능하면 민감한 정보가 포함된 원본 테이블 대신 데이터 뷰를 공유하세요.
* 개인 정보 보호 및 비즈니스 보호를 위해 필요한 최소한의 공유 필드만 사용하세요.
* 민감한 데이터에 대한 액세스 줄이고 효율성을 높이기 위해 데이터 집계를 고려하십시오.

</Accordion>

<div id="supported-ingestion-cloud-services-and-formats" />

<Accordion title="지원되는 데이터 수집 클라우드 서비스 및 형식">

DCP는 다음과 같은 여러 클라우드 서비스를 통한 데이터 수집을 지원합니다.

* AWS S3
* Google 클라우드 스토리지
* BigQuery
* Snowflake

<div id="format-guidance" />

#### 형식 안내

* 각 사용자가 **식별자 유형별로 하나의 가치** ( 이메일 하나, 전화번호 하나 등)만 가지고 있는 경우 **CSV (쉼표로 구분된) 형식을** 사용하다 .
* 사용자가 동일한 식별자 유형에 대해 **여러 값을** 가질 수 있는 경우(예: 여러 개의 해시된 이메일)에는 **배열 지원 형식을** 사용하는 것이 좋습니다.
  * 파케트(빅데이터에서 흔히 사용됨)
  * BigQuery(배열은 내장 기능입니다)
  * Snowflake(배열이 내장되어 있습니다)

**참고:**

* "배열"은 단순히 "값들의 목록"을 의미합니다.
* BigQuery/Snowflake에서 Parquet과 배열은 표준적인 방식이며, 대부분의 데이터 팀은 이를 자연스럽게 지원 수 있습니다.

[커넥터별 예제 자료(AWS S3, GCS, BigQuery, Snowflake)를 참조하세요.](#appendix-b-connectorspecific-example-assets-aws-s3-gcs-bigquery-snowflake)

<div id="data-structures-that-arent-recommended" />

<Accordion title="권장하지 않는 데이터 구조">

특정 유형의 데이터 구조는 DCP로의 수집에 이상적으로 적합하지만, 그렇지 않은 유형도 있습니다. 다음은 **권장하지 않는** 데이터 구조 목록입니다.

<div id="avoid-multiple-columns-for-the-same-identifier-type" />

#### 피하다: 동일한 식별자 유형에 대한 여러 열

"기본/보조/제3 이메일"과 같은 예시는 사용하지 않는 것이 좋습니다.

**피해야 할 예시**

| 사용자 ID | 이메일(해시됨) | 이메일(해시됨) | 이메일(해시됨) |
| --- | --- | --- | --- |
| 123 | a1b2 | c3d4 |  |
| 456 | z9y8 |  |  |

**피해야 하는 이유**

* 사용자별 값의 개수는 예측할 수 없습니다.
* 컬럼이 과도하게 늘어나고 스키마 유지 관리 문제가 발생합니다.

<div id="avoid-lists-inside-a-single-cell-free-text" />

#### 피하다: "단일 셀 내의 목록"(자유 텍스트)

편리해 보일지라도 오류 발생 가능성이 높습니다.

**피해야 할 예시**

| 사용자 ID | 해시 처리된 이메일(텍스트) |
| --- | --- |
| 123 | a1b2 · c3d4 · e5f6 |

**피해야 하는 이유**

* 진정한 배열 유형이 아닙니다.
* 서식/이스케이프 오류는 흔히 발생합니다.
* 사소한 불일치가 섭취를 방해할 수 있습니다.

<div id="avoid-multiple-rows-per-user-for-identifiers-when-your-goal-is-a-user-identity-table" />

#### 피하다: 사용자 식별자를 위한 여러 행이 사용자별로 필요합니다(사용자 ID 표 만들려 목표 경우).

사용자별 행 하나로 관리할 수 있다면, 신원 정보를 여러 행으로 분산시키지 마세요.

**피해야 할 예시**

| 사용자 ID | 식별자 유형 | 식별자 값 |
| --- | --- | --- |
| 123 | hashed\_email | a1b2 |
| 123 | hashed\_email | c3d4 |

**피해야 하는 이유**

* 사용자 정보를 재구성하려면 추가 처리가 필요합니다.
* 중복 및 불일치 위험 증가
* 대규모의 수록 효율성이 떨어진다

**참고:** 거래 테이블에서는 사용자별로 여러 행이 있는 것이 일반적이지만, 일치 검색에 사용되는 ID(사용자 수준) 표 에서는 이상적이지 않습니다.

</Accordion>

</Accordion>

<div id="additional-information" />

## 추가 정보

이 섹션에서는 관련 주제에 대한 추가적인 심층 정보를 제공합니다.

<div id="appendix-a-transactional-data-examples" />

<Accordion title="거래 데이터 예시">

거래/ 이벤트 데이터는 사용자별로 여러 행을 포함할 수 있습니다.

| 트랜잭션 ID | 사용자 ID | 거래일 | 금액 | 카테고리 |
| --- | --- | --- | --- | --- |
| t\_001 | 123 | 2025-12-01 | 120.00 | 식료품점 |
| t\_002 | 123 | 2. | 45.00 | 약국 |
| t\_003 | 456 | 2. | 300.00 | 전자제품 |

**추천**

* 거래 데이터를 원래 구조 그대로 수집합니다.
* 데이터 보기 도구를 사용하다 공동 작업에 적합한 사용자 수준 보기(예: 지난 30일간 지출 , 카테고리 선호도, 최근/빈도 요약)를 생성하세요.

</Accordion>

<div id="appendix-b-connectorspecific-example-assets-aws-s3-gcs-bigquery-snowflake" />

<Accordion title="커넥터별 예제 자산(AWS S3, GCS, BigQuery, Snowflake)">

<div id="what-does-arraylist-of-identifiers-mean" />

### “식별자 배열/목록”이란 무엇을 의미합니까?

경우에 따라 한 사용자가 여러 개의 이메일 나 전화번호를 가질 수 있습니다(예: 개인 이메일과 작업하다 이메일). 이러한 값들을 별도의 열이나 복잡한 텍스트 필드에 억지로 넣는 대신, 값들의 목록으로 표현합니다.

| 사용자 ID | 해시 처리된 이메일(목록) |
| --- | --- |
| u\_0001 | [a1b2 · c3d4 · e5f6] |
| u\_0002 | [z9y8 · x7w6] |

<div id="1-aws-s3-and-gcs-connector-parquet" />

### 1. AWS S3 및 GCS 커넥터(Parquet)

**신원 확인 샘플에 포함되어야 할 내용(스키마)**

| 필드 | 유형 | 참고 |
| --- | --- | --- |
| user\_id | 문자열 | 사용자당 한 줄씩 |
| hashed\_emails | string 배열 | 다중값 식별자(권장) |
| hashed\_phones | string 배열 | 다중값 식별자(권장) |
| 하녀 | 문자열 | 선택적 추가 식별자 |

Parquet은 목록을 기본적으로 지원하므로 사용자가 여러 개의 이메일 주소나 전화번호를 사용하는 경우에 권장됩니다.

<div id="2-bigquery-connector-table-preview-and-schema-screenshot" />

### 2. BigQuery 커넥터(표 미리보기 및 스키마 스크린샷)

**예시 ID 스키마 (BigQuery)**

| 필드 | 유형 | 모드 |
| --- | --- | --- |
| user\_id | 문자열 | 널 가능 |
| hashed\_emails | 문자열 | 반복됨(배열) |
| hashed\_phones | 문자열 | 반복됨(배열) |
| 하녀 | 문자열 | 널 가능 |

BigQuery에서는 배열이 기본 기능입니다(반복 필드). 여러 개의 이메일 주소나 전화번호가 있는 경우 권장되는 접근 방식입니다.

<div id="3-snowflake-connector-table-preview-and-schema-screenshot" />

### 3. Snowflake 커넥터(표 미리보기 및 스키마 스크린샷)

**예시 ID 스키마(Snowflake)**

| 필드 | 유형 | 참고 |
| --- | --- | --- |
| USER\_ID | 바르차르 | 사용자당 한 줄씩 |
| `{해시된_이메일}` | 배열 | 다중값 식별자 |
| 해시된 전화번호 | 배열 | 다중값 식별자 |
| MAID | 바르차르 | 선택 사항 |

Snowflake는 리스트와 유사한 필드(배열)를 지원합니다. 이는 email\_1/email\_2/mail\_3 열을 생성하는 것보다 선호됩니다.

</Accordion>

<div id="appendix-c-why-dataviews-matter-and-recommended" />

<Accordion title="데이터 뷰를 권장하는 이유">

<Anchor target="_blank" href="/marketers/ko/docs/data-collaboration-platform-dcp-create-customized-data-views">데이터 뷰는</Anchor> 기존 데이터 소스의 사용자 지정 하위 집합으로, 원본 데이터 세트를 변경하지 않고 생성할 수 있습니다. 이 기능들을 사용하면 데이터를 수정, 정제 및 요약하여 협업에서 관련성 있는 데이터만 공유할 수 있으므로 공유하는 데이터는 명확하고 핵심에 집중된 상태로 유지하고 나머지 데이터는 비공개로 안전하게 보호할 수 있습니다. 협업에서 데이터 뷰를 사용하다 이유는 다음과 같습니다.

<div id="are-business-oriented-and-easier-to-collaborate-with" />

#### 비즈니스 지향적이며 협업이 더 용이합니다.

* 데이터 뷰를 사용하면 원시 로그나 복잡한 거래 스키마 대신 깔끔하고 비즈니스 친화적인 구조(예: "고객 ID 뷰", "대상 고객 뷰", "구매 요약 뷰")로 데이터를 표시할 수 있습니다.
* 이러한 표준화된 정의(예: "활성 고객", "지난 30일간 총 지출 ")를 통해 양측이 일관된 논리를 사용하도록 돕다 .

<div id="are-more-privacy-safe-by-design" />

#### 설계상 개인정보 보호에 더욱 안전합니다.

* 데이터 뷰는 데이터 최소화를 지원 . 전체 원시 데이터 세트를 노출하는 대신 공동 작업에 필요한 필드와 행만 공유할 수 있습니다.
* 다음과 같은 기능을 통해 개인정보 보호 위험을 줄일 수 있습니다.
  * 불필요한 속성을 제외하세요
  * 세부 정보 수준을 제한하세요(예: 개별 거래 내역 대신 집계된 지표를 공유하세요).
  * 매칭에 필요한 식별자만 공유하고, 추가적인 민감한 열은 공유하지 마세요.

<div id="protect-sensitive-business-data" />

#### 중요한 비즈니스 데이터를 보호하세요

* 가공되지 않은 거래 테이블에는 매우 민감한 비즈니스 신호(예: 상세한 구매 행태, 가격 패턴, 가맹점 관계, 내부 ID)가 포함될 수 있습니다.
* 데이터 뷰를 사용하면 공동 작업에 필요한 정보만 공유할 수 있습니다.
  * 예시: 품목별 세부 정보 대신 카테고리별 집계 정보를 공유합니다.
  * 예: 정확한 항목별 지출 대신 지출 구간별 비율 또는 요약 지표를 공유하세요.
* 이는 경쟁사 정보나 자체 개발한 정보를 의도치 않게 공개할 위험을 줄여줍니다.

<div id="can-make-your-data-more-cost-effective-and-performant" />

#### 데이터를 더욱 비용 효율적이고 성능이 뛰어나게 만들 수 있습니다.

데이터 뷰는 더 가볍고 효율적으로 구성할 수 있으며, 이는 종종 다음과 같은 이점을 제공합니다.

* 스캔된 데이터
* 처리 시간
* 비용 계산

협업에 최적화된 보기(특히 집계된 보기)를 미리 구성해 두면 협업 속도를 높이고 운영상의 예측 가능성을 높일 수 있습니다.

</Accordion>

<div id="appendix-d-multiple-ids-keys-upload-and-matching-behavior-by-platform" />

<Accordion title="플랫폼 별 다중 ID/키 업로드 및 매칭 동작">

**DCP 식별자 업로드**

| 파트너/플랫폼 | 지원되는 식별자 유형 | 업로드 모드 | 업로드 동작 | 식별자 우선순위(단일 유형 파트너의 경우) |
| --- | --- | --- | --- | --- |
| Meta | 이메일, 전화번호, IDFA, GAID, 안드로이드 ID, 이름, 성, 생년월일, 도시, 주, 우편번호, 국가 | 지원되는 모든 유형 | 지원되는 모든 식별자 유형을 업로드합니다. | 해당 없음 - 모든 업로드 |
| Google | 이메일, 전화번호, IDFA, GAID, 안드로이드 ID, 고객 ID | 단일 유형 | 청중별로 식별자 유형을 하나씩 업로드합니다. | 1. 이메일 1: phone 모바일 ID 4. 고객 ID |
| TikTok | 이메일, 전화번호, IDFA, GAID, 안드로이드 ID | 지원되는 모든 유형 | 지원되는 모든 식별자 유형을 업로드합니다. | 해당 없음 - 모든 업로드 |
| Pinterest | 이메일, 전화번호, IDFA, GAID | 단일 유형 | 청중별로 식별자 유형을 하나씩 업로드합니다. | 1. 이메일 1: phone 모바일 ID |
| Infillion | 이메일, 전화번호, IDFA, GAID, MM-UUID | 지원되는 모든 유형 | 지원되는 모든 파일 형식을 최대 3개까지 그룹화하여 업로드할 수 있습니다. | 해당 없음 - 모든 업로드 |
| TheTradeDesk | 이메일, 전화번호: | 단일 유형 | 청중별로 식별자 유형을 하나씩 업로드합니다. | 1. 이메일 1: 전화 |
| 앱스플라이어 - 데이터 락커 | 사용 가능한 식별자: | 모든 유형을 합산 | 모든 식별자를 하나의 통합 파일로 제공합니다. | 해당 없음 - 모든 것을 제공합니다 |

| 플랫폼 | 사용자당 여러 개의 ID를 보낼 수 있나요? | 그들이 그 중 어느 하나라도 일치시킬 수 있을까요? | 여러 개의 ID를 결합할 수 있나요? | 매칭 모델 (실용적) | 참고 |
| --- | --- | --- | --- | --- | --- |
| Meta | 예 | 예 | 예 | 결정론적, 모든 ID /조합 | 이메일, 전화, MAID, fbp/fbc 모두 평가; 가장 강력한 "이 중 하나" 행동 |
| Google | 예 | 제한됨 | 아니요 | 결정론적, 우선순위 지정 | 하나의 ID 사용자를 식별할 수 있으며, ID를 조합하여 일치하는 항목을 만들지는 않습니다. |
| TikTok | 예 | 예 | 예 | 결정론적, 모든 ID /조합 | Meta 와 매우 유사합니다. ttclid는 이벤트 처리에 강력합니다. |
| Pinterest | 예 | 부분적 | 제한됨 | 결정론적, ID 중심적 | 주로 이메일 과 MAID를 사용하며, 교차 ID 확인은 제한적으로 이루어집니다. |
| 더 트레이드 데스크(TTD) | 예 | ID 그래프를 통해 | 예 (그래프를 통해) | 항등 그래프를 통한 결정론적 접근 | EUID/UID2 그래프를 통해 UID2 + MAID + 쿠키가 해석됩니다. |
| Infillion | 예 | ID 그래프를 통해 | 예 (그래프를 통해) | 파트너 그래프를 통한 결정론적 접근 | OmniID/파트너 ID 확인에 의존합니다. |

**활성화 계획 수립을 위한 핵심 사항**

* **Meta 와 틱톡**
  * 가지고 있는 모든 것을 보내주세요
  * 진정한 "any- ID" 동작
  * 아이덴티티가 풍부한 클린룸 활성화를 위한 최고의 플랫폼
* **Google**
  * 커버리지 확보를 위해 여러 개의 ID를 보내주세요.
  * 교차 ID 강화 효과를 기대하지 마십시오.
  * 이메일/전화의 지배력은 실제 입니다.
* **TTD 및 충전**
  * 매칭 품질은 아이덴티티 그래프 참여도에 더 크게 좌우됩니다.
  * UID2/OmniID 적용 범위가 단순 식별자 개수보다 더 중요합니다.
* **Pinterest**
  * Meta 보다는 구글 에 더 가깝게 동작합니다.
  * 이메일 + MAID 외에는 상승 여력이 제한적입니다.

**핵심 요약**

* Meta 와 TikTok만이 "이러한 모든 것"을 기본적으로 매칭해주는 기능을 제공합니다.
* 구글 은 결정론적이지만 단일 ID 해결됩니다.
* 개방형 웹 플랫폼은 원시 ID가 아닌 ID 그래프를 통해 매칭합니다.

</Accordion>

<div id="appendix-e-hashed-data-formatting-guidelines-by-media-partner" />

<Accordion title="미디어 파트너가 제공하는 해시 데이터 형식 지정 지침">

**유니버설 정규화 규칙:**  
데이터를 해싱하기 전에 거의 모든 플랫폼은 매칭 정확도를 보장하기 위해 다음과 같은 정규화 단계를 요구합니다.

* **Text:** 소문자로 변환하고 앞뒤 공백을 모두 제거합니다.
* phone E.164 형식으로 변환하세요 (예: +15551234567)
* 해싱 SHA-256은 업계 표준이지만 일부 플랫폼에서는 MD5 또는 SHA-1도 허용합니다.

| 미디어 파트너 | 이메일 가이드라인 | 전화번호 지침 | 모바일 ID (MAID) 가이드라인 | 플랫폼별 특성 및 매칭 로직 | 관련 참고 자료 |
| --- | --- | --- | --- | --- | --- |
| Google Ads / DV360 | 형식: 소문자로 변환하고 공백을 제거하세요. 도메인을 포함하세요. Gmail 규칙: @gmail.com / @googlemail.com의 경우, "@" 앞에 있는 마침표(.)와 (+) 뒤에 있는 접미사를 제거하세요. 해싱 SHA-256 (16진수 인코딩). | 형식: E.164 (e.g., +16505551212). 국가 코드 포함 해싱 SHA-256. | 형식: IDFA(iOS) 또는 GAID(안드로이드). 해싱 해시하지 마세요. | 일치 우선순위: 결정론적이고 우선순위가 지정된 (1. 이메일 1: phone 모바일 ID). 여러 ID를 결합하여 일치하는 항목을 생성하지 않습니다(단일 ID 해결). DV360 PAIR: DV360은 안전한 게시자-광고주 조정을 위한 PAIR 프로토콜도 지원합니다. | <Anchor target="_blank" href="https://developers.google.com/google-ads/api/docs/remarketing/audience-segments/customer-match/get-started">고객 매칭(구글 Ads API) 시작하기</Anchor> |
| Meta (Facebook/ 인스타그램) | 형식: 소문자로 변환하고 공백을 제거하세요. 해싱 SHA-256이 필요합니다.<br /><br />**참고:** Meta 해싱 정규화 과정에서 이메일 주소의 점(.)을 제거하지 않습니다. Meta 의 해싱 전에는 소문자 및 공백 제거만 적용해야 합니다. 점(.)이 제거된 해시 이메일 (DCP 소스 매핑에서 "점 없는 해시 이메일 ")을 보내면 Meta 자체의 해시와 결과 하지 않아 이메일 도메인 사용자의 일치율이 낮아집니다. 이 식별자 변형은 점 제거가 필요한 파트너(예: 구글 Ads)를 위한 것이며 Meta/ Facebook 활성화에는 사용해서는 안 됩니다. | 형식: 기호, 문자 및 선행 0을 제거합니다. 국가 코드 포함 해싱 SHA-256. | 형식: IDFA 또는 GAID. 해싱 해시하지 마세요. 소문자로 작성하고 하이픈은 그대로 두세요. | 일치 논리: "이 중 어느 것이든"이라는 논리를 사용하며, 여러 ID(이메일, 전화번호, MAID 등)를 조합하여 사용자를 식별함으로써 강력한 교차 ID 강화 기능을 제공합니다.<br /><br />CAPI: 브라우저 매칭을 위해서는 해시되지 않은 client\_ip\_address와 client\_user\_agent가 필요합니다. | <Anchor target="_blank" href="https://developers.facebook.com/docs/marketing-api/conversions-api/parameters/customer-information-parameters/">고객 정보 매개변수 - 전환 API</Anchor> |
| TikTok | 형식: 소문자로 입력하고 공백을 모두 제거하세요. 해싱 SHA-256. | 형식: E.164 (+[국가 코드][숫자]). 플러스(+) 기호 없이도 허용됩니다. 해싱 SHA-256. | 형식: GAID(안드로이드) 또는 IDFA(iOS). 사례: 모두 위쪽이거나 모두 아래쪽입니다. 해싱: SHA-256 또는 MD5. | 매칭 논리: Meta 와 유사하게, 유효한 ID 하나만 있으면 되는 "어떤 것이든"이라는 결정론적 매칭 논리를 사용합니다.<br /><br />오디언스 규모 맞춤 잠재고객을 활성화하려면 최소 1,000명의 일치하는 사용자가 필요합니다. | <Anchor target="_blank" href="https://ads.tiktok.com/help/article/how-to-create-a-custom-audience-with-a-customer-file">고객 파일을 사용하여 맞춤 잠재고객을 만드는 방법</Anchor> |
| 트레이드 데스크(UID2) | 형식: 구글 과 동일한 "지메일 규칙"(점/플러스 기호 제거). 부호화: 원시 바이트를 Base64로 인코딩합니다(결과 는 44자입니다). | 형식: E.164. 해싱: SHA-256. 인코딩: 원시 바이트를 Base64로 인코딩합니다. | 형식: AAID(소문자) / IDFA(대문자). 해싱: SHA-256, MD5, or SHA-1. | 매칭 논리: 항등 그래프를 통한 결정론적 접근. 매칭은 단순히 ID 커버리지를 확인하는 것이 아니라 그래프 참여도를 기준으로 이루어집니다.<br /><br />중요한 뉘앙스: 해시의 원시 바이트를 base64로 인코딩해야 합니다. 16진수 문자열 인코딩이 실패합니다. |  |
| Pinterest | 형식: 반드시 "@"를 포함해야 합니다. 해싱: SHA-256, MD5, or SHA-1. | 형식: E.164. 특수 문자(공백, 하이픈)를 제거하세요. 해싱: SHA-256, MD5, or SHA-1. | 형식: IDFA 또는 GAID. 해싱: SHA-256, MD5, or SHA-1. | 매칭 논리: "ID-Centric." 매칭은 주로 이메일과 MAID 정보를 기반으로 이루어집니다. Meta 에 비해 교차 ID 강화가 미약하기 때문에 다른 ID를 제공하는 데에는 "제한적인 이점"만 있습니다. 업로드 동작: 오디언스별로 식별자 유형을 하나씩 업로드합니다. | DCP 데이터 수집 및 구조화 지침 |

</Accordion>

<div data-zendesk-anchors="about-dcp-ingestion-and-preparation-of-data=%EB%8D%B0%EC%9D%B4%ED%84%B0-%EC%A4%80%EB%B9%84%EC%97%90-%EA%B4%80%ED%95%98%EC%97%AC h_01KFX4HVTT50TZMY2YF37B1C4R=%EB%8D%B0%EC%9D%B4%ED%84%B0-%EC%A4%80%EB%B9%84%EC%97%90-%EA%B4%80%ED%95%98%EC%97%AC data-types=%EB%8D%B0%EC%9D%B4%ED%84%B0-%EC%9C%A0%ED%98%95%EC%9D%84-%EC%9D%B4%ED%95%B4%ED%95%98%EC%84%B8%EC%9A%94 h_01KFX4HVTTAMFEGJQEYXXWG9PT=%EB%8D%B0%EC%9D%B4%ED%84%B0-%EC%9C%A0%ED%98%95%EC%9D%84-%EC%9D%B4%ED%95%B4%ED%95%98%EC%84%B8%EC%9A%94 data-ingestion-recommendations=%EB%8D%B0%EC%9D%B4%ED%84%B0-%EA%B5%AC%EC%A1%B0%ED%99%94-%EC%A7%80%EC%B9%A8 h_01KFX4HVTT2Q2EV4GAC6M8R4A2=%EB%8D%B0%EC%9D%B4%ED%84%B0-%EA%B5%AC%EC%A1%B0%ED%99%94-%EC%A7%80%EC%B9%A8 h_01KFZJ2PK9XADZ2143VJB3YZ55=workflow-and-structuring-guidelines recommended-identifier-structures=%EA%B6%8C%EC%9E%A5-%EC%8B%9D%EB%B3%84%EC%9E%90-%EA%B5%AC%EC%A1%B0 h_01KFXB0KEF59QCYET0R8XNH84D=%EA%B6%8C%EC%9E%A5-%EC%8B%9D%EB%B3%84%EC%9E%90-%EA%B5%AC%EC%A1%B0 h_01KFZN8104KSPFRSS5SED7VT19=practical-checklist-for-dcp-collaborators identity-userlevel-dataset-checklist=%EC%8B%A0%EC%9B%90%EC%82%AC%EC%9A%A9%EC%9E%90-%EC%88%98%EC%A4%80-%EB%8D%B0%EC%9D%B4%ED%84%B0-%EC%84%B8%ED%8A%B8-%EC%B2%B4%ED%81%AC%EB%A6%AC%EC%8A%A4%ED%8A%B8 h_01KFZNGRC0XX7YYBYT09M49YFA=%EC%8B%A0%EC%9B%90%EC%82%AC%EC%9A%A9%EC%9E%90-%EC%88%98%EC%A4%80-%EB%8D%B0%EC%9D%B4%ED%84%B0-%EC%84%B8%ED%8A%B8-%EC%B2%B4%ED%81%AC%EB%A6%AC%EC%8A%A4%ED%8A%B8 transactional-events-dataset-checklist=%EA%B1%B0%EB%9E%98%EC%9D%B4%EB%B2%A4%ED%8A%B8-%EB%8D%B0%EC%9D%B4%ED%84%B0-%EC%84%B8%ED%8A%B8-%EC%B2%B4%ED%81%AC%EB%A6%AC%EC%8A%A4%ED%8A%B8 h_01KFZNJ7YKCT1YFYE400CNY6SP=%EA%B1%B0%EB%9E%98%EC%9D%B4%EB%B2%A4%ED%8A%B8-%EB%8D%B0%EC%9D%B4%ED%84%B0-%EC%84%B8%ED%8A%B8-%EC%B2%B4%ED%81%AC%EB%A6%AC%EC%8A%A4%ED%8A%B8 dataviews-checklist=%EB%8D%B0%EC%9D%B4%ED%84%B0-%EB%B3%B4%EA%B8%B0-%EC%B2%B4%ED%81%AC%EB%A6%AC%EC%8A%A4%ED%8A%B8 h_01KFZNKBXJQ4S89YHCGKP8J5F4=%EB%8D%B0%EC%9D%B4%ED%84%B0-%EB%B3%B4%EA%B8%B0-%EC%B2%B4%ED%81%AC%EB%A6%AC%EC%8A%A4%ED%8A%B8 h_01KFZJ2PK9TT2RZQ366Y2THS7E=supported-ingestion-cloud-services-and-formats format-guidance=%ED%98%95%EC%8B%9D-%EC%95%88%EB%82%B4 h_01KFX6XSNACVR9JWZWZW12F6C4=%ED%98%95%EC%8B%9D-%EC%95%88%EB%82%B4 h_01KFZJ2PK92Y5HHFC2D1H8AD9B=data-structures-that-arent-recommended avoid-multiple-columns-for-the-same-identifier-type=%ED%94%BC%ED%95%98%EB%8B%A4-%EB%8F%99%EC%9D%BC%ED%95%9C-%EC%8B%9D%EB%B3%84%EC%9E%90-%EC%9C%A0%ED%98%95%EC%97%90-%EB%8C%80%ED%95%9C-%EC%97%AC%EB%9F%AC-%EC%97%B4 h_01KFX72MNYH1CSKWZAGZ2XETXY=%ED%94%BC%ED%95%98%EB%8B%A4-%EB%8F%99%EC%9D%BC%ED%95%9C-%EC%8B%9D%EB%B3%84%EC%9E%90-%EC%9C%A0%ED%98%95%EC%97%90-%EB%8C%80%ED%95%9C-%EC%97%AC%EB%9F%AC-%EC%97%B4 avoid-%E2%80%9Clists-inside-a-single-cell%E2%80%9D-free-text=%ED%94%BC%ED%95%98%EB%8B%A4-%EB%8B%A8%EC%9D%BC-%EC%85%80-%EB%82%B4%EC%9D%98-%EB%AA%A9%EB%A1%9D%EC%9E%90%EC%9C%A0-%ED%85%8D%EC%8A%A4%ED%8A%B8 h_01KFX70V3BHNK93SKCRGGDVY3W=%ED%94%BC%ED%95%98%EB%8B%A4-%EB%8B%A8%EC%9D%BC-%EC%85%80-%EB%82%B4%EC%9D%98-%EB%AA%A9%EB%A1%9D%EC%9E%90%EC%9C%A0-%ED%85%8D%EC%8A%A4%ED%8A%B8 avoid-multiple-rows-per-user-for-identifiers-when-your-goal-is-a-user-identity-table=%ED%94%BC%ED%95%98%EB%8B%A4-%EC%82%AC%EC%9A%A9%EC%9E%90-%EC%8B%9D%EB%B3%84%EC%9E%90%EB%A5%BC-%EC%9C%84%ED%95%9C-%EC%97%AC%EB%9F%AC-%ED%96%89%EC%9D%B4-%EC%82%AC%EC%9A%A9%EC%9E%90%EB%B3%84%EB%A1%9C-%ED%95%84%EC%9A%94%ED%95%A9%EB%8B%88%EB%8B%A4%EC%82%AC%EC%9A%A9%EC%9E%90-id-%ED%91%9C-%EB%A7%8C%EB%93%A4%EB%A0%A4-%EB%AA%A9%ED%91%9C-%EA%B2%BD%EC%9A%B0 h_01KFX70V3BJE2PR7132QE27C4V=%ED%94%BC%ED%95%98%EB%8B%A4-%EC%82%AC%EC%9A%A9%EC%9E%90-%EC%8B%9D%EB%B3%84%EC%9E%90%EB%A5%BC-%EC%9C%84%ED%95%9C-%EC%97%AC%EB%9F%AC-%ED%96%89%EC%9D%B4-%EC%82%AC%EC%9A%A9%EC%9E%90%EB%B3%84%EB%A1%9C-%ED%95%84%EC%9A%94%ED%95%A9%EB%8B%88%EB%8B%A4%EC%82%AC%EC%9A%A9%EC%9E%90-id-%ED%91%9C-%EB%A7%8C%EB%93%A4%EB%A0%A4-%EB%AA%A9%ED%91%9C-%EA%B2%BD%EC%9A%B0 additional-information=%EC%B6%94%EA%B0%80-%EC%A0%95%EB%B3%B4 h_01KFZJ2PNKB4X962VKCKSYVFFB=%EC%B6%94%EA%B0%80-%EC%A0%95%EB%B3%B4 h_01KFX6XSJYGYFF052EM8NHNMYQ=appendix-a-transactional-data-examples h_01KFX6XSJYZNCTGD5CNSKN5KF7=appendix-b-connectorspecific-example-assets-aws-s3-gcs-bigquery-snowflake what-does-%E2%80%9Carraylist-of-identifiers%E2%80%9D-mean=%EC%8B%9D%EB%B3%84%EC%9E%90-%EB%B0%B0%EC%97%B4%EB%AA%A9%EB%A1%9D%EC%9D%B4%EB%9E%80-%EB%AC%B4%EC%97%87%EC%9D%84-%EC%9D%98%EB%AF%B8%ED%95%A9%EB%8B%88%EA%B9%8C h_01KFX4HVTVPHZQFNRWDH9VCEZQ=%EC%8B%9D%EB%B3%84%EC%9E%90-%EB%B0%B0%EC%97%B4%EB%AA%A9%EB%A1%9D%EC%9D%B4%EB%9E%80-%EB%AC%B4%EC%97%87%EC%9D%84-%EC%9D%98%EB%AF%B8%ED%95%A9%EB%8B%88%EA%B9%8C 1-aws-s3-and-gcs-connector-parquet=1-aws-s3-%EB%B0%8F-gcs-%EC%BB%A4%EB%84%A5%ED%84%B0parquet h_01KFX4HVTVNQZY9A8AGEBBHF6Y=1-aws-s3-%EB%B0%8F-gcs-%EC%BB%A4%EB%84%A5%ED%84%B0parquet 2-bigquery-connector-table-preview-and-schema-screenshot=2-bigquery-%EC%BB%A4%EB%84%A5%ED%84%B0%ED%91%9C-%EB%AF%B8%EB%A6%AC%EB%B3%B4%EA%B8%B0-%EB%B0%8F-%EC%8A%A4%ED%82%A4%EB%A7%88-%EC%8A%A4%ED%81%AC%EB%A6%B0%EC%83%B7 h_01KFX4HVTVCMB0H1B76TCK36SF=2-bigquery-%EC%BB%A4%EB%84%A5%ED%84%B0%ED%91%9C-%EB%AF%B8%EB%A6%AC%EB%B3%B4%EA%B8%B0-%EB%B0%8F-%EC%8A%A4%ED%82%A4%EB%A7%88-%EC%8A%A4%ED%81%AC%EB%A6%B0%EC%83%B7 3-snowflake-connector-table-preview-and-schema-screenshot=3-snowflake-%EC%BB%A4%EB%84%A5%ED%84%B0%ED%91%9C-%EB%AF%B8%EB%A6%AC%EB%B3%B4%EA%B8%B0-%EB%B0%8F-%EC%8A%A4%ED%82%A4%EB%A7%88-%EC%8A%A4%ED%81%AC%EB%A6%B0%EC%83%B7 h_01KFX4HVTVN9MSWFB7ZRT9MVCG=3-snowflake-%EC%BB%A4%EB%84%A5%ED%84%B0%ED%91%9C-%EB%AF%B8%EB%A6%AC%EB%B3%B4%EA%B8%B0-%EB%B0%8F-%EC%8A%A4%ED%82%A4%EB%A7%88-%EC%8A%A4%ED%81%AC%EB%A6%B0%EC%83%B7 h_01KFX6XSJYF4V3ZTX8X07J0FGS=appendix-c-why-dataviews-matter-and-recommended are-businessoriented-and-easier-to-collaborate-with=%EB%B9%84%EC%A6%88%EB%8B%88%EC%8A%A4-%EC%A7%80%ED%96%A5%EC%A0%81%EC%9D%B4%EB%A9%B0-%ED%98%91%EC%97%85%EC%9D%B4-%EB%8D%94-%EC%9A%A9%EC%9D%B4%ED%95%A9%EB%8B%88%EB%8B%A4 h_01KFX4HVTV43QFEQARSB2N49Z5=%EB%B9%84%EC%A6%88%EB%8B%88%EC%8A%A4-%EC%A7%80%ED%96%A5%EC%A0%81%EC%9D%B4%EB%A9%B0-%ED%98%91%EC%97%85%EC%9D%B4-%EB%8D%94-%EC%9A%A9%EC%9D%B4%ED%95%A9%EB%8B%88%EB%8B%A4 are-more-privacysafe-by-design=%EC%84%A4%EA%B3%84%EC%83%81-%EA%B0%9C%EC%9D%B8%EC%A0%95%EB%B3%B4-%EB%B3%B4%ED%98%B8%EC%97%90-%EB%8D%94%EC%9A%B1-%EC%95%88%EC%A0%84%ED%95%A9%EB%8B%88%EB%8B%A4 h_01KFX4HVTVJA8Q3FTQB8A94MA1=%EC%84%A4%EA%B3%84%EC%83%81-%EA%B0%9C%EC%9D%B8%EC%A0%95%EB%B3%B4-%EB%B3%B4%ED%98%B8%EC%97%90-%EB%8D%94%EC%9A%B1-%EC%95%88%EC%A0%84%ED%95%A9%EB%8B%88%EB%8B%A4 protect-sensitive-business-data=%EC%A4%91%EC%9A%94%ED%95%9C-%EB%B9%84%EC%A6%88%EB%8B%88%EC%8A%A4-%EB%8D%B0%EC%9D%B4%ED%84%B0%EB%A5%BC-%EB%B3%B4%ED%98%B8%ED%95%98%EC%84%B8%EC%9A%94 h_01KFX4HVTVF8A0PM90FA6XA0V5=%EC%A4%91%EC%9A%94%ED%95%9C-%EB%B9%84%EC%A6%88%EB%8B%88%EC%8A%A4-%EB%8D%B0%EC%9D%B4%ED%84%B0%EB%A5%BC-%EB%B3%B4%ED%98%B8%ED%95%98%EC%84%B8%EC%9A%94 can-make-your-data-more-costeffective-and-performant=%EB%8D%B0%EC%9D%B4%ED%84%B0%EB%A5%BC-%EB%8D%94%EC%9A%B1-%EB%B9%84%EC%9A%A9-%ED%9A%A8%EC%9C%A8%EC%A0%81%EC%9D%B4%EA%B3%A0-%EC%84%B1%EB%8A%A5%EC%9D%B4-%EB%9B%B0%EC%96%B4%EB%82%98%EA%B2%8C-%EB%A7%8C%EB%93%A4-%EC%88%98-%EC%9E%88%EC%8A%B5%EB%8B%88%EB%8B%A4 h_01KFX4HVTVJ70HV606Y8KE4JD1=%EB%8D%B0%EC%9D%B4%ED%84%B0%EB%A5%BC-%EB%8D%94%EC%9A%B1-%EB%B9%84%EC%9A%A9-%ED%9A%A8%EC%9C%A8%EC%A0%81%EC%9D%B4%EA%B3%A0-%EC%84%B1%EB%8A%A5%EC%9D%B4-%EB%9B%B0%EC%96%B4%EB%82%98%EA%B2%8C-%EB%A7%8C%EB%93%A4-%EC%88%98-%EC%9E%88%EC%8A%B5%EB%8B%88%EB%8B%A4 h_01KFX6XSJY4WGJDBP5JEQXC6E3=appendix-d-multiple-ids-keys-upload-and-matching-behavior-by-platform h_01KGFDYKG8KPYR7H5VBKVTXTQS=appendix-e-hashed-data-formatting-guidelines-by-media-partner" />
