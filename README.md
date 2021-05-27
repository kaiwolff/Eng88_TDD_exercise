# TDD Exercise

Trying out a TDD approach to writing a calculator

First, we ensure that pytest is installed as we need this to run our tests.

Since we are trialling Test-Driven Development, we write the tests before the code, defining what functions we want to have in our calculator and what we want them to return for our test cases.

To do this, we create a class that inherits from the TestCase class in the unittest library. This class lets us run methods to test the functionality of our code. We also need to have imported the classes we want to test.

After that we simply define what we require the test case to return when we run a function with a set of inputs. Instantiating an object of the testable code in our test case and then defining the functions lets us run the test case to make sure the code does what we want it to. The full code is below:
