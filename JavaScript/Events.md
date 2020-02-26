# Events

## Signature of `addEventListener`

-   `(event, handler, [{ once: boolean, capture: boolean, passive: boolean }) | capture: boolean]`.
-   `(event, {handleEvent(e) {}}`

Flag `passive` indicates that event will be not prevented.

## Event phases

-   `0` - capture
-   `1` - target.
-   `2` - bubbling.

## Event prevention

-   `e.preventDefault`.
-   `return false` on `onEvent` handlers.

## Event object

-   `defaultPrevented`.
-   `isTrusted` - is triggered by interaction.

## Event generation

Custom events is created by constructor `new Event(type: string), options: { bubbles = false: boolean, cancelable = false: boolean }`.

Events triggered by `element.dispatchEvent(e)` imperatively. Returns `false` if prevented.
