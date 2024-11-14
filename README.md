# Here are my favourite git tricks, not base commands

#### delete local branch
```
git branch -D "${BRANCH_NAME}"
```

#### delete remote branch
```
git push -d origin "${BRANCH_NAME}"
```

#### my favourite format of git log
paste code into '~/.gitconfig', section 'alias'
```
lg        = log --color --pretty=format:'%Cred%h%Creset -%C(yellow)%d%Creset %s %Cgreen(%cD) %C(cyan)<%an>%Creset' --abbrev-commit
```

#### Show git branch in Bash prompt
paste code into '~/.bash_profile'
```
export PS1='\[\e[0;48;5;220m\] \[\e[0;38;5;232;48;5;220m\]\w\[\e[0;48;5;220m\] \[\e[0;48;5;214m\] \[\e[0;1;38;5;232;48;5;215m\]$(git branch 2>/dev/null | grep '"'"'^*'"'"' | colrm 1 2)\[\e[0;48;5;214m\] \[\e[0;48;5;39m\] \[\e[0;48;5;39m\]\t\[\e[0;48;5;39m\] \[\e[0m\] \[\e[0m\]\$ \[\e[0m\]'
```

#### Undo last unpushed commit (the changes will be saved)
```
git reset --soft HEAD^ 
```

#### Append changes to previous commit
```
git add -- my_some_files
git commit --amend --no-edit
```

#### Hide changes in working directory tempopary 
```
git stash save
```

#### Un-hide stashed changes
```
git stash pop
```
