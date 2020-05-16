## Rebase
### perform a rebase and keep Version of HEAD in case of a conflict  
![image](https://user-images.githubusercontent.com/10247813/67139644-c6ea6180-f252-11e9-9529-f69cad60b487.png)

`git rebase -X theirs foo`  

## Stash
### Add a named stash  
`git stash save stash_name`  
### List named stashes
`git stash list`  
### Unstash a named stash
`git stash pop stash@{1}`   
  
### stash a single file
`git stash push -m stash@{0} ~/foo.rb` 

### unstash a single file
`git co stash@{0} path/foo.rb` 

### git stash including untracked files  
`git stash --all`  


## Miscellaneous

### Applying .gitignore to committed files

   - Edit .gitignore as you wish
   - git rm -r --cached .
   - git add .

### Sync origin and local branch   
`git branch --set-upstream-to=origin/<branch> development`  
### show differing logs between branches  
`git log release/v6.8.0..master`  

### git log time from now  
`git tblame`  
