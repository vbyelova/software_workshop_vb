# Code Quality 101

This course is an introduction to using pylint to increase the quality of software that you may write in the future.


### Prerequisites

* Access to a computer that has Python installed
* Familiar with any programming language - beneficial if you have basic Python
* Basic familiarity with how to start command-line based tools


### Summary

As software engineers or scientists that write software scripts, whether this is for proper distributable software pacakages and tools or simply to share simulation setup protocols with your colleagues. It is best practice from the outset to write code with quality, sharing and maintainability in mind, even if at the start you do not wish to develop for the purpose of sharing.

In this course we will focus on tools for code quality in the Python and git toolchains, but you can find similar tools for other toolchains out in the wild.


## Code Quality - Why do we care?

Imagine you are a new enthusiastic researcher, you have just landed a new research post (PhD or PDRA) and on your first day you are introduced to your project. The project up until now has been described as working on an exciting piece of science to extend previous works in a new cutting edge direction.

On your first day you are given a compressed file archive and told "this is the software we have for doing this research, it has been developed by several folks over the years". You are probably thinking "ok - awesome, can't wait to get started". You go away and start looking through the code and you start to find it is very poorly structured, difficult to read and has been coded in several different styles all smashed together - and here is the kicker, there's also no version control!

To stop this endless cycle of drama with software development, software engineers have for many years put significant effort into standardising the way that we write our software so that such issues become a thing of the past. This has required a significant community effort to standardise the ways in which we write software so that we can make this happen.

One such standard that belongs to the Python community is the PEP 8 standard (or style guide). [PEPs](https://peps.python.org/) are Python community parlance for ratified and agreed ways of doing things that all developers of tools in the language should adhere to. There are many useful PEPs but in this particular workshop, we will focus on [PEP 8](https://peps.python.org/pep-0008/). 

*Activity*: Have a look over the two links above just to appreciate what information they contain.

The reason we use standards, is that they lead to cleaner code that is more easy to share, if we all write and learn to read code in a particular format, then contributing to other projects becomes very easy. Which means our code is a lot easier to maintain as it grows, both in its size and in community.

This course is designed to give you an introduction to some of the types of tools that are available to us as developers and how to get started using them. Often the difficult bit is simply getting going rather than learning about the advanced features!

[Next](2_pylint.md)
[Home](../)
