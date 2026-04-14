# How to do a Cherry Pick

## What is a Git Cherry-Pick?

A **git cherry-pick** allows you to take a specific commit from one branch and apply it onto another branch.  
Instead of merging an entire branch, you selectively pick individual commits.

This is useful when:
- You only need a specific fix or feature from another branch
- You want to avoid merging unrelated changes
- You are applying a hotfix from a different branch

Cherry-pick creates a **new commit** on the target branch with the same changes as the original one, but with a different commit hash.

---

## How to Cherry-Pick a Commit (Step by Step)

### 1. Identify the source and target branches

First, identify the branch where the changes you want to apply are located (source branch), and the branch where you want to apply those changes (target branch).

For example, you may have some changes in the `qa` branch that you want to apply to the `release/1.6.1` branch.

In this case:
- **Source branch:** `qa`
- **Target branch:** `release/1.6.1`

Next, you need to identify the commit hash(es) from the source branch (`qa`) that you want to cherry-pick.


### 2. Go to the source branch (`qa`) and click on **Commits**

Navigate to the `qa` branch in your repository and open the **Commits** view.

_Image 1_


### 3. Copy the commit hash

Find the commit you want to cherry-pick and copy its commit hash.

_Image 2_


### 4. Switch to the target branch

Checkout the branch where you want to apply the commit.

Example:

```bash
git checkout release/1.6.1
```

### 5. Perform the cherry-pick
Run the cherry-pick command using the copied commit hash.
Example:

```bash
git cherry-pick 331ff06a05ae1f2bb8ceee2b3b45e16529325aef
```

6. Push the changes
Once the cherry-pick is completed successfully, push the changes to the remote repository:

```bash
git push
```
