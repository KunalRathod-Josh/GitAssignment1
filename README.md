# Git Assignment

## Task 1: Initialize a Git Repository

Create a directory for project and initialize a Git repository.

```bash
mkdir GitAssignment1
cd GitAssignment1
git init
```

---

## Task 2: Create at least 2 feature branches from the main branch (Add multiple files)

1. Create a feature branch `branch1` from the current `master` branch.

```bash
git branch branch1
git checkout branch1
```

2. Add a file and commit the changes.

```bash
vi myfile.txt  # Create a new file
git add .
git commit -m "myfile.txt is created"
```

3. Switch back to the `master` branch and create another feature branch `branch2`.

```bash
git checkout master
git checkout -b branch2
```

4. Add another file and commit the changes.

```bash
vi bio.txt  # Create another file
git add .
git commit -m "bio.txt is created"
```

---

## Task 3: Add Commits on Each Feature Branch

### On `branch1`:

Create and commit `myfile.txt`:

```bash
echo "# Git Assignment" > README.md
git add README.md
git commit -m "First commit"
git branch  # Confirm you're on 'master' branch
git branch branch1  # Create branch1
git checkout branch1  # Switch to branch1
vi myfile.txt  # Create a new file
git add .
git commit -m "myfile.txt is created"
```

### On `branch2`:

Create and commit `bio.txt`:

```bash
git checkout master  # Switch back to master
git checkout -b branch2  # Create and switch to branch2
vi bio.txt  # Create the bio.txt file
git add .
git commit -m "bio.txt is created"
```

---

## Task 4: Try These Git Commands

### 1. **Diff**

The `git diff` command shows changes between the working directory and the staging area:

```bash
git diff
```

Output:

```diff
diff --git a/bio.txt b/bio.txt
index ecee933..87de02d 100644
--- a/bio.txt
+++ b/bio.txt
@@ -1 +1,2 @@
 I am Kunal
+A Software Engineer
```

---

### 2. **Reset (Soft and Hard)**

- **Soft Reset**: This command moves the `HEAD` to the previous commit but leaves your working directory unchanged.

```bash
git reset --soft HEAD~1
```

- **Hard Reset**: This command resets the `HEAD` to the previous commit and also updates the working directory, discarding any changes.

```bash
git reset --hard HEAD~1
```

---

### 3. **Stash**

Stashing saves your changes temporarily so you can switch branches or commit later.

```bash
git stash  # Save the changes
git checkout branch1  # Switch to branch1
git checkout branch2  # Switch back to branch2
git stash pop  # Retrieve stashed changes
git add .
git commit -m "stash used"
```

---

### 4. **Delete a Branch**

You can delete a branch after you’ve merged or finished working with it.

```bash
git branch -d branch1  # Delete branch safely if merged
git branch -D branch1  # Force delete if not merged
```

---

## Task 5: Push Each Branch to the Remote

### 1. Push `branch2` to the remote repository:

```bash
git push origin branch2
```

### 2. Merge `branch2` into `master` and Push:

1. Merge the changes from `branch2` into `master`.

```bash
git checkout master
git merge branch2
```

2. Push the merged changes to the remote `master` branch.

```bash
git push origin master
```
