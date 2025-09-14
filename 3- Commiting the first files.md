# Commit your first file
This scenario shows how to add and commit your first files to the repository.

# Initialize the Repository

When starting a new project, you first need to initialize a Git repository.

## Step 1
Create a directory for your project 
```bash
mkdir my-project
```
## Step 2
Now let's initialize Git 
```bash
git init
```

Now if you executed status command `git status` , it tells you information about your status
```bash 
$ git status
On branch master

No commits yet

nothing to commit (create/copy files and use "git add" to track)
```

## Step 3 
Now it is the time to create the first file.

```bash
touch newfile && echo "my first commit"
```

Let's check, if git sees the file `git status`

```bash
$ git status
On branch master

No commits yet

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        newfile

nothing added to commit but untracked files present (use "git add" to track)
```
In the output you see that our new file is untracked.

## Step 4 
Now it is the time to commit the first file.

Now it’s time to let Git know which changes we want to stage. To add a new file to the staging area, run:
```bash
git add newfile
```

Now lets check the status of git:
```bash
$ git status
On branch master

No commits yet

Changes to be committed:
  (use "git rm --cached <file>..." to unstage)
        new file:   newfile
```
You see that the file is tracked and ready to be commited.

So let's commit it!
```bash
git commit newfile -m "my first commit
```

Congratulations, you commited your first file!


You can try this scenario yourself in the following lab: [Commiting the first file](https://killercoda.com/pawelpiwosz/course/gitFundamentals/git-03-repo-init)