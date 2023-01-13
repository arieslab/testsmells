🔙 <a href="https://github.com/railana/testsmells">Back to previous page</a> 

<p align="center">
 <h2>Definition of test code refactorings 🧹🧹🧹</h2>
</p>

<img width="48%" src="refactorings.svg" align="center" alt=""/>

🟣 <b>Good practices for preventing problems with roots on </b>

* Test steps
  * <b>Use setup/teardown:</b> 🔴
  * <b>Do not mix different types of test codes:</b> NEVER mix the test code with the UI Automation code.
  * <b>Do not put assertions in the setup method:</b> To use it, when I have some test errors in that class, I know that if testSetup() has an error, I don't need to bother with the other errors, I need to fix this one first.
  * <b>Organize the code following good practices:</b> There are several ways of organizing tests into classes. The most common patterns are Testcase Class per Class, Testcase Class per Feature and Testcase Class per Fixture.
  * <b>Separate setup and assert methods:</b> ⚫
* Code-related
  * <b>Follow naming conventions:</b> 🔴
  * <b>Give meaningfull names:</b> 🔴
  * <b>Asserting strings instead of discrete values:</b>
  * <b>Fast, Focused Feedback:</b> Your tests should isolate the failure quickly and give you useful information as to its cause.
  * <b>Propositional Style Naming:</b> Propositional Style Naming, using a Most Recently Used List.
  * <b>Write meaningfull assert messages:</b> This "state your intention rather than your method name" principle becomes ever more important as test cases become more complex, potentially involving more than one method.
* Dependencies
  * <b>Use mocks:</b> 
  * <b>Keep all code related entries together:</b> 
  * <b>Tests should run independently of each other:</b> 
  * <b>Use fakes instead of mock:</b> 
* Mock and stub related
  * <b>Do not mock entire classes:</b> 
  * <b>Do not use unrealistic test data:</b> 
* In association with production code
  * <b>Assert the behavior of your class's features:</b> 
  * <b>Do not test private methods:</b> 
  * <b>Avoid coupling your code to unit tests:</b> 
  * <b>Minimize Test-Code Distance:</b> 
* Test execution / behavior
  * <b>Avoid use sleep statements:</b> 
  * <b>Idempotent between test sessions:</b> 
  * <b>Results do not vary based on the environment:</b> 
  * <b>Static state sharing between threads:</b> 
* Test semantic / logic
  * <b>One scenario per test:</b> 
  * <b>Asserting elements in a UI:</b> 
  * <b>Do as little as possible:</b> 
  * <b>Do not create tests only for the happy path:</b> 

🟡 <b>Patterns</b>

* Test steps
  * <b>Arrange, Act and Assert (AAA):</b> 
  * <b>Don't Repeat Yourself (DRY):</b> 
  * <b>Four-Phase Test:</b> 
  * <b>Given-When-Then:</b> 

🔵 <b>Refactorings for problems associated with </b>

* Test steps
  * <b>Extract setup/teardown:</b> 
* Code-related
  * <b>Reestructure test folder:</b> 
  * <b>Remove unnused method:</b> 
  * <b>Rename test methods and classes:</b> 
  * <b>Test the 'helper object' in isolation:</b> 
  * <b>Create helper methods:</b> 
  * <b>Replace print by assert:</b> 
* Dependencies
  * <b>Use dependency injection:</b> 
  * <b>Create mocks:</b> 
  * <b>Mock database:</b> 
* Mock and stub related
  * <b>Create a shared sttubing:</b> 
  * <b>Match widely and verify precisely:</b> 
* In association with production code
  * <b>Create an interface:</b> 
  * <b>Fixing production class:</b> 
  * <b>Use abstract factory:</b> 
  * <b>Use reflection:</b> 
* Test execution / behavior
  * <b>Use test annotation:</b> 
  * <b>Mock the elapsed time:</b> 
  * <b>Use explicit wait:</b> 
* Test semantic / logic
  * <b>Decompose test logic:</b> What I might consider is decomposing the logic that generates the markup into smaller units, which you can test in more granular fashion.
  * <b>Use guard asserts to multiple assertions:</b> I am not a fan of multiple asserts in a single test, but there are cases when a single "fact" can only be checked by multiple asserts and I can also think of a number of scenarios in which having some "guard" asserts before the actual "fact" being asserted can help in debugging failures.
