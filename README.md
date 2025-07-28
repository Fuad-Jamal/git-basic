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