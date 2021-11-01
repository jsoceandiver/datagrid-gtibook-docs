# HTML Table with Sortable Headers

[DataGrid Library](https://codecanyon.net/item/datagrid-javascript-pagination-sort-and-filter/29876926) may be used for creating HTML tables with sortable headers, search, and pagination. Any DataGird control can be used with tables as with any other HTML structure.

![HTML Table with Sortable Headers](../.gitbook/assets/tablw-woth-sortable-headers.gif)

First, let's add a minimal HTML structure:

```markup
<!DOCTYPE html>
<html lang="en">
    <head>
        <meta charset="UTF-8" />
        <title>HTML Table with Sortable Headers</title>
        <meta name="viewport" content="width=device-width, initial-scale=1, shrink-to-fit=no" />
    </head>
    <body>

    </body>
</html>
```

Now, let's add a table with some sample data. It will contain three columns - user first name, user last name, and age. Each column has an appropriate CSS class: **`.first-name`** and **`.last-name`**  , and **`.age`**

```markup
<!DOCTYPE html>
<html lang="en">
    <head>
        <meta charset="UTF-8" />
        <title>HTML Table with Sortable Headers</title>
        <meta name="viewport" content="width=device-width, initial-scale=1, shrink-to-fit=no" />
    </head>
    <body>
        <table class="demo-table">
            <thead>
                <tr>
                    <th>First Name</th>
                    <th>Last Name</th>
                    <th>Age</th>
                </tr>
            </thead>
            <tbody>
                <tr>
                    <td class="first-name">Wendye</td>
                    <td class="last-name">Lightwing</td>
                    <td class="age">24</td>
                </tr>
                <tr>
                    <td class="first-name">Milena</td>
                    <td class="last-name">Torre</td>
                    <td class="age">82</td>
                </tr>
                <tr>
                    <td class="first-name">Erinn</td>
                    <td class="last-name">Hills</td>
                    <td class="age">81</td>
                </tr>
                <tr>
                    <td class="first-name">Yoshiko</td>
                    <td class="last-name">Smithson</td>
                    <td class="age">62</td>
                </tr>
                <tr>
                    <td class="first-name">Umberto</td>
                    <td class="last-name">McFadden</td>
                    <td class="age">93</td>
                </tr>
                <tr>
                    <td class="first-name">Donaugh</td>
                    <td class="last-name-name">Huban</td>
                    <td class="age">75</td>
                </tr>
                <tr>
                    <td class="first-name">Cami</td>
                    <td class="last-name">Pickthorn</td>
                    <td class="age">45</td>
                </tr>
                <tr>
                    <td class="first-name">Alistair</td>
                    <td class="last-name">Reddell</td>
                    <td class="age">55</td>
                </tr>
                <tr>
                    <td class="first-name">Genia</td>
                    <td class="last-name">Crawshay</td>
                    <td class="age">60</td>
                </tr>
                <tr>
                    <td class="first-name">Allyn</td>
                    <td class="last-name">Liell</td>
                    <td class="age">37</td>
                </tr>
            </tbody>
        </table>
    </body>
</html>
```

Also, let's add some styles:

```css
.demo-table{
    margin: 2rem auto;
    border: 1px solid #ddd;
    border-collapse: collapse;
    table-layout: fixed;
    font-family: "Helvetica Neue", Helvetica, Arial, sans-serif;
    width: 100%;
}

.demo-table td,
.demo-table th{
    padding: 1rem;
    border: 1px solid #ddd;
    width: 33%;
    text-align: left;
}

.demo-table tr:nth-child(odd) td{
    background: #f4f4f4;
}

.demo-table th a{
    color: #07909b;
    display: flex;
    align-items: center;
    justify-content: space-between;
    text-decoration: none;
}

.demo-table th a::after{
    margin-left: 1rem;
    display: inline-block;
    font-size: 1rem;
    content: '\2195';
}

.dg-sort-selected.dg-asc::after{
    content: '\25BC';
    font-size: 0.8rem;
}

.dg-sort-selected.dg-desc::after{
    content: '\25B2';
    font-size: 0.8rem;
}
```

Now we need to add a DataGrid CSS to the HEAD of the document:

```markup
<!-- DataGrid library CSS -->
<link href="datagrid.min.css" rel="stylesheet" />
```

And additionally, we need to add the DataGrid script at the bottom of the document.

```markup
<!-- DataGrid library JavaScript -->
<script src="datagrid.min.js"></script>
```

All we need to do now is to define what exactly should be sorted. Let's add the **`data-grid`** attribute to the **`<tbody>`** element of the table, and **`data-grid-item`** property to each **`<tr>`** element. Now the table will look like follows:

```markup
<table class="demo-table">
    <thead>
        <tr>
            <th>First Name</th>
            <th>Last Name</th>
            <th>Age</th>
        </tr>
    </thead>
    <tbody data-grid>
        <tr data-grid-item>
            <td class="first-name">Wendye</td>
            <td class="last-name">Lightwing</td>
            <td class="age">24</td>
        </tr>
        <tr data-grid-item>
            <td class="first-name">Milena</td>
            <td class="last-name">Torre</td>
            <td class="age">82</td>
        </tr>
        <tr data-grid-item>
            <td class="first-name">Erinn</td>
            <td class="last-name">Hills</td>
            <td class="age">81</td>
        </tr>
        <tr data-grid-item>
            <td class="first-name">Yoshiko</td>
            <td class="last-name">Smithson</td>
            <td class="age">62</td>
        </tr>
        <tr data-grid-item>
            <td class="first-name">Umberto</td>
            <td class="last-name">McFadden</td>
            <td class="age">93</td>
        </tr>
        <tr data-grid-item>
            <td class="first-name">Donaugh</td>
            <td class="last-name-name">Huban</td>
            <td class="age">75</td>
        </tr>
        <tr data-grid-item>
            <td class="first-name">Cami</td>
            <td class="last-name">Pickthorn</td>
            <td class="age">45</td>
        </tr>
        <tr data-grid-item>
            <td class="first-name">Alistair</td>
            <td class="last-name">Reddell</td>
            <td class="age">55</td>
        </tr>
        <tr data-grid-item>
            <td class="first-name">Genia</td>
            <td class="last-name">Crawshay</td>
            <td class="age">60</td>
        </tr>
        <tr data-grid-item>
            <td class="first-name">Allyn</td>
            <td class="last-name">Liell</td>
            <td class="age">37</td>
        </tr>
    </tbody>
</table>
```

Now let's replace table headers with [Sort Button controls](../controls/sort-button-control.md):

```markup
<table class="demo-table">
    <thead>
        <tr>
            <th>
                <a
                        href="#"
                        data-id="table_header_sort"
                        data-grid-control="sort-button"
                        data-path=".first-name"
                        data-direction="asc"
                        data-toggle-direction
                        data-type="text">First Name</a>
            </th>
            <th>
                <a
                        href="#"
                        data-id="table_header_sort"
                        data-grid-control="sort-button"
                        data-path=".last-name"
                        data-direction="asc"
                        data-toggle-direction
                        data-type="text">Last Name</a>
            </th>
    
            <th>
                <a
                        href="#"
                        data-id="table_header_sort"
                        data-grid-control="sort-button"
                        data-path=".age"
                        data-direction="asc"
                        data-toggle-direction
                        data-type="number">Age</a>
            </th>
        </tr>
    </thead>
    <tbody data-grid>
        <tr data-grid-item>
            <td class="first-name">Wendye</td>
            <td class="last-name">Lightwing</td>
            <td class="age">24</td>
        </tr>
        <tr data-grid-item>
            <td class="first-name">Milena</td>
            <td class="last-name">Torre</td>
            <td class="age">82</td>
        </tr>
        <tr data-grid-item>
            <td class="first-name">Erinn</td>
            <td class="last-name">Hills</td>
            <td class="age">81</td>
        </tr>
        <tr data-grid-item>
            <td class="first-name">Yoshiko</td>
            <td class="last-name">Smithson</td>
            <td class="age">62</td>
        </tr>
        <tr data-grid-item>
            <td class="first-name">Umberto</td>
            <td class="last-name">McFadden</td>
            <td class="age">93</td>
        </tr>
        <tr data-grid-item>
            <td class="first-name">Donaugh</td>
            <td class="last-name-name">Huban</td>
            <td class="age">75</td>
        </tr>
        <tr data-grid-item>
            <td class="first-name">Cami</td>
            <td class="last-name">Pickthorn</td>
            <td class="age">45</td>
        </tr>
        <tr data-grid-item>
            <td class="first-name">Alistair</td>
            <td class="last-name">Reddell</td>
            <td class="age">55</td>
        </tr>
        <tr data-grid-item>
            <td class="first-name">Genia</td>
            <td class="last-name">Crawshay</td>
            <td class="age">60</td>
        </tr>
        <tr data-grid-item>
            <td class="first-name">Allyn</td>
            <td class="last-name">Liell</td>
            <td class="age">37</td>
        </tr>
    </tbody>
</table>
```

{% hint style="info" %}
You may find the detailed documentation of the sort button control [here](../controls/sort-button-control.md).
{% endhint %}

The final step is to initialize the DataGrid library as follows:

```markup
<script>
    datagrid();
</script>
```

That's all! The final HTML is:

```markup
<!DOCTYPE html>
<html lang="en">
    <head>
        <meta charset="UTF-8" />
        <title>Sort HTML Table with DataGrid Library</title>
        <meta name="viewport" content="width=device-width, initial-scale=1, shrink-to-fit=no" />

        <!-- Demo page CSS -->
        <link href="styles.css" rel="stylesheet" />

        <!-- DataGrid library CSS -->
        <link href="datagrid.min.css" rel="stylesheet" />
    </head>
    <body>
        <table class="demo-table">
            <thead>
            <tr>
                <th>
                    <a
                            href="#"
                            data-id="table_header_sort"
                            data-grid-control="sort-button"
                            data-path=".first-name"
                            data-direction="asc"
                            data-toggle-direction
                            data-type="text">First Name</a>
                </th>
                <th>
                    <a
                            href="#"
                            data-id="table_header_sort"
                            data-grid-control="sort-button"
                            data-path=".last-name"
                            data-direction="asc"
                            data-toggle-direction
                            data-type="text">Last Name</a>
                </th>

                <th>
                    <a
                            href="#"
                            data-id="table_header_sort"
                            data-grid-control="sort-button"
                            data-path=".age"
                            data-direction="asc"
                            data-toggle-direction
                            data-type="number">Age</a>
                </th>
            </tr>
            </thead>
            <tbody data-grid>
            <tr data-grid-item>
                <td class="first-name">Wendye</td>
                <td class="last-name">Lightwing</td>
                <td class="age">24</td>
            </tr>
            <tr data-grid-item>
                <td class="first-name">Milena</td>
                <td class="last-name">Torre</td>
                <td class="age">82</td>
            </tr>
            <tr data-grid-item>
                <td class="first-name">Erinn</td>
                <td class="last-name">Hills</td>
                <td class="age">81</td>
            </tr>
            <tr data-grid-item>
                <td class="first-name">Yoshiko</td>
                <td class="last-name">Smithson</td>
                <td class="age">62</td>
            </tr>
            <tr data-grid-item>
                <td class="first-name">Umberto</td>
                <td class="last-name">McFadden</td>
                <td class="age">93</td>
            </tr>
            <tr data-grid-item>
                <td class="first-name">Donaugh</td>
                <td class="last-name-name">Huban</td>
                <td class="age">75</td>
            </tr>
            <tr data-grid-item>
                <td class="first-name">Cami</td>
                <td class="last-name">Pickthorn</td>
                <td class="age">45</td>
            </tr>
            <tr data-grid-item>
                <td class="first-name">Alistair</td>
                <td class="last-name">Reddell</td>
                <td class="age">55</td>
            </tr>
            <tr data-grid-item>
                <td class="first-name">Genia</td>
                <td class="last-name">Crawshay</td>
                <td class="age">60</td>
            </tr>
            <tr data-grid-item>
                <td class="first-name">Allyn</td>
                <td class="last-name">Liell</td>
                <td class="age">37</td>
            </tr>
            </tbody>
        </table>

        <!-- DataGrid library JavaScript -->
        <script src="datagrid.min.js"></script>

        <script>
            datagrid();
        </script>
    </body>
</html>
```

{% content-ref url="broken-reference" %}
[Broken link](broken-reference)
{% endcontent-ref %}
