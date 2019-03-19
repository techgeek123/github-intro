## Releases


### Release0: Introduction to Git Commands
Follow this link & finish the online exercise [Learn Git in 15 Minutes](https://try.github.io/levels/1/challenges/1)

### Release1: Branching

1. Create a folder called learn_branching and cd into it => `mkdir learn_branching && cd learn_branching`.
2. Initialize a git repository => `git init`.
3. Create a file called first.txt => `touch first.txt`.
4. Add that file `git add .`.
5. Commit that file `git commit -m "initial commit"`.
6. Create a new branch called feature => `git checkout -b feature`.
7. Now that you are on the feature branch, create a file called new.txt => `touch new.txt`.
8. Add that file => `git add .`.
9. Commit that file => `git commit -m "adding new.txt"`.
10. Create another file called another.txt => `touch another.txt`.
11. Add that file => `git add .`.
12. Commit that file => `git commit -m "adding another.txt"`.
13. Change back to the master branch => `git checkout master`. Note that this branch has no awareness of new.txt or another.txt!
14. Merge our changes from the feature branch into the master branch => `git merge feature`
15. Delete our branch called feature => `git branch -D feature`
16. Now if you take a look at `git log --oneline --decorate` you'll see that the commit history on feature has ben merged into master! (`--decorate` gives you nice coloring around branches and where they are in the commit history.)

### Release2: Branching Exercise

Go to this website [Learn Git Branching](http://learngitbranching.js.org/) & finish the exercises

### Release 3: Branching Quick Challenge
1. Create a folder called branch_time.
2. `cd` into that folder.
3. Initialize an empty git repository.
4. Create a file called first.txt, then add and commit the file.
5. Create a new branch called amazing_feature.
6. Create a file called best.txt.
7. Add the file.
8. Commit the file with the message `-m "added best.txt"`.
9. Switch back to the master branch.
10. Merge your changes from the feature branch into master.
11. Delete the feature branch.


### Release4: (Follow to understand Merge & Merge Conflicts. To get more info read `merging.md`)

Things get even worse when you commit changes to the same file on two different branches. In that case, Git does not know which commit to go with so it creates a merge conflict. This is basically Git's way of saying "Hey human, you're asking me to put conflicting files in the commit history; I don't know how to resolve these conflicts, so you take care of it and let me know when you're done."

Let's see an example by creating our very own merge conflict! Starting in our home directory:

- `mkdir merge_conflicts`
- `cd merge_conflicts`
- `git init`
- `echo first > first.txt`
- `git add .`
- `git commit -m "first commit"`

- `git checkout -b new_branch`
- `echo second > second.txt`
- `git add .`
- `git commit -m "adding second.txt"`

- `git checkout master`
- `echo something_else > second.txt`
- `git add .`
- `git commit -m "adding second.txt on the master branch"`

- `git merge new_branch`

### This final command should output

Auto-merging second.txt
CONFLICT (add/add): Merge conflict in second.txt
Recorded preimage for 'second.txt'
Automatic merge failed; fix conflicts and then commit the result.

Looks like we have an issue because when we tried to merge the new_branch, git does not know which second.txt file to use! Both branches have a file with the same name, but different contents.

If we take a look at our second.txt file (`cat second.txt`) we will see this
```
something_else
=======
second
>>>>>>> new_branch
```
What we see is the contents in HEAD, where master is, followed by the contents in new_branch. Let's open up this file in our text editor and change it so that it looks like this:
```
second
```
This is our way of letting Git know that we want to keep the text from new_branch and discard the text from master.

Then let's go back to the terminal and run

- `git add .`
- `git commit -m "fixing merge conflict"`

From here you should be good to go.
