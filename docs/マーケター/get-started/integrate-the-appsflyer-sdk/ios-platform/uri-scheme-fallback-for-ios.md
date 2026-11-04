---
title: iOSでのURIスキームによる代替起動
metadata:
  keywords:
    - Advertisers
    - Redirects
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
  created_at: '2017-05-10T12:50:00Z'
  edited_at: '2026-10-28T09:11:38Z'
  id: 115002366466
  locale: ja
  section: iOS platform
  section_id: 6551263106577
  url: https://support.appsflyer.com/hc/ja/articles/115002366466
---
> **概要：** iOSデバイスのユーザーがOneLinkカスタムリンクをクリックしても、Universal Linksでアプリが開かない場合の動作を説明します。

<div id="about-uri-fallback-for-ios" />

## iOSでのURIスキームによる代替起動について

* iOSデバイスでアプリを開く方法として、最も広くサポートされているのはUniversal Linksです。 2016年以降、iOSのUniversal Linksでアプリが開かない場合に、URIスキームで代わりに起動する方法には、OS自体による大きな制限があります。これらはAppsFlyerに起因する制限ではなく、URIスキームでアプリを開く他のリンクにも影響します。
* デフォルトでは、URIスキーム（af\_dpパラメータの値として指定）は、一部のブラウザやプラットフォームでのみ、iOSアプリの代替起動に使用されます。
* Safariでは、OneLink URLに次のパラメータを設定することで、URIスキームによるiOSアプリの代替起動を試すことができます。 
  * `af_dp`：値としてURIスキームを指定します。
  * `af_force_deeplink=true`：af\_dpに指定したURIスキームでアプリを強制的に開きます。このパラメータがない場合、URIスキームでアプリは開きません。
* その他のブラウザでは、URIスキームの動作が安定しないため、デフォルトではサポートされていません。リンクをクリックしたユーザーは、App Storeにリダイレクトされる可能性が高くなります（`af_ios_url`パラメータが設定されている場合は、そのURLにリダイレクトされます）。
* 詳しくは、以下のシナリオ別のフローチャートとケース別の動作を参照してください。

<div id="note" />

> 📘 **注意**
>
> X（Twitter）はURIスキームをサポートしていません。アプリが起動しない問題を避けるため、Universal Linksを設定したソーシャルアプリ向けランディングページ（SALP）の使用を推奨します。

<div id="scenarios-flowchart" />

### シナリオ別のフローチャート

<Image alt="flowchartdoctored.png" src="https://files.readme.io/5917ad4d8a01010db16eb16dd4c9a5beca02e80797ec9d47999772a8d4433401-41284711408529.png" width="1564px" />

<div id="use-cases" />

## ケース別の動作

<div id="browsers-that-can-use-uri-schemes-by-default" />

<Accordion title="デフォルトでURIスキームを使用できるブラウザ">

アプリがインストールされていない場合や、リンクにUniversal Linksが設定されていない場合など、Universal Linksでアプリが開かないことがあります。このような場合、次のブラウザやプラットフォームでは、デフォルトでURIスキームを使用してアプリを代わりに起動できます。

* Chrome
* Kakaotalk
* Naver
* Naver-Blog
* Weibo

<div id="flowchart" />

#### **フローチャート**

<Image alt="use case flowchart.png" src="https://files.readme.io/9b68ccc634b55d72a9be8f8b07d9744214a10b2f14f11bf97416fcb377b28963-41284872656401.png" width="75.41%" />

</Accordion>

<div id="safari" />

<Accordion title="Safari">

Universal Linksでアプリが開かず、リンクに`af_dp`（値としてURIスキームを指定）が含まれている場合の動作は、次のとおりです。

**アプリがインストールされていない場合：**

