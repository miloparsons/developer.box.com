---
rank: 2
related_endpoints:
  - get_webhooks
related_guides:
  - webhooks/manage/for-file
related_resources:
  - webhook
required_guides: []
alias_paths: []
category_id: webhooks
subcategory_id: webhooks/manage
id: webhooks/manage/list-all
type: guide
is_index: false
total_steps: 7
sibling_id: webhooks/manage
parent_id: webhooks/manage
next_page_id: webhooks/manage/for-file
previous_page_id: webhooks/manage
---
# すべてのWebhookのリストを取得

認証済みユーザーのすべてのWebhookのリストを取得するには、[すべてのWebhookのリストを取得][1]APIを使用します。

<Samples id="get_webhooks">

</Samples>

<Message type="warning">

このAPIを使用するには、アプリケーションの\[webhookを管理]スコープが有効になっている必要があります。

</Message>

このAPI呼び出しは、認証済みユーザーのWebhookのみをリストし、会社内の他のユーザーのWebhookはリストしません。

[1]: endpoint://get_webhooks
