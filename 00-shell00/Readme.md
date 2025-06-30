# Notes

 You must not leave any additional files in your directory other than those specified in the assignment. 

The terminal is just another interface to perform actions on your machine.

**Directory** means folder.

---

### Basic Navigation & File Management

* `pwd` - **p**rint **w**orking **d**irectory -> displays the directory (or folder) you're currently in.
* **`cd` - change directory**
    * `cd ..` -> Go back one directory.
    * `cd ../..` -> Go back two directories.
* **`ls` - list files and directories**
    * `ls -l` -> List in long format, showing details like permissions, owner, size, and modification date.
    *  `ls -Ftm` -> Lists files with a `/` appended to directories, sorts them by modification time (`t`), and separates them with a comma and space (`m`). 
* **`mv <source> <destination>` - move or rename files**
    * `mv Readme.txt folder1` -> Moves `Readme.txt` into `folder1`.
    * You can move multiple files: `mv file1 file2 file3 folder1`
* **`cp <source> <destination>` - copy files**
    * `cp -r folder1 folder3` -> Copies the `folder1` directory recursively into `folder3`. The `-r` is necessary for copying folders.

**Pro Tip:** Use the `Tab` key to auto-complete file and folder names in the terminal.

---

### File Creation & Manipulation

1.  **`touch <filename>`**
    * Creates a new, empty file.
    * Example: `touch my_new_file`

2.  **`echo "some text" > <filename>`**
    * Creates a file and writes text into it. If the file exists, it will be overwritten.
    * `echo "" > test3` creates a file that isn't empty because it contains a newline character.

3.  **`mkfile <size> <filename>`**
    * Creates a file of a specific size.
    * Example: `mkfile 25b test` (creates a 25-byte file).

---

### Links

* **Soft Link (Symbolic Link)**: A shortcut to another file or directory.
    * `ln -s /path/to/original /path/to/link`
    *  Example: `ln -s test0 test6` creates a link `test6` that points to `test0`. 

* **Hard Link**: A new name for an existing file. Both names point to the same data on the disk.
    * `ln /path/to/file /path/to/hardlink`
    *  Example: `ln test3 test5` means `test3` and `test5` are essentially the same file. 

---

### Timestamps

* **`touch -t <YYYYMMDDhhmm.ss> <filename>`**
    * Changes the modification and access time of a file.
    * ss is optional
    * `touch -h -t <YYYYMMDDhhmm.ss> <linkname>` -> The `-h` flag modifies the timestamp of a symbolic link itself, not the file it points to.
    *  Example: `touch -t 202406012047 test0` 

---

### File Permissions (`chmod`)

Permissions are set for three classes of users: **u**ser (owner), **g**roup, and **o**thers.

Permissions can be represented by numbers:
* **4** -> **r**ead (r)
* **2** -> **w**rite (w)
* **1** -> **e**xecute (x)

You add the numbers to combine permissions. For example, `rwx` would be `4+2+1=7`.

**Example:** `chmod 755 <filename>`
* **Owner**: `7` (4+2+1) -> `rwx`
* **Group**: `5` (4+0+1) -> `r-x`
* **Others**: `5` (4+0+1) -> `r-x`

---

### SSH Keys

Secure Shell (SSH) keys are used for secure authentication.

* **Generate a new SSH key:**
    ```bash
    ssh-keygen
    ```
* **View your public key:**
    *  This is the key you add to services like GitHub to grant access. 
    ```bash
    cat ~/.ssh/id_rsa.pub
    ```
 **Important**: Never share your private key (`id_rsa`). 

---

### Git Commands

* **`git clone <repository_url>`**
    * Downloads a repository from a remote source (like GitHub) to your local machine.

* **`git add <file>`**
    * Adds a specific file to the staging area, preparing it for the next commit.

* **`git add .`**
    * Adds all new and modified files in the current directory and subdirectories to the staging area.

* **`git commit -m "Your commit message"`**
    * Saves the staged changes to the repository's history with a descriptive message.

* **`git push`**
    * Uploads your local commits to the remote repository.

* **`git log --oneline -5`**
    * A way to view the last 5 commits, showing just the commit ID and message.  A similar command would be needed for the `git_commit.sh` script. 

* **`git rm --cached <file>`**
    * Removes a file from the staging area (untracks it) but keeps the actual file in your directory. Useful for files that were added by mistake and should be in your `.gitignore`.
