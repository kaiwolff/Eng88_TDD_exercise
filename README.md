# TDD Exercise

Trying out a TDD approach to writing a calculator

First, we ensure that pytest is installed as we need this to run our tests.

Since we are trialling Test-Driven Development, we write the tests before the code, defining what functions we want to have in our calculator and what we want them to return for our test cases.

To do this, we create a class that inherits from the TestCase class in the unittest library. This class lets us run methods to test the functionality of our code. We also need to have imported the classes we want to test.

After that we simply define what we require the test case to return when we run a function with a set of inputs. Instantiating an object of the testable code in our test case and then defining the functions lets us run the test case to make sure the code does what we want it to. The full code is below:

```python
#this file requires pytest to be installed.
import pytest
import unittest

from FunctionalCalc import FunctionalCalc

class FunctionalCalcTest(unittest.TestCase):

    calc = FunctionalCalc()

    def test_add(self): # naming convention is essential as 'test' is the word that we need to use when naming tests so python interpreter recognises it as a testcase.
        self.assertEqual(self.calc.add(2, 4), 6)

    def test_subtract(self):
        self.assertEqual(self.calc.subtract(4, 2), 2)

    def test_multiply(self):
        self.assertEqual(self.calc.multiply(2, 4), 8)

    def test_divide(self):
        self.assertEqual(self.calc.divide(2, 4), 0.5)

    def test_inch_to_cm(self):
        self.assertEqual(self.calc.inch_to_cm(2), 5.08)

    def test_triangle_area(self):
        self.assertEqual(self.calc.triangle_area(2,2),2.0)

    def test_divisible(self):
        self.assertEqual(self.calc.divisible(2,0), False)
        self.assertEqual(self.calc.divisible(2,3), False)
        self.assertEqual(self.calc.divisible(2,2), True)

```

Notice that all testing functions start with `test`, which is important as it is needed for the interpreter to recognise them as tests. Also notice that the test of divisible has three test cases, one for each branch of the intended control flow.

Now that we have defined what tests we want our code to pass, we write code to pass these tests. As this exercise is about the TDD approach, I took my calculator code from a previous iteration.