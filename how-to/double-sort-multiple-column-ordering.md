# Double Sort (Multiple Column Ordering)

DataGrid library allows sorting on multiple columns at the same time. Let's see an example with **double sorting** a list of DIV elements.

![](<../.gitbook/assets/Double Sort (Multiple Column Ordering).gif>)

Let's add a basic HTML structure:

```markup
<!DOCTYPE html>
<html lang="en">
    <head>
        <meta charset="UTF-8">
        <title>Double Sort (Multiple Column Ordering)</title>
        <meta name="viewport" content="width=device-width, initial-scale=1, shrink-to-fit=no" />

        <!-- Demo page CSS -->
        <link href="styles.css" rel="stylesheet" />

    </head>
    <body>

        <div class="wrapper">
            <div class="item header">
                <div>Name</div>
                <div>Birth Year</div>
            </div>

            <!-- items to sort -->
            <div class="data">
                <div class="item">
                    <div class="name">Arch</div>
                    <div class="year">1956</div>
                </div>

                <div class="item">
                    <div class="name">Birdie</div>
                    <div class="year">1987</div>
                </div>

                <div class="item">
                    <div class="name">Denver</div>
                    <div class="year">1976</div>
                </div>

                <div class="item">
                    <div class="name">Arch</div>
                    <div class="year">1955</div>
                </div>

                <div class="item">
                    <div class="name">Oberon</div>
                    <div class="year">1965</div>
                </div>

                <div class="item">
                    <div class="name">Heath</div>
                    <div class="year">2013</div>
                </div>

                <div class="item">
                    <div class="name">Filippo</div>
                    <div class="year">1973</div>
                </div>

                <div class="item">
                    <div class="name">Kip</div>
                    <div class="year">1940</div>
                </div>

                <div class="item">
                    <div class="name">Filippo</div>
                    <div class="year">1972</div>
                </div>

                <div class="item">
                    <div class="name">Oberon</div>
                    <div class="year">1967</div>
                </div>

                <div class="item">
                    <div class="name">Kip</div>
                    <div class="year">1939</div>
                </div>

                <div class="item">
                    <div class="name">Arch</div>
                    <div class="year">1957</div>
                </div>

                <div class="item">
                    <div class="name">Filippo</div>
                    <div class="year">1971</div>
                </div>

                <div class="item">
                    <div class="name">Kip</div>
                    <div class="year">1941</div>
                </div>

                <div class="item">
                    <div class="name">Oberon</div>
                    <div class="year">1966</div>
                </div>
            </div>
        </div>
    </body>
</html>
```

Page styles could be:

{% code title="styles.css" %}
```css
.wrapper{
    font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, "Helvetica Neue", Arial, "Noto Sans", sans-serif, "Apple Color Emoji", "Segoe UI Emoji", "Segoe UI Symbol", "Noto Color Emoji";
    font-size: 1rem;
    width: 400px;
    max-width: 95%;
    margin: 3rem auto;
    display: flex;
    flex-direction: column;
    border-radius: 0.5rem;
    overflow: hidden;
    border: 1px solid #ccc;
}

.item{
    display: flex;
    border-bottom: 1px solid #ccc;
    padding: 0.5rem 1rem;
}

.item:last-child{
    border-bottom: 0;
}

.header{
    font-weight: bold;
    background: #e0f9ff;
}

.item >div{
    width: 50%;
}

.item a{
    color: #000
}

.item a::after{
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
{% endcode %}

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

Now we need to define what exactly should be sorted. Let's add the **`data-grid`** attribute to the  div that wraps data and the **`data-grid-item`** property to each data element. Now the HTML will look like follows:

```markup
 <!-- items to sort -->
