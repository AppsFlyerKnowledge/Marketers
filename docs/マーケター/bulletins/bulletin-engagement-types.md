---
title: お知らせ：エンゲージメントの種類
metadata:
  keywords:
    - Marketers
    - Mobile Attribution
table_of_contents: false
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-moran-davida
    - Marketers
    - Mobile Attribution
  created_at: '2023-11-15T10:50:04Z'
  edited_at: '2026-10-14T09:25:48Z'
  id: 20161875390865
  locale: ja
  section: Bulletins
  section_id: 6551161473041
  url: https://support.appsflyer.com/hc/ja/articles/20161875390865
---

<Table>
  <tbody>
    <tr>
      <td>
        **更新情報**
      </td>
      <td>
        ローデータレポートに新しいデータ項目がいくつか追加されました。

        * engagement\_type
        * contributor1\_engagement\_type
        * contributor2\_engagement\_type
        * contributor3\_engagement\_type

        これらのパラメータは、次のような値もしくは空白でレポートされます： preload / click\_to\_download / click\_to\_app / engaged\_click / engaged\_view / view / listening

        | **engagement\_type** | 説明 |
        | --- | --- |
        | preload | アプリが、端末上で初めてプロバイダーもしくはファクトリーにより初期化されたときにプリロードされたことを指します。または、デバイスが初めて初期化された際に、ウィザードによりユーザーにアプリをダウンロードするように求められた場合。 |
        | click\_to\_download | ユーザーが広告に接触した際に、アプリストアにリダイレクトされることなく、アプリが自動的にダウンロードされ、デバイスにインストールされるケース |
        | click\_to\_app | 広告のクリック、QR コードのスキャン、ディープリンクなど、ユーザーをアプリまたは関連するアプリストアにリダイレクトしてアプリをダウンロードするクリック。 |
        | engaged\_click | 広告に接触したが、ユーザーを同じコンテキストにとどめ、アプリストアに誘導したり、アプリを起動したりしないクリック。 |
        | engaged\_view | ユーザーによる「有意義」な広告閲覧が行われることを指します。例：ユーザーがスキップ可能な動画広告をすべて閲覧完了した、もしくは10秒以上視聴した場合など |
        | view | 広告がレンダリングされ、インプレッションが発火したことを指します。例：バナー、インタースティシャル、エンゲージメントのない動画などがあります。 |
        | listening | ユーザーがポッドキャスト広告などの音声広告を聴いたことを指します。 |
      </td>
    </tr>
    <tr>
      <td>
        **発効日**
      </td>
      <td>
        1月18日
      </td>
    </tr>
    <tr>
      <td>
        影響内容
      </td>
      <td>
        * ローデータレポートにアクセスできる広告主と代理店は、これらの項目を報告するアドネットワークと連携しています。
          * ディープリンクのpreloadとclick\_to\_appは、アドネットワークが項目を報告するかどうかに関係なく、AppsFlyerによって入力されます。
        * * これらの項目はデフォルトで選択されていません（Push APIのすべて選択を除く）。これらの項目を使用するには、ローデータ製品で手動で選択する必要があります。
      </td>
    </tr>
  </tbody>
</Table>
