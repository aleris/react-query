---
id: removeQueries
title: removeQueries
---

The `removeQueries` function can be used to remove queries from the cache based on their query keys or any other functionally accessible property/state of the query.

```js
import { removeQueries } from 'react-query'

removeQueries(environment, queryKey, { exact: true })
```

**Options**

- `environment: Environment`
- `queryKey?: QueryKey`: [Query Keys](../guides/query-keys)
- `filters?: QueryFilters`: [Query Filters](../guides/query-filters)

**Returns**

This method does not return anything
