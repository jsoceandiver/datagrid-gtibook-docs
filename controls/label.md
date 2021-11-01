# Label Control

The label control is used to print information about the current page state. For example, it may be the selected page number or the total page number.

```markup
<div 
    data-grid-control="label" 
    data-type="pagination-pages">
</div>
```

| Data Attribute    | Value                                                                          | Description                              | Required |
| ----------------- | ------------------------------------------------------------------------------ | ---------------------------------------- | -------- |
| data-grid-control | label                                                                          | This attribute defines the control type. | Required |
| data-type         | <ul><li>pagination-pages</li><li>pagination-items</li><li>no-results</li></ul> | Label type.                              | Optional |

#### Label Types

| Type             | Example           |
| ---------------- | ----------------- |
| pagination-pages | Page 1 of 3       |
| pagination-items | 1 - 12 of 36      |
| no-results       | No results found. |

#### No results label

This label appears when the total number of items becomes zero.

```markup
<div 
    data-grid-control="label" 
    data-type="no-results" 
    data-text="No results found.">
</div>
```

#### Custom label

It is possible to create a custom label using the following callback function:

```markup
<script>
    datagrid({
        // render custom label HTML
        renderLabelControl: function(state, $control){
            return 'any custom html';
        }
    });
</script>
```

If the label is empty, it has a **`dg-label-empty`** CSS class. This way, it's possible to add special styles:

```css
.dg-label-empty{
    display: none;
}
```
