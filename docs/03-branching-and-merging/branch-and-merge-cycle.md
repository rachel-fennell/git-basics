# Branches and Merging  

## Goal
Practice the full branch-and-merge cycle, including a conflict and a fast-forward, in your course repository.

## Steps taken
1. On main, created and committed practice/03/notes.txt
2. Created feature/notes-edit, changed that line, and committed the feature edit
3. Switched back to main, changed the same line and committed. Merging feature/notes-edit caused a conflict. I resolved it in notes.txt and committed the merge.
4. Created feature/extra, added practice/03/extra.txt and committed it. Merging feature/extra into main by fast-forward.
5. Captured the commit graph then deleted eature/notes-edit and feature/extra

## Commands
mkdir -p practice/03
git add practice/03/notes.txt
git commit -m "Add original notes for merge practice"
git log -1 --oneline --decorate
git switch -c feature/notes-edit
echo "Line 1: edited on feature" > practice/03/notes.txt
git add practice/03/notes.txt
git commit -m "Edit notes on feature branch"
git log -1 --oneline --decorate
git switch main
echo "Line 1: edited on main" > practice/03/notes.txt
git add practice/03/notes.txt
git commit -m "Edit notes on main branch"
git log -1 --oneline --decorate
git merge feature/notes-edit
open -e practice/03/notes.txt
git add practice/03/notes.txt
git log -1 --oneline --decorate
git switch -c feature/extra
echo "Extra note for the fast-forward." > practice/03/extra.txt
git add practice/03/extra.txt
git commit -m "Add extra practice file"
git switch main
git merge feature/extra
git log --oneline --graph --all --decorate
git branch -d feature/notes-edit
git branch -d feature/extra

## Results

rachel@BEL-MC-260924B git-basics % git log --oneline --graph --all --decorate
* 7a46095 (HEAD -> main, feature/extra) Add extra practice file
*   79203a0 merge feature notes edited
|\
| * 9ec880d (feature/notes-edit) Edit notes on feature branch
* | de2c649 Edit notes on main branch
|/
* 629e332 Add original notes for merge practice
* 2d55a34 (origin/main, origin/HEAD) adding in staging
* 73e5b21 adding tasks.md
* 6cb5c84 deleted extra lines in tasks.md
* ac42630 added in fourth task to list
* a024933 updated project schedule task
* 278e7d5 adding in 02 folder
* 6071399 edited gitignore file
* b693b1e added intital tasks list
* a268335 editing gitignore file to test out git commands
* 3b9afbf Completed task 1 (read a repo)
* a2a94ed Fixed folder structure
* b4789c1 creating folder and file for first task
* 6779247 added in learning objectives
* eeaff9e added in evidence template
* 177c11d Add notes file
* af5a584 Initial commit
rachel@BEL-MC-260924B git-basics % git branch -d feature/notes-edit
Deleted branch feature/notes-edit (was 9ec880d).
rachel@BEL-MC-260924B git-basics % git log -1 --oneline --decorate
7a46095 (HEAD -> main, feature/extra) Add extra practice file
rachel@BEL-MC-260924B git-basics % git branch -d feature/extra
Deleted branch feature/extra (was 7a46095).



## Observations

