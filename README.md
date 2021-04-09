## This is sharhan-alhassan git project!

### Practic resource
[freecodecamp](https://www-freecodecamp-org.cdn.ampproject.org/v/s/www.freecodecamp.org/news/practical-git-and-git-workflows/amp/?amp_js_v=a6&amp_gsa=1&usqp=mq331AQFKAGwASA%3D#aoh=16177855701263&csi=0&referrer=https%3A%2F%2Fwww.google.com&amp_tf=From%20%251%24s&ampshare=https%3A%2F%2Fwww.freecodecamp.org%2Fnews%2Fpractical-git-and-git-workflows%2F)


### Populating a file with text
1. Using `>>` will append the message to the file. Eg
    touch message.txt
    echo "Hello, worl" >> message.txt 
2. Using `>` will overide or replace the contents with the new message in the file. Eg
    echo "Clear and replace this message" > message.txgt
    

### git status
- this command tells us or gives us the status of the project like where we are in (main or branch)
- origin/main: actually *origin* is a new concept known as *remote*, which is the 'remote source' (github or bitbucket) different from what is on your local machine
- github is our origin

### git remote -v (-v for vebose)
This command lists all of our remotes. The remote is named 'origin'. this remote was automatically setup for us when we first run 'git clone'

### git add
This command tells git to track files by adding them.

### git commit
This command is used in saving a unit chunk of work all at once. It's best best practice to add a message to show what kind of commits/save you're making.

### git commint -m
This adds the 'message' flag to show why or what's the commit about

### git log
Gives detail of each commit made with the date, commit message, and commit SHA -- a unique ID generated by a hashing algorithm for this commit. 
- Other information close to the commit SHA are;
    1. (HEAD -> main) -- this info is next to the latest commit
    2. (origin/main, origin/HEAD) -- this info is next to the commit before the latest commit

### git push
- This command is used to update the 'source of truth' - the origin remote -aka Github
- The command is used and we specify "where we want to push and what branch we want to push to".
- git push origin main
    clarification
    - git push origin(to remote Github) main(to the main branch)
    the output of the push gives:
    - `2566....aete(SHA) main - >main`
    - meaning, we have pushed our main branch to Github's main branch

### git diff
- A diff(short for difference) is the difference between two sets of changes. 
    1. Lines starting with `(-)` are lines we deleted entirely or in part
    2. Lines starting with `(+)` are lines we added
- This process can look tiring, thus the existence of GUI program to implement this
- The program is called `GitX`. 
- Other alternatives are GitHub Desktop client. In fact, the github page or repository offers this wonderful tool

## How to collaborate with others in Git
- The power of git lies in working or collaborating with others on a project.
- For best best practice, it is advisable not to work directly on the `main` branch. The `main` branch suppose to be the `source of truth` for the project and changes to it should be carefully reviewed. 
- So it is appropriate to *branch* off our *main* into our own *feature branch* and then *merge* those changes back again into *main*

### git chechout -b
This command moves you out to a feature branch, for instance `git checkout -b chapter-2`. This basically mean, to `change my local project to look exactly like the project looked at some specific point in time`. It is basically identical to `main`

## Git workflows for collaboration
There are different workflows one can adopt depending your team's needs. Some are:

1. First method: Say you've a branch called `chapter-2`, merge changes in `chapter-2` into the local `main` branch. This method is straightforward. 

2. Second method: Push local `main` branch to `origin/main`. This method is a bit complicated but this is the workflow:
    - Push our local `chapter-2` branch to origin--github(this creates a new branch on `origin` called `origin/chapter-2`)
    - Merge `origin/chapter-2` into `origin/main` on Github
    - Pull down the new changes from `origin/main` to our local `main`

For solo developers, the `first method` will be okay but for team/group developemnt `second method` will be appropriate. 

### git merge
This command takes the content of one branch and merge it to the main branch.
The first thing to do is first of all be in the primary branch. Since we want `main` to absorb the changes from the `chapter-2`, we first need to be on the `main` branch. 

### git chechout
This commad is used to exit the branch and enter into the main. You need to specify the branch name, `main`. No need for the `-b` flag because we want to switch to an existing branch and not create a new one:
    - git checkout main


