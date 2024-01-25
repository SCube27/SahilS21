# Git Commands and Purposes :

1. ```git config --list``` :
    - It displays all currently set Git configuration settings for your user.
    - It pulls these settings from different configuration files, each with varying levels of precedence.

2. ```git init``` :
    - It initializes a new git repository inside the current folder.
    - Also creates a .git folder that contains all the logic to manage the repository.

3. ```git status``` :
    - It displays the current state of the Git working directory and staging area.
    - It's an essential tool for understanding changes made to files and tracking progress before committing those changes.

5. ```git add <file-name>``` :
    - Adds files to the staging area. The files over which git add is used are tracked by git.
 
4. ```git rm -cached <file-name>``` :
    - Restores the file from staging area to working area. Basically opposite of git add.

5. ```git commit -m "Message"``` :
    - Registes staging changes to a commit. Basically goes from staging area to repository area.

6. ```git log``` :
    - Keeps a log / record of all our commits. And hence shows all our commits.

7. ```git restore <file-name>``` :
    - Restores / Erases all the changes done to an already commited file.
    - If we did ```git add``` on already staged file then normal restore won't work.
    - For this do ```git restore --staged <file-name>```.

8. ```git diff <commit ID1> <commit ID2>``` :
    - This command shows the difference between two commits.
    - Take the commit IDs of the two commits you want to compare from git log.

9. ```git remote add <name-of-connection e.g origin> <online-repo-url>``` :
    - This command helps us to connect one repository with another repository.
    - It creates a direct link between two repositories so we can access & make change in one repo from another.
    - Here origin is the name of the connection, it can be anything else. So now if we just do git remote then it will list down names of all the connections the local repo has, in this case its *origin*.

10. ```git remote rm <name-of-connection>``` :
    - This command deletes the remote connection. It breaks the connection of local and online repository.

11. ```git remote rename <oldname> <newname>``` :
    - This command renames the remote connection already preent.

12. ```git push origin main``` :
    - The git push command makes the code push online to be visible for the users to see on Github.
    - It pushes all the commited code to the online repository on Github.
    - The origin is the name of the connection with online repository and main is the name of the branch to which we pushed th code.

13. ```git pull origin main``` :
    - Downloads the latest change from the branch of the mentioned remote connection.
    - Suppose someone has done changes in the code from their local repo or directly on github, that won't be visible on our local repo. We can make them visible by doing git pull. 
    - The connection name and branch name can vary.     

14. ```git stash``` :
    - Stashes the code that we don't want to be left in working directory but also don't want to insert in staging directory.
    - This only works on the staged files i.e files that are added (```git add```).

15. ```git stash list``` :
    - Shows the list of the stashes present previously.

16. ```git stash apply <stash-name>``` :
    - Retrieves the stashed code back from the stash for the given stash name.
[**NOTE**] : The applied stash is still going to be inside the stash, even though its retrieved.

17. ```git stash --include-untracked -- filename``` :
    - Stashes the untracked files (Files not even added i.e not git add). Modified version of ```git stash```.
    - To stash all the files whether tracked or untracked use ```git stash --all```.

18. ```git stash pop``` :
    - Takes out a stashed file back to the working directory.
    - This command removes the file from the stash too, so its not like apply that is creates a copy.
    - **NOTE**: This will work on last added file to stash.

19. ```git stash drop``` :
    - Takes out a stashed file back, but not in working directory.
    - The stashed file is deleted totally, so its neither present in stash nor in working directory.
    - **NOTE**: This will work on last added file to stash. To drop a specific stash use ```git stash drop <stash-name>```

20. ```git stash clear``` :
    - Deletes all the files present in stash.
    - Remaining all same functionalities as git stash drop.

21. ```git stash save "Message"``` :
    - To stash a tracked file with a specified message use this command.
    - To stash an untracked file use the following command ```git stash save "Message" --include-untracked```. 

22. ```git commit --amend "Message"``` :
    - To add files to the last commit instead of creating a new commit we can use this command.
    - So even if we left some files to include in the last commit, we can add those files to that commit by using this command. 

23. ```git log --graph``` :
    - This shows a graph like structure of all commits and branches.

24. ```git checkout -b <branch-name>``` :
    - This command creates a new branch. Now the HEAD points to this new branch.
    - Hence all the commits are added to this new branch.

25. ```git branch``` :
    - This command lists all the branches present in the git repository.
    - The branch who has * marked to it is the branch to which HEAD is pointing & hence all commits are added to it.

26. ```git checkout <branch-name>``` :
    - This command switches the branches as the name given in command.

27. ```git branch -d <branch-name>``` :
    - This command deletes the current working branch.
    (Before deleting the branch check whether the right branch to be deleted is active or not.) 

28. ```git clone <repo-link>``` :
    - This command downloads the github repository on the given url to your local machine of making changes and contributing to it.  

