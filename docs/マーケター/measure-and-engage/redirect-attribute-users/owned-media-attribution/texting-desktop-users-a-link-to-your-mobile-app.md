---
title: デスクトップユーザーにモバイルアプリへのリンクをテキストで送信
metadata:
  keywords:
    - Advertisers
    - Developers
    - Marketers
    - QR-to-App
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-asaf-mashiah
    - Marketers
    - QR-to-App
  created_at: '2019-11-21T09:13:52Z'
  edited_at: '2026-10-14T09:32:26Z'
  id: 360003799658
  locale: ja
  section: Owned media attribution
  section_id: 6551214397585
  url: https://support.appsflyer.com/hc/ja/articles/360003799658
---
> **概要：**

![text-me-the-app-web-form.png](https://files.readme.io/d28b843ab7528138b4d85b147b8d613efde740d354238227b0f123030fa3a1de-360004940018.png)

## はじめに

## 要件



* <Anchor target="_blank" href="https://docs.aws.amazon.com/sns/latest/dg/sns-mobile-phone-number-as-subscriber.html"><span id="setting-up"></span>AWS SNS</Anchor>
* <Anchor target="_blank" href="https://www.braze.com/docs/user_guide/message_building_by_channel/sms/create/">Braze</Anchor>
* <Anchor target="_blank" href="https://www.airship.com/platform/channels/sms/">Airship</Anchor>
* [Swrve](https://docs.swrve.com/user-documentation/campaigns/campaign-channels/intro-to-sms/)
* <Anchor target="_blank" href="https://help.mixpanel.com/hc/en-us/articles/115004730066-Send-SMS-Messages-From-Mixpanel">Mixpanel</Anchor>





* <span id="a-backend-environment-to-communicate-with-the-sms-provider"></span>campaign: text-me-the-app





## ピープルベースドアトリビューション

詳細については<Anchor target="_blank" href="/marketers/ja/docs/people-based-attribution-pba-overview">こちら</Anchor>をご覧ください。

<div data-zendesk-anchors="introduction=%E3%81%AF%E3%81%98%E3%82%81%E3%81%AB requirements=%E8%A6%81%E4%BB%B6 sms-provider-account-to-text-a-link-to-the-app=setting-up a-multiplatform-custom-link=a-backend-environment-to-communicate-with-the-sms-provider texting-the-app-to-users=a-backend-environment-to-communicate-with-the-sms-provider create-a-multiplatform-onelink=a-backend-environment-to-communicate-with-the-sms-provider set-up-an-sms-topic-in-your-sms-provider-account=%E3%83%94%E3%83%BC%E3%83%97%E3%83%AB%E3%83%99%E3%83%BC%E3%82%B9%E3%83%89%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3 set-up-a-web-form-to-collect-phone-numbers=%E3%83%94%E3%83%BC%E3%83%97%E3%83%AB%E3%83%99%E3%83%BC%E3%82%B9%E3%83%89%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3 apply-logic-in-your-backend=%E3%83%94%E3%83%BC%E3%83%97%E3%83%AB%E3%83%99%E3%83%BC%E3%82%B9%E3%83%89%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3 how-attribution-works-when-sending-a-link-to-the-app=%E3%83%94%E3%83%BC%E3%83%97%E3%83%AB%E3%83%99%E3%83%BC%E3%82%B9%E3%83%89%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3 peoplebased-attribution=%E3%83%94%E3%83%BC%E3%83%97%E3%83%AB%E3%83%99%E3%83%BC%E3%82%B9%E3%83%89%E3%82%A2%E3%83%88%E3%83%AA%E3%83%93%E3%83%A5%E3%83%BC%E3%82%B7%E3%83%A7%E3%83%B3" />
