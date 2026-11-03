---
title: 앱 삭제 측정
metadata:
  keywords:
    - Advertisers
    - Developers
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-alina-koifman
    - Marketers
    - Mobile Attribution
  created_at: '2021-10-14T08:03:47Z'
  edited_at: '2026-10-14T10:39:03Z'
  id: 4408933557137
  locale: ko
  section: Attribution scenarios
  section_id: 6551328497041
  url: https://support.appsflyer.com/hc/ko/articles/4408933557137
---
> **한눈에 보기**: 귀사의 앱 삭제 비율을 측정하고 어떤 소스(미디어 소스, 캠페인, 광고 크리에이티브, 지역)가 우수한 사용자를 유입시키는지 판단합니다.

## 개요

귀사의 앱 사용자 가치를 파악하려면 인스톨과 앱 삭제 비율을 모두 분석해야 합니다. 앱 삭제 지표는 귀사의 성과를 측정하고 사용자가 앱을 떠나는 시기와 이유를 이해하는 데 도움이 됩니다.

### 어떻게 작동하나요?

1. 앱스플라이어는 Firebase Cloud Messaging(FCM)과 Apple 푸시 알림 서비스(APNS)에 매일 API 요청을 보냅니다.
2. FCM과 APNS는 앱이 지정된 디바이스에 아직 설치되어 있는지 확인하기 위해 무음 푸시 알림을 발송합니다.
3. 응답이 앱이 삭제되었다고 표시되는 경우(FCM 및 APNS) 또는 지난 270일 동안 유저 액티비티가 기록되지 않은 경우(FCM만 해당) 앱 삭제가 기록됩니다.
4. 앱스플라이어는 사용자를 유입시킨 원래 미디어 소스에 앱 삭제를 귀속시킵니다.

> 📘 **참고**
>
> 앱 삭제 지표는 유저 유입 보기에서만 제공합니다

## 앱 삭제 데이터 활용 방법

다음은 앱 삭제 측정을 통해 얻을 수 있는 인사이트와 그 데이터를 사용하여 캠페인과 사용자 인게이지먼트를 최적화하는 방법에 대한 몇 가지 예입니다.

<div id="compare-the-quality-of-sources" />

<Accordion title="소스의 품질 비교하기">

다양한 소스(미디어 소스, 캠페인, 광고 크리에이티브, 지역)에서 확보한 사용자 품질을 비교하면 앱 삭제율이 가장 낮은 미디어 소스를 파악할 수 있고, 그쪽으로 자금을 재분배할 수 있습니다.

