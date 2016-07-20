# changing remote urls
- `git remote set-url origin https://github.com/USERNAME/OTHERREPOSITORY.git`
# git status
- `git status -s` or `git stage --short` : display filenames and their tracking status
`$` `git  status -s
M    README
MM   Rakefile
A    lib/git.rb
M    lib/simplegit.rb
??   LICENSE.txt
`
## git submodules
- `git submodule add <url> path_to_submodule` : to add git submodule 
- `git submodule update` : same as git pull but supper repository tells its submodules to update itself
to stage only modified files
========
- git add -u
# to make git diff use vimdiff for viewing the git diff of two files
- git config --global diff.tool vimdiff
- git config --global difftool.prompt false
- git config --global alias.d difftool
