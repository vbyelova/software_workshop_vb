## Pytest

Pytest is one example of a program used for running tests.
The documentation for pytest can be found [here](https://docs.pytest.org)
Pytest looks for files named test_* .py and within those it looks for functions named test_* and then runs all the tests it can find.

# Installing and running pytest
You can install pytest using pip.
```bash
pip install pytest
```
Check that it has installed
```bash
pytest --version
```
or read the help
```bash
pytest --help
```

Run pytest using the command line in the file where your `test_*.py` file(s) are.
```bash
pytest
```


*Activity* Change to the `code_testing/example` directory of the software workshop.
Look at the `functions.py` code and the `test_functions.py`.
Try running the tests. What happens?
Can you change the code so that all the tests pass?

Does the test cover all the functionality? Try writting more tests.

[Home](../)
