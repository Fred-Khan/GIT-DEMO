
# Git Commands Quick Reference

This reference guide provides essential Git commands for beginner users on **Windows**, **macOS**, and **Linux**. It covers configuration, repository initialisation, advanced operations (merging, conflict resolution, stashing), detailed Git workflows, branching strategies, and tips for teamwork. Common Troubleshooting Tips for Git Beginners section is also included at the end for common errors. If this is your first time pushing to GitHub, you can follow the numbered steps from 1 to 10 as a guide.

---

## 1. Configure Git User Settings

1. **Set your Git username**  
   🔧 *Configures your global Git username (used in commits).*  
   ```bash
   git config --global user.name "Your Name"
   ```

2. **Set your Git email**  
   ✉️ *Configures your global Git email address (used in commits).*  
   ```bash
   git config --global user.email youremail@domain.com
   ```

3. **Set the default branch for new repositories**  
   🌿 *Specifies the default branch name (`main`) for new repositories initialised with `git init`.*  
   ```bash
   git config --global init.defaultBranch main
   ```

---

## 2. Initialise a New Git Repository

4. **Initialise Git tracking in the current directory**  
   🚀 *Starts a new Git repository in your project folder.*  
   ```bash
   git init
   ```

5. **Stage all changes for commit**  
   ➕ *Adds all files in the current directory to the staging area.*  
   ```bash
   git add .
   ```

6. **Commit the staged changes**  
   💾 *Commits your changes with a descriptive message.*  
   ```bash
   git commit -m "commit message"
   ```
   - **Commit Best Practices:** Write clear, descriptive commit messages (e.g., "Fix login bug when user enters invalid credentials") to ensure your project history is easy to understand.

7. **Rename the current branch to `main`**  
   🔀 *Renames your branch to `main` to match modern best practices.*  
   ```bash
   git branch -M main
   ```

---

## 3. Connect to a Remote Repository

8. **Add a remote repository URL**  
   🌐 *Associates your local repository with a GitHub repository.*  
   ```bash
   git remote add origin https://github.com/username/repo-name.git
   ```

9. **Pull changes from the remote repository**  
   ⬇️ *Synchronises your local repository with changes from the remote.*  
   ```bash
   git pull origin main
   ```

10. **Push your commits to GitHub**  
    ⬆️ *Uploads your local commits to the remote repository.*  
    ```bash
    git push -u origin main
    ```

---

## 4. Advanced Git Operations: Merging, Resolving Conflicts, and Stashing

11. **Merge a branch into the current branch**  
    🔀 *Merges changes from another branch into your current branch.*  
    ```bash
    git merge <branch-name>
    ```
    - *Example:* Merging a feature branch (`feature/login-page`) into `main` so that the new login functionality becomes part of your current code.

12. **Resolve merge conflicts**  
    🛠️ *When conflicts occur, open the affected files, manually resolve sections marked by `<<<<<<<`, `=======`, and `>>>>>>>`, then stage and commit changes:*  
    ```bash
    git add <file-name>
    git commit -m "Resolved merge conflict in <file-name>"
    ```

13. **Stash your changes temporarily**  
    📦 *Saves your modified tracked files without making a commit (useful if you need a clean working directory).*  
    ```bash
    git stash
    ```
    - To see your stashed changes:
      ```bash
      git stash list
      ```
    - To reapply the most recent stashed changes:
      ```bash
      git stash pop
      ```

---

## 5. Delete a Local Git Repository

Before deletion, **navigate to your project's root folder**.

### For Linux/macOS:
14. **Remove the `.git` folder**  
    🗑️ *Deletes all Git tracking data from the current project.*  
    ```bash
    rm -fr .git
    ```

### For Windows:
15. **Remove the `.git` folder**  
    🗑️ *Deletes all Git tracking data from the current project directory.*  
    ```cmd
    rmdir /s .git
    ```

16. **Verify deletion from the local repository**  
    🔍 *Should display an error indicating absence of Git tracking (not a Git repository).*  
    ```bash
    git status
    ```
    *Expected output: `fatal: not a git repository (or any of the parent directories): .git`*

17. **(Optional) Reinitialise a new Git repository**  
    🚀 *Creates a fresh Git repository, if needed.*  
    ```bash
    git init
    ```

---

## 6. Delete a Remote Git Repository on GitHub

Follow these steps on GitHub.com:

18. **Navigate to the repository's main page.**

19. **Click the "Settings" tab**  
    ⚙️ *If the "Settings" tab is hidden, check the dropdown menu for it.*

20. **Scroll to the "Danger Zone" and select "Delete this repository."**

21. **Read the warnings carefully.**

22. **Confirm deletion by typing the repository name in the confirmation box.**

23. **Click "I understand the consequences, delete this repository."**

