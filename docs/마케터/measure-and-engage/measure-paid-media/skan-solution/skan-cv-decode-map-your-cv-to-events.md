---
title: SKAN CV 디코딩(CV를 이벤트에 매핑)
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
  created_at: '2020-10-26T20:31:40Z'
  edited_at: '2026-10-14T10:31:07Z'
  id: 360014696297
  locale: ko
  section: SKAN solution
  section_id: 6552135379985
  url: https://support.appsflyer.com/hc/ko/articles/360014696297
---
> **한눈에 보기:** 앱스플라이어는 사용자가 설정한 전환 값을 디코딩하여 이벤트로 변환합니다. 이벤트는 SKAN 대시보드, 로데이터, 파트너에 대한 포스트백을 채우는 데 사용됩니다.

![SKAdNetwork_-_Custom__1_.png](https://files.readme.io/74f0d3836ee6a73f6746afa2d6d6a468c09cba696561c5a2075149ca360b78bf-34255690318097.png)

<div id="decode-skan-conversion-value" />

## SKAN 전환 값 디코딩

광고주는 <Anchor target="_blank" href="/marketers/ko/docs/skan-conversion-studio">변환 스튜디오</Anchor>에서 사용할 수 있는 옵션을 사용하는 대신 전환 가치 디코딩을 사용합니다. Decode를 사용하는 경우 앱 로직에 따라 <Anchor target="_blank" href="https://developer.apple.com/documentation/storekit/skadnetwork/4097267-updatepostbackconversionvalue">updatePostbackConversionValue</Anchor>를 설정해야 합니다.

앱에서 전환 가치(CV)를 설정하는 것 외에도 나머지 흐름, 기능 및 보고 옵션은 <Anchor target="_blank" href="/marketers/ko/docs/skadnetwork-skan-solution-guide">SKAN 솔루션 가이드</Anchor>에 설명된 것과 동일합니다. 즉, 액티비티 윈도우(사용자가 제어)가 만료되면 iOS는 포스트백을 광고 네트워크로 전송하고, 광고 네트워크는 이를 앱스플라이어에 전달합니다. 앱스플라이어는 SDK에서 설정한 디코딩된 CV와 마찬가지로 처리된 이벤트로 매핑에 따라 CV를 디코딩합니다.

<div id="custom-conversion-valuedecode" />

## 사용자 지정 변환 값 - 디코딩

사용자 정의 CV 디코드를 구현하려면 CV 매핑이 포함된 CSV 파일을 앱스플라이어 플랫폼에 업로드해야 합니다.

**디코딩 매핑 원칙**

* 미세 변환 값(1&#126;63)에 대한 디코드 매핑을 제공하고, Windows 1&#126;3에 대한 거친 변환 값(낮음, 보통, 높음)을 제공합니다. 전체 값 범위를 매핑해야 하는 것은 아닙니다. 예를 들어 값 1, 2, 10 및 43을 매핑할 수 있습니다.
* CV 0은 항상 설치에 매핑됩니다. 설정할 수 없습니다.
* 매핑 테이블은 CSV 파일로 앱스플라이어에 업로드됩니다. 필요에 따라 업데이트된 매핑 테이블을 업로드할 수 있습니다.
* iOS에서 포스트백을 받으면 CV는 예제와 같이 이벤트로 디코딩됩니다.
* 설치 시간은 포스트백 도착 시간을 사용하여 파생됩니다.
* 이벤트의 시간은 설치 시간과 동일합니다.
* 스키마를 준비하는 방법을 가장 잘 이해하려면 다음 매핑 시나리오를 검토하십시오.
* <Anchor target="_blank" href="/marketers/ko/docs/in-app-event-postback-configuration#커스텀-이벤트">인앱 이벤트</Anchor> 이름을 사용자 정의할 수 있습니다.
  * 즉, SDK에서 보낸 적이 없더라도 새 이벤트 이름을 보냅니다.
  * 인앱 이벤트를 광고 네트워크 인앱 이벤트에 매핑할 수 있습니다.
  * 이는 Meta 광고 통합에도 적용되며, 다음 섹션에 자세히 설명된 Meta 관련 규칙이 적용됩니다.

<div id="decode-mapping-scenario-rules" />

<Accordion title="디코딩 매핑 시나리오 규칙">

고려 사항:

* 미세한 변환 값 범위: 1-63
* 대략적인 변환 값 범위: 낮음, 중간, 높음
* 주어진 전환 가치는 광고주가 지정한 하나 이상의 인앱 이벤트에 매핑됩니다. 인앱 이벤트에는 선택적 매개변수가 있습니다.
* 예를 들면 다음과 같습니다. 설치 날짜가 2월 1일 08:00이라고 가정합니다.
* 다음 표는 디코딩 매핑 테이블의 예입니다. 해당 구조는 필요한 CSV 파일의 구조와 유사합니다. 다음 표에는 디코딩 프로세스의 결과로 생성된 이벤트가 있습니다.
* 설치 이벤트는 매핑에 관계없이 항상 생성됩니다.
* 수익 측정:
  * 수익은 USD로 표시됩니다.
  * 주어진 전환 가치에는 min\_revenue와 max\_revenue로 제한되는 수익 범위가 있습니다.
  * 집계된 보고서 및 대시보드에서 수익은 범위의 평균으로 계산됩니다. 예: min\_revenue=4 및 max\_revenue=10인 경우, 계산된 수익은 7입니다.
  * 로데이터 보고서에는 계산된 수익(skad\_revenue), min\_revenue 및 max\_revenue이 포함됩니다.

<div id="meta-specific-rules" />

#### **메타 특정 규칙**

Meta 광고와 통합하는 경우 다음 규칙을 준수하세요.

* 지정된 전환 가치에 대한 최소 및 최대 수익 값은 서로 달라야 합니다. 즉, 같지 않습니다.
* 값은 겹치지 않아야 하며 다음 표의 conversion\_value 1-2 및 62와 같이 연속된 순서여야 합니다.
* 이벤트 횟수: Meta 광고는 이 값을 고려하지 않습니다. [모범 사례] 값 1로 채웁니다.

<div id="example-decode-mapping" />

### 예시: 디코딩 매핑

| conversion\_  <br />값에 포함되어 있으며, | event\_  <br />이름 | event\_  <br />값에 포함되어 있으며, | min\_revenue<br /><br />(포함되지 않음) | max\_revenue(포함) | event\_  <br />카운터 | hours\_from\_  <br />인스톨 |
| --- | --- | --- | --- | --- | --- | --- |
| 1 | af\_구매 | abc | 0 | 3 | 1 | 24 |
| 2 | af\_구매 | `{def}` | 3 | 10 | 3 | 36 |
| 21 | event\_a |  |  |  | 1 | 24 |
| 21 | event\_b |  |  |  | 3 | 24 |
| 21 | event\_c | xyz$ |  |  | 2 | 24 |
| 21 | event\_d |  |  |  | 1 | 24 |
| 21 | event\_e |  |  |  | 1 | 24 |
| 21 | event\_f |  |  |  | 1 | 24 |
| 21 | event\_g |  |  |  | 1 | 24 |
| 62 | af\_구매 | \{fgh) | 10 | 17 | 2 | 72 |
| 62 | event\_a | `{klm}` |  |  | 3 | 72 |

<div id="example-a-fine-conversion-value-1" />

### 예제 A: 미세한 변환 값 1

| event\_name | skad\_수익 | min\_revenue | max\_revenue | event\_value |
| --- | --- | --- | --- | --- |
| 인스톨 |  |  |  |  |
| af\_구매 | 1.5 | 0 | 3 | abc |

<div id="example-b-fine-conversion-value-2" />

### 예시 B: 미세한 변환 값 2

| event\_name | skad\_수익 | min\_revenue | max\_revenue | event\_value |
| --- | --- | --- | --- | --- |
| 인스톨 |  |  |  |  |
| af\_구매 | 6.5 | 3 | 10 | `{def}` |
| af\_구매 | 6.5 | 3 | 10 | `{def}` |
| af\_구매 | 6.5 | 3 | 10 | `{def}` |

<div id="example-c-fine-conversion-value-21" />

### 예시 C: 미세한 변환 값 21

| event\_name | skad\_수익 | min\_revenue | max\_revenue | event\_value |
| --- | --- | --- | --- | --- |
| 인스톨 |  |  |  |  |
| event\_a |  |  |  |  |
| event\_b |  |  |  |  |
| event\_b |  |  |  |  |
| event\_b |  |  |  |  |
| event\_c |  |  |  | xyz$ |
| event\_c |  |  |  | xyz$ |
| event\_d |  |  |  |  |
| event\_e |  |  |  |  |
| event\_f |  |  |  |  |
| event\_g |  |  |  |  |

<div id="ssot-support-for-decode-mode" />

<div id="faq" />

<div id="how-to-enable-ssot-for-decode-mode" />

<div id="key-benefits" />

<div id="overview" />

<div id="example-d-fine-conversion-value-62" />

### 예시 D: 미세한 변환 값 62

| event\_name | skad\_수익 | min\_revenue | max\_revenue | event\_value |
| --- | --- | --- | --- | --- |
| 인스톨 |  |  |  |  |
| af\_구매 | 13.5 | 10 | 17 | `{fgh}` |
| af\_구매 | 13.5 | 10 | 17 | `{fgh}` |
| event\_a |  |  |  | `{klm}` |
| event\_a |  |  |  | `{klm}` |
| event\_a |  |  |  | `{klm}` |

</Accordion>

<div id="zd-decode-csv-file-specification" />

<div id="decode-csv-file-specification" />

<Accordion title="csv 파일 사양 디코딩">

전환 가치는 하나 이상의 인앱 이벤트에 매핑됩니다.

**파일 규칙**

* 형식: CSV 파일
* 최대 행 수: 640 + 헤더 행; 총 641개.
* 머리글 행  여기에 표시되는 대로 모든 열 이름을 정확히 포함해야 합니다. 모범 사례: 첨부된 예제 파일을 템플릿으로 사용합니다. <Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vSCbqgR0D0hqJni36FTOr0MEAaIJSx9h2qaUQ-vWmCUGj7j_-00Ap3J8k4LohMQPndkooLrFFpFPtnH/pub?gid=0&single=true&output=csv">SKAN 3</Anchor>및 <Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vSCbqgR0D0hqJni36FTOr0MEAaIJSx9h2qaUQ-vWmCUGj7j_-00Ap3J8k4LohMQPndkooLrFFpFPtnH/pub?gid=1187444449&single=true&output=csv">SKAN 4</Anchor>에 대한 샘플 디코딩 CSV 파일을 참조하세요.
* 다음 문자를 열의 첫 번째 문자로 사용하지 마세요:`=`,`+`,`-` 및 `@` (편집됨).

### csv 파일 사양 디코딩

| 열 | 필수 값 | 콘텐츠 | 세부 정보 |
| --- | --- | --- | --- |
| 전환 값 | 예, 다음과 같은 경우:<ul><li>SKAN 3 이하</li><li>postback\_sequence\_index가 0인 SKAN 4</li></ul> | 정수 값 1–63 | 동일한 미세한 전환 값이 두 번 이상 나열될 수 있습니다. 자세한 설명은 예제를 참조하십시오. |
| coarse\_conversion\_value | SKAN 4에만 해당 | 문자열:<ul><li>낮음</li><li>중간 규모</li><li>높음</li></ul> | 동일한 대략적인 변환 값이 두 번 이상 나열될 수 있습니다. |
| event\_name | 예 | 문자열 | 인앱 이벤트. 앱스플라이어에 이미 존재하는 이벤트일 필요는 없습니다.<br /><br />참고! 인앱 이벤트 이름은 대소문자를 구분합니다.<br /><br />모범 사례: 수익 af\_skad\_revenue의 이벤트 이름입니다. |
| event\_value | 아니요 | 문자열 | 광고주가 시스템에서 디코딩할 데이터를 포함하는 개발자가 설정한 문자열입니다. 일반적으로 JSON 형식입니다. |
| min\_revenue | 아니요 | 정수 또는 부동 소수점 | <ul><li>수익을 전환 가치와 연결하지 않으려면 min\_revenue 및 max\_revenue를 비워 두세요.</li><li>min\_revenue에 설정된 값은 포함되지 않습니다. 0보다 큼을 의미합니다. 0.0001과 유사</li><li>max\_value에 설정된 값은 포함됩니다.</li><li>예시: min\_revenue이 0이고 max\_revenue이 4이면 범위가 0.0001-4임을 의미합니다</li></ul>**참고!** Excel을 사용하여 파일을 생성하는 경우 저장하기 전에 열 형식을 통화가 아닌 쉼표로 변경하여 Excel에서 CSV 파일에 $ 기호가 포함되지 않도록 합니다. |
| max\_revenue | 아니요 |  | min\_revenue 채우는 경우: max\_revenue은 0보다 큰 값을 가져야 합니다.<br /><br />자세한 내용은 min\_revenue 참조하십시오. |
| event\_revenue\_usd | 아니요 |  | 2021년 6월 7일부터 더 이상 사용되지 않습니다. min\_revenue 및 max\_revenue 사용 |
| event\_counter | 예 | 정수 | <ul><li>디코딩 시 이벤트가 중복되는 횟수입니다. 일반적으로 사용자가 지정된 작업을 수행한 횟수를 나타냅니다.</li><li>최소값 1.</li></ul>예시: 사용자가 지정된 이벤트를 5번 수행한 경우 5개의 이벤트가 생성됩니다.<br /><br />고려 사항: 수익을 보내는 경우 보고된 총 USD 금액에 event\_counter의 값을 곱합니다. 즉, min\_revenue = 0, max\_revenue = 3, event\_counter = 4인 경우 총 수익은 1.5 X 4 = 6으로 보고됩니다.<br /><br />예제를 참조하십시오. |
| hours\_from\_install | 예 | 정수 | <ul><li>설치 후 경과 시간</li><li>최소값: 1</li><li>최대값: 1512(63일)</li><li>지정된 conversion\_value의 모든 행에 대한 값은 동일해야 합니다. 즉, 서로 다른 변환 값에 대해 다른 값이 허용됩니다.</li></ul>앱스플라이어는 이를 사용하여 다음과 같이 설치 날짜를 도출하고 설정합니다.<ul><li>포스트백이 SKAN V4인 경우 설치 날짜 공식은 다음과 같습니다. 설치 날짜 = 포스트백 도착 시간 - [누적 윈도우 길이] - [평균 포스트백 지연].<ul><li>포스트백 1: 설치 날짜 = 포스트백 도착 시간 - 48시간 - 36시간</li></ul></li><li>포스트백이 SKAN V3인 경우 설치 날짜 공식은 다음과 같습니다. 설치 날짜 = 포스트백 도착 시간 - 36시간 - [평균 최종 활성 범위].<ul><li>기본값 [평균 최종 활성 범위]는 12시간입니다.</li><li>전환 값이 0인 경우 평균 최종 활성 범위는 0으로 설정됩니다.</li></ul></li></ul> |
| postback\_sequence\_index | 예, 하지만 SKAN 4에만 해당 | 정수<ul><li>0</li><li>1</li><li>2</li></ul> | 정확한 값의 경우 0의 값만 받을 수 있습니다. |

</Accordion>

<div id="upload-conversion-value-schema-file" />

<Accordion title="전환값 스키마 파일 업로드">

**시작하기 전**:

* 변환 값 스키마 CSV 파일을 준비합니다.
* Meta 광고와 통합하고 수익을 측정하는 경우 스키마가 [Meta 관련 규칙](/docs/skan-cv-decode-map-your-cv-to-events#메타-특정-규칙)을 준수하는지 확인하세요. 그렇지 않으면 Meta 광고에서 스키마를 해석할 수 없습니다.

**디코드 측정을 사용하여 SKAN 측정을 활성화하는 방법:**

1. 앱스플라이어에서 **설정** > **SKAN 변환 스튜디오**로 이동합니다.
2. 옵션(⋮)을 클릭하고 **디코드 매핑 파일 업로드**를 선택합니다.
3. 아직 SKAN 4로 업그레이드하지 않았다면 SKAN 4 또는 SKAN 4 이전 버전용 파일 업로드를 선택하십시오. SKAN 4로 업그레이드하면 다른 버전을 선택할 수 없습니다.
4. 다음 중 하나를 선택하세요.
   * **파일을 끌어서 놓으세요.**
   * **업데이트된 매핑 파일을 업로드합니다.**
5. 사용자 인터페이스의 지침에 따라 파일을 업로드합니다.
6. **SKAN 측정 기능**을 켭니다.
7. **변경 사항 저장**을 클릭하세요.   
   참고: 다음 48-72시간 동안 대시보드의 데이터가 모호합니다. 즉, iOS 타이머 문제로 인해 디코딩 매핑이 사용자가 사용한 인코딩 매핑과 일치하는지 확신할 수 없습니다.
8. 파트너가 포스트백을 올바르게 사용할 수 있도록 인앱 이벤트를 파트너가 사용하는 이벤트에 매핑했는지 확인하십시오.

</Accordion>

<div id="upload-error-messages" />

<div id="troubleshooting-the-csv-upload-errors-file" />

## CSV 업로드 오류 파일 문제 해결

파일에 있는 하나 이상의 값이 필요한 형식과 일치하지 않습니다. 2021년 6월 7일부터 파일 형식이 변경되었습니다. 파일 형식이 이 문서의 예제와 일치하는지 확인합니다.


<div id="using-excel-to-format-the-event_revenue_usd-column" />

<Accordion title="Excel을 사용하여 event_revenue_usd 열 서식 지정">

Excel/Google 시트를 사용하여 CSV 파일을 만드는 경우 파일을 CSV 파일로 저장하기 전에 event\_revenue\_usd 열의 형식을 올바르게 지정해야 합니다.

CSV 파일을 저장한 후 콘텐츠의 형식이 올바른지 확인합니다. **참고**: 확인을 위해 Excel을 사용하지 말고 [편집기](/docs/skan-cv-decode-map-your-cv-to-events#visual-inspection-of-the-csv-file-without-excel)를 사용하세요.

<div id="formatting-event_revenue_usd-cells-in-excel" />

#### Excel에서 event\_revenue\_usd 셀 서식 지정

그림에 표시된 대로 Excel은 일반적으로 값 셀을 쉼표로 형식화하여 수천 개로 구분합니다. 이 형식은 CSV 파일을 업로드하는 데 적합하지 않습니다. $ 기호도 제거해야 합니다.

![mceclip0.png](https://files.readme.io/3b2aface429f87eb651e6d678760ee3a4b85234a11b0ae2da771d7af7279c1e7-34255643021073.png)

Excel에서 셀 서식을 지정하여 이 문제를 해결할 수 있습니다.

**1000 단위 구분 기호 없이 지출 금액의 형식을 지정하려면:**

1. 서식을 지정할 셀을 선택합니다.
2. 마우스 오른쪽 버튼을 클릭하고 **셀 포맷**을 선택합니다.  
   셀 형식 창이 열립니다.
3. **숫자**를 선택합니다.

1. **1000 단위 구분 기호(,) 사용**을 선택 취소합니다.
2. (선택 사항) **소수점 이하 자릿수**를 설정합니다. 기본값은 2입니다. 허용되는 최대 개수는 5개입니다.
3. **확인**을 클릭하십시오.  
   셀이 올바르게 포맷되었습니다.

</Accordion>

<div id="visual-inspection-of-the-csv-file-without-excel" />

<Accordion title="Excel 없이 CSV 파일의 육안 검사">

CSV 파일의 내용을 검사하려면 편집기를 사용하여 파일을 봅니다.

* Windows: 메모장, 메모장++
* macOS: TextEdit

다음은 편집기에 표시되는 <Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vSCbqgR0D0hqJni36FTOr0MEAaIJSx9h2qaUQ-vWmCUGj7j_-00Ap3J8k4LohMQPndkooLrFFpFPtnH/pub?output=csv">예제 CSV 파일</Anchor>의 스크린샷입니다.

**편집기 보기**

![SKCustomeEditor.png](https://files.readme.io/d8677e9967a70db32e8d04c4ee835bd477b18c1cb464a9cd0e593f72ce3f3c15-34255690323217.png)

편집기를 사용하여 CSV 파일을 검사합니다. 다음 사항에 특히 주의하십시오.

* **공백:** 필드를 구분하는 쉼표의 앞뒤에 공백이 없는지 확인합니다. Excel에서 @trim 명령을 사용하여 공백을 제거합니다.
* **event\_revenue\_usd:** event\_revenue\_usd 열에 쉼표나 $ 기호가 없는지 확인합니다.  

  ![mceclip1.png](https://files.readme.io/3b2aface429f87eb651e6d678760ee3a4b85234a11b0ae2da771d7af7279c1e7-34255643021073.png)

</Accordion>

<div id="csv-files-generated-by-excel-dont-have-commas-as-delimiters" />

<Accordion title="Excel에서 생성된 CSV 파일에는 구분 기호로 쉼표가 없습니다.">

Excel에서 세미콜론 ";" 또는 기타 문자를 구분 기호로 사용하지만 쉼표는 사용하지 않는 CSV 파일을 만드는 경우:

* 이 문제는 컴퓨터의 국가별 설정이 영어가 아닌 언어/지역으로 설정되어 있을 때 발생합니다.
* 국가별 설정에서 독일어를 선택할 때 특히 자주 발생합니다.
* 해결 방법은 컴퓨터 운영 체제(macOS 또는 Windows)에 따라 다릅니다.
* 이 문제를 해결하려면 <Anchor target="_blank" href="https://support.office.com/en-us/article/import-or-export-text-txt-or-csv-files-5250ac4c-663c-47ce-937b-339e391393ba#ID0EAAFAAA=Office_2016-2010">Microsoft</Anchor> 또는 다른 포럼에서 시작할 최신 안내를 검색하여 해결하십시오. 다음 검색어를 사용하세요. *운영 체제 (macOS 또는 Windows) Excel에서 CSV 파일의 구분 기호를 변경합니다.*

</Accordion>

<div data-zendesk-anchors="decode-skan-conversion-value=skan-%EC%A0%84%ED%99%98-%EA%B0%92-%EB%94%94%EC%BD%94%EB%94%A9 h_01HAMKKCKJEGCDPN5P8J6X0E8E=skan-%EC%A0%84%ED%99%98-%EA%B0%92-%EB%94%94%EC%BD%94%EB%94%A9 custom-conversion-value%E2%80%94decode=%EC%82%AC%EC%9A%A9%EC%9E%90-%EC%A7%80%EC%A0%95-%EB%B3%80%ED%99%98-%EA%B0%92---%EB%94%94%EC%BD%94%EB%94%A9 h_01HAMKKCKJ5K6J6NNPF394ZK61=%EC%82%AC%EC%9A%A9%EC%9E%90-%EC%A7%80%EC%A0%95-%EB%B3%80%ED%99%98-%EA%B0%92---%EB%94%94%EC%BD%94%EB%94%A9 h_01HAMKKCKJT7MA03SHT4X3MH4W=decode-mapping-scenario-rules facebookspecific-rules=%EB%A9%94%ED%83%80-%ED%8A%B9%EC%A0%95-%EA%B7%9C%EC%B9%99 h_01HAMKKCKJDCEKCNZFSF0V6KH8=%EB%A9%94%ED%83%80-%ED%8A%B9%EC%A0%95-%EA%B7%9C%EC%B9%99 example-decode-mapping=%EC%98%88%EC%8B%9C-%EB%94%94%EC%BD%94%EB%94%A9-%EB%A7%A4%ED%95%91 h_01HAMKKCKJ5B7W8FGK01QCKN7Y=%EC%98%88%EC%8B%9C-%EB%94%94%EC%BD%94%EB%94%A9-%EB%A7%A4%ED%95%91 example-b-conversion-value-1=%EC%98%88%EC%A0%9C-a-%EB%AF%B8%EC%84%B8%ED%95%9C-%EB%B3%80%ED%99%98-%EA%B0%92-1 h_01HAMKKCKJ1ZRH00A7Q4HZ4BBK=%EC%98%88%EC%A0%9C-a-%EB%AF%B8%EC%84%B8%ED%95%9C-%EB%B3%80%ED%99%98-%EA%B0%92-1 example-b-conversion-value-2=%EC%98%88%EC%8B%9C-b-%EB%AF%B8%EC%84%B8%ED%95%9C-%EB%B3%80%ED%99%98-%EA%B0%92-2 h_01HAMKKCKJZBASWWM1VD0VXWBX=%EC%98%88%EC%8B%9C-b-%EB%AF%B8%EC%84%B8%ED%95%9C-%EB%B3%80%ED%99%98-%EA%B0%92-2 example-c-conversion-value-21=%EC%98%88%EC%8B%9C-c-%EB%AF%B8%EC%84%B8%ED%95%9C-%EB%B3%80%ED%99%98-%EA%B0%92-21 h_01HAMKKCKJ4YHMQENKNVPMV4KC=%EC%98%88%EC%8B%9C-c-%EB%AF%B8%EC%84%B8%ED%95%9C-%EB%B3%80%ED%99%98-%EA%B0%92-21 example-d-conversion-value-62=%EC%98%88%EC%8B%9C-d-%EB%AF%B8%EC%84%B8%ED%95%9C-%EB%B3%80%ED%99%98-%EA%B0%92-62 h_01HAMKKCKJP7V7D26MGM1WVDTE=%EC%98%88%EC%8B%9C-d-%EB%AF%B8%EC%84%B8%ED%95%9C-%EB%B3%80%ED%99%98-%EA%B0%92-62 h_01HAMKKCKKJFRTXYJNWZNGF97V=decode-csv-file-specification decode-csv-file-specification::d6a1f3f1=csv-%ED%8C%8C%EC%9D%BC-%EC%82%AC%EC%96%91-%EB%94%94%EC%BD%94%EB%94%A9 h_01HAMKKCKK7G7VP6SDEHBH6383=csv-%ED%8C%8C%EC%9D%BC-%EC%82%AC%EC%96%91-%EB%94%94%EC%BD%94%EB%94%A9 h_01HAMKKCKKN7WDP6F5E4W91HQJ=upload-conversion-value-schema-file troubleshooting-the-csv-upload-errors-file=csv-%EC%97%85%EB%A1%9C%EB%93%9C-%EC%98%A4%EB%A5%98-%ED%8C%8C%EC%9D%BC-%EB%AC%B8%EC%A0%9C-%ED%95%B4%EA%B2%B0 h_01HAMKKCKK0QQ8AS8FZ83MZ8FH=csv-%EC%97%85%EB%A1%9C%EB%93%9C-%EC%98%A4%EB%A5%98-%ED%8C%8C%EC%9D%BC-%EB%AC%B8%EC%A0%9C-%ED%95%B4%EA%B2%B0 h_01HAMKKCKKFJAE4B88QV00HYPW=using-excel-to-format-the-event_revenue_usd-column formatting-event_revenue_usd-cells-in-excel=excel%EC%97%90%EC%84%9C-event_revenue_usd-%EC%85%80-%EC%84%9C%EC%8B%9D-%EC%A7%80%EC%A0%95 h_01HAMKKCKKKVYCWCQCAEMSBMF7=excel%EC%97%90%EC%84%9C-event_revenue_usd-%EC%85%80-%EC%84%9C%EC%8B%9D-%EC%A7%80%EC%A0%95 h_01HAMKKCKK39C9SP7K86ER3HZK=visual-inspection-of-the-csv-file-without-excel h_01HAMKKCKK9GEBC64JE4DSDAMQ=csv-files-generated-by-excel-dont-have-commas-as-delimiters" />
