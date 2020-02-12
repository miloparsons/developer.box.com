---
rank: 160
alias_paths:
  - /docs/work-with-metadata
category_id: metadata
subcategory_id: null
id: metadata
type: guide
is_index: true
total_steps: 0
sibling_id: guides
parent_id: guides
next_page_id: ''
previous_page_id: ''
---
# メタデータ

メタデータを使用すると、ユーザーやアプリケーションは、所有するファイルやフォルダに関連付けられたカスタムデータを定義、保存できます。

メタデータは、ファイルまたはフォルダに属するキー/値ペアで構成されます。たとえば、重要な契約には、`clientNumber: 820183`と`clientName: bioMedicalCorp`のキー/値ペアが使用されている場合があります。

## テンプレート、インスタンス、およびカスケード

メタデータを操作するには、開発者は3つの異なる種類のリソースを使用する必要があります。

* **テンプレート:** [メタデータテンプレート][template]には、ファイルに割り当てることができる一連のキー/値ペアが記載されています。たとえば、`invoiceData`テンプレートでは、請求書に関するデータを保持するため、請求書IDと発注書IDのフィールドが設定されています。
* **インスタンス:** [メタデータインスタンス][instance]には、メタデータの値など、テンプレートとファイルやフォルダ間の関係が記載されています。たとえば、ユーザーは、`invoiceData`メタデータテンプレートをファイルに割り当て、2つの値を指定しています。この場合、1つは請求書ID用、もう1つは発注書ID用です。
* **カスケード**: [メタデータカスケードポリシー][cascade]には、フォルダのメタデータテンプレートに対する自動カスケード機能が記載されています。たとえば、ユーザーは、同じ`invoiceData`メタデータテンプレートをプロジェクトフォルダに割り当てると(2つの値を含む)、そのフォルダ内のすべてのファイルとフォルダに自動的に適用できます。

## メタデータを使用する理由

メタデータは多くの目的で使用できます。会社がマーケティングチーム向けにデジタルアセットを効率よく編成する場合もあれば、開発者がワークフローや承認の促進のような高度なコンテンツ機能を提供する場合もあります。

たとえば、`marketingCollateral`テンプレートでは、特定のマーケティングコンテンツを使用する状況とタイミングを定義できます。ユーザーは、Boxウェブアプリでテンプレートのレプリゼンテーションを確認すると同時に、ファイルのプレビューに移動できます。

詳細については、[Boxコミュニティの記事][community]を参照してください。

[community]: https://community.box.com/t5/Organizing-and-Tracking-Content/Using-Metadata/ta-p/30765

[template]: g://metadata/templates

[instance]: g://metadata/instances

[cascade]: g://metadata/cascades
