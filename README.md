# Getting Started

****[**DataGrid Library**](https://codecanyon.net/item/datagrid-javascript-pagination-sort-and-filter/29876926) is a simple and powerful solution to enable sorting, filtering, and pagination on any page.

On behalf of our team, we would like to thank you for purchasing this library. Your support encourages us to build better plugins and continuously bring value to our products. This documentation file covers all the information needed to install and use this library.

## Bootstrap 5 Example

Let's build a page based on Bootstrap 5 with a text filter by item title.\
Get started with a minimal Bootstrap layout as described in [Bootstrap 5 documentation](https://getbootstrap.com/docs/5.0/getting-started/introduction/):

{% code title="index.html" %}
```markup
<!DOCTYPE html>
<html lang="en">
    <head>
        <title>DataGrid Example</title>

        <!-- Required meta tags -->
        <meta charset="utf-8" />
        <meta name="viewport" 
            content="width=device-width, initial-scale=1, shrink-to-fit=no" />

        <!-- Bootstrap CSS -->
        <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.0.0-beta1/dist/css/bootstrap.min.css" 
              rel="stylesheet" 
              integrity="sha384-giJF6kkoqNQ00vy+HMDP7azOuL0xtbfIcaT9wjKHr8RbDVddVHyTfAAsrekwKmP1" 
              crossorigin="anonymous" />
    </head>
    <body>


        <!-- Bootstrap Script (Optional) -->
        <script 
            src="https://cdn.jsdelivr.net/npm/bootstrap@5.0.0-beta1/dist/js/bootstrap.bundle.min.js" 
            integrity="sha384-ygbV9kiqUc6oa4msXn9868pTtWMgiQaeYH7/t7LECLbyPA2x65Kgf80OJFdroafW" 
            crossorigin="anonymous"></script>
    </body>
</html>
```
{% endcode %}

{% hint style="info" %}
&#x20;DataGrid library can be used with any CSS Framework or with your custom HTML & CSS.
{% endhint %}

Copy-paste the stylesheet `<link>` into your `<head>` to load DataGrid CSS:

```markup
<link href="datagrid.min.css" rel="stylesheet" />
```

Place the `<script>` near the end of your pages, right before the closing `</body>` tag:

```markup
<script src="datagrid.min.js"></script>
```

Add a **container element** that will hold all items that need to be filtered, sorted, etc. This container should have the`data-grid`attribute.&#x20;

```markup
<div class="container">
    <div class="row" data-grid>
        <!-- content -->
    </div>
</div>
```

Add several items to the container. The items can have **any HTML layout**, for example like this:

```markup
<div class="container">
    <div class="row" data-grid>
    
        <!-- item #1 -->
        <div class="col" data-grid-item>
            <p class="title">Lorem ipsum sed</p>
        </div>
        
        <!-- item #2 -->
        <div class="col" data-grid-item>
            <p class="title">Est ullamcorper eget</p>
        </div>
        
        <!-- item #2 -->
        <div class="col" data-grid-item>
            <p class="title">Amet tellus cras</p>
        </div>
        
        <!-- more items ... -->
        
    </div>
</div>
```





{% hint style="info" %}
Every item should have**`data-grid-item`** attribute.
{% endhint %}

Let's add text filter control:

```markup
<div class="row mb-4">
    <div class="col">
        <input
            type="text"
            class="form-control"
            placeholder="Filter by title"
            data-grid-control="text-filter"
            data-path=".title"
        />
    </div>
</div>
```

{% hint style="info" %}
**`data-path`** attribute points to the text that should be filtered. It accepts **any valid CSS selector** string, for example, class or ID.
{% endhint %}

Add DataGrid library initialization:

```markup
<script>
    datagrid();
</script>
```

DataGrid settings can be passed in the following way:

```markup
<script>
    datagrid({
       // Settings ....
    });
</script>
```

The final version:

{% code title="index.html" %}
```markup
<!DOCTYPE html>
<html lang="en">
    <head>
        <title>DataGrid Example</title>

        <!-- Required meta tags --> 
        <meta charset="utf-8" />
        <meta name="viewport" content="width=device-width, initial-scale=1, shrink-to-fit=no" />

        <!-- Bootstrap CSS -->
        <link href="//cdn.jsdelivr.net/npm/bootstrap@5.0.0-beta1/dist/css/bootstrap.min.css" 
              rel="stylesheet" 
              integrity="sha384-giJF6kkoqNQ00vy+HMDP7azOuL0xtbfIcaT9wjKHr8RbDVddVHyTfAAsrekwKmP1" 
              crossorigin="anonymous" />
              
        <!-- DataGird CSS -->      
        <link href="datagrid.min.css" rel="stylesheet" />      
    </head>
    <body>
    
        <div class="container">
        
            <div class="row mb-4">
                <div class="col">
                
                    <!-- text filter by title -->
                    <input
                        type="text"
                        class="form-control mr-2"
                        placeholder="Filter by title"
                        data-grid-control="text-filter"
                        data-path=".title"
                    />
                </div>
            </div>
        
            <!-- DataGrid container -->
            <div class="row" data-grid>
            
                <!-- item #1 -->
                <div class="col" data-grid-item>
                    <p class="title">Lorem ipsum sed</p>
                </div>
                
                <!-- item #2 -->
                <div class="col" data-grid-item>
                    <p class="title">Est ullamcorper eget</p>
                </div>
                
                <!-- item #2 -->
                <div class="col" data-grid-item>
                    <p class="title">Amet tellus cras</p>
                </div>
                
                <!-- more items ... -->
                
            </div>
        </div>


        <!-- Bootstrap Script -->
        <script 
            src="//cdn.jsdelivr.net/npm/bootstrap@5.0.0-beta1/dist/js/bootstrap.bundle.min.js" 
            integrity="sha384-ygbV9kiqUc6oa4msXn9868pTtWMgiQaeYH7/t7LECLbyPA2x65Kgf80OJFdroafW" 
            crossorigin="anonymous"></script>
            
        <!-- DataGird Script -->    
        <script src="datagrid.min.js"></script>    
        
        <!-- DataGird initialization -->
        <script>
            datagrid();
        </script>
    </body>
</html>
```
{% endcode %}
