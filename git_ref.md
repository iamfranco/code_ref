# Git Reference

#### Configure username & email:
```
git config --global user.name "userName"
git config --global user.email "userEmail"
```

#### Initialise git in current directory
```
git init
```

#### .gitignore
For example, if you want `git` to ignore the `content/` folder and any file named `.DS_Store` (auto-generated within macOS), then save the following within a file named `.gitignore`:
```
.gitignore
content/
**/.DS_Store
```

#### Set new remote repo URL
```
git remote add origin https://...
```

#### Update remote repo URL
```
git remote set-url origin https://...
```

#### Show remote repo URL
```
git remote -v
```

#### Show file changes
```
git status
```

#### Add *filename* to staging area
```
git add filename
```

#### Add all modified files to staging area
```
git add .
```

#### Commit staged files
```
git commit -m "commit message here"
```

#### Push commits to remote repo URL
```
git push origin master
```