> 📄 **예시**
>
> 귀하는  PlayIt Gaming International의 게임 앱 마케터입니다. 방금 새 앱을 출시했고 두 개의 다른 미디어 소스(미디어 소스 A와 미디어 소스 B)에서 캠페인을 운영 중입니다.
>
> 대시보드를 확인하면 미디어 소스 A가 인스톨 수(10,390)가 가장 높지만 앱 삭제율(30%)도 가장 높은 것을 알 수 있습니다.
>
> 반면, 미디어 소스 B는 5,949개의 인스톨과 가장 낮은 앱 삭제율(12%)을 보였습니다.
>
> [alt앱 삭제율.pngalt](https://support.appsflyer.com/hc/article_attachments/30448123869585)
>
> 이러한 데이터 인사이트를 바탕으로 미디어 소스 B에 더 많은 예산을 재분배하고 더 많은 참여 사용자를 확보할 수 있습니다.

</Accordion>

<div id="share-uninstall-data-with-ad-networks-for-optimization" />

<Accordion title="최적화를 위해 애드 네트워크와 앱 삭제 데이터 공유">

협력하는 애드 네트워크에 앱 삭제 이벤트 포스트백을 발송하는 것은 유저 유입 캠페인을 최적화하는 데 유용합니다. 앱 삭제 이벤트는 [af\_uninstall을 애드 네트워크에 매핑하여](/docs/measure-uninstalls#앱-삭제-이벤트-매핑) 발송할 수 있습니다. 매핑이 완료되면, 사용자가 앱을 삭제한 것으로 식별될 때마다 이벤트가 전송됩니다. 애드 네트워크는 이 정보를 활용해 참여도가 낮은 사용자를 판단하고 더 높은 참여도를 가진 사용자 확보에 집중할 수 있습니다.

> 📄 **예시**
>
> 당신은 PlayIt Gaming International의 게임 앱 마케터입니다. 미디어 소스 A는 새로운 안드로이드 앱 출시를 위해 협력하고 있는 애드 네트워크입니다. 미디어 소스 A와 함께 운영한 이전 캠페인에서는 1,000명의 신규 사용자가 앱을 설치했으며, 그 후 300명의 사용자가 앱을 삭제했습니다. 새 캠페인에서는 미디어 소스 A가 앱 삭제 데이터를 받도록 하세요. 이를 통해 미디어 소스 A는 앱 삭제 문제를 신속하게 해결할 수 있습니다.
>
> 이전 캠페인 통찰력에 기반하여 미디어 소스 A는 새 캠페인에서 특정 사용자 유형을 제외하는 캠페인 제외 목록을 만듭니다.
>
> * 귀사의 앱에 대한 가치가 낮다고 이미 판단된 사용자입니다.
> * 정기적으로 앱 삭제하는 사용자입니다.
>
> 이를 통해 미디어 소스 A는 캠페인 광고를 볼 필요가 없는 사용자에게 귀사의 캠페인 예산이 낭비되지 않도록 오디언스 타겟팅을 최적화합니다.

</Accordion>

<div id="exclude-uninstalls-from-retargeting-campaigns" />

<Accordion title="리타겟팅 캠페인에서 앱 삭제 제외">

일부 경우에는 GDPR 및 CCPA와 같은 규제를 준수하기 위해 앱을 삭제한 사용자를 리타겟팅 캠페인에서 제외해야 할 수 있습니다. 앱 삭제 정보는 제외 목록을 만들고, 고객의 개인정보 및 데이터를 보호하는 조치를 취할 수 있게 합니다.

사용자를 제외하는 방법은 다음과 같습니다:

* <Anchor target="_blank" href="/marketers/ko/docs/raw-data-reporting-overview#user-journey-report-availability">원시 데이터 리포트:</Anchor> 삭제된 사용자의 목록을 **앱 삭제** 리포트에서 가져와 제외 목록을 만드는 수동적인 메서드입니다.
* <Anchor target="_blank" href="/marketers/ko/docs/audiences-guide">앱스플라이어 오디언스:</Anchor> 특정 기준(예: 앱을 **삭제하지 않은** 사용자)으로 타겟 오디언스를 정의하는 자동 메서드입니다. 기준을 충족하지 않는 사용자는 오디언스에서 제외됩니다.

> 📄 **예시**
>
> 당신은 PlayIt Gaming International의 게임 앱 마케터입니다. 안드로이드 앱 중 하나에 대한 리타겟팅 캠페인을 운영 중이며, 앱스플라이어 오디언스를 사용해 리타겟팅 오디언스를 정의하기로 했습니다. 오디언스에 대한 기준은 다음과 같습니다:
>
> * 앱을 삭제하지 않은 사용자.
> * 최근 30일 이내에 앱을 실행하지 않은 사용자.
>
> 이렇게 하면 더 정확한 리타겟팅 오디언스를 만들 수 있습니다. 리타겟팅 캠페인이 실행되면, 광고는 정의된 리타겟팅 오디언스 내의 사용자에게만 게재됩니다.

</Accordion>

## 앱 삭제 측정 설정

앱 삭제 지표를 설정하려면 마케터와 개발자가 협력해야 합니다. 구현 지침은 앱이 운영되는 운영 체제에 따라 다릅니다.

마케터와 개발자의 흐름은 다음과 같습니다:

<Tabs>
<Tab title="안드로이드">

| 작업 | 책임자 |
| --- | --- |
| [Firebase 클라우드 메시징(FCM)을 앱스플라이어와 연결하기](/docs/measure-uninstalls#firebase-cloud-메시징을-앱스플라이어에-연결하기안드로이드) | 마케터 |
| [앱스플라이어에서 앱 삭제 측정 설정](/docs/measure-uninstalls#앱스플라이어에서-앱-삭제-측정-구성) | 마케터 |
| <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/uninstall-measurement">SDK와 연동하기</Anchor> | 안드로이드 개발자 |
| [앱 삭제 측정 시험](/docs/measure-uninstalls#앱-삭제-측정-시험하기) | 마케터 |
| [선택 사항] 대시보드에서 관련 파트너에게 [앱 삭제 이벤트 매핑](/docs/measure-uninstalls#앱-삭제-이벤트-매핑) | 마케터 |

</Tab>

<Tab title="iOS">

| 작업 | 책임자 |
| --- | --- |
| <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/uninstall-measurement-ios#creating-a-p12-certificate">P12 인증서 생성</Anchor> | iOS 개발자 |
| [앱스플라이어에서 앱 삭제 측정 설정](/docs/measure-uninstalls#앱스플라이어에서-앱-삭제-측정-구성) | 마케터 |
| <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/uninstall-measurement">SDK와 연동하기</Anchor> | iOS 개발자 |
| [앱 삭제 측정 시험](/docs/measure-uninstalls#앱-삭제-측정-시험하기) | 마케터 |
| [선택 사항] 대시보드에서 관련 파트너에게 [앱 삭제 이벤트 매핑](/docs/measure-uninstalls#앱-삭제-이벤트-매핑) | 마케터 |

</Tab>
</Tabs>

## 구현 절차

구현에는 모바일 개발자가 푸시 알림에 대응할 수 있는 메커니즘을 앱에 연동하기 위한 작업이 필요합니다. 구현 지침은 운영 체제에 따라 다릅니다.

### Firebase Cloud 메시징을 앱스플라이어에 연결하기(안드로이드)

안드로이드 앱 삭제 측정은 앱스플라이어에서 앱 삭제 측정을 설정하고 귀사의 앱에 Firebase Cloud 메시징(FCM)을 도입하여 사용할 수 있습니다.

<div id="http-v1" />

<Accordion title="HTTP V1">

**앱 삭제를 위해 FCM HTTP V1을 설정하려면:**

1. **프로젝트 ID를 얻으려면**:
   1. FCM <Anchor target="_blank" href="https://console.firebase.google.com/">콘솔로 이동합니다.</Anchor>
   2. 프로젝트를 선택하세요.
   3. **프로젝트 개요** > **프로젝트 설정으로 이동합니다.**

      ![UninstallFirebase.png](https://files.readme.io/15e74e10daa2f1f1d872f0c8fea274c9819c52c4655baa903728257dd6337e80-33839423254289.png)
   4. 프로젝트 ID를 복사하세요. 이는 나중에 필요합니다.
2. FCM API를 활성화하려면:
   1. **클라우드 메시징 탭**으로 이동합니다.
   2. Firebase Cloud 메시징 API (V1)가 **활성화되어 있는지 확인하세요.**
3. **앱스플라이어에 앱 삭제 역할을 할당하려면:**
   1. **서비스 계정** 탭으로 이동합니다.
   2. **서비스 계정 권한 관리**를 클릭합니다.   
      Google Cloud 플랫폼에서 새 브라우저 탭이 열립니다.
   3. 사이드 메뉴에서 **역할**을 선택합니다.
   4. **+역할 만들기**를 클릭합니다.
   5. 다음과 같이 완료하세요.
      * 제목: **앱스플라이어 앱 삭제**를 입력합니다.
      * ID: `af_uninstalls`을 입력하세요.
      * 역할 시작 단계: **일반 출시**를 선택하세요.
   6. **권한 추가**를 클릭합니다.
   7. In <Image alt="adjusted.png" src="https://files.readme.io/c9fc0c6358ff89e1004ac1ab348a4b286d58c8a5cbe024aeb5c637136f3a67ac-33839382508049.png" width="20px" /> **필터**에서 **cloudmessaging.messages.create** 권한을 선택합니다.

      [altalt](https://support.appsflyer.com/hc/article_attachments/30448138892817)
   8. **추가**를 클릭한 다음 **만들기**를 클릭합니다.
4. **앱스플라이어에 FCM 앱 삭제 역할을 할당하려면:**
   1. 사이드 메뉴에서 **IAM**을 선택합니다.
   2. 권한 -> 주체별 뷰 탭을 엽니다.
   3. 액세스 권한 **부여를 클릭합니다.**
   4. 주체 추가 -> 새 주체에 **af-uninstalls-tracking@af-uninstalls-tracking.iam.gserviceaccount.com**을 입력합니다.
   5. 역할 할당 -> 역할에서 생성한 커스텀 역할 **앱스플라이어 앱 삭제**를 선택합니다.
   6. 저장**을 클릭**합니다.   
      앱스플라이어 서비스 계정에 앱스플라이어 앱 삭제 역할이 지정되었습니다.

      > 📘 **참고**
      >
      > 앱스플라이어는 무음 푸시 알림을 오직 앱 삭제 측정이나 비활성 사용자 식별에만 사용하며 다른 목적으로는 사용하지 않습니다.


</Accordion>

<div id="legacy-http" />

<Accordion title="[중단됨] 기존 HTTP">

> 🚧 **중요!**
>
> HTTP 기존 API는 2023년 6월 20일에 Firebase에서 지원이 중단되었으며, 2024년 6월 21일에 삭제될 예정입니다. 기존 API를 사용 중인 경우 [HTTP v1 API](/docs/measure-uninstalls#http-v1) 사용을 적극 권장합니다. <Anchor target="_blank" href="https://firebase.google.com/docs/cloud-messaging/http-server-ref">더 보기</Anchor>

Firebase 메시징을 사용한 앱 삭제 측정은 안드로이드 SDK V4.7.0 이상에서 지원됩니다.

**Firebase 서버 키를 얻으려면:**

1. Firebase 안드로이드 애플리케이션 프로젝트를 만드세요 (아직 만들지 않았다면), 또는 **Google 개발자 콘솔**에서 프로젝트를 마이그레이션하세요 (콘솔의 지침을 따르세요). 자세한 내용은 <Anchor target="_blank" href="https://firebase.google.com/docs/cloud-messaging/android/client">Firebase</Anchor>를 참조하세요.
2. Firebase <Anchor target="_blank" href="https://console.firebase.google.com">콘솔</Anchor>을 엽니다.
3. Firebase 콘솔에서 프로젝트 설정으로 이동합니다 (페이지 왼쪽 창의 프로젝트 개요 옆에 있는 톱니바퀴 아이콘을 클릭하세요).  

   ![firebase_cloud_messaging_server_key.png](https://files.readme.io/4e31c02a1bea013c823b0148ba1704d4492f66d04e23f0e13e00a9c0c22d286c-33839382513041.png)
4. 클라우드 메시징 탭에서 두 개의 서버 키를 볼 수 있습니다.
5. **서버 키**를 복사하세요.

</Accordion>

### 앱스플라이어에서 앱 삭제 측정 구성

<Tabs>
<Tab title="안드로이드">

**필수 조건**: 안드로이드 개발자가 <Anchor target="_blank" href="https://dev.appsflyer.com/hc/docs/uninstall-measurement">연동 지침</Anchor>을 완료해야 합니다.

**앱스플라이어에서 앱 삭제 측정을 구성하려면**:

1. 앱스플라이어의 측면 메뉴**에서** 설정 **>** 앱 설정을 선택합니다.
2. 필요한 경우 **앱 삭제 측정**을 켜세요.
3. Select **HTTP V1을 선택하고 준비한 프로젝트 ID를 입력하세요.**

   ![UninstallHTTPV1.png](https://files.readme.io/80d13e47ea7ae1585d2ecc0e2f7210572e47dba936557c8e96314e49b0d738d8-33839423258641.png)
4. **연결 테스트**를 클릭하세요.  
   성공 메시지가 표시됩니다.
5. **설정 저장**을 클릭합니다.

</Tab>

<Tab title="iOS">

**필수 조건: iOS 개발자는 연동 지침을 완료해야 합니다.**

**앱스플라이어에서 앱 삭제 측정을 구성하려면:**

1. 귀사의 개발자로부터 P12 파일을 받으세요.
2. 앱스플라이어의 측면 메뉴**에서** 설정 **>** 앱 설정을 선택합니다.
3. 아래로 스크롤하여 앱 삭제 섹션을 찾으세요.
4. 앱 삭제 측정`<g1>`}을 켭니다.

   ![Uninstall_iOS_p2.png](https://files.readme.io/3f9de3ebe6099886fa9bc210bd6e491ba91e8ff2c890c980f66c4d48398a597c-33839423260561.png)
5. 업로드 아이콘을 클릭하고 P12 파일을 선택하세요.
6. [선택 사항] P12 인증서가 비밀번호로 보호된 경우 비밀번호를 입력하세요.
7. **검증을 클릭하여 인증서를 앱스플라이어로 발송하고 검증을 받으세요.**
8. 설정 **저장**을 클릭합니다.

</Tab>
</Tabs>

## 앱 삭제 측정 시험하기

구현 절차가 완료된 후, 앱을 설치했다가 삭제하여 앱 삭제 기록이 올바르게 되는지 시험할 수 있습니다. 앱 삭제와 삭제율은 개요 대시보드에 표시됩니다.

<Tabs>
<Tab title="안드로이드">

다음의 앱에서 이 시험을 수행할 수 있습니다:

* 구글 플레이 스토어에서
* 보류 중(구글 플레이 스토어에 나열되지 않음)
* 직접 다운로드를 통해 사용 가능
* 대체 앱 스토어에서

안드로이드 앱을 시험할 때 다음 사항을 유의하세요.

* 앱 삭제 측정은 <Anchor target="_blank" href="/marketers/ko/docs/about-data-freshness-and-timezone-support#uninstalls">매일</Anchor> 처리됩니다. 앱 삭제 이벤트는 24시간 이내에 등록되지만, 이 기간 동안 앱을 다시 설치하면 이벤트가 기록되지 않습니다.
* **앱 삭제 이벤트는** 로데이터 리포트 <Anchor target="_blank" href="/marketers/ko/docs/raw-data-reporting-overview">및 앱스플라이어 대시보드(데이터 집약형 성과 리포트)에 표시되기까지 최대 48시간이 걸립니다.</Anchor>

</Tab>

<Tab title="iOS">

iOS 앱을 시험할 때 다음 사항을 유의하세요.

* 앱 삭제는 앱스플라이어 대시보드에 즉시 표시되지 않습니다. Apple 푸시 알림 서비스로 인해, 대시보드에 삭제 사항이 나타나기까지 걸리는 시간은 최소 9일입니다. 앱스플라이어는 매일 앱 삭제에 대한 지표를 업데이트하고 집계합니다.

  <div id="h_01HB8CXQ49QN0PH138V2PD2QXE" />

  > 📄 **예시**
  >
  > * 1일차: 사용자가 귀사의 앱을 인스톨합니다.
  > * 4일차: 사용자가 귀사의 앱을 삭제합니다.
  > * 12일차: Apple 푸시 알림 서비스는 앱 삭제 후 8일째에 앱 삭제를 보고합니다.
  > * 13일차: 앱 삭제 데이터는 앱스플라이어 대시보드와 로데이터에 나타납니다.

* 앱의 시험 버전에서 시험을 수행할 경우, 샌드박스 환경을 사용하고 있는지 확인하세요. [앱 삭제 샌드박스 절차에 대한 개발자 지침을 참조하세요.](https://dev.appsflyer.com/hc/docs/uninstall-measurement-ios#testing-uninstall-measurement)

</Tab>
</Tabs>

## 앱 삭제 이벤트 매핑

![앱삭제_이벤트_포스트백.png](https://files.readme.io/9c3c7f3fd330720d4f6f41fdf509c5af00d042291c1350ab83a1951464ac8e8f-33839423261713.png)

애드 네트워크와 앱 삭제 데이터를 공유하려면 <Anchor target="_blank" href="/marketers/ko/docs/set-up-an-integrated-partner#g-in-app-event-postback-configuration">af\_uninstall 이벤트</Anchor>를 파트너와 매핑해야 합니다. 일반 인앱 이벤트에 대한 포스트백과 달리, 앱 삭제 이벤트는 실시간으로 전송되지 않습니다. 보고된 이벤트 시간은 앱스플라이어가 앱이 삭제되었다고 판단한 시간을 나타내며, 실제 앱 삭제 시간을 나타내지 않습니다.

다음 사항을 유의하세요.

* 앱스플라이어가 이벤트가 실제로 발생하고 기록될 때만 포스트백을 발송할 수 있습니다.
* 대시보드의 개요 페이지나 원시 데이터 리포트에서 앱 삭제가 보이지 않는다면, 이는 **af\_uninstall** 이벤트가 매핑되어 있더라도 파트너에게 앱 삭제 포스트백이 전송되지 않았음을 의미합니다.

#### 제한 사항

* 인앱 이벤트 포스트백 리포트에는 앱 삭제 이벤트가 포함되지 않습니다.
* **af\_uninstall** 이벤트는 모든 파트너가 지원합니다. 이벤트를 파트너와 매핑하고자 하나 파트너의 연동 탭에서 이벤트가 보이지 않는 경우, 귀사의 CSM에게 문의하거나 [hello@appsflyer.com](mailto:hello@appsflyer.com)으로 연락하세요.

## 앱 삭제 측정 해제

<Tabs>
<Tab title="안드로이드">

Firebase/GCM 서버 키가 제공되면 앱 삭제 측정이 기본적으로 활성화됩니다. 앱 소유자는 대시보드를 통해 이 기능을 비활성화할 수 있습니다.

</Tab>

<Tab title="iOS">

P12 인증서가 제공되고 검증되면 앱 삭제 측정이 기본적으로 활성화됩니다. 앱 소유자는 대시보드를 통해 이 기능을 비활성화할 수 있습니다.

</Tab>
</Tabs>

**참고:** 앱 삭제가 보고되려면, 앱 설치 시 **앱 삭제 측정 사용**이 켜져 있어야 합니다. **앱 삭제 측정 사용**이 꺼져 있을 때 발생한 인스톨은 보고되지 않습니다.

#### **앱 삭제 측정을 끄려면**:

1. 앱스플라이어의 측면 메뉴**에서** 설정 **>** 앱 설정을 선택합니다.
2. **어트리뷰션** > **앱 삭제 측정**로 이동하여 **앱 삭제 측정 사용**을 끕니다.

<div id="traits-and-limitations" />

<Accordion title="특징 및 제약 사항">

| 특징 | 비고 |
| --- | --- |
| CUID | CUID는 앱 삭제 포스트백에서 전송되지 않습니다. |

</Accordion>

<div data-zendesk-anchors="overview=%EA%B0%9C%EC%9A%94 h_01HB8CXQ4824V2WEPYGK8YS4DC=%EA%B0%9C%EC%9A%94 how-does-it-work=%EC%96%B4%EB%96%BB%EA%B2%8C-%EC%9E%91%EB%8F%99%ED%95%98%EB%82%98%EC%9A%94 h_01HB8CXQ48JEJECC1HR79DXCRK=%EC%96%B4%EB%96%BB%EA%B2%8C-%EC%9E%91%EB%8F%99%ED%95%98%EB%82%98%EC%9A%94 h_01HK25HB9SYTZY759VRMZMF3YY=%EC%B0%B8%EA%B3%A0 how-to-use-uninstall-data=%EC%95%B1-%EC%82%AD%EC%A0%9C-%EB%8D%B0%EC%9D%B4%ED%84%B0-%ED%99%9C%EC%9A%A9-%EB%B0%A9%EB%B2%95 h_01HB8CXQ48E2SRN95MH4E2H7ZH=%EC%95%B1-%EC%82%AD%EC%A0%9C-%EB%8D%B0%EC%9D%B4%ED%84%B0-%ED%99%9C%EC%9A%A9-%EB%B0%A9%EB%B2%95 h_01HB8CXQ48HX9RH50G45FZMZTK=compare-the-quality-of-sources h_01HB8CXQ48DZYQW7FYBD3XYREM=%EC%98%88%EC%8B%9C h_01HB8CXQ488E22GPCEBE69VQ3M=share-uninstall-data-with-ad-networks-for-optimization h_01HB8CXQ48ZE5TTZRPQE5SEKJS=%EC%98%88%EC%8B%9C-1 h_01HB8CXQ48JTET73GH0QQBX5HF=exclude-uninstalls-from-retargeting-campaigns h_01HB8CXQ4832ZHRYQECYCQPP66=%EC%98%88%EC%8B%9C-2 setting-up-uninstall-measurement=%EC%95%B1-%EC%82%AD%EC%A0%9C-%EC%B8%A1%EC%A0%95-%EC%84%A4%EC%A0%95 h_01HB8CXQ4810HTB45FAS5ZVRHF=%EC%95%B1-%EC%82%AD%EC%A0%9C-%EC%B8%A1%EC%A0%95-%EC%84%A4%EC%A0%95 implementation-procedures=%EA%B5%AC%ED%98%84-%EC%A0%88%EC%B0%A8 h_01HB8CXQ489HRF72VRZ4G532GX=%EA%B5%AC%ED%98%84-%EC%A0%88%EC%B0%A8 connect-firebase-cloud-messaging-to-appsflyer-android=firebase-cloud-%EB%A9%94%EC%8B%9C%EC%A7%95%EC%9D%84-%EC%95%B1%EC%8A%A4%ED%94%8C%EB%9D%BC%EC%9D%B4%EC%96%B4%EC%97%90-%EC%97%B0%EA%B2%B0%ED%95%98%EA%B8%B0%EC%95%88%EB%93%9C%EB%A1%9C%EC%9D%B4%EB%93%9C h_01HB8CXQ48ZD5Y0RKTG1W51TKW=firebase-cloud-%EB%A9%94%EC%8B%9C%EC%A7%95%EC%9D%84-%EC%95%B1%EC%8A%A4%ED%94%8C%EB%9D%BC%EC%9D%B4%EC%96%B4%EC%97%90-%EC%97%B0%EA%B2%B0%ED%95%98%EA%B8%B0%EC%95%88%EB%93%9C%EB%A1%9C%EC%9D%B4%EB%93%9C h_01HB8CXQ4865MNVG0VERSNSE3F=http-v1 h_01J14PAAGZ60Y8SHH0PNT8SSXS=%EC%B0%B8%EA%B3%A0-1 h_01HB8CXQ48H079WQ6Q6G0XSQC7=legacy-http h_01HB8CXQ48ENMG65YH5ECGST9Z=%EC%A4%91%EC%9A%94 configure-uninstall-measurement-in-appsflyer=%EC%95%B1%EC%8A%A4%ED%94%8C%EB%9D%BC%EC%9D%B4%EC%96%B4%EC%97%90%EC%84%9C-%EC%95%B1-%EC%82%AD%EC%A0%9C-%EC%B8%A1%EC%A0%95-%EA%B5%AC%EC%84%B1 h_01HB8CXQ48CVA9B8B78W0H357C=%EC%95%B1%EC%8A%A4%ED%94%8C%EB%9D%BC%EC%9D%B4%EC%96%B4%EC%97%90%EC%84%9C-%EC%95%B1-%EC%82%AD%EC%A0%9C-%EC%B8%A1%EC%A0%95-%EA%B5%AC%EC%84%B1 testing-uninstall-measurement=%EC%95%B1-%EC%82%AD%EC%A0%9C-%EC%B8%A1%EC%A0%95-%EC%8B%9C%ED%97%98%ED%95%98%EA%B8%B0 h_01HB8CXQ48SW2TT5Z85XD3XWT6=%EC%95%B1-%EC%82%AD%EC%A0%9C-%EC%B8%A1%EC%A0%95-%EC%8B%9C%ED%97%98%ED%95%98%EA%B8%B0 mapping-the-uninstall-event=%EC%95%B1-%EC%82%AD%EC%A0%9C-%EC%9D%B4%EB%B2%A4%ED%8A%B8-%EB%A7%A4%ED%95%91 h_01HB8CXQ499ABX9ZGDFB1VAE8W=%EC%95%B1-%EC%82%AD%EC%A0%9C-%EC%9D%B4%EB%B2%A4%ED%8A%B8-%EB%A7%A4%ED%95%91 limitations=%EC%A0%9C%ED%95%9C-%EC%82%AC%ED%95%AD h_01HB8CXQ49F2ARQTEV8Q032P9V=%EC%A0%9C%ED%95%9C-%EC%82%AC%ED%95%AD turning-off-uninstall-measurement=%EC%95%B1-%EC%82%AD%EC%A0%9C-%EC%B8%A1%EC%A0%95-%ED%95%B4%EC%A0%9C h_01HB8CXQ49Y5NCG7GK93HXHYMD=%EC%95%B1-%EC%82%AD%EC%A0%9C-%EC%B8%A1%EC%A0%95-%ED%95%B4%EC%A0%9C to-turn-off-uninstall-measurement=%EC%95%B1-%EC%82%AD%EC%A0%9C-%EC%B8%A1%EC%A0%95%EC%9D%84-%EB%81%84%EB%A0%A4%EB%A9%B4 h_01HB8CXQ49WXZS4M6CK5XG1BCX=%EC%95%B1-%EC%82%AD%EC%A0%9C-%EC%B8%A1%EC%A0%95%EC%9D%84-%EB%81%84%EB%A0%A4%EB%A9%B4 h_01HB8CXQ4916CJ9NDZWGWQHKSA=traits-and-limitations" />
