---
title: 비용 데이터 가져오기
metadata:
  keywords:
    - Ad Network
    - Agency
    - Advertisers
    - Agencies
    - Premium
    - Premium Feature
    - Xpend
    - Marketers
    - ROI360
    - Ad Networks
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-maytav-avnat
    - Marketers
    - Agencies
    - ROI360
    - Ad Networks
  created_at: '2019-09-15T15:53:44Z'
  edited_at: '2026-10-14T10:37:00Z'
  id: 360002516838
  locale: ko
  section: Cost aggregation
  section_id: 6551029483281
  url: https://support.appsflyer.com/hc/ko/articles/360002516838
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **한눈에 보기:** 비용 가져오기, AppsFlyer ROI360의 일부로, 광고주가 업로드 또는 이메일을 통해 CSV 파일을 가져와 마케팅 비용을 완전하고 정확하게 파악할 수 있도록 합니다.

## 개요

비용 가져오기 사용

* 모든 마케팅 활동(모바일 캠페인, 인플루언서 캠페인, CTV 등)의 캠페인 비용을 AppsFlyer로 가져옵니다. 이는 API를 통해 비용을 보고하지 않거나 귀속 링크에서 보고하지 않는 미디어 소스에 특히 중요합니다.
* 기존 비용 데이터를 소급하여 덮어쓰고 수정합니다.

비용은 AppsFlyer에 업로드되거나 이메일로 전송된 CSV 파일을 통해 보고됩니다. AppsFlyer가 파일을 수신하면 데이터가 처리되어 몇 시간 내에 대시보드와 보고서에서 사용할 수 있게 됩니다. 이것은 캠페인 비용과 ROI에 대한 완전한 그림을 제공합니다.

**참고**:

* 광고 네트워크는 관련 권한이 제공되면 고객을 위해 비용 파일을 가져올 수 있습니다.
* 에이전시는 데이터를 업로드할 수 없습니다. 파일을 준비하고 광고주에게 보내 업로드할 수 있습니다.

## 절차

비용 가져오기 기능을 사용하고 비용 데이터를 AppsFlyer에 전송하려면 다음이 필요합니다:

