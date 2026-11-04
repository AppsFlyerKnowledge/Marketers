---
title: お知らせ：Meta広告のチャネル別内訳に関する更新
metadata:
  keywords:
    - Marketers
    - Mobile Attribution
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-shay-maoz
    - Marketers
    - Mobile Attribution
  created_at: '2026-08-04T08:33:09Z'
  edited_at: '2026-10-13T09:15:09Z'
  id: 49465306965393
  locale: ja
  section: Bulletins
  section_id: 6551161473041
  url: https://support.appsflyer.com/hc/ja/articles/49465306965393
---
| セクション | 詳細 |
| --- | --- |
| **新機能** | Metaでは、2026年8月6日より、`impression_device`の内訳を利用するには広告アカウントごとのオプトインが必要になります。 MetaのレポートAPIでは、地域別とチャネル別の両方で内訳を分けたコストデータを同じクエリで返せないため、このオプトインを行っていないアカウントでは不完全なデータが表示されます：<ul><li>デフォルトの［My Dashboards］ビューで、チャネルレベルのコストデータが欠落する可能性があります</li><li>Cost ETLでMetaのデータが欠落する可能性があります</li></ul>同じ制限は、チャネル別に分類されたクリエイティブのパフォーマンスデータにも影響します。 |
| **Effective date** | 2026年8月6日 |
| **What you need to know** | Metaは、このオプトインをAppsFlyerの顧客アカウントに自動的に適用します。 8月6日までは、対応していただく必要はありません。<ul><li>8月6日以降も、チャネル別のコストデータまたはチャネル別のクリエイティブのパフォーマンスデータが欠落している場合は、自動オプトインがまだアカウントに適用されていません。</li></ul> |
| **What you need to do** | 次のステップを実行してください：<ol><li>8月6日以降、チャネル別のコストデータ（My Dashboards）とチャネル別のクリエイティブのパフォーマンスデータを確認してください。</li><li>If you notice a gap, contact Meta directly for guidance on enabling the opt-in, or reach out to your AppsFlyer representative for help.</li><li>オプトインがアカウントに適用されると、その後まもなくバックフィルによってデータは自動的に追いつきます。</li><li>アカウントでインプレッションデバイスがすでに有効になっているかどうかは、Ads Managerで直接確認することもできます。手順については、以下の[Ads Managerでインプレッションデバイスを確認する](#ads-managerでインプレッションデバイスを確認する)を参照してください。</li></ol> |

<div id="check-impression-device-in-ads-manager" />

## Ads Managerでインプレッションデバイスを確認する

広告アカウントでインプレッションデバイスがすでに有効になっているかどうかを確認するには、次の手順を実行します：

1. <Anchor target="_blank" href="https://adsmanager.facebook.com/">Ads Manager</Anchor>に移動し、**Settings**を選択します。

[![［設定］ボタンが表示された広告マネージャーツールバー](https://files.readme.io/64c9ac8d571e88bfd098b542456886cc64d6320bf3856721335a077c4f19e5b5-49469436208529.png)](https://files.readme.io/64c9ac8d571e88bfd098b542456886cc64d6320bf3856721335a077c4f19e5b5-49469436208529.png)

2. ［作成］ビューパネルで、**Delivery**を選択します。
3. Delivery の下で、**Additional Breakdowns**を探します。
4. ［Additional Breakdowns］の下で、**Impression Device**（`impression_device`）の横にあるプラス記号がすでに選択されているかどうかを確認します。選択されている場合、このアカウントではオプトインが有効です。

[![広告マネージャーのAdditional Breakdownsパネル。 Time of Day、Impression Device、Frequency Valueのプラスアイコンが表示されている](https://files.readme.io/71eb7c75a3f49a82e98522fcf418acbc6ef378eeda5f093535a168aa8505ade1-49469462456081.png)](https://files.readme.io/71eb7c75a3f49a82e98522fcf418acbc6ef378eeda5f093535a168aa8505ade1-49469462456081.png)

<div data-zendesk-anchors="check-impression-device-in-ads-manager=ads-manager%E3%81%A7%E3%82%A4%E3%83%B3%E3%83%97%E3%83%AC%E3%83%83%E3%82%B7%E3%83%A7%E3%83%B3%E3%83%87%E3%83%90%E3%82%A4%E3%82%B9%E3%82%92%E7%A2%BA%E8%AA%8D%E3%81%99%E3%82%8B h_01KZ63J08GPADE2AH0KV9NNESC=ads-manager%E3%81%A7%E3%82%A4%E3%83%B3%E3%83%97%E3%83%AC%E3%83%83%E3%82%B7%E3%83%A7%E3%83%B3%E3%83%87%E3%83%90%E3%82%A4%E3%82%B9%E3%82%92%E7%A2%BA%E8%AA%8D%E3%81%99%E3%82%8B" />
