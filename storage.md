# Storage

It is possible to save the current user selection so it will be restored after page refresh or once the user travels between different pages. This state can be saved in local storage, session storage, or cookies.

| Storage Type    | Description                                                                                                                                                                          | Code Name         |
| --------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ----------------- |
| Local Storage   | <p>Local storage is persistent storage </p><p>that keeps data even if the user closes the browser. </p><p>It will be cleared only when the user </p><p>clears the browser cache.</p> | 'local-storage'   |
| Session Storage | <p>Session storage will be cleared when </p><p>the browser session is over, </p><p>typically when the user closes the browser.</p>                                                   | 'session-storage' |
| Cookies         | <p>Cookies may have an expiration date, </p><p>and also they are passed to the server.</p>                                                                                           | 'cookies'         |

#### Storage Properties

| Property Name | Values                                                         | Description                                                                                                        |
| ------------- | -------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------ |
| storage       | <p>'', 'local-storage', <br>'session-storage' or 'cookies'</p> | Storage type. The default is an empty value.                                                                       |
| name          | any text value                                                 | <p>If multiple pages have the same storage name, </p><p>they will share the same control state.</p>                |
| expiration    | Cookie expiration in minutes.                                  | <p>Used for cookies only. </p><p>Default value -1 (The cookie expires when the user</p><p>closes the browser.)</p> |
|               |                                                                |                                                                                                                    |

#### Local Storage

```markup
<script>
    datagrid({
        storage: 'local-storage',
        name: 'my-page'
    });
</script>
```

#### Session Storage

```markup
<script>
    datagrid({
        storage: 'session-storage',
        name: 'my-page'
    });
</script>
```

#### Cookies

```markup
<script>
    datagrid({
        storage: 'cookies',
        name: 'my-page'
    });
</script>
```
