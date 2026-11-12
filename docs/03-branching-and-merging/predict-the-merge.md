# Merging branches and predicting outcomes

## Goal
Predict merge outcomes from the commit graph before running them.

## Steps taken
1. Created document for recording predictions
2. Created a branch and merged into the unchanged main: fast-forward example and practice/03/predict/fast-forward.txt
3. Created branches to change different files and committed to main: feature-side file and practice/03/predict/feature-only.txt also main-only file and practice/03/predict/main-only.txt
4. Created branches to merge on the same line in a file: practice/03/predict/same-line.txt 
5. Resolved commit conflict and merged branches

## Commands
rachel@BEL-MC-260924B git-basics % clear
rachel@BEL-MC-260924B git-basics % mkdir -p practice/03/predict
rachel@BEL-MC-260924B git-basics % git switch -c predict/fast-forward
Switched to a new branch 'predict/fast-forward'
rachel@BEL-MC-260924B git-basics % echo "Fast-forward example" > practice/03/predict/fast-forward.txt
rachel@BEL-MC-260924B git-basics % git add practice/03/predict/fast-forward.txt
rachel@BEL-MC-260924B git-basics % git commit -m "adding fast-forward example"
rachel@BEL-MC-260924B git-basics % git log --oneline --graph --all --decorate
rachel@BEL-MC-260924B git-basics % git merge predict/fast-forward
rachel@BEL-MC-260924B git-basics % git switch -c predict/different-files
Switched to a new branch 'predict/different-files'
rachel@BEL-MC-260924B git-basics % echo "Feature-side file" > practice/03/predict/feature-only.txt
rachel@BEL-MC-260924B git-basics % git add practice/03/predict/feature-only.txt
rachel@BEL-MC-260924B git-basics % git commit -m "Add feature file"
rachel@BEL-MC-260924B git-basics % git switch main
rachel@BEL-MC-260924B git-basics % echo "main-only file" > practice/03/predict/main-only.txt
rachel@BEL-MC-260924B git-basics % git add practice/03/predict/main-only.txt
rachel@BEL-MC-260924B git-basics % git commit -m "adding main file"
rachel@BEL-MC-260924B git-basics % git log --oneline --graph --all --decorate
rachel@BEL-MC-260924B git-basics % git merge predict/different-files
rachel@BEL-MC-260924B git-basics % echo "Line 1: original" > practice/03/predict/same-line.txt
rachel@BEL-MC-260924B git-basics % git add practice/03/predict/same-line.txt
rachel@BEL-MC-260924B git-basics % git commit -m "add same line for conflict example"
rachel@BEL-MC-260924B git-basics % git switch -c predict/same-line
Switched to a new branch 'predict/same-line'
rachel@BEL-MC-260924B git-basics % echo "Line 1: feature version" > practice/03/predict/same-line.txt
rachel@BEL-MC-260924B git-basics % git add practice/03/predict/same-line.txt
rachel@BEL-MC-260924B git-basics % git commit -m "edited same line on feature"
rachel@BEL-MC-260924B git-basics % git switch main
rachel@BEL-MC-260924B git-basics % echo "Line 1: main version" > practice/03/predict/same-line.txt
rachel@BEL-MC-260924B git-basics % git add practice/03/predict/same-line.txt
rachel@BEL-MC-260924B git-basics % git commit -m "edited same line on main"
rachel@BEL-MC-260924B git-basics % git log --oneline --graph --all --decorate
rachel@BEL-MC-260924B git-basics % git merge predict/same-line
rachel@BEL-MC-260924B git-basics % open -e practice/03/predict/same-line.txt
rachel@BEL-MC-260924B git-basics % git add practice/03/predict/same-line.txt
rachel@BEL-MC-260924B git-basics % git commit -m "fixed same line merge conflict"
[main 5f50850] fixed same line merge conflict
rachel@BEL-MC-260924B git-basics % git log --oneline --graph --all --decorate


## Results
1.
scenario :unchanged main branch
evidence before merge: * d6494f1 (HEAD -> predict/fast-forward) adding fast-forward example
* b28b9ef (main) 03-branching-and-merging: record branch and merge cycle
* 7a46095 Add extra practice file
*   79203a0 merge feature notes edited
|\
| * 9ec880d Edit notes on feature branch
* | de2c649 Edit notes on main branch
|/
prediction and reason: fast-forwarded as main has not moved 
actual outcome: rachel@BEL-MC-260924B git-basics % git merge predict/fast-forward
Updating b28b9ef..d6494f1
Fast-forward
 practice/03/predict/fast-forward.txt | 1 +
 1 file changed, 1 insertion(+)
 create mode 100644 practice/03/predict/fast-forward.txt


2.
scenario : different files
evidence before merge: rachel@BEL-MC-260924B git-basics % git log --oneline --graph --all --decorate
* 6fb67c9 (HEAD -> main) adding main file
| * 4138cb4 (predict/different-files) Add feature file
|/
* d6494f1 (predict/fast-forward) adding fast-forward example
* b28b9ef 03-branching-and-merging: record branch and merge cycle
* 7a46095 Add extra practice file
*   79203a0 merge feature notes edited
prediction and reason: clean merge committed as branches change different files 
actual outcome: rachel@BEL-MC-260924B git-basics % git merge predict/different-files
Merge made by the 'ort' strategy.
 practice/03/predict/feature-only.txt | 1 +
 1 file changed, 1 insertion(+)
 create mode 100644 practice/03/predict/feature-only.txt

3.
scenario :same line merge
evidence before merge: rachel@BEL-MC-260924B git-basics % git log --oneline --graph --all --decorate
* 6ce1026 (HEAD -> main) edited same line on main
| * a46d418 (predict/same-line) edited same line on feature
|/
* 4b54b46 add same line for conflict example
*   648901d Merge branch 'predict/different-files'
|\
| * 4138cb4 (predict/different-files) Add feature file
* | 6fb67c9 adding main file
prediction and reason: merge conflict as both branches change same line in file
actual outcome: rachel@BEL-MC-260924B git-basics % git merge predict/same-line
Auto-merging practice/03/predict/same-line.txt
CONFLICT (content): Merge conflict in practice/03/predict/same-line.txt
Automatic merge failed; fix conflicts and then commit the result.
rachel@BEL-MC-260924B git-basics % open -e practice/03/predict/same-line.txt
rachel@BEL-MC-260924B git-basics % git add practice/03/predict/same-line.txt
rachel@BEL-MC-260924B git-basics % git commit -m "fixed same line merge conflict"
[main 5f50850] fixed same line merge conflict
rachel@BEL-MC-260924B git-basics % git log --oneline --graph --all --decorate
*   5f50850 (HEAD -> main) fixed same line merge conflict
|\
| * a46d418 (predict/same-line) edited same line on feature
* | 6ce1026 edited same line on main


## Observations
Everything went as expected. I did have this come up on my screen which I wasn't too sure about however when I exited it still merged as planned:

Merge branch 'predict/different-files'
Please enter a commit message to explain why this merge is necessary,
especially if it merges an updated upstream into a topic branch.

Lines starting with '#' will be ignored, and an empty message aborts
the commit.
