---
rank: 3
related_endpoints:
  - get_authorize
related_guides:
  - applications/custom-apps/app-token-setup
required_guides: []
related_resources: []
alias_paths: []
category_id: authentication
subcategory_id: authentication/app-token
id: authentication/app-token/endpoints
type: guide
is_index: false
total_steps: 4
sibling_id: authentication/app-token
parent_id: authentication/app-token
next_page_id: authentication/app-token/rollover
previous_page_id: authentication/app-token/without-sdk
---
# サポートされているエンドポイント

アプリトークン認証で現在サポートされているBox APIは少数です。

| エンドポイント                                      | パス                       |
| -------------------------------------------- | ------------------------ |
| [ファイルをアップロード](e://post-files-content)        | `POST /files/content`    |
| [Download a file](e://get-files-id-content)  | `GET /files/:id/content` |
| [Delete a file](e://delete-files-id-content) | `DELETE /files/:id`      |
| [Get embed link](e://get-files--id)          | `GET /files/:id`         |
