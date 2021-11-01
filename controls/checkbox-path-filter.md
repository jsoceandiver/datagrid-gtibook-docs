# Checkbox Filter

Checkbox path filter is used to show or hide HTML elements depending on their path and user selection.

```markup
<input
    type="checkbox"
    data-grid-control="checkbox-filter"
    data-path=".title"
/>
```

| Data Attribute    | Value                   | Description                                                                                        | Required |
| ----------------- | ----------------------- | -------------------------------------------------------------------------------------------------- | -------- |
| data-grid-control | checkbox-filter         | This attribute defines the control type.                                                           | Required |
| data-path         | any CSS selector        | It defines the path to the item that should be filtered.                                           | Optional |
| data-id           | any alphanumeric string | <p>This attribute may be used in the deep-link, </p><p>local storage, or complex filter logic.</p> | Optional |
| data-inverted     | false (default), true   | This attribute inverts the filter.                                                                 | Optional |
| checked           |                         | <p>A Boolean attribute indicating whether or not </p><p>this checkbox is checked by default.</p>   | Optional |

If the **`data-value`** attribute is specified, the filter will look for this text value in the provided **`data-path`**. In this case, the following data attributes may be specified:

| Data Attribute | Value                                                                        | Description                                                                                           | Required |
| -------------- | ---------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------- | -------- |
| data-value     | any text                                                                     | <p>The filter will look for this text </p><p>in the given <strong><code>data-path</code></strong></p> | Optional |
| data-mode      | <ul><li>contains</li><li>startsWith</li><li>endsWith</li><li>equal</li></ul> | Filter mode. The default value is "**equal**".                                                        | Optional |
| data-skip      | \[^a-zA-Z0-9]+                                                               | <p>Defines a regex of characters </p><p>that should be skipped.</p>                                   | Optional |
