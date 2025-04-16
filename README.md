# Git Notes

---

## Complete Process of Adding Code to GitHub

1. Initialize a Git repository:
   ```bash
   git init
   ```

2. Add files to the staging area:
   ```bash
   git add <filename>
   ```
   or to add all files:
   ```bash
   git add .
   ```

3. Commit the changes with a message:
   ```bash
   git commit -m "Initial commit"
   ```

4. Add the remote origin URL to your local repo:
   ```bash
   git remote add origin https://github.com/username/repo-name.git
   ```

5. Push the code to the GitHub repository:
   ```bash
   git push -u origin main
   ```

---

## Git Config Settings

Git allows you to configure settings at two levels:

### 1. Repository-Level Settings
- Apply only to a specific repository.
- Useful when working with different identities across multiple projects.

### 2. Global-Level Settings
- Apply system-wide for the current user.
- Ideal for setting a default identity for all repositories.

### Common Git Config Commands:
Set your global user name and email:
```bash
git config --global user.name "Ronnie Coleman"
git config --global user.email "example@email.com"
```

- These commands store your identity in the global Git configuration file.
- Git uses this info to associate commits with your name/email.
- The `--global` flag makes this the default for all repositories.

---

## Creating a Repository-Level Configuration

1. Check Git status:
   ```bash
   git status
   ```
    *Note: If no Git repository exists in the directory, you'll get an error like:*
   ```
   fatal: not a git repository (or any of the parent directories): .git
   ```

2. Initialize a Git repository:
   ```bash
   git init
   ```

---

## Code Staging

1. Initialize a Git repository:
   ```bash
   git init
   ```

2. Add files to the staging area:
   ```bash
   git add <filename>
   ```
   or:
   ```bash
   git add .
   ```

3. Check the status:
   ```bash
   git status
   ```
   - Staged files are ready to be committed.

---

## Commit Files

1. Stage the files:
   ```bash
   git add <filename>
   ```
   or:
   ```bash
   git add .
   ```

2. Commit with a message:
   ```bash
   git commit -m "Your message here"
   ```

   or simply:
   ```bash
   git commit
   ```
   *(opens the default editor to write a commit message)*

---

## Repository Logs

- View full commit logs:
  ```bash
  git log
  ```

- View concise commit history (oneline format):
  ```bash
  git log --oneline
  ```

---

## .gitignore File

- `.gitignore` specifies which files or directories should be **ignored by Git**.
- Useful for excluding:
  - Temporary files
  - Build artifacts
  - Environment config files
  - IDE-specific folders (like `.vscode`, `.idea`)

---

## .gitkeep File

- Git **does not track empty folders** by default.
- To include an empty directory in your repo, add a `.gitkeep` file inside it.
- This is a common convention (not an official Git feature).

---

## Git Branch

Branching allows you to create independent lines of development within your repository.

### 1. Check the Current Branch
```bash
git branch
```

### 2. Create a New Branch
```bash
git branch branch-01
```

### 3. Switch to a Branch
```bash
git switch branch-01
```
or:
```bash
git checkout branch-01
```

### 4. Create and Switch to a New Branch in One Command
```bash
git switch -c branch-02
```

---

## Merging Branches

When you're ready to bring changes from one branch into another (typically from a feature branch into `main`), use the following:

### Merge a Branch into the Current Branch
```bash
git merge <branch_name>
```

This integrates changes from `<branch_name>` into your current working branch.

### Handling Merge Conflicts

Sometimes, Git can’t automatically merge changes due to conflicts (e.g., edits on the same line).

#### Two Ways to Resolve Merge Conflicts:

### 1. Manual Resolution
- Run the merge command.
- Open the conflicted file.
- Manually remove the conflict markers (`<<<<<<<`, `=======`, `>>>>>>>`).
- Edit to resolve the differences.
- Save the file.
- Add and commit:
  ```bash
  git add <file>
  git commit -m "Resolved merge conflict"
  ```

### 2. Automated Resolution Using VS Code
- Run the merge command.
- Open the conflicted file in VS Code.
- Use the UI options (e.g., "Accept Current Change", "Accept Incoming Change", or both).
- Save the file.
- Add and commit:
  ```bash
  git add <file>
  git commit -m "Resolved merge conflict using VS Code"
  ```

---
