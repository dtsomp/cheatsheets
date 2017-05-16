# git

Find files in current directory that are different:  

    git diff --name-only <branch> -- .

`git diff` but with list of changed files
    
    git log --stat 

Do a vimdiff of file foobar and its BRANCH version:  

    vimdiff foobar <(git show BRANCH:path/to/foobar)   

vimdiff all files in current dir, between master and test branches:  

    git difftool -t vimdiff master test .

Diff using Meld, directory view:  

    git difftool -t meld -d test

Get specific file from branch:  

    git checkout [branch] -- [file]

Delete remote and local branch (order of exec matters):

    git push orign --delete [branch]
    git branch -d [branch]

Cherry-pick changes:

    $ git checkout feature-branch
    $ git log -1

    commit f6a617e0c4e6ad03eed64e7095d3d963ae84913c
    Author: Dimitris Tsompanidis <dimitris.tsompanidis@comeon.com>
    Date:   Wed Mar 15 14:06:14 2017 +0100

        Fuck typos


    $ git checkout master
    $ git cherry-pick 24973ae80591f58928c4f162a7a4dd7e2d1e087d
    [master f6a617e] Fuck typos
    Date: Wed Mar 15 14:06:14 2017 +0100
    1 file changed, 1 insertion(+), 1 deletion(-)


Amending a commit message:

    git commit --ammend -m 'New commit message'
    # If you've already pushed to remote, then:
    git push <remote> <branch> --force

Undo the last pushed commit (i.e. create a patch that undoes the last commit):

    git revert HEAD
