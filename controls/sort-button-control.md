# Sort Button Control

The Sort Button Control is used to sort HTML elements using links or buttons. It is possible to sort text and numerical content.

{% hint style="info" %}
This control is added in DataGrid v1.0.2
{% endhint %}

```markup
<a
    href="#"
    data-id="my_button"
    data-grid-control="sort-button"
    data-path=".first-name"
    data-direction="asc"
    data-toggle-direction
    data-type="text">First Name</a>
```

It also can be a button:

```markup
<button 
    type="button" 
    data-id="my_button"
    data-grid-control="sort-button"
    data-path=".first-name"
    data-direction="asc"
    data-toggle-direction
    data-type="text">First Name</button>
```

#### Select data attributes

| Data Attribute        | Value                   | Description                                                                                                                                                                | Required |
| --------------------- | ----------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------- |
| data-grid-control     | sort-button             | This attribute defines the control type.                                                                                                                                   | Required |
| data-path             | any CSS selector        | <p>It defines the path to the item </p><p>that should be sorted.</p>                                                                                                       | Optional |
| data-direction        | asc, desc               | Sort direction                                                                                                                                                             | Optional |
| data-type             | text, number, initial   | Sort type                                                                                                                                                                  | Optional |
| data-skip             | \[^a-zA-Z0-9]+          | <p>Defines a regex of characters </p><p>that should be skipped.</p>                                                                                                        | Optional |
| data-toggle-direction | no value                | <p>If this attribute exists, the control </p><p>will toggle direction between <strong><code>asc</code></strong> and <strong><code>desc</code></strong> on every click.</p> | Optional |
| data-id               | any alphanumeric string | <p>This attribute may be used in the deep-link, </p><p>local storage, or complex filter logic.</p>                                                                         | Optional |

#### Sort Types

| Sort Type | Description                     |
| --------- | ------------------------------- |
| text      | Sort by text content.           |
| number    | Sort by numeric content.        |
| initial   | Sort by initial document order. |

The control supports the following CSS classes:

```css
.dg-asc{
  /* when the control in the ASC state */
} 

.dg-desc{
  /* when the control in the DESC state */
} 
 
 .dg-sort-selected{
   /* when the control in the latest 
     clicked between other sort buttons 
     with the same data-id
   */
}
```

