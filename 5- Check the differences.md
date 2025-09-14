# Check the differences

Git status gives us the current status. But how to get more detailed information what we changed?

##  Understanding `git diff`

The `git diff` command shows the differences between your **working directory** (current changes) and the **last commit** (`HEAD`) by default.  
It highlights what has been added, removed, or modified.

## Example

When we run:

```bash
git diff
```

We get:
```
diff --git a/testfile-01 b/testfile-01
index 303ff98..48db2e4 100644
--- a/testfile-01
+++ b/testfile-01
@@ -1 +1,2 @@
 first file
+change
```
lets Explana Each Part of the output

```bash
diff --git a/testfile-01 b/testfile-01
```
This line tells us Git is comparing the file testfile-01.

- a/ = the old version of the file.
- b/ = the new version of the file.

```bash
index 303ff98..48db2e4 100644
```
- 303ff98 → hash (ID) of the old file content.
- 48db2e4 → hash (ID) of the new file content.
- 100644 → file permissions (normal text file).

```bash
--- a/testfile-01
+++ b/testfile-01
```
- --- shows the old version of the file.
- +++ shows the new version of the file.

```bash
@@ -1 +1,2 @@
```
This line explains where the change happened.

- -1 → before, the file had 1 line.
- +1,2 → after, the file has 2 lines.

```bash
first file
+change
```
- Line with no symbol → unchanged (first file).
- Line starting with + → new line added (change).
- If a line had been removed, it would start with -.

You can try this scenario yourself in the following lab: [Check the differences](https://killercoda.com/pawelpiwosz/course/gitFundamentals/git-07-what-was-changed)