# .Net Core Csharp ManyWhere

This extension performs many clauses where

```csharp
using LinqKit;

public static IQueryable<T> ManyWhere<T>(this IQueryable<T> query, 
                                              IQueryable<Expression<Func<T, bool>>> predicate)
{
    foreach (var item in predicate)
    {
        query = query.Where(item.Expand());
    }

    return query;
}
```

## Usage

```csharp
  //IQueryable<Expression<Func<T, bool>>> predicate <= parameter in method
  var result = await dbSet.ManyWhere(predicate);
```


https://www.nuget.org/packages/LINQKit.Core/
