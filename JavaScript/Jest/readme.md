# Jest
* JavaScript/TypeScript testing framework
  * Developed by Facebook
* Test runner
  * Executes tests
  * Set of global functions
    * `test()`
    * `expect()`
    * `beforeEach()`
    * `afterEach()`
    * `beforeAll()`
    * `afterAll()`
    * `describe()`
    * `it()`
    * `jest.fn()`
    * `jest.mock()` etc.
* Assertion library
  * Powerful set of matchers
    * `toBe()` : For primitive type like number, string
    * `toEqual()` : For non-primitive type like object
    * `not.toBe()`
    * `toBeNull()`
    * `toBeUndefined()`
    * `toBeDefined()`
    * `toBeTruthy()`
    * `toBeFalsy()`
    * `toBeGreaterThan()` etc


## Parametrized tests
```js
describe('ToUpperCase examples', () => {
  it.each([
    {input:'abc', expected: 'ABC'},
    {input:'My-String', expected: 'MY-STRING'},
    {input:'def', expected: 'DEF'}
  ])('$input toUpperCase should be $expected', ({input, expected})=>{
    const actual = toUpperCase(input);
    expect(actual).toBe(expected);
  });
})
```

# Jest Aliases

## `describe.skip`, `test.skip`
## `describe.only`, `test.only`
## `test.concurrent`
## `test.todo`

# Ignoring code from test report
using `/* istanbul ignore next */` as comment we can ignore function or class to including from test report.

### Resources
* [Unit Testing for Typescript & NodeJs Developers with Jest](https://www.udemy.com/course/unit-testing-typescript-nodejs)