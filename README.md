# Project Setup and Upload to Github

This guide explains how to set up a project and upload it to GitHub for both your personal and student accounts. It includes the necessary steps to configure your repository, manage SSH keys, and handle multiple GitHub accounts.


<!-- ## TABLE OF CONTENT -->

## 1. Initialize a New Git Repository

- Navigate to the project directory in your terminal:

```bash
cd <your-project-directory>
``` 

- Initialize a Git repository:
```bash
git init
```

- This creates a .git folder to track changes in your project.

### 2. Set Your Git Username and Email

- Personal Account:
```bash
git config user.name "YourPersonalName"
git config user.email "yourpersonalemail@example.com"
```
- Student Account:
```bash
git config user.name "YourStudentName"
git config user.email "yourstudentemail@example.com"
```
***Note: Use --global if you want to set these details for all repositories. Otherwise, omit --global to set them only for this specific project***

### 3. Add Files to Git

>To stage files for a commit, use the following command:

- Add a specific file:
``` bash
git add <file-name>
```

- Add all files in the directory:

```bash
git add .
```

### 4. Commit Changes
- Save your changes with a commit message:
```bash
git commit -m "Initial commit"
```

### 5.Create a Repository on GitHub
1. Log in to your GitHub account (personal or student).
2. Create a new repository with a name matching your project.
3. Do not initialize the repository with a README file (you’ll add yours later).

### 6. Set Up the Remote Repository
Copy the repository’s SSH URL from GitHub. It should look like this:
- Personal Account:

```bash
git@github.com:YourPersonalUsername/<repo-name>.git
```

- Student Account:

```bash
git@github.com-student:YourStudentUsername/<repo-name>.git
```

- Add remote repository

```bash
git remote add origin <your-ssh-url>
```

- Verify the remote:

```bash
git remote -v
```
### 7. Push Changes to GitHub
Push your changes to the main branch:

```bash
git push -u origin main
```
If your default branch is *master*, replace *main* with *master*.

### 8. Verify the Push
Go to your GitHub repository page and ensure all files, including the **README.md** , have been uploaded.

### 9. Managing SSH Keys for Multiple Accounts
- If you’re using multiple GitHub accounts (personal and student), configure your SSH keys and ~/.ssh/config file as follows:

Generate SSH Keys for Each Account
- Personal:

```bash
ssh-keygen -t ed00000 -C "yourpersonalemail@example.com"
```

- Student:
```bash
ssh-keygen -t ed00000 -C "yourstudentemail@example.com"
``` 
Edit the ***~/.ssh/config*** File

```plaintext
# Personal GitHub Account
Host github.com
    HostName github.com
    User git
    IdentityFile ~/.ssh/id_ed00000

# Student GitHub Account
Host github.com-student
    HostName github.com
    User git
    IdentityFile ~/.ssh/id_ed00000_student
```

Test the SSH Connection
- Personal:

```bash
ssh -T git@github.com
```

Student:

```bash
ssh -T git@github.com-student
```

*You should see a success message for both accounts.*

Example Project Structure
```plaintext
<project-directory>
├── README.md
├── test.py
└── other-files
```
- Follow this guide to manage projects for both personal and student accounts seamlessly! 🎉

> This is a blockquote.

## **License**

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

---