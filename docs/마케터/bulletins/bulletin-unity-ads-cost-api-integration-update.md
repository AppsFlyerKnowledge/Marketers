---
title: '업데이트 알림: Unity 애즈 비용 API 연동 업데이트'
metadata:
  keywords:
    - Marketers
    - ROI360
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-maytav-avnat
    - Marketers
    - ROI360
  created_at: '2024-06-20T14:43:15Z'
  edited_at: '2026-10-14T10:26:46Z'
  id: 26078530790289
  locale: ko
  section: Bulletins
  section_id: 6551161473041
  url: https://support.appsflyer.com/hc/ko/articles/26078530790289
---
| **새로운 소식** | 앱스플라이어는 비용 데이터를 얻을 수 있는 Unity와의 API 연동을 제공합니다. 해당 API가 곧 업데이트될 예정이므로, Unity 비용 데이터를 계속 전송 받으시려면 연동을 업데이트해야 합니다. |
| --- | --- |
| **업데이트 날짜** | 2024년 8월 6일 |
| **중요 사항** | <ul><li>Unity는 새로운 비용 API 연동을 도입할 예정입니다.</li><li>기존 비용 API 연동으로는 종료일인 2024년 10월 1일까지만 비용 데이터를 가져올 수 있습니다.</li></ul> |
| **해야 할 일** | 2024년 10월 1일 이후에도 비용 데이터를 계속 전송받기 위해서는 새로운 Unity 비용 API 연동에 대한 자격 증명을 업데이트해야 합니다.<br /><br />필요한 자격 증명은 다음과 같습니다.<ul><li>Organization Core ID</li><li>Service Account Secret Key</li><li>Service Account Key ID (서비스 계정 키 ID)</li></ul>앱스플라이어의 Unity 비용 연동을 업데이트하려면 다음 섹션의 지침을 따르세요. Unity 비용 연동을 업데이트하려면 다음 2가지 단계를 수행해야 합니다.<ol><li>[새로운 Unity 자격 증명을 받습니다](/docs/bulletin-unity-ads-cost-api-integration-update#get-unity-credentials).</li><li>[앱스플라이어에 자격 증명을 입력하여 Unity 비용 API 연동을 업데이트합니다.](/docs/bulletin-unity-ads-cost-api-integration-update#set-up-unity-cost-api-integration-in-appsflyer)</li></ol> |

<div id="unity-cost-api-integration-procedures" />

## Unity 비용 API 연동 절차

Unity 비용 API를 연동하려면 다음 2가지 단계를 거쳐야 합니다.

1. 새로운 Unity 자격 증명을 받습니다.
2. 앱스플라이어에 자격 증명을 입력하여 Unity 비용 API 연동을 업데이트합니다.

각 단계별 자세한 지침은 아래를 참고하시기 바랍니다.

<div id="get-unity-credentials" />

<Accordion title="Unity 자격 증명 받기">

Unity 비용 API 연동에 필요한 자격 증명은 다음과 같습니다.

* Organization Core ID
* Service Account Secret Key
* Service Account Key ID

**참고**: 비밀 키와 키 ID를 받으려면 새로운 Unity 서비스 계정을 만드는 것을 권장드립니다. 자격 증명을 얻는 자세한 방법은 아래를 참고하시기 바랍니다.

**Unity 서비스 계정을 설정하고 Unity 비용 API 연동에 필요한 자격 증명을 얻으려면 다음 단계를 수행하세요**.

1. Unity Cloud 계정에 로그인합니다.
2. 왼쪽 메뉴에서 **Unity Ads User Acquisition** > **Settings**로 이동합니다.  
    <Image align="center" alt="" src="https://files.readme.io/2fcc359913c11a4bcce29e1aaf30cb84161a09e39b14cdcd4ad4f141debd1798-26134832885137.png" />
3. **Organization Core ID**를 찾아서 복사하고 저장합니다.  
   Organization Core ID 예시: 5773102414648
4. 왼쪽 메뉴에서 **Unity Ads User Acquisition** > **`{}` API Management**로 이동하고 **Stats API v2.0** 섹션에서 **Service Account를 클릭**합니다.  
    <Image align="center" alt="" src="https://files.readme.io/36dd40e68eeeb6562c1e5a19f92873e8eb99b66f80c45db066e0ff54b66d0080-26369979011985.png" />
5. **+ New**를 클릭하여 새 서비스 계정을 만듭니다.  
    <Image align="center" alt="" src="https://files.readme.io/3a53e932bf8d023e910b66f74ea6f630c8048787885d45ea4206b2f1f3d4f65e-26136910848785.png" />
6. **Keys** 섹션에서 **+ Add key** 를 클릭하여 서비스 계정의 키를 만듭니다.  
    <Image align="center" alt="" src="https://files.readme.io/f528d44a9659372bfeeb8d13538f9caf0a7955f53194194543988af983f9c517-26136957380753.png" />
7. **Key ID**와 **Secret key**를 복사하여 저장합니다. **참고**: 이 단계에서만 비밀 키에 액세스할 수 있으니, 꼭 저장해 두세요!
   * 서비스 계정 Secret key 예: b0de73b1-b3ad-4175-bf9b-4913a0ff83ec
   * 서비스 계정 Key ID 예시: a0X\_cqHiXH4ABPS1Qr9TCy6EJdvG8ql5  
      <Image align="center" alt="" src="https://files.readme.io/6de3cd868541ab5487370dbefc758a375c3395434e07361f74553a1b9a9c7d57-26136957383697.png" />
8. **Organization roles** 섹션에서 **+ Manage organization roles**를 클릭합니다.  
    <Image align="center" alt="" src="https://files.readme.io/d368d6c611db2a8df76e341c7b6a692128b5ae37f51f6642fa7e60cd00f29689-26136910860689.png" />
9. **Edit roles in organization**에서 **Growth**를 **Advertise Stats API MMP Viewer**로 설정합니다.  
    <Image align="center" alt="" src="https://files.readme.io/f1243cb65978d2f96d148ceb34b528ca005091c38dbed95368923047b3cfbfd1-26136957386513.png" />

</Accordion>

<div id="set-up-unity-cost-api-integration-in-appsflyer" />

<Accordion title="앱스플라이어 내에서 Unity 비용 API 연동 업데이트">

**앱스플라이어에서 Unity 비용 API를 업데이트하려면 다음 단계를 진행하세요**:

1. 앱스플라이어의 사이드 메뉴에서 **협엽** > **활성화된 연동**을 선택하고 **Unity**를 선택합니다.
2. **연동 관리**를 클릭합니다.
3. 통합된 파트너의 **비용** 탭을 엽니다.
4. **비용 데이터 가져오기** 토글을 활성화합니다. 파트너에 연결하기 위한 요구 사항이 표시됩니다.
5. Unity 자격 증명을 입력합니다.
6. **비용 저장**을 클릭합니다.
7. **연결 테스트**를 클릭합니다.  
   * API가 활성 상태입니다. 앱스플라이어는 하루 6번, 평균 4시간마다 한 번씩 파트너로부터 데이터를 수집합니다.

<Anchor target="_blank" href="/marketers/ko/docs/set-up-roi360-cost-api-to-measure-cost-data">비용 연동을 연결하는 방법에 대해 자세히 알아보기</Anchor>

</Accordion>

<div data-zendesk-anchors="unity-cost-api-integration-procedures=unity-%EB%B9%84%EC%9A%A9-api-%EC%97%B0%EB%8F%99-%EC%A0%88%EC%B0%A8 h_01J11ZP5XG6VDSQKRWASAYK4QJ=unity-%EB%B9%84%EC%9A%A9-api-%EC%97%B0%EB%8F%99-%EC%A0%88%EC%B0%A8 h_01J14M3C6WNXPJJQHVWVNFB4GS=get-unity-credentials h_01J11ZHPJDZDZ7S24ZQK58B2FN=set-up-unity-cost-api-integration-in-appsflyer" />
