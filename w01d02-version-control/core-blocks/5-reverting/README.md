# Releases

# Release0: Reverting

- When to use `git revert`?
- Why is `git revert` preffered over `git reset`?

# Release1:

- Create a folder called `learn_revert`
- `cd` into the folder `learn_revert`
- Initialize a git repository
- Create a file called `first.txt`
- Add the text "Start" to `first.txt`
- Add the `first.txt` file
- Commit with the message "Adding first.txt"
- Add the text "WRONG" to `wrong.txt`
- Add the `wrong.txt` file
- Commit with the message "Adding WRONG to wrong.txt"
- Add the text "More" to `first.txt`
- Add the `first.txt` file
- Commit with the message "Adding More to first.txt"
- Add the text "Even More" to `first.txt`
- Add the `first.txt` file
- Commit with the message "Adding More to first.txt"
- OH NO! We want to undo the commit with the text "WRONG" - let's revert! Since this commit was 2 from where we are not. What will we do?

> note that the commit history hasn't been altered, we've just added a new commit reflecting the removal of the `wrong.txt`