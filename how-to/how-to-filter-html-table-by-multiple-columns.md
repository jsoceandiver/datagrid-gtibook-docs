# How to Filter HTML Table By Multiple Columns

![](<../.gitbook/assets/How to Filter HTML Table By Multiple Columns.gif>)

First, let's add a basic HTML structure:

```markup
<!DOCTYPE html>
<html lang="en">
    <head>
        <meta charset="UTF-8" />
        <title>How to Filter HTML Table By Multiple Columns</title>
        <meta name="viewport" content="width=device-width, initial-scale=1, shrink-to-fit=no" />
    </head>
    <body>

    </body>
</html>
```

Now, let's add a table with some sample data. It will contain three columns - user first name, user last name, and age. Each column has an appropriate CSS class: **`.first-name`** and **`.last-name`**, and** `.age`.**

```markup
<!DOCTYPE html>
<html lang="en">
    <head>
        <meta charset="UTF-8" />
        <title>How to Filter HTML Table By Multiple Columns</title>
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
    font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, "Helvetica Neue", Arial, "Noto Sans", sans-serif, "Apple Color Emoji", "Segoe UI Emoji", "Segoe UI Symbol", "Noto Color Emoji";
    font-size: 1rem;
    margin: 2rem auto;
    border: 1px solid #ddd;
    border-collapse: collapse;
    width: 600px;
    max-width: 95%;
}

.demo-table td,
.demo-table th{
    padding: 1rem;
    border: 1px solid #ddd;
    text-align: left;
}

.demo-table tr:nth-child(even) td{
    background: #f4f4f4;
}

input[type="text"]{
    border: 1px solid #ccc;
    border-radius: 0.5rem;
    padding: 0.3rem 0.5rem;
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

All we need to do now is to define what exactly should be filtered. Let's add the **`data-grid`** attribute to the **`<tbody>`** element of the table, and **`data-grid-item`** property to each **`<tr>`** element of **`<tbody>`**. Now the table will look like follows:

```markup
<!DOCTYPE html>
<html lang="en">
    <head>
        <meta charset="UTF-8" />
        <title>How to Filter HTML Table By Multiple Columns</title>
        <meta name="viewport" content="width=device-width, initial-scale=1, shrink-to-fit=no" />

        <!-- DataGrid library CSS -->
        <link href="datagrid.min.css" rel="stylesheet" />

        <!-- Demo page CSS -->
        <style>
        .demo-table{
            margin: 2rem auto;
            border: 1px solid #ddd;
            border-collapse: collapse;
            width: 600px;
            max-width: 95%;
        }
        
        .demo-table td,
        .demo-table th{
            padding: 1rem;
            border: 1px solid #ddd;
            text-align: left;
        }
        
        .demo-table tr:nth-child(even) td{
            background: #f4f4f4;
        }
        </style>
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

    </body>
</html>
```

Now, let's add [text filter controls](../controls/text-filter.md) to the table **`thead`** section:

```markup
<table class="demo-table">
    <thead>
        <tr>
            <th>
                <input
                        type="text"
                        placeholder="Filter by first name"
                        data-grid-control="text-filter"
                        data-path=".first-name"
                />
            </th>
            <th>
                <input
                        type="text"
                        placeholder="Filter by last name"
                        data-grid-control="text-filter"
                        data-path=".last-name"
                />
            </th>
            <th>
                <input
                        type="text"
                        placeholder="Filter by age"
                        data-grid-control="text-filter"
                        data-path=".age"
                />
            </th>
        </tr>
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

{% hint style="info" %}
You may find the detailed documentation of the text filter control [here](../controls/text-filter.md).
{% endhint %}

We can also add [no results label control ](../controls/label.md#no-results-label)to the bottom of the table. This control will appear if the filters return no results.

```markup
<tfoot>
    <tr>
        <td colspan="3">
            <!-- no results label -->
            <div
                    data-grid-control="label"
                    data-type="no-results"
                    data-text="No results found.">
            </div>
        </td>
    </tr>
</tfoot>
```

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
        <title>How to Filter HTML Table By Multiple Columns</title>
        <meta name="viewport" content="width=device-width, initial-scale=1, shrink-to-fit=no" />

        <!-- DataGrid library CSS -->
        <link href="datagrid.min.css" rel="stylesheet" />

        <style>
        .demo-table{
            font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, "Helvetica Neue", Arial, "Noto Sans", sans-serif, "Apple Color Emoji", "Segoe UI Emoji", "Segoe UI Symbol", "Noto Color Emoji";
            font-size: 1rem;
            margin: 2rem auto;
            border: 1px solid #ddd;
            border-collapse: collapse;
            width: 600px;
            max-width: 95%;
        }
        
        .demo-table td,
        .demo-table th{
            padding: 1rem;
            border: 1px solid #ddd;
            text-align: left;
        }
        
        .demo-table tr:nth-child(even) td{
            background: #f4f4f4;
        }
        
        input[type="text"]{
            border: 1px solid #ccc;
            border-radius: 0.5rem;
            padding: 0.3rem 0.5rem;
        }
        </style>
    </head>
    <body>
        <table class="demo-table">
            <thead>
                <tr>
                    <th>
                        <input
                                type="text"
                                placeholder="Filter by first name"
                                data-grid-control="text-filter"
                                data-path=".first-name"
                        />
                    </th>
                    <th>
                        <input
                                type="text"
                                placeholder="Filter by last name"
                                data-grid-control="text-filter"
                                data-path=".last-name"
                        />
                    </th>
                    <th>
                        <input
                                type="text"
                                placeholder="Filter by age"
                                data-grid-control="text-filter"
                                data-path=".age"
                        />
                    </th>
                </tr>
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
            <tfoot>
                <tr>
                    <td colspan="3">
                        <!-- no results label -->
                        <div
                                data-grid-control="label"
                                data-type="no-results"
                                data-text="No results found.">
                        </div>
                    </td>
                </tr>
            </tfoot>
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
