### Remove Sensitive Data 
1. Download BFG from https://rtyley.github.io/bfg-repo-cleaner/
2. Remove all occurences of sensitive data and push
3. Replace sensitive data in history:
```
$ git clone --mirror git://example.com/repo.git
$ java -jar bfg.jar  --replace-text replacements.txt -fi *.filetype  repo.git
$ cd repo.git
$ git reflog expire --expire=now --all && git gc --prune=now --aggressive
$ git push
```
Issue: commits are doubled:  
Drop commmits with `git rebase -i HEAD~1` then force a push

### Set Up
Initialise a directory as a Git repository ` git init `

Setting your username in Git: https://help.github.com/articles/setting-your-username-in-git/


### Basic Commands
Clone a git repository `git clone https://github.com/DaveloperDavo/repository`

Add file contents to the staging area 
```
git add myFile
-f (force add)
```

Commit
```
git commit
-m 'commit message'
```

Push 
```
git push [alias] [branch]
--force 
```

View status
```
git status 
-s # shorter version
```

### Modifying 

Modify commit messages
```
git commit --amend # before pushing
git rebase -i HEAD~n # displays a list of the last n commits on the current branch which can be modified and can also remove commits (**WARNING!**)
```

Modify author
```
git commit --amend --author="Author Name <email@address.com>"
```

Revert a commit (and add new entry to commit history) `git revert <commit_hash>`  
Revert last `n` commits and add `n` entries to commit history `git revert HEAD~n..HEAD`  
Revert commits between A and Z (inclusively) `git revert --no-commit A..Z`  

Remove local changes (untracked files are ignored) `git reset --hard`  
Remove last `n` commits from commit history (if it has not been pushed) and:
- keep *staged* changes `git reset --soft HEAD~n`  
- keep changes `git reset HEAD~n`    
- (**WARNING! - removes all uncommitted files**) *restore* repository to latest commit `git reset --hard HEAD~n`     
  - (**WARNING!**) or as a commit hash `git reset --hard <commit_hash>`  

Remove files from repository (not locally) - useful after updating .gitignore
```
git rm --cached  myFile
git rm -r --cached myDirectory
```

(**WARNING!**) Remove entire commit history of a file and delete locally
```
git filter-branch --force --index-filter 'git rm --cached --ignore-unmatch <filename>' --prune-empty --tag-name-filter cat -- --all
git push origin --force --all
```
### Merging and Splitting
Merge two repos (where b becomes the repo)
```
cd path/to/project-b
git remote add project-a https://github.com/{user}/project-a
git fetch project-a
git merge project-a/master
git remote remove project-a
```

Splitting a subfolder out into a new repository
- create newRepo
```
git filter-branch --prune-empty --subdirectory-filter <folder>/ master
git remote remove origin 
git remote add origin https://github.com/{user}/newRepo
git push --set-upstream origin master
```

### Branching
Create new branch`$ git branch <name>`  
Checkout branch `$ git checkout <name>`  
Create and checkout new branch `$ git -b checkout <name>`  

### Stashing
Save the state of the working directory 
```
git stash
-u (unversioned)
list (view current stashes)
apply (bring back saved changes)
apply stash@{x}
drop (remove an item from the list)
clear (removes all items from the list)
```
### History
History of changes/commits: 
```
git log
--oneline
--stat
--patch
--patch --oneline
--graph --all --decorate --oneline
```
### Remotes
List, add and delete remote repository aliases 
```
git remote (lists remote aliases)
-v (see url)
git remote add [alias] https://github.com/user/repo.git
git remote remove origin
git remote rename [old-alias] [new-alias]
git remote set-url [url] (upadates the url)
```
Stop updating a file `git update-index --assume-unchanged <file> `  
Continue updating a file `git update-index --no-assume-unchanged <file>`  

### Tagging
`git tag <version> <commit id>` For example: `git tag 1.0.0 1b2e1d63ff`  

References:  
- http://gitref.org/branching/
- http://stackoverflow.com/questions/1139762/ignore-files-that-have-already-been-committed-to-a-git-repository
- http://rogerdudler.github.io/git-guide/
- https://stackoverflow.com/questions/4114095/how-to-revert-git-repository-to-a-previous-commit  

