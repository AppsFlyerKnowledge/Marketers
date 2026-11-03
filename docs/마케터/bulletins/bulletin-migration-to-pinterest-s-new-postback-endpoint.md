---
title: '업데이트 알림: Pinterest의 새로운 포스트백 엔드포인트로의 마이그레이션'
metadata:
  keywords:
    - Marketers
    - Mobile Attribution
table_of_contents: false
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2025-07-23T07:26:53Z'
  edited_at: '2026-10-14T10:28:41Z'
  id: 37418019002641
  locale: ko
  section: Bulletins
  section_id: 6551161473041
  url: https://support.appsflyer.com/hc/ko/articles/37418019002641
---

<Table>
  <thead>
    <tr>
      <th>
        섹션
      </th>
      <th>
        세부 정보
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        **이번 업데이트로 달라진 점:**
      </td>
      <td>
        Pinterest는 Conversions API (CAPI) 인프라를 기반으로 한 새로운 엔드포인트로 마이그레이션했습니다. Pinterest에 앱 이벤트를 계속 전송하려면 업그레이드해야 합니다. 2025년 9월 30일에 이전 엔드포인트를 사용 중단할 예정입니다.
      </td>
    </tr>
    <tr>
      <td>
        **발효일**
      </td>
      <td>
        $475.22
      </td>
    </tr>
    <tr>
      <td>
        **핵심 내용**
      </td>
      <td>
        > 📘 **참고**
        >
        > 이 공지는 CAPI로의 마이그레이션 단계와 관련된 정보를 포함합니다. Pinterest 통합에 대한 일반 정보는 <Anchor target="_blank" href="/marketers/ko/docs/pinterest-create-a-mobile-app-integration#인앱-이벤트-설정">KB 기사</Anchor>를 참조하세요.

        새 API 인앱 이벤트 설정으로 업데이트하면 Pinterest 측정이 중단 없이 계속되며, 다음도 포함됩니다:

        * **더 많은 “이벤트” 유형**: 목표에 더 잘 맞추기 위해 추가 이벤트를 추적하세요, 예를 들어: 리드, 검색, 카테고리 조회, 페이지 방문 등.
          * **참고:** 새로운 Pinterest V5 엔드포인트의 이벤트 이름은 다릅니다. 대시보드가 적절히 업데이트되지 않으면 이벤트 보고서에 “알 수 없음”이 표시됩니다. 아래의 새로운 이벤트 이름을 검토하세요.
        * **개선된 데이터 품질:** 향상된 매칭 및 더 강력한 귀속 정확성의 혜택을 누리세요.

        새 통합에는 **광고 계정 ID**와 **액세스 토큰**가 모두 필요합니다. 포스트백 기능을 유지하려면 파트너는 2025년 9월 30일까지 새로운 포스트백 엔드포인트로 전환해야 합니다.   

        **Pinterest AppsFlyer 광고 계정 ID 찾는 방법**  
        현재 AppsFlyer Pinterest 전환 보고 광고 계정 ID는 Pinterest **비즈니스 관리자** 또는 Pinterest **전환** 보고에서 찾을 수 있습니다.

        1. Pinterest 비즈니스 계정에 로그인하세요 (허브 옵션을 보려면 비즈니스 프로필에 있어야 합니다).
        2. 브라우저에 [https://www.pinterest.com/business/hub/](https://www.pinterest.com/business/hub/)를 입력하거나 붙여넣고 Enter 키를 누르세요.
        3. 허브의 왼쪽에 있는 어두운 회색 탐색 열을 확인하세요. 열이 축소되어 있으면, 왼쪽 상단 모서리에 있는 작은 “≡” (햄버거) 아이콘을 클릭하여 확장하세요.
        4. 조금 스크롤하여 “비즈니스 관리”라는 제목의 섹션을 찾으세요.
        5. Conversions를 클릭하세요(“비즈니스 관리” 바로 아래에 있습니다). 이것은 Conversions 대시보드를 열어, Pinterest로 전송된 AppsFlyer 전환을 검토할 수 있습니다.
        6. 광고 계정 ID는 URL에 표시됩니다.
        7. 여러 Pinterest 광고 계정 ID가 AppsFlyer에서 복제된 전환을 받는 경우, Pinterest 비즈니스 관리자에서 모든 기존 광고 계정 ID를 확인하세요. AppsFlyer 전환을 위한 원래 부모 광고 계정 ID가 선택되었는지 확인하세요.

        **Pinterest AppsFlyer 액세스 토큰 찾는 방법**  
        Pinterest의 도움말 센터 <Anchor target="_blank" href="https://help.pinterest.com/en/business/article/getting-started-with-the-conversions-api">여기</Anchor>에 설명된 단계를 따르세요. Pinterest Conversions에 들어가면, **Conversions API** > **API 설정**을 클릭하고 계정을 위한 새로운 액세스 토큰을 생성하세요.  

        Important Note AppsFlyer 외부에서 Pinterest에 대해 이미 Conversions API를 설정한 경우, AppsFlyer 전환을 위해 여기서 동일한 액세스 토큰을 사용하세요.
      </td>
    </tr>
    <tr>
      <td>
        **필요한 조치**
      </td>
      <td>
        AppsFlyer 대시보드에서 인앱 이벤트 포스트백을 설정하고 마이그레이션하는 방법에 대한 지침을 따르세요.

        1. **인앱 이벤트 설정 및 대시보드 매개변수 처리**  
           현재 Pinterest와 Appsflyer 이벤트를 매핑하기 위해 다음 대시보드 매개변수를 지원합니다:

           * **광고 계정 ID** (표시됨)
           * **액세스 토큰** (표시됨)
           * **태그 ID** (대시보드에 표시되지 않지만, 새로운 V5 버전으로의 전환을 지원하기 위해 백엔드에서 지원됨. V5 엔드포인트로의 전환이 완전히 지원되면, 태그 ID도 백엔드에서 제거됩니다.)

           다음 사항을 참고하십시오.  
           새로운 포스트백 설정을 위해서는 **광고 계정 ID**와 **액세스 토큰**을 모두 입력해야 합니다(이들은 Pinterest에서 얻을 수 있습니다). **이 값 중 하나라도 누락되면 포스트백이 실패합니다**. Pinterest **활성 통합** 페이지에 두 매개변수가 올바르게 입력되었는지 확인해 주십시오. 자세한 내용은 <Anchor target="_blank" href="/marketers/ko/docs/pinterest-create-a-mobile-app-integration#인앱-이벤트-설정">KB 문서</Anchor>를 참조하십시오.  
           원활한 전환을 위해 귀하의 협조가 중요합니다. 지원해 주셔서 감사합니다.
        2. **앱 내 이벤트 매핑 및 포스트백 설정**
           1. 현재 Pinterest 이벤트 이름을 **파트너 이벤트 이름** 섹션의 새로운 Pinterest 전환 API 이벤트 이름으로 교체하고 매핑해 주십시오. 예를 들어, 현재 파트너 이벤트 섹션에서 `pin_add_to_cart`를 사용하고 있다면, 대신 `add_to_cart`으로 교체하십시오. 자세한 내용은 <Anchor target="_blank" href="/marketers/ko/docs/pinterest-create-a-mobile-app-integration#inapp-event-postbacks">KB 문서</Anchor>를 참조하십시오.

        | 이벤트 이름 (구형) | 이벤트 이름 (새 전환 API) |
        | --- | --- |
        | pin\_add\_to\_cart | add\_to\_cart |
        | pin\_purchase | 결제 |
        | pin\_search | 검색 |
        | pin\_registration | 가입 |
        | pin\_sign\_up | 가입 |
        | pin\_category\_view | view\_category |
        | add\_cart | add\_to\_cart |
        | start\_checkout | 결제 |
        | content\_view | view\_category |

              **참고:** 구형 이벤트 이름을 전환 API에 대한 올바른 이벤트 이름으로 업데이트하지 않으면 Pinterest에서 이벤트 이름이 ‘기타’로 표시되며, 올바른 이벤트 이름이 표시되지 않습니다.
           2. **앱 내 이벤트 포스트백 창**을 선택하여 **평생** so Pinterest가 광고 최적화를 위해 최대 수의 전환을 받을 수 있도록 합니다.
           3. **모든 미디어 소스 포함**을 선택하여 **사용자에게** Pinterest가 광고 최적화를 위해 최대 수의 전환을 받을 수 있도록 합니다. 자세한 내용은 <Anchor target="_blank" href="/marketers/ko/docs/pinterest-create-a-mobile-app-integration#inapp-event-postbacks">KB 문서</Anchor>를 참조하십시오.
        3. **문제가 발생할 경우 롤백 프로세스**  
           광고주는 마이그레이션 중 발생할 수 있는 문제를 감지하기 위해 Pinterest에서 AppsFlyer 앱 전환을 모니터링할 것을 권장합니다. AppsFlyer 전환 데이터가 Pinterest에 표시되기까지 최대 30분이 소요될 수 있으며, 마이그레이션 성공을 검증하기 위해 며칠 동안 정기적으로 모니터링해 주십시오.  

           광고주는 통합 설정에서 `account_id` 및 `access_token` 중 하나 또는 둘 다 생략하여 레거시 엔드포인트로 되돌릴 수 있습니다. 

           **행동 규칙:**

           * `account_id`과 `access_token`가 모두 없으면 → 포스트백은 레거시(구) 엔드포인트로 전송됩니다.
           * 오직 `account_id`만 제공됨(즉, `access_token`는 비어 있음) → 포스트백은 레거시 엔드포인트로 전송됩니다.
           * 오직 `access_token`만 제공됨(즉, `account_id`는 비어 있음) → 포스트백은 레거시 엔드포인트로 전송됩니다.
           * `account_id`과 `access_token`가 모두 제공됨 → 포스트백은 새 엔드포인트로 전송됩니다.

           문제가 발생하는 경우 support@appsflyer.com을 통해 AppsFlyer 지원팀에 문의해 주십시오. Pinterest에서 문제가 발생하면 api-support@pinterest.com 또는 Pinterest 담당자에게 문의해 주십시오.
      </td>
    </tr>
  </tbody>
</Table>

<div data-zendesk-anchors="h_01K0VD1AY1XVQWA6JP0WCQP8RN=%EC%B0%B8%EA%B3%A0" />
