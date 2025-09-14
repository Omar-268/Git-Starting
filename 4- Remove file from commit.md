# Remove file from commit
At times, we might change our mind about the work we’ve done. Git offers ways to clean up.

## Remove files from stage

Let's imagine you have 4 files in stage.

```bash
$ git status
On branch master

No commits yet

Changes to be committed:
  (use "git rm --cached <file>..." to unstage)
        new file:   testfile-01
        new file:   testfile-02
        new file:   testfile-03
        new file:   testfile-04
```

Let's remove testfile-01

```bash
git rm --cached testfile-01
```
Lets Check Again 

```bash
 git status
On branch master

No commits yet

Changes to be committed:
  (use "git rm --cached <file>..." to unstage)
        new file:   testfile-02
        new file:   testfile-03
        new file:   testfile-04

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        testfile-01

```

## Restore previous state of the file

Sometimes, instead of just removing a file from stage, we want to completely discard our changes and bring the file back to the state from the last commit.

First, let's check what is in the file testfile-01

```bash
$ cat testfile-01
first file
change
```
Now lets use the command `git checkout testfile-01` and chek the file again

```bash
$ git checkout testfile-01
Updated 1 path from the index
$ cat testfile-01
first file
```
We succesfully reset the file to the state from previous commit


You can try this scenario yourself in the following lab: [Remove file from commit](https://killercoda.com/pawelpiwosz/course/gitFundamentals/git-04-remove-file-from-commit)