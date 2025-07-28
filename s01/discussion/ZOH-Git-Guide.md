# ZOH S01 - Git Basics Guide

## Set up SSH Key

### 1. Generate an SSH key (you only need to do this once per device).
#### Desktop > Git Bash Terminal

```
ssh-keygen -t rsa
```

#### Note:
- After running the command, you will be prompted to choose a file location to store the SSH key on your device. **Just press Enter to use the default location**.
- You’ll also be prompted to set a passphrase, which acts like a password for your SSH key. **Press Enter again to leave the passphrase empty for easier access** (though setting a passphrase is more secure).

### 2. Copy your SSH public key to the clipboard.
#### Desktop > Git Bash Terminal

**Windows:**
```
cat ~/.ssh/id_rsa.pub | clip
```

**Mac:**
```
pbcopy < ~/.ssh/id_rsa.pub
```

**Linux:**
```
xclip -sel clip < ~/.ssh/id_rsa.pub
```

### 3. Add the generated SSH key to your GitHub account.
#### https://github.com/settings/keys

#### a. Click "New SSH key".
#### b. Set a Title (e.g., "My Laptop" or "Work PC").
#### c. Paste your copied SSH public key into the Key field.
#### d. Click Add SSH key.

## Configure Git Identity

### Set up your Git credentials (you only need to do this once per device).
#### Desktop > Git Bash Terminal

#### 1. Configure the global Git email:
```
git config --global user.email "your-email@example.com"
```

#### 2. Configure the global Git username:
```
git config --global user.name "git account username"
```

#### 3. Verify your Git configuration:
```
git config --global --list
```

## Creating `fcb-zoh` GitHub Repository

#### 1. Go to https://github.com/new
#### 2. In the Repository name field, enter `fcb-zoh`
#### 3. Leave the other settings at their default
#### 4. Click "Create repository"

## Git commands to upload files from your local repository (PC) to a remote repository (GitHub)

### 1. Open a Git Bash terminal inside your "open-house" folder.
#### Documents > open-house > Git Bash Terminal

### 2. Initialize a local Git repository (you only need to do this once).
#### Documents > open-house > Git Bash Terminal

```
git init
```

### 3. Stage files for commit.
#### Documents > open-house > Git Bash Terminal

**To stage a specific file**
```
git add [filename]
```

**To stage all files:**
```
git add .
```
or
```
git add -A
```
 
### 4. Commit the staged files.
#### Documents > open-house > Git Bash Terminal

```
git commit -m "initial commit"
```

#### Note:
- "initial commit" is commonly used to label the first commit of a project.
- Future commit messages should clearly describe the changes made.
	- Example: `git commit -m "added text to discussion.txt file".`

### 5. Connect the local repository to the remote repository (you only need to do this once).

#### a. In your GitHub `fcb-zoh` repository, under `Quick Setup`, select `SSH` and copy the `SSH clone URL` (you only need to do this once).

#### b. In the terminal, run:
#### Documents > open-house > Git Bash Terminal

```
Sample:
git remote add origin your-ssh-link-here
```

### 8. Upload (push) the local repository to GitHub.
#### Documents > open-house > Git Bash Terminal
```
git push origin master
```