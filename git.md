# git

Find files in current directory that are different:  

    git diff --name-only <branch> -- .

Do a vimdiff of file foobar and its BRANCH version:  

    vimdiff foobar <(git show BRANCH:path/to/foobar)   

vimdiff all files in current dir, between master and test branches:  

    git difftool -t vimdiff master test .

Diff using Meld, directory view:  

    git difftool -t meld -d test

Get specific file from branch:  

    git checkout [branch] -- [file]