29. ```git remote add upstream <repo-link of the original repo>``` :
    - This command creates an upstream for you from the repository you have forked in.
    - In normal repos owned by you the changes can be seen by you directly as you pull changes from the repo.
    - But for the forked repos, you've cloned even if you pull changes they can't be seen as the changes are made on the original repo & not the forked one with you.
    - So we setup a upstream for the original repo so we can get the latest changes made in the original repo.
    ![Upstream](https://devopscube.com/wp-content/uploads/2021/02/git-forked-upstream-min.png.webp)

30. ```git log --since="time-period" ``` :
    - This command helps us to get in list of commits done in the given *time period*.
    - The time periods can be specified as : "yesterday", "1 minute ago", "5 minutes ago" etc.

31. ```git log --grep=<some word>``` :
    - This command shows the list of all the commits having the given specified word in their commit message.
    - The word can be any word that you think is written in the past commit messages.

32. ```git clean <flag> <file-name>``` :
    - This command cleans the working area by deleting all the untracked files present in it.
    - The flag is defined to know what kind of cleaning we want to do.
        1. -f : This forcefully deletes all the untracked files present in the working area.
        2. --dry-run : This flag shows us which files it will remove, it doesnt directly remove the files.
        3. -d --dry-run : Same as above flag just that the -d flag will also add all the untracked directory.
        4. -d -f : This will delete all the untracked files as well as directories(folders) in the working area.
        
33. ```git reset ...``` :
    - Check the theory section for understanding this command and concept behind it.

34. ```git revert <commit-id> / HEAD-traversal``` :
    - This command doesnt move the head and branch pointer to a new commit rather, it creates a new revert commit ahead of current commnit which contains the similar data to the previous commit of current commit. 

35. ```git switch <branch-name>``` :
    - This command is used to switch the branch pointer from current to the specified one.
    - Just name the branch in the command to switch and then we switch to the specified branch as the current working branch.

36. ```git merge <feature-branch name>``` :
    - This command is used to merge the specified feature branch in the main branch.
    - If the main & feature branch has changes in same file then it will create a merge conflict.
    - If the main branch has not moved ahead since feature branch was created then Fast-Forward will occur.
    - If the main branch has moved ahead since feature branch creation then a proper merge happens with a merge commit message.

37. ```git rebase <feature-branch name>``` :
    - This is somewhat similar to ```git merge```, this command creates a copy of the feature branch(all commits in feature) and adds them infront of the main branch.
    - This creates a clean linear structure at the end of the merge in the main branch.

38. ```git rebase --interactive main``` :
    - This command is used to rebase the feature branch in the main branch using a single commit only. Basically this squashes all the commits of feature in a single commit and adds them to the main branch.
    - [**IMP**] Use this command from the branch to be rebased only.
    - This opens a interactive window in the VS code through which we perform squashing. (Read the instructions in the VS code window properly while squashing).

[**NOTE** : We can do this squashing thing from GitHub itself too making it more easier]

39. ```git fetch origin <branch-name>``` :
    - The fetch command helps us to fetch changes from a particular branch only, from the remote repository.
    - Instead of pull we can use fetch to pull changes in the current working branch.
    - Basic difference between pull & fetch is that pull downloads the branch and merges it in the current working branch while fetch just downloads the branch but doesnt merge it.

# Windows Commands :

1. ```dir /a``` : This shows all the hidden files inside the current folder.

2. If dont want to let git manage the folder then delete the **.git** folder.

3. ```del``` : To delete a file or folder.

4. ```echo some-content > filename``` : Creates a file with some content in it

5. ```type filename``` : Shows conten present inside the file.

6. ```nslookup <website-name.com (.in .edu etc)``` : This shows the name of the authority holding the website and IP address of server serving the website.

# Some other Theory :

1. In a git project there are 3 areas in which the file changes can reside :
    - *Working Area* : Files not being tracked by git are present in Working area (before git add)
    - *Staged Area* : Files not present in the github are present in Staged area (before git commit)
    - *Repository Area* : Files present and visible in github are in Repository area (after git commit)
Any file change done in the project might reside in any of these three areas.

2. A Commit is a particular version of the project. It captures a snapshot of the project's staged changes.

3. If you want to move the whole file back to untracked area then we have to do ```git rm``` and if we want to play with staging area and working area then we use ```git restore```.

4. Just a cool hack git command ```git log --all --decorate --oneline --graph``` to see a visualizing structure (graph) of all commits and branches.

5. ```git checkout <commit-id, branch-name>``` this command is used to move the head pointer to the specified commit, branch etc

6. ```git reset <commit id, branch name>``` this command is used to move both branch and head pointer to the specified commit / branch at the same time. This command has 3 modes as follows :
    - **Soft** : 
        1. Command is ```git reset --soft <commit id>```, this command moves the head & branch to the specified commit
        2. Now the previous commit the head & branch was pointing to is no more referenced and hence is lost
        3. A new commit created will be pointed by this commit on which HEAD & branch are pointing.
        4. There's a way to go back to go to the previous lost commit by using the command ```git reset ORIG_HEAD```
        5. This command is safe as it doesnt make changes in the working or staging area and hence these changes can be retained.
        [**NOTE** : The command on 4th point will only work if there are no new commits created from this new commit position.]

    - **Mixed** :
        1. Command is ```git reset --mixed <commit-id>```, this command not only moves the head & branch to the specified commit but also overrides the staged changes to which the head & branch are moved.
        2. In easy words when we apply this command the branch & head move to specified commit and move all the files in staging area to untracked area too.

    - **Hard** : 
        1. Command is ```git reset --hard <commit-id>```, this command not only moves the head & branch to the specified commit but also removes (deletes) the changes present in the staging and working area.
        2. Basically it makes the tree clean with no changes present at all.

*(So in summary --soft makes no changes either to working & staging area, --mixed makes changes to only the staging area, --hard makes changes to both working and staging area)*

## Recommended Practice To Do :
    1. Make changes to the files
    2. git add
    3. git commit
    4. git pull
    5. git push

### Some important articles based on Git :

* Git Reset & Modes : https://www.atlassian.com/git/tutorials/undoing-changes/git-reset
* Git forking, pr & upstreams : https://devopscube.com/set-git-upstream-respository-branch/ 