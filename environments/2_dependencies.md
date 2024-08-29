## Dependencies

When installing software, many of the challenges come from the dependencies.
Dependencies are when one code uses other codes or libraries (sets of functions).
The software you want won't work unless it can find all the other bits of code it depends on.
Here we will look at some of the potential issues and ways to make your software installation work.

# Versions and Package Managers

Some software has lots of dependencies and often the software needs a particular version of the other codes.
You can look in the documentation for the list of requirements and install each of them, but it is easier to use a package manager if there is one that has the software you want.

Two common package managers are the [Python Package Index](https://pypi.org) which uses the `pip` command to install packages and [Conda/Miniconda](https://docs.anaconda.com/miniconda).
Please be aware of terms of service when using Anaconda's repository (and in general pay attention to licenses).

I recommend looking at the documentation for the software you want to install and following their instructions.
Reading documentation is not the most exciting thing in the world, but it can be helpful.

# Environments

One thing that can make installing software tricky is when different pieces of software have conflicting dependencies.
This can happen when they use different versions of a common library.
Environments are the solution; they allow you to create separate compartments for different software or projects.
Different versions of the same software can be installed in different environments without clashing.

To create an environment for python programs, use the `venv` command.
The documentation for venv can be found [here](https://docs.python.org/3/library/venv.html).
There are two steps: creating the environment and activating it.

```bash
python3 -m venv /name/of/environment/
```

or use the -h option to get information on using venv

```bash
python3 -m venv -h
```

You would create the environment once and then activate it everytime you want to use that software environment.

```bash
source /name/of/environment/bin/activate
```

and when you are finished using the environment

```bash
deactivate
```

An alternative to using the python venv is to install conda/miniconda and then create conda environments.

```bash
conda create -n <environment_name>
conda activate <environment_name>
```

# Virtual Machines

A more extreme way of separating software is to use a virtual machine.
A virtual machine has its own operating system and file system, separate to the host operating system.
This can be useful, for example if you have a Windows laptop and want to run a Linux system without losing access to the Windows programs.
A virtual machine will allow you to act like you have two machines and switch between them.
One example is [Virtual Box](https://www.virtualbox.org)
