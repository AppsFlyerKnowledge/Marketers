---
title: Protect360｜導入ガイド
metadata:
  keywords:
    - Marketers
    - Protect360
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-yanai
    - Marketers
    - Protect360
  created_at: '2025-04-21T09:58:52Z'
  edited_at: '2026-10-28T08:58:43Z'
  id: 34554022072209
  locale: ja
  section: Protect your traffic
  section_id: 6551015912465
  url: https://support.appsflyer.com/hc/ja/articles/34554022072209
---
> **概要：** この段階的な導入ガイドに沿って進めることで、わずか6週間でProtect360の効果を最大限に引き出し、マーケティング投資を迅速かつ効果的に不正から守れます。

<div id="onboarding-timeline-and-what-to-expect" />

## **導入スケジュールと各段階で行うこと**

このガイドでは、6週間で段階的に導入を進める方法を説明します。

* **設定（1～3週目）**：Protect360を導入し、動作を検証します。
* **最適化（3～5週目）**：初期の分析結果に基づいて最適化します。
* **照合（5～6週目）**：広告パートナーと不正データを照合します。
* **高度な不正対策（6週目以降）［任意］**：高度な不正対策の機能を有効にします。

<div id="about-protect360" />

## **Protect360について**

Protect360は、広告不正の検知、防止、対処を行う高度な不正対策ソリューションです。 AIとリアルタイムの検知によって、不正のブロックや無駄な広告費の削減を支援します。クリックインジェクション（インストール直前に偽クリックを送信して成果を横取りする手法）、偽のインストール、ボットなどの脅威から、マーケティング活動を保護します。検証ルールやFraud Protection Studioなどの機能により、細かな設定と、不正対策の状況の明確な把握が可能です。

<div id="setup-weeks-1-3" />

<Accordion title="設定（1～3週目）">

この段階では、AppsFlyerへのアプリ内データの送信、不正対策の基本設定、BIツール（データ分析ツール）とAppsFlyerでの用語や意味の統一を行います。

**アプリ内イベントデータ**

AppsFlyerにアプリ内イベントデータを送信する方法は、SDKとサーバー間通信（S2S）の2つです。使用する方法に応じて、対応が必要な場合があります。

* **SDK**：対応は不要です。
* **サーバー間通信（S2S）**：API3経由でイベントが送信されていることを確認してください。<Anchor target="_blank" href="/marketers/ja/docs/bulletin-upgrading-the-appsflyer-s2s-api">詳しい手順はこちらをご覧ください。0></Anchor>

<div id="note" />

> 📘 **注意**
>
> 使用している方法が不明な場合は、開発チームまたはマーケティング運用チームに確認してください。

<div id="fraud-protection-studio-settings" />

#### **Fraud Protection Studioの設定**

Fraud Protection Studio（不正対策の設定・検証機能）では、AppsFlyerのさまざまな不正対策機能の影響と効果を検証できます。不正の検知と、ブロックなどの処理の適用を明確に区別できます。

適切に判断するには、この違いと選択できる設定を理解することが重要です。

* **適用**（デフォルト）：不正な活動をリアルタイムで自動的にブロックします。インストール後に検知した場合は、ポストアトリビューション不正としてマークします。不正に即座に対処することが目的に合っている場合に適しています。
* **タグ付け**：不正を検知してタグ付けしますが、アトリビューションは有効なまま維持します。自動的にブロックせずに、分析・確認できます。適用前に柔軟に設定し、詳しく分析したい場合に選択してください。

<div id="note-1" />

> 📘 **注意**
>
> ビジネス上の目的の変化に合わせて、いつでも**適用**と**タグ付け**を切り替えられます（<Anchor target="_blank" href="/marketers/ja/docs/user-management">管理者のみ</Anchor>）。<Anchor target="_blank" href="/marketers/ja/docs/beta-fraud-protection-studio#key-concepts">詳しくはこちら</Anchor>。

<Image alt="" src="https://files.readme.io/70bf87550e949fed4898270f731424e948a24f7cf2cff39e81ba44473af94189-35506628777105.png" width="624px" />

