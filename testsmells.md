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
  * <b>Ugly mirror:</b> 
  * <b>Test logic in production code:</b> 
  * <b>Coupling with Production code:</b> 
  * <b>Hard to co-evolve:</b> 
  * <b>Obsolete tests:</b> 
  * <b>Doppelgänger:</b> 
  * <b>For Testers only:</b> 
  * <b>Friction:</b> 
  * <b>Replicating Disadvantages of the Code:</b> 
  * <b>Second Class Citizens:</b> 
  * <b>The Forty Foot Pole Test:</b> 

🔮 <b>Mock and stub related</b>

* Mock and stub related
  * <b>Using more than one mock for a test:</b> 
  * <b>Mock makes the test always passes:</b> 
  * <b>Mocking whole classes:</b> 
  * <b>General Mocking:</b> 
  * <b>Is Mockito Working Fine:</b> 
  * <b>Mock call verification:</b> 
  * <b>Mock naming:</b> 
  * <b>The Dead Tree:</b> 
  * <b>The Mockery:</b> 

🔔 <b>Issues in test steps</b>

* Issues in assertions
  * <b>Tests That Can’t Fail:</b> 
  * <b>Inappropriate Assertions:</b> 
  * <b>Line hitter:</b> 
  * <b>Redundant Assertion:</b> 
  * <b>The Turing Test:</b> 
* Issues in setup
  * <b>General Fixture:</b> 
  * <b>Inappropriately Shared Fixture:</b> 
  * <b>Excessive Setup:</b>
  * <b>Fragility:</b> 
  * <b>Logic in Setups:</b> 
  * <b>Setup/Teardown Bloat:</b> 
  * <b>The Cuckoo:</b> 
  * <b>The Mother Hen:</b> 
* Issues in teardown
  * <b>Wet Floor:</b> 
* Other test steps
  * <b>The Secret Catcher:</b> 
  * <b>Boiler Plate:</b> 
  * <b>Brittle Unit Tests:</b> 
  * <b>Fragile Unit Tests:</b> 

🧩 <b>Test execution / behavior</b>

* Other test execution / behavior
  * <b>Verify behaviour:</b> 
  * <b>Non-deterministic tests:</b> 
  * <b>Sleep Test:</b> 
  * <b>The Flickering Test:</b> 
* Performance
  * <b>Slow Runtime:</b> 
  * <b>The Slow Poke:</b> 

🏓 <b>Test semantic / logic</b>

* Other test logic related
  * <b>The Sleeper:</b> 
  * <b>Lazy Test:</b> 
  * <b>Conditional logic:</b> 
  * <b>Happy Path:</b> 
  * <b>The Inspector:</b> 
  * <b>Wait and See:</b> 
* Testing many things
  * <b>Assertion Roulette:</b> 
  * <b>Multiple Responsabilities:</b> 
  * <b>Tests of Different Behaviors:</b> 
  * <b>The Test It All:</b> 