1. Safariに「アドレスが無効なため、Safariはページを開けません」というエラーメッセージのダイアログが表示されます。  
   [![](https://files.readme.io/d6b44169a7005fe7068b0692f71fac58bdd16bdca1424eb0a25499511c375caa-360016139237.jpg)](https://files.readme.io/d6b44169a7005fe7068b0692f71fac58bdd16bdca1424eb0a25499511c375caa-360016139237.jpg)
2. ユーザーが<strong>［OK］</strong>をクリックしてダイアログを閉じると、背後でランディングページが読み込まれる様子が一瞬表示されます。その後、1秒以内にApp Store、またはaf\_ios\_urlパラメータで指定したURLに自動的にリダイレクトされます。

**アプリがインストールされている場合：**

* リンクに`af_force_deeplink=true`が含まれていない場合、ユーザーはApp Store、またはaf\_ios\_urlパラメータで指定したURLにリダイレクトされます。
* リンクに`af_force_deeplink=true`が含まれている場合：
  1. Safariのダイアログが表示されます。  
     [![](https://files.readme.io/0f56dfa3c0c9ea65c1d28f7bb4ebc9a1b3fa25ec1a7e8e620dc013b869012386-360016209978.jpg)](https://files.readme.io/0f56dfa3c0c9ea65c1d28f7bb4ebc9a1b3fa25ec1a7e8e620dc013b869012386-360016209978.jpg)
  2. ユーザーが<strong>［開く］</strong>をクリックすると、アプリが開きます。
  3. ユーザーが<strong>［キャンセル］</strong>をクリックした場合：
     * af\_ios\_urlパラメータが設定されている場合、ユーザーは指定したURLにリダイレクトされます。
     * af\_ios\_urlパラメータが設定されていない場合、ランディングページの上にSafariのエラーメッセージのダイアログが表示され、「アドレスが無効なため、Safariはページを開けません」と表示されます。  
       [![](https://files.readme.io/d6b44169a7005fe7068b0692f71fac58bdd16bdca1424eb0a25499511c375caa-360016139237.jpg)](https://files.readme.io/d6b44169a7005fe7068b0692f71fac58bdd16bdca1424eb0a25499511c375caa-360016139237.jpg)
  4. ユーザーが<strong>［OK］</strong>をクリックすると、操作を促すボタン（CTA）があるランディングページが表示されます。
  5. ユーザーがCTAボタンをクリックすると、ダイアログが表示されます。  
     [![](https://files.readme.io/0f56dfa3c0c9ea65c1d28f7bb4ebc9a1b3fa25ec1a7e8e620dc013b869012386-360016209978.jpg)](https://files.readme.io/0f56dfa3c0c9ea65c1d28f7bb4ebc9a1b3fa25ec1a7e8e620dc013b869012386-360016209978.jpg)
  6. ユーザーが<strong>［開く］</strong>をクリックすると、アプリが開きます。
  7. ユーザーが<strong>［キャンセル］</strong>をクリックすると、ダイアログが表示されます。  
     [![](https://files.readme.io/dd3aa8492bdf1883246bd740118e1b8d2f075a77a164e3ad55843f7c4d44d2b9-360016210038.jpg)](https://files.readme.io/dd3aa8492bdf1883246bd740118e1b8d2f075a77a164e3ad55843f7c4d44d2b9-360016210038.jpg)
  8. ユーザーが<strong>［OK］</strong>をクリックすると、App Storeにリダイレクトされます。
  9. ユーザーが<strong>［キャンセル］</strong>をクリックすると、ランディングページにとどまります。

<div id="flowchart-1" />

#### **フローチャート**

![Copy_of_Ios_fall_back_-_safari.png](https://files.readme.io/5e50eb558b23a849f02e1ffe5df3181ad7c8d9514f5813fbffcfa6160493de81-360016515318.png)

</Accordion>

<div id="facebook-post-unpaid" />

<Accordion title="Facebookの通常投稿（広告以外）">

Universal Linksでアプリが開かず、リンクに`af_dp`（値としてURIスキームを指定）が含まれている場合の動作は、次のとおりです。

**アプリがインストールされている場合：**

* アプリが開きます。

**アプリがインストールされていない場合：**

1. ソーシャルメディアアプリが設定されていない場合、またはユーザーがSALP上のCTAボタンをクリックした後、ランディングページの上にダイアログが表示されます。  
   [![](https://files.readme.io/200a0baef3755ab58c5385dac5fcb00ae3d72e762fbaa571c1735f7222d3b0b9-360016599277.jpg)](https://files.readme.io/200a0baef3755ab58c5385dac5fcb00ae3d72e762fbaa571c1735f7222d3b0b9-360016599277.jpg)
2. ［アプリを開く］をクリックします。次のいずれかの動作になります。
   * `af_ios_url`パラメータが設定されている場合、ユーザーは指定したURLにリダイレクトされます。
   * `af_ios_url`パラメータが設定されておらず、リンクに`af_force_deeplink=true`も含まれていない場合、ユーザーは設定に応じてリダイレクトされます。
   * af\_ios\_urlパラメータが設定されておらず、リンクに`af_force_deeplink=true`が含まれている場合、ランディングページの上に再びダイアログが表示されます。  
     [![](https://files.readme.io/200a0baef3755ab58c5385dac5fcb00ae3d72e762fbaa571c1735f7222d3b0b9-360016599277.jpg)](https://files.readme.io/200a0baef3755ab58c5385dac5fcb00ae3d72e762fbaa571c1735f7222d3b0b9-360016599277.jpg)
3. ユーザーが<strong>［開く］</strong>をクリックすると、App Storeに移動します。
4. ユーザーが<strong>［閉じる］</strong>をクリックすると、背後にあったランディングページが表示されます。  
   [![](https://files.readme.io/98748f47f3f9df43addc9c871c8165ecf4f849b17bdcfd660b90d4b6ded6727d-360016668478.jpg)](https://files.readme.io/98748f47f3f9df43addc9c871c8165ecf4f849b17bdcfd660b90d4b6ded6727d-360016668478.jpg)
5. ユーザーがApp Storeのバッジをクリックすると、App Storeにリダイレクトされます。

<div id="flowchart-2" />

#### **フローチャート**

![diagram-X.png](https://files.readme.io/0c8040d27bbf34fdf1374b4b40a8239b6af7b6c7719db9666f36dd2829bc3217-small-17710399441553.png)

</Accordion>

<div data-zendesk-anchors="about-uri-fallback-for-ios=ios%E3%81%A7%E3%81%AEuri%E3%82%B9%E3%82%AD%E3%83%BC%E3%83%A0%E3%81%AB%E3%82%88%E3%82%8B%E4%BB%A3%E6%9B%BF%E8%B5%B7%E5%8B%95%E3%81%AB%E3%81%A4%E3%81%84%E3%81%A6 h_01HFV6PXS5401CCW6N2T04HGSM=ios%E3%81%A7%E3%81%AEuri%E3%82%B9%E3%82%AD%E3%83%BC%E3%83%A0%E3%81%AB%E3%82%88%E3%82%8B%E4%BB%A3%E6%9B%BF%E8%B5%B7%E5%8B%95%E3%81%AB%E3%81%A4%E3%81%84%E3%81%A6 h_01KAXQDBSG2YCPBDYYPFHBXR91=%E6%B3%A8%E6%84%8F scenarios-flowchart=%E3%82%B7%E3%83%8A%E3%83%AA%E3%82%AA%E5%88%A5%E3%81%AE%E3%83%95%E3%83%AD%E3%83%BC%E3%83%81%E3%83%A3%E3%83%BC%E3%83%88 h_01HFV6PXS5WWS0B1VYF7RJAV1J=%E3%82%B7%E3%83%8A%E3%83%AA%E3%82%AA%E5%88%A5%E3%81%AE%E3%83%95%E3%83%AD%E3%83%BC%E3%83%81%E3%83%A3%E3%83%BC%E3%83%88 use-cases=%E3%82%B1%E3%83%BC%E3%82%B9%E5%88%A5%E3%81%AE%E5%8B%95%E4%BD%9C h_01HFV6PXS51B2W497TADRGBX7Y=%E3%82%B1%E3%83%BC%E3%82%B9%E5%88%A5%E3%81%AE%E5%8B%95%E4%BD%9C h_01HFV6PXS5HE462CJEE18CM5ZR=browsers-that-can-use-uri-schemes-by-default flowchart=%E3%83%95%E3%83%AD%E3%83%BC%E3%83%81%E3%83%A3%E3%83%BC%E3%83%88 h_01HFV6PXS5N98MHJFYPSAB5XKZ=%E3%83%95%E3%83%AD%E3%83%BC%E3%83%81%E3%83%A3%E3%83%BC%E3%83%88 h_01HFV6PXS521E3MTCHJ5QBQGJ2=safari flowchart::db5f50ee=%E3%83%95%E3%83%AD%E3%83%BC%E3%83%81%E3%83%A3%E3%83%BC%E3%83%88-1 h_01HFV6PXS57ZRSX2WAECS69XB4=%E3%83%95%E3%83%AD%E3%83%BC%E3%83%81%E3%83%A3%E3%83%BC%E3%83%88-1 facebook-post%E2%80%94unpaid=facebook-post-unpaid h_01HFV6PXS5K8YZPE2B82V3DNTV=facebook-post-unpaid flowchart::df1b7de0=%E3%83%95%E3%83%AD%E3%83%BC%E3%83%81%E3%83%A3%E3%83%BC%E3%83%88-2 h_01HFV6PXS504YQRDHZ1S1WS8CV=%E3%83%95%E3%83%AD%E3%83%BC%E3%83%81%E3%83%A3%E3%83%BC%E3%83%88-2" />
