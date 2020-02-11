# Apollo Client

## Resolvers

Signature

```js
fieldName: (parent, args, context, info) => data;
```

Arguments of resolver

-   `parent`. An object that contains the result returned from the resolver on the parent type.
-   `args`. An object that contains the arguments passed to the field.
-   `context`. An object shared by all resolvers in a GraphQL operation.
-   `info`. Information about the execution state of the operation.

`Context` contains:

-   `client`.
-   `cache`. Has `readQuery`, `writeQuery`, `readFragment`, `writeFragment`, `writeData`, `getCacheKey` (returns a key from the cache using a \_\_typename and id).

## API

### Hooks

-   `useQuery`.
-   `useLazyQuery` - executes query after manual trigger.
-   `useMutation`.
-   `useApolloClient`.

## Update cache

-   `client.writeData`
-   `client.onResetStore(callback)`
-   `client.writeQuery({ query, data })`.
-   `client.readQuery({ query })`.

-   `@client(always: true)` - always rerun local resolver on query.
