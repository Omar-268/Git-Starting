# Git merge 

Version control makes it possible to develop multiple variations of the code at once, thanks to the use of branches.

## Branches

Branch represents an independent line of development. We create branches to independently and uninterruptly work on some functionality, which later is merged to the main line.

we can check what branches we have and also on which branch we currently are.
```bash
$ git branch
* master
```
Our current branch is pointed by asterisk.

We can create new branch using `git checkout -b newbranch-name`
```bash
git checkout -b newbranch
$ git branch
  master
* newbranch
```

you can view the Commit History using `git adog`:
```bash
$ git adog
* 21450a0 (HEAD -> newbranch, master) my new feature
* ac028b6 commit for all new files
* be34289 commit for testfile-02
* 1c84521 commit for testfile-01
```
This shows how the commit history diverges when working on different branches.
You’ll notice the HEAD pointer moves depending on the branch you’re on.


## Merging Branches

To merge the branch back into master:

```bash
git checkout master
git merge newbranch --no-edit
```

As we finished work on branch, we can delete it

```bash
git branch -d newbranch && git branch
```


You can try this scenario yourself in the following lab: [Merge branches](https://killercoda.com/pawelpiwosz/course/gitFundamentals/git-13-git-merge)
