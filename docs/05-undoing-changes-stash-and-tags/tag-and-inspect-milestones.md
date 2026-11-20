## Tagging 

## Goal
List your module tags, verify them on GitHub, inspect the repository as it was at module-03 in detached HEAD state, fix a tag created on the wrong commit before pushing it, and create an annotated v1.0.0 release tag

## Steps taken
1. Listed all module tags to verify what needed to be added
2. Added in missing module tags at correct points in the repo
3. Created a test tag and added it then deleted it
4. Created a V1.0.0 tag 

##Commands
git tag --list
git ls-remote --tags origin 'module-*'
git tag module-01 a26833523338dde74f7800d15ec00dd2450b6190
git push origin module-01
git tag module-02 6fa50b7
git tag module-03 3435ffd
git push origin module-02 module-03
git switch --detach module-03
git ls-files
git switch main
git tag test-tag HEAD
git show --no-patch test-tag
git tag -d test-tag
git tag test-tag module-03
git show --no-patch test-tag
git tag -d test-tag
git tag -a v1.0.0 -m "Git Basics course complete"
git show v1.0.0
git push origin v1.0.0

##Results
* [new tag]         module-02 -> module-02
 * [new tag]         module-03 -> module-03
* [new tag]         module-01 -> module-01

a26833523338dde74f7800d15ec00dd2450b6190        refs/tags/module-01
6fa50b79f8cd3bfa8ea47da78cd83f96d8c50b51        refs/tags/module-02
3435ffd8b77b15b53b8c70fc67fe167a2643d32b        refs/tags/module-03
b449948861dd30ed805595b6b906d3cef71d2473        refs/tags/module-04

HEAD is now at 3435ffd 03-branching-and-merging: recording merge predictions
.gitignore
README.md
docs/01-introduction-to-git/read-a-repository-s-history.md
docs/02-making-commits/a-clean-series-of-commits.md
docs/03-branching-and-merging/branch-and-merge-cycle.md
docs/03-branching-and-merging/predict-the-merge.md
docs/evidence-template.md
notes.md
practice/03/extra.txt
practice/03/notes.txt
practice/03/predict/fast-forward.txt
practice/03/predict/feature-only.txt
practice/03/predict/main-only.txt
practice/03/predict/same-line.txt
tasks.md
Previous HEAD position was 3435ffd 03-branching-and-merging: recording merge predictions
Switched to branch 'main'
Your branch is up to date with 'origin/main'.

eb82678 (HEAD -> main, tag: test-tag, origin/main, origin/HEAD) 05-undoing-changes-stash-and-tags: record undo and recovery exercise
Deleted tag 'test-tag' (was eb82678)

3435ffd (tag: test-tag, tag: module-03) 03-branching-and-merging: recording merge predictions
Deleted tag 'test-tag' (was 3435ffd)

Git Basics course complete
commit eb82678c9ccb1afbb0ef1332c8549baedbbfbe79 (HEAD -> main, tag: v1.0.0, origin/main, origin/HEAD)
* [new tag]         v1.0.0 -> v1.0.0


##Observations
Found finding the right code for the test tag part slightly hard as it wasn't really listed in exercise. Was able to find the correct code from the git directory instead. The rest was pretty straightforward and simple to do.