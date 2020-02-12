---
rank: 1
alias_paths: []
category_id: metadata
subcategory_id: metadata/templates
id: metadata/templates
type: guide
is_index: true
total_steps: 1
sibling_id: metadata
parent_id: metadata
next_page_id: ''
previous_page_id: ''
---
# メタデータテンプレート

[メタデータテンプレート][template]には、ファイルまたはフォルダに割り当てることができる一連のキー/値ペアが記載されています。

たとえば、`invoiceData`テンプレートでは、請求書に関するデータを保持するため、請求書IDと発注書IDのフィールドが設定されています。

ファイルまたはフォルダには、`marketingCollateral`テンプレートインスタンスや`retentionPolicy`テンプレートインスタンスなど、複数の異なるテンプレート[インスタンス][instance]を関連付けることができます。

## テンプレートとキー名

メタデータテンプレートが作成されると、テンプレートの`name`から自動的に`templateKey`が生成されます。その際、名前に含まれるスペースと規格外の文字は削除され、キャメルケース形式に変換されます。

たとえば、`Test Name (with-special_) Characters`という名前のメタデータテンプレートの`templateKey`は`testNameWithspecialCharacters`になります。

その後、このテンプレートキーは、テンプレートの情報を取得したり、項目にテンプレートを割り当てたりするためのAPIリクエストを実行するときに使用されます。

## メタデータのスコープ

テンプレートインスタンスも、2つの異なるグループ、つまり**スコープ**にグループ化されます。

* **`global`**: 所属する会社に関係なく、Boxを使用するすべてのユーザーが使用できるテンプレートのグループ。たとえば、追加のスキーマを関連付けずに自由形式のキー/値の`string`ペアを配置する場所として使用される`global.properties`テンプレートがあります。
* **`enterprise_*`**: 特定の会社で定義されたテンプレートのグループ。これらのテンプレートには、管理者がウェブアプリ内で作成したものもあれば、APIを使用してアプリケーションによって作成されたものもあります。

## 型

テンプレートでは、`string`、`enum`、`float`、`date`という4つの属性の型がサポートされます。日付は、ミリ秒まで正確なRFC3339形式で表されます。

## 制約事項

メタデータテンプレートの作成は、管理者権限を持つユーザーに制限されています。つまり、管理者、または管理者から**会社のメタデータテンプレートの作成および編集**権限が付与されている共同管理者だけがウェブアプリまたはAPIを使用してテンプレートを管理できます。

テンプレートは会社あたり500個までに制限されています。

メタデータテンプレートの構造化方法の詳細については、[こちらのBoxコミュニティページ][community]を参照してください。

[instance]: g://metadata/instances

[template]: g://metadata/templates

[community]: https://community.box.com/t5/How-to-Guides-for-Admins/How-to-Create-the-Right-Metadata-Structure-for-your-Enterprise/ta-p/43960
