---
rank: 1
related_endpoints:
  - get_legal_hold_policies
related_guides:
  - legal-holds/get
related_resources:
  - legal_hold_policies
required_guides: []
alias_paths: []
category_id: legal-holds
subcategory_id: null
id: legal-holds/list
type: guide
is_index: false
total_steps: 2
sibling_id: legal-holds
parent_id: legal-holds
next_page_id: legal-holds/get
previous_page_id: ''
---
# すべてのリーガルホールドポリシーのリストの取得

会社内に作成されたすべてのリーガルホールドポリシーのリストを取得するには、[`GET /legal_hold_policies`][legal_holds] APIエンドポイントを呼び出します。

<Samples id="get_legal_hold_policies">

</Samples>

## 必須のスコープ

リーガルホールドAPIのいずれかを使用する前に、アプリケーションでは適切なスコープを有効にしておく必要があります。詳細については、[必須のスコープ][scopes]を参照してください。

[legal_holds]: e://get_legal_hold_policies

[scopes]: g://legal-holds#required-scopes
