# GraphQL

-   Query fields are executed in parallel, mutations in series.
-   Supports interfaces and types.

## Type system

### Basic types

There types are entry point of app.

-   `Query`. Each GraphQL service should have this type.
-   `Mutation`.

### Primitive types

-   `Int`. A 32‐bit integer.
-   `Float`. A double-precision floating-point value.
-   `String`. A UTF‐8 character sequence.
-   `Boolean`.
-   `ID`. Unique identifier.

### Complex types

-   Lists.
-   Object types.
-   Enums.
-   Union types.
-   `input` types. Object types is used for mutations. Can't have arguments.
-   `scalar`.
-   `!` - non-nullable field. Non-nullable arrays can be empty.

### Introspection types

-   `__directive`.
-   `__enumValue`.
-   `__field`.
-   `__inputValue`.
-   `__schema`.
-   `__type`.
-   `__typeKind`.
-   `__typename` returns name of data type.

## Directives

-   `@include(if: Boolean)`.
-   `@skip(if: Boolean)`.

## Examples

Variables is preceded by `$`.

```
{
    input Review {
        id: ID
        name: String
    }

    # Comment
    onePerson: person(id: String) {
        job
        age
        ...comparisonFields
    }
    otherPerson: person(id: String, withFriends: Boolean) {
        job
        age
        friends @include(if: $withFriends) {
            name
        }
        ...comparisonFields
    }

    fragment comparisonFields on Character {
        birthday
        name
    }
}
```

Inline fragments is used for creating disjoint unions types.

```
query HeroForEpisode($ep: Episode!) {
  hero(episode: $ep) {
    __typename
    ... on Human {
      name
    }
    ... on Droid {
      name
    }
    ... on Starship {
      name
    }
  }
}
```
