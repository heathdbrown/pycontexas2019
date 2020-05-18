# Egad! How do we start writing (better) Tests?

Everyone has ran into software bugs.
No one really tests their code.

Why don't we automate those tests?

## Three tough points

1.) Test automation is necessary
2.) Test automation is hard
3.) Test automation is intimdating

Teams either skip test coverage and hire for manual
Teams will try...but not implemented well and the tests gets in the way

## Where do I start?

What is your main goal?

Make sure the critical parts are working and tests will catch errors

Sounds like functional tests


## The Automated TEsting Pyramid

How to structure

All sections are functional tests

Bottom: White Box (makes calls directly in code)
 - Unit Tests: 1ms (strong foundation, to catch quickly)

Top: Black Box (makes calls to deployed layers) (feature tests)
 - Integration: 1s Cover where things meet
 - End-to-End: 1m Cover passes through entire system, like the user would enter

## What skills do you need to get started?

Test automation university

## What framework should we use?

If doing python....

pytest is pretty solid if using python

More than just a framework...you need packages (look before you leap)
  - requests
  - selenium
  - flask
  - django
  - splinter

## Resources

Books:
  - Python testing with pytest
  - pytest quick start guide
  - Hands-on enterprise automation with python

## How do you avoid duplicate code ?

Avoid duplication by using tools to run against various tests

Hypothesis
pytest-bdd

Python Talks at 2018

## How do I handle test data?

White box test data generated by mock

Black box test data
  - Test Values
    - Used by test cases for validation
    - Handle on the fly
    - Always clean up after test
  - Config Data
    - input values like URL and usernames
    - Never hard-code into automation
    - Best to pu in key mgmt service
  - Ready State
    - Used by many tests and expensive to set up
    - Use scripts to prepare before test suite runs
    - Reset periodically to avoid test damage

## Which tests should we automate?

Automation is expensive focus on ROI

### Good for automation

- Core feature behaviors
- Happy paths
- Tests that must be run repeatedly
- Tests with straightforward setup

### Good for manual testing

- Edge cases
- one-off checks
- Tests requiring complicated setup
- Exploratory tests
- UX / Look and feel checks

## How can we reduce the burden of testing burden?

Integrate tests into CI/CD - run tests in parallel pytest-xdist

Code needs to be fixtures and have no locking like logins

selenium-Grid

Sauce labs or browser stack

Auto notify feature owners of failures

## CI/CD

pytest + jenkins + pytest-xdist

## 4 Common Failure Reasons

More tests = more failures
1.) Feature under test has tricky bug
2.) Feature under test was updated without also updating the test
3.) automation didn't handle an unexpected condition
4.) automation itself is the bug

## How od you make test more reliable?

CI is production for test automation

Test code should follow same code rigor

Safety wrappers around remote calls and race conditions (contract testing)

Pursue better collaboration with the team for handling failures.