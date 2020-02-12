---
rank: 3
alias_paths: []
category_id: metadata
subcategory_id: metadata/cascades
id: metadata/cascades
type: guide
is_index: true
total_steps: 0
sibling_id: metadata
parent_id: metadata
next_page_id: ''
previous_page_id: ''
---
# メタデータカスケードポリシー

メタデータカスケードポリシーでは、フォルダの[メタデータインスタンス][instance]に対する自動カスケード動作を記述して、メタデータがそのフォルダ内のすべての項目に自動的に適用されるようにすることができます。

たとえば、アプリケーションは、プロジェクトIDの値を含む`projectData`メタデータテンプレートをプロジェクトフォルダに割り当てるとします。その後、このテンプレートにカスケードポリシーを割り当てると、Boxは、プロジェクトフォルダ内にある既存および新規のファイルやフォルダすべてに同じメタデータを自動的に適用できます。

## 権限

フォルダの編集権限を持つユーザーは、その特定のフォルダ用にメタデータカスケードポリシーを作成できます。ポリシーは、1つのフォルダとそのフォルダの1つのメタデータインスタンスだけに割り当てられます。

## 制限

ファイルのアップロードからメタデータの適用まで、若干の遅延が生じます。この遅延の程度はフォルダ内の項目の数によって大きく変わります。

[instance]: g://metadata/instances
