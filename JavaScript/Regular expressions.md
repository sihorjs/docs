# Regular expressions

## Methods

-   `String.prototype.match(/regExp/)`. Returns `null|string[]`.
-   `String.prototype.matchAll` returns collection of each capturing group. Can convert to array and refer to index or refer to name of capturing group. Returns empty collection if there is no match.
-   `String.prototype.replace(/regExp/, replacement).` Can refer to match capturing group using index (`$n`) or name (`$<name>`).

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

## Capturing groups

Capturing group `(...)` allows to extract match to separate array. Quantifiers in are applied to all content of group.

`String.prototype.match` without `g` flag return array: [wholeMatch, matchGroup1, matchGroup2, ...].

### Examples

```js
// Optional group
const optionalGroupRegExp = /([a-z])?/;

// Named group
const namedGroupRegExp = /(?<name>[a-z])/;

// Exclude match of capturing group from result
const excludeMatchFromRegExp = /(?:[a-z])/;

// Swap match of capturing groups
string.replace(/(a) (z)/, "$2 $1");
```

## Examples

```js
const HTMLCommentPattern = /<!-{2,}.*?-{2,}>/gs;
const HTMLTagPattern = /<[^<>]+>/;
const hexRegExp = /#([0-9a-f]{3}){1,2}\b/gi;
```
