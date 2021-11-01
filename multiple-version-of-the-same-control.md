# Multiple version of the same control (data-id attribute)

Sometimes one control may appear more than one time on the page. For example, it may be placed at the top and bottom panels. Or it may appear in the content item with different styling. In this case, all instances of this control should have the same**`data-id`**attribute. For example:

```markup
<!-- top panel -->
<input
    type="text"
    placeholder="Filter by title"
    data-grid-control="text-filter"
    data-path=".product-name"
    data-id="search"
/>

<!-- .... content ... -->

<!-- bottom panel -->
<input
    type="text"
    placeholder="Filter by title"
    data-grid-control="text-filter"
    data-path=".product-name"
    data-id="search"
/>
```

