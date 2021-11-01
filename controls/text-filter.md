# Text Filter

The text filter control is used to find HTML elements that match the user input.

```markup
<input
    type="text"
    placeholder="Filter by title"
    data-grid-control="text-filter"
    data-path=".title"
/>
```

| Data Attribute    | Value                                                                        | Description                                                                                        | Required |
| ----------------- | ---------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------- | -------- |
| data-grid-control | text-filter                                                                  | This attribute defines the control type.                                                           | Required |
| data-path         | any CSS selector                                                             | It defines the path to the item that should be filtered.                                           | Optional |
| data-mode         | <ul><li>contains</li><li>startsWith</li><li>endsWith</li><li>equal</li></ul> | Filter mode. The default value is "**contains**".                                                  | Optional |
| data-id           | any alphanumeric string                                                      | <p>This attribute may be used in the deep-link, </p><p>local storage, or complex filter logic.</p> | Optional |
| data-skip         | \[^a-zA-Z0-9]+                                                               | Defines a regex of characters that should be skipped.                                              | Optional |

{% hint style="info" %}
If the filter returns no results, it's possible to add [no results found label](label.md#no-results-label).
{% endhint %}

