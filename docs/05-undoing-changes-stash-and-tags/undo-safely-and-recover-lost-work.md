# recovering lost work and safely undoing

## Goal
squash three local commits with reset --soft, undo a pushed commit with revert, lose a local commit with reset --hard and recover it from the reflog, and set work aside with stash while making an urgent commit

## Steps taken
1. Created three practice notes then combined their commits into one and pushed
2. Added and pushed mistake.txt then reverted that commit and pushed the revert
3. Committed recovered.txt locally, reset it off main, found it in the reflog and created/pushed the rescue branch
4. On feature/half-done, I made an unfinished edit to squash-notes.txt and stashed it. Switched to main, committed and pushed an urgent fix then returned to the feature branch and restored the stashed edit

## Commands
mkdir -p practice/05
echo "First practice note." > practice/05/squash-notes.txt
git add practice/05/squash-notes.txt
git commit -m "add first squash practice note"
echo "Second practice note." >> practice/05/squash-notes.txt
git add practice/05/squash-notes.txt
git commit -m "add second squash practice note"
echo "Third practice note." >> practice/05/squash-notes.txt
git add practice/05/squash-notes.txt
git commit -m "add third squash practice note"
git reset --soft HEAD~3
git commit -m "adding 1st,2nd,3rd squash practice notes"
git push
echo "This is a practice line and will be reverted" > practice/05/mistake.txt
git add practice/05/mistake.txt
git commit -m "adding mistaken practice file"
git push
git revert 4968d1c
git push
echo "this local note will be recovered" > practice/05/recovered.txt
git add practice/05/recovered.txt
git commit -m "adding a local commit recovery note"
git reset --hard HEAD~1
git reflog -5
git switch -c rescue 'HEAD@{1}'
git push -u origin rescue
git switch main
git switch -c feature/half-done
echo "unfinished edit on notes" >> practice/05/squash-notes.txt
git stash push -m "unfinished edit"
git status
git switch main
echo "urgent fix" > practice/05/urgent-fix.txt
git add practice/05/urgent-fix.txt
git commit -m "added urgent fix"
git push
git switch feature/half-done
git stash pop

## Results
541b375 (HEAD -> main) add third squash practice note
edea86a add second squash practice note
94d246e add first squash practice note

[main 4968d1c] adding mistaken practice file

[main 1f95453] Revert "adding mistaken practice file"
 1 file changed, 1 deletion(-)
 delete mode 100644 practice/05/mistake.txt

[main a27ceb8] adding a local commit recovery note
 1 file changed, 1 insertion(+)
 create mode 100644 practice/05/recovered.txt

HEAD is now at 1f95453 Revert "adding mistaken practice file"
1f95453 (HEAD -> main, origin/main, origin/HEAD) HEAD@{0}: reset: moving to HEAD~1
a27ceb8 HEAD@{1}: commit: adding a local commit recovery note
1f95453 (HEAD -> main, origin/main, origin/HEAD) HEAD@{2}: revert: Revert "adding mistaken practice file"
4968d1c HEAD@{3}: commit: adding mistaken practice file
8817786 HEAD@{4}: commit: adding 1st,2nd,3rd squash practice notes
Switched to a new branch 'rescue'

branch 'rescue' set up to track 'origin/rescue'

Switched to a new branch 'feature/half-done'
Saved working directory and index state On feature/half-done: unfinished edit
On branch feature/half-done

Switched to branch 'main'
Your branch is up to date with 'origin/main'.
[main 6c64ae4] added urgent fix
Switched to branch 'feature/half-done'
On branch feature/half-done
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   practice/05/squash-notes.txt

no changes added to commit (use "git add" and/or "git commit -a")
Dropped refs/stash@{0} (820b72e4738b3dddfbed13c67b35afb0a64696a7)

branch 'feature/half-done' set up to track 'origin/feature/half-done'.

## Observations
This was a hard bit of work but was quite easy to follow with the notes provided. Found it difficult at times to understand the outputs on the terminal but was able to work through it using the git web directory link to understand the commands better.
