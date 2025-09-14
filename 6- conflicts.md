# How to fix conflicts

Conflicts can happen. If some number of people are working on the same project, they might work on the same file at the sime time. And then, when you try to commit, or merge, you find out that something called conflict was created.

## Scenario
Imagine you have a file called `testfile-02`.  
- First, you wrote a sentence → that became **commit1**.  
- Then, you added another sentence → that became **commit2**.  

Now you decide: *"I want to go back one step"* → you run **revert**.


## The Problem
When you reverted `commit2`, Git tried to remove **only the last change**.  
But since the same file was also changed in `commit1`, Git didn’t know exactly what to keep and what to remove.  

Result: **CONFLICT** 

lets see what is in **testfile-02** now

```
$ cat testfile-02
second file
This is my important change
```

Now, Let's try to do revert 

```bash
$ git revert --no-edit HEAD~1
Auto-merging testfile-02
CONFLICT (content): Merge conflict in testfile-02
error: could not revert 502c2ba... my new feature
hint: After resolving the conflicts, mark them with
hint: "git add/rm <pathspec>", then run
hint: "git revert --continue".
hint: You can instead skip this commit with "git revert --skip".
hint: To abort and get back to the state before "git revert",
hint: run "git revert --abort".
```
Git tries to undo that commit, but:
- The same file (testfile-02) was changed in multiple commits.
- Git can’t decide what to keep → merge conflict.

Let's see what we have in file
```bash
$ cat testfile-02
second file
<<<<<<< HEAD
This is my important change
=======
>>>>>>> parent of 502c2ba (my new feature)
```
Git added special markers inside the file to show the conflict:

- <<<<<<< HEAD → shows the content currently in your branch.
- ======= → is the separator line.
- '>>>>>>>' → shows the content Git wanted to bring back (empty in this case)

## The Solution

Simply open the file, remove the conflict markers, and keep only the text you want.

In this example, we used a quick command to remove the conflict lines
`sed -i '2,5d' testfile-02`

This deleted lines 2 to 5, which contained the conflict.

After Fixing the File

Tell Git that you have resolved the conflict:

```bash
git add testfile-02
git commit -m "fixed conflict"
```

You can try this scenario yourself in the following lab: [Conflicts Lab](https://killercoda.com/pawelpiwosz/course/gitFundamentals/git-09-houston-we-have-conflict)