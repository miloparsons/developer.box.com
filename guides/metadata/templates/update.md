---
rank: 1
related_endpoints:
  - put_metadata_templates_id_id_schema
related_guides: []
related_resources:
  - metadata_template
required_guides: []
alias_paths: []
category_id: metadata
subcategory_id: metadata/templates
id: metadata/templates/update
type: guide
is_index: false
total_steps: 1
sibling_id: metadata/templates
parent_id: metadata/templates
next_page_id: ''
previous_page_id: ''
---
# メタデータテンプレートの更新

メタデータテンプレートを更新するには、一連の操作を[`PUT /metadata_templates/:id/:id/schema`][endpoint] APIに渡します。

<Samples id="put_metadata_templates_id_id_schema">

</Samples>

## 安全な操作

APIに提供されるリストにある各操作は、テンプレートの変換を実行してそのスキーマを変更します。以下に、このAPIで使用できる、以前のテンプレートに影響しない操作のリストを示します。

### テンプレートプロパティの編集

`editTemplate`操作では、`displayName`や`copyInstanceOnItemCopy`など、テンプレートの基本プロパティを編集できます。

| パラメータ  |                                                 |
| ------ | ----------------------------------------------- |
| `data` | An object representing the properties to change |

```json
{
  "op": "editTemplate",
  "data": {
    "displayName": "Client",
    "copyInstanceOnItemCopy": true
  }
}
```

これにより、新しい表示名がClientになるようにテンプレートが更新されます。

### フィールドの追加

`addField`操作では、テンプレートにフィールドを追加します。

| パラメータ  |                                     |
| ------ | ----------------------------------- |
| `data` | An object representing field to add |

```json
{
  "op": "addField",
  "data": {
    "displayName": "Category",
    "key": "category",
    "hidden": false,
    "type": "string"
  }
}
```

これにより、`displayName`および`key`が**category**に指定されている、非表示ではない新しい文字列フィールドが追加されます。

### フィールドの並べ替え

`reorderFields`操作では、テンプレート内のフィールドのリストを、リクエストされたフィールドリストに合わせて並べ替えます。

| パラメータ       |                                                   |
| ----------- | ------------------------------------------------- |
| `fieldKeys` | The new list of field keys in the requested order |

```json
{
  "op": "reorderFields",
  "fieldKeys": ["field2", "field1", "field3"]
}
```

これにより、テンプレートのフィールドは、最初に`field2`、その後`field1`、`field3`が続くように並べ替えられます。

### 列挙型オプションの追加

`addEnumOption`操作では、指定されたフィールドの列挙型オプションリストの末尾に列挙型オプションを追加します。

<!-- markdownlint-disable line-length -->

| パラメータ      |                                                                    |
| ---------- | ------------------------------------------------------------------ |
| `data`     | An object representing the option to add to the enum               |
| `fieldKey` | The key of the field to add the option. This must be an enum field |

<!-- markdownlint-enable line-length -->

```json
{
  "op": "addEnumOption",
  "fieldKey": "category",
  "data": {
    "key": "Technology"
  }
}
```

### 列挙型オプションの並べ替え

`reorderEnumOptions`操作では、列挙型のオプションのリストを並べ替えます。

<!-- markdownlint-disable line-length -->

| パラメータ            |                                                                             |
| ---------------- | --------------------------------------------------------------------------- |
| `fieldKey`       | The key of the field to reorder the options for. This must be an enum field |
| `enumOptionKeys` | The new list of enum option keys in the requested order                     |

<!-- markdownlint-enable line-length -->

```json
{
  "op": "reorderEnumOptions",
  "fieldKey": "category",
  "enumOptionKeys": [
    "option2",
    "option1",
    "option3"
  ]
}.
```

これにより、フィールドカテゴリの列挙型オプションは、最初に`option2`、その後`option1`、`option3`が続くように並べ替えられます。

### 複数選択オプションの並べ替え

