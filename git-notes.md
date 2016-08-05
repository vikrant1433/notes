Toc
# rename a remote
* `git remote rename` `<old_remote_name>` `<new_remote_name>`
#  see all the remote branches
* git branch -a
# a successful git branching model
http://nvie.com/posts/a-successful-git-branching-model/
* We consider `origin/master` to be the main branch where the source code of `HEAD` always reflects a production-ready state.
* `origin/develop` to be the main branch where the source code of `HEAD` always reflects a state with the latest delivered development changes for the next release. Some would call this the “integration branch”. This is where any automatic nightly builds are built from.
# show remote git branches
* `git branch -r`
# git ls-tree -r master --name-only
* list filename under version control for master branch
# do not show untracked files in git status
* git status --untracked-files=no
alternative
* git status -uno
# Extract file from another branch.
* git show <branch_name>:<file_name>
# Remove entry in the global config.
* git config --global --unset <entry-name>
# Instantly browse your working repository in gitweb.
* git instaweb [--local] [--httpd=<httpd>] [--port=<port>] [--browser=<browser>]
# Open all conflicted files in an editor.
* git diff --name-only | uniq | xargs $EDITOR
# Commits in Branch1 that are not in Branch2
* git log Branch1 ^Branch2
# List ignored files.
* git check-ignore *
# list all the alias and configs.
* git config --list
# Restore deleted file.
* git checkout <deleting_commit>^ -- <file_path>
# Restore file to a specific commit-hash
* git checkout <commit-ish> -- <file_path>
# rename a branch
* git branch -m <new-branch-name>
alternative
* git branch -m [<old-branch-name>] <new-branch-name>
# update all submodules
* git submodule foreach git pull
alternative
* git submodule update --init --recursive
* git submodule update --remote
# Use vimdiff as git mergetool
## git config
- add vimdiff as git mergetool to do that run the below commands
```bash
git config merge.tool vimdiff
git config merge.conflictstyle diff3
git config mergetool.prompt false
```
# Resolving merge conflict with vimdiff
- `git mergetool`
- Notes: `LOCAL` – this is file from the current branch `BASE` – common ancestor, how file looked before both changes `REMOTE` – file you are merging into your branch `MERGED` – merge result, this is what gets saved in the repo
- move your cursor to a merge conflict area and then:
> :diffget RE
# changing remote urls
- `git remote set-url origin https://github.com/USERNAME/OTHERREPOSITORY.git`
# git short status
- `git status -s` or `git stage --short` : display filenames and their tracking status
```bash
$git  status -s
M    README
MM   Rakefile
A    lib/git.rb
M    lib/simplegit.rb
??   LICENSE.txt
```
## git submodules
- `git submodule add <url> path_to_submodule` : to add git submodule 
- `git submodule update` : same as git pull but supper repository tells its submodules to update itself
to stage only modified files
========
- git add -u
# make git diff use vimdiff for viewing the git diff of two files
- git config --global diff.tool vimdiff
- git config --global difftool.prompt false
- git config --global alias.d difftool
