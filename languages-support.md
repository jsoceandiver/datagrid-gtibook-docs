# Languages Support

By default, all controls have a **`data-skip`** attribute that defines what characters should be skipped during sorting, filtering, etc.

Initially, this attribute contains regex **`[^a-zA-Z0-9]+`**, meaning that control should skip all characters except English letters and numbers.

In other languages, control should have different regex with the letters of the given alphabet.

For example, for French, it could be:

```
[^a-zàâçéèêëîïôûùüÿñæœ0-9]+
```

In text filter control you may use it in the following way:

```markup
<input
    type="text"
    placeholder="Filter by title"
    data-grid-control="text-filter"
    data-path=".title"
    data-skip="[^a-zàâçéèêëîïôûùüÿñæœ0-9]+"
/>
```

Please check the relevant control documentation page for **data-skip** usage examples.
