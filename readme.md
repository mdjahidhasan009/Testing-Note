# Types of Tests

## Unit
- Method
- Class 
- Module

## Integration

## End-to-End(E2E)

# AAA Principle
## Arrange

## Act

## Assert

## Example
```js
describe('Utils test suite', () => {
    test('Should return uppercase', () => {
        //arrange
        const sut = toUpperCase;
        const expected = 'ABC';

        // act
        const actual = sut('abc');

        //assert
        expect(actual).toBe(expected);
    })
})
```



# Setup and Teardown


# F.I.R.S.T. Principle
Principal, not rules, that we my follow when writting test
### Fast
* Unit test should be fast
  * Faster tests - faster feedback
  
### Independent / Isolated
* Tests should be isolated from
  * Other tests
  * External Environment
    * No shared state with other tests
    * The order in which tests run should not matter
    * Contradiction with the F(fast) principle
      * Individual test take more time to setup

### Repeatable
* Same result with same input
  * Challenges: Random/Date values - we will often mock those
* Example: test that writes to a database
  * It should always clean up
* In contradiction with Fast principle
  * More setup and teardown operations

### Self-Validating
* After the test is finished, it's result should be clear
  * Pass/fail
  
### Thorough
* Cover all the cases/paths/scenarios
  * Hard to think at all of them from the beginning
* Hard cases, bad paths, edge cases
* Invalid values
* Large values
* 100% code coverage - not a great indicator

# RED GREEN BLUE cycle
* RED failing test
* GREEN passing test
* BLUE change or add logic


# Low Mock vs High Mock
* Low Mock
  * Mocking only the dependencies of the unit under test
  * Mocking only the direct dependencies of the unit under test
* High Mock
  * Mocking all the dependencies of the unit under test
  * Mocking all the dependencies of the dependencies of the unit under test


# Environment Variables

# Multiple Test Configurations

# Snapshot Testing
- Test large objects
- Test UI components, generated login (JSON, HTML, XML etc)

# Custom Matchers

# The NodeJs Native Test Runner

# Jest
* Test Runner
* Assertion Library
* Mocking Library
## Jest Advantages
* One tool for all
* Easy TS integration
* Popular (better support)
* Test UI features(React)

# Mocha
* Test Runner

# SinonJs
* Complex mocking library

# Chai
* Assertion library


### Resources
* [Unit Testing for Typescript & NodeJs Developers with Jest](https://www.udemy.com/course/unit-testing-typescript-nodejs)