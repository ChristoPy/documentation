---
title: Derive - ElysiaJS
head:
  - - meta
    - property: 'og:title'
      content: Derive - ElysiaJS

  - - meta
    - name: 'description'
      content: Derive allows you to customize `Context` based on existing `Context` as `Context.store`, useful when you to need to create a value based on an existing value reactively

  - - meta
    - property: 'og:description'
      content: Derive allows you to customize `Context` based on existing `Context` as `Context.store`, useful when you to need to create a value based on an existing value reactively
---

# Derive
Just like _state_ and _decorate_, derive allows you to customize `Context` based on existing `Context` as `Context.store`.

This is useful when you need to create a value based on an existing value reactively.

### Example
```typescript
app
    .state('version', 1)
    .decorate('getDate', () => Date.now())
    .derive(({ request: { headers }, store, getDate }) => {
        return {
            authorization: headers.get('Authorization')
        }
    })
    .get('/version', ({ authorization }) => authorization
)
```
