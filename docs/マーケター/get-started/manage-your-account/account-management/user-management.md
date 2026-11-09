---
title: ユーザー管理
metadata:
  keywords:
    - Advertisers
    - Marketers
    - Platform essentials
x-zendesk:
  category: Marketers
  category_id: 6550444307985
  content_tags:
    - pm-roy-negri
    - Marketers
    - Platform essentials
  created_at: '2021-10-17T11:54:49Z'
  edited_at: '2026-10-28T09:13:10Z'
  id: 4409128270481
  locale: ja
  section: Account management
  section_id: 6551191075473
  url: https://support.appsflyer.com/hc/ja/articles/4409128270481
---
> **概要：** アカウントのAppsFlyerユーザーを作成・管理し、機能、アプリ、データへのアクセス権限を割り当てます。

<div id="overview" />

## 概要

AppsFlyerのアカウントには複数のユーザーを登録でき、ユーザーごとに権限を管理できます。アカウントに登録できるユーザー数の上限は、契約プランによって異なります。

各ユーザーの権限は、主に次の3つの観点で設定します。

* **ロール**（機能へのアクセスと操作の権限）
* 現在のアプリと、今後追加されるアプリへの**アクセス**
* メディアソース・地域ごとの**データへのアクセス**
  * 重要メディアソースや地域によるデータアクセスの制限があるユーザーは、一部のAppsFlyerダッシュボードや機能を利用できません。対象のダッシュボードと機能は、[こちらの一覧](#dashboard-and-feature-availability-for-users-with-limited-media-sourcegeo-access)を参照してください。

これらの権限は、それぞれ独立して設定できます。たとえば、幅広い操作ができる**ロール**を割り当てながら、操作できる範囲を特定の**アプリ、メディアソース、地域に限定することが可能です。** ただし、後述の[Adminロール](#admin)は例外で、すべての機能、アプリ、メディアソース、地域にアクセスできます。

管理者は[同じユーザーを複数のアカウントに追加](#multiple-accounts)でき、ユーザーはアカウントを簡単に切り替えられます。

<div id="user-management-page" />

## ユーザー管理ページ

**ユーザー管理ページを開くには、次の手順に従います。**

* 上部のバーでアカウントメニュー（メールアドレスのドロップダウン）を開き、<strong>［ユーザー管理］</strong>を選択します。

<Image align="center" alt="user-management-page.jpg" src="https://files.readme.io/0ca6dd472b6f50bfde693bba9c131ce9454dc1df90e3a0fb029e2e05b2330db4-31780969019665.jpg" />

<div id="users-tab" />

<Accordion title="ユーザータブ">

<strong>［ユーザー］</strong>タブには、アカウントに登録されているすべてのユーザーが表形式で表示されます。このタブから、ユーザーの作成、管理、削除を行います。

ユーザータブの使い方：

* <strong>［ユーザー］</strong>列の見出しをクリックすると、アルファベット順（昇順・降順）に並べ替えられます。
* 検索ボックスを使うと、特定のユーザーを検索して表示できます。
* ［ロール］列の見出しにあるフィルターアイコン <Image alt="filter_icon.png" src="https://files.readme.io/1ceaac3efead3a218909988be1d50a2f0af93b07360f7197cd398b11d661992b-16162502598417.png" width="25px" /> をクリックし、**ロール**（暫定ロールを含む）ごとにユーザーを絞り込みます。
  * 絞り込みを解除するには、フィルターのドロップダウンリストで<strong>［なし］</strong>を選択します。
* <strong>［最終ログイン］</strong>列の見出しをクリックすると、AppsFlyerへの最終ログイン日時で並べ替えられます。
  * **ヒント：** この機能で利用されていないユーザーを見つけて[削除](#deleting-users)すると、不正ログインのリスクを抑えられます。
* チェックボックスで選択すると、[複数のユーザーをまとめて編集](#複数のユーザーをまとめて編集する)できます。
* 管理者のみ：ページ右上のダウンロードアイコン <Image alt="download_icon.png" src="https://files.readme.io/fba5d56ceb7f6b3dc3191e5ec33c85ccbba0f7dc409ad0390de238c12b479b61-31780969029777.png" width="24px" /> をクリックすると、ユーザー一覧全体をCSVファイルでダウンロードできます。
  * ダウンロードしたファイルには、<strong>［ユーザー］</strong>タブの表と同じ列が含まれます。

</Accordion>

<div id="roles-tab" />

<Accordion title="ロールタブ">

<strong>［ロール］</strong>タブには、アカウントに定義されている次のロールがすべて表示されます。

* [定義済みロール](#定義済みロール)
* [カスタムロール](#カスタムロールの管理)（自分で作成したもの）
* 現在ユーザーに割り当てられている[暫定ロール](#暫定ロール)

各ロールの横には、そのロールが現在割り当てられているユーザー数が表示されます。

左側のパネルでロール名をクリックすると、そのロールの操作権限の詳細を確認できます。

</Accordion>

ユーザーとロールを管理するための各操作を、以下で説明します。

<div id="manage-users" />

## ユーザーの管理

管理者は、ユーザーの新規作成、複数アカウントへの追加、ロールやアプリ・データへのアクセス権限などの編集、削除を行えます。 一部の操作は、[専用APIを使って一括で実行](#apiによるユーザーの一括管理)できます。

<div id="creating-users" />

<Accordion title="ユーザーの作成">

<Embed title="ユーザー管理" typeOfEmbed="youtube" url="https://www.youtube.com/embed/wLCXP5dFrKg" providerUrl="https://www.youtube.com" />

ユーザーの作成・編集ページには、複数のセクションがあります。以下の説明に従って、それぞれ設定してください。必要な変更が完了したら、ページ右下の<strong>［保存］</strong>をクリックします。

<div id="user-details" />

#### ユーザー情報

1. <strong>［ユーザー］</strong>タブで、<strong>［新しいユーザー］</strong>をクリックします。
2. ユーザーの氏名を入力します（必須）。
   * 文字、数字、スペース、ピリオド（.）、ハイフン（-）、アンダースコア（\_）、一重引用符（'）、二重引用符（"）を使用できます。
   * そのほかの特殊文字は使用できません。
3. ユーザーのメールアドレスを入力します（必須）。

   * 文字、数字、アポストロフィ（'）、アンパサンド（&）、ドル記号（$）、ハッシュ記号（#）、ハイフン（-）、アンダースコア（\_）、ピリオド（.）を使用できます。
   * ピリオドの連続（..）や、そのほかの特殊文字は使用できません。
   * 末尾は、有効なメールドメインである必要があります。

   <div id="important" />

   > 🚧 **重要**
   >
   > AppsFlyerではメールアドレスでユーザーを識別するため、次の点に注意してください。
   >
   > * 変更するには、ユーザーを削除して再作成する必要があります。
   > * ユーザーが実際にメールを受信できる、有効なメールアドレスを登録してください。
   > * [複数アカウントで利用するユーザー](#multiple-accounts)を除き、いずれのAppsFlyerアカウントでも、ほかのユーザーと同じメールアドレスは使用できません。同じメールアドレスが自分またはほかのアカウントですでに使用されている場合、*「このユーザーを作成できません」*と表示されます。 [以下のトラブルシューティング手順](/docs/user-management#troubleshooting-can-t-create-this-user)に従って解決してください。

4. ［任意］ユーザーの部署を選択します。

<div id="role" />

#### ロール

定義済みロール、または作成済みのカスタムロールから、ユーザーのロールを選択します（必須）。

<div id="app-access" />

#### アプリへのアクセス

ユーザーがアクセスできるアプリを選択します。

* デフォルトでは、アカウント内のすべての既存アプリと、今後追加されるアプリへのアクセスが許可されます。変更するには、チェックボックスでアプリを選択・解除します。
* 今後追加されるすべてのアプリへのアクセスを許可できるのは、現在のすべてのアプリにアクセスできるユーザーのみです。

<div id="data-access" />

#### データへのアクセス

メディアソースと地域ごとに、ユーザーのデータへのアクセスを設定します。すべてを許可するか、特定のものだけを選択して許可するかを決めます。

<div id="note" />

> 📘 **注意**
>
> メディアソースや地域へのアクセスが制限されているユーザーは、一部の[ダッシュボードや機能](/docs/user-management#dashboard-and-feature-availability-for-users-with-limited-media-sourcegeo-access)を利用できません。

<div id="media-sources" />

#### メディアソース

デフォルトの<strong>［すべて］</strong>では、アカウント内のすべてのメディアソースへのアクセスが許可されます。今後追加されるメディアソースも含まれます。特定のメディアソースを選択した場合、今後追加されるメディアソースへのアクセスは含まれません。

<div id="note-1" />

> 📘 **注意**
>
> * メディアソースへのアクセスが制限されているユーザーは、一部の[ダッシュボードや機能](/docs/user-management#dashboard-and-feature-availability-for-users-with-limited-media-sourcegeo-access)を利用できません。
> * AdminロールとSecurityロールでは、すべてのメディアソースに制限なくアクセスできます。この設定は変更できません。

**メディアソースの種類：**

リストには、次の2種類のメディアソースが表示されます。

* **有料メディアソース：** アドネットワーク、Self-Reporting Network（SRN）、代理店
* **<span id="custom_media_sources"></span>カスタムメディアソース：** あらかじめ定義されたメディアソース。自社メディアのリンク、単一ソースのリンク、OneLinkのリンク、広告主がAppsFlyer以外で作成したリンクなどが含まれます。

**メディアソース一覧の仕様：**

* 過去24か月間にトラフィックがあったメディアソースを、直近のトラフィックが新しい順に表示します。
* 代理店は、リストの下部にまとめて表示されます。
* 最大100,000件のメディアソースが含まれます。
  * アドネットワーク、SRN、カスタムメディアソース：最大50,000件
  * 代理店：最大50,000件
* 1日1回更新されます。新たに追加されたメディアソースは、トラフィックがシステムに入った翌日にリストに表示されます。
* 5年以上トラフィックがないメディアソースは、リストから削除されます。

**デフォルト設定を変更するには、次の手順に従います。**

1. <strong>［メディアソース］</strong>で、<strong>［すべて］</strong>をクリックします。
2. ドロップダウンリストから、ユーザーにアクセスを許可するメディアソースを選択します。

設定を保存すると、そのユーザーのダッシュボードには、選択したメディアソースのデータのみが表示されます。

<div id="geos" />

#### 地域

**すべて**の地域のデータにアクセスを許可するか、特定の地域のみに許可するかを選択します。デフォルトでは、すべての地域へのアクセスが許可されます。 アクセスが制限されているユーザーは、一部の[ダッシュボードや機能](/docs/user-management#dashboard-and-feature-availability-for-users-with-limited-media-sourcegeo-access)を利用できません。

**デフォルト設定を変更するには、次の手順に従います。**

1. <strong>［地域］</strong>で、<strong>［すべて］</strong>をクリックします。
2. ドロップダウンリストから、ユーザーにアクセスを許可する地域を選択します。

<div id="user-activation" />

#### ユーザーの有効化

ユーザーを作成すると、ユーザー一覧に封筒アイコン![pending_invitation_icon.png](https://files.readme.io/68ac08ab6e52191a592350f82996f7ade9d181773d0bdbc6e2cb60315b60a8f2-16162502609553.png)付きで表示されます。このアイコンは、招待が送信され、有効化を待っている状態を示します。ユーザーは、メール内のリンクからアカウントを有効化する必要があります。有効化リンクの有効期間は48時間です。ユーザーがアカウントを有効化すると、封筒アイコンは表示されなくなります。

<div id="note-2" />

> 📘 **注意**
>
> ユーザーに招待が届かない場合や、リンクの有効期限が切れた場合は、[招待を再送信](/docs/user-management#resending-a-user-invitation)できます。

</Accordion>

<div id="multiple-accounts" />

<Accordion title="同じユーザーを複数のアカウントに追加する">

同じユーザーを複数のアカウントに追加し、アカウントごとに異なるロールを割り当てることができます。ユーザーは、ログイン情報を再入力せずに別のアカウントで作業できます。

<div id="log-in-to-multiple-accounts" />

#### 複数アカウントへのログイン

複数アカウントへのログインでは、すべてのログイン方法、つまりユーザー名とパスワード、<Anchor target="_blank" href="/marketers/ja/docs/implementing-and-using-2fa-login">2FA</Anchor>、<Anchor target="_blank" href="/marketers/ja/docs/set-up-sso-authentication-with-your-identity-provider-idp">SSO</Anchor>を利用できます。

<div id="note-3" />

> 📘 **注意**
>
> 初回ログイン時ではなく、アカウントを切り替える際には、利用したログイン方法にかかわらず、メールで届く6桁の認証コードを追加で入力する必要があります。<Anchor target="_blank" href="/marketers/ja/docs/welcome-to-appsflyer#アカウントを切り替える">アカウントの切り替え方法の詳細は、こちらの記事を参照してください</Anchor>。

<div id="supported-accounts-and-users" />

#### 対応するアカウントとユーザー

広告主アカウントでは、同じユーザーを複数のアカウントで利用できます。必要な権限があれば、すべてのアカウントにユーザーを追加できます。以下の制限事項を確認してください。

<div id="limitations-on-adding-users-to-multiple-accounts" />

#### 複数アカウントへのユーザー追加に関する制限事項

* この機能は、広告主アカウントで、必要なユーザー管理権限を持つユーザーのみが利用できます。
* 1人のユーザーが[アカウント所有者](#アカウント所有者)になれるのは、1つのアカウントのみです。ほかのアカウントでは、それ以外のロールを割り当てることができます。
* まだ[アカウントを有効化していない](#ユーザーの有効化)ユーザーは、別のアカウントに追加できません。

<div id="add-users-to-multiple-accounts" />

#### 同じユーザーを複数のアカウントに追加する

**同じユーザーを複数のアカウントに追加するには、次の手順に従います。**

1. ユーザーを追加するアカウントにログインします。
2. メニューバーで、**メールアドレスのドロップダウン**＞<strong>［ユーザー管理］</strong>をクリックします。
3. <strong>［ユーザー］</strong>タブで、<strong>［新しいユーザー］</strong>をクリックします。
4. 必要な情報を入力し、このアカウントで割り当てるロールを選択して、<strong>［保存］</strong>をクリックします。
5. 手順1～4を繰り返し、ほかのアカウントにもユーザーを追加します。

</Accordion>

<div id="editing-users" />

<Accordion title="ユーザーの編集">

ユーザーは、1人ずつ編集することも、複数人をまとめて編集することもできます。

<div id="individual-editing" />

#### 個別に編集する

**ユーザーを個別に編集するには、次の手順に従います。**

1. <strong>［ユーザー］</strong>タブで、対象ユーザーの行の右端にある<strong>［操作］</strong><Image alt="actions_icon.png" src="https://files.readme.io/24ad987d1e77d9dfa8559a370733a7b62a6d86954ec1d552eac9c406445ed927-16162502616593.png" width="25px" />ボタンをクリックします。
2. メニューから<strong>［編集］</strong>を選択します。
3. 必要に応じてユーザー設定を編集します。
4. メールアドレス以外のすべての設定（ロール、アプリ、メディアソース、地域など）を編集できます。
5. **Save**をクリックします。

<div id="multi-user-editing" />

#### 複数のユーザーをまとめて編集する

複数ユーザーの一括編集では、複数のユーザーのアカウント権限を一度に効率よく変更できます。<strong>［ユーザー］</strong>タブの検索・絞り込みと組み合わせると、多数のユーザーを管理する場合に便利です。

<div id="note-4" />

> 📘 **注意**
>
> 一括編集では、ユーザーにAdminロールを割り当てることはできません。

**複数のユーザーを編集するには、次の手順に従います。**

1. <strong>［ユーザー］</strong>タブで、編集するユーザーのチェックボックスを選択します。
   * 列見出しのチェックボックスを選択すると、表示中のすべてのユーザーを選択できます。
   * 選択中のユーザー数は、検索ボックスの右側に表示されます。[アカウント所有者](#アカウント所有者)は選択できず、選択人数にも含まれません。
2. 表の右上に、**［ロール］、［アプリ］、［メディアソース］**、<strong>［地域］</strong>のボタンが表示されます。
   * 選択したユーザーの中に、今後追加されるアプリへのアクセス権限を持つユーザーがいる場合、<strong>［アプリ］</strong>ボタンは利用できません。（以下の[暫定ロールの制限事項](/docs/user-management#暫定ロールの制限事項)を参照してください。）
3. 変更する権限のボタンをクリックします。
4. 表示されたダイアログやドロップダウンリストで、必要な変更を行います。
   * 変更内容は、選択したすべてのユーザーに適用される点に注意してください。
5. 編集したユーザーは表内で強調表示され、保存後の状態を確認できます。この時点ではまだ保存されていないため、次の手順で変更内容を確認し、確定またはキャンセルできます。
6. 変更内容を確認します。確定する場合は<strong>［保存］</strong>、取り消す場合は<strong>［キャンセル］</strong>をクリックします。

<div id="example" />

> 📄 **例**
>
> * アカウントに30人のユーザーがいます。そのうち10人に、**Marketing – limited**ロールが割り当てられています。
> * Alice、Bill、Charlieが昇進したため、3人のロールを**Marketing – limited**から**Marketing**に変更するとします。
> * AliceはAstoundingアプリを担当します。 BillはBeautifulアプリを担当します。 CharlieはCharmingアプリを担当します。
>
> **手順：**
>
> 1. ロールフィルター<Image alt="filter_icon.png" src="https://files.readme.io/1ceaac3efead3a218909988be1d50a2f0af93b07360f7197cd398b11d661992b-16162502598417.png" width="25px" />を使い、**Marketing–limited**ロールのユーザーだけを表示します。
> 2. Alice、Bill、Charlieのロールを**Marketing**に変更します。
>    * Alice、Bill、Charlieのチェックボックスを選択します。
>    * <strong>［ロール］</strong>ボタンをクリックします。
>    * ドロップダウンリストから**Marketing**を選択します。
>    * <strong>［保存］</strong>をクリックして確定します。
>    * 変更を確定すると、<strong>［ロール］</strong>のフィルターが解除され、すべてのユーザーが表示されます。
> 3. Alice、Bill、Charlieに、それぞれ適切なアプリへのアクセスを許可します。
>    * 検索ボックスでAliceを検索し、個別に編集してAstoundingアプリへのアクセスを許可します。
>    * BillとCharlieにも同じ操作を行い、それぞれBeautifulアプリとCharmingアプリへのアクセスを許可します。

</Accordion>

<div id="deleting-users" />

<Accordion title="ユーザーの削除">

複数のユーザーをアカウントからまとめて削除できます。

<div id="note-5" />

> 📘 **注意**
>
> * [アカウント所有者](/docs/user-management#アカウント所有者)は削除できません。
> * 削除したユーザーは元に戻せません。

<span id="to-delete-users"></span>**ユーザーを削除するには、次の手順に従います。**

1. <strong>［ユーザー］</strong>タブで、削除するユーザーのチェックボックスを選択します。検索やフィルターを使うと、ユーザーを見つけやすくなります。
2. ユーザーを選択すると表の右上に表示される<strong>［削除］</strong>ボタンをクリックします。
3. 確認ウィンドウに、削除対象のユーザーが表示されます。<strong>［はい、削除します］</strong>をクリックして削除を確定します。

</Accordion>

<div id="manage-users-in-bulk-via-api" />

### APIによるユーザーの一括管理

次のユーザー管理操作は、<Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/bulk-users-management-overview">専用API</Anchor>を使って一括で実行できます。

* 複数のユーザーの[作成](https://dev.appsflyer.com/hc/reference/bulk-users-post)
* 複数のユーザーの<Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/bulk-users-delete">削除</Anchor>
* 複数のユーザーのアクセス権限情報の<Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/bulk-users-get">取得</Anchor>

このAPIは、管理画面の主なユーザー管理機能に対応し、同じエラー検証も行います。

<div id="manage-roles" />

## ロールの管理

AppsFlyerアカウントの各ユーザーには、ロールを割り当てる必要があります。ロールは、ユーザーがアクセスできるAppsFlyerの機能と、実行できる操作を定義します。ロールごとの操作権限の一覧は、<strong>［ユーザー管理］</strong>ページの[［ロール］タブ](#roles-tab)で確認できます。

AppsFlyerのロールには、[定義済みロール](#定義済みロール)、[カスタムロール](#カスタムロール)、特定の場合に使用する[暫定ロール](#暫定ロール)があります。

<div id="predefined-roles" />

### 定義済みロール

AppsFlyerには、次の定義済みロールが用意されています。

* [Admin（特別な権限を持つ管理者ロール）](#admin)
* Team manager
* Marketing lead
* Marketing
* Marketing – limited
* Contributor
* Accounting
* Security
* Quality Assurance

<div id="note-6" />

> 📘 **注意**
>
> 定義済みロールの操作権限は固定されており、個別の権限を自由に組み合わせることはできません。ただし、別の定義済みロールやカスタムロールに変更することで、ユーザーの操作権限をいつでも変更できます（後述の[アカウント所有者](#アカウント所有者)を除く）。

<div id="example-1" />

> 📄 **例**
>
> Bill Batesに**Team manager**ロールを割り当てたとします。このロールでは**OneLinkテンプレート**を管理できますが、<strong>［マイプラン］</strong>や<strong>［支払い］</strong>ページにはアクセスできません。
>
> **質問：** BillのロールをTeam managerのままにして、［マイプラン］や［支払い］ページへのアクセスも許可できますか？ OneLinkテンプレートの管理権限を外すことはできますか？
>
> **回答：** できません。 Team managerロールのままでは、［マイプラン］や［支払い］ページへのアクセスを追加できません。 OneLinkテンプレートの管理権限を外すこともできません。別の定義済みロールを割り当てると、Billの権限は、そのロールに定義されたものに変更されます。または、Bill向けのカスタムロールを作成し、必要な操作権限を設定できます。

### Admin

AppsFlyerアカウントには、**1人以上のAdmin**を登録できます。このロールには、次の特徴があります。

<div id="access" />

#### アクセス

Adminロールは、次のものを含む**アカウントのすべての機能とデータ**にアクセスできます。

* すべての機能と操作
* 現在のすべてのアプリと、今後追加されるアプリ
* すべてのメディアソースと地域

Adminロールがすべてにアクセスできるという特性は、変更・制限できません。

<div id="manage-tokens" />

#### トークンの管理

APIトークンやサーバー間トークンの作成、名前の変更、削除といった<Anchor target="_blank" href="/marketers/ja/docs/managing-appsflyer-tokens">トークンの管理</Anchor>を行えるのは、Adminロールのユーザーのみです。

<div id="role-duplication" />

#### ロールの複製

[カスタムロール](#カスタムロールの管理)を作成する際に、Adminロールを**複製することはできません**。

<div id="invite-new-partners-to-appsflyer" />

#### 新しいパートナーをAppsFlyerに招待する

管理者ロールのユーザーは、パートナーマーケットプレイスから<Anchor target="_blank" href="/marketers/ja/docs/partner-integrations#appsflyerに新規パートナーを招待する">招待リンクを送信</Anchor>し、AppsFlyerとまだ連携していないパートナーを招待できます。

<div id="account-owner" />

### アカウント所有者

アカウント開設時に作成された「アカウント所有者」<strong>には、</strong>デフォルトで**Adminロールが割り当てられます**。ユーザー管理権限を持つほかのユーザーが作成されるまでは、アカウント所有者がユーザーを追加します。

アカウント所有者には、それ以外のAdminロールのユーザーとは異なる特性があります。ほかのAdminと異なり、アカウント所有者は、[**［ユーザー管理］**](/docs/user-management#ユーザー管理ページ)ページからの削除、Adminロールからの変更、そのほかの編集が**できません**。アカウント所有者を変更する必要がある場合は、[以下の手順](#changing-the-account-owner)に従ってください。

<div id="custom-roles" />

### カスタムロール

AppsFlyerの定義済みロールには、一般的な用途に必要な操作権限が組み合わせて設定されています。そのため、多くの広告主は、追加のカスタマイズをせずに利用できます。カスタマイズが必要な場合も、定義済みロールをベースにすると、ユーザーの操作権限を設定しやすくなります。

[カスタムロールの管理](#カスタムロールの管理)の詳細を確認してください。

<div id="temp-roles" />

### 暫定ロール

旧ユーザー管理システム（AdminとTeam memberのみを利用できたシステム）から移行したアカウントでは、すべてのユーザーが従来の操作権限を維持したまま新しいシステムに移行しています。そのため、これらのユーザーの多くは、現在のシステムでは**暫定ロール**として表示されます。

[暫定ロールの管理](#managing-temp-roles)の詳細を確認してください。

<div id="get-roles-data-via-api" />

### APIによるロール情報の取得

<Anchor target="_blank" href="https://dev.appsflyer.com/hc/reference/get_roles">Get roles API</Anchor>を使うと、アカウントの現在のロール一覧と、各ロールの属性を取得できます。

<div id="manage-custom-roles" />

## カスタムロールの管理

<div id="creating-custom-roles" />

<Accordion title="カスタムロールの作成">

* **前提条件：** カスタムロールを作成できるのは、[アカウント所有者](#アカウント所有者)または[Adminロールの権限](#admin)を持つユーザーのみです。

**カスタムロールを作成するには、次の手順に従います。**

1. <strong>［ロール］</strong>タブの左側のパネルで、検索バーの下にある<strong>［＋新しいカスタムロール］</strong>をクリックします。
2. **ロール名：** 新しく作成するロールの名前を入力します。
   * **注意：** カスタムロールの名前は、保存後に変更できません。
   * **推奨：** 後から見ても内容を識別しやすい名前を付けてください。
3. **ロールテンプレート：** 作成するカスタムロールの操作権限に近い定義済みロールを、ベースとして選択します。
4. 選択したロールテンプレートの設定を、必要な内容に調整します。変更可能な操作権限は、それぞれの権限レベルがボタンで表示されます。ボタンをクリックし、新しいカスタムロールの権限レベルを変更します。（下までスクロールして、すべての操作権限を確認してください。）
   * **注意：** ボタンが表示されていない操作権限は、現時点では変更できません。
5. 必要な操作権限をすべて設定したら、<strong>［ロールを保存］</strong>をクリックします。  
   新しいカスタムロールが左側のパネルに表示され、ユーザーの新規作成や編集時に割り当てられるようになります。

</Accordion>

<div id="editing-custom-roles" />

<Accordion title="カスタムロールの編集">

**カスタムロールを編集するには、次の手順に従います。**

1. <strong>［ロール］</strong>タブの左側のパネルで、編集するカスタムロールの名前をクリックします。
2. ページ右上の<strong>［編集］</strong>アイコン <Image alt="edit-icon.jpg" src="https://files.readme.io/d32f150cb5d0271c5504fb3c107e23f73e59c9a3be1630769ad309edf4e79ea0-31780971794321.jpg" width="25px" /> をクリックします。右側のパネルの表示が変わり、ロールの権限設定を編集できるようになります。
   * **注意：** ロール名は変更できません。変更するには、そのロールを削除し、別の名前で新しく作成する必要があります。
3. 変更可能な操作権限は、それぞれの権限レベルがボタンで表示されます。ボタンをクリックし、新しいカスタムロールの権限レベルを変更します。（下までスクロールして、すべての操作権限を確認してください。）
4. すべての設定を確認したら、<strong>［ロールを保存］</strong>ボタンをクリックします。
5. 変更した権限レベルは、新規ユーザーと既存ユーザーの両方に適用されます。

<div id="important-1" />

> 🚧 **重要**
>
> カスタムロールに加えた変更は、そのロールが割り当てられている**すべての既存ユーザー**に自動で適用されます。

</Accordion>

<div id="deleting-custom-roles" />

<Accordion title="カスタムロールの削除">

**カスタムロールを削除するには、次の手順に従います。**

1. <strong>［ロール］</strong>タブの左側のパネルで、削除するカスタムロールの名前をクリックします。
2. ページ右上の<strong>［削除］</strong>アイコン<Image alt="delete-icon.jpg" src="https://files.readme.io/87f206e21926af0836690be064a5af7cb3bce0007f0fc62301b2925701b1d9f9-31780971797265.jpg" width="24px" />をクリックします。
3. ロールの削除を確定します。
   * カスタムロールは、割り当てられているユーザーがいない場合にのみ削除できます。割り当てられているユーザーがいる場合は、先に別のロールへ変更してから削除してください。

</Accordion>

<div id="special-situations-and-additional-procedures" />

## 特殊なケースと追加の手順

<div id="managing-temp-roles" />

<Accordion title="暫定ロールの管理">

旧ユーザー管理システムから移行したアカウントでは、従来の操作権限を維持したまま新しいシステムを利用できるように、既存ユーザーに[**暫定ロール**](/docs/user-management#暫定ロール)が割り当てられています。

* 同じ操作権限を持つユーザーには、同じ暫定ロールが割り当てられています。
* [［ロール］タブ](/docs/user-management#roles-tab)で、暫定ロールごとの操作権限と、割り当てられているユーザーの一覧を確認できます。

<div id="temp-role-limitations" />

#### 暫定ロールの制限事項

暫定ロールは、旧ユーザー管理システムから円滑に移行するために設けられたものです。そのため、利用できる場面には次の制限があります。

* 暫定ロールを、ほかのユーザーに新たに割り当てることはできません（新規・既存を問いません）。
* 暫定ロールのユーザーを別の暫定ロールに変更することはできませんが、アクセス可能なアプリ、メディアソース、地域は変更できます。
  * 暫定ロールのユーザーは、今後追加されるアプリへのアクセス設定を**変更できません**。
* 暫定ロールから定義済みロールに変更したユーザーを、元の暫定ロールや別の暫定ロールに戻すことはできません。
* 暫定ロールに割り当てられた最後のユーザーがそのロールから外れると、そのロールはアカウントに表示されなくなります。

<div id="example-2" />

> 📄 **例**
>
> このアカウントは、以前は旧ユーザー管理システムを使用していました。 DianaとEdwardは、新しいシステムへの移行時点ですでに登録されていたユーザーです。現在、DianaにはTemp role 1、EdwardにはTemp role 2が割り当てられています。
>
> * 新入社員のFionaを採用しました。 Fionaには、いずれかの[定義済みロール](/docs/user-management#定義済みロール)を割り当てられます。ただし、Temp role 1やTemp role 2を割り当てることはできません。
> * DianaをTemp role 1からTemp role 2へ変更することはできません。ただし、いずれかの定義済みロールへの変更は可能です。アプリ、メディアソース、地域へのアクセスも、必要に応じて変更できます。
> * DianaをTemp role 1からAccountingロールに変更すると、後からTemp role 1に戻すことはできません。
> * DianaがTemp role 1の最後のユーザーだった場合、Accountingロールへの変更後、Temp role 1はアカウントに表示されなくなります。

</Accordion>

<div id="dashboard-and-feature-availability-for-users-with-limited-media-sourcegeo-access" />

<Accordion title="メディアソース・地域へのアクセスが制限されたユーザーが利用できるダッシュボードと機能">

特定のメディアソースや地域のみにアクセスできるユーザーは、次のAppsFlyerダッシュボードを**利用できません**。

* SKAN概要
* SKAN Conversion Studio
* Protect360
* 継続率
* People-Based Attribution
* Incrementality

これらのユーザーは、次のAppsFlyer機能も**利用できません**。

* ピボット
* OneLink
* 検証ルール
* Audiences（メディアソースへのアクセスが制限されたユーザーは利用不可。地域へのアクセスが制限されたユーザーは、「国」フィルターを含むオーディエンスのうち、アクセスが許可された国のもののみ利用可能）
* SDK情報
* 広告費データの取り込み
* Cost ETL

</Accordion>

<div id="combined-media-source-and-agency-access" />

<Accordion title="メディアソースと代理店のアクセス権限を組み合わせる場合">

特定の代理店**と**特定のメディアソースへのアクセスを許可した場合、閲覧できるのは両方の条件に該当するデータだけです。その代理店が扱う全メディアソースのデータや、そのメディアソースを扱う全代理店のデータではなく、両方の権限が重なる範囲だけが表示されます。

<div id="example-3" />

> 📄 **例**
>
> ユーザーに代理店BとメディアソースAへのアクセスを許可したとします。代理店Bは、メディアソースAを含む複数のメディアソース経由のインストールを管理しています。このユーザーに表示されるのは、代理店Bが管理するメディアソースA経由のインストールだけであり、代理店Bが扱うほかのメディアソースのデータや、ほかの代理店が管理するメディアソースAのデータは表示されません。

</Accordion>

<div id="changing-the-account-owner" />

<Accordion title="アカウント所有者の変更">

Adminは基本的にアカウント所有者と同じ権限を持つため、通常はアカウント所有者を変更する必要はありません。変更が必要な場合は、次の手順に従ってください。

<div id="important-2" />

> 🚧 **重要**
>
> アカウント所有者の変更は、以下の手順に従って手動で行う必要があります。<strong>［ユーザー管理］</strong>ページからは変更できません。

<div id="1assign-a-team-member-the-admin-role" />

#### 手順1：チームメンバーにAdminロールを割り当てる

アカウント所有者の変更を依頼できるのは、Adminロールのユーザーのみです。そのため、次の対応を推奨します。

* すべての手続きを行えるチームメンバーに、**Admin**ロールを割り当てます。
* そのユーザーは、少なくとも一度ログインして、アカウントを有効化する必要があります。

<div id="2send-an-email-request" />

#### 手順2：メールで変更を依頼する

Adminロールのユーザーが、**現在のアカウント所有者のメールアドレスから**AppsFlyerに変更依頼を送信する必要があります。

* AppsFlyerのアカウントに登録されている、現在のアカウント所有者のメールアドレスを必ず使用してください。
* 現在のアカウント所有者が退職している場合は、そのアドレスからメールを送信できるよう、IT部門に依頼してください。

依頼メールには、次の情報を含めてください。

| 宛先： | 担当のAppsFlyer CSMまたはhello@appsflyer.com |
| --- | --- |
| CC： | 新しいアカウント所有者のメールアドレス |
| 件名： | `{account name}`のアカウント所有者の変更依頼 |
| 本文： | 新しいアカウント所有者の氏名と役職を含む、簡潔な依頼文 |

以下のメール例を参考にしてください。

<Image align="center" alt="account_owner_change_email.png" src="https://files.readme.io/eb10736386a7a8cfc274979a3aa933e23288c74d1b26c0f06d72005ceebafe06-31780969048081.png" />

<div id="3next-steps" />

#### 手順3：変更後の対応

変更処理が完了すると、AppsFlyerからメールで通知されます。

* 以前のアカウント所有者が引き続きAppsFlyerアカウントを利用する場合は、[ユーザーを新規作成](/docs/user-management#creating-users)して、新しいロールを割り当ててください。
* トークンV2を使用するAPIは、アカウント所有者の変更による影響を受けません。<Anchor target="_blank" href="/marketers/ja/docs/managing-appsflyer-tokens">トークンの管理の詳細を確認してください</Anchor>。

</Accordion>

<div id="troubleshooting-can-t-create-this-user" />

<Accordion title="トラブルシューティング｜「このユーザーを作成できません」">

新しいユーザーのメールアドレスを入力した際に*「このユーザーを作成できません」*と表示される場合、通常は、そのアドレスが自分またはほかのアカウントのAppsFlyerユーザーにすでに紐付いています。状況に応じて、次の手順に従ってください。

そのユーザーが自分のアカウントに登録されている場合：

* ユーザーがアカウントを有効化済みか確認します。有効化していない場合は、必要に応じて[招待を再送信](/docs/user-management#resending-a-user-invitation)します。
* 有効化済みの場合は、そのユーザーに紐付くメールアドレスで再度ログインするよう依頼します。必要に応じて、**パスワードを忘れた場合**の手順を案内します。

メールアドレスが別のアカウントで使用されている場合や、使用されているアカウントが分からない場合は、次のいずれかの方法で対応します。

* 別のアカウントから削除して自分のアカウントに追加します（自分または対象ユーザーが、その別のアカウントで必要な権限を持っている必要があります）。または、
* 別のメールアドレスを使用して、自分のアカウントに追加します。実際にメールを受信できる、有効なメールアドレスである必要があります。または、
* 担当のカスタマーサクセスマネージャー（CSM）、またはCustomer Engagementチームの[hello@appsflyer.com](mailto:hello@appsflyer.com)にお問い合わせください。

</Accordion>

<div id="resending-a-user-invitation" />

<Accordion title="ユーザー招待の再送信">

新しいユーザーに[アカウント有効化の招待](#ユーザーの有効化)が届かなかった場合や、48時間以内に有効化しなかった場合は、次の手順でメールを再送信できます。

1. <strong>［ユーザー］</strong>タブで、<strong>［操作］</strong>ボタン <Image alt="actions_icon.png" src="https://files.readme.io/24ad987d1e77d9dfa8559a370733a7b62a6d86954ec1d552eac9c406445ed927-16162502616593.png" width="25px" /> （対象ユーザーの行の右端）をクリックします。
   * 未有効化のユーザーには、その状態を示す封筒アイコン![pending_invitation_icon.png](https://files.readme.io/68ac08ab6e52191a592350f82996f7ade9d181773d0bdbc6e2cb60315b60a8f2-16162502609553.png)が引き続き表示されています。
2. メニューから<strong>［招待メールを再送信］</strong>を選択します。

</Accordion>

<div id="resetting-twofactor-authentication-2fa" />

<Accordion title="ユーザーの2要素認証（2FA）のリセット">

アカウントで2FAを使用している場合、ユーザーの2FA設定をリセットする必要が生じることがあります。次の手順でリセットします。

1. <strong>［ユーザー］</strong>タブで、対象ユーザーの行の右端にある<strong>［操作］</strong>ボタン<Image alt="actions_icon.png" src="https://files.readme.io/24ad987d1e77d9dfa8559a370733a7b62a6d86954ec1d552eac9c406445ed927-16162502616593.png" width="25px" />をクリックします。
2. メニューから<strong>［2FAをリセット］</strong>を選択します。

**注意：** 管理者は、自分自身と[アカウント所有者](#アカウント所有者)を除く、ほかの管理者の2FAをリセットできます。アカウント所有者の2FAをリセットするには、AppsFlyerサポートチームにお問い合わせください。

</Accordion>

<div data-zendesk-anchors="background=%E6%A6%82%E8%A6%81 h_01H9Q9007QP8YMPDVZ57N4M1HD=%E6%A6%82%E8%A6%81 user-management-page=%E3%83%A6%E3%83%BC%E3%82%B6%E3%83%BC%E7%AE%A1%E7%90%86%E3%83%9A%E3%83%BC%E3%82%B8 h_01H9Q9007QW1RD3MTTV01Q8QRE=%E3%83%A6%E3%83%BC%E3%82%B6%E3%83%BC%E7%AE%A1%E7%90%86%E3%83%9A%E3%83%BC%E3%82%B8 h_01J6W88SQ45MA3AZ29K3WMW9PV=users-tab h_01J6W88SQ5B16Q897YMJ7ZNMQX=roles-tab managing-users=%E3%83%A6%E3%83%BC%E3%82%B6%E3%83%BC%E3%81%AE%E7%AE%A1%E7%90%86 h_01H9Q9007QYSJZYZMP0C8NA98G=%E3%83%A6%E3%83%BC%E3%82%B6%E3%83%BC%E3%81%AE%E7%AE%A1%E7%90%86 h_01H9Q9007QH3ME2P8PHC9DJBZV=creating-users user-details=%E3%83%A6%E3%83%BC%E3%82%B6%E3%83%BC%E6%83%85%E5%A0%B1 h_01HMP4EYM562HFSP80MQQ82B47=%E3%83%A6%E3%83%BC%E3%82%B6%E3%83%BC%E6%83%85%E5%A0%B1 h_01H9Q9007Q6SK4391P8C3A147N=%E9%87%8D%E8%A6%81 role=%E3%83%AD%E3%83%BC%E3%83%AB h_01HMP4Q56XP10343YFW17VX00W=%E3%83%AD%E3%83%BC%E3%83%AB app-access=%E3%82%A2%E3%83%97%E3%83%AA%E3%81%B8%E3%81%AE%E3%82%A2%E3%82%AF%E3%82%BB%E3%82%B9 h_01HMP4RDXVRM3Z0WDCJD3P2W8S=%E3%82%A2%E3%83%97%E3%83%AA%E3%81%B8%E3%81%AE%E3%82%A2%E3%82%AF%E3%82%BB%E3%82%B9 data-access=%E3%83%87%E3%83%BC%E3%82%BF%E3%81%B8%E3%81%AE%E3%82%A2%E3%82%AF%E3%82%BB%E3%82%B9 h_01HMP4SW7RMESGDFNP1KFN7641=%E3%83%87%E3%83%BC%E3%82%BF%E3%81%B8%E3%81%AE%E3%82%A2%E3%82%AF%E3%82%BB%E3%82%B9 h_01HR6VBJHTZM48493B29FCWQT8=%E6%B3%A8%E6%84%8F media-sources=%E3%83%A1%E3%83%87%E3%82%A3%E3%82%A2%E3%82%BD%E3%83%BC%E3%82%B9 h_01HRPRS4BHX2AMR9W4FNGE0N1P=%E3%83%A1%E3%83%87%E3%82%A3%E3%82%A2%E3%82%BD%E3%83%BC%E3%82%B9 01HRPRSF0F8ENJ9ZAE1ZDTMAMB=%E6%B3%A8%E6%84%8F-1 geos=%E5%9C%B0%E5%9F%9F h_01HRPRVXYFX4P2ZG0H5HPNF2AG=%E5%9C%B0%E5%9F%9F user-activation=%E3%83%A6%E3%83%BC%E3%82%B6%E3%83%BC%E3%81%AE%E6%9C%89%E5%8A%B9%E5%8C%96 h_01HFRCWNR8T5J990TV68K6B45T=%E3%83%A6%E3%83%BC%E3%82%B6%E3%83%BC%E3%81%AE%E6%9C%89%E5%8A%B9%E5%8C%96 h_01HFRFRQXD1RD66EBRQH0T7Q78=%E6%B3%A8%E6%84%8F-2 01HFRF6SENRY51A4ZAQJTMTDA3=multiple-accounts log-in-to-multiple-accounts=%E8%A4%87%E6%95%B0%E3%82%A2%E3%82%AB%E3%82%A6%E3%83%B3%E3%83%88%E3%81%B8%E3%81%AE%E3%83%AD%E3%82%B0%E3%82%A4%E3%83%B3 h_01J2GN6ZA29SFC12HR4ZVBDFDT=%E8%A4%87%E6%95%B0%E3%82%A2%E3%82%AB%E3%82%A6%E3%83%B3%E3%83%88%E3%81%B8%E3%81%AE%E3%83%AD%E3%82%B0%E3%82%A4%E3%83%B3 h_01M2ZBMHB9P3FEAFDA637ZH4MC=%E6%B3%A8%E6%84%8F-3 supported-accounts-and-users=%E5%AF%BE%E5%BF%9C%E3%81%99%E3%82%8B%E3%82%A2%E3%82%AB%E3%82%A6%E3%83%B3%E3%83%88%E3%81%A8%E3%83%A6%E3%83%BC%E3%82%B6%E3%83%BC h_01H9Z7XXE0CKRSE191ZN017MGE=%E5%AF%BE%E5%BF%9C%E3%81%99%E3%82%8B%E3%82%A2%E3%82%AB%E3%82%A6%E3%83%B3%E3%83%88%E3%81%A8%E3%83%A6%E3%83%BC%E3%82%B6%E3%83%BC limitations-on-adding-users-to-multiple-accounts=%E8%A4%87%E6%95%B0%E3%82%A2%E3%82%AB%E3%82%A6%E3%83%B3%E3%83%88%E3%81%B8%E3%81%AE%E3%83%A6%E3%83%BC%E3%82%B6%E3%83%BC%E8%BF%BD%E5%8A%A0%E3%81%AB%E9%96%A2%E3%81%99%E3%82%8B%E5%88%B6%E9%99%90%E4%BA%8B%E9%A0%85 01J2GMV7ZYV5G0Q6C18RRY1TY0=%E8%A4%87%E6%95%B0%E3%82%A2%E3%82%AB%E3%82%A6%E3%83%B3%E3%83%88%E3%81%B8%E3%81%AE%E3%83%A6%E3%83%BC%E3%82%B6%E3%83%BC%E8%BF%BD%E5%8A%A0%E3%81%AB%E9%96%A2%E3%81%99%E3%82%8B%E5%88%B6%E9%99%90%E4%BA%8B%E9%A0%85 add-users-to-multiple-accounts=%E5%90%8C%E3%81%98%E3%83%A6%E3%83%BC%E3%82%B6%E3%83%BC%E3%82%92%E8%A4%87%E6%95%B0%E3%81%AE%E3%82%A2%E3%82%AB%E3%82%A6%E3%83%B3%E3%83%88%E3%81%AB%E8%BF%BD%E5%8A%A0%E3%81%99%E3%82%8B h_01H9G1MP3Z7VCQQ8ZSQDGSWPC3=%E5%90%8C%E3%81%98%E3%83%A6%E3%83%BC%E3%82%B6%E3%83%BC%E3%82%92%E8%A4%87%E6%95%B0%E3%81%AE%E3%82%A2%E3%82%AB%E3%82%A6%E3%83%B3%E3%83%88%E3%81%AB%E8%BF%BD%E5%8A%A0%E3%81%99%E3%82%8B h_01H9Q9007RTMXVRMR4RM6J80CW=editing-users individual-editing=%E5%80%8B%E5%88%A5%E3%81%AB%E7%B7%A8%E9%9B%86%E3%81%99%E3%82%8B h_01H9Q9007R3QW4AYRJBTF0X7B9=%E5%80%8B%E5%88%A5%E3%81%AB%E7%B7%A8%E9%9B%86%E3%81%99%E3%82%8B multiuser-editing=%E8%A4%87%E6%95%B0%E3%81%AE%E3%83%A6%E3%83%BC%E3%82%B6%E3%83%BC%E3%82%92%E3%81%BE%E3%81%A8%E3%82%81%E3%81%A6%E7%B7%A8%E9%9B%86%E3%81%99%E3%82%8B h_01H9Q9007R4JQPKQS2HVB251GH=%E8%A4%87%E6%95%B0%E3%81%AE%E3%83%A6%E3%83%BC%E3%82%B6%E3%83%BC%E3%82%92%E3%81%BE%E3%81%A8%E3%82%81%E3%81%A6%E7%B7%A8%E9%9B%86%E3%81%99%E3%82%8B h_01H9Q9007R9M9YDMJ2YYNZDW3D=%E6%B3%A8%E6%84%8F-4 h_01H9Q9007RAFXB899YK6CADD9R=%E4%BE%8B h_01H9Q9007RF8QKS7YBZ1GRXVCF=deleting-users h_01HGTR4NEBYJZTW4BA5V9JJX5X=%E6%B3%A8%E6%84%8F-5 h_01HGTK2664A0R2RBJM37EYWNZG=to-delete-users manage-users-in-bulk-via-api=api%E3%81%AB%E3%82%88%E3%82%8B%E3%83%A6%E3%83%BC%E3%82%B6%E3%83%BC%E3%81%AE%E4%B8%80%E6%8B%AC%E7%AE%A1%E7%90%86 h_01HYASD07FG0HGX22FTHEQ9APP=api%E3%81%AB%E3%82%88%E3%82%8B%E3%83%A6%E3%83%BC%E3%82%B6%E3%83%BC%E3%81%AE%E4%B8%80%E6%8B%AC%E7%AE%A1%E7%90%86 more-about-roles=%E3%83%AD%E3%83%BC%E3%83%AB%E3%81%AE%E7%AE%A1%E7%90%86 h_01H9Q9007Q8CMR2RD6E4KN26YE=%E3%83%AD%E3%83%BC%E3%83%AB%E3%81%AE%E7%AE%A1%E7%90%86 predefined-roles=%E5%AE%9A%E7%BE%A9%E6%B8%88%E3%81%BF%E3%83%AD%E3%83%BC%E3%83%AB h_01H9Q9007Q28D43B6JRP71NDQM=%E5%AE%9A%E7%BE%A9%E6%B8%88%E3%81%BF%E3%83%AD%E3%83%BC%E3%83%AB h_01J6VZ7ANV3JHJZ5EVBF1BY585=%E6%B3%A8%E6%84%8F-6 h_01H9Q9007QXSGG375PR2SCS7QS=%E4%BE%8B-1 admin%E2%80%94a-special-role=admin h_01H9Q9007Q4A6KETAAGAWEPQQ9=admin access=%E3%82%A2%E3%82%AF%E3%82%BB%E3%82%B9 h_01HF8N2Z8ZP3HV06XJPMQ19DTK=%E3%82%A2%E3%82%AF%E3%82%BB%E3%82%B9 manage-tokens=%E3%83%88%E3%83%BC%E3%82%AF%E3%83%B3%E3%81%AE%E7%AE%A1%E7%90%86 h_01HV1F5S0FE083B73P8MEYX4FM=%E3%83%88%E3%83%BC%E3%82%AF%E3%83%B3%E3%81%AE%E7%AE%A1%E7%90%86 role-duplication=%E3%83%AD%E3%83%BC%E3%83%AB%E3%81%AE%E8%A4%87%E8%A3%BD h_01HF8N6DKWYKMBE35QKKB55KEM=%E3%83%AD%E3%83%BC%E3%83%AB%E3%81%AE%E8%A4%87%E8%A3%BD invite-new-partners-to-appsflyer=%E6%96%B0%E3%81%97%E3%81%84%E3%83%91%E3%83%BC%E3%83%88%E3%83%8A%E3%83%BC%E3%82%92appsflyer%E3%81%AB%E6%8B%9B%E5%BE%85%E3%81%99%E3%82%8B h_01HVK8EB3SMC09VD8TJND9YWCD=%E6%96%B0%E3%81%97%E3%81%84%E3%83%91%E3%83%BC%E3%83%88%E3%83%8A%E3%83%BC%E3%82%92appsflyer%E3%81%AB%E6%8B%9B%E5%BE%85%E3%81%99%E3%82%8B account-owner=%E3%82%A2%E3%82%AB%E3%82%A6%E3%83%B3%E3%83%88%E6%89%80%E6%9C%89%E8%80%85 h_01HF8N69VYE3ZJVFW1ENC0XA62=%E3%82%A2%E3%82%AB%E3%82%A6%E3%83%B3%E3%83%88%E6%89%80%E6%9C%89%E8%80%85 custom-roles=%E3%82%AB%E3%82%B9%E3%82%BF%E3%83%A0%E3%83%AD%E3%83%BC%E3%83%AB h_01H9Q9007QZ7F2TX8B9D1TNYPN=%E3%82%AB%E3%82%B9%E3%82%BF%E3%83%A0%E3%83%AD%E3%83%BC%E3%83%AB temp-roles=%E6%9A%AB%E5%AE%9A%E3%83%AD%E3%83%BC%E3%83%AB h_01H9Q9007QE8YT1DNRPNTFQWYH=%E6%9A%AB%E5%AE%9A%E3%83%AD%E3%83%BC%E3%83%AB get-roles-data-via-api=api%E3%81%AB%E3%82%88%E3%82%8B%E3%83%AD%E3%83%BC%E3%83%AB%E6%83%85%E5%A0%B1%E3%81%AE%E5%8F%96%E5%BE%97 h_01J6VZ2XP6HM6NJ2TB5DJXD6SA=api%E3%81%AB%E3%82%88%E3%82%8B%E3%83%AD%E3%83%BC%E3%83%AB%E6%83%85%E5%A0%B1%E3%81%AE%E5%8F%96%E5%BE%97 managing-custom-roles=%E3%82%AB%E3%82%B9%E3%82%BF%E3%83%A0%E3%83%AD%E3%83%BC%E3%83%AB%E3%81%AE%E7%AE%A1%E7%90%86 h_01H9Q9007RQHHNHZ3M38E88YPW=%E3%82%AB%E3%82%B9%E3%82%BF%E3%83%A0%E3%83%AD%E3%83%BC%E3%83%AB%E3%81%AE%E7%AE%A1%E7%90%86 h_01H9Q9007RYZD19CFNSM60EARZ=creating-custom-roles h_01H9Q9007R6E6JGD8BC2WY8G3G=editing-custom-roles h_01H9Q9007RANMZP4T6S8R6WA1B=%E9%87%8D%E8%A6%81-1 h_01H9Q9007R16190B6RB884FY61=deleting-custom-roles special-situations-and-additional-procedures=%E7%89%B9%E6%AE%8A%E3%81%AA%E3%82%B1%E3%83%BC%E3%82%B9%E3%81%A8%E8%BF%BD%E5%8A%A0%E3%81%AE%E6%89%8B%E9%A0%86 h_01H9Q9007RSWFVAZQ5DNVNN7T2=%E7%89%B9%E6%AE%8A%E3%81%AA%E3%82%B1%E3%83%BC%E3%82%B9%E3%81%A8%E8%BF%BD%E5%8A%A0%E3%81%AE%E6%89%8B%E9%A0%86 h_01H9Q9007RNZ28128XDB76ZVZC=managing-temp-roles temp-role-limitations=%E6%9A%AB%E5%AE%9A%E3%83%AD%E3%83%BC%E3%83%AB%E3%81%AE%E5%88%B6%E9%99%90%E4%BA%8B%E9%A0%85 h_01H9Q9007RJ0CQRGEYNEQJ2QR5=%E6%9A%AB%E5%AE%9A%E3%83%AD%E3%83%BC%E3%83%AB%E3%81%AE%E5%88%B6%E9%99%90%E4%BA%8B%E9%A0%85 h_01H9Q9007RHBYD2B6PHQRD7TWV=%E4%BE%8B-2 h_01H9Q9007RRY6QERXQ0C4FSYCN=dashboard-and-feature-availability-for-users-with-limited-media-sourcegeo-access h_01K7B3N5G8R2M4X9Y1D6W0T3PQ=combined-media-source-and-agency-access h_01K7B3N7H9S3N5Y0Z2E7X1U4RT=%E4%BE%8B-3 h_01H9Q9007R221KXA7DFTXJY0PE=changing-the-account-owner h_01H9Q9007RR4M8V599A19B2M0F=%E9%87%8D%E8%A6%81-2 1%E2%80%93send-an-email-request=%E6%89%8B%E9%A0%861%E3%83%81%E3%83%BC%E3%83%A0%E3%83%A1%E3%83%B3%E3%83%90%E3%83%BC%E3%81%ABadmin%E3%83%AD%E3%83%BC%E3%83%AB%E3%82%92%E5%89%B2%E3%82%8A%E5%BD%93%E3%81%A6%E3%82%8B h_01H9Q9007RSA5406WXCB1E4JRK=%E6%89%8B%E9%A0%861%E3%83%81%E3%83%BC%E3%83%A0%E3%83%A1%E3%83%B3%E3%83%90%E3%83%BC%E3%81%ABadmin%E3%83%AD%E3%83%BC%E3%83%AB%E3%82%92%E5%89%B2%E3%82%8A%E5%BD%93%E3%81%A6%E3%82%8B h_01K5P1G80QACK6YMKX4AGJA5ZK=%E6%89%8B%E9%A0%862%E3%83%A1%E3%83%BC%E3%83%AB%E3%81%A7%E5%A4%89%E6%9B%B4%E3%82%92%E4%BE%9D%E9%A0%BC%E3%81%99%E3%82%8B 2%E2%80%93next-steps=%E6%89%8B%E9%A0%863%E5%A4%89%E6%9B%B4%E5%BE%8C%E3%81%AE%E5%AF%BE%E5%BF%9C h_01H9Q9007RZ2X9RAY8067SZETF=%E6%89%8B%E9%A0%863%E5%A4%89%E6%9B%B4%E5%BE%8C%E3%81%AE%E5%AF%BE%E5%BF%9C troubleshooting-can%E2%80%99t-create-this-user=troubleshooting-can-t-create-this-user h_01H9Q9007RR4VYEPGT90MEHV3T=troubleshooting-can-t-create-this-user h_01H9Q9007R11BQWQZC66X5FV0N=resending-a-user-invitation h_01H9Q9007R72FAH89XW58MWCXT=resetting-twofactor-authentication-2fa" />
