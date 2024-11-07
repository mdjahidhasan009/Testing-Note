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
    * `toContain()` : For array
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

# Test Doubles in Jest and Typescript
We need to use test doubles when we want to isolate the code under test from the rest of the system. We can use test
doubles to replace the real implementation of a dependency with a fake object that we can control and observe. Like
while test a function that uses a database, we can replace the real database with a fake database that we can control
and observe.

## Stubs
Stubs are incomplete implementations of a dependency that we can control and observe. They are used to replace the real
implementation of a dependency with a fake object that we can control and observe. We should not use them in assertions.

**OtherUtils.ts**
```ts
export type stringInfo = {
    lowerCase: string,
    upperCase: string,
    characters: string[],
    length: number,
    extraInfo: Object | undefined
}

export function calculateComplexity(stringInfo: stringInfo){
    return Object.keys(stringInfo.extraInfo).length * stringInfo.length
}
```
**OtherUtils.test.ts**
```ts
import {calculateComplexity} from "../../app/doubles/OtherUtils";

describe("OtherUtils test suite", () => {
    it("Calculate complexity", () => {
        const someInfo = {
            length: 5,
            extraInfo: {
                field1: 'someInfo',
                field2: 'someOtherInfo'
            }
        }

        const actual = calculateComplexity(someInfo as any);
        expect(actual).toBe(10);
    })
});
```

## Fakes
Fakes are objects that have working implementations, but not same as production one. Usually they take some shortcut and
therefore are not suitable for production.

## Mocks
Mocks are objects pre-programmed with expectations which form a specification of the calls they are expected to receive.

### Mocking Modules


## Spies
Spies are a type of mock that record the calls made to them so that we can assert that the code under test called the
dependency with the correct parameters.

## Dummy Objects
Dummy objects are objects that are passed around but never actually used. Usually they are just used to fill parameter
lists.

<br/></br>
In jest mocks and spies have a lot in common.
#### Spies Vs Mocks
* Spies are not directly injected in system under test(SUT).
* Original functionality is preserved in spies.
* Spices usually track method calls.

## TDD styles
### London Style - Low Focus on Mocks
* A unit: a collection of pieces
* Test from a broader view
* Little use of mocks

### Chicago Style - Heavy Focus on Mocks
* A unit: a class
* Mock all its dependencies




### Resources
* [Unit Testing for Typescript & NodeJs Developers with Jest](https://www.udemy.com/course/unit-testing-typescript-nodejs)