_For more details, see [GitHub's documentation on deleting a repository](https://docs.github.com/en/repositories/creating-and-managing-repositories/deleting-a-repository)._

---

## 7. Git Workflows

Understanding Git workflows can help tailor your process for different project needs. Here are common models with real-world examples:

- **Centralised Workflow:**  
  *All team members commit directly to a single central repository.*  
  - **Example:** A small startup where everyone pushes changes directly to the `main` branch of a central repository.
  
- **Feature Branch Workflow:**  
  *Develop new features in separate branches and merge into the main branch only when features are tested and complete.*  
  - **Example:** In a web application, developers create branches like `feature/user-authentication` or `feature/payment-integration` and later merge them into `main` after code review.
  
- **Forking Workflow:**  
  *Contributors fork the main repository, make changes in their own copy, and then submit pull requests to merge into the original repository.*  
  - **Example:** In an open-source project, external contributors fork the repo on GitHub, work on their feature branch, and create a pull request for review by the project maintainers.
  
- **Pull Request Workflow:**  
  *Often combined with feature branches; team members submit pull requests for their changes, which are then reviewed and merged by peers or maintainers.*  
  - **Example:** A large enterprise project where every change is subjected to code review via a pull request before merging into the central repository.

_Select the workflow that fits your team size and the complexity of your project._

---

## 8. Branching Strategies

Effective branching strategies help maintain a clean project history. Consider the following real-world strategies:

- **Feature Branching:**  
  *Create individual branches for new features.*  
  - **Example:** Create a branch named `feature/shopping-cart` when building an e-commerce app, and merge only after thorough testing.
  
- **Release Branching:**  
  *Maintain a branch dedicated to preparing for a new release.*  
  - **Example:** For a mobile app, maintain a `release/v2.0` branch to fix final bugs and prepare documentation before the official release.
  
- **Hotfix Branching:**  
  *Quickly address critical issues on the production branch without disrupting ongoing development.*  
  - **Example:** If a critical bug is found in production, create a `hotfix/critical-bug` branch to apply a fast patch and merge it back into both `main` and the development branch.
  
- **Trunk-Based Development:**  
  *Develop directly on a single branch (usually `main`) with small, frequent commits that are continuously integrated.*  
  - **Example:** In a continuous delivery environment, developers commit small changes directly to `main` while automated tests ensure stability.

_These strategies can be tailored to your project's size, release cadence, and team workflow._

---

## 9. Graphical Interfaces

For those who prefer visual tools, consider the following graphical Git clients:

- **[GitHub Desktop](https://desktop.github.com):** A simple interface for managing your repositories.  
- **[SourceTree](https://www.sourcetreeapp.com):** A robust client that supports Git and Mercurial with powerful visualization tools.  
- **[GitKraken](https://www.gitkraken.com):** Offers an intuitive visual interface for branch management, merging, and conflict resolution.

---

## 10. Using Git in Team Collaboration

Collaborating in a team often means coordinating multiple remotes and ensuring everyone’s work is properly integrated. Here are some steps and tips for effective team collaboration:

1. **Forking vs. Shared Repository:**  
   - For small teams, use a shared repository where each collaborator has push access.  
   - For open-source or larger projects, use the forking model where each contributor works on their own copy and then submits pull requests.

2. **Adding Multiple Remotes:**  
   If you need to add a second remote (for example, to collaborate with another team or to sync with a backup repository), use:  
   ```bash
   git remote add collaborator https://github.com/otheruser/repo-name.git
   ```
   - *Use `git remote -v` to verify the list of remotes.*

3. **Coordinating Changes:**  
   - **Regular Pulls:** Always run `git pull origin main` before pushing any changes to avoid conflicts.  
   - **Peer Reviews:** Use pull requests and code review to improve code quality and maintain consistency across the team.
  
4. **Communication and Issue Tracking:**  
   - Use GitHub Issues, project boards, and discussion threads to track tasks and coordinate development efforts.
  
5. **Real World Example:**  
   - In a collaborative project, one developer pushes changes to `main` and another collaborator, working on a feature branch, regularly syncs their branch with `main`. Upon completion, a pull request is submitted, reviewed, and merged by a team lead ensuring that integration is smooth and conflicts are resolved rapidly.

---

## 11. Common Troubleshooting Tips for Git Beginners

- **Merge Conflicts:**  
  If you encounter conflicts, review markers (`<<<<<<<`, `=======`, `>>>>>>>`), resolve conflicts manually, then run:
  ```bash
  git add <file-name>
  git commit -m "Resolved merge conflict in <file-name>"
  ```
  
- **Detached HEAD:**  
  If you find yourself in a detached HEAD state, create a branch from your current commit:
  ```bash
  git checkout -b <new-branch-name>
  ```
  
- **Accidental Commits:**  
  To undo a commit while keeping your changes staged:
  ```bash
  git reset --soft HEAD~1
  ```
  
- **Lost Changes:**  
  If you lose work after a hard reset or merge, use:
  ```bash
  git reflog
  ```
  to identify and recover commits. Then use:
  ```bash
  git checkout <commit-hash>
  ```
  
- **Not a Git Repository Error:**  
  Ensure you're operating within the project's root where Git tracking exists. Running:
  ```bash
  git status
  ```
  outside a Git-managed folder will return an error.

---

## Contributing
Contributions to improve or expand this guide further is welcome!