<div class="data" data-grid>
    <div class="item" data-grid-item>
        <div class="name">Arch</div>
            <div class="year">1956</div>
        </div>

        <div class="item" data-grid-item>
            <div class="name">Birdie</div>
            <div class="year">1987</div>
        </div>

        <div class="item" data-grid-item>
            <div class="name">Denver</div>
            <div class="year">1976</div>
        </div>

        <div class="item" data-grid-item>
            <div class="name">Arch</div>
            <div class="year">1955</div>
        </div>

        <div class="item" data-grid-item>
            <div class="name">Oberon</div>
            <div class="year">1965</div>
        </div>

        <div class="item" data-grid-item>
            <div class="name">Heath</div>
            <div class="year">2013</div>
        </div>

        <div class="item" data-grid-item>
            <div class="name">Filippo</div>
            <div class="year">1973</div>
        </div>

        <div class="item" data-grid-item>
            <div class="name">Kip</div>
            <div class="year">1940</div>
        </div>

        <div class="item" data-grid-item>
            <div class="name">Filippo</div>
            <div class="year">1972</div>
        </div>

        <div class="item" data-grid-item>
            <div class="name">Oberon</div>
            <div class="year">1967</div>
        </div>

        <div class="item" data-grid-item>
            <div class="name">Kip</div>
            <div class="year">1939</div>
        </div>

        <div class="item" data-grid-item>
            <div class="name">Arch</div>
            <div class="year">1957</div>
        </div>

        <div class="item" data-grid-item>
            <div class="name">Filippo</div>
            <div class="year">1971</div>
        </div>

        <div class="item" data-grid-item>
            <div class="name">Kip</div>
            <div class="year">1941</div>
        </div>

        <div class="item" data-grid-item>
            <div class="name">Oberon</div>
            <div class="year">1966</div>
        </div>
</div>
```

Now let's replace table headers with [Sort Button controls](../controls/sort-button-control.md). Please note that **`data-id`** should have different values:

```markup
<div class="item header">
    <div>
        <a
                href="#"
                data-id="name"
                data-grid-control="sort-button"
                data-path=".name"
                data-direction="asc"
                data-toggle-direction
                data-type="text">Name</a>
    </div>
    <div>
        <a
                href="#"
                data-id="year"
                data-grid-control="sort-button"
                data-path=".year"
                data-direction="asc"
                data-toggle-direction
                data-type="number">Birth Year</a>
    </div>
</div>
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
        <meta charset="UTF-8">
        <title>Double Sort (Multiple Column Ordering)</title>
        <meta name="viewport" content="width=device-width, initial-scale=1, shrink-to-fit=no" />

        <!-- DataGrid library CSS -->
        <link href="datagrid.min.css" rel="stylesheet" />

        <!-- Demo page CSS -->
        <link href="styles.css" rel="stylesheet" />
    </head>
    <body>

        <div class="wrapper">
            <div class="item header">
                <div>
                    <a
                            href="#"
                            data-id="name"
                            data-grid-control="sort-button"
                            data-path=".name"
                            data-direction="asc"
                            data-toggle-direction
                            data-type="text">Name</a>
                </div>
                <div>
                    <a
                            href="#"
                            data-id="year"
                            data-grid-control="sort-button"
                            data-path=".year"
                            data-direction="asc"
                            data-toggle-direction
                            data-type="number">Birth Year</a>
                </div>
            </div>

            <!-- items to sort -->
            <div class="data" data-grid>
                <div class="item" data-grid-item>
                    <div class="name">Arch</div>
                    <div class="year">1956</div>
                </div>

                <div class="item" data-grid-item>
                    <div class="name">Birdie</div>
                    <div class="year">1987</div>
                </div>

                <div class="item" data-grid-item>
                    <div class="name">Denver</div>
                    <div class="year">1976</div>
                </div>

                <div class="item" data-grid-item>
                    <div class="name">Arch</div>
                    <div class="year">1955</div>
                </div>

                <div class="item" data-grid-item>
                    <div class="name">Oberon</div>
                    <div class="year">1965</div>
                </div>

                <div class="item" data-grid-item>
                    <div class="name">Heath</div>
                    <div class="year">2013</div>
                </div>

                <div class="item" data-grid-item>
                    <div class="name">Filippo</div>
                    <div class="year">1973</div>
                </div>

                <div class="item" data-grid-item>
                    <div class="name">Kip</div>
                    <div class="year">1940</div>
                </div>

                <div class="item" data-grid-item>
                    <div class="name">Filippo</div>
                    <div class="year">1972</div>
                </div>

                <div class="item" data-grid-item>
                    <div class="name">Oberon</div>
                    <div class="year">1967</div>
                </div>

                <div class="item" data-grid-item>
                    <div class="name">Kip</div>
                    <div class="year">1939</div>
                </div>

                <div class="item" data-grid-item>
                    <div class="name">Arch</div>
                    <div class="year">1957</div>
                </div>

                <div class="item" data-grid-item>
                    <div class="name">Filippo</div>
                    <div class="year">1971</div>
                </div>

                <div class="item" data-grid-item>
                    <div class="name">Kip</div>
                    <div class="year">1941</div>
                </div>

                <div class="item" data-grid-item>
                    <div class="name">Oberon</div>
                    <div class="year">1966</div>
                </div>
            </div>
        </div>

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
