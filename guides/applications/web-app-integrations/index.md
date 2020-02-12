---
rank: 4
related_endpoints: []
related_guides: []
required_guides: []
related_resources: []
alias_paths:
  - /docs/web-application-integrations
  - /docs/box-web-application-integrations
category_id: applications
subcategory_id: applications/web-app-integrations
id: applications/web-app-integrations
type: guide
is_index: true
total_steps: 3
sibling_id: applications
parent_id: applications
next_page_id: ''
previous_page_id: applications/web-app-integrations/configure
---
# ウェブアプリ統合

Box Platformにより、アプリケーションはBoxウェブアプリ内で直接Boxユーザーに機能を提供できるようになります。ウェブアプリ統合によって、アプリケーションはBox内で使用できるようになり、ユーザーはサードパーティ製アプリケーションを使用してファイルを共有したり編集したりできます。

## 機能

ウェブアプリ統合を使用した場合、ユーザーは、サードパーティ製アプリケーションを使用して、Boxに保存されているドキュメントやフォルダを変更、共有、または編集できます。このアプリケーションでは、さまざまなBoxコンテンツを操作することも、Boxでサポートされるアクションをすべて実行することもできます。また、\[統合]ポップアップメニューを介してBoxユーザーに新機能を提供できます。

<ImageFrame border shadow width="400" center>

![統合の例](../images/integration-popup.png)

</ImageFrame>

ウェブアプリ統合を有効にすると、アプリケーションをこれらのメニューに追加できるため、ユーザーはそのアプリケーションでファイルを使用できるようになります。統合は、特定のコンテンツタイプとファイル拡張子に制限することができます。

## アプリへのウェブアプリ統合の追加

Boxユーザーがアプリケーションの機能を使用できるようにするには、[OAuth 2.0][oauth2]認証を使用して[開発者コンソール][devconsole]で[カスタムアプリ][custom-app]を作成します。

その後、必要なBox APIの機能をサポートするよう構成し、[Boxアプリギャラリー][app-gallery]からリリースする必要があります。

アプリケーションがアプリギャラリーでリリースされたら、ユーザーはアプリギャラリーにアクセスすることで自分のBoxアカウントにそのアプリケーションを追加し、ファイルやフォルダで表示されるコンテキストメニューからその機能を使用できます。

[app-gallery]: g://applications/app-gallery

[custom-app]: g://applications/custom-apps/oauth2-setup

[oauth2]: g://authentication/oauth2

[devconsole]: https://app.box.com/developers/console
