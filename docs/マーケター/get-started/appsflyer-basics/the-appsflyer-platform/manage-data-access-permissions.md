---
title: データへのアクセス権限の管理
metadata:
  keywords:
    - permissions
    - Advertisers
    - Agencies
    - Ad Networks
    - network permissions
    - Marketers
    - Platform essentials
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-negri
    - Marketers
    - Platform essentials
    - Agencies
    - Ad Networks
  created_at: '2018-01-08T11:33:39Z'
  edited_at: '2026-10-21T18:45:28Z'
  id: 115005972889
  locale: ja
  section: The AppsFlyer platform
  section_id: 6551361489297
  url: https://support.appsflyer.com/hc/ja/articles/115005972889
---
> **概要：** AppsFlyerでアクセスできるデータや機能は、チームメンバーが所属するアカウントの種類、各チームメンバーの権限、およびアカウントの権限によって異なります。

<div id="access-to-data-by-account-type" />

## アカウントの種類別のデータアクセス

広告主、アドネットワーク、代理店は、それぞれのアカウントの種類に応じて、以下のデータにアクセスできます。

| アカウントの種類 | アクセスできるデータ |
| --- | --- |
| 広告主 | AppsFlyer内の自社のすべてのデータ。ただし、以下に該当する一部のデータは値の一部が非表示にされるか、ハッシュ化（元の値を直接読み取れない形式への変換）されます。<ul><li>法令上の要件やデータ共有条件により制限が設けられているメディアソースにアトリビューションされたトラフィック。</li></ul> |
| アドネットワーク | 当該アドネットワークにアトリビューションされたデータ |
| 代理店 | 当該代理店が運用し、トラフィックがアトリビューションされたキャンペーンに関するデータ |

<div id="access-to-data-by-roles-and-permissions" />

## ロールと権限に応じたデータアクセス

広告主がアドネットワーク（<Anchor target="_blank" href="/marketers/ja/docs/set-up-an-integrated-partner#アドネットワークの権限">アドネットワークの権限</Anchor>を参照）または代理店（<Anchor target="_blank" href="/marketers/ja/docs/set-up-an-integrated-partner#代理店の許可">代理店の権限</Anchor>を参照）の［権限］トグルをオンにした場合も、アクセスできるデータはアカウントの**アドミン**と**チームメンバー**というロールによって異なります。詳細は以下の表をご覧ください。

**注意：** アクセスが許可されている場合でも、閲覧できるのは当該アドネットワークまたは代理店が獲得したトラフィックに限られます。

表中の記号の意味

| 記号 | 意味 |
| --- | --- |
| ✓ | 広告主がメインの権限トグルを有効にするとアクセスできます |
| P | 広告主が該当する追加権限を有効にするとアクセスできます |
| L | 広告主が権限を有効にすると、限定された範囲でアクセスできます |
| – | アクセス不可 |

<div id="access-by-feature-page-for-agencies-and-ad-networks" />

#### 代理店・アドネットワークの機能ページ別アクセス権限

