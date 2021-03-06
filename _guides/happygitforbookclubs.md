Happy Git For Bookclubs
================
Tan Ho
2020-09-04

#### 2/2: Setting Up Your Local Machine

This next video summarises the happiest way to set up a copy of a GitHub
repository on your computer and to interact with it. This video assumes
that you have Git installed, if you do not, please check out
<https://happygitwithr.com/install-git.html>.

In fact, you probably want to read <https://happygitwithr.com> cover to
cover - EIKIFJB.

``` r
# Usethis is magical. Automagical, even.

usethis::create_from_github(
  repo_spec = "r4ds/bookclub-template",  # the repo you want goes here
  destdir = "GitHub/tan", # where do you want the repo folder to go?
  fork = TRUE) # you want a fork. (no spoons allowed!)

# You may also need to run this to give RStudio permissions to access your GitHub account to make the fork
usethis::browse_github_token()
```

I prefer the terminal for git. Asmae Toumi tells me that there’s a GUI
in RStudio for it. Pshaw.

Here are my incantations for git terminal:

``` eval
git checkout main # make sure you're on the main branch

git pull upstream # get latest changes from upstream repository on GH

# CRITICALLY IMPORTANT FOR PAIN FREE GIT - DO NOT MAKE ANY CHANGES TO THE MAIN BRANCH
git checkout -b newbranch 

### DO STUFF, SAVE YOUR WORK ###

git add {file} # You may be tempted to add everything with "git add ." Resist.

git commit -m "{commit message goes here}" # use -m flag for maximum expediency.

git push --set-upstream origin newbranch 
# you need the set-upstream flag because the branch doesn't yet exist there

### GO TO GITHUB AND MAKE A PULL REQUEST FROM THE NEWBRANCH TO THE MAIN/UPSTREAM REPO ###

# Someone will review your PR. 
# If any changes are necessary, add + commit + push to this same branch

### PROFIT ###
```
