🔙 <a href="README.md">Back to previous page</a> 


<p align="center">
 <h2>Definition of test smells 🐞🐞🐞</h2>
</p>
<img width="100%" src="problems.svg" align="center" alt=""/>


🎀 <b>Code related </b>

* Code duplication
  * <b>Test Redundancy:</b> When there are similar test codes, even if there are few simple duplications.
  * <b>Annotation Repetition:</b> When there are similar test codes, even if there are few simple duplications.
  * <b>Unecessary Test:</b> Unit testing should be asserting the behavior of your class's features, when the test case does not fulfill this objective, it becomes dispensable (e.g. check visibility of its constructors and methods).
* Complex / Hard to understand
  * <b>Multiple Assertion:</b> There are two many assertions happening in one method, though indirectly and it defeats the idea of one responsibility per test.
  * <b>Verbose Test:</b> According to "Clean Code" any test that takes longer than 1/10th of a second is a test that takes too long.
  * <b>God Test Class:</b> A test class with too many test cases.
  * <b>Irrelevant Information:</b>  Data, variables, resources, or objects that are not essential for checking the behavior of the output class.
  * <b>Obscure Test:</b> Inappropriate choice of data structures that make the test difficult to understand.
  * <b>The Giant:</b> A unit test that, although it is validly testing the object under test, can span thousands of lines and contain many many test cases. The test is so complicated that it starts to contain bugs of its own or flaky behavior.
* Violating coding best practices
  * <b>Bad Namin:</b> Test methods and classes should follow the testing framework naming conventions. It allow developers to quickly look at a test name and determine roughly what tests are being done.
  * <b>Code Organization:</b> All tests should be associated with their respective production classes. Following the naming conventions, the project should have two source folders, one called src the other called test. The source folders should have the exact same package structure and each src Class has a test equivalent with "Test" appended to its name.
  * <b>Print Statement:</b> Printing from unit tests is not the right thing to do.
  * <b>Anal Probe:</b> A test which has to use insane, illegal or otherwise unhealthy ways to perform its task like: Reading private fields using Java's setAccessible(true) or extending a class to access protected fields/methods or having to put the test in a certain package to access package global fields/methods.
  * <b>Magic Number:</b> Test methods containing magic numbers. 
  * <b>Messy Tests:</b> Test methods that do not follow a coding standart or naming convention
  * <b>Sensitive Equality:</b> When the same unit test applied to data multiple items that are roughly equivalent (two non-empty strings). For example, this occurs when implement multiple unit test methods, with names like MethodNonEmptyValidString1 and MethodNonEmptyValidString2.
  * <b>The Test With No Name:</b> The test that gets added to reproduce a specific bug in the bug tracker and whose author thinks does not warrant a name of its own. Instead of enhancing an existing, lacking test, a new test is created with aleatory name (e.g.  testForBUG123).

🥏 <b>Depedencies</b>

* Dependencies among tests
  * <b>Coupling Between Test Methods:</b> A test that calls another test, it is a smell for some problem in your tests.
  * <b>Chain Gang:</b> A couple of tests that must run in a certain order, i.e. one test changes the global state of the system (global variables, data in the database) and the next test(s) depends on it. You often see this in database tests. Instead of doing a rollback in teardown(), tests commit their changes to the database. Another common cause is that changes to the global state aren't wrapped in try/finally blocks which clean up should the test fail.
  * <b>Order Dependent Tests:</b> I run a bunch of tests in parallel and some tests fail. I run them sequentially and they all pass.
* External dependencies
  * <b>Mystery Guest:</b> When (unit) testing, is is bad to expect the code to use certain paths or external resources. For example, using a 'real' database makes it hard to setup, take down, and isolate the unit tests.
  * <b>Tooling Details in Test Case: </b> You should decouple your business logic that's in charge of collecting all email addresses, email subject and body, from that 3rd party library. 
  * <b>Hidden Dependency:</b>A unit test that requires some existing data to have been populated somewhere before the test runs. If that data wasn’t populated, the test will fail and leave little indication to the developer, forcing them to dig through of code to find out where the data it was using was supposed to come from.
  * <b>Hardcoded dependency:</b> Objects depend upon other objects. Hard-coded dependencies can be stubbed out during testing, but only during testing. It is not possible to change behaviour or reuse code by providing different dependencies, if they are hard-coded.
  * <b>Dependencies on test containers: </b> If your test code depends on other components, the test results become less trustworthy - failing tests may be due to the other components, passing tests can be due to the created objects having different properties than intended in the test.
  * <b>State Leak:</b> When test cases fail differently depending on, for instance, what order they are run.
  * <b>The Butterfly:</b> You have to test something which contains data that changes all the time, like a structure which contains the current date, and there is no way to nail the result down to a fixed value. The ugly part is that you don't care about this value at all. It just makes your test more complicated without adding any value.
  * <b>The Conjoined Twins:</b> Tests that people are calling "Unit Tests" but are really integration tests since they are not isolated from dependencies (file configuration, databases, services, other in other words the parts not being tested in your tests that people got lazy and did not isolate) and fail due to dependencies that should have been stubbed or mocked.
  * <b>The Environmental Vandal:</b> A 'unit' test which for various 'requirements' starts spilling out into its environment, using and setting environment variables / ports. Running two of these tests simultaneously will cause 'unavailable port' exceptions etc.These tests will be intermittent, and leave developers saying things like 'just run it again'.One solution Ive seen is to randomly select a port number to use. This reduces the possibility of a conflict, but clearly doesnt solve the problem.
  * <b>The Local Hero:</b> A test case that is dependent on something specific to the development environment it was written on in order to run. The result is the test passes on development boxes, but fails when someone attempts to run it elsewhere.

