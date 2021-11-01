# Page Size Control

Page size control allows changing the number of items on a page.

```markup
<select data-grid-control="page-size" style="width: 200px">
    <option value="4">4 items per page</option>
    <option value="8">8 items per page</option>
    <option value="12">12 items per page</option>
    <option value="16">16 items per page</option>
    <option value="Infinity">all</option>
</select>
```

| Data Attribute    | Value     | Description                                                                                                                        | Required |
| ----------------- | --------- | ---------------------------------------------------------------------------------------------------------------------------------- | -------- |
| data-grid-control | page-size | This attribute defines the control type.                                                                                           | Required |
| data-scroll-top   | no value  | <p>If this data attribute exists, </p><p>the page will scroll to the top each time </p><p>a pagination button will be pressed.</p> | Optional |

#### Initial value

To define the initial page size value, the following setting should be passed to the initialization function:

```markup
<script>
    datagrid({
        pageSize: 12
    });
</script>
```
