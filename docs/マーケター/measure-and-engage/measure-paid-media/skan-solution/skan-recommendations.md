---
title: SKANの推奨設定
metadata:
  keywords:
    - Marketers
    - SKAN
    - SKAdNetwork
    - SKAdNetwork (SKAN)
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-gil-or
    - Marketers
    - SKAdNetwork (SKAN)
  created_at: '2022-06-23T07:56:50Z'
  edited_at: '2026-10-28T09:17:55Z'
  id: 7078169815057
  locale: ja
  section: SKAN solution
  section_id: 6552135379985
  url: https://support.appsflyer.com/hc/ja/articles/7078169815057
---
> **概要**：SKANの推奨設定を使用してCV設定を最適化し、インストール後の行動をより正確に計測できます。

<div id="overview" />

## 概要

AppleのiOSに組み込まれているSKAdNetwork（SKAN）を使用すると、広告主はユーザーのプライバシーを保護しながら、キャンペーンの成果を計測できます。 SKAdNetworkでは、インストール後の行動を0〜63の数値、つまりコンバージョン値だけで計測します。

AppsFlyerの<Anchor target="_blank" href="/marketers/ja/docs/skan-conversion-studio">Conversion Studio</Anchor>では、各CVを最大限に活用できるよう、柔軟に設定できます。インストール後のどの行動をどのくらいの期間計測するかなど、CVに反映する計測データを細かく指定できます。

ただし、SKANには計測上の制限があるため、収益、アプリ内イベント、リテンションなど、何を計測するか、0〜63のCVをどう使うのが最適か、判断に迷うことがあります。判断には、推定や試行錯誤、アプリ内部のデータを使う機械学習ツールが用いられることもあります。その結果、十分な計測精度を得られるとは限りません。

AppsFlyerのSKAN推奨設定は、以下の特徴を備えています。

* 現在のCV設定を改善し、CVの利用効率と計測精度を高めるための提案を行います。
* CV設定を決定する際の難しさを解消します。
* 業種、地域、SKANとSKAN以外のアプリデータ、ユーザー行動に基づいて提案します。

<div id="recommendations" />

## 推奨設定

<div id="revenue" />

<Accordion title="収益">

<div id="understanding-revenue-recommendations" />

#### **収益の推奨設定について**

収益を正確に報告するには、適切な収益計測スキーマが欠かせません。

収益報告用のCV設定が必ずしも完全に正確とは限らず、SKANが報告する収益と実際の収益が異なる場合があります。たとえば、AppsFlyerが報告する実際のARPPUが10ドルで、現在のCV設定によるSKAN ARPPUが7ドルの場合、SKANは購入ユーザー1人あたりの収益を3ドル少なく報告しています。

AppsFlyerは、SKAN以外の収益データ（精度100%）を毎日確認します。このデータを基に、SKAN収益レポートの精度を高めるための、アプリに合った推奨設定を提案します。提案には、Conversion Studioに保存されたアクティビティ期間の設定や、業種、地域、アプリユーザーの行動も考慮されます。

推奨設定には、以下のメリットがあります。

* 正確な収益レポートにより、キャンペーンの成果を明確に把握できます。
* より少ない範囲で収益を正確に計測し、CVの消費を抑えられます。
* アプリ内購入と広告収益の両方を考慮します。

<div id="revenue-recommendations-layout" />

#### **収益の推奨設定画面の構成**

<table><tbody><tr><td colspan="2"><p><img alt="revenue_recommendions_layout.png" src="https://files.readme.io/1595d3f59b6e30154da560a99430e231d8353d1bd54ebed6192ec0f13cd3f5b3-8976338886801.png"/></p></td></tr><tr><td><p><span>A</span></p></td><td><span>Conversion Studioに保存されたアクティビティ期間。この期間のSKAN収益が計測されます。</span></td></tr><tr><td><p><span>B</span></p></td><td><span>アプリの実際の購入ユーザー1人あたりの平均収益（ARPPU）。AppsFlyerの方法でアトリビューションされた、オーガニック／ノンオーガニックユーザーの正確なデータに基づきます。</span></td></tr><tr><td><p><span>C</span></p></td><td><p><span>現在の設定に基づくARPPU（SKAN ARPPU）。Conversion Studioの<span>アクティビティ期間と、収益報告用のCV設定を使って計測したARPPUです。</span></span></p></td></tr><tr><td><span>D</span></td><td><p><span>推定ARPPU：選択した範囲数で期待されるARPPU。 SKANや従来の方法など、アトリビューション方法を問わず、アプリの過去14日間の収益をすべて合計し、購入ユーザー数で割って算出します。 </span><span>FとGを参照してください。</span></p><p><span><strong>注意：</strong></span><span>この数値は、AppsFlyerのほかのダッシュボードでは確認できません。ここではARPPU（購入ユーザー1人あたりの平均収益）を表示しますが、ほかのダッシュボードではARPU（ユーザー1人あたりの平均収益）を表示します。</span></p></td></tr><tr><td><p><span>E</span></p></td><td><p>概算誤差：BとCの差<span>です。SKAN ARPPUが実際より高く報告されているか、低く報告されているかに応じて、プラスまたはマイナスになります。</span></p><p><span>例：実際のARPPUが10ドル、SKAN ARPPUが7ドルの場合、概算誤差は−30%です。ユーザー1人あたり3ドル少なく報告されていることになります。</span></p></td></tr><tr><td><p><span>F</span></p></td><td><p>SKANの収益設定に対する推奨内容。設定に含める範囲の数を選択します。</p></td></tr><tr><td><p><span>G</span></p></td><td><p><span>Conversion Studioに設定されている現在の収益設定。</span><span></span></p></td></tr></tbody></table>

