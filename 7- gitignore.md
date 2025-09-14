# How to ignore some content

## .gitignore
Git gives us the possibility to control what will be synchronized with remote and what will be not.

This is realized by file named `.gitignore`

We have this Folder 
```bash
$ cd test && ls -al
total 40
drwxr-xr-x 5 root root 4096 Sep 13 17:52 .
drwx------ 5 root root 4096 Sep 13 17:52 ..
drwxr-xr-x 7 root root 4096 Sep 13 17:52 .git
drwxr-xr-x 2 root root 4096 Sep 13 17:52 firstdirectory
-rw-r--r-- 1 root root   23 Sep 13 17:52 neveringit
drwxr-xr-x 2 root root 4096 Sep 13 17:52 seconddirectory
-rw-r--r-- 1 root root   11 Sep 13 17:52 testfile-01
-rw-r--r-- 1 root root   40 Sep 13 17:52 testfile-02
-rw-r--r-- 1 root root   11 Sep 13 17:52 testfile-03
-rw-r--r-- 1 root root   25 Sep 13 17:52 testfile-04
```
And we don't want to commit

- seconddirectory{{}} directory and its content
- neveringit file

If we checked git status 
```bash
$ git status
On branch master

No commits yet

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        firstdirectory/
        neveringit
        seconddirectory/
        testfile-01
        testfile-02
        testfile-03
        testfile-04
```
we can see `seconddirectory` `neveringit`.        

Let's now creat `.gitignore`

```bash
touch .gitignore
echo neveringit >> .gitignore
echo seconddirectory >> .gitignore
```

Now check the status agian:
```bash
$ git status
On branch master

No commits yet

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        .gitignore
        firstdirectory/
        testfile-01
        testfile-02
        testfile-03
        testfile-04
```
everything looks fine, you can now complete your job.

You can try this scenario yourself in the following lab: [.gitignore Lab](https://killercoda.com/pawelpiwosz/course/gitFundamentals/git-11-gitignore)