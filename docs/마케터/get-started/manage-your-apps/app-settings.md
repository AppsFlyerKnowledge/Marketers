---
title: 앱 설정
metadata:
  keywords:
    - App Settings
    - Advertisers
    - Agencies
    - Developers
    - Marketers
    - Platform essentials
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - Marketers
    - Platform essentials
    - Agencies
    - pm-guy-riesenberg
  created_at: '2016-08-16T07:50:37Z'
  edited_at: '2026-10-14T10:35:48Z'
  id: 211719806
  locale: ko
  section: Manage your apps
  section_id: 6551015977105
  url: https://support.appsflyer.com/hc/ko/articles/211719806
---
> **한눈에 보기:** 모든 매체 소스에서 귀사의 앱 어트리뷰션 및 분석에 영향을 미치는 설정에 대해 알아보세요.

## 앱 설정

**액세스:**

* 관리자(또는 적절한 권한이 있는 사용자)는 앱 설정을 **변경**할 수 있습니다.
* 특정 앱에 액세스할 수 있는 모든 계정 사용자는 해당 앱 설정을 **볼 수** 있습니다.

**앱 설정을 변경하거나 보려면:**

1. 앱스플라이어의 사이드 메뉴에서 **설정** > **앱 설정**을 선택합니다.
2. 앱 설정 페이지에서 설정을 확인하고 필요에 따라 변경하세요.
3. **설정 저장**을 클릭하세요.

### 일반 앱 설정

