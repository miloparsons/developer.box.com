---
rank: 2
related_endpoints: []
related_resources: []
related_guides:
  - authentication
required_guides:
  - applications/select
alias_paths:
  - /docs/how-to-get-an-api-key
category_id: authentication
subcategory_id: authentication/access-tokens
id: authentication/access-tokens/api-calls
type: guide
is_index: false
total_steps: 8
sibling_id: authentication/access-tokens
parent_id: authentication/access-tokens
next_page_id: authentication/access-tokens/sdks
previous_page_id: authentication/access-tokens/resource
---
# トークンの使用

すべての認証済みAPI呼び出しでは、`Bearer Token`としてアクセストークンを`Authorization`ヘッダーに含めて渡す必要があります。そうしないと、`401 Unautorized` HTTPステータスが返されます。

```curl
curl https://api.box.com/2.0/users/me \
    -H "Authorization: Bearer EGmDmRVfhfHsqesn5yVYHAqUkD0dyDfk"
```

<Message>

アクセストークンが認証されるユーザーを調べるには、[`GET /users/me`](endpoint://get-users-id)エンドポイントを使用してください。

</Message>
