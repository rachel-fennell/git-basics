# Doing a PR with comments

## Goal
Open an issue in your course repository, make the change on a branch, push it, open a pull request that closes the issue, review it, push a follow-up commit, merge it with squash and merge, and clean up the branch locally and on GitHub. 

## Steps taken
1. Created an issue titled 'Add a contributing guide' with a description
2. Created a new branch and a CONTRIBUTING.md file. Added commit rules to this file.
3. Opened the PR and reviewed it. Created a line comment on CONTRIBUTING.md relating to naming examples and then edited the file to address this comment. 
4. Merged the PR and closed the issue and then deleted the remote branch

## Commands
rachel@BEL-MC-260924B git-basics % gh issue create --title "Add a contributing guide" --body "add a contributing.md file that explains the repos branch and commit-message rules so contributors know how to make and submit changes"
rachel@BEL-MC-260924B git-basics % git push origin main
rachel@BEL-MC-260924B git-basics % git switch -c docs/contributing-guide
rachel@BEL-MC-260924B git-basics % git add CONTRIBUTING.md
rachel@BEL-MC-260924B git-basics % git diff --staged
rachel@BEL-MC-260924B git-basics % git commit -m "adding a contribution guide"
rachel@BEL-MC-260924B git-basics % git push -u origin docs/contributing-guide
rachel@BEL-MC-260924B git-basics % gh pr create --web
rachel@BEL-MC-260924B git-basics % open -e CONTRIBUTING.md
rachel@BEL-MC-260924B git-basics % git add CONTRIBUTING.md
rachel@BEL-MC-260924B git-basics % git commit -m "update contribution guide from review"
rachel@BEL-MC-260924B git-basics % git push
rachel@BEL-MC-260924B git-basics % git switch main
rachel@BEL-MC-260924B git-basics % git branch -d docs/contributing-guide
rachel@BEL-MC-260924B git-basics % git push origin --delete docs/contributing-guide

## Results

rachel@BEL-MC-260924B git-basics % gh issue create --title "Add a contributing guide" --body "add a contributing.md file that explains the repos branch and commit-message rules so contributors know how to make and submit changes"

Creating issue in rachel-fennell/git-basics

https://github.com/rachel-fennell/git-basics/issues/1

rachel@BEL-MC-260924B git-basics % git push origin main
Enumerating objects: 95, done.
Counting objects: 100% (95/95), done.
Delta compression using up to 11 threads
Compressing objects: 100% (63/63), done.
Writing objects: 100% (91/91), 10.70 KiB | 3.57 MiB/s, done.
Total 91 (delta 40), reused 0 (delta 0), pack-reused 0
remote: Resolving deltas: 100% (40/40), completed with 1 local object.
To github.com:rachel-fennell/git-basics.git
   2d55a34..6fa50b7  main -> main

rachel@BEL-MC-260924B git-basics % git diff --staged
diff --git a/CONTRIBUTING.md b/CONTRIBUTING.md
new file mode 100644
index 0000000..f683085
--- /dev/null
+++ b/CONTRIBUTING.md
@@ -0,0 +1,16 @@
+# Contribution rules
+
+## Branches
+Start each change from the latest main branch
+Use a separate branch for each change
+Use a short, descriptive name in lowercase
+
+## Commits
+Keep each commit focused on one logical change
+Write the subject as an instruction
+Keep the subject short and specific. Add a body when you need to know why the change was made
+
+## Pull requests
+Open a pull request against main and explain what changed and why
+Link the related issue in the description with the related issue number
+Address review feedback with a follow-up commit
\ No newline at end of file
rachel@BEL-MC-260924B git-basics % git commit -m "adding a contribution guide"
[docs/contributing-guide 75b48c3] adding a contribution guide
 1 file changed, 16 insertions(+)
 create mode 100644 CONTRIBUTING.md
rachel@BEL-MC-260924B git-basics % git push -u origin docs/contributing-guide

remote: Create a pull request for 'docs/contributing-guide' on GitHub by visiting:
remote:      https://github.com/rachel-fennell/git-basics/pull/new/docs/contributing-guide
remote:
To github.com:rachel-fennell/git-basics.git
 * [new branch]      docs/contributing-guide -> docs/contributing-guide
branch 'docs/contributing-guide' set up to track 'origin/docs/contributing-guide'.

rachel@BEL-MC-260924B git-basics % git commit -m "update contribution guide from review"
[docs/contributing-guide 1dfab63] update contribution guide from review
 1 file changed, 1 insertion(+), 1 deletion(-)

rachel@BEL-MC-260924B git-basics % git branch -d docs/contributing-guide
warning: deleting branch 'docs/contributing-guide' that has been merged to
         'refs/remotes/origin/docs/contributing-guide', but not yet merged to HEAD.
Deleted branch docs/contributing-guide (was 1dfab63).

rachel@BEL-MC-260924B git-basics % git push origin --delete docs/contributing-guide
To github.com:rachel-fennell/git-basics.git
 - [deleted]         docs/contributing-guide


## Observations
Had difficulty with squashing and merging PR and issue. Had to do it on git website instead. 
