# Fully Automating all of this

We have seen now how to install various tools, a linter and two formatters to help us significantly up our game when it comes to code quality. The next step is how to hook this into our version control tooling so that it is all automated.


### Introducing pre-commit

You can find a much more exhaustive look at isort in the [Documentation](https://pre-commit.com/index.html)

Git has an interface that allows developers to extend the functionality of the application to include features beyond just version controlling code. This interface is called "hooks", git hooks are basically just a set of scripts that run at various "hooked" stages within the git workflow. For example, you can hook the commit step of the version control workflow to run tools whenever you are about to commit a new code change to your repository.

pre-commit is a python scripted interface to simplify this process, with pre-commit we can very easily setup git hooks that run linters or code formatters when running commit related version control steps. With this it means that we can make sure that code that is version controlled, is actually of a high quality at the point we wish to record its history.

Now isn't that convenient!!

The pre-commit project has also rather nicely compiled a list of quite a lot of other [projects](https://pre-commit.com/hooks.html) that offer hooks for different applications


### Installing pre-commit

Again as you have seen with the other tools, pre-commit is available via the Python pip installer:

```bash
pip install pre-commit
```

Check your installation worked ok:

```bash
pre-commit --version
```

To use pre-commit we are going to need to configure what it does when it is hooked by git commit commands, and to do this we will use a configuration file.


### Preparation of new repository

For this task to really work, we need a new git repository to configure. This is because if we set this up on the repository provided, then it will start to overwrite files you are going to use in the workshop!!

So lets start by initialising a new git repository. Firstly change to a directory that is safe to work in, lets say your home directory:

```bash
cd ~
```

Now lets make a memorable directory name:

```bash
mkdir precommit-tutorial
```

Lets change out terminal into this directory:

```bash
cd precommit-tutorial
```

and now lets initialise it as a git repository:

```bash
git init
```

Now this is done you will have a completely empty git repo to work inside.


### Configuring pre-commit

To setup pre-commit we need to create a yaml configuration file. In this file we will configure each of the applications that we wish to run. In this case we are setting up isort, Black and Pylint to run checks.

A typical example configuration file would look like the following:

Create a file called ".pre-commit-config.yaml" and place the following code inside:

```yaml
repos:
- repo: https://github.com/pre-commit/pre-commit-hooks
  rev: v4.4.0
  hooks:
    - id: end-of-file-fixer
    - id: mixed-line-ending
    - id: trailing-whitespace

- repo: https://github.com/PyCQA/isort
  rev: 5.12.0
  hooks:
    - id: isort

- repo: https://github.com/psf/black
  rev: 23.3.0
  hooks:
    - id: black

- repo: local
  hooks:
  - id: pylint
    language: system
    types: [file, python]
    name: pylint
    description: "This hook runs the pylint static code analyzer"
    exclude: &exclude_files >
      (?x)^(
          docs/.*|
      )$
    entry: pylint
```

As you can see in this config file, we are initialising Black, isort and Pylint.

Before we add any code or set things up further you can commit this change to your repository. It is a good idea to version control utilities like this incase something breaks later.

```bash
git add .pre-commit-config.yaml
```

and then commit the change:

```bash
git commit -m "adding pre-commit configuration to this repository"
```

### Adding/Running the hooks

Once you have configured what tools you wish to run in the yaml configuration file, you simply add them to the git hooks by running:

```bash
pre-commit install
```

This will then place the relevant scripts in the git hooks interface and will run them each time you run the corresponding git commands that you have hooked. You now have a completely clean project that is version controlled and setup with Python code quality tools from the outset! To see what this does, we need to bring in some code.

Lets grab some code from somewhere to see what this does:

```bash
wget https://gist.githubusercontent.com/jimboid/291c92703a61f5014fdcbe744690e2f2/raw/b313157178fed899125a9487b09e73350d4ccf1b/badprog.py
```

Ok so once downloaded lets firstly add it to our github repository:

```bash
git add badprog.py
```

Lets see what that looks like with git status, as you can see we have added a file to be tracked by git and there should be no untracked changes at this point.

```bash
git status
```

In a normal project you would not usually do this step, but lets have a look at the Pylint rating:

```bash
pylint badprog.py
```

As you can see it is pretty bad. Now earlier we set up our pre-commit hooks to run the code quality tools on commit, so lets commit the code and see what happens.

```bash
git commit -m "adding some bad code for the tutorial"
```

You will see some things passed but others failed, and this will have blocked the changes being committed. Now running git status again will show there are untracked changes, because we have edited the files with isort and Black.

```bash
git status
```

If you wish, you can see what the diff looks like to see what was changed:

```bash
git diff badprog.py
```

As you can see lines have been changed, hopefully this is for the better. Before trying to commit the fixes again, we can run these tools without issuing the git command to check they pass.

```bash
pre-commit run --all
```

You can now see all of the checks pass, so we have automatically corrected the code. We can go ahead and add them and commit them.

```bash
git add badprog.py

```

then:

```bash
git commit -m "adding some better code for the tutorial"
```

So hopefully, now you can understand the power that these tools can bring to empower developers to write better code without having to spend lots of time learning standards first!!

[Next](6_final_remarks.md)
[Home](../)
