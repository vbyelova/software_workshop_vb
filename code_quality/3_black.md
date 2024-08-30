# Introducing Black

You can find a much more exhaustive look at Black in the [Documentation](https://black.readthedocs.io/en/stable/)

Wouldn't it be great if we could automate some of the changes that we need to make in order to simplify making our codes of better quality?

Black is a really useful software utility that enables us to make some of these changes automatically. It will mainly sort out code formatting issues that would crop up as convention issues within Pylint.


### Installing Black

Again, like with Pylint, we can very quickly and easily install black with Python pip.

```bash
pip install black
```

Also, like with Pylint, you can pip install this into any conda environment that you may be using should you have many projects with different dependencies.


### Getting started with Black

As with Pylint, you can check the package is installed correctly and find out what version you have by running:

```bash
black --version
```

You can also get some pointers on the command-line for how to use the tool by running:

```bash
black --help
```

Black is generally run in one of two ways. 

The first way is you can have it run through your code and only do checks to report what it found, like this:

```bash
black --check --target-version=py35 <file-or-directory-to-check-goes-here>
```

or the second way is you let it reformat your code so that you have automated code quality improvements. Like this:

```bash
black --target-version=py35 <file-or-directory-to-check-goes-here>
```

There is an important caution that needs to be made here. Black is not always right!!! It can sometimes make changes that although might meet the language spec of something like PEP 8, it would look really bad to a human working on the source. You tend to see these kinds of artifacts when processing certain types of formatted lists or strings where formatting effort has been designed to make them readable but not neccessarily standard, but this is still rare.

It is important to still run a linter on the changes that Black makes, so in the case of Python, you would run Pylint after running Black.

### Example of using Black

Make sure your terminal is still in the examples directory, if you are in the repository main directory then:

```bash
cd code_quality/examples
```

Once here lets run Pylint again on the second file example. This is actually the same program you had in the Pylint example, but with the original mistakes.

```bash
pylint 2_random_code.py
```

You will recognise the errors and warnings from the previous example (hopefully). Ok so this time we are not going to fix it by hand. We are going to use Black to fix as much of it as possible as a first pass.

```bash
black --check --target-version=py35 2_random_code.py
```

Hopefully you will see that Black has its usual "Oh no!" message when it has found issues with your code and said it would reformat it. Now this is not very useful if you wanted to see what it would do beforehand. If you want to see what it will change, then use the --diff flag on the command-line:

```bash
black --check --diff --target-version=py35 2_random_code.py
```

You will see a typical diff that Linux diff utils usually present with lines beginning with a "-" denoting lines that have been removed and lines beginning with a "+" denoting lines added, in this case it is dealing mostly with bad indentation and white space issues as per the PEP 8 standard so you will see the lines changing in those ways. 

Now if you are happy with what you see, you can run the same command again without the --check flag and it will change the file.

```bash
black --target-version=py35 2_random_code.py
```

We don't really always need to check and look at the diff, we are doing this for your benefit so you can see what the tool is doing to the code. In reality this is fully automatable like Pylint is, and we only check deeper when issues arise, since it is mostly rare.

Now lets check that file with Pylint again, since we should always check Pylint after tools have modified code:

```bash
pylint 2_random_code.py
```

What do you see now, compared to the very first time?

You are probably noticing it has fixed a whole bunch of things but a few minor things remain. Usually things that remain will be things like the docstrings etc, since Black cannot interpret what your code is supposed to do and add documentation (though this might change in the post-chatGPT era!!!).

*Activity*: Can you find a random program on the internet or even one you have written yourself and apply Black to it?

The upshot is that you would have a lot less work to do on minor issues than if you only used Pylint and manual fixing, so the technical debt of maintaining high quality code is even lower.

[Next](4_isort.md)
[Home](../)
