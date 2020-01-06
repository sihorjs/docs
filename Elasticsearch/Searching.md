# Searching data

## Basic usage

### API

Endpoint - GET /index/\_search

Usage:

-   From querystring

```
q=+key:value+key:value
```

-   Body of get request

```json
{
    "query": {
        "query_type": {
            "search_field": "query params"
        }
    }
}
```

### Concepts

**Levenshtein edit distance** represents number of misspellings (deletions, insertions, typos).

**Slop** - distance in both directions between words in query phrase.

**N-grams**. Edge n-grams are built from beginning of each term.

To **sort** analyzed text field make keyword copy in mappings.

**Exact-match search** uses keyword mappings.
**Partial-match search** uses data handled by analyzers.

### Search request params:

| Param  | Type of value | Definition                                 |
| ------ | ------------- | ------------------------------------------ |
| size   | integer       | Quantity of results                        |
| from   | integer       | Start position                             |
| pretty | bool          | Flag to display results in prettified form |
| sort   | string        | Name of field that used as sort key        |

## Filters

-   `term` - exact match of string.
-   `terms` - match from list values.
-   `range`.
-   `exists`.
-   `missing`.
-   `bool` - used with keywords `must`, `must_not`, `should` (equivalent `or`).

## Queries

-   `match_all` - return all documents.
-   `match` - full text search.
-   `match_phrase`.
-   `match_phrase_prefix`.
-   `multi_match` - searches on multiple fields.
-   `bool` - works like bool filter, return results, scored by relevance.
-   `prefix`.
-   `wildcard`.
-   `fuzzy` - used for input that can contain typos. `fuzziness` param defines levenshtein distance.

### Auto fuzziness

-   0 for 1-2 characters.
-   1 for 3-5 characters.
-   2 for > 5 characters.

## Example

```json
{
    "query": {
        "bool": {
            "must": {
                "term": {
                    "title": "your search input"
                },
                "filter": {
                    "range": {
                        "year": {
                            "gte": 1980
                        }
                    }
                }
            }
        }
    }
}
```
