# Pagination

The pagination control splits HTML elements into multiple pages of content. It helps to improve the user experience in UI with a large number of items.

```markup
<nav
    aria-label="pagination"
    data-grid-control="pagination"
    data-prev="&laquo;"
    data-next="&raquo;"
    data-first="First"
    data-last="Last"></nav>
```

| Data Attribute       | Value                 | Description                                                                                                                        | Required |
| -------------------- | --------------------- | ---------------------------------------------------------------------------------------------------------------------------------- | -------- |
| data-grid-control    | pagination            | This attribute defines the control type.                                                                                           | Required |
| data-prev            | any text              | The title of the _previous_ button.                                                                                                | Optional |
| data-next            | any text              | The title of the _next_ button.                                                                                                    | Optional |
| data-first           | any text              | The title of the _first_ button.                                                                                                   | Optional |
| data-last            | any text              | The title of the _last_ button.                                                                                                    | Optional |
| data-hide-first-last | true, false (default) | <p>If true, the first and the last button </p><p>will be hidden.</p>                                                               | Optional |
| data-scroll-top      | no value              | <p>If this data attribute exists, </p><p>the page will scroll to the top each time </p><p>a pagination button will be pressed.</p> | Optional |
| data-ul-class        | pagination            | The class of dynamically generated UL element.                                                                                     | Optional |
| data-li-class        | page-item             | The class of dynamically generated LI elements.                                                                                    | Optional |
| data-link-class      | page-link             | <p>The class of dynamically generated </p><p>A and SPAN elements.</p>                                                              | Optional |
| data-disabled-class  | disabled              | The class of disabled links.                                                                                                       | Optional |
| data-active-class    | active                | The class of the currently selected page.                                                                                          | Optional |
| data-prev-class      | page-prev             | The class of the LI with the previous button.                                                                                      | Optional |
| data-next-class      | page-next             | The class of the LI with the next button.                                                                                          | Optional |
| data-first-class     | page-first            | The class of the LI with the first button.                                                                                         | Optional |
| data-last-class      | page-last             | The class of the LI with the last button.                                                                                          | Optional |

#### How to define pagination values on page load

To define initial pagination values, the following settings may be passed to the initialization function:

```markup
<script>
    datagrid({
        currentPage: 0,
        pageSize: 12,
        pagesRange: 10
    });
</script>
```

| Property    | Value  | Description                                                                                             | Required |
| ----------- | ------ | ------------------------------------------------------------------------------------------------------- | -------- |
| currentPage | number | <p>The selected page starting from 0. </p><p>The default is 0. </p>                                     | Optional |
| pageSize    | number | <p>The number of items per page.</p><p>The default is Infinity.</p>                                     | Optional |
| pagesRange  | number | <p>The maximal number of pagination bullets</p><p>that is visible at once. The default value is 10.</p> | Optional |

#### Custom Pagination HTML

It is possible to entirely customize pagination HTML using the following callback function:

```markup
<script>
    datagrid({
        currentPage: 0,
        pageSize: 12,
        pagesRange: 10,
        
        // render custom pagination HTML
        renderPaginationControl: function(state, $control){
            return 'any custom html';
        }
    });
</script>
```

If the pagination is empty, it has a **`dg-pagination-empty`** CSS class. This way, it's possible to add special styles:

```css
.dg-pagination-empty{
    display: none;
}
```