<Table>
  <thead>
    <tr>
      <th>
        설정
      </th>
      <th>
        설명
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td><span id="sdk-authentication-dev-key"></span>
        SDK 인증: 개발 키
      </td>
      <td>
        * 개발 키는 앱이나 S2S가 앱스플라이어로 전송하는 이벤트를 인증합니다.
        * 키는 계정별로 고유하며 해당 계정의 모든 앱에서 사용됩니다.
        * 키는 해당 앱에 액세스할 수 있는 모든 계정 사용자에게 앱 설정 페이지에서 제공됩니다.
        * [선택 사항] 특정 시나리오에서 개별 앱 키를 할당할 수 있습니다. 이와 관련하여 논의하려면 귀사의 CSM에 문의하세요.
      </td>
    </tr>
    <tr>
      <td><span id="aggregated-advanced-privacy-ios-apps"></span>
        데이터 집약형 고급 개인 정보 보호(iOS 앱)
      </td>
      <td>
        이 기능이 켜져 있으면 광고주가 사용자 수준 어트리뷰션 데이터를 사용할 수 없습니다. 파트너에게 공유되는 포스트백 및 이벤트 데이터는 데이터 집약형이며 익명으로 처리됩니다(자세한 내용은 <Anchor target="_blank" href="/marketers/ko/docs/apply-aggregated-advanced-privacy-framework">데이터 집약형 고급 개인 정보 보호</Anchor> 프레임워크 참조).

        이 기능을 끄면 사용자 수준 어트리뷰션 데이터가 모든 파트너에게 데이터 집약형 형태로 제공되며, 각 파트너별로 개별 설정할 수 있습니다.
      </td>
    </tr>
    <tr>
      <td><span id="analytics-define-loyal-user-trigger"></span>
        분석: 충성 고객 트리거 정의
      </td>
      <td>
        * 유저를 충성 고객으로 지정하는 트리거입니다. 앱을 추가할 때 설정된 기본 옵션은 3번의 앱 오픈입니다.
        * 인앱 이벤트 어트리뷰션이 완료된 후 인앱 이벤트를 트리거 이벤트로 사용할 수 있습니다.
          * [기본값] 3번의 앱 오픈.
          * 충성 고객 설정은 유저의 질적인 평가를 나타냅니다. 프로드 방지에는 <Anchor target="_blank" href="/marketers/ko/docs/protect360-anti-fraud-guide#faq">Protect360</Anchor>을 사용하는 것을 고려하세요.
          * 이 설정을 변경하면 데이터가 소급 적용되어 과거의 충성 고객 데이터가 다시 계산됩니다.
      </td>
    </tr>
    <tr>
      <td><span id="app-store-country"></span>
        앱 스토어 국가
      </td>
      <td>
        앱이 제공되는 앱 스토어의 국가를 설정합니다. 이 설정은 여기에서 설명된 대로 앱에 영향을 미칩니다.

        * **앱 상태를 대기 중에서 라이브로 변경**:
          * <Anchor target="_blank" href="/marketers/ko/docs/why-is-my-app-still-pending">앱이 라이브 상태가 되면</Anchor>, 앱스플라이어는 국가 설정을 사용하여 스토어를 확인하고 앱의 아이콘 등 세부 정보를 가져옵니다.
          * 설정된 스토어 국가에서 앱이 발견되지 않으면 앱스플라이어는 앱 상태를 대기 중에서 라이브로 변경할 수 없습니다.
        * 리디렉션 동작은 시나리오에 따라 설정의 영향을 받으며, 이는 다음 표에 자세히 설명되어 있습니다.

        | 유저 유형 | 리디렉션 시나리오 |
        | --- | --- |
        | <span id="mobile"></span>모바일 | 사용자는 다른 모바일 앱에서 어트리뷰션 링크를 주로 클릭합니다. 클릭 시, 운영 체제는 사용자가 리디렉션될 애플 앱 스토어의 국가를 결정합니다.  <br /><br />* **안드로이드**는 사용자의 IP 또는 위치에 따라 리디렉션합니다.<br />* **iOS**는 디바이스에서 활성화된 iTunes 계정과 연관된 애플 앱 스토어로 리디렉션합니다. |
        | <span id="mobile-and-web"></span>모바일 및 웹 | 웹 사용자가 **웹사이트**(모바일 및 데스크톱)에서 어트리뷰션 링크를 클릭하면 인앱 설정된 국가로 초기 리디렉션됩니다.<br /><br />설치를 시도할 때, 운영 체제는 모바일의 이전 행에서 설명한 대로 국가 스토어로 리디렉션합니다. |
        | <span id="ipad-ios-13"></span>iPad iOS 13 | iOS 13 이상에서는 <Anchor target="_blank" href="https://www.apple.com/ipados/features/">iPad가 웹사이트의 데스크톱 버전을 제공합니다</Anchor>. 즉, 사용자 유형(모바일 또는 웹)은 무관합니다. 어트리뷰션 링크 클릭 시 데스크톱 사이트로 이동하며, 이후 리디렉션 규칙은 웹 사용자와 동일합니다. |
      </td>
    </tr>
    <tr>
      <td><span id="localization-time-zone"></span>
        로컬라이제이션: 시간대
      </td>
      <td>
        기본 앱 설정은 UTC입니다. <Anchor target="_blank" href="/marketers/ko/docs/changing-app-time-zone-settings">앱 시간대에 대한 정보입니다.</Anchor>
      </td>
    </tr>
    <tr>
      <td><span id="localization-currency"></span>
        로컬라이제이션: 통화
      </td>
      <td>
        * 이것은 다음 지표에 사용되는 앱 전용 통화를 정의합니다:
          * 비용
          * 인앱 이벤트/수익
          * 광고 수익
        * 기본 앱 설정은 USD입니다.
          * 수익이나 비용이 없는 앱은 통화 변경이 가능합니다.
          * New 앱의 경우, 앱이 추가될 때 통화가 설정됩니다.

        #### 앱 통화의 영향을 받는 리포팅 도구

        | 리포팅 도구 | 사용 가능한 통화 옵션 |
        | --- | --- |
        | <span id="dashboards"></span>대시보드 | 앱별 통화 |
        | <span id="export-data-page"></span>데이터 내보내기 페이지 | 앱별 통화 |
        | <span id="push-api"></span>Push API | 앱별 통화와 USD를 동시에 사용 가능 |
        | <span id="pull-api"></span>Pull API | 집계 데이터: 앱별 통화<br /><br />로데이터: USD 또는 앱별 통화 선택 가능 |
        | <span id="master-api"></span>마스터 API | USD 또는 앱별 통화 선택 가능 |
        | <span id="data-locker"></span>데이터 락커 | USD만 가능 |
      </td>
    </tr>
  </tbody>
</Table>

### 어트리뷰션 설정

