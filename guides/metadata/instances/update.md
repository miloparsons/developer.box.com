---
rank: 1
related_endpoints:
  - put_files_id_metadata_id_id
  - put_folders_id_metadata_id_id
related_guides: []
related_resources:
  - metadata
required_guides: []
alias_paths: []
category_id: metadata
subcategory_id: metadata/instances
id: metadata/instances/update
type: guide
is_index: false
total_steps: 1
sibling_id: metadata/instances
parent_id: metadata/instances
next_page_id: metadata/instances
previous_page_id: ''
---
# メタデータインスタンスの更新

ファイルのメタデータを更新するには、一連のJSON操作を[`PUT /files/:id/metadata_templates/:id/:id`][files_endpoint] APIに渡します。

<Samples id="put_files_id_metadata_id_id">

</Samples>

同様に、フォルダに割り当てられたメタデータを更新するには、一連のJSON操作を[`PUT /files/:id/metadata_templates/:id/:id`][folders_endpoint] APIに渡します。

<Samples id="put_folders_id_metadata_id_id">

</Samples>

## JSON操作

リクエスト本文は[JSON-Patchの仕様][jsonpatch]に従う必要があります。これは、操作オブジェクトのリストとして表されます。

更新には、`add`、`replace`、`remove`、`test`、`move`、または`copy`のいずれかを指定できます。テンプレートインスタンスを更新できるのは、テンプレートがすでにファイルまたはフォルダに割り当てられている場合のみです。

```json
[
  { "op": "test", "path": "/competitiveDocument", "value": "no" },
  { "op": "remove", "path": "/competitiveDocument" },
  { "op": "test", "path": "/status", "value": "active" },
  { "op": "replace", "path": "/status", "value": "inactive" },
  { "op": "test", "path": "/author", "value": "Jones" },
  { "op": "copy", "from": "/author", "path": "/editor" },
  { "op": "test", "path": "/currentState", "value": "proposal" },
  { "op": "move", "from": "/currentState", "path": "/previousState" },
  { "op": "add", "path": "/currentState", "value": "reviewed" }
]
```

どの操作も、`op`の名前、変更対象のフィールドを指す[JSON Pointer][pointer] `path`のほか、実行される操作に応じた`value`または`from`値(省略可)で構成されます。

<Message>

メタデータを編集する際には、メタデータテンプレートのスキーマに準拠した値のみを使用できます。更新は完全に適用されるか、まったく適用されないかのどちらかです。更新操作の適用中にエラーが発生した場合、メタデータインスタンスは変更されません。

</Message>

## 制限

ユーザーのルートフォルダ(ID `0`)に対するフォルダメタデータ操作は許可されていません。このフォルダに対してメタデータ操作を実行しようとすると、`403` HTTPステータスコードが返されます。

[files_endpoint]: e://put_files_id_metadata_id_id

[folders_endpoint]: e://put_folders_id_metadata_id_id

[jsonpatch]: https://tools.ietf.org/html/rfc6902

[pointer]: https://tools.ietf.org/html/rfc6901
