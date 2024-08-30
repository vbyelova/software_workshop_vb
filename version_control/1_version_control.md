# Version Control

We want to be able to track changes without having multiple copies of files.
We also want to be able to work with other people.
Git is one of the most widely used version control tools, but others exist.

## Using Basic Git

To get a local copy of a repository:
```bash
git clone https://github.com/name/of/repository.git
```

When making changes there are three steps add files to git tracking, commit the changes, and push the changes to the repository.
You would need write permissions to push changes.
```bash
git add <filename>
git commit -m "your message here"
git push
```

[Cheat Sheet](https://training.github.com/downloads/github-git-cheat-sheet.pdf)

[Next](2_git.md)
[Home](../)
