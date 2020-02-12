---
rank: 3
related_endpoints:
  - get_files_id_content
related_guides:
  - downloads/file
  - uploads/direct/file
required_guides: []
related_resources: []
alias_paths: []
category_id: downloads
subcategory_id: null
id: downloads/get-url
type: guide
is_index: false
total_steps: 6
sibling_id: downloads
parent_id: downloads
next_page_id: downloads/folder
previous_page_id: downloads/file-version
---
# ダウンロードURLの取得

Box公式SDKでは、ファイルのダウンロード時にバイナリデータが返されます。代わりにデータのダウンロードURLを取得する場合は、SDKの以下のメソッドを使用します。

<Samples id="get_files_id_content" variant="get_url">

</Samples>

## ダウンロードURLの有効期限

このダウンロードURLは、ファイルのダウンロードを許可するためにユーザーのブラウザに渡すことができますが、このURLが期限切れになると、その後でダウンロードするには再度リクエストする必要があります。

[api]: e://get_files_id_content
