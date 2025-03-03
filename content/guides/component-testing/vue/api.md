---
title: 'Vue API'
---

## Methods

### mount

```js
// Vue 3
import { mount } from 'cypress/vue'

// Vue 2
import { mount } from 'cypress/vue2'
```

<table class="api-table table-list">
  <tr>
    <td>Description</td>
    <td>
      Used for mounting Vue components in isolation. It is
      responsible for rendering the component within Cypress's sandboxed iframe and
      handling any framework-specific cleanup.
    </td>  
  </tr>
  <tr>
    <td>Signature</td>
    <td>mount(originalComponent: { new (...args: any[]): {}; __vccOpts: any; }, options?: MountOptions): Cypress.Chainable&lt;MountReturn&gt;</td>
  </tr>
</table>

<table class="api-table">
  <caption>mount Parameters</caption>
    <thead>
    <td>Name</td>
    <td>Type</td>
    <td>Description</td>
  </thead>
  <tr>
    <td>originalComponent</td>
    <td>new (...args: any[])</td>
    <td>The component to mount in test</td>
  </tr>
  <tr>
    <td>options</td>
    <td>MountOptions (optional)</td>
    <td>The options for mounting the component</td>
  </tr>
</table>

## Interfaces

### MountOptions

([Vue 3 MountingOptions](https://test-utils.vuejs.org/api/#mount) or
[Vue 2 MountingOptions](https://v1.test-utils.vuejs.org/api/options.html)) from
[Vue Test Utils](https://test-utils.vuejs.org/)

### MountReturn

Type that the `mount` function yields

<table class="api-table">
  <caption>members</caption>
  <thead>
    <td>Name</td>
    <td>Type</td>
    <td>Description</td>
  </thead>
  <tr>
    <td>wrapper</td>
    <td>VueWrapper</td>
    <td>The Vue Test Utils `wrapper`</td>
  </tr>
  <tr>
    <td>component</td>
    <td>VueComponent</td>
    <td>The component instance</td>
  </tr>
</table>
