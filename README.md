# @deck.gl/test-utils minimal reproduction of "Failed to created device" error

This is a minimal reproduction of an error seen when using `@deck.gl/test-utils`:

```
Failed to created device 'undefined': Cannot read properties of null (reading 'addEventListener')
```

This occurs simply when trying to import `testLayer` (view the contents of `/test.js`):

```js
import { testLayer } from "@deck.gl/test-utils";
```

## Installation

1. Install Node.js: https://nodejs.org
1. Install Yarn: https://yarnpkg.com/getting-started/install
1. Clone the repo and navigate into it: `git clone git@github.com:davidcalhoun/deck.gl-test-utils-bug.git && cd deck.gl-test-utils-bug`
1. Install package dependencies: `yarn install`

## Running

Run `yarn test` and view the output, which should look similar to this:

```shell
yarn test
  console.error
    Failed to created device 'undefined': Cannot read properties of null (reading 'addEventListener')

    > 1 | import { testLayer } from "@deck.gl/test-utils";
        | ^
      2 |

      at createTestDevice (.yarn/__virtual__/@luma.gl-test-utils-virtual-e7922c1f22/3/.yarn/berry/cache/@luma.gl-test-utils-npm-9.0.14-cb312c65ae-10c0.zip/node_modules/@luma.gl/test-utils/dist/create-test-device.js:25:17)
      at Object.<anonymous> (.yarn/__virtual__/@luma.gl-test-utils-virtual-e7922c1f22/3/.yarn/berry/cache/@luma.gl-test-utils-npm-9.0.14-cb312c65ae-10c0.zip/node_modules/@luma.gl/test-utils/dist/create-test-device.js:30:28)
      at Object.<anonymous> (.yarn/__virtual__/@deck.gl-test-utils-virtual-39bcfdacb3/3/.yarn/berry/cache/@deck.gl-test-utils-npm-9.0.14-934d2420c7-10c0.zip/node_modules/@deck.gl/test-utils/dist/utils/setup-gl.js:1:48)
      at Object.require (test.js:1:1)
```
