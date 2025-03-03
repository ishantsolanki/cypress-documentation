---
title: clearAllLocalStorage
---

Clear
[`localStorage`](https://developer.mozilla.org/en-US/docs/Web/API/Window/localStorage)
data for all origins with which the test has interacted.

<Alert type="warning">

Cypress automatically clears all local storage _before_ each test to prevent
state from being shared across tests when
[test isolation](/guides/core-concepts/writing-and-organizing-tests#Test-Isolation)
is enabled. You shouldn't need to use this command unless you're using it to
clear localStorage inside a single test or test isolation is disabled.

</Alert>

## Syntax

```javascript
cy.clearAllLocalStorage()
cy.clearAllLocalStorage(options)
```

### Usage

**<Icon name="check-circle" color="green"></Icon> Correct Usage**

```javascript
cy.clearAllLocalStorage()
```

### Arguments

**<Icon name="angle-right"></Icon> options** **_(Object)_**

Pass in an options object to change the default behavior of
`cy.clearAllLocalStorage()`.

| Option | Default | Description                                                                              |
| ------ | ------- | ---------------------------------------------------------------------------------------- |
| `log`  | `true`  | Displays the command in the [Command log](/guides/core-concepts/cypress-app#Command-Log) |

### Yields [<Icon name="question-circle"/>](/guides/core-concepts/introduction-to-cypress#Subject-Management)

- `cy.clearAllLocalStorage()` yields `null`.

## Rules

### Requirements [<Icon name="question-circle"/>](/guides/core-concepts/introduction-to-cypress#Chains-of-Commands)

- `cy.clearAllLocalStorage()` requires being chained off of `cy`.

### Assertions [<Icon name="question-circle"/>](/guides/core-concepts/introduction-to-cypress#Assertions)

- `cy.clearAllLocalStorage()` cannot have any assertions chained.

### Timeouts [<Icon name="question-circle"/>](/guides/core-concepts/introduction-to-cypress#Timeouts)

<List><li>`cy.clearAllLocalStorage()` cannot time out.</li></List>

## See also

- [`cy.clearAllSessionStorage()`](/api/commands/clearallsessionstorage)
- [`cy.clearCookies()`](/api/commands/clearcookies)
- [`cy.clearLocalStorage()`](/api/commands/clearlocalstorage)
- [`cy.getAllLocalStorage()`](/api/commands/getalllocalstorage)
- [`cy.getAllSessionStorage()`](/api/commands/getallsessionstorage)
