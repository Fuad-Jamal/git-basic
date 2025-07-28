User@GisaF23 MINGW64 ~/Codes/project/git-basic (master)
$ touch test{1..4}.md

User@GisaF23 MINGW64 ~/Codes/project/git-basic (master)
$ git add test1.md && git commit -m "chore: Create initial file"
git add test2.md && git commit -m "chore: Create another file"
git add test3.md && git commit -m "chore: Create third and fourth files"
[master fe40b54] chore: Create initial file
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test1.md
[master 0e359d6] chore: Create another file
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test2.md
[master b9323ee] chore: Create third and fourth files
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test3.md

User@GisaF23 MINGW64 ~/Codes/project/git-basic (master)
$ git status
On branch master
Your branch is ahead of 'origin/master' by 3 commits.
  (use "git push" to publish your local commits)

Changes not staged for commit:
  (use "git add/rm <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        deleted:    index.html

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        test4.md

no changes added to commit (use "git add" and/or "git commit -a")

User@GisaF23 MINGW64 ~/Codes/project/git-basic (master)
$ git push
Enumerating objects: 7, done.
Counting objects: 100% (7/7), done.
Delta compression using up to 4 threads
Compressing objects: 100% (6/6), done.
Writing objects: 100% (6/6), 631 bytes | 631.00 KiB/s, done.
Total 6 (delta 2), reused 0 (delta 0), pack-reused 0 (from 0)
remote: Resolving deltas: 100% (2/2), done.
To https://github.com/Fuad-Jamal/git-basic.git
   b6f5c49..b9323ee  master -> master

User@GisaF23 MINGW64 ~/Codes/project/git-basic (master)
$ git status
On branch master
Your branch is up to date with 'origin/master'.

Changes not staged for commit:
  (use "git add/rm <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        deleted:    index.html

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        README.md
        test4.md

no changes added to commit (use "git add" and/or "git commit -a")

User@GisaF23 MINGW64 ~/Codes/project/git-basic (master)
$ git log
commit b9323ee901491f05a052f8bb05f3d5f7338cf771 (HEAD -> master, origin/master)
Author: Fuad Jamal <jamalfuad34@gmail.com>
Date:   Thu Jul 24 10:25:54 2025 +0200

    chore: Create third and fourth files

commit 0e359d64cf19e8cbbd2de0434eec7297e73181fc
Author: Fuad Jamal <jamalfuad34@gmail.com>
Date:   Thu Jul 24 10:25:54 2025 +0200

User@GisaF23 MINGW64 ~/Codes/project/git-basic (master)
$ git rebase -i HEAD~3
hint: Waiting for your editor to close the file...       0 [sig] bash 1248! sigpacket::process: Suppressing signal 18 to win32 process (pid 22820)
reword  0e359d6 chore: Create second file
chore: Create second file
1255997 [sig] bash 1248! sigpacket::process: Suppressing signal 18 to win32 process (pid 22820)        
1753639 [sig] bash 1248! sigpacket::process: Suppressing signal 18 to win32 process (pid 22820)        
2428659 [sig] bash 1248! sigpacket::process: Suppressing signal 18 to win32 process (pid 22820)        
2962667 [sig] bash 1248! sigpacket::process: Suppressing signal 18 to win32 process (pid 22820)        
3431836 [sig] bash 1248! sigpacket::process: Suppressing signal 18 to win32 process (pid 22820)        
Successfully rebased and updated refs/heads/master.

User@GisaF23 MINGW64 ~/Codes/project/git-basic (master)
$ git rebase -i HEAD~3
[detached HEAD 4986306] chore: Create second file
 Date: Thu Jul 24 10:25:54 2025 +0200
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test2.md
Successfully rebased and updated refs/heads/master.

User@GisaF23 MINGW64 ~/Codes/project/git-basic (master)
$ git status
On branch master
Your branch and 'origin/master' have diverged,
and have 3 and 2 different commits each, respectively.
  (use "git pull" if you want to integrate the remote branch with yours)

nothing to commit, working tree clean

User@GisaF23 MINGW64 ~/Codes/project/git-basic (master)
$ git log --oneline
4df1b27 (HEAD -> master) showing the steps
7f9fc9f chore: Create third and fourth files
4986306 chore: Create second file
fe40b54 chore: Create initial file
b6f5c49 starting exercise
a7feaa4 testing
ff17226 fileg


User@GisaF23 MINGW64 ~/Codes/project/git-basic (master)
$ touch unwanted.txt

User@GisaF23 MINGW64 ~/Codes/project/git-basic (master)
$ git status
On branch master
Your branch and 'origin/master' have diverged,
and have 5 and 3 different commits each, respectively.
  (use "git pull" if you want to integrate the remote branch with yours)

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   README.md

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        unwanted.txt

no changes added to commit (use "git add" and/or "git commit -a")

User@GisaF23 MINGW64 ~/Codes/project/git-basic (master)
$ git add unwanted.txt 

User@GisaF23 MINGW64 ~/Codes/project/git-basic (master)
$ git commit -m 'unwanted commit'
[master ce9b1ee] unwanted commit
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 unwanted.txt

User@GisaF23 MINGW64 ~/Codes/project/git-basic (master)
$ git log --oneline
ce9b1ee (HEAD -> master) unwanted commit
a6056d1 the following steps detail rebasing and changing the last commit
e6308ea showing the steps
283b211 Create fourth file
fa4ab04 Create third file
3b0a69a chore: Combination of another && second file
b6f5c49 starting exercise
a7feaa4 testing
ff17226 file

User@GisaF23 MINGW64 ~/Codes/project/git-basic (master)
$ git rebase -i HEAD~
error: cannot rebase: You have unstaged changes.
error: Please commit or stash them.

User@GisaF23 MINGW64 ~/Codes/project/git-basic (master)
drop ce9b1ee unwanted commit
$ git add README.md

User@GisaF23 MINGW64 ~/Codes/project/git-basic (master)
$ git commit -m 'adding previous file'
[master 64f5df6] adding previous file
 1 file changed, 1 insertion(+), 1 deletion(-)

User@GisaF23 MINGW64 ~/Codes/project/git-basic (master)
$ git rebase -i HEAD~2
Successfully rebased and updated refs/heads/master.

User@GisaF23 MINGW64 ~/Codes/project/git-basic (master)
$

User@GisaF23 MINGW64 ~/Codes/project/git-basic (main)
$ git checkout -b ft/branch
Switched to a new branch 'ft/branch'

User@GisaF23 MINGW64 ~/Codes/project/git-basic (ft/branch)
$ touch test5.md

User@GisaF23 MINGW64 ~/Codes/project/git-basic (ft/branch)
$ git add test5.md 

User@GisaF23 MINGW64 ~/Codes/project/git-basic (ft/branch)
$ git commit -m 'implemented test 5'
[ft/branch 96acba3] implemented test 5
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test5.md

User@GisaF23 MINGW64 ~/Codes/project/git-basic (ft/branch)
$ git log --oneline
96acba3 (HEAD -> ft/branch) implemented test 5
46fc073 (main) successfully deleted test 5
b17e69b dropping commit
64efbdc implemented test 5
e96dfc0 (master) dropping a commit
f3966b9 adding previous file
a6056d1 the following steps detail rebasing and changing the last commit
e6308ea showing the steps
283b211 Create fourth file

User@GisaF23 MINGW64 ~/Codes/project/git-basic (ft/branch)
$ git checkout main
Switched to branch 'main'
Your branch is ahead of 'origin/main' by 13 commits.
  (use "git push" to publish your local commits)

User@GisaF23 MINGW64 ~/Codes/project/git-basic (main)
$ git log ft/branch --oneline
96acba3 (ft/branch) implemented test 5
46fc073 (HEAD -> main) successfully deleted test 5
b17e69b dropping commit
64efbdc implemented test 5
e96dfc0 (master) dropping a commit
f3966b9 adding previous file
a6056d1 the following steps detail rebasing and changing the last commit
e6308ea showing the steps
283b211 Create fourth file

User@GisaF23 MINGW64 ~/Codes/project/git-basic (main)
$ git cherry-pick 96acba3
[main ddb37f3] implemented test 5
 Date: Mon Jul 28 11:13:57 2025 +0200
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 test5.md

User@GisaF23 MINGW64 ~/Codes/project/git-basic (main)
$ git log --oneline
ddb37f3 (HEAD -> main) implemented test 5
46fc073 successfully deleted test 5
b17e69b dropping commit
64efbdc implemented test 5
e96dfc0 (master) dropping a commit
f3966b9 adding previous file
a6056d1 the following steps detail rebasing and changing the last commit
e6308ea showing the steps
283b211 Create fourth file

User@GisaF23 MINGW64 ~/Codes/project/git-basic (main)
$ git log --graph
* commit 65b7d0d41cdf475b8ace0632f0cc6918d057c72e (HEAD -> main)
| Author: Fuad Jamal <jamalfuad34@gmail.com>
| Date:   Mon Jul 28 11:19:10 2025 +0200
|
|     cherry-picking commits
|
* commit ddb37f3e4150d1de41152616b0487aa43a419e8b
| Author: Fuad Jamal <jamalfuad34@gmail.com>
| Date:   Mon Jul 28 11:13:57 2025 +0200
|
|     implemented test 5
|
* commit 46fc073f7fa50053efe970d42918af18b1485ab6
| Author: Fuad Jamal <jamalfuad34@gmail.com>
| Date:   Mon Jul 28 11:09:57 2025 +0200
|
|     successfully deleted test 5
|
*   commit b17e69baf096eb8ea32acf856f8ec0bd7b625d4e
|\  Merge: d34fd7d 64efbdc
| | Author: Fuad Jamal <jamalfuad34@gmail.com>
| | Date:   Mon Jul 28 11:09:34 2025 +0200
| |
| |     dropping commit
| |
| * commit 64efbdcca1cb92984230d913e762f9e68db3cdfa
| | Author: Fuad Jamal <jamalfuad34@gmail.com>
| | Date:   Mon Jul 28 10:49:48 2025 +0200
| |
| |     implemented test 5
| |
| * commit e96dfc06eba37bee95bacc6beadc31cdb7bc340d (master)
| | Author: Fuad Jamal <jamalfuad34@gmail.com>
| | Date:   Mon Jul 28 10:45:13 2025 +0200
| |
| |     dropping a commit

User@GisaF23 MINGW64 ~/Codes/project/git-basic (main)
$ git reflog
69b1081 (HEAD -> main) HEAD@{0}: commit: visualizing git history on a graph
65b7d0d HEAD@{1}: commit: cherry-picking commits
ddb37f3 HEAD@{2}: cherry-pick: implemented test 5
46fc073 HEAD@{3}: checkout: moving from ft/branch to main
96acba3 (ft/branch) HEAD@{4}: commit: implemented test 5
46fc073 HEAD@{5}: checkout: moving from main to ft/branch
46fc073 HEAD@{6}: commit: successfully deleted test 5
b17e69b HEAD@{7}: commit (merge): dropping commit
d34fd7d (origin/main) HEAD@{8}: checkout: moving from ft/branch to main
:
69b1081 (HEAD -> main) HEAD@{0}: commit: visualizing git history on a graph
65b7d0d HEAD@{1}: commit: cherry-picking commits
ddb37f3 HEAD@{2}: cherry-pick: implemented test 5
46fc073 HEAD@{3}: checkout: moving from ft/branch to main
96acba3 (ft/branch) HEAD@{4}: commit: implemented test 5
46fc073 HEAD@{5}: checkout: moving from main to ft/branch
46fc073 HEAD@{6}: commit: successfully deleted test 5
b17e69b HEAD@{7}: commit (merge): dropping commit
d34fd7d (origin/main) HEAD@{8}: checkout: moving from ft/branch to main
:
69b1081 (HEAD -> main) HEAD@{0}: commit: visualizing git history on a graph
65b7d0d HEAD@{1}: commit: cherry-picking commits
ddb37f3 HEAD@{2}: cherry-pick: implemented test 5
46fc073 HEAD@{3}: checkout: moving from ft/branch to main
96acba3 (ft/branch) HEAD@{4}: commit: implemented test 5
46fc073 HEAD@{5}: checkout: moving from main to ft/branch
46fc073 HEAD@{6}: commit: successfully deleted test 5
b17e69b HEAD@{7}: commit (merge): dropping commit
d34fd7d (origin/main) HEAD@{8}: checkout: moving from ft/branch to main

User@GisaF23 MINGW64 ~/Codes/project/git-basic (main)
$ git checkout -b ft/new-feature
Switched to a new branch 'ft/new-feature'

User@GisaF23 MINGW64 ~/Codes/project/git-basic (ft/new-feature)
$ touch feature.txt

User@GisaF23 MINGW64 ~/Codes/project/git-basic (ft/new-feature)
$ git add feature.txt && git commit -m 'implemented core functionality for new feature'
[ft/new-feature f1fd1fc] implemented core functionality for new feature
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 feature.txt

User@GisaF23 MINGW64 ~/Codes/project/git-basic (ft/new-feature)
$ git checkout main
Switched to branch 'main'
Your branch is ahead of 'origin/main' by 17 commits.
  (use "git push" to publish your local commits)

User@GisaF23 MINGW64 ~/Codes/project/git-basic (main)
$ tourch readme.txt
bash: tourch: command not found

User@GisaF23 MINGW64 ~/Codes/project/git-basic (main)
$ tourh readme.txt
bash: tourh: command not found

User@GisaF23 MINGW64 ~/Codes/project/git-basic (main)
$ touch readme.txt

User@GisaF23 MINGW64 ~/Codes/project/git-basic (main)
$ git add readme.txt && git commit -m 'updated project readme'
[main d7d8702] updated project readme
 1 file changed, 1 insertion(+)
 create mode 100644 readme.txt

User@GisaF23 MINGW64 ~/Codes/project/git-basic (main)


User@GisaF23 MINGW64 ~/Codes/project/git-basic (main)
$ git merge ft/new-feature
Merge made by the 'ort' strategy.
 feature.txt | 0
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 feature.txt

User@GisaF23 MINGW64 ~/Codes/project/git-basic (main)
$ git branch -d ft/new-feature 
Deleted branch ft/new-feature (was f1fd1fc).


User@GisaF23 MINGW64 ~/Codes/project/git-basic (main)
$ git checkout -b ft/new-branch-from-commit 67b3713
Switched to a new branch 'ft/new-branch-from-commit'

User@GisaF23 MINGW64 ~/Codes/project/git-basic (ft/new-branch-from-commit)
$ git checkout main
Switched to branch 'main'
Your branch is ahead of 'origin/main' by 22 commits.
  (use "git push" to publish your local commits)

User@GisaF23 MINGW64 ~/Codes/project/git-basic (main)
$ git merge ft/new-branch-from-commit 
Already up to date.

User@GisaF23 MINGW64 ~/Codes/project/git-basic (main)
$ git checkout ft/new-branch-from-commit 
Switched to branch 'ft/new-branch-from-commit'

User@GisaF23 MINGW64 ~/Codes/project/git-basic (ft/new-branch-from-commit)
$

User@GisaF23 MINGW64 ~/Codes/project/git-basic (ft/new-branch-from-commit)
$ git checkout main
error: Your local changes to the following files would be overwritten by checkout:
        README.md
Please commit your changes or stash them before you switch branches.
Aborting

User@GisaF23 MINGW64 ~/Codes/project/git-basic (ft/new-branch-from-commit)
$ git switch main
error: Your local changes to the following files would be overwritten by checkout:
        README.md
Please commit your changes or stash them before you switch branches.
Aborting

User@GisaF23 MINGW64 ~/Codes/project/git-basic (ft/new-branch-from-commit)
$ git add README.md && git commit -m 'changes
> '
[ft/new-branch-from-commit 8c8272a] changes
 1 file changed, 2 insertions(+), 1 deletion(-)

User@GisaF23 MINGW64 ~/Codes/project/git-basic (ft/new-branch-from-commit)
$ git switch main
Switched to branch 'main'
Your branch is ahead of 'origin/main' by 22 commits.
  (use "git push" to publish your local commits)

User@GisaF23 MINGW64 ~/Codes/project/git-basic (main)
$ git merge ft/new-branch-from-commit 
Auto-merging README.md
CONFLICT (content): Merge conflict in README.md
Automatic merge failed; fix conflicts and then commit the result.

User@GisaF23 MINGW64 ~/Codes/project/git-basic (main|MERGING)
$ git add README.md && git commit -m 'merging new feature branch to main'
[main 900f3e8] merging new feature branch to main

User@GisaF23 MINGW64 ~/Codes/project/git-basic (main)
$ 

User@GisaF23 MINGW64 ~/Codes/project/git-basic (main)
$ git branch -m ft/new-branch-from-commit ft/improved-branch-name

User@GisaF23 MINGW64 ~/Codes/project/git-basic (main)
$ git branch
  ft/branch
  ft/improved-branch-name
* main
  master

  User@GisaF23 MINGW64 ~/Codes/project/git-basic (main)
$ git checkout c0f44c1
Note: switching to 'c0f44c1'.

You are in 'detached HEAD' state. You can look around, make experimental
changes and commit them, and you can discard any commits you make in this
state without impacting any branches by switching back to a branch.

If you want to create a new branch to retain commits you create, you may
do so (now or later) by using -c with the switch command. Example:

  git switch -c <new-branch-name>

Or undo this operation with:

  git switch -

Turn off this advice by setting config variable advice.detachedHead to false

HEAD is now at c0f44c1 renaming branch

User@GisaF23 MINGW64 ~/Codes/project/git-basic ((c0f44c1...))
$ git log --oneline
c0f44c1 (HEAD, main) renaming branch
baab283 creating branch from commit
900f3e8 merging new feature branch to main
8c8272a (ft/improved-branch-name) changes
ef1d4ca branch deletion
67b3713 Merge branch 'ft/new-feature'
d0a2b93 creating new feature branch and readme file
d7d8702 updated project readme
f1fd1fc implemented core functionality for new feature
:
c0f44c1 (HEAD, main) renaming branch
baab283 creating branch from commit
900f3e8 merging new feature branch to main
8c8272a (ft/improved-branch-name) changes
ef1d4ca branch deletion
67b3713 Merge branch 'ft/new-feature'
d0a2b93 creating new feature branch and readme file
d7d8702 updated project readme
f1fd1fc implemented core functionality for new feature

User@GisaF23 MINGW64 ~/Codes/project/git-basic ((c0f44c1...))
$ git branch
* (HEAD detached at c0f44c1)
  ft/branch
  ft/improved-branch-name
  main
  master

User@GisaF23 MINGW64 ~/Codes/project/git-basic ((c0f44c1...))
$ git checkout main
Switched to branch 'main'
Your branch is ahead of 'origin/main' by 26 commits.
  (use "git push" to publish your local commits)