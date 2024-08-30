# Introduction to isort

You can find a much more exhaustive look at isort in the [Documentation](https://pycqa.github.io/isort/)

Another area of code that is often overlooked but is extremely important in automating the process of making your code better and more readable.

isort is a tool for dealing with the python module imports part of a script, it will sort the imports alphabetically and also separate different types of imports into groups of like types such that it makes it very simple to keep track of them.

### Installing isort

Like with the other tools we can simply install isort using the python pip installer like this:

```bash
pip install isort
```

You can also install it with pip into a conda environment as we have discussed with the other tools.


### Getting started with isort

As with Pylint and black, you can check the package is installed correctly and find out what version you have by running:

```bash
isort --version
```

You can also get some pointers on the command-line for how to use the tool by running:

```bash
isort --help
```

It is possible to run isort in a number of ways and the usual basic syntax goes something like this:


```bash
isort <file/s or directory here>
```

Or for all files in the current directory you could just do:

```bash
isort .
```

Like with black it is possible to run isort to show a diff of what it will change before letting it do it, and you do this again with the --diff flag.

```bash
isort --diff <file/s or directory here>
```

When running isort automatically without checking the outputs (which is what you want), you can instruct it to only make changes if there are no syntax errors introduced, and we do this by setting the --atomic flag.

```bash
isort --atomic <file/s or directory here>
```

### Example with isort

isort is a pretty simple utility that only acts on the imports in a Python application. This is an example from the isort documentation, but it illustrates how isort works perfectly!

Again, lets make sure you are in the correct directory path, if you are in the repository root then:

```bash
cd code_quality/examples
```

Firstly lets have a look at the contents of the file we are about to sort out:

```bash
cat 3_random_import.py
```

You will see that there is not much going on in this program, and if you tried to run it then it probably wouldn't actually run anything, it is just for the purpose of this sort of example. As you will see this file is all over the place, imports that import functions from the same package are on different lines and there is no sorting or aggregation of similar imports. This is bad practice because if you were maintaining this package it would take you a lot longer to identify imports to change if your code changes if they are not organised properly. This gets a lot, lot worse for bigger projects.

So lets see what isort will actually change:

```bash
isort --diff 3_random_import.py
```

As you can see, again like with Black, the diff will show which lines are removed (minus) and which ones are added (plus). You can see when comparing the minus lines with the plus lines that they are both better organised and shorter in general than the original file.

To have isort run and change the file:

```bash
isort 3_random_import.py
```

Then if you have a look in the file again with cat:

```bash
cat 3_random_import.py
```

You will see it is much, much more organised and easier to read.

*Activity*: Can you find a random program on the internet or even one you have written yourself and apply isort to it?

[Next](5_precommit.md)
[Home](../)