| 설정 | 설명 |
| --- | --- |
| <span id="reattribution-window"></span>리어트리뷰션 윈도우 | The <Anchor target="_blank" href="/marketers/ko/docs/set-up-re-attribution-window">리어트리뷰션 윈도우</Anchor>은 첫 인스톨 날짜부터 시작하는 기간으로, 이 동안 재인스톨은 새 인스톨로 측정되지 않습니다.<ul><li>[기본값] 3개월</li><li>값 범위: 1-24개월</li></ul> |
| <span id="viewthrough-attribution-via-probabilistic-modeling"></span>확률적 모델링을 통한 뷰-쓰루 어트리뷰션 | <ul><li>비활성화된 경우, 뷰-쓰루 확률 모델링을 활성화합니다.</li><li>뷰-쓰루 확률적 모델링을 활성화한 후 애드 네트워크 연동 탭에서 뷰-쓰루 어트리뷰션도 활성화해야 합니다.</li></ul> |
| <span id="reengagement-attribution"></span>리인게이지먼트 어트리뷰션 | 관련 문서: <Anchor target="_blank" href="/marketers/ko/docs/retargeting-attribution-guide">리타겟팅 가이드</Anchor><br /><br />**리인게이지먼트 어트리뷰션을 활성화하려면:**<ul><li>앱스플라이어의 사이드 메뉴에서 **설정** > **앱 설정**을 선택하고 **리인게이지먼트 어트리뷰션**을 켭니다.</li></ul>앱 설정 외에도 <Anchor target="_blank" href="/marketers/ko/docs/retargeting-attribution-guide#retargeting-settings">파트너별 설정을 완료</Anchor>해야 합니다.<br /><br /><Anchor target="_blank" href="/marketers/ko/docs/retargeting-attribution-guide#제외-기간">**리인게이지먼트 전환 간 최소 시간**</Anchor> 설정은 기존 리인게이지먼트 윈도우가 설정된 기간 전에 종료되는 것을 방지합니다. |
| <span id="organic-search-seo-mobile-app-attribution"></span>오가닉 검색(SEO) 모바일 앱 어트리뷰션 | 관련 문서: <Anchor target="_blank" href="/marketers/ko/docs/set-up-organic-search-seo-and-organic-ai-answers-aeo-re-engagement-attribution">오가닉 검색 어트리뷰션</Anchor><br /><br />**오가닉 검색 어트리뷰션을 활성화하려면:**<ul><li>앱스플라이어의 사이드 메뉴에서 **설정** > **앱 설정**을 선택하고 **오가닉 검색(SEO) 모바일 앱 어트리뷰션**을 켭니다.</li></ul> |
| <span id="uninstall-measurement"></span>앱 삭제 측정 | <Anchor target="_blank" href="/marketers/ko/docs/measure-uninstalls">앱 삭제 측정</Anchor>은 앱 삭제 측정이 활성화되어 있을 때 발생하는 인스톨과 관련됩니다.<br /><br />**앱 삭제 측정을 활성화하려면:**<ol><li>각 운영 체제별로 다음 작업을 완료하세요.<ul><li>**iOS**: 앱이 iOS 앱 삭제 어트리뷰션 기능을 구현하면 여기에 P12 인증서를 업로드해야 합니다.</li><li>**안드로이드**: 안드로이드 앱 삭제 어트리뷰션을 위해 Firebase/GCM 서버 키를 여기에 정의해야 합니다.</li></ul></li><li>앱 **삭제 측정**를 켭니다.</li><li>**설정 저장**을 클릭합니다.</li></ol>**앱 삭제 측정을 중지하려면:**<ol><li>**앱 삭제 측정**을 끕니다.</li><li>**설정 저장**을 클릭하세요.</li></ol> |

### 고급 설정

