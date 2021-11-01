# Select Filter

Select path filter is used to show or hide HTML elements depending on their path and user selection.

```markup
<select data-grid-control="select-filter">
    <option data-path="">Filter by property type</option>
    <option data-path=".property-type-cottage">Cottage</option>
    <option data-path=".property-type-apartment">Apartment</option>
    <option data-path=".property-type-villa">Villa</option>
</select>
```

#### Select data attributes

| Data Attribute    | Value                   | Description                                                                                        | Required |
| ----------------- | ----------------------- | -------------------------------------------------------------------------------------------------- | -------- |
| data-grid-control | select-filter           | This attribute defines the control type.                                                           | Required |
| data-id           | any alphanumeric string | <p>This attribute may be used in the deep-link, </p><p>local storage, or complex filter logic.</p> | Optional |

#### Option elements data attributes

| Data Attribute | Value                 | Description                                            |
| -------------- | --------------------- | ------------------------------------------------------ |
| data-path      | any CSS selector      | It defines the path to the item that should be sorted. |
| data-inverted  | false (default), true | This attribute inverts the filter.                     |

If the **`data-value`** attribute is specified, the filter will look for this text value in the provided **`data-path`**. In this case, the following data attributes may be specified:

| Data Attribute | Value                                                                        | Description                                                                                           | Required |
| -------------- | ---------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------- | -------- |
| data-value     | any text                                                                     | <p>The filter will look for this text </p><p>in the given <strong><code>data-path</code></strong></p> | Optional |
| data-mode      | <ul><li>contains</li><li>startsWith</li><li>endsWith</li><li>equal</li></ul> | Filter mode. The default value is "**equal**".                                                        | Optional |
| data-skip      | \[^a-zA-Z0-9]+                                                               | <p>Defines a regex of characters </p><p>that should be skipped.</p>                                   | Optional |

{% hint style="info" %}
The selected option should be marked with the **selected** attribute.
{% endhint %}