<div id="using-revenue-recommendations" />

#### **収益の推奨設定の使用方法**

**前提条件：** 収益の推奨設定には、少なくとも14日分の収益データが必要です。

<div id="note" />

> 📘 **注意**
>
> データは毎日更新されます。つまり、昨日を最終日とする、過去14日間のデータを使用します。たとえば、今日が8月28日の場合、推奨設定には、8月13日〜27日のデータを使用します。

**収益の推奨設定を使用する手順：**

1. AppsFlyerで、SKAN 4、カスタム、固定［従来のモード］のどれを使用しているかに応じて、以下のいずれかに移動します。
   * **［設定］**＞**［SKAN Conversion Studio］**＞**［SKAN 4］**＞**［総収益／アプリ内イベント］**。
   * **［設定］**＞**［SKAN Conversion Studio］**＞**［カスタム］**＞**［総収益／アプリ内イベント］**。
   * **［設定］**＞**［SKAN Conversion Studio］**＞**［収益］**。
2. 収益範囲が既に設定されている場合は、この手順を省略します。未設定の場合は、ここで収益範囲を設定します。  
   収益範囲を設定すると、設定の精度と概算誤差が表示されます。
3. <strong>［推奨設定を確認］</strong>をクリックします。  
   現在の設定の情報とともに、推奨する収益範囲と、その設定を適用した場合に見込まれる精度（概算誤差）が表示されます。範囲数を維持する場合と、変更する場合の両方について、推奨設定が提示されます。
4. 推奨する範囲を選択します。
5. <strong>［推奨設定を適用］</strong>をクリックします。
   * カスタムモードで収益を設定している場合は、推奨設定が適用されます。
   * 固定モード（収益）を使用している場合は、推奨された範囲を控えてください。その後、**［SKAN Conversion Studio］**＞**［カスタム］**＞<strong>［総収益］</strong>に移動し、その範囲を設定します。
6. <strong>［保存］</strong>をクリックします。
   * その後に収益設定を変更した場合も、設定を再確認して、新しい推奨内容を表示できます。

</Accordion>

<div data-zendesk-anchors="overview=%E6%A6%82%E8%A6%81 h_01HGSZ05CH4P8BQT23VYH6DKVP=%E6%A6%82%E8%A6%81 recommendations=%E6%8E%A8%E5%A5%A8%E8%A8%AD%E5%AE%9A h_01HGSZ05CHPZKWKY7MR6MA68YZ=%E6%8E%A8%E5%A5%A8%E8%A8%AD%E5%AE%9A h_01HGSZ05CH2RG3514N576ZGDFM=revenue understanding-revenue-recommendations=%E5%8F%8E%E7%9B%8A%E3%81%AE%E6%8E%A8%E5%A5%A8%E8%A8%AD%E5%AE%9A%E3%81%AB%E3%81%A4%E3%81%84%E3%81%A6 h_01HGSZ05CHC93SHP28DN9EK27N=%E5%8F%8E%E7%9B%8A%E3%81%AE%E6%8E%A8%E5%A5%A8%E8%A8%AD%E5%AE%9A%E3%81%AB%E3%81%A4%E3%81%84%E3%81%A6 revenue-recommendations-layout=%E5%8F%8E%E7%9B%8A%E3%81%AE%E6%8E%A8%E5%A5%A8%E8%A8%AD%E5%AE%9A%E7%94%BB%E9%9D%A2%E3%81%AE%E6%A7%8B%E6%88%90 h_01HGSZ05CH5DVKAQ24EED16JRN=%E5%8F%8E%E7%9B%8A%E3%81%AE%E6%8E%A8%E5%A5%A8%E8%A8%AD%E5%AE%9A%E7%94%BB%E9%9D%A2%E3%81%AE%E6%A7%8B%E6%88%90 using-revenue-recommendations=%E5%8F%8E%E7%9B%8A%E3%81%AE%E6%8E%A8%E5%A5%A8%E8%A8%AD%E5%AE%9A%E3%81%AE%E4%BD%BF%E7%94%A8%E6%96%B9%E6%B3%95 h_01HGSZ05CJ4W0V3Y4XBWRMFW8K=%E5%8F%8E%E7%9B%8A%E3%81%AE%E6%8E%A8%E5%A5%A8%E8%A8%AD%E5%AE%9A%E3%81%AE%E4%BD%BF%E7%94%A8%E6%96%B9%E6%B3%95 h_01HGSZCYCWRYEJPWZKDBC9SX8H=%E6%B3%A8%E6%84%8F" />
