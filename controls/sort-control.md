# Sort DropDown Control

The sort dropdown control is used to sort HTML elements by the specified CSS selector using the HTML SELECT element. It is possible to sort text and numerical content.

```markup
<select data-grid-control="sort">
    <option data-type="initial" selected>Sort by</option>
    <option data-path=".title" data-direction="asc" data-type="text">Sort by title asc</option>
    <option data-path=".title" data-direction="desc" data-type="text">Sort by title desc</option>
    <option data-path=".price" data-direction="asc" data-type="number">Sort by price asc</option>
    <option data-path=".price" data-direction="desc" data-type="number">Sort by price desc</option>
</select>
```

#### Select data attributes

| Data Attribute    | Value                   | Description                                                                                        | Required |
| ----------------- | ----------------------- | -------------------------------------------------------------------------------------------------- | -------- |
| data-grid-control | sort                    | This attribute defines the control type.                                                           | Required |
| data-id           | any alphanumeric string | <p>This attribute may be used in the deep-link, </p><p>local storage, or complex filter logic.</p> | Optional |

#### Option elements data attributes

| Data Attribute | Value                 | Description                                            | Required |
| -------------- | --------------------- | ------------------------------------------------------ | -------- |
| data-path      | any CSS selector      | It defines the path to the item that should be sorted. | Optional |
| data-direction | asc, desc             | Sort direction                                         | Optional |
| data-type      | text, number, initial | Sort type                                              | Optional |
| data-skip      | \[^a-zA-Z0-9]+        | Defines a regex of characters that should be skipped.  | Optional |
| selected       |                       | The selected option                                    | Optional |

{% hint style="info" %}
The selected option should be marked with the **selected** attribute.
{% endhint %}

#### Sort Types

| Sort Type | Description                                                                    |
| --------- | ------------------------------------------------------------------------------ |
| text      | Sort by text content.                                                          |
| number    | Sort by numeric content.                                                       |
| initial   | <p>Sort by initial document order.</p><p><em>Added in DataGrid v1.0.2</em></p> |

