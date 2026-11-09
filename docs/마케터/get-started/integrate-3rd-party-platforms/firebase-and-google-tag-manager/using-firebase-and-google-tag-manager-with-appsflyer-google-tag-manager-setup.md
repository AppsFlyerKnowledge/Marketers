---
title: Firebase와 Google 태그 관리자를 앱스플라이어와 함께 사용하기—Google 태그 관리자 설정
metadata:
  keywords:
    - Developers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-ravid-naori
    - Marketers
    - Mobile Attribution
  created_at: '2021-11-09T10:28:45Z'
  edited_at: '2026-10-14T10:39:01Z'
  id: 4410481509393
  locale: ko
  section: Firebase and Google Tag Manager
  section_id: 6551267006225
  url: https://support.appsflyer.com/hc/ko/articles/4410481509393
---
> **한눈에 보기:** Firebase SDK를 통해 보고된 이벤트를 Google 태그 관리자에서 앱스플라이어로 전송하기 위한 설정 지침입니다.

<div id="google-tag-manager-setup" />

## Google 태그 관리자 설정

이 섹션에서는 Google 태그 관리자(GTM) 화면에서 필요한 설정에 대해 설명합니다. GTM에서 앱스플라이어로 이벤트를 전송하기 위해서는 이 섹션에 설명된 모든 단계를 수행해야 합니다. 목록에 나열된 순서대로 단계를 진행해 주세요.

다음 단계는 모바일 앱용 Google 태그 관리자에서 진행할 사항입니다. 귀하의 Google 태그 관리자의 UI가 이 단계들의 스크린샷과 다르다면 다음을 확인해 보세요.

1. Google 태그 관리자 컨테이너가 모바일 앱용으로 설정되어 있어야 합니다.
2. 컨테이너는 버전 5입니다. 더 자세한 정보는 <Anchor target="_blank" href="https://support.google.com/tagmanager/answer/7003315">여기</Anchor>를 클릭하여 볼 수 있습니다.

<div id="note" />

> 📘 **참고**
>
> 이 섹션에 설명된 단계들은 구매 이벤트를 예로 들었지만, 전송하고자 하는 모든 이벤트에 적용할 수 있습니다.

<div id="1-creating-event-parameter-variables" />

<Accordion title="1. 이벤트 파라미터 변수 생성">

이벤트 파라미터 변수를 사용하면 Google 태그 관리자가 이벤트로부터 데이터를 획득할 수 있습니다. 이벤트를 전송할 때 앱스플라이어 ID와 개발자 키 변수가 같이 전달됩니다. Google 태그 관리자는 해당 값을 평가하여 데이터를 획득하는 방식입니다. 이벤트로부터 얻은 데이터는 두 가지 기능이 있습니다.

1. Google 태그 관리자에 앱스플라이어 ID와 개발자 키를 제공
2. Google 태그 관리자에 이벤트 이름과 이벤트 파라미터 제공

<Tabs>
<Tab title="앱스플라이어 디바이스 ID와 개발자 키">

Google 태그 관리자가 앱스플라이어에 이벤트를 전송할 때는 반드시 앱스플라이어 ID와 개발자 키를 함께 전송해야 합니다. 개발자 키는 Google 태그 관리자가 앱스플라이어 서버와의 통신을 가능하게 합니다. 앱스플라이어 ID는 앱스플라이어에게 해당 이벤트를 어떤 사용자에게 귀속할지 알려줍니다.

1. Google 태그 관리자에서 ***변수***를 선택한 후 ***새로 생성***를 클릭하세요.
2. 변수의 이름을 “AppsFlyer Dev Key"로 지정하고 <strong><em>변수 설정(Variable Configuration)</em></strong>을 클릭하세요.
3. ***이벤트 파라미터***를 선택하세요.
4. ***사용자 정의 파라미터***를 선택하세요.
5. ***이벤트 파라미터*** 필드에 'dev\_key'을 입력하고 저장하세요.
6. 앱스플라이어 ID에 대해서도 같은 과정을 반복하되, 변수명을 '앱스플라이어 디바이스 ID'로 설정하고 ***이벤트 파라미터*** 필드에 'af\_id'를 입력하세요.

<div id="note-1" />

