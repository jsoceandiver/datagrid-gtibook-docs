# Radio Button Filter

Radio button filter is used to show or hide HTML elements depending on their path, value and user selection.

```markup
<label>
    <input
        type="radio"
        name="my-radio"
        data-grid-control="radio-filter"
        data-path=".color-red"
    /> Red
</label>

<label>
    <input
        type="radio"
        name="my-radio"
        data-grid-control="radio-filter"
        data-path=".color-blue"
    /> Blue
</label>

<label>
    <input
        type="radio"
        name="my-radio"
        data-grid-control="radio-filter"
        data-path=""
    /> All
</label>
```

| Data Attribute    | Value                 | Description                                                                                         | Required |
| ----------------- | --------------------- | --------------------------------------------------------------------------------------------------- | -------- |
| data-grid-control | radio-filter          | This attribute defines the control type.                                                            | Required |
| data-path         | any CSS selector      | <p>It defines the path to the item </p><p>that should be filtered.</p>                              | Optional |
| data-inverted     | false (default), true | This attribute inverts the filter.                                                                  | Optional |
| checked           | ​Content              | <p>A Boolean attribute indicating whether or not</p><p>this radio button is checked by default.</p> | Optional |

If the **`data-value`** attribute is specified, the filter will look for this text value in the provided **`data-path`**. In this case, the following data attributes may be specified:

| Data Attribute | Value                                                                        | Description                                                                                           | Required |
| -------------- | ---------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------- | -------- |
| data-value     | any text                                                                     | <p>The filter will look for this text </p><p>in the given <strong><code>data-path</code></strong></p> | Optional |
| data-mode      | <ul><li>contains</li><li>startsWith</li><li>endsWith</li><li>equal</li></ul> | Filter mode. The default value is "**equal**".                                                        | Optional |
| data-skip      | \[^a-zA-Z0-9]+                                                               | <p>Defines a regex of characters </p><p>that should be skipped.</p>                                   | Optional |

{% hint style="info" %}
In radio button path filter control, the **`name`** attribute is used instead of **`data-id`** attribute.
{% endhint %}
