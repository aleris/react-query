---
id: invalidateQueries
title: invalidateQueries
---

The `invalidateQueries` function can be used to invalidate and refetch single or multiple queries in the cache based on their query keys or any other functionally accessible property/state of the query. By default, all matching queries are immediately marked as invalid and active queries are refetched in the background.

- If you **do not want active queries to refetch**, and simply be marked as invalid, you can use the `refetchActive: false` option.
- If you **want inactive queries to refetch** as well, use the `refetchInactive: true` option

```js
await invalidateQueries(environment, 'posts', {
  exact,
  refetchActive = true,
  refetchInactive = false
}, { throwOnError })
```

**Options**

- `environment: Environment`
- `queryKey?: QueryKey`: [Query Keys](../guides/query-keys)
- `filters?: QueryFilters`: [Query Filters](../guides/query-filters)
  - `refetchActive: Boolean`
    - Defaults to `true`
    - When set to `false`, queries that match the refetch predicate and are actively being rendered via `useQuery` and friends will NOT be refetched in the background, and only marked as invalid.
  - `refetchInactive: Boolean`
    - Defaults to `false`
    - When set to `true`, queries that match the refetch predicate and are not being rendered via `useQuery` and friends will be both marked as invalid and also refetched in the background
- `refetchOptions?: RefetchOptions`:
  - `throwOnError?: boolean`
    - When set to `true`, this method will throw if any of the query refetch tasks fail.
