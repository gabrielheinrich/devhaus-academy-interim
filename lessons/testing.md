## Why do we need tests?

- There's no other way to catch bugs

### Free Benefits

- Testable code is composable code
- Confidence to change code

### Kinds of software testing

#### Manual testing

x

- Done by developer / tester
- Manual work
- Error Prone
- No setup needed

#### Unit Testing

- Automated scripts that test small parts in isolation
- Catch bugs early and close to their actual source
- Necessary for robustness

#### End to End Testing / Integration Testing

- Automated tests that test the complete application
- Difficult to setup
- Good for less fine-grained testing

### Costs of testing

- Every dependency has to be mocked
- For simple apps > 50% of development time
- UIs are hard to test
- A test suite increases the costs of changes, because more code has to be rewritten

### What to test / not to test

- Test return values and side effects, based on input arguments and scenario
- Don't test libraries, it's the job of the library maintainers
- Don't test the specific implementation, i.e. test what a function does, not how it does it
- Every bug found in production / manual testing should become a unit test

#### Note: Exhaustive testing is impossible. Why?

### Unit Testing Setup

- For every source code file there's a test file
- The test file imports the functions that should be tested from the source code file
- In the test file, tests are split up into test suites and test cases
- In every test case we call one of the imported functions with some test inputs and check the outputs
  - Test frameworks contain a library of assertions, that make it easier to do these kind of checks
- A test runner can be invoked from the command line
  This will run all the test cases from all test files and output to the console a detailed report about which tests passed and which failed.

### Test Driven Development

Test Driven Development is the gold standard of Software Development

#### Rule: No implementation may be written if there's not a failing test case.

#### Benefits

- You have to think before you code
- Automatic documentation / specification of every feature
- Double checking: Implementation checks tests, tests check implementation
- Fully tested robust application

#### Drawbacks

- Requires more initial effort
- Testing is often harder than writing the implementation

### Jest

- [Jest Setup](https://jestjs.io/docs/en/getting-started)
- [Jest Matchers](https://jestjs.io/docs/en/using-matchers)

#### Reference

- [Jest globals](https://jestjs.io/docs/en/api)
- [Jest expect](https://jestjs.io/docs/en/expect)
- [Jest Mocking](https://jestjs.io/docs/en/mock-functions)
- [Jest Mock Functions](https://jestjs.io/docs/en/mock-function-api)
