### Exercise
1. Make bad changes to a file, then use `git checkout` to fix it. Use `git checkout` to reset your file back to an earlier point in time.
2. Use `git clean` to remove untracked files from your repo. Remember to use `--dry-run` first.
3. Stage a change and then use `git reset` to unstage it. Use `git reset --hard` to reset your branch back pointer, staging area, and working area to an earlier commit. Use "mixed mode" to reset your branch back to an earlier commit, then use `ORIG_HEAD` to reset your branch back to where you were.
4. Practice using `git revert` to safely revert a commit with a new commit.

## Solutions

### Step 1 - Undo changes in your working area with `git checkout -- <file>`

```
$> echo "Bad data" > hello.template

$> cat hello.template
Bad data
```

```
$> git checkout -- hello.template

$> cat hello.template
[greeting] [noun]!
This is a test of the emergency git-casting system.
```

# Let's find the commit where hello.txt was renamed to hello.template

$> git log --name-status --follow --oneline hello.template

# Now let's checkout hello.txt from one commit before then

$> git checkout fec9e7b -- hello.txt
$> cat hello.txt

$> git reset HEAD hello.txt

$> git rm hello.template


$> git status