1. [비용 데이터를 전송할 CSV 파일](/docs/import-cost-data#prepare-csv-file-with-cost-data)을 준비합니다.
2. 파일을 다음 방법 중 하나로 AppsFlyer에 전송합니다:
   * [AppsFlyer UI에서](/docs/import-cost-data#email-file) 업로드합니다.
   * 이메일 **참고**: CTV, PC, 콘솔 플랫폼의 앱에는 이 방법만 사용합니다.

자세한 지침은 다음 섹션을 참조하십시오.

<div id="prepare-csv-file-with-cost-data" />

<Accordion title="비용 데이터가 포함된 CSV 파일 준비">

광고주, 광고 네트워크 및 에이전시는 비용 가져오기 CSV 파일을 준비할 수 있습니다. <Anchor target="_blank" href="https://docs.google.com/spreadsheets/d/e/2PACX-1vQ0oJTWdlNyT1gBHkGaN1QP-tUatugbPBzC2qYVNmjl_T_i3fKo1abYzTp6F7OqGeN_f7bBAJa3hxVz/pub?gid=0&single=true&output=csv">샘플 파일을 참조하십시오.</Anchor>

CSV 파일 준비

* 다음 표에 자세히 설명된 파일 스키마, 형식 및 규칙을 따르십시오.  
  **참고**: Excel 또는 Google Sheets를 사용하여 파일을 생성하는 경우 [Excel 및 Google Sheets 형식 지침](/docs/import-cost-data#using-excel-or-google-sheets-to-prepare-csv-file)을 따르십시오.

#### CSV 스키마

<table><thead><tr><th><p><span>열 이름</span></p><p><span>(대소문자 구분)</span></p></th><th><span>형식/비고</span></th><th><span>예시</span></th><th><span>필수 여부</span></th></tr></thead><tbody><tr><td><span>date</span></td><td><ul><li><span>비용이 발생한 날짜</span></li><li> <span>형식: 문자열</span><br/><span>모범 사례:<ul><li><span>YYYY-MM-DD</span></li><li><span>YYYY/MM/DD</span></li><li><span>MM-DD-YYYY</span></li><li> <span>MM/DD/YYYY </span><br/> </li></ul></span> </li><li>향후 날짜는 허용되지 않습니다.</li><li> <strong>모범 사례</strong>: 앱스플라이어에서 앱에 대해 정의된 시간대와 동일한 시간대를 사용하세요.</li><li> <strong>참고</strong>: Excel/Google 시트를 사용하여 파일을 준비하고 있습니까? <a href="./import-cost-data#using-excel-or-google-sheets-to-prepare-csv-file">이것을 읽어보십시오</a>. </li></ul></td><td><ul><li><span>2019-05-30</span></li><li>$475.22</li><li><span>5-30-2019</span></li><li>5/30/2019</li><li>05-30-2019</li><li>05-30-2019</li></ul></td><td><span>✓</span></td></tr><tr><td><span>app-id</span></td><td><ul><li><span>형식: 문자열</span></li><li> 앱스플라이어에 표시되는 앱 ID</li><li>단일 파일에 여러 앱이 허용됩니다.</li><li>모든 앱 ID는 동일한 광고주 계정에 속해야 합니다.</li></ul></td><td><ul><li><span>com.app.name </span></li><li><span>id12356789</span></li></ul></td><td><span>✓</span></td></tr><tr><td><span>media-source</span></td><td><ul><li><span>형식: 문자열</span></li><li><span>미디어 소스 이름 <strong>정확히</strong> AppsFlyer에 표시된 대로입니다. <strong>참고:</strong> 관련이 있는 경우 _int 접미사를 포함하세요.</span></li><li> <span>파일당 하나의 미디어 소스만 허용됩니다.</span> 동일한 미디어 소스에 대해 여러 앱이 허용됩니다.</li></ul></td><td><span>network_x_int</span></td><td><span>✓</span></td></tr><tr><td><span>campaign</span></td><td><ul><li> <span>형식: 문자열</span><span></span> </li><li><span>캠페인 이름. 캠페인 이름이 광고 네트워크에 표시되면, 이 파일의 이름은 대소문자를 구분하여 일치해야 합니다.</span></li><li>다중 앱에 동일한 캠페인 이름을 사용하지 마십시오.</li></ul></td><td>campaign_a</td><td><p><span>✓</span></p><p><span><strong>참고</strong>: 어트리뷰션 데이터에 이름과 ID가 모두 존재하는 경우, 일치하려면 CSV에 두 가지가 모두 포함되어야 합니다.</span></p></td></tr><tr><td><span>지출</span></td><td><ul><li><span>금전적 비용</span></li><li><span>소수점 뒤에 5자리 숫자 허용</span></li><li><span>값 0(영)은 허용</span></li><li> 참고:<ul><li>1000개의 쉼표 구분자는 허용되지 않습니다. 예를 들어: "2,874.12".</li><li>Excel/Google 시트를 사용하여 파일을 준비하고 있습니까? <a href="./import-cost-data#using-excel-or-google-sheets-to-prepare-csv-file">여기를 참조하세요</a>.</li></ul></li></ul></td><td><p><span>2874.12345</span></p></td><td><span><span>✓</span></span></td></tr><tr><td><span>geo</span></td><td><ul><li><span>형식: 문자열</span></li><li> <span><a href="https://www.iso.org/iso-3166-country-codes.html">ISO 3166을</a> 준수하는 두 자리 국가 코드입니다. </span> <strong>참고</strong>: 공백 없이 두 개의 문자를 보내야 합니다. </li><li> <span>영국의 경우</span> GB가 아닌 UK<span> 를 사용합니다.<br/> </span> </li></ul></td><td><p><span>US, CN, AU</span></p></td><td><span>아니요</span></td></tr><tr><td><span>currency</span></td><td><ul><li><span>형식: 문자열</span></li><li>세 글자의 통화 코드는 ISO 4217을 준수해야 합니다.  <strong>참고</strong>: 선행 또는 후행 공백 없이 세 글자를 보내야 합니다.</li><li> <span>파일에 앱당 하나의 통화 코드가 허용됩니다. </span><span>앱마다 통화 코드가 다를 수 있습니다 </span>. </li></ul></td><td><span>USD, GBP, EUR, JPY</span></td><td><p><span>그것은 아닙니다.</span></p><p><span>비워 두면 기본적으로 USD로 설정됩니다.</span></p></td></tr><tr><td><span>campaign-id</span></td><td>형식: 문자열</td><td>abc1234def</td><td rowspan="5"><p>그것은 아닙니다.</p><p><strong>참고</strong>: 어트리뷰션 데이터에 이름과 ID가 모두 존재하는 경우, 일치하려면 CSV에 두 가지가 모두 포함되어야 합니다.</p></td></tr><tr><td><span>adset</span></td><td>형식: 문자열 </td><td>my_adset_1</td></tr><tr><td><span>adset-id</span></td><td>형식: 문자열</td><td>id5678ghi</td></tr><tr><td><span>ad</span></td><td>형식: 문자열 </td><td>my_ad_name</td></tr><tr><td> <span>ad-</span><span>id</span> </td><td>형식: 문자열 </td><td>id91011jkl</td></tr><tr><td><span>site-id</span></td><td><ul><li>형식: 문자열 </li><li>광고를 게재하는 퍼블리셔를 식별하는 고유 ID입니다. <a href="./about-link-structure-and-parameters#site-id-parameter" target="_blank">더 알아보기</a> </li></ul></td><td>id1213mno</td><td>아니요</td></tr><tr><td><span>channe</span></td><td>형식: 문자열 </td><td> 비디오</td><td>아니요</td></tr><tr><td><span>키워드</span></td><td>형식: 문자열</td><td><ul><li>더 좋은</li><li>더 나은 앱</li><li>더 나은 온라인</li></ul></td><td>아니요</td></tr><tr><td><span>에이전시</span></td><td><ul><li>형식: 문자열</li><li>에이전시 이름. <code>af_prt</code> 파라미터의 값입니다.</li><li>하나의 에이전시만 파일에 포함할 수 있습니다.그리고 해당 에이전시에서 관리하는 캠페인만 파일에 포함할 수 있습니다.</li><li>행마다 에이전시 이름을 입력해야 합니다. 에이전시 열에는 빈 셀이 허용되지 않습니다.</li><li>에이전시는 파일에 포함된 모든 앱에 대한 권한이 있어야 합니다.</li><li>광고주만 파일을 업로드할 수 있습니다. 에이전시는 데이터를 업로드할 수 없습니다. 파일을 준비하고 광고주에게 보내 업로드할 수 있습니다.</li><li>동일한 날짜에 대한 비용 데이터가 다시 전송되고 원본에 없는 후속 제출에 에이전시 이름(<code>af_prt</code>)이 포함된 경우 중복된 비용 데이터가 발생합니다.</li></ul></td><td>에이전시 이름</td><td>아니요</td></tr><tr><td colspan="4"><span><strong>참고:</strong> 영어가 아닌 문자가 포함된 이름은 UTF-8을 사용하여 인코딩해야 합니다.</span></td></tr></tbody></table>

#### CSV 형식 및 규칙

| 규칙 | 요구 사항 |
| --- | --- |
| 금지된 문자 | 문자열 형식의 필드에는 `=`, `+`, `-` 또는 `@` 을 첫 문자로 사용할 수 없습니다. 예를 들어 `@example_campign` 또는 `=123` 은 금지됩니다. |
| 앱 소유자 | 파일당 한 명의 광고주(앱 소유자)가 허용됩니다. 동일한 광고주 계정의 여러 앱이 허용됩니다. |
| 파일 이름 확장자 | CSV 예시: abc123.csv |
| 파일 구조 | <ul><li>**형식**: 파일은 각 열이 쉼표로 구분되는 CSV 형식입니다.</li><li>**헤더 행**: 첫 번째 행은 스키마와 일치하는 헤더 행입니다.</li><li>**데이터 행**: 필수 열을 포함합니다. **참고**: 데이터에 후행 공백이 없는지 확인하십시오. 예를 들어, [USD] (**D** 뒤의 공백은 [USD]로 변경해야 합니다.</li><li>**빈 행**: 허용되지 않음</li><li>동일한 키를 가진 **중복된 행**: 허용되지 않습니다. 키는 필수 필드를 사용하여 파생됩니다.</li><li>**빈 셀:** 파일에 빈 값은 허용되지 않습니다. 특정 필드를 업로드하지 않으려면 해당 필드를 파일에 포함하지 않아야 합니다.</li></ul> |
| 광고 계층 구조 | 비용은 캠페인 수준에서 기록되어야 하며 비용 기록에서 광고 계층 구조의 다른 기준은 선택 사항입니다.<br /><br />하위 계층 구조에 업로드된 모든 부분 데이터는 캠페인 수준 아래의 모든 데이터를 재정의합니다.<br /><br />**예:** 광고 설정 1에 대한 캠페인 비용이 포함된 파일을 가져오고 동일한 캠페인의 광고 설정 2에 대한 다른 파일을 별도로 가져오는 경우, 캠페인의 총 비용이 대체되어 광고 설정 2 데이터만 표시됩니다. 총 캠페인 비용의 경우 가져오는 파일에 광고 세트 1과 광고 세트 2가 포함되어야 합니다. |

</Accordion>

<div id="upload-file" />

<Accordion title="파일 업로드">

광고주와 광고 네트워크는 비용 가져오기 CSV 파일을 업로드할 수 있습니다.

**선행 조건**: 애드 네트워크는 [비용 가져오기 권한을 광고주에게 부여해야 합니다](/docs/import-cost-data#cost-import-permissions-for-ad-networks).

**AppsFlyer UI를 통해 CSV 파일을 업로드하려면**:

1. 앱스플라이어의 사이드 메뉴에서 **설정** > 비용 가져오기를 선택합니다.  
   **비용 가져오기 페이지가 표시됩니다.**
2. 클릭 **+ 비용 파일 가져오기**  
   비용 가져오기 창이 열립니다.
3. CSV 파일을 **비용 파일 가져오기** 창으로 드래그하세요.  
   파일 처리 중 메시지가 표시됩니다.
4. 업로드 중에 오류 메시지가 표시되는 경우: 오류를 수정하고 관련 단계를 반복합니다.
5. **비용 가져오기: 파일 요약** 창이 열립니다.
6. 다음 중 하나를 수행하세요.
   * 업로드를 중단하고 **가져오기 취소**를 클릭합니다.
   * 가져오기 프로세스를 완료하고 **파일 가져오기**를 클릭합니다.  
     "모든 설정 완료!"가 메시지가 표시됩니다.
   * 오류 메시지가 표시되면 [오류 메시지 지침을](#error-messages-and-solutions) 따르십시오.
7. **다른 파일 가져오기** 또는 **완료**를 클릭합니다.

</Accordion>

<div id="email-file" />

<Accordion title="이메일 파일">

광고주와 광고 네트워크는 비용 가져오기 CSV 파일을 이메일로 보낼 수 있습니다.

**선행 조건**:

* 광고주
  * 발신자 이메일은 등록된 앱스플라이어 사용자의 이메일이어야 합니다.
* **애드 네트워크**:
  * 발신자 이메일은 등록된 앱스플라이어 사용자의 이메일이어야 합니다.
  * [비용 광고주로부터 관련 허가를 받은 경우](/docs/import-cost-data#cost-import-permissions-for-ad-networks).

**CSV 파일을 이메일로 보내려면**:

1. 이메일 가져오기 [토큰을 받으세요](/docs/import-cost-data#token-for-email-import).
   1. 앱스플라이어의 사이드 메뉴에서 **설정** > **비용 가져오기**를 선택합니다.
   2. 페이지의 오른쪽 상단에서 **이메일 가져오기용 토큰을 클릭하세요.**
   3. 토큰을 복사하여 저장하세요.
2. 다음 필드로 이메일을 작성하세요:
   * **받는 사람**:`adspend-upload@appsflyer.com`
   * **CC: 자동 피드백을 받아야 하는 사용자**
   * **제목**: 주제 필드에 이메일 가져오기용 토큰을 붙여넣으세요.
   * **첨부**: CSV 파일에 데이터를 저장합니다.
3. 이메일을 보냅니다.
   * 파일이 수신되고 처리되면 상태 이메일이 처리 중 발견된 세부사항, 문제 또는 오류를 요약합니다. 이메일은 제출 이메일과 광고주 관리에 대한 모든 당사자에게 발송됩니다. 오류가 식별되는 경우 [오류 메시지 지침](#error-messages-and-solutions)을 따르십시오.
   * [비용 가져오기 페이지](/docs/import-cost-data#error-messages-and-solutions)에서 제출된 파일의 상태를 확인할 수 있습니다.

</Accordion>

## 대시보드

비용 가져오기 대시보드를 사용하면 파일을 업로드하고 이전에 업로드된 파일의 세부 정보를 볼 수 있습니다.

<div id="cost-import-dashboard" />

<Accordion title="비용 가져오기 대시보드">

비용 가져오기 대시보드를 보려면 AppsFlyer에서 사이드 메뉴에서 **설정** > **비용 가져오기**를 선택하세요.

이전에 가져온 파일에 대한 정보는 다음 표에 설명되어 있습니다.

| 열 이름 | 설명 |
| --- | --- |
| CSV 파일 이름 | AppsFlyer에 가져온 비용 파일의 이름입니다. |
| 업로드 날짜 | 파일이 가져온 날짜입니다. |
| 미디어 소스 | 파일에 포함된 미디어 소스입니다. |
| 날짜 범위 | 광고 지출이 발생한 파일의 첫 번째 및 마지막 날짜입니다. |
| 일치하는 행 | 비용이 귀속에 맞춰진 파일의 행 비율입니다. 더 알아보기 |
| 상태 | 가져온 파일의 상태입니다:<ul><li>성공! 조치가 성공적으로 완료되었습니다.  비용이 기록되었으며 AppsFlyer 대시보드 및 보고서에서 사용할 수 있습니다.</li><li>유효성 검사 오류 앱스플라이어 시스템 문제. 10분간 기다렸다가 다시 시도하십시오. 다시 실패하는 경우 앱스플라이어 지원팀에 문의하십시오.</li><li>권한 없음 토큰이 이 앱에 대해 승인되지 않았습니다.<ul><li>광고주 앱 ID가 올바른지 확인하세요.</li><li>애드 네트워크 광고주와 확인하여 비용 가져오기 권한을 받았는지 확인하세요.</li></ul></li><li>Reverted 조치가 성공적으로 완료되었습니다.  파일이 다른 데이터로 덮어쓰여졌습니다.</li></ul> |
| 조치 | <ul><li>파일 수준에서: 파일에 포함된 모든 앱에 대한 앱 권한이 있는 경우:<ul><li>**CSV 파일 다운로드**: 이것은 가져온 CSV 파일의 복사본입니다.</li><li>파일의 모든 앱에 대해 **일치하지 않는 리포트를 다운로드**합니다. 자세한 내용은 이 표의 일치하는 행 섹션을 참조하십시오.</li></ul></li><li>앱 수준에서: 특정 파일을 클릭하면 해당 특정 파일 및 다른 파일의 앱에 대한 모든 비용 가져오기 정보가 표시됩니다. 앱에 대한 앱 권한이 있는 경우 다음을 수행할 수 있습니다:<ul><li>**앱 데이터를 다운로드합니다.**</li><li>앱에 대해 **일치하지 않는 리포트를 다운로드**합니다.</li><li>선택한 앱의 비용 가져오기를 **되돌리기** (취소)합니다.</li></ul></li></ul> |

</Accordion>

<div id="matched-rows" />

<Accordion title="일치하는 행">

행 일치는 가져온 비용이 AppsFlyer에 기록된 귀속 데이터와 일치하는 과정입니다. 이는 미디어 소스, 캠페인, 광고 세트, 광고 등과 같은 모든 차원 이름(아이디 아님)을 사용하여 수행됩니다. 모두 일치하는 경우, 행은 is-matching=TRUE로 지정됩니다.

비용은 일치 상태와 관계없이 AppsFlyer 대시보드 및 보고서에 기록되고 사용할 수 있습니다.

일치하는 행의 비율이 비용 가져오기 대시보드에 표시됩니다. 일치하지 않는 행이 예상치 못한 경우 또는 일치하는 행의 수(%)가 예상보다 높은 경우:

* 원인을 조사하기 위해 일치하지 않는 보고서를 다운로드하십시오. 일치하지 않는 리포트에는 값이 TRUE(일치됨) 또는 FALSE(일치하지 않음) 행 값이 있을 수 있는 열 is-matched가 있습니다.
* 필요한 경우 가져오기를 되돌려 취소합니다.
* 자세한 내용은 이 표의 작업 섹션을 참조하십시오.

</Accordion>

## 추가 정보

<div id="using-excel-or-google-sheets-to-prepare-csv-file" />

<Accordion title="Excel 또는 Google Sheets를 사용하여 CSV 파일 준비하기">

Excel/Google 시트를 사용하여 CSV 파일을 만드는 경우 파일을 CSV 파일로 저장하기 전에 날짜 및 지출 열의 형식을 올바르게 지정해야 합니다. CSV 파일을 저장한 후 콘텐츠의 형식이 올바른지 확인합니다. 다음 지침을 사용하십시오:

* 날짜 셀 형식 지정하기.
* 지출 셀 형식 지정하기.
* 내용 형식 확인하기.

#### 날짜 셀 형식 지정하기.

**Excel에서 날짜 셀의 서식을 YYYY-MM-DD 형식으로 지정하려면**:

1. 서식을 지정할 셀을 선택합니다.
2. 마우스 오른쪽 버튼을 클릭한 다음 **셀 서식**을 선택합니다.  
   셀 형식 창이 열립니다.  
   <Image alt="Formatdate..png" src="https://files.readme.io/43d0f370f299d73b8ce93fec1c912cb7525d0071db779a64a58f5917df2a5531-360004042458.png" width="379px" />
3. **사용자 지정**을 선택합니다.
4. 유형 필드에 **YYYY-MM-DD**를 입력합니다
5. **확인**을 클릭하세요.  
   날짜가 포맷됩니다.

#### 지출 셀 서식 지정

그림에 표시된 대로 Excel은 일반적으로 값 셀을 쉼표로 형식화하여 수천 개로 구분합니다. 이 형식은 비용 가져오기 파일에 적합하지 않습니다.

<Image alt="mceclip1.png" src="https://files.readme.io/d54e21ddd937dfe25a33bb96193761a5a724c22a35a55bb7d71eb03a6433d7ed-360003949177.png" width="291px" />

**지출 셀에 1000 단위 구분 기호 없이 서식 지정하기** :

1. 서식을 지정할 셀을 선택합니다.
2. 마우스 오른쪽 버튼을 클릭한 다음 **셀 서식**을 선택합니다.  
   셀 형식 창이 열립니다.
3. **숫자**를 선택합니다.  
   <Image alt="Formatnumbers.png" src="https://files.readme.io/4c1b61d1eae9149e818d4cc9793128fbdaafed5daed9acf6cbc503571475cc0e-34255643022481.png" width="381px" />
4. **1000 단위 구분 기호(,) 사용**을 지웁니다.
5. (선택 사항) **소수점 이하 자릿수**를 설정합니다. 기본값은 2입니다. 허용되는 최대 개수는 5개입니다.
6. **확인**을 클릭하십시오.  
   셀이 올바르게 포맷되었습니다.

#### 내용 형식 확인

**내용 형식 확인하기** :

1. 편집기를 사용하여 파일을 봅니다.
   * Windows: 메모장, 메모장++
   * macOS: TextEdit
2. 다음 사항에 특히 주의하십시오.
   * **공백:** 필드를 구분하는 쉼표의 앞뒤에 공백이 없는지 확인합니다. Excel에서 @trim 명령을 사용하여 공백을 제거합니다.
   * **날짜:** 날짜 셀의 형식이 YYYY-MM-DD인지 확인합니다.
   * **지출:** 지출 셀에 쉼표가 없도록 합니다.
   * **구분 기호** : 쉼표여야 합니다. 세미콜론인 경우:
     * 이 문제는 컴퓨터의 지역 설정이 영어가 아닌 언어/지역(특히 독일어)로 설정되어 있을 때 발생할 수 있습니다.
     * 해결 방법은 컴퓨터 운영 체제(macOS 또는 Windows)에 따라 다릅니다.
     * 이 문제를 해결하려면 <Anchor target="_blank" href="https://support.office.com/en-us/article/import-or-export-text-txt-or-csv-files-5250ac4c-663c-47ce-937b-339e391393ba#ID0EAAFAAA=Office_2016-2010">Microsoft</Anchor> 또는 다른 포럼에서 시작할 최신 안내를 검색하여 해결하십시오. 다음 검색어를 사용하세요. 운영 체제 (macOS 또는 Windows) Excel에서 CSV 파일의 구분 기호를 변경합니다.

다음은 편집기에 표시되는 [예제 CSV 파일](https://docs.google.com/spreadsheets/d/e/2PACX-1vQ0oJTWdlNyT1gBHkGaN1QP-tUatugbPBzC2qYVNmjl_T_i3fKo1abYzTp6F7OqGeN_f7bBAJa3hxVz/pub?gid=0&single=true&output=csv)의 스크린샷입니다.

<Image alt="mceclip1.png" src="https://files.readme.io/1398c5e9bad7a46b697e3b21030e64d656162e33a4a63f39475c64993bbe7a72-360003996197.png" width="672px" />

</Accordion>

<div id="token-for-email-import" />

<Accordion title="이메일 가져오기 토큰">

이메일 가져오기 토큰은 이메일 발신자가 비용 가져오기 파일을 제출할 수 있는 권한이 있는지 확인하는 데 사용됩니다.

광고주와 애드 네트워크 토큰은 다릅니다.

* 광고주 토큰:
  * 동일한 토큰이 계정의 모든 앱에 유효합니다.
  * 모든 계정 사용자가 토큰을 받을 수 있습니다.
* 광고 네트워크 토큰:
  * 모든 광고주에게 동일한 토큰이 사용됩니다.

광고주와 광고 네트워크는 서로 토큰을 공유해서는 안 됩니다!

</Accordion>

<div id="cost-import-permissions-for-ad-networks" />

<Accordion title="광고 네트워크에 대한 비용 가져오기 권한">

광고 네트워크는 비용 가져오기에 접근하기 위해 앱별로 광고주 권한이 필요합니다.

**광고 네트워크 비용 가져오기 권한을 부여합니다:**

1. 앱스플라이어에서 <strong>광고주</strong>는 사이드 메뉴로 이동하여 <strong>연동</strong>> 활성 통합을 선택합니다.  
   통합 파트너 페이지가 표시됩니다.
2. 연동 파트너를 선택하세요.
3. **권한** 탭으로 이동합니다.
4. 아직 이렇게 하지 않은 경우 **광고 네트워크 권한**을 사용 가능으로 설정하십시오.
5. (선택사항) 계정 사용자를 추가하십시오.
6. **비용 가져오기 사용.**
7. 권한 저장을 클릭합니다.

</Accordion>

## 문제 해결, 특성 및 제한 사항

<div id="error-messages-and-solutions" />

<Accordion title="오류 메시지 및 솔루션">

다음 표에는 가능한 모든 비용 가져오기 오류 메시지와 해당 해결 방법이 나와 있습니다.

| 오류 메시지 | 설명 | 솔루션 |
| --- | --- | --- |
| 파일에 제공된 앱 ID는 앱스플라이어에 존재하지 않습니다. 앱 ID의 정확성을 확인하십시오. | 앱 ID가 계정에 존재하지 않습니다. | 앱 ID를 변경하고 다시 제출하십시오. |
| 행[행 이름]의 열 수가 잘못되었습니다. 예상하는 [숫자] 열, 수신한 [숫자] 열. | 파일의 모든 열에는 값이 있어야 합니다. | 정의한 헤더에 기반하여 파일에 기록된 값을 변경하십시오. |
| 파일 헤더의 'media-source' 누락. | <ul><li>파일 헤더에 미디어소스가 누락되었습니다.</li><li>열 이름은 스키마에 있는 것과 정확히 일치해야 합니다.</li></ul> | 미디어소스를 헤더 이름으로 추가합니다. |
| 파일은 하나의 미디어소스만 포함할 수 있습니다. 파일에서 여러 개의 미디어 소스가 발견됨: [매체 소스 수]. | 파일에는 하나 이상의 미디어 소스가 포함되어 있습니다. CSV의 숨겨진 빈 줄이나 잘못된 행도 이 오류를 유발할 수 있으며, Excel에서 보이지 않더라도 마찬가지입니다. | 파일을 Notepad++와 같은 텍스트 편집기에서 열고 빈 줄이나 잘못된 행을 제거하십시오. 파일을 저장하고 다시 업로드하십시오. 파일에 하나 이상의 미디어 소스가 포함되어 있다면, 각 미디어 소스마다 하나의 파일로 분할하십시오. |
| [field]의 [value]에 제공된 값이 이 열에 대해 유효한 값이 아닙니다. | 열의 데이터 형식이 올바르지 않습니다. 예를 들어, 날짜는 yyyy-mm-dd가 아니라 dd-mm-yy입니다. | 형식을 수정하고 다시 제출하십시오. |
| 앱에서 여러 통화가 식별되었습니다. 파일의 각 앱에 대해 단일 통화를 사용하십시오. 발생한 통화: %number of currencies%. | 앱에 하나의 통화만 사용할 수 있습니다. | 업로드에서 하나의 통화를 사용하여 다시 제출하십시오. |
| 파일 헤더의 다음 열[파일 헤더]이 지원되지 않습니다. | 파일 헤더가 스키마와 일치하지 않습니다. 즉, 열 이름은 스키마에 있는 것과 정확히 일치해야 합니다. | 지원되지 않는 열을 제거하고 다시 제출하십시오. |
| 파일 헤더에서 필수 열이 누락됨: [파일 헤더] | 파일 헤더에 필수 열이 누락되었습니다. | 누락된 열과 해당 값을 추가하고 다시 제출하십시오. |
| 앱에 미래 날짜 [date]가 포함되어 있습니다. | 미래 날짜는 허용되지 않습니다. | 오늘 날짜나 이전 날짜를 정정한 후 다시 제출하십시오. |
| 파일이 비어 있습니다. 처리할 데이터가 없습니다. | 파일이 비어 있습니다. | 파일에 데이터를 채우고 다시 제출하십시오. |
| 동일한 기준으로 인해 다음 두 행이 충돌합니다. 차원 세트당 한 행의 지출을 입력하세요. [충돌하는 행] | 동일한 키(필수) 필드가 있는 행이 둘 이상 있습니다. | 중복 행을 제거하고 다시 제출하십시오. |
| 이 파일은 단일 광고주 계정의 데이터만 포함할 수 있습니다. 파일에서 다른 광고주 [advertiser names]이(가) 조우했습니다. | 파트너의 경우, 업로드는 둘 이상의 광고주에서 진행할 수 없습니다. | 광고주당 하나의 파일로 업로드를 분할하십시오. |
| 계정에 앱[app ID]이 존재하지 않습니다. 앱 ID를 확인하십시오. | 앱 ID가 존재하지 않습니다. | 앱 ID를 수정한 다음 다시 제출하십시오. |
| 앱 [앱 ID]에서 지역(국가) 코드를 찾을 수 없습니다. ISO 3166 2-문자 코드를 사용하십시오. | 지역이 존재하지 않습니다. | 지역을 수정하고 다시 제출하십시오. |
| 앱 [앱 ID]에서 통화 코드를 찾을 수 없습니다. ISO 4217 3문자 코드를 사용하십시오. | 통화가 존재하지 않습니다. | 통화를 유효한 통화로 변경하고 다시 제출하십시오. |
| 파일에 있는 하나 이상의 앱에 대한 유효성 검증 오류가 있습니다. 자세한 내용은 파일 정보를 검토하십시오. | 파일에 오류가 두 개 이상 있습니다. | 파일을 다운로드하고 오류를 검토하십시오. |
| 파일을 처리하는 중에 내부 오류가 발생했습니다. 다시 업로드하십시오. | <ul><li>파일을 처리하는 백엔드 문제가 발생했습니다.</li><li>일반적으로 임시 문제입니다.</li></ul> | 1시간 동안 기다렸다가 다시 업로드하십시오. |

</Accordion>

<div id="traits-and-limitations" />

<Accordion title="특징 및 제한 사항">

| 특징 | 비고 |
| --- | --- |
| 애드 네트워크 | 지원됨.<br /><br />예외:<ul><li>Meta ads</li><li>X Ads</li><li>ASA</li></ul> |
| 에이전시 | <ul><li>에이전시는 데이터를 업로드할 수 없습니다. 파일을 준비하고 광고주에게 보내 업로드할 수 있습니다.</li><li>이렇게 하려면 CSV 파일에 에이전시 이름이 있는 에이전시 열이 포함되어야 합니다 (에이전시 이름은 af\_prt 파라미터의 값임). CSV 스키마 참조</li></ul> |
| 에이전시 투명성 | 지원되지 않음 |
| 앱별 시간대 | 지원됨 |
| 앱별 통화 | 지원됨. 캠페인 비용이 앱 특정 통화로 변환됩니다. |
| Campaign name | 동일한 캠페인 이름을 여러 앱에 사용할 수 없거나 하나의 앱의 비용이 둘 다에 적용됩니다. |
| 필드 이름 | 캠페인 계층의 필드 이름이 기여 데이터에 표시되는 필드 이름과 일치하지 않으면 별도로 계산됩니다. <br /><br />예를 들어 캠페인 이름이 일치하지 않으면 캠페인 ID가 동일하더라도 다른 캠페인으로 계산됩니다. |
| 파일 크기 | CSV 비용 가져오기 파일 업로드 시 크기 제한:<ul><li>앱스플라이어 대시보드: 2 MB</li><li>이메일: 파일당 5MB</li></ul> |
| 오가닉 데이터 | 지원됨. |
| 논오가닉 데이터 | 지원됨. |
| 데이터 최신성 | <Anchor target="_blank" href="/marketers/ko/docs/about-data-freshness-and-timezone-support#intraday-during-the-day">광고 비용</Anchor> |
| 과거 데이터 | 지원됨. 입력한 비용 데이터는 제출 후 최대 90일까지 취소 혹은 수정할 수 있습니다. |
| 리타겟팅 | 지원되지 않습니다. |
| 계정 유저 액세스 | 지역 또는 미디어소스 제한이 있는 사용자는 사용할 수 없습니다. |

</Accordion>

<div data-zendesk-anchors="ad-spend-import=%EA%B0%9C%EC%9A%94 01H7VYHJ2BN3EFDC4J3YN3P4WM=%EA%B0%9C%EC%9A%94 procedures=%EC%A0%88%EC%B0%A8 h_01HYZBZMNTM0244V4PN6AJ45KR=%EC%A0%88%EC%B0%A8 h_01HYZD52VRTMGJ0BFBFJNGQ50E=prepare-csv-file-with-cost-data ad-spend-csv-schema=csv-%EC%8A%A4%ED%82%A4%EB%A7%88 01H7VYHJ2CWF2HWHCTZDEZHT29=csv-%EC%8A%A4%ED%82%A4%EB%A7%88 csv-format-and-rules=csv-%ED%98%95%EC%8B%9D-%EB%B0%8F-%EA%B7%9C%EC%B9%99 h_01HYZEDYKCAPTK1WD6VGWTA6PQ=csv-%ED%98%95%EC%8B%9D-%EB%B0%8F-%EA%B7%9C%EC%B9%99 h_01HYZD52VRWK7D6Q0YBW9SEFK6=upload-file h_01HYZKN3YEPFG8525GFQD0PC5K=email-file dashboard=%EB%8C%80%EC%8B%9C%EB%B3%B4%EB%93%9C h_01HZ4NVKPVHV1KT12V59MZBGPZ=%EB%8C%80%EC%8B%9C%EB%B3%B4%EB%93%9C h_01HZ1SXQQ2CHG77KX96D74J6TQ=cost-import-dashboard h_01HZ4NVKPVSM5ZTG76HJF3GW4J=matched-rows additional-information=%EC%B6%94%EA%B0%80-%EC%A0%95%EB%B3%B4 h_01HYZFNKFEQW13F0BWAG3FZF69=%EC%B6%94%EA%B0%80-%EC%A0%95%EB%B3%B4 h_01HYZFNKFE3AVH1GNGDT511M5B=using-excel-or-google-sheets-to-prepare-csv-file formatting-date-cells-in-excel=%EB%82%A0%EC%A7%9C-%EC%85%80-%ED%98%95%EC%8B%9D-%EC%A7%80%EC%A0%95%ED%95%98%EA%B8%B0 01H7VYHJ2DSWC2J1NY04Q9Q620=%EB%82%A0%EC%A7%9C-%EC%85%80-%ED%98%95%EC%8B%9D-%EC%A7%80%EC%A0%95%ED%95%98%EA%B8%B0 formatting-spend-cells-in-excel=%EC%A7%80%EC%B6%9C-%EC%85%80-%EC%84%9C%EC%8B%9D-%EC%A7%80%EC%A0%95 01H7VYHJ2DA9JM4Q33V2TF7BD3=%EC%A7%80%EC%B6%9C-%EC%85%80-%EC%84%9C%EC%8B%9D-%EC%A7%80%EC%A0%95 verify-content-format=%EB%82%B4%EC%9A%A9-%ED%98%95%EC%8B%9D-%ED%99%95%EC%9D%B8 h_01HYZJJVC463C141AQ3VY5Z0TQ=%EB%82%B4%EC%9A%A9-%ED%98%95%EC%8B%9D-%ED%99%95%EC%9D%B8 h_01HYZFNKFEXK4CYRBZ3ABRCWNJ=token-for-email-import h_01HZ1XV6ZX5FAN9JJPQM9RYD3Z=cost-import-permissions-for-ad-networks troubleshooting-traits-and-limitations=%EB%AC%B8%EC%A0%9C-%ED%95%B4%EA%B2%B0-%ED%8A%B9%EC%84%B1-%EB%B0%8F-%EC%A0%9C%ED%95%9C-%EC%82%AC%ED%95%AD h_01HZ4PBGAG9R9JMHPXVQC1GX3V=%EB%AC%B8%EC%A0%9C-%ED%95%B4%EA%B2%B0-%ED%8A%B9%EC%84%B1-%EB%B0%8F-%EC%A0%9C%ED%95%9C-%EC%82%AC%ED%95%AD h_01HZ2859J5P6MFKACKBK46J6GP=error-messages-and-solutions h_01HZ27W0409NF4Y6RNT8WPW8HP=traits-and-limitations" />
