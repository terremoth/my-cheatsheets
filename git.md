# git
git clone https://yourrepository.com/repo.git repo_name = downloads the remote project locally

git config user.name \<your github username\> = add your username in the project

git config user.email \<your github email\> = add your email in the project

git init = create git code repository

git status = show repository status

git remote = list remote repositories

git add <file, ...files> = add modiefied files to the staging area

git commit -m "modification description in present tense" = register that file(s) modification in the repository

git log = show commits registers list

git log --oneline = show commits registers but in one line 

git merge \<branch\> = merge the commits from that branch to your working branch now

git pull origin \<branch\> = gets the remote modifications and automatically try to merge

git push origin \<branch\> = send the modifications to the remote branch/repository

git fetch = downloads the origin branchs and let them "stand-by", not merging them

git branch = show what branch you are editing files

git checkout \<branch\> = change your atual branch to the desired branch

git checkout -- <file, ...files> = ignore file(s) modifications and rollback them as it was before

git checkout -b \<branch name\> = creates a new branch from the current branch you were working and goes into it

git checkout -b local_branch_name origin/remote_branch_name = enters a branch that is only available remotely and bring it locally

git reset HEAD = unadd the files that you "add" before

git reset \<sha1_code\> = rollback your project to that commit sha1 register in specific

git diff \<file\> = show modifications you made in your files comparing to the latest commit

git blame \<file\> = show who edited each line of the file, the commit hash and when (time)
