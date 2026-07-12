# Git & GitHub Workflows

A hands-on Git and GitHub project demonstrating feature branching, pull requests, Git LFS, Git Stash, and version control best practices.

---

## Table of Contents

- [Project Overview](#project-overview)
- [Q1 – CalculatorPlus Feature Development](#q1--calculatorplus-feature-development)
- [Q2 – Git LFS Implementation](#q2--git-lfs-implementation)
- [Q3 – Geometry Calculator Using Git Stash](#q3--geometry-calculator-using-git-stash)
- [Project Structure](#project-structure)
- [Branch Structure](#branch-structure)
- [Version Releases](#version-releases)
- [Git Log Visualization](#git-log-visualization)
- [Conclusion](#conclusion)

---

# Project Overview

The project consists of three main tasks:

* **Q1 – CalculatorPlus Feature Development**
* **Q2 – Git LFS for Large Files**
* **Q3 – Geometry Calculator using Git Stash**

All development steps, branching strategies, and version releases are documented below.

---

# Q1 – CalculatorPlus Feature Development

## Step 1 – Repository Setup

A private GitHub repository named **git-github-workflows** was created and cloned locally.

```
git clone <repository-url>
cd git-github-workflows
```

---

## Step 2 – Create Development Branch

A development branch `dev` was created from `main`.

```
git checkout -b dev
git push origin dev
```

The base **CalculatorPlus** Python application was added.

---

## Step 3 – Version 1 Release

The development branch was merged into the main branch to create **Version 1**.

```
git checkout main
git merge dev
git tag v1.0
git push origin v1.0
```

---

## Step 4 – Implement Square Root Feature

A new feature branch was created:

```
git checkout -b feature/sqrt
```

The square root functionality was implemented using Python's `math.sqrt()`.

Example implementation:

```
def square_root(self, x):
    return math.sqrt(x)
```

A Pull Request was created:

```
feature/sqrt → dev
```

---

## Step 5 – Bug Fix in Divide Function

While developing the feature, a critical bug was discovered in the divide function.

Fixed implementation:

```
def divide(self, a, b):
    if b == 0:
        raise ValueError("Cannot divide by zero.")
    return a / b
```

The fix was committed to the `dev` branch.

---

## Step 6 – Version 2 Release

After completing the feature and bug fix, the `dev` branch was merged into `main`.

```
git checkout main
git merge dev
git tag v2.0
git push origin v2.0
```

---

# Q2 – Git LFS Implementation

Git Large File Storage (LFS) was used to handle large binary files.

## Install Git LFS

```
git lfs install
```

---

## Create LFS Branch

```
git checkout -b lfs
```

---

## Track Binary Files

```
git lfs track "*.bin"
```

This created the `.gitattributes` file.

---

## Add Large File

A large binary file (greater than 200MB) was generated and added.

```
git add largefile.bin
git commit -m "Add large file using Git LFS"
git push origin lfs
```

Verification command:

```
git lfs ls-files
```

---

# Q3 – Geometry Calculator Using Git Stash

A new Python program was created to calculate the area of a circle and rectangle.

## Create Branch

```
git checkout -b geometry-calculator
```

Created file:

```
geometry.py
```

---

## Feature Branch – Circle Area

```
git checkout -b feature/circle-area
```

Circle area calculation was implemented:

```
Area = π × radius²
```

Before committing, incomplete changes were stored using:

```
git stash
```

---

## Feature Branch – Rectangle Area

```
git checkout -b feature/rectangle-area
```

Rectangle area formula implemented:

```
Area = length × width
```

Again, work was temporarily stored using:

```
git stash
```

---

## Restore Stashed Work

Saved work was restored using:

```
git stash pop
```

Both features were completed and committed.

---

## Pull Requests

Two pull requests were created:

```
feature/circle-area → dev
feature/rectangle-area → dev
```

After review, both pull requests were merged.

Finally, the `dev` branch was merged into `main`.

```
git checkout main
git merge dev
git push origin main
```

---

# Project Structure

```
calculatorplus.py
geometry.py
README.md
```

---

# Branch Structure

```
main
dev
feature/sqrt
feature/circle-area
feature/rectangle-area
geometry-calculator
lfs
```

---

# Version Releases

```
v1.0 – Initial release of CalculatorPlus
v2.0 – Added square root functionality and bug fix
```

---

# Git Log Visualization

The following command was used to visualize the branch structure:

```
git log --graph --oneline --decorate --all



```
# Code Review Collaboration
```

# For collaboration, I reviewed an another GitHub repository.

Steps performed:
1. Reviewed the feature implementation in their repository.
2. Provided feedback and approved their Pull Request.


# A pull request was created and reviewed by the collaborator.

Steps performed:
1. Created a feature branch and raised a pull request.
2. The collaborator reviewed and approved the pull request.
3. The pull request was merged into the main branch after approval.
```
---
## Conclusion
```
This repository demonstrates the following Git concepts:
* Branching strategy
* Feature development workflow
* Pull request and code review process
* Git stash usage
* Git LFS for large files
* Version tagging and releases
```
---
## Thank You
