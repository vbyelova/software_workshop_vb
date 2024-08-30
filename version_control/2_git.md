# More Git

Once you learn the basics of getting a repository and comitting changes there are some slightly more advanced features of git

## Branching Models

A common model has several branches:
- "main" branch for released/stable versions of the code
- "dev" or "develop" branch for the latest working code
- "feature" branches (each named for the relevant feature) for adding to the code and working on it until that feature is ready to join the main code
- "hot fix" branch(es) for quick bug fixes


You can organise branches the way you want.
For example you might not bother with a dev branch and just do the development on the main branch with tags for release points.

You can use
```bash
git branch <branch-name>
```
to create a branch, and
```bash
git checkout <branch-name>
```
to change to an existing branch.

## GitHub

[GitHub](https://github.com) is a website that hosts repositories.
It uses git to interact with the repositories and allows you to "fork" or copy public repositories.
Cloning a repository gives you a local copy, where you can change code and then push back to the repository; whereas forking a repository makes you the owner of a new repository that can diverge from the original one.
GitHub will also limit permissions for who can make changes to a repository, and you would need to register for an account to make or write to repositories.

GitHub uses tokens for authentication from the command line.
See [GitHub authentication](https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/managing-your-personal-access-tokens) for more information.

GitHub also has tools like a issue tracker where people can raise issues (for bugs, feature requests, or comments).
The issue tracker can help you keep track of problems that have been raised and comments used for discussions.

## Activity

Create a GitHub account if you don't already have one.

Fork the workshop repository (https://github.com/ccpbiosim/software_workshop.git).

Clone the repository to your local workstation.

Alternatively, if you don't want or can't get a GitHub account, you can clone the repository directly from the ccpbiosim version. In this case, you will be able to work with the files on your local machine but will not be able to push any changes to the remote repository.

Make a new branch and then make changes to the example code (functions.py).

Can you commit and push the changes?

[Home](../)
