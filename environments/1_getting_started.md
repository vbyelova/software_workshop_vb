## Enviornments

This session aims to cover some of the basics and get you started with installing software.

# Operating Systems

The operating system manages the hardware and software for your machine.
It allows us to manage files and install and run software.
There are several flavours of operating systems; the three most common are Windows, Mac, and Linux.
Linux is often used in scientific programming and on high performance computing (HPC) resources.

# Resources for Getting Started with Linux

If you are new to Linux here are some links to introductory material.
- [YouTube video by ProgrammingKnowledge](https://www.youtube.com/watch?v=PTaL1s3YJPY&ab_channel=ProgrammingKnowledge)
- [Command Line](https://ubuntu.com/tutorials/command-line-for-beginners#1-overview)
- [Virtual Machines](https://ubuntu.com/tutorials/how-to-run-ubuntu-desktop-on-a-virtual-machine-using-virtualbox#1-overview)

And some links for Virtual Box (to create/run virtual machines) and Windows Subsystem for Linux.
- [Virtual Box](https://www.virtualbox.org/manual/UserManual.html#intro-installing)
- [Windows Subsystem for Linux](https://learn.microsoft.com/en-us/windows/wsl/setup/enviornment)

# Troubleshooting

There will be times when installing or using software does not work smoothly.
When this happens, start by reading the error messages carefully.
Be patient but in all the output you get there can be useful clues as to what you need to fix.

Checking version numbers is a quick way to locate some errors in the installation.
Usually, if you are on the command line and type the name of the program (as you would if you were running it) followed by --version, it will print out the version number or tell you if the program is not installed.
Then you can check the requirements for the program you want to install and make sure everything matches up.

If the error message is telling you that it can't find things you know are installed, check the PATH variable (on Linux).
You might have to add/change the PATH variable so that your operating system looks in the right place for the programs and libraries it needs.
