---
title: 수신 파트너 연결 - Braze
metadata:
  keywords:
    - Advertisers
    - Premium Feature
    - Marketers
    - Audience Segmentation
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-neama-benhabib
    - Marketers
    - Audience Segmentation
  created_at: '2021-11-17T09:55:26Z'
  edited_at: '2026-10-14T10:31:36Z'
  id: 4411130243217
  locale: ko
  section: Audiences
  section_id: 6551336428945
  url: https://support.appsflyer.com/hc/ko/articles/4411130243217
---
> **한눈에 보기:** Braze 메시지 인게이지먼트 이벤트를 앱스플라이어 오디언스로 발송하여 오디언스 정의를 더 정밀하게 할 수 있습니다.

Braze 계정과 앱스플라이어 오디언스 사이의 수신 연결을 설정하여 Braze 메시지 인게이지먼트 이벤트 데이터를 오디언스로 가져올 수 있습니다. 이 데이터는 오디언스를 정의할 때 <Anchor target="_blank" href="%20/docs/audiences-guide#all-about-rulesets">규칙 집합</Anchor>에 사용할 수 있습니다.

> 🚧 **필수 조건**
>
> * Braze와 앱스플라이어 SDK가 모두 귀사의 앱에 통합되어야 합니다.
> * Braze의 **Currents** 기능을 구독해야 합니다.

## Braze 수신 연결 설정

Braze 수신 연결을 설정하는 세 가지 주요 단계가 있습니다.

