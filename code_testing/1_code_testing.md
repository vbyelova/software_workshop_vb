## Code Testing

One of the most important factors for a scientific code is being correct.
We want to be able to check that the code is giving the answer we expect and that any changes to the code are not inadvertantly changing the output.
This is why tests are a part of high quality code.

# Types of Tests

Unit tests are small tests that each test a particullar part (or unit) of the code.
Unit tests are used to test each function one at a time, and in some cases might even test just part of a function or class.

Integration tests check that pieces of code are working together as expected.
This is used for multiple functions at the same time.

Regression tests look at the final answer for an example input and are used to check that changes to one part of the code are not changing the overall performance.

# Code Coverage

Code coverage is a metric related to how much of your code is being tested.
Low code coverage suggests that there are parts of the code that may or may not contain bugs.
In this case, writting more tests is recommended.

High code coverage is good, but does not guarentee that all bugs have been found.
Some functions might need more than one test to cover all the possible input cases.
