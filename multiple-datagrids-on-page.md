# Multiple DataGrids on Page

It is possible to have multiple DataGrid containers on one page:

```typescript
datagrid('.path1');
datagrid('.path2');
```

Each DataGrid initialization may have its own settings:

```typescript
// container #1
datagrid('.path1', {
   currentPage: 0,
   pageSize: 12,
   pagesRange: 10
});

// container #2
datagrid('.path2', {
   currentPage: 0,
   pageSize: 3,
   pagesRange: 10
});
```

{% hint style="info" %}
Multiple DataGrids don't support deep linking and storage.
{% endhint %}

