![Pic](https://github.com/RedRockControls/SimpleUnitTestLibrary/blob/master/img/Banner.JPG)

# SimpleUnitTestLibrary

A lightweight unit test library for testing TwinCAT3 source code with the following goals:
1. Impose minimum setup cost for a new test
2. Provide a Gui to show test results
3. Support re-testing after an online change 
4. Support concurrent and sequential test execution


To create a test:
* Inherit from a base class
* Create an instance
* Call TestFinished()

To run all the tests together, call:

```pascal
tcl_SimpleUnitTestLibrary.TestFramework.TestRunner(RunTestsSequentially := FALSE);
```
To run all the tests one after another, call: 
```pascal
tcl_SimpleUnitTestLibrary.TestFramework.TestRunner(RunTestsSequentially := TRUE);
```

To stop tests from running automatically on download or (re)init, call: 
```pascal
tcl_SimpleUnitTestLibrary.TestFramework.TestRunner(ManualTestRunsOnly := TRUE);
```

Options can be combined in any way. I.e. call: 
```pascal
// Run tests concurrently, but only with press of Visualisation button 
tcl_SimpleUnitTestLibrary.TestFramework.TestRunner(
    RunTestsSequentially := FALSE,
    ManualTestRunsOnly := TRUE
);
```