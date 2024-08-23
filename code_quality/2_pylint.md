# Introducing Pylint

You can find a much more exhaustive look at Pylint in the [Documentation](https://pylint.readthedocs.io/en/stable/)

Now PEP 8 is a rather large document and we are not going to get very far in improving our ways of working if we require all developers to memorise a standard like that!! So this is where pylint comes in, we use pylint to test our compliance against a standard and by default this will be PEP 8. So every time you are working on python, you can use Pylint to check your code for compliance before you version control it, and this means you don't have to hold the whole of PEP 8 in your head!


### Installing Pylint

Installing pylint is fairly trivial, we can simply use Python pip.

```bash
pip install pylint
```

If you are working in a conda environment then you can use pip to install it into your conda environment. You must have activated the environment before running "pip install pylint" otherwise it will not be installed into the correct path. This is particularly useful if you have many projects, and some might have different python package version and/or dependency requirements.


### Getting started with Pylint

If the above installation went smoothly, and it really should have since it is just a pip installed package.

You should then be able to check it is installed by running:

```bash
pylint --version
```

This is a good way to also see what specific version is installed. We can get some help on the command-line with regards to basic functionality by running:

```bash
pylint --help
```

It is often more helpful to run the longer help output to get a quick idea of what you can do with pylint on the command-line without having to go into the documentation:


```bash
pylint --long-help
```

A useful part of the help output is the towards the end of the help message. It shows the following output, and this gives you an idea of what the messages that pylint will return is picking on. 

```bash
Output:
   Using the default text output, the message format is :
  MESSAGE_TYPE: LINE_NUM:[OBJECT:] MESSAGE
  There are 5 kind of message types :
  * (C) convention, for programming standard violation
  * (R) refactor, for bad code smell
  * (W) warning, for python specific problems
  * (E) error, for probable bugs in the code
  * (F) fatal, if an error occurred which prevented pylint from doing
  further processing.
```

For example if pylint had this as one of its outputs "C0114: Missing module docstring (missing-module-docstring)" the "C" is telling you it is a convention related issue so is likely to be a violation of the PEP 8 standard, if you don't yet know how to fix it you can go to the PEP 8 document linked above and actually look at the correct way. The other letters will typically indicate syntactic or errors in the code that should be fixed.

You should however consult the documentation linked above, for very specific information about Pylint, and of course for advanced information not covered in this introduction.


### Using Pylint on an example

Enough with the intro, lets get going on taking Pylint for a spin. We have provided a code example randomly discovered on the internet, since they are often badly written and this one will not disappoint!

In your terminal, change into the examples directory for the code quality part of the workshop, for example if you are already in the repository path in your terminal then:

```bash
cd code_quality/examples
```

It is worth to have a look at the example programme to see what the code looks like, but you don't need to figure out exactly what it does for this tutorial. The cat command will dump the contents of the file to your terminal:

```bash
cat 1_random_code.py
```

Now run Pylint on this file:

```bash
pylint 1_random_code.py
```

What do you see and what does it mean?

You will notice that there are listed a bunch of bad indentation warnings and a few other warnings, and you will also it grades the code out of 10, this one is pretty shocking! If you are not sure what these mean and how to fix them, then consult the [PEP 8](https://peps.python.org/pep-0008/) standard where it will tell you specifically what the code should have looked like.

Activity: Use the PEP 8 standard and Pylint together to fix this code. Can you get this to zero warnings and a code score of 10?

Activity: Can you find a random program on the internet or even one you have written yourself and apply Pylint to it?

That is all there is to using Pylint, you can imagine, this was a small code. Imagine you had just inherited thousands of lines or tens of thousands or even a million lines of code. You aren't going to fix it all by hand any time fast, and this effort is what we call technical debt. Technical debt is a concept in programming where we measure the effort required versus the benefit of doing it, for massive code bases it would be a big effort to standardise a badly written code base.

This is where the next tool comes in!