> 📄 **예시**
>
> 아래는 GTM 사용자 인터페이스의 스크린샷입니다. 이벤트 파라미터의 최종 설정을 보여줍니다:
>
> <Image align="center" alt="event_parameter_variable_dev_key.png" src="https://files.readme.io/f5030ce110ec4459f673a4088c2c09a4e3f90a35976f4fbfccb8750cb112e69e-49839295695889.png" />

<div id="important" />

> 🚧 **중요!**
>
> iOS의 경우, 추가적인 이벤트 파라미터 설정이 필요합니다. 위에서 설명한 절차대로 진행하세요. 변수를 생성하고 'Apple 앱 ID'라고 명명하세요. 이벤트 파라미터 필드에 'apple\_app\_id'를 입력하고 저장하세요.

다음으로, 앱 안에서 앱스플라이어 ID와 개발 키 변수를 생성 및 설정해야 합니다. 이 단계는 <Anchor target="_blank" href="/marketers/ko/docs/using-firebase-and-google-tag-manager-with-appsflyer-sending-installs-and-events#앱에서-이벤트-구성하기">이벤트 전송</Anchor> 세션에서 다룹니다.

</Tab>

<Tab title="수익과 가격">

대부분 인앱 이벤트는 이벤트 값 파라미터가 요구됩니다. 이 경우는 af\_revenue와 af\_price 파라미터가 해당되지만 다른 이벤트 파라미터들도 전송할 수 있습니다. 앱에서 이벤트를 설정한 후에는 Google 태그 관리자에서 수익과 가격에 해당하는 변수들을 생성해야 합니다. 이 변수들은 나중에 구매 이벤트 태그에 이용됩니다.

1. Google 태그 관리자에서 af\_revenue와 af\_price에 대한 이벤트 파라미터 변수 두 개를 생성하세요.
2. 'af\_revenue'의 경우 변수명을 '수익'으로 설정하고 ***이벤트 파라미터 키***를 'af\_revenue'로 하세요.
3. 'af\_price'의 경우 변수명을 '가격'으로 설정하고 ***이벤트 파라미터 키***를 'af\_price'로 하세요.

<div id="note-2" />

> 📄 **예시**
>
> 아래는 GTM 사용자 인터페이스의 스크린샷입니다. 이벤트 파라미터의 최종 설정을 보여줍니다:
>
> <Image align="center" alt="event_parameter_variable_revenue.png" src="https://files.readme.io/40e6ccd8d2df9370210847d6ff54a5a44c04f295dac9ece18dac715e5fc335a1-49839295696657.png" />

<div id="note-3" />

> 📘 **참고**
>
> 여기에 제시된 예제는 수익과 가격에 관한 이벤트 파라미터 변수를 생성하는 방법을 보여줍니다. 전달되는 이벤트에 따라 어떠한 종류의 이벤트 파라미터에 대해서도 변수를 생성할 수 있습니다.

</Tab>
</Tabs>

</Accordion>

<div id="2-creating-a-trigger-for-the-purchase-event" />

<Accordion title="2. 구매 이벤트에 대하여 트리거를 생성하세요.">

Google 태그 관리자가 이벤트를 앱스플라이어로 전송할지 여부를 판단할 수 있도록 해당 이벤트에 대한 트리거 설정이 필요합니다.

1. Google 태그 관리자에서 ***트리거***를 클릭하고 ***새로 만들기***를 선택하세요.
2. 트리거 이름을 '구매'로 설정하고 ***트리거 구성***을 클릭하세요.
3. ***커스텀***을 선택하세요.
4. ***일부 이벤트***를 선택하세요.
5. "af\_purchase"와 같은 ***이벤트 이름***일 때 트리거가 작동하도록 조건을 설정합니다
6. ***저장*** 버튼을 클릭합니다.

<div id="note-4" />

> 📄 **예시**
>
> 아래는 GTM 사용자 인터페이스의 스크린샷입니다. 트리거의 최종 설정 상태를 확인할 수 있습니다:
>
> <Image align="center" alt="trigger_purchase_event.png" src="https://files.readme.io/ef2e70fb2aa0b25f1243d6fa565e3cdb1df407fd2d4b3105dee412ccad7f2704-49839256428689.png" />

</Accordion>

<div id="3-creating-a-tag-for-the-purchase-event" />

<Accordion title="3. 구매 이벤트 태그 만들기">

필요한 변수들과 이벤트 트리거를 설정한 후, 구매 이벤트 태그를 만들 준비가 되었습니다.