`reorderMultiSelectOptions`操作では、複数選択のオプションのリストを並べ替えます。

<!-- markdownlint-disable line-length -->

| パラメータ                   |                                                                                     |
| ----------------------- | ----------------------------------------------------------------------------------- |
| `fieldKey`              | The key of the field to reorder the options for. This must be an multi select field |
| `multiSelectOptionKeys` | The new list of multi select option keys in the requested order                     |

<!-- markdownlint-enable line-length -->

```json
{
  "op": "reorderMultiSelectOptions",
  "fieldKey": "category",
  "multiSelectOptionKeys": [
    "option2",
    "option1",
    "option3"
  ]
}.
```

これにより、フィールドカテゴリの複数選択オプションは、最初に`option2`、その後`option1`、`option3`が続くように並べ替えられます。

### 複数選択オプションの追加

`addMultiSelectOption`操作では、指定されたフィールドの複数選択オプションリストの末尾に複数選択オプションが追加されます。

<!-- markdownlint-disable line-length -->

| パラメータ      |                                                                           |
| ---------- | ------------------------------------------------------------------------- |
| `fieldKey` | The key of the field to add an item to. This must be a multi select field |
| `data`     | The new item to add to the multi select                                   |

<!-- markdownlint-enable line-length -->

```json
{
  "op": "addMultiSelectOption",
  "fieldKey": "category",
  "data": {
    "key": "Technology"
  }
}
```

これにより、`category`フィールドで**Technology**という新しい複数選択オプションが追加されます。

## 危険な操作

APIに提供されるリストにある各操作は、テンプレートの変換を実行してそのスキーマを変更します。以下に、このAPIで使用できる、以前に割り当てたテンプレートのデータを変更する可能性のある操作のリストを示します。

このような変更は、ファイルの変更ではなくテンプレートの変更としてログに記録されます。

### フィールドの編集

`editField`操作オプションでは、`displayName`、`description`、`key`、`hidden`状態など、フィールドの基本プロパティをいくつでも編集できます。

<!-- markdownlint-disable line-length -->

| パラメータ      |                                                                |
| ---------- | -------------------------------------------------------------- |
| `data`     | An object representing the new properties to set for the field |
| `fieldKey` | The key of the field to be edited                              |

<!-- markdownlint-enable line-length -->

```json
{
  "op": "editField",
  "fieldKey": "category",
  "data": {
    "displayName": "Customer Group"
  }
}
```

これにより、新しい表示名が**Customer Group**になるようにフィールド`category`が更新されます。このキーが変更された場合、指定されたフィールドの既存の値は新しいキーに移行されます。検索インデックスは更新されますが、更新にかかる時間は、この変更の対象となるファイルの数によって異なります。

<Message warning>

これは、このテンプレートの既存のインスタンスに影響する可能性があります。

</Message>

### フィールドの削除

`removeField`操作では、テンプレートからフィールドを削除します。

<!-- markdownlint-disable line-length -->

| パラメータ      |                                                  |
| ---------- | ------------------------------------------------ |
| `fieldKey` | The key of the field to remove from the template |

<!-- markdownlint-enable line-length -->

```json
{
  "op": "removeField",
  "fieldKey": "brand"
}
```

これにより、フィールド`brand`は、テンプレートに加えて、テンプレートのすべてのインスタンスから削除されます。検索インデックスは更新されますが、更新にかかる時間は、この変更の対象となるファイルの数によって異なります。

<Message warning>

これは、このテンプレートの既存のインスタンスに影響します。

</Message>

### 列挙型オプションの編集

`editEnumOption`操作では、列挙型のオプションを編集します。

<!-- markdownlint-disable line-length -->

| パラメータ           |                                                                              |
| --------------- | ---------------------------------------------------------------------------- |
| `data`          | An object with the new key of the `enumOption`                               |
| `fieldKey`      | The key of the field the enum option belongs to. Must refer to an enum field |
| `enumOptionKey` | The key of the enum option to be edited                                      |