ヒント：チームがProtect360の使い方に慣れていくこの段階では、Fraud Protection Studioの<Anchor target="_blank" href="/marketers/ja/docs/beta-fraud-protection-studio#app-detection-evaluation">**アプリ単位の不正検知の検証**</Anchor>カードで、アプリ単位の設定をテストし、動作を理解することを強く推奨します。

<div id="data-connection-setup" />

#### **データ連携の設定**

Protect360のデータは、<Anchor target="_blank" href="/marketers/ja/docs/protect360-raw-data-reports#protect360ローデータレポートについて">ローデータレポート</Anchor>、<Anchor target="_blank" href="/marketers/ja/docs/protect360-raw-data-reports#pull-api">Pull API</Anchor>、<Anchor target="_blank" href="/marketers/ja/docs/protect360-raw-data-reports#data-locker">Data Locker</Anchor>の3つの方法で出力できます。どの方法でも、不正データを正確にレポートし、効果的に分析するためには、データ連携を適切に設定することが重要です。

<Image alt="" src="https://files.readme.io/d6a96db3fd8ffd3ed6f3f8abb680b4f3778a457142166d69e1ade7fe3263709e-35506660373393.png" width="624px" />

<div id="important" />

> 🚧 **重要**
>
> Protect360の効果を十分に得るため、毎月8日に<Anchor target="_blank" href="/marketers/ja/docs/protect360-raw-data-reports#postattribution-reports">ポストアトリビューションレポート</Anchor>を出力し、パートナーと改めて照合してください。

<div id="how-to-display-hijacked-installs-correctly-in-your-bi" />

#### **BIツールでハイジャックされたインストールを正しく表示する方法**

自社システムで不正対策データの整合性を高め、より詳しく把握するには、**ローデータレポート、Pull API、Data Lockerを使い、ハイジャックされたインストールをBIツールで正しく表示してください。**

<div id="raw-data-report" />

#### **ローデータレポート**

BIツールでハイジャックされたインストールを正しく表示するには：

1. **Rejected Reason Value**フィールドを確認します。
2. このフィールドには、次のいずれかが入力されます。
   1. 空欄、organic、contributor1、contributor2など。
3. 各値の意味をBI担当チームに共有し、用語とデータの解釈を統一してください。

* 空欄：ハイジャックされていません。
* Organic：アトリビューションをオーガニックに変更します。
* Contributor1、contributor2、contributor3など：指定されたメディアソースにアトリビューションを修正します。

<div id="note-2" />

> 📘 **注意**
>
> されたデータを詳しく確認するには、次の4つのローデータレポートを利用できます。
>
> * タグ付けされたインストール
> * ポストアトリビューションでタグ付けされたインストール
> * タグ付けされたアプリ内イベント
> * ポストアトリビューションでタグ付けされたアプリ内イベント

