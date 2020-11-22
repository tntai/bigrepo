# bigrepo
Convert directory to git submodules 
- Original repo at https://github.com/tntai/bigrepo/tree/v1.0

### Extract bigrepolibx folder to git repo
- Clone original repo
- Remove remote branche
`git remote remove origin`
- Extract library folder
`git filter-branch --subdirectory-filter bigrepolibx -- --all`
- Upload library to new repo
```
git remote add origin https://github.com/tntai/libx.git
git push origin master --tags
```

### Add submodule
- Clone original repo
- Delete bigrepolibx folder and commit changes
- Add new submodule
`git submodule add https://github.com/tntai/libx.git bigrepolibx`
- Commit changes

### Clone full repo
- Only clone main repo to bigrepo folder
`git clone https://github.com/tntai/bigrepo.git`
- Clone full repo to fullbigrepo folder
`git clone --recursive https://github.com/tntai/bigrepo.git fullbigrepo`
