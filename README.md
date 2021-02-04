## Git Flow

![](https://image.slidesharecdn.com/gitflow-160421170910/95/git-flow-7-638.jpg?cb=1461258649)

### The Flow
1. Branch from staging
2. Rebase staging
3. PR to staging
4. PR to production

### Step one : Branch from staging
Staging is always going to be the most advanced branch and the only branch allowed to be merged into production. Thus the first step when creating a new dev branch is to branch from staging

```bash
git checkout staging
git checkout -b task12345
```

### Step two : Rebase
Some changes might have been pushed to staging from you or another developer. To avoid having any conflicts in the PR we are going to rebase staging before doing our PR. Rebase will make it as if you just branched now from staging. Basically it is applying all the changes of staging as if they were done before your dev. Because rebase will change the history, we are need to do a push force

```bash
git checkout staging
git pull origin staging
git checkout task12345
git rebase staging
git push origin task12345 --force
```

### Step three : Make a PR to staging

The next step is going to be a code review, so we will create a PR on github to staging. Here is the 
[guide](https://docs.github.com/en/free-pro-team@latest/github/collaborating-with-issues-and-pull-requests/creating-a-pull-request)

### Step Four : Make a PR to production
Same step as before, production is protected and only a PR can be merged into it. A quick code review will be done once again

## Git cheat-sheet

I have changes preventing me from changing branch and i dont wanna lose my changes

```bash
git stash
git checkout second-task
git checkout first-task
git stash pop
```

I made a wrongful commit that i want to change and haven't pushed to remote yet

```bash
git reset --soft HEAD~1
```

I made a mess of my repository and want to go back to how it was before

```bash
git reset --hard HEAD
```

I changed the remote and want to go back one commit in time

```bash
git reset --hard HEAD~1
git push origin name-of-branch --force
```

***

Keep your branch strategy **simple**:

1. Use feature branches and merge into develop.
2. Keep a high quality, up-to-date main branch for production and only merge into main from develop. 

***

### Resources:

- [Microsoft Docs: Git branching guidance - Azure Repos](https://docs.microsoft.com/en-us/azure/devops/repos/git/git-branching-guidance?view=azure-devops) ⭐
- [GitFlow - Get Git Into Your Workflow](https://www.gitflow.com/)
- [Gitflow Workflow | Atlassian Git Tutorial](https://www.atlassian.com/git/tutorials/comparing-workflows/gitflow-workflow) ⭐
- [Gitkraken: Git Flow - What is the best Git Workflow? - Learn Git](https://www.gitkraken.com/learn/git/git-flow) ⭐
- [Introducing GitFlow](https://datasift.github.io/gitflow/IntroducingGitFlow.html)
- [git-flow cheatsheet](https://danielkummer.github.io/git-flow-cheatsheet/)
- [Read Git Flow - Leanpub](https://leanpub.com/git-flow/read#:~:text= How Git Flow Works  1 Historical,(or a predetermined release date is... More )

#### Github Repo

- [nvie/gitflow: Git extensions to provide high-level repository operations for Vincent Driessen's branching model](https://github.com/nvie/gitflow)

#### Windows Installation

- [Install gitflow on Windows (github.com)](https://gist.github.com/ilyar/11190988)

**Install gitflow on Windows**

Download and install **Git** from  [MSysGit](http://msysgit.github.io)  or [Git SCM](http://git-scm.com/).
Download and install `getopt.exe` from the [util-linux package](http://gnuwin32.sourceforge.net/packages/util-linux-ng.htm) into `C:\Program Files\Git\bin`. (Only `getopt.exe`, the others util-linux files are not used). Also install `libintl3.dll` and `libiconv2.dll` from the Dependencies packages ([libintl](http://gnuwin32.sourceforge.net/packages/libintl.htm) and [libiconv](http://gnuwin32.sourceforge.net/packages/libiconv.htm)), into the same directory.

> Suppose that **Git** is installed in the folder `c:\bin\git` and **GnuWin32** in the folder `c:\bin\GnuWin32`.

Clone the git-flow sources from GitHub:

```
$ git clone --recursive git://github.com/nvie/gitflow.git
```

Run the `msysgit-install` script from a command-line prompt (you may have to
run it with "Full Administrator" rights if you installed msysgit with its
installer, and ensure you're running from a Windows command prompt, not MINGW):

```
cd gitflow
cp c:\bin\GnuWin32\bin\getopt.exe c:\bin\git\bin\getopt.exe
cp c:\bin\GnuWin32\bin\libintl3.dll c:\bin\git\bin\libintl3.dll
cp c:\bin\GnuWin32\bin\libiconv2.dll c:\bin\git\bin\libiconv2.dll
contrib\msysgit-install.cmd c:\bin\git
```

In Git bash create a symbolic link for git-flow so that you can actually use the `$ git flow` command from any location.

```
ln -s /C/gitflow/git-flow git-flow
```