<table><thead><tr><th colspan="2" rowspan="2">機能</th><th colspan="2">代理店</th><th colspan="2">アドネットワーク</th></tr><tr><th>アドミン</th><th>チームメンバー</th><th>アドミン</th><th>チームメンバー</th></tr></thead><tbody><tr><td rowspan="10"><span id="dashboards"></span><p>ダッシュボード</p></td><td>オーバービュー</td><td><span><span>✓</span></span></td><td><span><span>✓</span></span></td><td><span><span>✓</span></span></td><td><span><span>✓</span></span></td></tr><tr><td><span id="protect360"></span>Protect360</td><td> &lt;0&gt;P0&gt;&lt;1&gt;(1)1&gt; </td><td> &lt;0&gt;P0&gt;&lt;1&gt;(1)1&gt; </td><td> &lt;0&gt;P0&gt;&lt;1&gt;(1)1&gt; </td><td> &lt;0&gt;P0&gt;&lt;1&gt;(1)1&gt; </td></tr><tr><td><span id="activity"></span>アクティビティ</td><td>–</td><td>–</td><td>–</td><td>–</td></tr><tr><td><span id="events"></span>イベント</td><td><span><span>✓</span></span></td><td><span><span>✓</span></span></td><td> </td><td> </td></tr><tr><td><span id="retention"></span>リテンション</td><td><a href="" target="_blank">P</a></td><td><a href="" target="_blank">P</a></td><td><a href="" target="_blank">P</a></td><td><a href="" target="_blank">P</a></td></tr><tr><td><span id="cohort"></span>コホート</td><td><a href="" target="_blank">P</a></td><td><a href="" target="_blank">P</a></td><td> </td><td> </td></tr><tr><td><span id="custom-dashboard"></span>カスタムダッシュボード</td><td>–</td><td>–</td><td>–</td><td>–</td></tr><tr><td><span id="skadnetwork"></span>SKAdNetwork</td><td><span><span>✓</span></span></td><td><span><span>✓</span></span></td><td> </td><td> </td></tr><tr><td><span id="loyal-users"></span>ロイヤルユーザー</td><td> </td><td> </td><td><a href="" target="_blank"><span><span>P</span></span></a></td><td><a href="" target="_blank"><span><span>P</span></span></a></td></tr><tr><td><span id="peoplebased-attribution"></span>ピープルベースドアトリビューション</td><td>–</td><td>–</td><td>–</td><td>–</td></tr><tr><td rowspan="6"><span id="reports"></span><p>レポート</p></td><td>ローデータ出力</td><td><a href="" target="_blank">P</a></td><td><a href="" target="_blank">P</a></td><td>L&lt;0&gt;(2)0&gt; </td><td>L&lt;0&gt;(2)0&gt; </td></tr><tr><td><span id="aggregated-data-export"></span>集計データ出力</td><td><span><span>✓</span></span></td><td><span><span>✓</span></span></td><td><a href="" target="_blank">P</a></td><td><a href="" target="_blank">P</a></td></tr><tr><td><span id="protect360-dashboard-raw-data"></span>Protect360ダッシュボードとローデータ</td><td><a href="" target="_blank">P</a></td><td><a href="" target="_blank">P</a></td><td><a href="" target="_blank">P</a></td><td><a href="" target="_blank">P</a></td></tr><tr><td><span id="ad-revenue-raw-data"></span>広告収益のローデータ（ユーザー獲得向けシグナル）</td><td>–</td><td>–</td><td><a href="" target="_blank">P</a></td><td><a href="" target="_blank">P</a></td></tr><tr><td><span id="retention-reports"></span>リテンションレポート</td><td><a href="" target="_blank">P</a></td><td><a href="" target="_blank">P</a></td><td><a href="" target="_blank">P</a></td><td><a href="" target="_blank">P</a></td></tr><tr><td><span id="pivot"></span>ピボット</td><td>–</td><td>–</td><td>–</td><td>–</td></tr><tr><td rowspan="6"><span id="configuration"></span><p>設定</p></td><td>連携済みパートナー</td><td>読み取り専用</td><td>読み取り専用</td><td>読み取り専用</td><td>読み取り専用</td></tr><tr><td><span id="active-integrations-configure-integration"></span>連携済みパートナー &gt; 連携の設定</td><td>–</td><td>–</td><td><a href="" target="_blank">P</a></td><td><a href="" target="_blank">P</a></td></tr><tr><td><span id="active-integrations-configure-inapp-event-postbacks"></span>連携済みパートナー &gt; アプリ内イベントポストバックの設定</td><td><a href="" target="_blank">P</a></td><td><a href="" target="_blank">P</a></td><td><a href="" target="_blank">P</a></td><td><a href="" target="_blank">P</a></td></tr><tr><td><span id="validation-rules"></span>検証ルール</td><td><a href="" target="_blank">P</a></td><td><a href="" target="_blank">P</a></td><td> &lt;0&gt;P0&gt;&lt;1&gt;(3)1&gt; </td><td> &lt;0&gt;P0&gt;&lt;1&gt;(3)1&gt; </td></tr><tr><td><span id="approved-agencies"></span>承認済み代理店</td><td>–</td><td>–</td><td>–</td><td>–</td></tr><tr><td><span id="app-settings"></span>アプリ設定</td><td>L&lt;0&gt;(4)0&gt; </td><td>–</td><td>–</td><td>–</td></tr><tr><td><span id="experiences-deep-linking"></span><p>ユーザー体験とディープリンク</p></td><td>OneLinkの設定</td><td>–</td><td>–</td><td>–</td><td>–</td></tr><tr><td rowspan="6"><span id="integration"></span><p>連携</p></td><td>AudiencesとIncrementality</td><td>–</td><td>–</td><td>–</td><td>–</td></tr><tr><td><span id="sdk-information"></span>SDK情報</td><td>–</td><td>–</td><td>–</td><td>–</td></tr><tr><td><span id="sdk-integration-tests"></span>SDK実装テスト</td><td>–</td><td>–</td><td>–</td><td>–</td></tr><tr><td><span id="api-access-pull-api-aggregate-data"></span>APIアクセス（Pull API集計データ） </td><td><span><span>✓</span></span></td><td><span><span>✓</span></span></td><td>–</td><td>–</td></tr><tr><td><span id="data-locker"></span>Data Locker</td><td>–</td><td>–</td><td>–</td><td>–</td></tr><tr><td><span id="ad-spend-ingestion"></span>コストインポート</td><td>–</td><td>–</td><td> &lt;0&gt;P0&gt;&lt;1&gt;(6)1&gt; </td><td> &lt;0&gt;P0&gt;&lt;1&gt;(6)1&gt; </td></tr><tr><td colspan="6"><span id="notes-and-limitations1-if-the-advertiser-has-protect360-premium-you-have-access-to-the-full-dashboard-if-not-you-have-access-to-the-lite-dashboard2-limited-to-raw-data-in-postbacks-attributed-to-the-partner-only-3-readonly4-limited-to-turning-on-agency-transparency-only-for-agencies-with-legacy-nontransparency5-agencies-cant-define-their-own-onelink-templates-but-they-can-create-attribution-links-using-onelink-templates-defined-by-the-advertiser6-partners-can-upload-spend-data-for-the-selected-app"></span><p><span><strong>注意事項と制限事項：</strong></span><br/><span></span><span><strong>1.</strong> 広告主が<a href="./protect360-anti-fraud-guide" target="_blank">Protect360</a>（有料機能）を契約している場合は、フル版のダッシュボードにアクセスできます。契約していない場合は、ライト版のダッシュボードにアクセスできます。<br/>0&gt;&lt;1&gt;&lt;2&gt;2.2&gt; アクセスできるのは、当該パートナーにアトリビューションされたポストバックのローデータのみです。 &lt;0&gt;1&gt;&lt;2&gt;2&gt;&lt;2&gt;&lt;3&gt;3. 読み取り専用です。<br/>0&gt;&lt;1&gt;&lt;2&gt;42&gt;. 従来の運用媒体を開示しない設定が適用されている代理店では、<a href="/partners/ja/docs/getting-started-agency-onboarding#運用媒体の開示" target="_blank">運用媒体の開示設定</a>をオンにする操作のみが可能です。<br/>&lt;0&gt;50&gt;. 代理店はOneLinkテンプレートやリンクを作成できません。</span>&lt;0&gt;&lt;1&gt;&lt;2&gt;6. <span>パートナーは、選択したアプリの広告費データをアップロードできます。<span></span>0&gt;<span></span></span></p></td></tr></tbody> 2&gt;</table>

