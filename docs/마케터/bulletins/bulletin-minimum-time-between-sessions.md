---
title: '업데이트 알림: 세션 간 최소 시간'
metadata:
  keywords:
    - Advertisers
    - Ad Networks
    - Marketers
    - Mobile Attribution
table_of_contents: false
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-guy-sarfatty
    - Marketers
    - Mobile Attribution
    - Ad Networks
  created_at: '2021-01-03T11:28:55Z'
  edited_at: '2026-10-14T10:30:48Z'
  id: 360016827858
  locale: ko
  section: Bulletins
  section_id: 6551161473041
  url: https://support.appsflyer.com/hc/ko/articles/360016827858
---

<Table>
  <tbody>
    <tr>
      <td>
        **새로운 소식**
      </td>
      <td>

      </td>
    </tr>
    <tr>
      <td>
        **시행일**
      </td>
      <td>
        2025년 2월 1일
      </td>
    </tr>
    <tr>
      <td>
        **변경되는 사항**

        **![Information_icon.png](https://files.readme.io/cc1ff74668360a2be64ec90db8f771d751b0a95847ecaee582c2e31c60e310cf-20445036062993.png)**
      </td>
      <td>
        * 1-60분
        * 0-24시간

        ![MinimumTimeBetweenSessions_us-en.jpg](https://files.readme.io/12bc7191a11dda474f57055a6cf5ce6bb69b3772ad33a2a0c7bfabc51e4c07ce-360015918477.jpg)

        **예:**

        | 예시 |  | 계수된 세션 수 | 무시된 세션 수 |
        | --- | --- | --- | --- |
        | A | 0, 10, 20, 30 | 4 | 없음 |
        | B | 0, 1, 9, 11 | 2 | 1, 9 |
        | C | 0, 10, 15, 21 | 3 | 15 |
      </td>
    </tr>
    <tr>
      <td>
        동일한 상태를 유지하는 사항
      </td>
      <td>
        * 지표:
          * 일일 활성 사용자(DAU)
          * 월간 활성 사용자 (MAU)
          * 잔존율
          * 기본 설정인 3-앱 열기를 사용하는 로열 유저
        * 리인게이지먼트 전환 데이터

        사용자가 일반적으로 하루에 한 번 앱을 실행하는 앱의 경우 특히 그렇습니다.
      </td>
    </tr>
    <tr>
      <td>
        **![Action_icon.png](https://files.readme.io/f6066b9dee413eea63c6a0bf04b627e3cef6a6fb21a6ca23634e615d3be1950d-360015730138.png)**
      </td>
      <td>
        1. 앱스플라이어에서. **설정** > **앱 설정**으로 갑니다.
        2. **세션 간 최소 시간**을 설정합니다.
        3. **설정 저장**을 클릭하세요.   
           변경 사항은 1시간 이내에 적용됩니다.
      </td>
    </tr>
  </tbody>
</Table>
