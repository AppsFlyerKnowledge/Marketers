---
title: '게시판: 광고 수익 리포트의 New 필드'
metadata:
  keywords:
    - Marketers
    - ROI360
table_of_contents: false
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-michael-talapov
    - Marketers
    - ROI360
  created_at: '2024-07-22T13:25:32Z'
  edited_at: '2026-10-14T10:35:23Z'
  id: 26907692192273
  locale: ko
  section: Bulletins
  section_id: 6551161473041
  url: https://support.appsflyer.com/hc/ko/articles/26907692192273
---

<Table>
  <tbody>
    <tr>
      <td>
        **새로운 기능**
      </td>
      <td>
        광고 수익 리포트에 New 필드가 추가되었습니다.
      </td>
    </tr>
    <tr>
      <td>
        **시행일**
      </td>
      <td>
        2024년 9월 19일
      </td>
    </tr>
    <tr>
      <td>
        **알아두어야 할 사항**
      </td>
      <td>
        다음 표는 각 리포트에 추가될 필드들을 보여줍니다. 각 필드의 정의와 자세한 내용은 <Anchor target="_blank" href="/marketers/ko/docs/raw-data-field-dictionary">로데이터 필드 사전</Anchor>을 참조하세요.

        | 리포트 | API 필드 이름 |
        | --- | --- |
        | <Anchor target="_blank" href="/marketers/ko/docs/revenue-etl-reports#ad-revenue-single-version-report-device-level">기존 광고 수익[단일 버전]</Anchor> | * 참여 유형<br />* 사용자 정의 데이터<br />* 고객 사용자 ID<br />* 광고 유형(ad\_revenue\_ad\_type) |
        | <Anchor target="_blank" href="/marketers/ko/docs/revenue-etl-reports#ad-revenue-single-version-report-device-level">광고 수익 [버전]</Anchor> | * 참여 유형<br />* 사용자 정의 데이터<br />* 고객 사용자 ID<br />* 광고 유형(ad\_revenue\_ad\_type) |
        | <Anchor target="_blank" href="/marketers/ko/docs/revenue-etl-reports#impression-level-report">광고 수익[SDK 노출 수준]</Anchor> | * 참여 유형<br />* 사용자 정의 데이터<br />* 고객 사용자 ID<br />* 광고 유형(ad\_revenue\_ad\_type)<br />* 광고 수익 사용자 정의 매개변수<br />* 앱 버전<br />* SDK 버전 |
      </td>
    </tr>
    <tr>
      <td>
        **해야 할 일**
      </td>
      <td>
        * <Anchor target="_blank" href="/marketers/ko/docs/data-locker-for-marketers#set-up-data-locker">앱스플라이어 데이터 락커 설정</Anchor>에서 리포트에 추가할 New 필드를 선택하세요.  
          **팁**!
        * New 필드를 수집하고 사용할 수 있도록 BI 시스템을 구성하세요.
      </td>
    </tr>
  </tbody>
</Table>
