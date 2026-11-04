---
title: 인앱이벤트 생성기
metadata:
  keywords:
    - Developers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-guy-sarfatty
    - Marketers
    - Mobile Attribution
  created_at: '2022-11-08T12:47:30Z'
  edited_at: '2026-10-14T10:37:14Z'
  id: 10457123447953
  locale: ko
  section: In-app events
  section_id: 6551285343761
  url: https://support.appsflyer.com/hc/ko/articles/10457123447953
---
> **한눈에 보기:** 요약: 비즈니스 요구에 따라 이벤트 이름과 콘텐츠를 정의하여 인앱이벤트를 전송하기 위한 앱 코드(네이티브 Android 및 iOS, Unity)를 자동으로 생성합니다.

<div id="introduction" />

## 소개

인앱이벤트는 앱 유저가 앱 설치 후 취하는 조치를 기반으로 **다양한 소스에서 유저의 질을 측정하는** 주요 도구입니다. 이벤트는 CPA 기반 마케팅 캠페인을 수행하는 데도 자주 사용됩니다.

하지만 두 명 이상이 인앱이벤트를 정의하고 앱에 연동하는 데 관여하는 경우가 많습니다. 마케팅 담당자/제품 관리자가 비즈니스 요구에 따라 이벤트 세트 콘텐츠를 정의하지만, 일반적으로 한 명 이상의 모바일 개발자가 앱에서 인앱이벤트 API를 구현해야 합니다.

앱스플라이어의 <Anchor target="_blank" href="https://evgen.appsflyer.com/">인앱이벤트 생성기</Anchor>**는 마케팀 담당자와 개발자 간의 필수적인 협업에 내재된 문제를 해결합니다**.

마케팅 담당자는 인앱이벤트 생성기를 사용하여 다음을 수행할 수 있습니다.

* 버티컬에 대해 미리 정의된 **권장 이벤트** 및 파라미터 세트를 사용합니다.
* 참조를 위해 미리 정의되거나 사용자 지정된 이벤트/파라미터, 설명, 트리거 및 예제를 추가하거나 제거합니다.
* **자동 생성된 코드**를 Android 및 iOS 모바일 개발자에게 전송하여 **작업 일수,** 중복 커뮤니케이션, 잠재적 오류를 줄일 수 있습니다.
* **나중에 이벤트를 업데이트하거나 새 이벤트를 추가하거나 새 앱을 추가하는 경우** 작업을 다시 사용합니다.

<div id="using-the-in-app-event-generator" />

## 인앱 이벤트 생성기 사용

인앱이벤트 생성기를 사용하여 새 앱에 대한 이벤트 세트를 만들거나 기존 세트를 업데이트합니다.

<div id="creating-a-new-event-set" />

### 새 이벤트 세트 만들기

**새 이벤트 세트를 만드는 방법:**

1. <Anchor target="_blank" href="https://evgen.appsflyer.com/">인앱이벤트 생성기</Anchor>로 이동하여 앱 이름을 입력합니다.
2. 버티컬을 선택하거나 이전에 JSON 파일로 내보낸 유사한 앱의 이벤트 세트를 가져옵니다.
3. 비즈니스 요구 사항에 따라 이벤트와 파라미터를 추가하거나 제거합니다.
5. .zip 다운로드를 **클릭하여**  나중에 사용하거나 개발자 및 동료와 협업할 수 있도록 이벤트 세트를 저장합니다.

<div id="updating-an-existing-event-set" />

### 기존 이벤트 세트 업데이트

**기존 이벤트 세트 업데이트 방법:**

1. <Anchor target="_blank" href="https://evgen.appsflyer.com/">인앱이벤트 생성기</Anchor>로 이동합니다.
2. 이전에 JSON 파일로 내보낸 앱의 이벤트 세트를 가져옵니다.
3. 비즈니스 요구 사항에 따라 이벤트와 파라미터를 추가하거나 제거합니다.
5. .zip 다운로드를 **클릭하여**  나중에 사용하거나 개발자 및 동료와 협업할 수 있도록 이벤트 세트를 저장합니다.

<div id="adding-events" />

### 이벤트 추가

**이벤트 세트에 새 이벤트를 추가하는 방법:**

