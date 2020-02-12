---
hide: true
category_id: internal
subcategory_id: internal/ui-elements
id: internal/ui-elements/tabs
type: guide
is_index: false
rank: 0
total_steps: 8
sibling_id: internal/ui-elements
parent_id: internal/ui-elements
next_page_id: internal/ui-elements
previous_page_id: ''
---
<!-- does not need translation -->

# タブ

タブに項目を追加するには、最初に`Tabs`オブジェクトを作成してから、その中にタイトルを付けた複数の`Tab`項目を作成します。

```html
<Tabs>
  <Tab title='Node'>
    Node
  </Tab>
  <Tab title='.NET'>
    .NET
  </Tab>
</Tabs>
```

<H>

<Tabs>

<Tab title="Node">

Node

</Tab>

<Tab title=".NET">

.NET

</Tab>

</Tabs>

</H>

タブは、Cookieを使用してユーザーの選択内容を記憶します。標準的なタイトルである`cURL`、`Java`、`.NET`、`Python`、および`Node`を使用して、現在サポートされている言語を参照してください。ユーザーには、ユーザーが選択した言語でサンプルが自動的に表示されます。