1. Google 태그 관리자에서 ***태그***를 선택하고 이어서 ***신규***를 클릭하세요
2. "구매"라는 이름의 태그를 만들고 ***태그 설정***를 클릭하세요
3. ***앱스플라이어*** 선택
4. ***어플리케이션 ID*** 필드에 앱 ID에 대한 내장 변수를 입력합니다

   <div id="important-1" />

   > 🚧 **중요!**
   >
   > iOS 용으로는 ***어플리케이션 ID*** 필드에 "apple\_app\_id" 커스텀 변수를 설정하세요.

5. ***개발 키*** 필드에서는 "앱스플라이어 개발 키" 변수를 선택하세요
6. ***앱스플라이어 디바이스 ID*** 필드에서는 "앱스플라이어 디바이스 ID" 변수를 선택하세요
7. 이벤트 이름 필드에는 내장 변수 ***이벤트 이름***을 지정하세요
8. ***이벤트 통화*** 필드에는 예를 들어 USD와 같은 귀사의 통화 코드를 입력합니다
9. ***이벤트 값 추가***를 두 번 클릭하세요
10. 아래와 같이 설정하세요:  
    ***키***: af\_revenue, ***값***: "수익" 이벤트 파라미터 변수를 선택합니다  
    ***키***: af\_price, ***값***: "가격" 이벤트 파라미터 변수를 선택합니다
11. ***트리거 설정*** 영역에서 ***트리거 발생*** 을 "구매" 이벤트 트리거로 설정하세요
12. ***저장*** 버튼을 클릭합니다.

<div id="note-5" />

> 📄 **예시**
>
> 아래는 GTM 사용자 인터페이스의 스크린샷입니다. 태그의 최종 설정 상태를 확인할 수 있습니다:
>
> <Image align="center" alt="purchase_tag.png" src="https://files.readme.io/893bdf6ce65bf6bd0435f4e7c02ff044b35e5e14ebea131f547040f763d7512d-49839295697169.png" />

</Accordion>

<div id="4-publishing-the-tag-manager-container" />

<Accordion title="4. 태그 관리자 컨테이너 배포">

Google 태그 관리자에서 변경사항(태그 추가 등)이 있을 때마다 컨테이너를 다운로드하여 앱의 루트 폴더에 추가해야 합니다:

* 안드로이드의 경우 - app/src/main/assets/containers
* iOS의 경우 - 루트 폴더/container

테스트 디바이스에서 애플리케이션을 빌드하고 설치한 후 디버그 로그로 이벤트가 정상적으로 트리거되고 전송되는지 확인하세요.

</Accordion>

<div data-zendesk-anchors="google-tag-manager-setup=google-%ED%83%9C%EA%B7%B8-%EA%B4%80%EB%A6%AC%EC%9E%90-%EC%84%A4%EC%A0%95 h_01HE7SFG97FKSVAY5QHVHGF3GV=google-%ED%83%9C%EA%B7%B8-%EA%B4%80%EB%A6%AC%EC%9E%90-%EC%84%A4%EC%A0%95 h_01HE7SFG97RP20KAEYDJMM460D=%EC%B0%B8%EA%B3%A0 h_01HE7SFG97YVYNT385MNFA9ECN=1-creating-event-parameter-variables h_01HE7SFG97NDENJQH63J8M8CDK=%EC%98%88%EC%8B%9C h_01HE7SFG97GYZP68YKW93Y0VFR=%EC%A4%91%EC%9A%94 h_01HE7SFG97WY50DX10ATM7Z31Y=%EC%98%88%EC%8B%9C h_01HE7SFG97E6Z7FEJET53T4CKR=%EC%B0%B8%EA%B3%A0 h_01HE7SFG98XGBMTA7ZF8XSNF29=2-creating-a-trigger-for-the-purchase-event h_01HE7SFG98CRQE99PJ3CEHWM0E=%EC%98%88%EC%8B%9C-2 h_01HE7SFG98R4DGTRWXE247MRPK=3-creating-a-tag-for-the-purchase-event h_01HE7SFG98DWKMETHSP0M15GW8=%EC%A4%91%EC%9A%94-1 h_01HE7SFG986JJKFKDZQCR6JKMQ=%EC%98%88%EC%8B%9C-3 h_01HE7SFG98R2KGRRDA9TQTYD3B=4-publishing-the-tag-manager-container" />
