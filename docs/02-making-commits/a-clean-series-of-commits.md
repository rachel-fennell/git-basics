# Series of Commits

## Goal
The history shows a .gitignore commit, two separate commits for the two edits to tasks.md with imperative subject lines, a commit removing the accidentally tracked file, and no .env file anywhere in the repository.

## Steps taken
1. Added .env, *.log, and build/ to .gitignore and committed it. Created a dummy .env and confirmed Git ignored it
2. Created tasks.md with three tasks and committed the starting version. Then I added in an extra line (4th task) and deleted a word and committed them separately using git add -p
3. Created build/output.txt, force-added and committed it, then used git rm --cached and committed the change to stop tracking it.
4. Made a commit, added the forgotten file with git commit --amend and checked the resulting history

## Commands
git add tasks.md
git commit -m "adding tasks.md"
git push
git add tasks.md
git commit -m "adding in stagng"
git add tasks.md
git commit --amend -m "adding in staging"
git log --oneline
git push
Git push --force

## Results

Unfortunately, I closed the terminal before completing this document and I do not have the exact outputs however I did do parts of this live with Amelia to confirm correct outputs.

Successful git add command - printed nothing

When using git status, .env was ignored and not listed. It was shown with !! beside it when using the command git status --short --ignored

For git amend: 

I started with this:

- Plan project schedules
- Cook dinner
- Complete git beginners module

And added in: - Adding in fourth task to list
And then deleted: - Cook dinner

## Observations
Found git add -p very hard to work and needed extra assistance on this part. The rest of the tasks were fine to complete.