🍊 <b>In association with production code</b>

* In association with production code
  * <b>Ugly mirror:</b> Creating complex objects from test code can make the test code complex and maintenance intensive. Re-using other application code to create these objects can simplify the test code, which otherwise would somehow duplicate the code for object creation.
  * <b>Test logic in production code:</b> Methods tests that include validating the result of other methods.
  * <b>Coupling with Production code:</b> Test methods calling several production methods or calling the same production method several times.
  * <b>Hard to co-evolve:</b> When a test method is coupled to other test methods or production code, any modification on its dependencies can broke the test.
  * <b>Obsolete tests:</b> Test case that may have been useful in the past. However, now is no longer used. These test case must be refactored.
  * <b>Doppelgänger:</b> In order to test something, you have to copy parts of the code under test into a new class with the same name and package and you have to use classpath magic or a custom classloader to make sure it is visible first (so your copy is picked up). This pattern indicates an unhealthy amount of hidden dependencies which you can't control from a test. 
  * <b>For Testers only:</b> Featurees or services that must run only in one type of environment, for example, emails were not to be sent on any other environment except live. If this standard is violated, it can degrade the quality of the application.
  * <b>Friction:</b> Existing tests that make it difficult to write new tests.
  * <b>Replicating Disadvantages of the Code:</b> If the utility functions themselves have further dependencies, or they compile, link or execute slowly, they bring all these disadvantages into the test code. 
  * <b>Second Class Citizens:</b> Unhandled duplications in test code, making it hard to maintain tests.
  * <b>The Forty Foot Pole Test:</b> Test classes do not test production classes because of the high abstraction level between them. Besides, such test classes include code lines from the code their are testing to replicate their logic. Therefore, these test classes are extremely brittle, and susceptible to many sorts of side-effects.

🔮 <b>Mock and stub related</b>

* Mock and stub related
  * <b>Using more than one mock for a test:</b> Test methods that use several mocks in cascade.
  * <b>Mock makes the test always passes:</b> Developers write tests where the mock is set up with an expectation, then the mock is called directly in the test. As a result, the test will always pass.
  * <b>Mocking whole classes:</b> Do not mock simple concrete classes.
  * <b>General Mocking:</b> There are not a shared implementation for mocks between methods, having as a consequence a duplication of mock.
  * <b>Is Mockito Working Fine:</b> Developers verify the implementations of Mockito API to ensure its correct behaviour instead of testing the production code.
  * <b>Mock call verification:</b> Developers often wirte mock call verifications. For example, given a service that has an injected repository, a unit test pass a mock of the Repository and verify that it was called within the method to be tested. This is a problem, because this practice turn the unit test are tightly coupled. 
  * <b>Mock naming:</b> Mocking objects that do not follow naming conventions.
  * <b>The Dead Tree:</b> A test which where a stub was created, but the test wasn't actually written.
  * <b>The Mockery:</b> Sometimes mocking can be good, and handy. But sometimes developers can lose themselves and in their effort to mock out what isn’t being tested. In this case, a unit test contains so many mocks, stubs, and/or fakes that the system under test isn’t even being tested at all, instead data returned from mocks is what is being tested.

🔔 <b>Issues in test steps</b>

* Issues in assertions
  * <b>Tests That Can’t Fail:</b> If the utility functions will never create malformed objects, then you might limit your testing such that you never test your SUT with malformed objects. I don't know how you would call this unit test but I strongly suggest you avoid writing it as there's nothing on earth to make the assert fail. 
  * <b>Inappropriate Assertions:</b> An inappropriate assertion is being used. For example, assertTrue is used to check the equality of values instead of assertEquals.
  * <b>Line hitter:</b> On the first look tests covers everything and code coverage tools confirms it with 100%, but in reality tests only hit code without any output analyses.
  * <b>Redundant Assertion:</b> Common set of expectation across several unit tests
  * <b>The Turing Test:</b> A testcase automagically generated by some expensive tool that has many, many asserts gleaned from the class under test using some too-clever-by-half data flow analysis. Lulls developers into a false sense of confidence that their code is well tested, absolving them from the responsibility of designing and maintaining high quality tests. If the machine can write the tests for you, why can't it pull its finger out and write the app itself!
