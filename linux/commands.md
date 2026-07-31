# Linux Command Reference 
This document contains Linux commands that I have personally used while learning software engineering. Each entry includes the command's purpose, syntax, examples from my own practice, common mistakes, and additional notes for future reference.

**Last Updated**: July 2026

## Table of Contents

- File & Directory Commands
- Developer Environment Setup
- Linux Symbols
- Common Flags
- Development Workflow

## File & Directory Commands

### `mkdir`

#### Purpose
Creates a new directory (folder).

#### Syntax
```bash
mkdir <folder_name>
```

#### Example
```bash
mkdir software-engineering-journey
```

#### When I Actually Used It
- Created the `software-engineering-journey` project directory.
- Created subdirectories such as `linux`, `git`, `cpp`, `dsa`, `python`, `notes`, `journal`, and `resources`.

#### Common Mistakes
- Running `mkdir` on an existing directory gives an error.
- If parent directories don't exist, use `mkdir -p` instead.

#### Special Notes
- Creates one directory at a time.

---

### `mkdir -p`

#### Purpose
Creates parent directories if they don't already exist.

#### Syntax
```bash
mkdir -p <path>
```

#### Example
```bash
mkdir -p ~/Developer
```

#### When I Actually Used It
Created the `Developer` directory under my home folder before organizing all my programming projects.

#### Common Mistakes
- Forgetting to use `-p` when creating nested directories whose parent folders don't exist.

#### Special Notes
- `-p` stands for **parents**.
- Does nothing if the directory already exists.

---

### `cd`

#### Purpose
Changes the current working directory.

#### Syntax
```bash
cd <directory>
```

#### Examples
```bash
cd ~/Developer
cd software-engineering-journey
cd linux
cd ..
```

#### When I Actually Used It
Navigated between my project folders while creating directories and practicing Linux commands.

#### Common Mistakes
- Trying to enter a directory that doesn't exist.
- Forgetting that `cd ..` moves one directory up.

#### Special Notes
- `cd ..` → Parent directory.
- `cd ~` → Home directory.

---

### `pwd`

#### Purpose
Displays the current working directory.

#### Syntax
```bash
pwd
```

#### Example
```bash
pwd
```

#### Output Example
```text
/home/kpmohan/Developer/software-engineering-journey
```

#### When I Actually Used It
Verified that I was inside the correct project directory before creating files and running Git commands.

#### Common Mistakes
- Assuming you're in the correct directory without checking.

#### Special Notes
- Very useful before deleting files or executing Git commands.

---

### `ls`

#### Purpose
Lists files and directories.

#### Syntax
```bash
ls
```

#### Example
```bash
ls
```

#### Output Example
```text
README.md cpp dsa git journal linux notes python resources
```

#### When I Actually Used It
Checked whether my files and folders had been created successfully.

#### Common Mistakes
- Thinking hidden files are missing. `ls` only shows visible files.

#### Special Notes
- Use `ls -la` to view hidden files.

---

### `ls -la`

#### Purpose
Lists all files, including hidden files, with detailed information.

#### Syntax
```bash
ls -la
```

#### Example
```bash
ls -la
```

#### When I Actually Used It
Verified hidden directories like `.git` and `.vscode` after setting up my project.

#### Common Mistakes
- Forgetting that files beginning with `.` are hidden.

#### Special Notes
- `-l` → Long listing format.
- `-a` → Show all files, including hidden ones.

---

### `tree`

#### Purpose
Displays the directory structure as a tree.

#### Syntax
```bash
tree
```

#### Example
```bash
tree
```

#### When I Actually Used It
Verified the structure of my `software-engineering-journey` repository after creating folders.

#### Common Mistakes
- Forgetting to install the `tree` package before using it.

#### Special Notes
- Install it using:
```bash
sudo apt install tree
```

---

### `touch`

#### Purpose
Creates an empty file.

#### Syntax
```bash
touch <filename>
```

#### Examples
```bash
touch day01.txt
touch commands.txt
touch commands.md
```

#### When I Actually Used It
Created practice files before learning how to rename, copy, and delete them.

#### Common Mistakes
- Expecting `touch` to add content to a file. It only creates an empty file.

#### Special Notes
- If the file already exists, only its timestamp is updated.

---

### `mv`

#### Purpose
Moves or renames files and directories.

#### Syntax
```bash
mv <source> <destination>
```

#### Example
```bash
mv day01.txt lesson01.txt
```

#### When I Actually Used It
Renamed `day01.txt` to `lesson01.txt`.

#### Common Mistakes
- Accidentally overwriting another file with the same name.
- Confusing `mv` with `cp`.

#### Special Notes
- Can both move and rename files.

---

### `cp`

#### Purpose
Copies files or directories.

#### Syntax
```bash
cp <source> <destination>
```

#### Example
```bash
cp lesson01.txt backup.txt
```

#### When I Actually Used It
Created `backup.txt` as a backup copy before practicing file deletion.

#### Common Mistakes
- Forgetting to use `-r` while copying directories.

#### Special Notes
- Original file remains unchanged after copying.

---

### `rm`

#### Purpose
Deletes files.

#### Syntax
```bash
rm <filename>
```

#### Example
```bash
rm backup.txt
```

#### When I Actually Used It
Deleted `backup.txt` after confirming that the `cp` command worked correctly.

#### Common Mistakes
- `rm` permanently deletes files.
- Always verify the filename before pressing **Enter**.
- To delete directories, use `rm -r`.

#### Special Notes
- Files deleted with `rm` do not go to the Recycle Bin.

---

### `cat`

#### Purpose
Displays the contents of a file.

#### Syntax
```bash
cat <filename>
```

#### Example
```bash
cat ~/.ssh/id_ed25519.pub
```

#### When I Actually Used It
Displayed my SSH public key so I could copy it into GitHub.

#### Common Mistakes
- Opening the private key (`id_ed25519`) instead of the public key (`id_ed25519.pub`).

#### Special Notes
- Best suited for viewing small text files quickly.

---

## Linux Symbols Used

| Symbol | Meaning | Example |
|---------|---------|---------|
| `~` | Home directory | `cd ~/Developer` |
| `..` | Parent directory | `cd ..` |
| `.` | Current directory | `git add .` |
| `/` | Directory separator | `/home/kpmohan/Developer` |

---

## Common Flags Used

| Flag | Command | Meaning | Example |
|------|---------|---------|---------|
| `-p` | `mkdir` | Create parent directories | `mkdir -p ~/Developer` |
| `-l` | `ls` | Long listing format | `ls -la` |
| `-a` | `ls` | Show hidden files | `ls -la` |
| `-y` | `apt install` | Automatically answer "Yes" | `sudo apt install ... -y` |
| `--version` | Various commands | Display installed version | `python3 --version` |
| `-t` | `ssh-keygen` | Specify key type | `-t ed25519` |
| `-C` | `ssh-keygen` | Add a comment | `-C "email@example.com"` |
| `-T` | `ssh` | Disable terminal allocation | `ssh -T git@github.com` |

---

## Development Workflow

```text
Learn
   ↓
Practice
   ↓
Write Notes
   ↓
Git Commit
   ↓
Git Push
```

Every study session should end by documenting what was learned, committing the changes to Git, and pushing them to GitHub. This creates a consistent learning history and a well-maintained personal knowledge base.