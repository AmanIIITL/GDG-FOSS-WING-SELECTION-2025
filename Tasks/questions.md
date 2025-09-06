### Answer the following questions in you own words.

> It's not necessary that you havee to know and answer all the questions. Just answer the ones
> you know and write in your own words.

1. Give the difference between the remotes - upstream and origin - with an example.

You answer: 
Origin typically refers to your own fork or clone of a repository.
"origin" is the default name Git gives to the server you cloned from.It represents your personal copy of the repository on a remote server. You push your local changes to "origin" to update your remote fork.
For example-
Use 'git push origin <branch>' to send your local changes to your personal remote fork.

Upstream points to the original repository from which you forked or cloned."upstream" refers to the original project repository. You fetch changes from "upstream" to keep your local repository ynchronized with the main project. This allows you to incorporate new features or bug fixes from the primary codebase.
For example-
Use 'git fetch upstream' to retrive updates from the original project repository.

Both the terms define the remote repositories your local Git setup tracks.

2. You have two branches A and B and you have currently made some changes in branch A.
You want to move into branch B but do not want to commit the current changes in branch A.
What will you do?

You answer:
We can use stash for this work.

In your repository A type:-
- git stash (this saves all the uncomitted changes)
then type:-
- git checkout B (switches to the branch B)

after your work here is done in B, type:-
- git checkout A (switches to the branch A)
then:-
- git stash pop (get your all saved uncommitted changes back)

3. You were assigned a work to implement a feature and create a PR to your organization's remote repository.
For this you made a branch (say A) and made some changes and commited them. Now you moved to some other branch 
(say B) to do some other assigned work. But later you realisd that have to complete the task assigned earlier 
first and commited some changes in branch B which are meant for branch A. How will you use git to bring the 
changes from branch B to branch A?

You answer:

3. What is the difference between fetching changes and pulling changes?

Your answer:
Fetching downloads ths latest changes from remote but does not merge them into your branch.
Pulling the changes not only downloads the files or performs fetching but it also puts it onto your workspace as well, i.e, merges the changes directly into your branch

4. What does -i flag stand for? What is it's significance in git?

You answer:
The -i flag is used in interactive mode. The -i flag lets you interactively edit, squash, or reorder the last 3 commits. It is useful when you want to combine commits, clean history, or fix commit messages before pushing.

5. You are working in an organization that follows very strict guidelines for PRs and commits.
You made three commits in your PR and the maintainer says you were supposed to make a single commit.
What will you do in this case?

You answer:

6. Explain `git merge` and `git rebase` with example(s).

You answer:
'git merge' combines two branches, creates a new commit showing history diverged. Hence, it will merge the two repoitories into a new one and shows the history hacing a merge commit.
For example:-
-git checkout main
-git merge feature
Result: history has a merge commit.

'git rebase' moves your branch commits on top of another branch, for example, if you type 'git rebase main' then it hows that you started work from the latest main branch by taking the commits at the top.

7. Write the flow how you create a repository and push changes to it. Also mention the commands used at each step.

You answer:
Firstly, create a repository on your GitHub account.
Then intialize the repository by:-
- git init
- git remote add origin <repository_url>

Then add your files:
- git add .

Commit the changes after that:-
- git commit -m "Commit sentence"

Then push your changes:-
- git branch -M main
- git push -u origin main

8. How would you prevent a file or folder from getting tracked by git?

Your answer:
By add the files or folder inside .gitignore which tells github to ignore the contents of the files inside it.

-node_modules/
-.env

9. You did not implement the step you mentioned in question 8 and now you have committed and pushed your database's
secret key to the github. How will you remove the key from your git's commit history to avoid any misuse?

You answer:
By removing the file from the repository
First remove the file:-
- git rm --cached secret.txt

Commit the removal of the file:-
- git commit -m "Remove secret key"
- git push origin main

If you completely want to remove from histroy-
- git filter-repo --path secret.txt --invert-paths

Force the push then:-
- git push origin --force --all
but keep in mind to change your secret key

---