# Regular expressions

## Methods

-   `String.prototype.match(/regExp/)`. Returns `null|string[]`.
-   `String.prototype.replace(/regExp/, replacement).`
-   `Regexp.prototype.test(string)`.

## Flags

-   `i` - case-insensitive.
-   `g`.
-   `s` - "dotall" regimen. Enables interpretation `.` as `\n`.
-   `m` - multiline search. Anchors `^` and `$` search in each new line.

## Symbol classes

-   `\d`.
-   `\s`.
-   `\w` - letters and underscore.
-   `.` - any symbol except linebreak.

## Anchors

-   `^` - start position.
-   `$` - end position.
-   `\b` - break of word - when surrounded by symbols matching `\w`.

## Symbols that require escaping

[ \ ^ \$ . | ? \* + ( )

## Set and range

Set is list of characters - `[abc]`. Excluding sets is preceded by caret - `[^abc]`.
Range is pre-defined list of characters.

### Escaping in ranges

-   Don't escape `. + ( )`.
-   Don't escape `-` at start or end.
-   Escape `^` at start.
-   Always escape `]`.

## Quantifiers

### Declaration

`{count}` or `{min,max}`
Max count can be omitted.

### Shortcuts

-   `+`- one or more.
-   `*` - zero or more.
-   `?` - zero or one.

### Lazy and greedy

Greedy quantifiers - default - takes as many symbols as possible.

Lazy quantifiers is activated by `?`, preceded by other quantifier.

## Examples

```js
const HTMLCommentPattern = /<!-{2,}.*?-{2,}>/gs;
const HTMLTagPattern = /<[^<>]+>/;
```
