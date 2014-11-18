Meteor-TDD
==========

Notes & experiments as I teach myself test driven development (TDD) in Meteor. My goal is to be able to use these methods effectively in my own work and also to develop lesson plans for teaching pair programming in my classes (I teach Exploring Computer Science and IB Computer Science at the US high school level). In my classes I'd like to use the coding retreat model from the [Global Day of Coderetreat](http://globalday.coderetreat.org).

Background
==========

**[Test Driven Development](http://en.wikipedia.org/wiki/Test-driven_development):**

In the [Meteor Cookbook](https://github.com/awatson1978/meteor-cookbook) the recipe [Test Driven Development](https://github.com/awatson1978/meteor-cookbook/blob/master/cookbook/test-driven-development.md) that provides a good introduction.

People, Terms, and Practices:

* [Kent Beck]()
* [extreme programming](http://en.wikipedia.org/wiki/Extreme_programming)
* [agile](http://en.wikipedia.org/wiki/Agile_software_development)
* [pair programming](http://en.wikipedia.org/wiki/Pair_programming) at the end of this article there are some interesting looking links with more details and video of pair programming teams at work.

**[Behavior Driven Development]():**

People, Terms, and Practices:

* []()

Tools
=====

[Velocity](https://github.com/meteor-velocity/velocity): Velocity is the official testing framework for Meteor. Typically you would add Velocity to your project by including a Velocity compatible test tool to your project. In turn those tools would pull in Velocity. For example the command:

  ```meteor add mike:mocha```

adds the Mocha test framework to your project, which in turn pulls in velocity:core and velocity:html-reporter.

Velocity is a reactive test runner. It monitors any files that change in the tests directory at the root of your project. It also notices when Meteor starts (or restarts). Either of these events results in a notice to the installed test frameworks to rerun their tests. The frameworks report pack to Velocity who in turn makes them available via a Reporter.

## Test Frameworks

Meteor's test frameworks often build on existing Node.js test frameworks – adding the code needed to make them work in a reactive context.

Framework Types:

* ATDD
* BDD
* TDD
* Unit Tests

  Have access to the internals of the unit under test.

  * In-context Unit Tests
  * Isolated Unit Tests

* Integration Tests
* End-to-end Browser Automation
* End-to-end Headless Browser Automation
* Code Coverage
* Package Tests
* **Acceptance Tests:** Treat the application as a "black box" testing only inputs and outputs.

* Static Code Analysis


* **[Mocha](http://mochajs.org):** TDD, BDD Integration, and In-context Unit tesing. Both server- and client-side integration testing are supported. The Meteor package for the Mocha framework is [mike:mocha](https://github.com/mad-eye/meteor-mocha-web), it uses Chai for assertions. The [Mocha project](https://github.com/mochajs/mocha) is hosted on GitHub.

  ```meteor add mike:mocha```

  Mocha uses an external library for assertions, all that the library needs to do is to throw an assertion. Libraries that are known to work include:
  * [better-assert](https://github.com/tj/better-assert): c-style self-documenting assert() statements.
  * [Chai Assertion Library](http://chaijs.com): a _"BDD/TDD assertion library for node and the browser that can be delightfully paired with any javascript testing framework."_ Chai provides assert(), expect(), and should style assertions. [Chai for Metor]() is frequently pulled in as a dependency of another package such as Mocha.
  * [expect.js](https://github.com/LearnBoost/expect.js): expect() style assertions.
  * [should.js](https://github.com/tj/should.js): BDD style assertions.

* **[Jasmine](http://jasmine.github.io):** A [behavior driven development](http://en.wikipedia.org/wiki/Behavior-driven_development) framework for  testing JavaScript and Ruby (and maybe Python too). Meteor/Velocity integration can be found here: [sanjo:meteor-jasmine](https://github.com/Sanjo/meteor-jasmine). To install:

  ```meteor add sanjo:jasmine```

  The Jasmine framework for Meteor is built on [Jasmine 2.0](http://jasmine.github.io/2.0/introduction.html).

* **[Tiny Test]():**

  * [Writing Unit Tests (with Tiny Test)](https://github.com/awatson1978/meteor-cookbook/blob/master/cookbook/writing.unit.tests.md)

* **[Cucumber]():**

* **[JSHint]():**

* **[Istanbul]():** Code coverage reporting via [xolvio:coverage
](https://github.com/xolvio/meteor-coverage/)


* **[Nightwatch](http://nightwatchjs.org/):** [clinical:nightwatch](https://github.com/awatson1978/selenium-nightwatch)

## Testing With Captured Browsers

* [Karma](http://karma-runner.github.io): The AngularJS test runner has been integrated with Metor as [sanjo:karma](https://github.com/Sanjo/meteor-karma.git). It is currently using version [0.12](http://karma-runner.github.io/0.12/index.html). Out of the box it automatically launches Google Chrome.

  * [AngularJS Testing with Karma and Jasmine](http://www.tuesdaydeveloper.com/2013/06/angularjs-testing-with-karma-and-jasmine/)
  * [JavaScript TDD with Jasmine and Karma](http://kroltech.com/2013/11/javascript-tdd-with-jasmine-and-karma/)

* [Proctor]():

* [PhantomJS](): Fake browser.

## Reporters

Reporters provide in-browser access to test results.

* [velocity:html-reporter](https://github.com/meteor-velocity/html-reporter/): add a dot in the upper right hand corner of the Meteor page displaying the test status. Clicking on the dot displays detailed test results.

  ```meteor add velocity:html-reporter```


Editors and IDEs
================

Tutorials
=========

Meteor specific testing tutorials and useful examples. When working with any of these tutorials you may have to do some experimenting with versions. Much of the test code is under active development and you may need to force an update. Like this:

```
meteor list # note any asterisks next to packages
meteor show <package name> # get a list of available versions
meteor update <package name>@<the version you want> # read the package issues
```

* [velocity-examples](https://github.com/meteor-velocity/velocity-examples):
This looks to be the "offical" set of examples. There is sample code for tests with Cucumber, Jasmine, and Mocha. The ReadMe links to several additional tutorials:
  * [Writing Acceptance Tests (with Nightwatch)](https://github.com/awatson1978/meteor-cookbook/blob/master/cookbook/writing.acceptance.test.md)
  * [Writing Unit Tests (with Jasmine and Velocity)](https://github.com/awatson1978/meteor-cookbook/blob/master/cookbook/writing.unit.tests.with.jasmine.md)
  * [Writing Unit Tests (with Tinytest)](https://github.com/awatson1978/meteor-cookbook/blob/master/cookbook/writing.unit.tests.md)


* [Bullet-proof Meteor applications with Velocity, Unit Testing, Integration Testing and Jasmine](http://doctorllama.wordpress.com/2014/09/22/bullet-proof-internationalised-meteor-applications-with-velocity-unit-testing-integration-testing-and-jasmine/):
This is a fairly recent (Meteor 0.9.3, it can be made to work with 1.0 by forcing package updates if necessary) and highly detailed tutorial, you can clone the code from its repository on GitHub: [https://github.com/tomitrescak/BulletProofMeteor](https://github.com/tomitrescak/BulletProofMeteor). The author, Tomas Trescak, is active in the comments section. Even though Meteor testing is a moving target and a lot of the tutorials that you'll find right now (late 2014) are out of date, this one is a good bet. Just be sure to read the comments and make sure you're using the right verison of Meteor.



Project Setup
=============

Quick start

Running tests from packages.

Resources
=========

Useful materials I discovered along the way:

* [mad-eye/meteor-mocha-web](https://github.com/mad-eye/meteor-mocha-web)
* [Writing Unit Tests With Jasmine and Velocity](https://github.com/awatson1978/meteor-cookbook/blob/master/cookbook/writing.unit.tests.with.jasmine.md)
* [Introduction to Velocity](https://www.youtube.com/watch?v=kwFv1mXrLWE&feature=youtu.be&t=40m51s): video of talk at SF DevShop 2014 by some of the Velocity development team.
* [Meteor Cookbook](https://github.com/awatson1978/meteor-cookbook/blob/master/cookbook/writing.unit.tests.with.jasmine.md)
* [Meteor Testing](http://www.meteortesting.com) by Sam Hatoum: Book, still in development. A free chapter introducing Velocity is available for review, you can also purchase the "beta edition."

Packages
========

Quick notes on other packages that get pulled into the fray:

* [velocity:shim]()
* [amplify]()

Other packages (I've seen references to these but haven't actually seen any of them get pulled in):

* [velocity:ci]()
* [velocity:meteor-stubs]()
