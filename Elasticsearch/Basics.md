# Elasticsearch basics

## API

| Address                | Method | Description              | Has body |
| ---------------------- | ------ | ------------------------ | -------- |
| /                      | PUT    | Mappings                 | y        |
| /\_doc                 | PUT    | Add new document         | y        |
| /\_doc/doc_id          | GET    | Get document             | n        |
| /\_doc/doc_id/\_update | POST   | Update existing document | y        |
| /\_doc/doc_id          | DELETE | Delete document          | n        |
| /\_bulk                | PUT    | Bulk import              | y        |
| /\_search              | GET    | Search documents         | y        |

## Concepts

### Document

Document is basic unit. Docs are immutable. Contains \_seq_no and \_primary_term to handle concurrency.

### Index

Index is collection of documents. Can hold only one type of documents. Contains mappings and inverted indices.

## Types of data

-   string.
-   date.
-   short integer.
-   long integer.
-   float.
-   double precision floating number.

Disable full-text search of field:

```json
{
    "mappings": {
        "properties": {
            "year": {
                "index": "not_analyzed"
            }
        }
    }
}
```

```json
{
    "mappings": {
        "properties": {
            "year": {
                "type": "date"
            },
            "description": {
                "analyzer": "english"
            }
        }
    }
}
```

## Analyzer

-   Filters characters.
-   Tokenizes input.
-   Filters tokens.

## Inverted index

Inverted index - collection of search terms.

Relevance is measured by TF \* IDF

-   Term frequency (TF) - frequency of word in document
-   Document frequency (IDF) - frequency of term in all documents