1. [앱스플라이어 SDK 설정](/docs/audiences-use-braze-events-in-audience-creation#set-up-the-appsflyer-sdk)
2. [앱스플라이어에서 수신 연결 생성](/docs/audiences-use-braze-events-in-audience-creation#create-an-incoming-braze-connection-in-appsflyer)
3. [Braze에서 Current 생성](/docs/audiences-use-braze-events-in-audience-creation#create-a-current-in-braze)

<div id="set-up-the-appsflyer-sdk" />

<Accordion title="앱스플라이어 SDK 설정">

Braze에서 들어오는 연결을 만들려면 귀사의 앱에 있는 앱스플라이어 SDK가 각 유저의 **Braze 외부 ID**를 앱스플라이어로 전달하도록 구성되어야 합니다. 다음 중 하나를 사용하여 수행할 수 있습니다.

* Braze 외부 ID 매개변수
* CUID 필드

#### **Braze 외부 ID 매개변수 사용**

앱스플라이어 SDK의 `setPartnerData` 함수를 사용하여 Braze 외부 ID를 앱스플라이어에 전달하기 위한 전용 매개변수를 구성할 수 있습니다. 다음은 사용 예입니다.

<Tabs>
<Tab title="안드로이드">

```java
Map<String, Object> brazeData = new HashMap<>();
partnerData.put("external_user_id", "some-braze-external-id-value");
AppsFlyerLib.getInstance().setPartnerData("braze_int", brazeData);
```

</Tab>

<Tab title="iOS">

```objectivec
NSDictionary *brazeInfo = @{
@"external_user_id":@"some-braze-external-id-value"
};
[[AppsFlyerLib shared] setPartnerDataWithPartnerId:@"braze_int"
partnerInfo:brazeInfo];
```

</Tab>
</Tabs>

#### **CUID 필드 사용**

다음과 같은 경우 Braze 외부 ID에 대한 전용 매개변수를 구성할 필요가 없습니다:

* SDK를 구성하여 각 유저에 대해 앱스플라이어로 <Anchor target="_blank" href="/marketers/ko/docs/customer-user-id-field-cuid">CUID</Anchor>를 발송합니다.
* CUID가 Braze 외부 ID와 동일한 값을 가집니다.

이 경우, 수신 Braze 연결을 [생성](/docs/audiences-use-braze-events-in-audience-creation#create-an-incoming-braze-connection-in-appsflyer)할 때 **CUID 옵션**을 SDK 파라미터로 선택하기만 하면 됩니다.

</Accordion>

<div id="create-an-incoming-braze-connection-in-appsflyer" />

<Accordion title="앱스플라이어에서 수신 Braze 연결 만들기">

**앱스플라이어에서 수신 연결을 만들려면 다음 단계를 따르세요:**

1. 앱스플라이어의 측면 메뉴에서 **인게이지먼트** > **오디언스**를 선택합니다.
2. 오디언스 페이지에서 **연결> 수신** **탭**으로 이동합니다.
3. **New incoming connection** 버튼을 클릭합니다.
4. 사용 가능한 파트너 목록에서 Braze를 선택하세요.
5. **저장** 버튼을 클릭하여 연결을 생성합니다.  
   **연결 자격 증명** 대화 상자가 열립니다.
6. Braze 플랫폼에서 앱스플라이어 오디언스와 연결할 때 사용할 자격 증명을 복사합니다.
   * 액세스 키 ID
   * 비밀 액세스 키
   * 버킷 이름
   * 폴더 경로
7. Braze 외부 ID 발송에 사용하는 SDK 매개변수를 선택하세요.
   * Braze 외부 ID
   * CUID

</Accordion>

<div id="create-a-current-in-braze" />

<Accordion title="Braze에서 Current 생성">

**Braze에서 Current를 생성하려면 다음 단계를 따르세요.**

1. 왼쪽 메뉴의 **연동** 섹션으로 이동합니다.
2. **Currents**를 클릭합니다.
3. **Create Current** 버튼을 클릭하세요.
4. **Amazon S3 데이터 내보내기**를 선택하세요.
5. **Create Currents Integration** 섹션에서:
   1. Current의 이름을 입력합니다 (예: 앱스플라이어 오디언스).
   2. Current 자격 증명에 문제가 발생할 경우, 귀사의 팀에 있는 사람의 이메일을 입력하세요.
6. **자격 증명** 섹션에서:
   1. **AWS 비밀 액세스 키** 옵션을 선택한 상태로 유지합니다 (기본값입니다).
   2. 앱스플라이어에서 복사한 자격 증명을 해당 필드에 입력하세요.
   3. **암호화 사용** 옵션을 선택하지 않습니다.
7. **일반 설정**에서 **익명 사용자 이벤트 포함** 항목을 선택한 상태로 유지합니다.
8. **메시지 인게이지먼트 이벤트** 섹션에서 앱스플라이어로 보낼 Braze 이벤트를 선택합니다. 지원되는 이벤트 목록은 [아래](/docs/audiences-use-braze-events-in-audience-creation#지원되는-이벤트)에서 확인하세요.
9. 고객 행동 및 사용자 이벤트 섹션에서 **고객 행동 및 사용자 이벤트 측정** 옵션을 비활성화 상태로 유지합니다.
10. **현재 실행** 버튼을 클릭하여 설정을 저장하고 Braze 메시지 인게이지먼트 이벤트를 오디언스로 보내기 시작합니다.

#### 지원되는 이벤트

> 📘 **지원되는 Braze 이벤트**
>
> * 구독 그룹 상태 변경
> * 이메일 클릭
> * 이메일 열기
> * 이메일 발송
> * 이메일 전달
> * 이메일 스팸으로 표시
> * 이메일 구독 취소
> * 이메일 반송
> * 이메일 소프트 반송
> * 푸시 열기
> * 푸시 발송
> * 푸시 반송
> * iOS 포그라운드 푸시
> * SMS 문자메시지 / MMS 발송

</Accordion>

## 오디언스에서 Braze 데이터 사용

Braze 수신 연결이 설정되면, 정의한 인게이지먼트 이벤트가 오디언스를 정의하기 위한 [규칙 집합 필터](/docs/audiences-use-braze-events-in-audience-creation/%20/docs/audiences-guide#all-about-rulesets)에서 옵션으로 표시됩니다.

[altaudiences\_braze\_ruleset.pngalt](https://support.appsflyer.com/hc/article_attachments/30448288631313)

**참고:** Braze에서 현재를 실행한 후, Braze 메시지 인게이지먼트 이벤트가 앱스플라이어에서 사용할 수 있게 되기까지 약 24시간이 소요됩니다.

<div data-zendesk-anchors="h_01HKW0BS5H5FS7MXZPHBARK3VR=%ED%95%84%EC%88%98-%EC%A1%B0%EA%B1%B4 set-up-the-braze-incoming-connection=braze-%EC%88%98%EC%8B%A0-%EC%97%B0%EA%B2%B0-%EC%84%A4%EC%A0%95 h_01HKW0BS5H1ANWAJZTVBWDQHJH=braze-%EC%88%98%EC%8B%A0-%EC%97%B0%EA%B2%B0-%EC%84%A4%EC%A0%95 h_01HKW0BS5HKREHBKPMQ25AYTMH=set-up-the-appsflyer-sdk using-a-braze-external-id-parameter=braze-%EC%99%B8%EB%B6%80-id-%EB%A7%A4%EA%B0%9C%EB%B3%80%EC%88%98-%EC%82%AC%EC%9A%A9 h_01HKW0BS5HGB2RYGWNXT1M163C=braze-%EC%99%B8%EB%B6%80-id-%EB%A7%A4%EA%B0%9C%EB%B3%80%EC%88%98-%EC%82%AC%EC%9A%A9 using-the-cuid-field=cuid-%ED%95%84%EB%93%9C-%EC%82%AC%EC%9A%A9 h_01HKW0BS5HQJZRR60VKBCWGHQB=cuid-%ED%95%84%EB%93%9C-%EC%82%AC%EC%9A%A9 h_01HKW0BS5H6P7WTT6XBYF7HP3X=create-an-incoming-braze-connection-in-appsflyer h_01HKW0BS5J83HMXPWB6VNKD6P1=create-a-current-in-braze supported-events=%EC%A7%80%EC%9B%90%EB%90%98%EB%8A%94-%EC%9D%B4%EB%B2%A4%ED%8A%B8 h_01HKW0BS5JM8A9XFVX22KWFE3H=%EC%A7%80%EC%9B%90%EB%90%98%EB%8A%94-%EC%9D%B4%EB%B2%A4%ED%8A%B8 h_01HKW0BS5J6V57BDHKRY9A5XZE=%EC%A7%80%EC%9B%90%EB%90%98%EB%8A%94-braze-%EC%9D%B4%EB%B2%A4%ED%8A%B8 using-braze-data-in-audiences=%EC%98%A4%EB%94%94%EC%96%B8%EC%8A%A4%EC%97%90%EC%84%9C-braze-%EB%8D%B0%EC%9D%B4%ED%84%B0-%EC%82%AC%EC%9A%A9 h_01HKW0BS5JTZQ71HFE305ZT1CS=%EC%98%A4%EB%94%94%EC%96%B8%EC%8A%A4%EC%97%90%EC%84%9C-braze-%EB%8D%B0%EC%9D%B4%ED%84%B0-%EC%82%AC%EC%9A%A9" />
