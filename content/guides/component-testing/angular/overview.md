---
title: 'Angular Component Testing'
---

## Framework Support

Cypress Component Testing supports Angular 13+.

## Tutorial

Visit the
[Angular Quickstart Guide](/guides/component-testing/angular/quickstart) for a
step-by-step tutorial on creating a new Angular app and adding component tests.

## Installation

To get up and running with Cypress Component Testing in Angular, install Cypress
into your project:

```bash
npm i cypress -D
```

Open Cypress:

```bash
npx cypress open
```

<DocsImage 
  src="/img/guides/component-testing/select-test-type.jpg" 
  caption="Choose Component Testing"> </DocsImage>

The Cypress Launchpad will guide you through configuring your project.

<Alert type="info">

For a step-by-step guide on how to create a component test, refer to the
[Angular Quickstart](/guides/component-testing/angular/quickstart) guide.

For usage and examples, visit the
[Angular Examples](/guides/component-testing/angular/examples) guide.

</Alert>

## Framework Configuration

Cypress Component Testing works out of the box with `@angular/cli` projects.
Cypress will automatically detect your project is Angular during setup and
configure it properly. The examples below are for reference purposes.

### Angular CLI Configuration

<cypress-config-file>
<template #js>

```js
module.exports = {
  component: {
    devServer: {
      framework: 'angular',
      bundler: 'webpack',
    },
    specPattern: '**/*.cy.ts',
  },
}
```

</template>
<template #ts>

```ts
import { defineConfig } from 'cypress'

export default defineConfig({
  component: {
    devServer: {
      framework: 'angular',
      bundler: 'webpack',
    },
    specPattern: '**/*.cy.ts',
  },
})
```

</template>
</cypress-config-file>

#### Options API

You can also use the `options` API to provide your own project specific
configuration to your `devServer`. The `devServer` configuration receives an
`options` property:

<code-group>
<code-block label="cypress.config.ts" active>

```ts
import { defineConfig } from 'cypress'

export default {
  component: {
    framework: 'angular',
    bundler: 'webpack',
    options: {
      projectConfig: {
        root: '',
        sourceRoot: 'apps/my-app',
        buildOptions: {
          outputPath: 'dist/my-app',
          index: 'apps/my-app/src/index.html',
          main: 'apps/my-app/src/main.ts',
          polyfills: 'apps/my-app/src/polyfills.ts',
          tsConfig: 'apps/my-app/tsconfig.app.json',
          inlineStyleLanguage: 'scss',
          assets: ['apps/my-app/src/favicon.ico', 'apps/my-app/src/assets'],
          styles: ['apps/my-app/src/styles.scss'],
          scripts: [],
          buildOptimizer: false,
          optimization: false,
          vendorChunk: true,
          extractLicenses: false,
          sourceMap: true,
          namedChunks: true,
        },
      },
    },
  },
}
```

</code-block>
</code-group>

#### Sample Angular Apps

- [Angular 14](https://github.com/cypress-io/cypress-component-testing-apps/tree/main/angular)
