## Git Flow

### Flow
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
