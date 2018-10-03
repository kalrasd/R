# Git, GitHub, and DS4PP
Throughout the course you will use GitHub to submit homework. 

GitHub provides online storage with version control using software called `git`. Everytime you commit to a change, `git` tracks those changes. This is useful when you want to go back to look at old work without storing multiple copies of a file and also allows for sophisticated collaboration on shared files.


## Overview

Here's an example of the commands you will use in the order you will use them. After, we provide an explanation of the commands and other useful information about `git`.
```
git clone https://github.com/ganong-harris/ps1-fall-2018-$USERNAME

# Do some work

git add ps1.pdf ps1.Rmd
git rm pset_template.*
git commit -m "halfway through ps1"
git push
```

## Explanation

For the purposes of this class, we will only use a few of the many available `git` commands:

### clone
`git clone` creates a copy of a local or GitHub repository (repo). By cloning a repo, we can download files from GitHub, make changes locally, and then push those changes back to GitHub to make them available to others. Cloning a GitHub repo will also set that repo as the default remote repo (the default location to push to). The syntax for cloning from GitHub is:

`git clone https://github.com/$username/$repo`

Replacing the username and repository name as appropriate. By default, `git clone` will place the cloned repo into your current command line/terminal directory. You can change this by specifying a path after the repo name in the clone command, like so:

`git clone https://github.com/$username/$repo /path/to/directory`

### add
Once a repository is cloned, you can make local changes to the files in that repo. For `git` to recognize those changes, you must tell it which files to track. Using `git add` will add files (or their changes) to `git`'s indexing system. You must use `git add` to update the index each time you make changes to a file or add a new file to your local repository. The syntax of `git add` is:

`git add filename`

You can also use glob patterns (wildcards) to specify which files you want to add. For example, if you want to add all `.Rmd` files, you could use:

`git add *.Rmd`

Where `*` is a wildcard character. You can also use `git add .` to add everything in your working directory.

### commit
Once you've added files or changes, you need to commit them. `git commit` is a way to take a snapshot of the state of your files, i.e. *commit* your changes to `git`'s memory. Each commit represents your files at a specific point in time, and you can jump back to any one of those points without losing data. You must commit before pushing to GitHub. To commit files or changes inside files, first use `git add`, then use:

`git commit -m "message"`

Where `message` is something describing the changes you've made. Most first time commits use the message `Initial commit`.

### push
After committing your changes, you can now push your commit to GitHub. If you've cloned a GitHub repo, `git` will push back to that repo by default. As such, the syntax for `git push` is simply:

`git push`

This will push any files or changes you've made to the remote repository, in this case GitHub, where you can view them online.

### pull
If you want to retrieve changes made to a remote repository, such as one on GitHub, you can use `git pull`. Pulling will download changes to your local repository. Assuming you've already set the remote repository or used `git clone`, the syntax of pulling is simply:

`git pull`

Note that if you have unadded/unindexed changes in your files, `git pull` will overwrite them.

### Using .gitignore
By default, `git add .` or `git add *` will add all files within a folder. Sometimes this is inconvenient, such as when working with large CSV files that don't need to be tracked or on GitHub. In such a case, you can use a `.gitignore` file to ensure that `git` does not add these files to the index when using `git add`. For example, if one wants to ignore all CSVs, simply make a file called `.gitignore` in your working directory, then add the line `*.csv`. This will ignore all files with the extension `.csv`.

# Homework Workflow
1. Use `git clone` through the command line to clone this repository. (We recommend that you do not clone or upload using GitHub desktop nor the website because later in the semester there will be assignments for which this will not be possible.)
2. Rename `pset_template.Rmd` as directed by the homework. Complete the assignment within this renamed file.
3. Delete the `pset_template.html` file from your repository. It only exists as an example.
4. Use `knitr` to create an html document of your assignment. It should have the same name as the `.Rmd` file, but with a `.html` extension.
5. Use `git add`, `git commit`, and `git push` to commit your finished assignment to GitHub.

Note: The html files can be viewed in a web browser (e.g. Firefox).  GitHub does not automatically render html documents, so you will not be able to preview them easily on Github. 

[A Helpful Git Guide](http://rogerdudler.github.io/git-guide/)
