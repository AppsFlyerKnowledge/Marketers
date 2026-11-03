---
title: OneLink API를 사용하여 대규모 캠페인에서 링크 생성
metadata:
  keywords:
    - api
    - Premium
    - Marketers
    - QR-to-App
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - Premium
    - pm-asaf-mashiah
    - Marketers
    - QR-to-App
  created_at: '2018-06-27T12:00:29Z'
  edited_at: '2026-10-14T10:33:39Z'
  id: 360001250345
  locale: ko
  section: Deep linking using OneLink
  section_id: 6551203111057
  url: https://support.appsflyer.com/hc/ko/articles/360001250345
---
<span class="af-tag af-tag--premium" title="This AppsFlyer premium feature is available for advanced account plans or as an add-on. You can check the Account management page to see if this feature is already included in your plan. For any further questions, contact your AppsFlyer CSM or write to hello@appsflyer.com.">Premium</span>

> **한눈에 보기:** 원링크 API를 통해 SMS 문자 메시지 등 다양한 경로에서 활용할 수 있는 대규모 캠페인의 개인화된 링크를 생성하여 엔드 유저의 참여를 유도하고 온드 미디어(owned media) 활용도를 높입니다. 원링크 API는 마케터와 개발자가 함께 구현해야 합니다.

## OneLink API

OneLink API는 프리미엄 기능으로 다음이 가능합니다:

* 커스텀 파라미터를 사용해 원링크 단축 URL을 자동으로 <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/create-onelink-attribution-link">Create</Anchor>, <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/get-onelink-attribution-link">Get</Anchor>, <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/update-onelink-attribution-link">Update</Anchor> 및 <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/delete-onelink-attribution-link">Delete</Anchor>합니다.  
  파라미터 종류:
  * 미디어 소스, 캠페인, 광고 애셋 같은 마케팅 성과 측정 및 모니터링에 사용되는 어트리뷰션 관련 파라미터 **참고**: 미디어 소스(pid) 파라미터는 필수입니다.
  * 관련 링크를 통해 앱이 열렸을 때, 사용자에게 딥링킹 및 개인화된 경험을 주기 위해 필요한 딥링크 및 개인화된 파라미터. 파라미터 정보를 바탕으로 사용자에게 맞춤형 인앱 컨텐츠 연결 경험을 줄 수 있습니다. (예: 특정 제품 페이지, 쿠폰 코드, 프로모션)
* 모바일 사용자에게 웹사이트 및 앱 콘텐츠를 직접 공유할 수 있습니다. (이를 통해 모바일 인게이지먼트 및 인스톨이 증가함)
* 원링크 커스텀 어트리뷰션 링크를 대량으로 빠르게 생성합니다.  
  **참고**: 추천 링크에 대해서는 <Anchor target="_blank" href="/marketers/ko/docs/user-invite-attribution">사용자 초대 어트리뷰션 문서</Anchor>를 참조하세요.

> 📄 **예시**
>
> 식품 배달 기업, Feed Me에서 기존 회원 고객에게 SMS 문자메시지로 개인화된 링크를 전송하여 Feed Me 앱을 다운로드 받고 바나나를 구매하도록 마케팅을 하려고 합니다. Feed Me는 원링크 REST API를 사용해 고객의 국가, 신원, 바나나 세일 정보를 포함한 커스텀 원링크 URL을 생성할 수 있습니다.

사용자의 원링크 API 쿼리 수 제한은 계정 유형에 따라 다릅니다. 원링크 API 대시보드에서 생성한 쿼리 수와 남아 있는 쿼리 수를 확인할 수 있습니다. 

고객 성공 매니저에 문의하여 API 쿼리 제한을 늘릴 수 있습니다.  

### 설정

**원링크 API 설정하려면:**

