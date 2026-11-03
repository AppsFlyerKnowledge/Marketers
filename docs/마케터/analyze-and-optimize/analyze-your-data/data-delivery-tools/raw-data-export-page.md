---
title: 로데이터 내보내기 페이지
metadata:
  keywords:
    - ad networks
    - Advertisers
    - Agencies
    - Marketers
    - Raw Reports
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-rona-einat
    - Marketers
    - Agencies
    - Raw Reports
    - Ad Networks
  created_at: '2020-05-11T22:25:33Z'
  edited_at: '2026-10-14T10:29:55Z'
  id: 360008613838
  locale: ko
  section: Data delivery tools
  section_id: 6550995484561
  url: https://support.appsflyer.com/hc/ko/articles/360008613838
---
> **한눈에 보기:** 로데이터 리포트를 CSV 파일로 다운로드하세요. 다운로드당 최대 1M 행. 필터를 사용하여 필요한 데이터만 리포트에 포함하세요.

다음 시각적 요소는 **로데이터 내보내기** 페이지로 처음 이동했을 때 표시됩니다; **내 리포트** 페이지는 다운로드 또는 복제가 가능한 리포트가 있는 경우에 표시됩니다.

[altRawDataSplash.pngalt](https://support.appsflyer.com/hc/article_attachments/30446824138513)

**내 리포트**

**내 리포트** 페이지에는 이전에 발생한 리포트가 나열되며, 다운로드, 복제 또는 둘 다 가능합니다. 나열된 리포트는 지난 90일 동안 발생한 것이며, 다운로드 기간은 7일입니다. 7일 후에도 리포트가 필요하면, 다시 생성해야 합니다.

로데이터 리포트에 대한 설명은 <Anchor target="_blank" href="/marketers/ko/docs/raw-data-reporting-overview">로데이터 리포팅 개요</Anchor>를 참조하세요.

리포트를 생성하거나 다운로드하려면 이 문서의 절차 섹션을 참조하세요.

[altMyReportsRawDataExport.pngalt](https://support.appsflyer.com/hc/article_attachments/30446824144529)

<div id="raw-data-export-page-features-and-filter-options" />

<Accordion title="로데이터 내보내기 페이지 기능 및 필터 옵션">

로데이터 내보내기 페이지는 다음 표에 나열된 기능을 갖춘 리포트를 제공합니다.

<Table>
  <thead>
    <tr>
      <th>
        기능
      </th>
      <th>
        비고
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td><span id="report-categories"></span>
        리포트 카테고리
      </td>
      <td>
        귀사의 구독 플랜에 따라 상이합니다.
      </td>
    </tr>
    <tr>
      <td><span id="date-range"></span>
        날짜 범위
      </td>
      <td>
        로데이터 리포트는 액티비티 날짜(이벤트 발생일)로 필터링됩니다. 인스톨 날짜에 대한 필터도 추가할 수 있습니다. 다음 표에서 필터 옵션 목록을 확인하세요.
      </td>
    </tr>
    <tr>
      <td><span id="maximum-number-of-rows"></span>
        최대 행 수
      </td>
      <td>
        1M 행
      </td>
    </tr>
    <tr>
      <td><span id="rate-limitation"></span>
        콜 수 제한
      </td>
      <td>
        <Anchor target="_blank" href="/marketers/ko/docs/report-generation-quotas-rate-limitations">할당량 메커니즘</Anchor>은 하루에 발생 가능한 리포트 수를 제한합니다.
      </td>
    </tr>
    <tr>
      <td><span id="retentionreport-window"></span>
        리텐션/리포트 기간
      </td>
      <td>
        지난 90일 중 인스톨 관련 리포트(인스톨, 인스톨 포스트백)는 **60**일 동안 단일 다운로드로 처리됩니다.

        인앱 이벤트 관련 리포트: 지난 90일 중 31일은 단일 다운로드로 처리됩니다.
      </td>
    </tr>
    <tr>
      <td><span id="filter-options"></span>
        필터 옵션
      </td>
      <td>
        나열된 필터는 사용할 수 있습니다. 경우에 따라 필터에 따라 필터 옵션이 채워집니다. 예를 들어, 지역별로 필터링하면 사용 가능한 국가 목록이 표시됩니다.
      </td>
    </tr>
    <tr>
      <td><span id="field-selection"></span>
        필드 선택
      </td>
      <td>
        가장 중요한 필드는 미리 선택되어 있습니다. **리포트 필드** 탭에서 선택한 필드를 추가/삭제할 수 있습니다. 일부 필드는 특정 리포트와 관련이 없을 수 있습니다. 그러나 필드를 선택할 수 있습니다. 리포트 형식(열)의 일관성을 유지하기 위해 이렇게 합니다.

        예를 들어, 유저 유입 인앱 이벤트 리포트에서 프로드(Protect360) 관련 필드를 선택하면 빈 열이 나타납니다. 이런 필드는 Protect360 리포트 내에서만 사용됩니다.
      </td>
    </tr>
    <tr>
      <td><span id="report-csv-field-order"></span>
        리포트(CSV) 필드 순서
      </td>
      <td>
        리포트의 열은 필드 순서 설정에 따라 배열됩니다. 스프레드시트에 [나열된 열 순서](https://docs.google.com/spreadsheets/d/e/2PACX-1vRGYcMOgC5yy_82yn3DWd3ucLE5KtuTA72eJfvu5KVB9fFH_mYwzM3KpR_inQOnat-KzgVjuuvXa6_g/pub?output=xlsx) 에는 기존과 기본 옵션에 대한 별도 탭이 포함되어 있습니다.

        | 설정 | 필드 선택 허용 | 비고 |
        | --- | --- | --- |
        | <span id="default"></span>기본 | 예 | * 선택된 필드는 앱스플라이어 템플릿에 맞게 배열됩니다.<br />* 추후에도 배열 순서는 유지됩니다. 새 필드는 기존 필드의 오른쪽에 추가됩니다. |
        | <span id="alphabetical-az"></span>알파벳순(A-Z) | 예 | 선택된 필드는 알파벳 순서(오름차순)로 배열됩니다. |
        | <span id="alphabetical-za"></span>알파벳순(Z-A) | 예 | 선택된 필드는 알파벳 역순(내림차순)으로 배열됩니다. |
        | <span id="legacy"></span>기존 | 아니오 | * 필드는 이전 버전의 내보내기 데이터 페이지에서 준비된 리포트의 열 순서에 따라 배열됩니다.<br />* 필드는 고정되어 변경할 수 없습니다.<br />* 실제 리포트에 따라 필드별 보고서에 약간의 차이가 있습니다. |
      </td>
    </tr>
  </tbody>
</Table>

> 📘 **참고**
>
> 에이전시 필터와 미디어 소스 필터를 둘 다 사용하면, 미디어 소스 필터는 비투명 에이전시에는 적용되지 않습니다. 비투명 에이전시의 경우, 필터링된 미디어 소스의 데이터뿐만 아니라 모든 데이터가 포함됩니다.

| 필터 | 광고주 | 애드 네트워크 | 에이전시 |
| --- | --- | --- | --- |
| 미디어 소스 | 예 | 아니오 | 예 |
| 액티비티 날짜 범위 | 예 | 예 | 예 |
| 인스톨 날짜 범위 | 예 | 예 | 예 |
| 에이전시 | 예 | 아니오 | 아니오 |
| 지역(영토\/국가) | 예 | 예 | 예 |
| 인앱 이벤트(인앱 이벤트 리포트에서 사용 가능) | 예 | 아니오 | 예 |

</Accordion>

## 절차

<div id="create-a-default-report" />

<Accordion title="기본 리포트 생성">

필드나 필터를 사용자 지정하지 않고도 기본 설정으로 리포트를 생성할 수 있습니다.

**기본 리포트를 생성하려면:**

1. 앱스플라이어에서 측면 메뉴를 통해 **내보내기** > **로데이터 내보내기**를 선택하세요.
2. + **New 리포트**를 클릭하세요.
3. 생성하려는 리포트 유형에 마우스를 올리고 **생성**을 클릭합니다.
4. 드롭다운 메뉴에서 **지금 생성**을 선택하세요.
5. 팝업 기간에서 **지금 생성을 클릭합니다.** 생성에는 최대 10분이 소요될 수 있습니다.
   * 리포트 생성 중에도 작업을 계속하거나, 추가 리포트를 만들거나, 다른 페이지로 이동할 수 있습니다.

**기본 리포트 필터 설정:**

| 필터 | 기본 설정 |
| --- | --- |
| 액티비티 날짜 | 지난 7일 |
| 파일당 최대 행 수 | 200,000 |
| 미디어 소스 | 모든 미디어 소스 |
| 에이전시 | 모든 에이전시 |
| 지역 | 모든 지리적 영역 |

</Accordion>

<div id="create-a-custom-report" />

<Accordion title="커스텀 리포트 만들기">

필터와 필드를 설정하여 커스텀 리포트를 만들 수 있습니다.

**커스텀 리포트를 만들려면:**

1. 앱스플라이어에서 측면 메뉴를 통해 **내보내기** > **로데이터 내보내기**를 선택하세요.
2. + **New 리포트**를 클릭하세요.
3. 생성하려는 리포트 유형에 마우스를 올리고 **생성**을 클릭합니다.
4. 드롭다운 메뉴에서 **사용자 지정**을 선택하세요.
5. 리포트 필터 설정
   * **액티비티 날짜:** 액티비티 날짜 범위를 선택하세요. 특정 날짜를 설정하거나 커스텀, 어제, 지난 7일 등의 옵션을 선택할 수 있습니다.
   * **파일당 최대 행 수:** [선택 사항] 파일에 포함될 수 있는 최대 행 수를 설정합니다. 100, 200K, 500K 또는 1M 행 중에서 선택하세요.
   * **미디어 소스:** [선택 사항] 선택한 미디어 소스에 속한 이벤트만 리포트에 포함됩니다. **항목 추가**를 클릭하면 목록에 미디어 소스를 추가할 수 있습니다.
   * **에이전시:** [선택 사항] 선택한 에이전시에 속한 이벤트만 리포트에 포함됩니다. **항목 추가**를 클릭하면 목록에 에이전시를 추가할 수 있습니다.
   * **지역:** [선택 사항] 선택한 지리적 영역에 속한 이벤트만 리포트에 포함됩니다.
   * **리포트 유형별 필터**: 각 리포트 유형에는 필터링 기준을 선택할 수 있는 고유한 필터가 있습니다.
6. [선택 사항]: 리포트는 필요한 필드로 자동으로 채워집니다. 다음과 같이 필드를 추가하거나 제거할 수 있습니다.
   1. **리포트 필드** 탭으로 이동합니다. 선택한 필드 목록이 표시됩니다. 필수 필드의 선택은 변경할 수 없습니다.
   2. 필요에 따라 특정 필드를 선택하거나 선택 취소합니다.
   3. [선택 사항] **리포트(CSV) 필드 순서**를 설정하여 열 순서를 설정합니다.
   4. [옵션] 필요한 경우 **기본값 복원**을 클릭합니다.
7. **만들기**를 클릭합니다.
   * **내 리포트** 페이지가 표시됩니다. 처음에는 상태가 리포트를 생성 중임을 나타냅니다.
   * 생성에는 최대 10분이 걸릴 수 있습니다.
   * 리포트 생성 중에도 작업을 계속하거나, 추가 리포트를 만들거나, 다른 페이지로 이동할 수 있습니다.

</Accordion>

<div id="download-report" />

<Accordion title="리포트 다운로드">

**리포트를 다운로드하려면**:

1. 앱스플라이어에서 사이드바를 열고 **내보내기** > **로데이터 내보내기**를 선택하세요.
2. ![DownloadIcon.png](https://files.readme.io/6c00f4922fc3a835a856d7fdf527aa32d2f50570710c1527b039f43a7acbba79-41225791763217.png) (다운로드)를 클릭하여 리포트를 다운로드하세요. 생성된 리포트는 7일 동안 다운로드할 수 있습니다.

</Accordion>

<div id="duplicate-and-edit-report-settings" />

<Accordion title="리포트 설정 복제 및 편집">

**리포트 설정을 복제 및 편집하려면:**

1. 앱스플라이어에서 사이드바를 열고 **내보내기** > **로데이터 내보내기**를 선택하세요.
2. ![Duplicate.png](https://files.readme.io/f745081f1bf0c4f5861e275a29048fe84e8020f8b3bf4ebe4ad6a8d9254ab4b5-41225784681233.png)를 클릭하여 리포트 설정을 복제한 후 설정을 편집하세요.
3. **생성**을 클릭하세요. 발생한 리포트는 7일 동안 이용 가능합니다.   
   * **내 리포트** 페이지가 표시됩니다. 처음에는 상태가 리포트를 생성 중임을 나타냅니다.
   * 생성에는 최대 10분이 걸릴 수 있습니다.
   * 리포트 생성 중에도 작업을 계속하거나, 추가 리포트를 만들거나, 다른 페이지로 이동할 수 있습니다.

</Accordion>

## 추가 정보

<div id="traits-and-limitations" />

<Accordion title="특성 및 한계">

| 특징 | 비고 |
| --- | --- |
| 애드 네트워크 액세스 | 예 |
| 에이전시 액세스 | 예 |
| 에이전시 투명성 | 예. 그러나 에이전시 필터와 미디어 소스 필터를 함께 사용할 경우, 투명하지 않은 에이전시에 대해 미디어 소스 필터가 적용되지 않습니다. 즉, 투명하지 않은 에이전시의 경우 필터링된 미디어 소스의 데이터뿐 아니라 모든 데이터가 포함됩니다. |
| 앱별 시간대 | 예 |
| 앱별 통화 | 예 |
| 제한 사항 | 다운로드당 최대 100만 레코드 |
| 오가닉 데이터 | 사용 가능 |
| 논오가닉 데이터 | 사용 가능 |
| 데이터 최신성 | 리포트에 따라 다릅니다 |
| 기록 데이터 | 지난 90일 |
| 계정 유저 액세스 | <Anchor target="_blank" href="/marketers/ko/docs/user-management">필요한 권한을 가진 역할</Anchor>에 있는 사용자 |
| 이메일 전송 | 지원되지 않음 |
| 인스톨 날짜 범위 | 인스톨 날짜 범위는 액티비티 날짜 범위보다 이전이어야 합니다. |
| 로데이터 포스트백 리포트 | 투명하지 않은 에이전시에 귀속된 이벤트로 인해 파트너에게 전송된 포스트백은 광고주의 로데이터 포스트백 리포트에 포함되지 않습니다. |

</Accordion>

<div id="field-sequence-templates" />

<Accordion title="필드 순서 템플릿">

리포트 필드 순서 설정을 통해 리포트 내 열의 순서를 지정할 수 있으며, 경우에 따라 필드 자체도 지정할 수 있습니다.

| 설정 | 필드 선택 허용 | 비고 |
| --- | --- | --- |
| <span id="default::b7bb6355"></span>기본 | 예 | <ul><li>선택된 필드는 앱스플라이어 템플릿에 맞게 배열됩니다.</li><li>추후에도 배열 순서는 유지됩니다. 새 필드는 기존 필드의 오른쪽에 추가됩니다.</li></ul> |
| <span id="alphabetical-az::b08af6b3"></span>알파벳순(A-Z) | 예 | 선택된 필드는 알파벳 순으로 정렬되어 있습니다. |
| <span id="alphabetical-za::f0b3beb8"></span>알파벳순(Z-A) | 예 | 선택된 필드는 알파벳 역순으로 정렬됩니다. |
| <span id="legacy::fb5fd8ec"></span>기존 | 아니오 | <ul><li>필드는 이전 버전의 내보내기 데이터 페이지에서 준비된 리포트의 열 순서에 따라 배열됩니다.</li><li>필드는 고정되어 변경할 수 없습니다.</li><li>실제 리포트에 따라 필드별 차이가 있을 수 있습니다.</li></ul> |

이 [스프레드시트](https://docs.google.com/spreadsheets/d/e/2PACX-1vRGYcMOgC5yy_82yn3DWd3ucLE5KtuTA72eJfvu5KVB9fFH_mYwzM3KpR_inQOnat-KzgVjuuvXa6_g/pub?output=xlsx)에는 기본 시트와 기존 시트가 포함되어 있습니다. 각 시트에는 관련 필드 순서 목록이 포함되어 있습니다.

**필드 순서를 변경하려면:**

1. 리포트 필드 탭에서 **리포트 필드 순서** 옵션을 선택하세요.
2. 필요한 필드를 선택하거나 선택 해제를 통해 선택된 필드를 변경하세요.

</Accordion>

<div data-zendesk-anchors="h_01HA28AT6QRSG68NBFYHH5SQY8=raw-data-export-page-features-and-filter-options h_01HA28CJ4W692V6EVC7XTQEZG6=%EC%B0%B8%EA%B3%A0 procedures=%EC%A0%88%EC%B0%A8 h_01HA28AT6Q9PV3M55C1YM3XN2E=%EC%A0%88%EC%B0%A8 h_01HZY1HQ9AVH6Q9QAQB4SM1VPX=create-a-default-report h_01HZY1HQ9ACEMZ4N8WPYNHZQP7=create-a-custom-report h_01HA28AT6QV1XP4N952PAEGSSG=download-report h_01HA28AT6QFT88RHJ3M05MV3B3=duplicate-and-edit-report-settings additional-information=%EC%B6%94%EA%B0%80-%EC%A0%95%EB%B3%B4 h_01HA28AT6Q4DXKCZ22R9XEN2RR=%EC%B6%94%EA%B0%80-%EC%A0%95%EB%B3%B4 h_01HA28AT6Q6SE8CB3EEXFMAN0H=traits-and-limitations h_01HA28AT6RW8C99ZGEBTN5E44R=field-sequence-templates" />
