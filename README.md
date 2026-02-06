# DND Stay Connected Project

This is the central repository for the DND Stay Connected project. This repository acts as a "meta-repo," aggregating various sub-projects (like our custom `open5gs` core network fork) into a single version-controlled workspace.

## 📂 Project Structure

This project uses **Git Submodules**. This means the folders you see below are actually links to other Git repositories.

* **`open5gs/`**: Our custom fork of the Open5gs core network.
* *(Future sub-projects will appear here)*

---

## 🚀 Getting Started

### 1. Prerequisites
* **Git**: Ensure you have a recent version of Git installed.
* **SSH Access**: Ensure your SSH keys are added to your GitHub account, as this repo uses SSH for submodule synchronization.

### 2. Cloning the Repository
**Do not** just use standard `git clone`. You must tell Git to initialize the submodules recursively.

Run this command in your terminal:

```bash
git clone --recurse-submodules git@github.com:nrg-uw/DND-stay-connected.git
```

**If you already cloned it without that flag:** You will see empty folders where code should be. Fix it by running:

```bash
git submodule update --init --recursive
```

### 3. Building the Code 
Currently, we do not have a centralized build system. You must build each sub-project individually according to its own documentation.

### 4. Contributing
#### Pulling Latest Changes from the Team

```Bash
# 1. Pull the changes for the parent repo
git pull

# 2. Update the submodules to the commit pinned by the team
git submodule update --recursive
```

#### Making Changes to Code in Sub-Project
1. Enter subproject directory `cd subproject-name`
2. Make new branch for yourself `git checkout -b my-branch`
3. Make your changes, compile, and test
4. Commit and push to the **sub-project's** remote
```bash
git add .
git commit -m "Commit Message"
git push origin my-branch
```
5. Go to GitHub to create a Pull Request into main branch if you are working on a subproject that someone else is working on. You may skip this if you are the only person working on this subproject.


---

#### Adding New Sub-Project
1. Checkout a new branch `git checkout -b add-submodule-name`
2. Add the submodule:
```bash
git submodule add git@github.com:YourTeam/new-repo-name.git folder-name folder-name
```
2. Commit and open PR:
```bash
git add .gitmodules folder-name
git commit -m "Add new-repo-name as a submodule"
git push origin
```