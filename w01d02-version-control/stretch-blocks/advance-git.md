# Releases

# Release0: Rebase Interactive

- Let's start with a project, add a few commits and then explore the command `git rebase -i`:

```
mkdir learn_rebase
cd learn_rebase
git init

echo first > first.txt
git add .
git commit -m "adding first"

echo second > second.txt
git add .
git commit -m "adding second"

echo third > third.txt
git add .
git commit -m "adding third"

echo fourth > fourth.txt
git add .
git commit -m "adding fourth"

echo fifth > fifth.txt
git add .
git commit -m "adding fifth"

echo sixth > sixth.txt
git add .
git commit -m "adding sixth"

git log --oneline | cat | wc -l # shows us we have 6 commits

git rebase -i HEAD~5 # let's rebase from the earliest commit possible
```

What results do you get? Analyse those result & read more about what `git rebase -i` returns.

## Release 1:

Finish all these exercises on this [Github Repo](https://github.com/praqma-training/gitkatas)

By the end of the exercise you'll be a Github Master