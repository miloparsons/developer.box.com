---
rank: 1
related_endpoints:
  - get_retention_policies
related_guides:
  - retention-policies/get
related_resources:
  - retention_policies
required_guides: []
alias_paths: []
category_id: retention-policies
subcategory_id: null
id: retention-policies/list
type: guide
is_index: false
total_steps: 2
sibling_id: retention-policies
parent_id: retention-policies
next_page_id: retention-policies/get
previous_page_id: ''
---
# すべてのリテンションポリシーのリストの取得

会社内に作成されたすべてのリテンションポリシーのリストを取得するには、[`GET /retention_policies`][retention_policies] APIエンドポイントを呼び出します。

<Samples id="get_retention_policies">

</Samples>

## 必須のスコープ

リテンションポリシーAPIのいずれかを使用する前に、アプリケーションでは適切なスコープを有効にしておく必要があります。詳細については、[必須のスコープ][scopes]を参照してください。

[retention_policies]: e://get_retention_policies

[scopes]: g://retention-policies#required-scopes
