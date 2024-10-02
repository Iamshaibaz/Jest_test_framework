# Jest_test_framework
## Jest Setup Guide

This guide walks you through setting up Jest, a popular testing framework for JavaScript and TypeScript.

## 1. Install Jest

To install Jest, first ensure you have an `npm` project initialized. If not, you can do so by running:

```bash
npm init -y
```

Now, install Jest as a development dependency:

```bash
npm install --save-dev jest
```

## 2. Configure `package.json`

To run tests using Jest, add the following script in the `scripts` section of your `package.json` file:

```json
{
  "scripts": {
    "test": "jest"
  }
}
```

This will allow you to run tests with the command:

```bash
npm test
```

## 3. Create Your First Test

1. Create a new file `sum.js` with the following content:

```javascript
// sum.js
function sum(a, b) {
  return a + b;
}
module.exports = sum;
```

2. Then, create a test file inside a `__tests__` folder:

```javascript
// __tests__/sum.test.js
const sum = require('../sum');

test('adds 1 + 2 to equal 3', () => {
  expect(sum(1, 2)).toBe(3);
});
```

## 4. Run the Test

You can now run the test using the following command:

```bash
npm test
```

You should see the test result in the terminal, indicating whether the test passed or failed.

## 5. Configuring Jest (Optional)

If you need custom configurations, create a `jest.config.js` file at the root of your project with the following content:

```javascript
module.exports = {
  verbose: true,
  testEnvironment: "node",
  collectCoverage: true,
  coverageDirectory: "coverage",
};
```

This enables detailed test results, sets the test environment to Node.js, and collects coverage reports in the `coverage/` folder.

## 6. Additional Features

- **Coverage Reports**: You can enable test coverage by updating your test script in `package.json`:

```json
{
  "scripts": {
    "test": "jest --coverage"
  }
}
```

This will generate a coverage report when you run the tests.

- **Snapshot Testing**: Jest supports snapshot testing for UI components (useful in React). You can add snapshot tests using `toMatchSnapshot()`.

Now you're all set to write and run tests using Jest!!!