<!-- markdownlint-enable line-length -->

```json
{
  "op": "editEnumOption",
  "fieldKey": "fy",
  "enumOptionKey": "FY11",
  "data": {
    "key": "FY16"
  }
}
```

これにより、`enumOption`の名前`FY11`が`FY16`に変更されます。この値が設定されているテンプレートの既存のインスタンスは新しいオプションに移行されます。検索インデックスは更新されますが、更新にかかる時間は、この変更の対象となるファイルの数によって異なります。

<Message warning>

これは、このテンプレートの既存のインスタンスに影響します。

</Message>

### 列挙型オプションの削除

`removeEnumOption`操作では、列挙型のオプションを削除します。

<!-- markdownlint-disable line-length -->

| パラメータ           |                                                                              |
| --------------- | ---------------------------------------------------------------------------- |
| `fieldKey`      | The key of the field the enum option belongs to. Must refer to an enum field |
| `enumOptionKey` | The key of the enum option to be removed                                     |

<!-- markdownlint-enable line-length -->

```json
{
  "op": "removeEnumOption",
  "fieldKey": "fy",
  "enumOptionKey": "FY11"
}
```

これにより、フィールド`fy`から`enumOption` `FY11`が削除されます。また、テンプレートのすべてのインスタンスから`enumOption`も削除されます。テンプレートのインスタンスのフィールドがこのオプションに設定されていた場合は、値は設定解除されます。

検索インデックスは更新されますが、更新にかかる時間は、この変更の対象となるファイルの数によって異なります。

<Message warning>

これは、このテンプレートの既存のインスタンスに影響します。

</Message>

### 複数選択オプションの編集

`editMultiSelectOption`操作では、複数選択のオプションを編集します。

<!-- markdownlint-disable line-length -->

| パラメータ                  |                                                                                              |
| ---------------------- | -------------------------------------------------------------------------------------------- |
| `data`                 | An object with the new key of the option                                                     |
| `fieldKey`             | The key of the field the multi select option belongs to. Must refer to an multi select field |
| `multiSelectOptionKey` | The key of the multi select option to be edited                                              |

<!-- markdownlint-enable line-length -->

```json
{
  "op": "editMultiSelectOption",
  "fieldKey": "fy",
  "multiSelectOptionKey": "FY11",
  "data": {
    "key": "FY16"
  }
}
```

これにより、`multiSelectOption`の名前`FY11`が`FY16`に変更されます。この値が設定されているテンプレートの既存のインスタンスは新しいオプションに移行されます。検索インデックスは更新されますが、更新にかかる時間は、この変更の対象となるファイルの数によって異なります。

<Message warning>

これは、このテンプレートの既存のインスタンスに影響します。

</Message>

### 複数選択オプションの削除

`removeMultiSelectOption`操作では、複数選択のオプションを削除します。

<!-- markdownlint-disable line-length -->

| パラメータ                  |                                                                                              |
| ---------------------- | -------------------------------------------------------------------------------------------- |
| `fieldKey`             | The key of the field the multi select option belongs to. Must refer to an multi select field |
| `multiSelectOptionKey` | The key of the multi select option to be removed                                             |

<!-- markdownlint-enable line-length -->

```json
{
  "op": "removeMultiSelectOption",
  "fieldKey": "fy",
  "multiSelectOptionKey": "FY11"
}
```

これにより、フィールド`fy`から`multiSelectOption` `FY11`が削除されます。また、テンプレートのすべてのインスタンスから`multiSelectOption`も削除されます。テンプレートのインスタンスのフィールドがこのオプションに設定されていた場合は、値は設定解除されます。

検索インデックスは更新されますが、更新にかかる時間は、この変更の対象となるファイルの数によって異なります。

<Message warning>

これは、このテンプレートの既存のインスタンスに影響します。

</Message>

[endpoint]: e://put_metadata_templates_id_id_schema
