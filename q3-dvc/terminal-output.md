```text
(aiops) hasini@ubuntu-m4:~/Desktop/aiops-module1$ git checkout v1
D	q2-mlflow/comparision.png
Note: switching to 'v1'.

You are in 'detached HEAD' state. You can look around, make experimental
changes and commit them, and you can discard any commits you make in this
state without impacting any branches by switching back to a branch.

If you want to create a new branch to retain commits you create, you may
do so (now or later) by using -c with the switch command. Example:

  git switch -c <new-branch-name>

Or undo this operation with:

  git switch -

Turn off this advice by setting config variable advice.detachedHead to false

HEAD is now at b582299 v1 - 1800 files

(aiops) hasini@ubuntu-m4:~/Desktop/aiops-module1$ git checkout main -- .dvc/config
(aiops) hasini@ubuntu-m4:~/Desktop/aiops-module1$ dvc checkout
Building workspace index                                                                                              |2.00 [00:00,  599entry/s]
Comparing indexes                                                                                                    |3.00 [00:00, 4.72kentry/s]
Applying changes                                                                                                      |1.00 [00:00,   455file/s]
M       q3-dvc/images-list.csv

(aiops) hasini@ubuntu-m4:~/Desktop/aiops-module1$ wc -l q3-dvc/images-list.csv
1801 q3-dvc/images-list.csv

(aiops) hasini@ubuntu-m4:~/Desktop/aiops-module1$ git checkout main
D	q2-mlflow/comparision.png
Previous HEAD position was b582299 v1 - 1800 files
Switched to branch 'main'
Your branch is ahead of 'origin/main' by 1 commit.
  (use "git push" to publish your local commits)

(aiops) hasini@ubuntu-m4:~/Desktop/aiops-module1$ dvc checkout
Building workspace index                                                                                              |2.00 [00:00,  895entry/s]
Comparing indexes                                                                                                    |3.00 [00:00, 4.74kentry/s]
Applying changes                                                                                                      |1.00 [00:00,   592file/s]
M       q3-dvc/images-list.csv

(aiops) hasini@ubuntu-m4:~/Desktop/aiops-module1$ wc -l q3-dvc/images-list.csv
2801 q3-dvc/images-list.csv

(aiops) hasini@ubuntu-m4:~/Desktop/aiops-module1$