3. 비즈니스 시나리오를 설명하는 이벤트의 목적을 입력합니다.
4. 이벤트에 대한 트리거 동작을 입력하여 유저 여정에서 이벤트를 전송해야 하는 시간을 설명합니다. 이 설명은 개발자가 빠르게 참조할 수 있도록 생성된 코드에 주석으로 추가됩니다.
5. [선택 사항] 이벤트에 하나 이상의 파라미터를 추가합니다.

<div id="adding-parameters" />

### 파라미터 추가

**이벤트 세트에 새 파라미터를 추가하는 방법:**

1. 관련 이벤트에 대한 **+ 파라미터 추가** 버튼을 클릭합니다.
2. 제안된 파라미터 목록에서 미리 정의된 **파라미터를 선택합니다(권장).**
3. 그렇지 않으면 **사용자 지정**을 클릭하여 고유한 파라미터 이름을 정의하고 **Enter**. 키를 누릅니다.
4. 참조할 일반적인 파라미터 값을 하나 이상 입력합니다.
5. 개발자에게 도움이 되도록, 앱의 파라미터 값에 대한 일반 설명, 필드 유형 또는 해당 소스를 입력합니다. 이는 생성된 코드의 각 이벤트 파라미터에 대한 주석으로 나타납니다.

**참고**: 일러두기: <Anchor target="_blank" href="/marketers/ko/docs/in-app-events-overview#predefined-and-custom-events">미리 정의된 이름 지정</Anchor>/span>이  권장되는 방법이며 이를 통해 이벤트 및 파라미터를 파트너에 자동으로 매핑할 수 있습니다.

<div id="see-also" />

> 📄 **참고 항목**
>
> * 이벤트 대시보드

<div data-zendesk-anchors="introduction=%EC%86%8C%EA%B0%9C h_01HE7T0ZA12E7KHS7WBQ757KF1=%EC%86%8C%EA%B0%9C using-the-inapp-event-generator=%EC%9D%B8%EC%95%B1-%EC%9D%B4%EB%B2%A4%ED%8A%B8-%EC%83%9D%EC%84%B1%EA%B8%B0-%EC%82%AC%EC%9A%A9 h_01HE7T0ZA2A1KS4NF43GRZB87X=%EC%9D%B8%EC%95%B1-%EC%9D%B4%EB%B2%A4%ED%8A%B8-%EC%83%9D%EC%84%B1%EA%B8%B0-%EC%82%AC%EC%9A%A9 creating-a-new-event-set=%EC%83%88-%EC%9D%B4%EB%B2%A4%ED%8A%B8-%EC%84%B8%ED%8A%B8-%EB%A7%8C%EB%93%A4%EA%B8%B0 h_01HE7T0ZA2KQ44P40Y028VVA4K=%EC%83%88-%EC%9D%B4%EB%B2%A4%ED%8A%B8-%EC%84%B8%ED%8A%B8-%EB%A7%8C%EB%93%A4%EA%B8%B0 updating-an-existing-event-set=%EA%B8%B0%EC%A1%B4-%EC%9D%B4%EB%B2%A4%ED%8A%B8-%EC%84%B8%ED%8A%B8-%EC%97%85%EB%8D%B0%EC%9D%B4%ED%8A%B8 h_01HE7T0ZA2P2WZ07CT880ZSK0Z=%EA%B8%B0%EC%A1%B4-%EC%9D%B4%EB%B2%A4%ED%8A%B8-%EC%84%B8%ED%8A%B8-%EC%97%85%EB%8D%B0%EC%9D%B4%ED%8A%B8 adding-events=%EC%9D%B4%EB%B2%A4%ED%8A%B8-%EC%B6%94%EA%B0%80 h_01HE7T0ZA2Z3D3J014E7E0T13X=%EC%9D%B4%EB%B2%A4%ED%8A%B8-%EC%B6%94%EA%B0%80 adding-parameters=%ED%8C%8C%EB%9D%BC%EB%AF%B8%ED%84%B0-%EC%B6%94%EA%B0%80 h_01HE7T0ZA2KAH7N44EQ9W5BH5G=%ED%8C%8C%EB%9D%BC%EB%AF%B8%ED%84%B0-%EC%B6%94%EA%B0%80 h_01HE7T4ZR4AY2J71B3PJKJP490=%EC%B0%B8%EA%B3%A0-%ED%95%AD%EB%AA%A9" />