<div id="access-for-advertisers" />

#### 広告主のアクセス権限

広告主アカウントの<Anchor target="_blank" href="/marketers/ja/docs/user-management#admin">アドミンロール</Anchor>は、[上の表](/docs/manage-data-access-permissions#代理店アドネットワークの機能ページ別アクセス権限)に記載されているすべての機能にアクセスできます。その他のユーザーは、割り当てられた<Anchor target="_blank" href="/marketers/ja/docs/user-management#ロールの管理">ロール</Anchor>に応じてアクセスできます。

<div id="access-to-the-aggregate-cost-and-revenue-data" />

#### コスト・収益の集計データへのアクセス

<table><thead><tr><th rowspan="1"> </th><th colspan="2">広告主</th><th colspan="2">代理店</th><th colspan="2">アドネットワーク </th></tr><tr><th rowspan="1"> </th><th>コスト</th><th>収益</th><th>コスト</th><th>収益</th><th>コスト</th><th>収益</th></tr></thead><tbody><tr><td>オーガニック</td><td>対象外</td><td><span>✓</span></td><td>対象外</td><td>P</td><td>対象外</td><td>-</td></tr><tr><td>非オーガニック</td><td><span>✓</span></td><td><span>✓</span></td><td><span>✓</span></td><td><span>✓</span></td><td><span>✓</span></td><td>-</td></tr><tr><td>Meta広告</td><td><span>✓</span></td><td><span>✓</span></td><td><span>✓</span></td><td><span>✓</span></td><td>対象外<span>(2)</span> </td><td>-</td></tr><tr><td>X広告</td><td> &lt;0&gt;&lt;1&gt;✓1&gt;0&gt;&lt;2&gt;(1)2&gt; </td><td><span>✓</span></td><td>-</td><td><span>✓</span></td><td>対象外<span>(2)</span> </td><td>-</td></tr><tr><td>Google広告</td><td><span>✓</span></td><td><span>✓</span></td><td>-</td><td><span>✓</span></td><td>対象外<span>(2)</span> </td><td>-</td></tr><tr><td>Apple Ads</td><td><span>✓</span></td><td>対象外</td><td><span>✓</span></td><td>対象外</td><td>対象外<span>(2)</span> </td><td>対象外</td></tr><tr><td>リターゲティング</td><td>-</td><td><span>✓</span></td><td>-</td><td><span>✓</span></td><td><span>✓</span></td><td>-</td></tr><tr><td colspan="7"> <span><strong>注意</strong>：</span><br/><span>1. 2020年6月以降</span><br/><span>2. 当該アドネットワークのみが閲覧できます。他のアドネットワークは閲覧できません。例：X Adsは、自社の広告費を確認できます。</span> </td></tr></tbody></table>

<div data-zendesk-anchors="access-to-data-by-advertisers-agencies-and-ad-networks=%E3%82%A2%E3%82%AB%E3%82%A6%E3%83%B3%E3%83%88%E3%81%AE%E7%A8%AE%E9%A1%9E%E5%88%A5%E3%81%AE%E3%83%87%E3%83%BC%E3%82%BF%E3%82%A2%E3%82%AF%E3%82%BB%E3%82%B9 h_01HCA2QJ28ABFQXDPT4DHD1HMZ=%E3%82%A2%E3%82%AB%E3%82%A6%E3%83%B3%E3%83%88%E3%81%AE%E7%A8%AE%E9%A1%9E%E5%88%A5%E3%81%AE%E3%83%87%E3%83%BC%E3%82%BF%E3%82%A2%E3%82%AF%E3%82%BB%E3%82%B9 access-to-data-by-roles-and-permissions=%E3%83%AD%E3%83%BC%E3%83%AB%E3%81%A8%E6%A8%A9%E9%99%90%E3%81%AB%E5%BF%9C%E3%81%98%E3%81%9F%E3%83%87%E3%83%BC%E3%82%BF%E3%82%A2%E3%82%AF%E3%82%BB%E3%82%B9 h_01HCA2QJ281TGPB59HR61192JF=%E3%83%AD%E3%83%BC%E3%83%AB%E3%81%A8%E6%A8%A9%E9%99%90%E3%81%AB%E5%BF%9C%E3%81%98%E3%81%9F%E3%83%87%E3%83%BC%E3%82%BF%E3%82%A2%E3%82%AF%E3%82%BB%E3%82%B9 access-by-feature=%E4%BB%A3%E7%90%86%E5%BA%97%E3%82%A2%E3%83%89%E3%83%8D%E3%83%83%E3%83%88%E3%83%AF%E3%83%BC%E3%82%AF%E3%81%AE%E6%A9%9F%E8%83%BD%E3%83%9A%E3%83%BC%E3%82%B8%E5%88%A5%E3%82%A2%E3%82%AF%E3%82%BB%E3%82%B9%E6%A8%A9%E9%99%90 h_01HCA2QJ289XXSJY926TJ6BTJJ=%E4%BB%A3%E7%90%86%E5%BA%97%E3%82%A2%E3%83%89%E3%83%8D%E3%83%83%E3%83%88%E3%83%AF%E3%83%BC%E3%82%AF%E3%81%AE%E6%A9%9F%E8%83%BD%E3%83%9A%E3%83%BC%E3%82%B8%E5%88%A5%E3%82%A2%E3%82%AF%E3%82%BB%E3%82%B9%E6%A8%A9%E9%99%90 notes-and-limitations1-if-the-advertiser-has-protect360-premium%E2%80%94you-have-access-to-the-full-dashboard-if-not-you-have-access-to-the-lite-dashboard2-limited-to-raw-data-in-postbacks-attributed-to-the-partner-only%C2%A03-readonly4-limited-to-turning-on-agency-transparency-only-for-agencies-with-legacy-nontransparency5-agencies-cant-define-their-own-onelink-templates-but-they-can-create-attribution-links-using-onelink-templates-defined-by-the-advertiser6-partners-can-upload-spend-data-for-the-selected-app=notes-and-limitations1-if-the-advertiser-has-protect360-premium-you-have-access-to-the-full-dashboard-if-not-you-have-access-to-the-lite-dashboard2-limited-to-raw-data-in-postbacks-attributed-to-the-partner-only-3-readonly4-limited-to-turning-on-agency-transparency-only-for-agencies-with-legacy-nontransparency5-agencies-cant-define-their-own-onelink-templates-but-they-can-create-attribution-links-using-onelink-templates-defined-by-the-advertiser6-partners-can-upload-spend-data-for-the-selected-app access-for-advertisers=%E5%BA%83%E5%91%8A%E4%B8%BB%E3%81%AE%E3%82%A2%E3%82%AF%E3%82%BB%E3%82%B9%E6%A8%A9%E9%99%90 h_01HCA2QJ28G37MPVZA6H7JJ0D9=%E5%BA%83%E5%91%8A%E4%B8%BB%E3%81%AE%E3%82%A2%E3%82%AF%E3%82%BB%E3%82%B9%E6%A8%A9%E9%99%90 access-to-the-aggregate-cost-and-revenue-data=%E3%82%B3%E3%82%B9%E3%83%88%E5%8F%8E%E7%9B%8A%E3%81%AE%E9%9B%86%E8%A8%88%E3%83%87%E3%83%BC%E3%82%BF%E3%81%B8%E3%81%AE%E3%82%A2%E3%82%AF%E3%82%BB%E3%82%B9 h_01HCA2QJ28Q4PQR8DZJKA4E42F=%E3%82%B3%E3%82%B9%E3%83%88%E5%8F%8E%E7%9B%8A%E3%81%AE%E9%9B%86%E8%A8%88%E3%83%87%E3%83%BC%E3%82%BF%E3%81%B8%E3%81%AE%E3%82%A2%E3%82%AF%E3%82%BB%E3%82%B9" />