1. <Anchor target="_blank" href="/marketers/ko/docs/create-a-onelink-template#원링크-템플릿-만들기">원링크 템플릿을 생성하세요</Anchor>.
2. 원링크 템플릿 ID(Template ID)를 복사합니다.  
   [![](https://files.readme.io/b25f9c4dfe6f4a5a39e9b0a4d1b82d68330f8c0853248284564ac46c72d4d423-360019487418.jpg)](https://files.readme.io/b25f9c4dfe6f4a5a39e9b0a4d1b82d68330f8c0853248284564ac46c72d4d423-360019487418.jpg)
3. <Anchor target="_blank" href="/marketers/ko/docs/managing-appsflyer-tokens#토큰-유형">원링크 API 토큰</Anchor>을 복사합니다. 보안을 위해 “관리자” 사용자가 토큰을 가져와야 하며 계정 사용자는 접근 권한이 없습니다.
4. 개발자에게 원링크 ID와 원링크 API 토큰을 제공합니다.
5. 개발자에게 <Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/onelink_rest_api">개발 허브 지침을 따르도록 안내</Anchor>하세요.

### 대시보드

원링크 API 대시보드는일별, 월별, 3개월 API 사용량을 표시합니다.

원링크 API 대시보드를 보려면:

앱스플라이어 플랫폼의 사이드 메뉴에서 **Engage** > **원링크 API**를 선택합니다.

### 특징 및 제약 사항

| 특징 | 비고 |
| --- | --- |
| API 할당량 제한 | <ul><li>원링크 API를 사용하여 원링크 링크를 생성, 편집 또는 삭제할 수 있는 한도는 계정당 월(UTC 시간대) 750만 회입니다.</li><li>이 한도를 초과한이후에 발생하는 요청은 처리되지 않으며 링크가 생성되지 않습니다. 한도 초과 후 API를 호출할 경우, 오류 상태 코드 429와 함께 “Monthly quota exceeded"라는 메시지가 뜹니다.</li><li>사용량/잔여량 정보는 원링크 API 대시보드에 표시됩니다.</li></ul> |
| 호출 제한 | <ul><li>기준 시간 내 API 최대 호출 횟수는 초당 500회(분당 30,000회)입니다.</li><li>초당 500건의 호출(분당 30000건)을 초과하는 모든 호출은 처리되지 않으며 링크가 생성되지 않습니다. 기준 시간 내 최대 호출 횟수를 초과한 뒤의 API 호출을 할 경우, "Rate limit exceeded"라는 메시지와 함께 오류 상태 코드 429를 수신하게 됩니다.</li></ul> |
| 링크 가시성 | <ul><li>API를 통해 생성된 링크는 앱스플라이어 원링크 관리 (OneLink Management) UI 내 원링크 커스텀 링크 목록에 나타나지 않습니다.</li><li>모범 사례: API로 생성한 링크를 로컬 테이블에 저장하여 향후 필요 시 사용하세요.</li></ul> |
| TTL | <ul><li>원링크 API로 생성된 원링크 단축 URL의 기본 유효 기간(TTL)은 31일입니다. 링크를 클릭할 때마다 유효 기간이 31일씩 늘어납니다. 유효 기간이 만료된 링크를 클릭할 경우, 원링크 템플릿 설정에 정의된대로 동작을 하지만, 어트리뷰션 측정은 되지 않습니다.<ul><li>TTL이 만료된 후 원링크의 단축 URL이 삭제되는 데 최대 48시간이 걸릴 수 있습니다.</li></ul></li><li>최대 TTL은 31일입니다. 31일을 초과하는 모든 TTL 값은 TTL 기본값인 31일로 대체됩니다.</li><li>파라미터 `ttl={value}` 를 추가하여 TTL 기본값을 일, 시간 또는 분 단위로 변경할 수 있습니다. 예를 들어, `ttl=7d`, `ttl=12h`, 혹은 `ttl=10m` 로 설정 가능합니다.</li><li>TTL 값을 구체적으로 변경하려면 <Anchor target="_blank" href="https://dev.appsflyer.com/reference/onelink_rest_api#update-onelink-attribution-link">업데이트 요청</Anchor>을 보낼 수 있습니다. 업데이트 요청을 하시면 (기존 링크에 대한) TTL이 요청 본문에 정의된대로 재설정됩니다.<ul><li>이는 TTL이 대체된다는 것을 의미합니다. 예를 들어 현재 TTL이 29일인 링크를 TTL 2일로 업데이트를 요청하면 TTL = 2d (TTL = 31d가 아님)로 변경됩니다.</li><li>TTL 업데이트 요청으로 링크의 유효 기간을 연장할 수 있습니다. 예를 들어 TTL이 20일인 링크에 대해 TTL을 31일로 업데이트 하도록 요청하면, 5일이 이미 경과했더라도 업데이트 시점으로부터 TTL이 31일로 설정됩니다.</li></ul></li><li>링크의 TTL이 자동으로 연장되지 않도록 하려면, 링크에 파라미터`renew_ttl=false`를 추가하세요. 이 파라미터의 값은 true (기본값) 또는 false인 boolean입니다.</li><li>파라미터 `renew_ttl` 는 실제 URL에 표시되지 않습니다.</li></ul> |
| 특수 문자 | API 생성 시 사용되는 경우 다음 문자는 반드시 인코딩되어야 합니다. links: ;, *, !, @, #, ?, $, ^, :, &, ~, \`, =, +, ’, >, &lt;, /<br />이 문자들을 인코딩하지 않으면 다음으로 대체됩니다 빈 공간으로, 링크와 그 기능이 잠재적으로 중단되고 리디렉션 문제를 일으킬 수 있습니다.<br /><br />**참고:** 다음 3개의 매개변수는 링크를 클릭할 때 디코딩되지 않으며 인코딩된 상태로 유지됩니다:<ul><li>\`af_dp\`</li><li>\`deep_link_value\`</li><li>\`deep_link_sub1\`</li></ul> |
| 페이로드 | 페이로드의 쿼리 문자열은 2,048자를 초과할 수 없습니다. |
| URL ID | URL ID(또는 숏링크 ID)를 편집하여 캠페인 콘텐츠를 강조할 수 있습니다. 예시: https://myapp.onelink.me/abc123/apples. URL ID는 50자를 초과할 수 없으며 문자와 숫자를 조합할 수 있습니다. 기본값은 8자입니다.<br /><br />참고:<ul><li>현재 ID가 사용되고 있지 않은 경우에만 URL ID를 편집할 수 있습니다.</li><li>URL ID가 이미 사용 중이면 링크를 생성할 수 없고, 오류 응답(400)이 발생합니다. 앱 소유주와 개발자는 이러한 이벤트가 발생할 경우 어떻게 처리할지 미리 결정하고 구현해야 합니다.</li><li>호출이 실패하더라도 월간 API 할당량에서 차감됩니다.</li></ul> |