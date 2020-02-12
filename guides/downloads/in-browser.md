---
rank: 4
related_endpoints:
  - get_files_id_content
related_guides:
  - downloads/file
  - uploads/direct/file
required_guides: []
related_resources: []
alias_paths:
  - /docs/download-all-files-from-a-folder-1
category_id: downloads
subcategory_id: null
id: downloads/in-browser
type: guide
is_index: false
total_steps: 6
sibling_id: downloads
parent_id: downloads
next_page_id: downloads
previous_page_id: downloads/get-url
---
# ブラウザでのダウンロード

アプリケーションでは、ファイルをHTML要素としてページに埋め込む場合があります。たとえば、オーディオプレーヤーを使用する場合です。

```html
<audio controls>
  <source src="..." type="audio/mp3">
</audio>
```

この場合、通常の[ダウンロードURL][durl]を使用しても機能しません。`dl.boxcloud.com`ドメインでは[クロスオリジンリソース共有][cors]がサポートされていないためです。

その代わり、アプリケーションでは次の形式を使用できます。

```sh
https://api.box.com/2.0/files/[FILE_ID]/content?access_token=[ACCESS_TOKEN]
```

<Message warning>

# CORS

これを機能させるために、アプリケーションでは、このファイルをホストするウェブサイトのドメインを[CORSの設定][cors]でホワイトリストに登録しておく必要があります。

</Message>

<Message warning>

# トークンのダウンスコープ

この方法を使用すると、アクセストークンがエンドユーザーに公開され、エンドユーザーはこのトークンを使用すると、意図したより多くの操作を行うことができる可能性があります。そのため、状況に応じてこのトークンを[ダウンスコープ][downscoping]することをお勧めします。

</Message>

[durl]: g://downloads/get-url

[cors]: g://best-practices/cors

[downscoping]: g://authentication/access-tokens/downscope