* Issues in setup
  * <b>General Fixture:</b> When there is more stub setup code then acting code indicitive of another underlying problem in code.
  * <b>Inappropriately Shared Fixture:</b> Several test cases in the test fixture do not even use or need the setup / teardown. 
  * <b>Excessive Setup:</b>A test that requires a huge setup in order to even begin testing.
  * <b>Fragility:</b> Tests fail often and unexpectedly even for seemingly trivial or unrelated code changes.
  * <b>Logic in Setups:</b> Having assertions in the Setup/TearDown methods is not advisable. It makes the test less readable if the user needs to "understand" that some of the test logic is not in the test method.
  * <b>Setup/Teardown Bloat:</b> When a setup/teardown is long and perform all sort of business logic.
  * <b>The Cuckoo:</b> A unit test which sits in a test case with several others, and enjoys the same (potentially lengthy) setup process as the other tests in the test case, but then discards some or all of the artifacts from the setup and creates its own.
  * <b>The Mother Hen:</b> A common setup which does far more than the actual test cases need. For example creating all sorts of complex data structures populated with apparently important and unique values when the tests only assert for presence or absence of something.
* Issues in teardown
  * <b>Wet Floor:</b> The test creates data that is persisted somewhere, but the test does not clean up when finished. This causes tests (the same test, or possibly other tests) to fail on subsequent test runs. For example, a test left a file lying around in the "temp" dir, with permissions from the user that ran the test the first time.
* Other test steps
  * <b>The Secret Catcher:</b> A test that at first glance appears to be doing no testing, due to absence of assertions. But the test is really relying on an exception to be thrown and expecting the testing framework to capture the exception and report it to the user as a failure.
  * <b>Boilerplate:</b>Test code snippets that should be included in many places with little change.
  * <b>Brittle Unit Tests:</b> Software brittleness is the increased difficulty in fixing older software that may appear reliable, but fails badly when presented with unusual data or altered in a seemingly minor way.
  * <b>Fragile Unit Tests:</b> Tests that break easily, i.e. test cases that appear to be reliable, but when dealing with code changes or unusual data, often fail badly.

🧩 <b>Test execution / behavior</b>

* Other test execution / behavior
  * <b>Verify behaviour:</b> Changes to test code that change its original behavior. Refactoring the test code must preserve its original result. Whether the changes do not preservee test results, this is problem of a test code design.
  * <b>Non-deterministic tests:</b> I run a bunch of tests in parallel and some tests fail. I run them sequentially and they all pass.
  * <b>Sleep Test:</b> Test case with wait caused by Thread.sleep().
  * <b>The Flickering Test:</b> A test which just occasionally fails, not at specific times, and is generally due to race conditions within the test. Typically occurs when testing something that is asynchronous, such as JMS.
* Performance
  * <b>Slow Runtime:</b> Test cases that take a long time to run. Do any of your individual unit tests take longer than a tenth of a second to run? 
  * <b>The Slow Poke:</b> A unit test that runs incredibly slow. 

🏓 <b>Test semantic / logic</b>

* Other test logic related
  * <b>The Sleeper:</b> Lack of control over the execution time of each individual test case. Knowing the slowest test cases can make the refactoring process easier.
  * <b>Lazy Test:</b> Test method, which calls similar method of same class.
  * <b>Conditional logic:</b> Test methods with conditional or loop statements
  * <b>Happy Path:</b> The test stays on happy paths (i.e. expected results) without testing for boundaries and exceptions.
  * <b>The Inspector:</b> A unit test that violates encapsulation in an effort to achieve 100% code coverage, but knows so much about what is going on in the object that any attempt to refactor will break the existing test and require any change to be reflected in the unit test.
  * <b>Wait and See:</b>A test that runs some set up code and then needs to 'wait' a specific amount of time before it can 'see' if the code under test functioned as expected. A testMethod that uses Thread.sleep() or equivalent is most certainly a "Wait and See" test.
* Testing many things
  * <b>Assertion Roulette:</b> There are two many assertions happening in one method, though indirectly and it defeats the idea of one responsibility per test.
  * <b>Multiple Responsabilities:</b> When a test case have more than a assertion. 
  * <b>Tests of Different Behaviors:</b> It changes the control flow between testing and live behavior, meaning we're not necessarily testing the same code.
  * <b>The Test It All:</b> Tests should not break the Single Responsibility Principle. Tests that break this rule are by definition a nightmare to maintain.