![](https://files.readme.io/70d33b5c4359f839da8d46c4b07baf277148fc4d5c6ebc7a3e8b2d600bd7c5fc-35506628785169.png)

#### **Pull API**

BIツールでハイジャックされたインストールを正しく表示するには：

4. **Rejected Reason Value**フィールドを確認します。
5. このフィールドには、次のいずれかが入力されます。
   1. 空欄、organic、contributor1、contributor2など。
6. 各値の意味をBI担当チームに共有し、用語とデータの解釈を統一してください。

* 空欄：ハイジャックされていません。
* Organic：アトリビューションをオーガニックに修正します。
* Contributor1、contributor2、contributor3など：指定されたメディアソースにアトリビューションを修正します。

#### **Data Locker**

BIツールでハイジャックされたインストールを正しく表示するには：

7. **validation\_reason\_value**フィールドを確認します。
8. このフィールドには、次のいずれかが入力されます。
   1. 空欄、organic、contributor1、contributor2など。
9. 各値の意味をBI担当チームに共有し、用語とデータの解釈を統一してください。

* 空欄：ハイジャックされていません。
* Organic：アトリビューションをオーガニックに修正します。
* Contributor1、contributor2、contributor3など：指定されたメディアソースにアトリビューションを修正します。

<div id="validation-rules" />

#### **検証ルール**

検証ルールでは、マーケティング戦略に合わせた独自の判定条件を、不正対策に追加できます。さまざまなパラメータを使い、用途に応じて、有効または無効とみなすインストールの条件を定義できます。

業種に適した推奨方法については、カスタマーサクセスマネージャーまたはアカウントマネージャーにお問い合わせください。

<div id="note-3" />

> 📘 **注意**
>
> ルールの効果を最大限に高めるため、ユーザー獲得（UA）、マーケティング、広告出稿の戦略を見直し、施策の目的に合うインストールやアプリ内イベントの種類を確認してください。そのうえで、必要に応じて許可またはブロックすることを推奨します。例えば、国（地域）Xでアプリを宣伝していない場合、地域Xからの該当する活動を自動的にブロックするルールを作成できます。複数のルールを作成して、マーケティング戦略に合った不正対策を行えます。

<div id="working-with-dashboards" />

#### **ダッシュボードの利用**

<Anchor target="_blank" href="/marketers/ja/docs/protect360-dashboard">Protect360ダッシュボード</Anchor>では、不正データの概要を視覚的に確認できます。さらに詳しく調べることで、不正検知の内容と施策への影響を把握できます。

<Image alt="" src="https://files.readme.io/4717e1f00d832a9808ac6469d89bf3a87f6701afb24a47f3b4393e4e393111ee-35506628785809.png" width="624px" />

</Accordion>

<div id="optimization-weeks-3-5" />

<Accordion title="最適化（3～5週目）">

<div id="campaign-optimization" />

#### **キャンペーンの最適化**

この段階では、Protect360の効果を最大限に引き出すために、キャンペーンを最適化します。次の内容を確認してください。

* [推奨方法](/docs/protect360-onboarding-guide#推奨方法)を確認
* [不正対策の設定の見直し](/docs/protect360-onboarding-guide#不正対策の設定の見直し)

<div id="best-practices" />

#### 推奨方法

* リアルタイムとポストアトリビューションのデータを組み合わせ、ユーザーの質（継続率、アプリ内イベントなど）と不正の状況に基づいて、キャンペーンのパフォーマンスを評価します。
* site\_idまたはsubsite\_idに基づいて、キャンペーンを最適化します。
* パートナーごとの不正率と不正の種類を分析します。

<div id="review-your-fraud-protection-settings" />

#### 不正対策の設定の見直し

[Fraud Protection Studioの設定](/docs/protect360-onboarding-guide#fraud-protection-studioの設定)を見直し、現在の目的に合っていることを確認してください。

<div id="note-4" />

> 📘 **注意**
>
> されたインストールは、有効なインストールの一部として扱われます。**適用**モードに切り替えると、Protect360の検知に基づいてリアルタイムでブロックします。

</Accordion>

<div id="reconciliation-weeks-5-6" />

<Accordion title="照合（5～6週目）">

<div id="fraud-data-reconciliation" />

#### **不正データの照合**

Protect360を導入して数週間分の不正検知データが蓄積されたら、広告パートナーと不正の分析結果を照合します。

これは、キャンペーンのパフォーマンス、不正検知の方法、データの正確性について、パートナーと認識を合わせるための重要な段階です。

<Anchor target="_blank" href="/marketers/ja/docs/protect360-anti-fraud-guide#postattribution-detection">ポストアトリビューションのデータ</Anchor>をダウンロードし、広告パートナーと緊密に連携して、不正に関する指標を突き合わせてください。この照合により、データの差異を特定し、見解の相違を早めに解消し、状況を明確に共有できます。広告パートナーとの不正データの照合方法は、<Anchor target="_blank" href="/marketers/ja/docs/protect360-anti-fraud-guide#fraud-reconciliation-with-ad-networks">こちら</Anchor>をご覧ください。

</Accordion>

<div id="advanced-protection-setup-week-6--optional" />

<Accordion title="高度な不正対策の設定（6週目以降）［任意］">

#### **Advanced Security Module**

Advanced Security Module（高度なセキュリティ機能）は、Protect360をご利用のお客様専用の、トラフィック量の多いアプリ向けの機能です。 Android SDKに重要な保護機能を追加し、ネットワークリクエストをリアルタイムで検証することで、偽装されたインストールや不正に操作されたトラフィックをブロックします。

不正な情報を送信元で除外することで、アプリストアとのデータの差異を減らし、アトリビューションの正確性を高め、高度なサイバー不正からデータを守ります。

担当のカスタマーサクセスマネージャー（CSM）に連絡するか、`<hello@appsflyer.com>`にメールでお問い合わせください。

</Accordion>

<div data-zendesk-anchors="what-to-expect=%E5%B0%8E%E5%85%A5%E3%82%B9%E3%82%B1%E3%82%B8%E3%83%A5%E3%83%BC%E3%83%AB%E3%81%A8%E5%90%84%E6%AE%B5%E9%9A%8E%E3%81%A7%E8%A1%8C%E3%81%86%E3%81%93%E3%81%A8 h_01JSBWNSH94Q2FBXJ5JSB2JKQ6=%E5%B0%8E%E5%85%A5%E3%82%B9%E3%82%B1%E3%82%B8%E3%83%A5%E3%83%BC%E3%83%AB%E3%81%A8%E5%90%84%E6%AE%B5%E9%9A%8E%E3%81%A7%E8%A1%8C%E3%81%86%E3%81%93%E3%81%A8 about-protect360=protect360%E3%81%AB%E3%81%A4%E3%81%84%E3%81%A6 h_01JSBWNSHDZ8J3B70KYEG2T03X=protect360%E3%81%AB%E3%81%A4%E3%81%84%E3%81%A6 setup-weeks-1%E2%80%933=setup-weeks-1-3 h_01JSBWJJMHSF6YQ5PDEWE0YTN5=setup-weeks-1-3 h_01JVVK5Z1HWN0TXKZVNNGK1CBV=%E6%B3%A8%E6%84%8F fraud-protection-studio-settings=fraud-protection-studio%E3%81%AE%E8%A8%AD%E5%AE%9A h_01JSY4SNK5X23DBVD374FV12FG=fraud-protection-studio%E3%81%AE%E8%A8%AD%E5%AE%9A h_01JVVK5Z1HZAVV3ZEA1AM7KVAY=%E6%B3%A8%E6%84%8F-1 data-connection-setup=%E3%83%87%E3%83%BC%E3%82%BF%E9%80%A3%E6%90%BA%E3%81%AE%E8%A8%AD%E5%AE%9A h_01JSY4SNK57K77TBXZB92QPBKA=%E3%83%87%E3%83%BC%E3%82%BF%E9%80%A3%E6%90%BA%E3%81%AE%E8%A8%AD%E5%AE%9A h_01JVVK5Z1H0TZH02S76M7JRKWQ=%E9%87%8D%E8%A6%81 how-to-display-hijacked-installs-correctly-in-your-bi=bi%E3%83%84%E3%83%BC%E3%83%AB%E3%81%A7%E3%83%8F%E3%82%A4%E3%82%B8%E3%83%A3%E3%83%83%E3%82%AF%E3%81%95%E3%82%8C%E3%81%9F%E3%82%A4%E3%83%B3%E3%82%B9%E3%83%88%E3%83%BC%E3%83%AB%E3%82%92%E6%AD%A3%E3%81%97%E3%81%8F%E8%A1%A8%E7%A4%BA%E3%81%99%E3%82%8B%E6%96%B9%E6%B3%95 h_01JVVJBVB4FRATEHVZ2Q7EWC54=bi%E3%83%84%E3%83%BC%E3%83%AB%E3%81%A7%E3%83%8F%E3%82%A4%E3%82%B8%E3%83%A3%E3%83%83%E3%82%AF%E3%81%95%E3%82%8C%E3%81%9F%E3%82%A4%E3%83%B3%E3%82%B9%E3%83%88%E3%83%BC%E3%83%AB%E3%82%92%E6%AD%A3%E3%81%97%E3%81%8F%E8%A1%A8%E7%A4%BA%E3%81%99%E3%82%8B%E6%96%B9%E6%B3%95 raw-data-report=%E3%83%AD%E3%83%BC%E3%83%87%E3%83%BC%E3%82%BF%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88 h_01JWDAV3K7JF8ATZP88D4NQRW4=%E3%83%AD%E3%83%BC%E3%83%87%E3%83%BC%E3%82%BF%E3%83%AC%E3%83%9D%E3%83%BC%E3%83%88 h_01JVVK5Z1HB5AVVF3XV5Q9KNGA=%E6%B3%A8%E6%84%8F-2 h_01JWDAV8GC5N1859AD1PMEQXH9=pull-api h_01JWDAVEVDAJD47WQYY0FNSPE9=data-locker validation-rules=%E6%A4%9C%E8%A8%BC%E3%83%AB%E3%83%BC%E3%83%AB h_01JSY4SNK5HAG08PAJQEPB7MQ4=%E6%A4%9C%E8%A8%BC%E3%83%AB%E3%83%BC%E3%83%AB h_01JVVK5Z1H05XX8BXECMXAJ4J7=%E6%B3%A8%E6%84%8F-3 working-with-dashboards=%E3%83%80%E3%83%83%E3%82%B7%E3%83%A5%E3%83%9C%E3%83%BC%E3%83%89%E3%81%AE%E5%88%A9%E7%94%A8 h_01JSY4SNK50RHSQ95E1E2ZK068=%E3%83%80%E3%83%83%E3%82%B7%E3%83%A5%E3%83%9C%E3%83%BC%E3%83%89%E3%81%AE%E5%88%A9%E7%94%A8 optimization-weeks-3%E2%80%935=optimization-weeks-3-5 h_01JSBWJJMH4YW52GSBE6639BP4=optimization-weeks-3-5 campaign-optimization=%E3%82%AD%E3%83%A3%E3%83%B3%E3%83%9A%E3%83%BC%E3%83%B3%E3%81%AE%E6%9C%80%E9%81%A9%E5%8C%96 h_01JV255GGVBY8XGQS28F0QZRVH=%E3%82%AD%E3%83%A3%E3%83%B3%E3%83%9A%E3%83%BC%E3%83%B3%E3%81%AE%E6%9C%80%E9%81%A9%E5%8C%96 best-practices=%E6%8E%A8%E5%A5%A8%E6%96%B9%E6%B3%95 h_01JV6WFR7MN2X8KTN7RMTXQ5KX=%E6%8E%A8%E5%A5%A8%E6%96%B9%E6%B3%95 review-your-fraud-protection-settings=%E4%B8%8D%E6%AD%A3%E5%AF%BE%E7%AD%96%E3%81%AE%E8%A8%AD%E5%AE%9A%E3%81%AE%E8%A6%8B%E7%9B%B4%E3%81%97 h_01JV6WGDRP200GHN6MJNZJ5MQE=%E4%B8%8D%E6%AD%A3%E5%AF%BE%E7%AD%96%E3%81%AE%E8%A8%AD%E5%AE%9A%E3%81%AE%E8%A6%8B%E7%9B%B4%E3%81%97 h_01JVVK5Z1HXPM2G6HAMTYV7MY5=%E6%B3%A8%E6%84%8F-4 reconciliation-weeks-5%E2%80%936=reconciliation-weeks-5-6 h_01JSBWJJMH1481TJW2EQMF118Q=reconciliation-weeks-5-6 fraud-data-reconciliation=%E4%B8%8D%E6%AD%A3%E3%83%87%E3%83%BC%E3%82%BF%E3%81%AE%E7%85%A7%E5%90%88 h_01JV25RP3VAJBCEWWK2TEZFKB2=%E4%B8%8D%E6%AD%A3%E3%83%87%E3%83%BC%E3%82%BF%E3%81%AE%E7%85%A7%E5%90%88 advanced-protection-setup-week-6-%5Boptional%5D=advanced-protection-setup-week-6--optional h_01JSBWJJMHZQNYE1N0W2BSJ37X=advanced-protection-setup-week-6--optional h_01JV260Y9M3M6CC48854YHQ01S=advanced-security-module" />
