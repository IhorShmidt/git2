
1. stash


2. undo commit
3. reset
    - soft, hard, mixed
4. cherry-pick
5. workflow






Precondition:
 index.html
Add changes to file without add

git checkout index.html - removes changes


Wrong commit message
	precondition
		changes made to index.html
		file added to sstaging area
		changes commited with wront message
	git commit —amend -m “new fixed message”

do not do this after push



commit to wrong branch
	preconditions
		branches : master, rc
		committed changes to master, but wanted to rc
	git log -> to see commit hash
	git checkout rc -> switch branch
	git cherry-pick hash ( can be not all hash, but only first 6 chars)

———
	here we have that commit on master and rc branch, in order to remove that, we should:
	git checkout master
		git reset —soft hash -> undo commit, changes present in staging are
		git reset hash -> mixed[default] reset -> some files may apear not staged
		git reset —hard hash -> revert changes from tracked files ( added though git add, untracked files are ignored

	git clean -df -> get rid of any untracked files


git reflog - to see log history
