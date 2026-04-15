---
title: 'Test Driven Development'
weight: 3
---
Test driven development (TDD) is a software development approach where:
- A test is defined that asserts the correct functionality of implementation code.
- It is confirmed that the test fails.
- Code is implemented until the test passes, and;
- Code is refactored to reduce code duplication, optimize for performance, and maintain high code quality. 
- Coverage is measured, and metrics on that coverage is tracked and reported as part of product tech debt and quality.

The primary reasons for using TDD are to reduce the number of bugs in software and support good code quality. Several secondary benefits also exists:
- Minimal code is written to provide the desired functionality.
- Tests live with the code repository and can be run continuously to give feedback about changes made to the codebase.
- Tests act as documentation for the codebase that describe the intent behind implementation code, providing team members confidence about the codebase in which they are working.
- Refactoring and optimizing efforts are easier since tests provide fast feedback.
- Testable code is enforced.
- Leads towards an application architecture that has low coupling and dependency inversion.
- Allows manual testers to focus their efforts on executing test cases that can’t be automated.
- Enables an efficient lean product practice where business direction for the product may pivot over time.

![TDD Image](/images/engineering/tdd.png)

## TDD steps
- Define a test that asserts the proper functionality of implementation code - Tests should be small in scope, specific, and fast-running. Avoid unnecessary tests – the fewer tests the better as this reduces execution time of the test suite and makes maintenance of the test suite easier over time
- Confirm that the test fails by running it – This confirms that existing code is functioning as expected. If the test were passing, it could indicate that the feature is already implemented or that the test doesn’t assert proper functionality.
- Implement code until the test passes – write the minimal amount of code required to make the new test pass as well, and run other tests in the test suite. 
- Commit the code
- Refactor – Refactoring after making tests pass is a way to reduce technical debt and ensure code is readable. This step may also be a good time to focus on doing performance enhancements. 
- Commit the code

## Example TDD Pattern
- For implementation code that require integration with a resource, here is an example that uses both integration and unit tests:
- Write an integration test for a specific behavior
- While integration test failing
- Write a unit test to fulfill partial behavior
- While unit test failing
- Write code to make unit test pass
- Commit
- While refactoring can be done
- Refactor
- While integration test failing
- Write code to make integration test pass
- Commit
- Push

## Other Guidelines
- Perform ping-pong pairing as a part of your pair programming approach. For each feature, assign one software engineer in the pair to write the test, and the other to write the implementation. After the successful completion of the TDD cycle (steps 1-4), the roles are swapped so that the software engineer that just wrote the implementation writes the test for the next feature. 
- Avoid trivial testing – Don’t test basic elements of the programming language, getter methods, setter methods, framework or library functionality, etc.
- Don’t always write tests for code spikes – sometimes it is unclear how to design or architect an application thereby making it impossible to write the test first. Spikes occur when testing is forgone to determine a usable design. After the spike is complete, the code used for the spike should be discarded and the feature should be rewritten using complete TDD cycles.
- Don’t TDD things that are too hard to test and provide minimal feedback value. Consider testing at a higher level of abstraction through component or manual testing.

## Good Tests
- Increase confidence
- ”Black Box” Functions
- Test behavior rather than implementation
- Have only one reason they can fail
- Have few assertions
- Mock the least amount needed
- Mock everything out of scope
- Easy to read 
- Run fast
- Aren’t coupled to other tests

## Bad Tests
* Depend on previous tests
* Test precise execution behavior timing or performance
* Test implementation details
* Mock out the file you are testing
* Test multiple steps
* Test frameworks
* Don’t actually test anything
* Are BIG
* Have huge setups

