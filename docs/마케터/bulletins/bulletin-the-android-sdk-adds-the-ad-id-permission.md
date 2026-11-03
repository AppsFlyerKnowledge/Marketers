---
title: '게시판: Android SDK는 AD_ID 권한을 추가합니다.'
metadata:
  keywords:
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
  created_at: '2022-07-12T08:57:45Z'
  edited_at: '2026-10-14T10:31:23Z'
  id: 7569900844689
  locale: ko
  section: Bulletins
  section_id: 6551161473041
  url: https://support.appsflyer.com/hc/ko/articles/7569900844689
---
> **한눈에 보기:** AppsFlyer Android SDK V6.8.0부터 AD\_ID 권한이 SDK의 AndroidManifest.xml에 선언됩니다.

| **배경** | 2022년 초, 구글은 구글 플레이 서비스의 동작과 안드로이드 광고 ID 가져오기의 변경을 발표했습니다.<br /><br /><Anchor target="_blank" href="https://support.google.com/googleplay/android-developer/answer/6048248?hl=en">발표</Anchor>에 따르면, Android 13(API 33) 이상을 타겟으로 하는 앱은 기기의 광고 ID에 액세스하기 위해 매니페스트 파일에서 구글 플레이 서비스 일반 권한을 선언해야 합니다.<br /><br />해당 권한은 설치 시 앱에 부여되며 사용자 상호작용을 유발하지 않습니다. |
| --- | --- |
| **변경 사항** | AppsFlyer Android SDK V6.8.0부터 AD\_ID 권한이 SDK의 AndroidManifest.xml에 선언됩니다. 앱이 빌드되면 SDK 매니페스트가 기본적으로 앱의 매니페스트와 병합되고, 앱에서 권한을 명시적으로 선언하지 않더라도 권한이 추가됩니다. 앱과 SDK에 모두 권한이 있는 경우에는 충돌 없이 잘 작동합니다. |
| **알아두어야 할 사항** | <ul><li>SDK V6.8.0을 사용 중이고 앱의 매니페스트에 AD\_ID 권한이 있는 경우, 매니페스트에서 권한을 선택적으로 제거하고 SDK가 이를 자동으로 추가하도록 할 수 있습니다.</li><li>SDK 버전이 6.8.0보다 **이전** 버전이고 앱이 Android 13(API 33) 이상을 타겟으로 하는 경우 SDK가 광고 ID에 액세스할 수 있도록 앱에 AD\_ID 권한을 추가해야 합니다.</li><li>**아동 대상 앱:** <Anchor target="_blank" href="https://support.google.com/googleplay/android-developer/answer/11043825?hl=en">구글의 정책</Anchor>에 따라, 어린이를 타겟으로 하는 앱은 광고 ID를 전송해서는 안 됩니다. 어린이용 앱을 개발 중이며 SDK V6.8.0 이상을 사용하는 경우 AD\_ID 권한을 취소해야 합니다. 개발자 지침은 <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/install-android-sdk#revoking-the-ad_id-permission">여기</Anchor>를 참조하세요.</li></ul> |