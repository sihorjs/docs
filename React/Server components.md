# Server components

Server components - components rendered on the server only. Default for newer version of react.

- Not included in bundle
- Read-only.

Client receives react server components payload (RSC payload). RSC payload contains output of RSC and placeholders for client components. After initial load RSC payload used for reconciliation server and client component trees.

Use cases:

- Data fetching
- Access to back-end resources (including direct access to DB)

In next.js server components in combination with `Suspense` can be used for streaming of HTML.

## Client components

**Client components** - can be rendered on the server and client.

Marked with directive `use client`. All components in client component are automatically become client components and bundled.

Use cases

- Browser API
- Access to state, effects and context

## Combination of client components

**Important**: client component cannot import server component directly. However, server components can be added passed as props or children to client component:

```tsx
<ClientComponent>
  <ServerComponent />
</ClientComponent>
```
