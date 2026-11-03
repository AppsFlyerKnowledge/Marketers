---
title: '업데이트 알림: 인게이지먼트 유형'
metadata:
  keywords:
    - Marketers
    - Mobile Attribution
table_of_contents: false
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-moran-davida
    - Marketers
    - Mobile Attribution
  created_at: '2023-11-15T10:50:04Z'
  edited_at: '2026-10-14T10:29:33Z'
  id: 20161875390865
  locale: ko
  section: Bulletins
  section_id: 6551161473041
  url: https://support.appsflyer.com/hc/ko/articles/20161875390865
---

<Table>
  <tbody>
    <tr>
      <td>
        **새로운 소식**
      </td>
      <td>
        로데이터 리포트에 몇 가지 새로운 필드가 추가되었습니다.

        * engagement\_type
        * contributor1\_engagement\_type
        * contributor2\_engagement\_type
        * contributor3\_engagement\_type

        파라미터는 preload, click\_to\_download, click\_to\_app, engaged\_click, engaged\_view, view, listening과 같은 값을 반환할 수 있으며 파라미터가 보고되지 않은 경우에는 빈 값을 반환합니다.비어 있습니다

        | **engagement\_type** | 설명 |
        | --- | --- |
        | preload | 디바이스 제조시 공장에서 혹은 업체에 의해 디바이스가 처음 활성화될 때 이미 앱이 탑재된 경우를 말합니다. 디바이스가 처음 활성화될 때, 설치 마법사가 유저에게 앱 다운로드를 요청합니다. |
        | click\_to\_download | 유저가 광고 혹은 푸시 메시지에 반응하면 앱 스토어로 리디렉션되지 않고 자동으로 앱이 다운로드되어 디바이스에 설치되는 경우를 일컫습니다. |
        | click\_to\_app | 광고 클릭, QR코드 스캔, 딥링크 클릭 혹은 기타 클릭으로 유저가 앱 또는 관련 앱 스토어로 리디렉션되어 앱을 다운받을 때를 말합니다. |
        | engaged\_click | 유저를 광고에 참여시키면서 의도한 여정 내에 머무르게 하는 클릭을 말하며 앱 스토어나 앱 실행으로 연결되지는 않습니다. |
        | engaged\_view | 참여수 조회는 의미 있는 조회가 발생하는 경우입니다. 유저가 건너뛸 수 있는 동영상 광고를 10초 이상 시청하거나 동영상을 끝까지 시청할 경우를 예로 들 수 있습니다. |
        | view | 광고 조회는 광고가 렌더링되고 노출이 발생하는 경우입니다. 배너, 삽입 광고 또는 참여하지 않는 동영상을 예로 들 수 있습니다. |
        | listening | 유저가 팟캐스트 광고와 같은 오디오 광고를 청취하는 경우를 뜻합니다. |
      </td>
    </tr>
    <tr>
      <td>
        **시행일**
      </td>
      <td>
        2024년 1월 17일
      </td>
    </tr>
    <tr>
      <td>
        이것이 주는 영향
      </td>
      <td>
        * 로데이터 보고서에 액세스할 수 있는 광고주 및 대행사는 이러한 필드를 보고하는 광고 네트워크와 협력합니다.
          * 딥링크에 대한 사전 로드 및 click\_to\_app은 광고 네트워크가 필드를 보고하는지 여부와 관계없이 앱스플라이어에 의해 채워집니다.
        * * 이러한 필드는 기본적으로 선택되지 않으며(푸시 API에서 모두 선택 제외) 이러한 필드를 사용하려면 원시 데이터 제품에서 수동으로 선택해야 합니다.
      </td>
    </tr>
  </tbody>
</Table>