| 설정 | 설명 |
| --- | --- |
| <span id="mask-ip-address-in-raw-data-reports"></span>IP 주소 마스킹 | 이 기능이 켜지면 최종 사용자 디바이스 <Anchor target="_blank" href="/marketers/ko/docs/apply-ip-masking-to-user-data">IP 주소가 마스킹되어</Anchor> 현재 선택된 앱에서 파트너에게 전송되는 로데이터 보고서와 포스트백에서 표시됩니다. |
| <span id="reinstall-detection-using-ondevice-storage-ios-only"></span>기기 내 저장소를 사용한 재설치 감지 (iOS 전용) | 광고 ID에 의존하지 않고 재설치를 감지합니다. 이 작업은 디바이스의 안전한 로컬 저장소(iOS의 경우 키체인)에 마지막 앱 인스톨 날짜를 저장하여 수행됩니다. 앱의 인스톨이 재설치인지 신규 인스톨인지 여부를 판별하면, 재설치 중복을 제거하여 어트리뷰션 분석을 더 정확하게 수행할 수 있습니다. |
| <span id="ios-103-redirect-fallback"></span>iOS 10.3 리디렉션 대체 | [더 이상 사용되지 않음] iOS 10.3 이상용. iOS 사용자에 대해 흐름을 단순화했으며 이 매개변수는 더 이상 사용되지 않습니다. <Anchor target="_blank" href="/marketers/ko/docs/uri-scheme-fallback-for-ios">iOS 리디렉션</Anchor>.<br /><br />이 옵션은 iOS 앱에서만 이용 가능합니다. |
| <span id="change-app-name"></span>앱 이름 변경 | <ul><li>대시보드와 데이터 보고서 전체에 표시되는 앱 이름입니다. 예를 들어, 지역에 따라 동일한 앱의 여러 버전이 있는 경우, 이 기능이 유용할 수 있습니다.</li><li>이 변경은 앱 표시 방식에 영향을 줍니다. 앱 ID는 다양한 앱스플라이어 API를 사용할 때 앱을 식별하는 데 사용되며, **변경되지 않습니다**.</li><li>이름은 최대 50자까지 가능합니다.</li></ul> |
| <span id="outofstore-app-url"></span>앱 스토어 외 다른 곳에서 다운로드된 앱 URL | <ul><li>앱과 연결된 어트리뷰션 링크에서 기본 리디렉션 목적지로 사용될 앱 다운로드 URL을 설정하세요.</li><li>이 필드는 스토어 외부 앱으로 지정된 안드로이드 앱에서는 필수입니다.</li><li>설정 후 약 1시간 내에 URL이 기본 리디렉션 대상으로 적용됩니다.</li></ul> |

> 📄 **참고 항목**
>
> * <Anchor target="_blank" href="/marketers/ko/docs/retargeting-attribution-guide">리타겟팅 어트리뷰션 가이드</Anchor>
> * <Anchor target="_blank" href="/marketers/ko/docs/set-up-organic-search-seo-and-organic-ai-answers-aeo-re-engagement-attribution">오가닉 검색 어트리뷰션</Anchor>

<div data-zendesk-anchors="app-settings=%EC%95%B1-%EC%84%A4%EC%A0%95 01ECHQME56X51MDW9TMA6DBNCK=%EC%95%B1-%EC%84%A4%EC%A0%95 general-app-settings=%EC%9D%BC%EB%B0%98-%EC%95%B1-%EC%84%A4%EC%A0%95 h_01HAVS8CVPQKSDKCEM3YHHJ99Y=%EC%9D%BC%EB%B0%98-%EC%95%B1-%EC%84%A4%EC%A0%95 reporting-tools-impacted-by-app-currency=%EC%95%B1-%ED%86%B5%ED%99%94%EC%9D%98-%EC%98%81%ED%96%A5%EC%9D%84-%EB%B0%9B%EB%8A%94-%EB%A6%AC%ED%8F%AC%ED%8C%85-%EB%8F%84%EA%B5%AC h_01HAVS8CVQESWAQXKDW5SNVHCJ=%EC%95%B1-%ED%86%B5%ED%99%94%EC%9D%98-%EC%98%81%ED%96%A5%EC%9D%84-%EB%B0%9B%EB%8A%94-%EB%A6%AC%ED%8F%AC%ED%8C%85-%EB%8F%84%EA%B5%AC attribution-settings=%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%EC%84%A4%EC%A0%95 h_01HAVS8CVQN1YYTT7S49VGB3J0=%EC%96%B4%ED%8A%B8%EB%A6%AC%EB%B7%B0%EC%85%98-%EC%84%A4%EC%A0%95 advanced-settings=%EA%B3%A0%EA%B8%89-%EC%84%A4%EC%A0%95 h_01HAVS8CVQTKXVXSMT5KNYZ3T4=%EA%B3%A0%EA%B8%89-%EC%84%A4%EC%A0%95 h_01HDPCC9465DR4A3CCXYQC2M56=%EC%B0%B8%EA%B3%A0-%ED%95%AD%EB%AA%A9" />
