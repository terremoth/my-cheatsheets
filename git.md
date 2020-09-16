# git
git clone https://yourrepository.com/repo.git repo_name = downloads the remote project locally

git init = create git code repository

git status = show repository status

git remote = list remote repositories

git add <file, ...files> = add modiefied files to the staging area

git commit -m "modification description in present tense" = register that file(s) modification in the repository

git log = show commits registers list

git merge <branch> = merge the commits from that branch to your working branch now

git pull origin <branch> = gets the remote modifications and automatically try to merge

git push origin <branch> = send the modifications to the remote branch/repository

git fetch = downloads the origin branchs and let them "stand-by", not merging them

git branch = show what branch you are editing files

git checkout <branch> = change your atual branch to the desired branch

git checkout -- <file, ...files> = ignore file(s) modifications and rollback them as it was before

git reset HEAD = unadd the files that you "add" before

git reset <sha1_code> = rollback your project to that commit sha1 register in specific

git diff <file> = show modifications you made in your files comparing to the latest commit
