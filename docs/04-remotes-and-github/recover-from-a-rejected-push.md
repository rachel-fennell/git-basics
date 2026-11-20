# Fixing rejected pushes to GitHub

## Goal
Edit README.md on GitHub's web editor and commit it to main. Without pulling, edit a different line of README.md locally, commit and try to push. Read the rejection, use git fetch and git log --oneline --graph --all to see the divergence, integrate with git pull, and push. Then repeat with both edits on the same line and resolve the conflict

## Steps taken
1. Edited readme on GitHub and didn't pull. Edited readme locally on a different line and tried to push. It was rejected because GitHub’s main had a commit my local main didn’t have
2. Inspected the divergence and integrated the remote change
3. Changed a line in readme on GitHub and committed it. Without pulling, changed the same line in my local readme to something different. Tried to commit this and push and it was rejected again.
4. Opened readme and replaced the conflict section to combine both edits and saved, committed and pushed successfully.

## Commands
rachel@BEL-MC-260924B git-basics % open -e README.md
rachel@BEL-MC-260924B git-basics % git add README.md
rachel@BEL-MC-260924B git-basics % git commit -m "update README locally"
rachel@BEL-MC-260924B git-basics % git push
rachel@BEL-MC-260924B git-basics % git fetch origin
rachel@BEL-MC-260924B git-basics % git pull --no-rebase
rachel@BEL-MC-260924B git-basics % git push
rachel@BEL-MC-260924B git-basics % open -e README.md
rachel@BEL-MC-260924B git-basics % git add README.md
rachel@BEL-MC-260924B git-basics % git commit -m "Merge README updates"
rachel@BEL-MC-260924B git-basics % git fetch origin
rachel@BEL-MC-260924B git-basics % git pull --no-rebase origin main
rachel@BEL-MC-260924B git-basics % open -e README.md
rachel@BEL-MC-260924B git-basics % git add README.md
rachel@BEL-MC-260924B git-basics % git commit -m "merge remote README.md"
rachel@BEL-MC-260924B git-basics % git push




## Results
[main e38fa60] update README locally
 1 file changed, 3 insertions(+), 1 deletion(-)
To github.com:rachel-fennell/git-basics.git
 ! [rejected]        main -> main (fetch first)
error: failed to push some refs to 'github.com:rachel-fennell/git-basics.git'
hint: Updates were rejected because the remote contains work that you do
hint: not have locally. This is usually caused by another repository pushing
hint: to the same ref. You may want to first integrate the remote changes
hint: (e.g., 'git pull ...') before pushing again.

rachel@BEL-MC-260924B git-basics % git log --oneline --graph --all --decorate
* e38fa60 (HEAD -> main) update README locally
| * c866132 (origin/main, origin/HEAD) Update README with task details
|/
* c10c7f0 04-remotes-and-github: record first pull request
*   d3f5295 Merge pull request #2 from rachel-fennell/docs/contributing-guide
|\
| * 1dfab63 update contribution guide from review
| * 75b48c3 adding a contribution guide
|/


Auto-merging README.md
CONFLICT (content): Merge conflict in README.md
Automatic merge failed; fix conflicts and then commit the result.
rachel@BEL-MC-260924B git-basics % git log --oneline --graph --all --decorate
* e38fa60 (HEAD -> main) update README locally
| * c866132 (origin/main, origin/HEAD) Update README with task details
|/
* c10c7f0 04-remotes-and-github: record first pull request
*   d3f5295 Merge pull request #2 from rachel-fennell/docs/contributing-guide
|\
| * 1dfab63 update contribution guide from review
| * 75b48c3 adding a contribution guide


rachel@BEL-MC-260924B git-basics % git push
To github.com:rachel-fennell/git-basics.git
 ! [rejected]        main -> main (non-fast-forward)
error: failed to push some refs to 'github.com:rachel-fennell/git-basics.git'
hint: Updates were rejected because the tip of your current branch is behind
hint: its remote counterpart. Integrate the remote changes (e.g.
hint: 'git pull ...') before pushing again.



[main b397db8] Merge README updates
rachel@BEL-MC-260924B git-basics % git push
To github.com:rachel-fennell/git-basics.git
 ! [rejected]        main -> main (fetch first)
error: failed to push some refs to 'github.com:rachel-fennell/git-basics.git'
hint: Updates were rejected because the remote contains work that you do
hint: not have locally. This is usually caused by another repository pushing
hint: to the same ref. You may want to first integrate the remote changes
hint: (e.g., 'git pull ...') before pushing again.


remote: Enumerating objects: 5, done.
remote: Counting objects: 100% (5/5), done.
remote: Compressing objects: 100% (2/2), done.
remote: Total 3 (delta 1), reused 0 (delta 0), pack-reused 0 (from 0)
Unpacking objects: 100% (3/3), 969 bytes | 242.00 KiB/s, done.
From github.com:rachel-fennell/git-basics
   c866132..742b949  main       -> origin/main
*   b397db8 (HEAD -> main) Merge README updates
|\
* | e38fa60 update README locally
| | * 742b949 (origin/main, origin/HEAD) Update README for task part 2
| |/
| * c866132 Update README with task details
|/
* c10c7f0 04-remotes-and-github: record first pull request
*   d3f5295 Merge pull request #2 from rachel-fennell/docs/contributing-guide
|\
| * 1dfab63 update contribution guide from review
| * 75b48c3 adding a contribution guide
|/


rachel@BEL-MC-260924B git-basics % git log --oneline --graph --all --decorate
*   b397db8 (HEAD -> main) Merge README updates
|\
* | e38fa60 update README locally
| | * 742b949 (origin/main, origin/HEAD) Update README for task part 2
| |/
| * c866132 Update README with task details


rachel@BEL-MC-260924B git-basics % git push
Enumerating objects: 15, done.
Counting objects: 100% (15/15), done.
Delta compression using up to 11 threads
Compressing objects: 100% (9/9), done.
Writing objects: 100% (9/9), 966 bytes | 966.00 KiB/s, done.
Total 9 (delta 5), reused 0 (delta 0), pack-reused 0
remote: Resolving deltas: 100% (5/5), completed with 1 local object.
To github.com:rachel-fennell/git-basics.git
   742b949..29400ac  main -> main
rachel@BEL-MC-260924B git-basics % cat README.md
# git-basics

Second change to readme for task to try and commit and reject :(

Editing readme for task

Editing readme for task part 2
rachel@BEL-MC-260924B git-basics % git log --oneline --graph --all --decorate
*   29400ac (HEAD -> main, origin/main, origin/HEAD) merge remote README.md
|\
| * 742b949 Update README for task part 2
* | b397db8 Merge README updates
|\|
| * c866132 Update README with task details
* | e38fa60 update README locally
|/

## Observations
No difficulty with this task 
