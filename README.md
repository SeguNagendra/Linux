# Linux - Brief Introduction

## What is Linux?
Linux is an **open-source**, **Unix-like** operating system kernel first released by **Linus Torvalds** in 1991. It's the core component of many operating system distributions.

## Key Characteristics
- 🐧 **Open Source:** Its source code is freely available, allowing anyone to view, modify, and distribute it.
- 💻 **Multi-user** system , **Multi-tasking** capabilities and **Highly customizable**
- ⚡ **Command Line Interface (CLI):** While many distros offer graphical user interfaces (GUIs), Linux is highly capable and often managed through its powerful **command line**.
- 🔒 **Security**  Generally considered more secure than many other operating systems, with robust permission-based architecture and frequent security updates.
- 🏗️ **Kernel:** At its core, Linux is a **kernel**, the essential part of the OS that manages hardware and software resources.
- **Distributions (Distros):** To make Linux user-friendly, various "distributions" bundle the Linux kernel with other software (like desktop environments, applications, and utilities). Popular examples include **Ubuntu, Fedora, Debian, and CentOS**.
- **Stability:** Known for its **reliability** and ability to run for long periods without crashing.


## Common Distributions
| Type          | Examples                          |
|---------------|-----------------------------------|
| Beginner      | Ubuntu, Linux Mint                |
| Enterprise    | RHEL, CentOS, SUSE                |
| Lightweight   | Lubuntu, Puppy Linux              |
| Rolling       | Arch Linux, Manjaro               |
| Specialized   | Kali Linux (security), Raspbian (RPi) |

## Why Use Linux?
- No licensing costs
- High stability and reliability
- Extensive software repositories
- Strong security model
- Runs on almost any hardware
- Large community support



In Linux, the **File System Hierarchy Standard (FHS)** defines the directory structure and the content of those directories. It ensures a consistent layout across different Linux distributions, making it easier for users and software to find files. Everything in Linux is treated as a file, and the file system starts from the **root directory (`/`)**.

---

# Linux File System Hierarchy

The Linux file system follows the Filesystem Hierarchy Standard (FHS). Below is a common structure of the root ( `/` ) directory:



### Key Directories and Their Purpose:

Here's a breakdown of the most common and important directories in the Linux file system:

* **`/` (Root Directory):**
    * The top-level directory of the entire file system hierarchy.
    * All other directories and files are located under the root directory.

* **`/bin` (Binaries):**
    * Contains essential user command binaries (e.g., `ls`, `cp`, `mv`, `cat`).
    * These commands are available to all users.

* **`/boot` (Boot):**
    * Contains files required to boot the operating system (e.g., kernel images, GRUB bootloader files).
    * **Do not modify files here unless you know what you are doing, as it can render your system unbootable.**

* **`/dev` (Devices):**
    * Contains device files representing hardware devices (e.g., hard drives, USB devices, terminals).
    * These are not actual files but interfaces to device drivers.

* **`/etc` (Etcetera):**
    * Contains system-wide configuration files (e.g., network configurations, user passwords, service configurations).
    * These files are typically text files and can be edited to customize system behavior.

* **`/home` (Home Directories):**
    * Contains the personal directories for regular users.
    * Each user typically has their own subdirectory (e.g., `/home/username`) where they store their documents, downloads, and personal configurations.

* **`/lib` (Libraries):**
    * Contains essential shared libraries required by the binaries in `/bin` and `/sbin`.
    * These libraries are crucial for many programs to run.

* **`/media` (Removable Media):**
    * Mount point for removable media devices such as USB drives, CDs, and DVDs.
    * When you plug in a USB stick, it's often mounted here.

* **`/mnt` (Mount):**
    * A temporary mount point for mounting file systems manually (e.g., network shares, other partitions).

* **`/opt` (Optional):**
    * Contains optional software packages and third-party applications not part of the standard system.
    * Often used for commercial or proprietary software.

* **`/proc` (Processes):**
    * A virtual file system that provides information about running processes and kernel parameters.
    * Files here are generated on the fly and contain real-time system data.

* **`/root` (Root User's Home Directory):**
    * The home directory for the `root` (administrator) user.
    * Separate from `/home` to ensure the root user's files are accessible even if `/home` is on a separate partition and becomes unavailable.

* **`/run` (Run-time Data):**
    * Contains volatile run-time data.
    * Data in this directory is typically created and deleted during system boot and shutdown.

* **`/sbin` (System Binaries):**
    * Contains essential system binaries used for system administration (e.g., `fdisk`, `reboot`, `ifconfig`).
    * These commands are typically only accessible to the root user or require `sudo` privileges.

* **`/srv` (Services Data):**
    * Contains site-specific data served by the system (e.g., web server data for Apache or Nginx).

* **`/sys` (System Files):**
    * A virtual file system providing an interface to the kernel and device drivers.
    * Allows access to hardware information and configuration.

* **`/tmp` (Temporary):**
    * Contains temporary files created by applications and users.
    * Files in this directory are often deleted on system reboot.

* **`/usr` (Unix System Resources):**
    * Contains shareable, read-only data (user programs and utilities).
    * Often the largest directory on a Linux system.
    * **`/usr/bin`**: Most user commands.
    * **`/usr/lib`**: Libraries for programs in `/usr/bin`.
    * **`/usr/local`**: Locally installed software, often compiled from source.
    * **`/usr/sbin`**: Non-essential system administration binaries.
    * **`/usr/share`**: Architecture-independent data (e.g., documentation, icons).

* **`/var` (Variable Data):**
    * Contains variable data files that change frequently during system operation.
    * Examples include log files, mail queues, and temporary files that persist across reboots.
    * **`/var/log`**: System and application log files.
    * **`/var/www`**: Default location for web server content on some distributions.


---
# Editing Files with VIM Text Editor

Vim (Vi IMproved) is a highly configurable and efficient text editor that is ubiquitous in the Linux environment. While it has a steep learning curve due to its modal editing nature, mastering Vim can significantly boost productivity for developers, system administrators, and anyone who frequently works with text files.

## Understanding Vim's Modes

Vim operates in different "modes," which determine how your keystrokes are interpreted. This is the fundamental concept to grasp when using Vim.

1.  **Normal Mode (Command Mode):**
    * This is the default mode when you open Vim.
    * Used for navigation, deleting text, copying, pasting, and executing commands.
    * **You cannot directly type text in this mode.**
    * Press `Esc` to return to Normal mode from any other mode.

2.  **Insert Mode:**
    * Used for inserting and editing text.
    * To enter Insert mode from Normal mode, press:
        * `i` (insert at current cursor position)
        * `a` (append after current cursor position)
        * `o` (open new line below current line)
        * `I` (insert at the beginning of the current line)
        * `A` (append at the end of the current line)
        * `O` (open new line above current line)

3.  **Visual Mode:**
    * Used for selecting blocks of text, similar to highlighting with a mouse.
    * Once text is selected, you can perform actions like copying, deleting, or changing it.
    * To enter Visual mode from Normal mode, press:
        * `v` (character-wise visual selection)
        * `V` (line-wise visual selection)
        * `Ctrl + v` (block-wise visual selection)

4.  **Command-Line Mode (Ex Mode):**
    * Used for executing commands that modify the file, search/replace, save, quit, etc.
    * To enter Command-Line mode from Normal mode, press `:` (colon).
    * You'll see a colon prompt at the bottom of the screen.

---

### Basic Vim Operations

#### 1. Opening a File

To open a file in Vim from your terminal:

```bash
vim filename.txt
```
If `filename.txt` doesn't exist, Vim will create a new empty file with that name when you save it.

#### 2\. Navigating in Normal Mode

*    **`h`**: Move cursor left
*    **`j`**: Move cursor down
*    **`k`**: Move cursor up
*    **`l`**: Move cursor right
*    **`w`**: Move cursor to the beginning of the next word
*    **`b`**: Move cursor to the beginning of the previous word
*    **`e`**: Move cursor to the end of the current word
*    **`0` (zero)**: Move cursor to the beginning of the current line
*    **`$`**: Move cursor to the end of the current line
*    **`gg`**: Go to the first line of the file
*    **`G`**: Go to the last line of the file
*    **`lineNumberG`**: Go to a specific line number (e.g., `5G` to go to line 5)
*    **`Ctrl + f`**: Page down
*    **`Ctrl + b`**: Page up

#### 3\. Editing Text (After entering Insert Mode)

Once you've entered Insert mode (by pressing `i`, `a`, `o`, etc.):

*    Type text as you normally would.
*    Use `Backspace` or `Delete` to remove characters.
*    **Press `Esc` to return to Normal mode** when you're done inserting text. This is crucial!

#### 4\. Deleting Text in Normal Mode

*    **`x`**: Delete character under the cursor
*    **`dw`**: Delete from cursor to the end of the current word
*    **`dd`**: Delete the entire current line
*    **`d$`**: Delete from cursor to the end of the current line
*    **`d0`**: Delete from cursor to the beginning of the current line
*    **`D`**: Delete from cursor to the end of the current line (same as `d$`)
*    **`ndd`**: Delete `n` number of lines (e.g., `5dd` to delete 5 lines)

#### 5\. Copying (Yanking) and Pasting in Normal Mode

*    **`yy`**: Copy (yank) the current line
*    **`yw`**: Copy (yank) from cursor to the end of the current word
*    **`y$`**: Copy (yank) from cursor to the end of the current line
*    **`nyy`**: Copy `n` number of lines (e.g., `3yy` to copy 3 lines)
*    **`p`**: Paste after the cursor (or below the current line if a line was copied)
*    **`P`**: Paste before the cursor (or above the current line if a line was copied)

#### 6\. Undo and Redo

*    **`u`**: Undo the last change
*    **`Ctrl + r`**: Redo the last undone change

#### 7\. Saving and Quitting (Command-Line Mode)

From Normal mode, press `:` to enter Command-Line mode:

*    **`:w`**: Save the file
*    **`:q`**: Quit Vim (only if there are no unsaved changes)
*    **`:wq`**: Save and quit
*    **`:x`**: Save and quit (similar to `:wq`)
*    **`:q!`**: Quit without saving (discard all changes)
*    **`:wqa`**: Save and quit all open buffers (if multiple files are open)

#### 8\. Search and Replace (Command-Line Mode)

From Normal mode, press `:` to enter Command-Line mode:

*    **`/pattern`**: Search forward for `pattern`. Press `n` for next match, `N` for previous.
*    **`?pattern`**: Search backward for `pattern`. Press `n` for next match, `N` for previous.
*    **`:%s/old/new/g`**: Replace all occurrences of `old` with `new` throughout the entire file.* *   `%`: Search the entire file.
*    **`s`**: Substitute command.
*    **`g`**: Global (replace all occurrences on each line).
*    **`:%s/old/new/gc`**: Replace all occurrences of `old` with `new`, with confirmation for each change **`c`**: Confirm before replacing.


### A Typical Workflow Example

1.   **Open the file:** `vim my_document.txt`
1.   **Navigate** to the section you want to edit (e.g., `G` to go to the end, `k` to move up a line).
1.   **Press `i`** to enter Insert mode.
1.   **Type** your changes.
1.   **Press `Esc`** to return to Normal mode.
1.   **Navigate** to another part of the file.
1.   **Press `dd`** to delete an unwanted line.
1.   **Press `yy`** to copy a line, then `p` to paste it somewhere else.
1.   **Press `:`** to enter Command-Line mode.
1.   **Type `wq`** and press `Enter` to save and quit.

---

In Linux, **environment variables** are dynamic named values that can affect the way running processes behave. They are part of the environment in which a process runs and are used by programs to store configuration information, paths, and other data that applications might need.

---

### What are Environment Variables?

Think of environment variables as a set of key-value pairs that the operating system makes available to any program or script you run. For instance:

* A program might look for an environment variable named `PATH` to know where to find executable commands.
* A web server might use `PORT` to determine which network port to listen on.
* Your shell might use `PS1` to customize the appearance of your command prompt.

---

### Types of Environment Variables

There are generally two types of environment variables:

1.  **System-wide Environment Variables:**
    * Set for all users and all shells on the system.
    * Typically configured in files like `/etc/profile`, `/etc/environment`, or within `/etc/profile.d/` scripts.
    * Require root privileges to modify.

2.  **User-specific Environment Variables:**
    * Set for a particular user and typically apply only to their shell sessions.
    * Configured in files within the user's home directory, such as `~/.bashrc`, `~/.bash_profile`, `~/.profile`, or `~/.zshrc` (depending on the shell).

---

### Common Environment Variables

Here are some of the most frequently encountered environment variables in Linux:

* **`PATH`**:
    * A colon-separated list of directories where the shell looks for executable commands.
    * When you type a command like `ls` or `vim`, the shell searches these directories in order.
    * Example: `/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin`

* **`HOME`**:
    * The absolute path to the current user's home directory.
    * Example: `/home/yourusername`

* **`USER`** / **`LOGNAME`**:
    * The username of the current logged-in user.

* **`SHELL`**:
    * The path to the default login shell for the current user.
    * Example: `/bin/bash` or `/bin/zsh`

* **`LANG`**:
    * Sets the default locale for language and character encoding settings.
    * Example: `en_US.UTF-8`

* **`TERM`**:
    * Defines the type of terminal emulation currently in use.
    * Example: `xterm-256color`

* **`PWD`**:
    * The absolute path of the current working directory.

* **`OLDPWD`**:
    * The absolute path of the previous working directory.

* **`PS1`**:
    * The primary prompt string that defines the appearance of your shell prompt.
    * Highly customizable.

* **`EDITOR`** / **`VISUAL`**:
    * Specifies the default text editor to be used by various programs.
    * Example: `vim` or `nano`

---

### How to Work with Environment Variables

#### 1. Viewing Environment Variables

* **`printenv`**: Displays all environment variables and their values.
    ```bash
    printenv
    ```
    To view a specific variable:
    ```bash
    printenv PATH
    ```

* **`env`**: Similar to `printenv`, often used without arguments to show all.
    ```bash
    env
    ```

* **`echo $VARIABLE_NAME`**: Displays the value of a specific environment variable. The `$` prefix is crucial.
    ```bash
    echo $PATH
    echo $HOME
    ```

* **`set`**: Displays all shell variables, including environment variables, shell functions, and local variables. This output is usually much larger than `printenv` or `env`.
    ```bash
    set
    ```

#### 2. Setting Environment Variables (Temporary)

You can set an environment variable for the current shell session using the `export` command. These changes will **only last for the current terminal session** and its child processes.

```bash
export MY_VARIABLE="Hello World"
echo $MY_VARIABLE
```

You can also set a variable for a single command's execution without exporting it for the entire session:

Bash

```
MY_TEMP_VAR="Temporary value" my_command
```

#### 3\. Setting Environment Variables (Permanent)

To make an environment variable persistent across reboots and new terminal sessions, you need to add it to a shell configuration file.

* *   **For the current user (most common):** Edit `~/.bashrc` (for Bash shell) or `~/.zshrc` (for Zsh shell) or `~/.profile`. Open the file with your favorite text editor (e.g., `vim`, `nano`):
 
Bash

``` 
    nano ~/.bashrc 
```
     
 Add lines like:
     
Bash
     
```
    export MY_PERMANENT_VAR="This is permanent"
    export ANOTHER_PATH="/opt/my_app/bin:$PATH" # Add to PATH
```
  
After saving the file, apply the changes without logging out and back in:

Bash     
```
    source ~/.bashrc
    # or
    . ~/.bashrc
```
     
* **For all users (system-wide):** This requires root privileges and is typically done for system-level configurations.
    
    * **`/etc/profile`**: Executed by all login shells for all users.
    * **`/etc/environment`**: A simple file where each line defines a `KEY="VALUE"` pair. It's read by non-login shells and some desktop environments.
    *  **`/etc/profile.d/`**: A directory containing scripts that are sourced by `/etc/profile`. It's recommended to create a new `.sh` file here (e.g., `/etc/profile.d/myvars.sh`) for new system-wide variables.
    
Bash     
```
sudo nano /etc/profile.d/myvars.sh
```
Add:

Bash
  
 ```
export GLOBAL_SETTING="true"
```
Then, source the script or reboot for changes to take effect.

#### 4\. Unsetting Environment Variables

To remove an environment variable from the current session:

Bash

```
unset MY_VARIABLE
echo $MY_VARIABLE # This will now be empty
```

### Importance of Environment Variables

*    **Configuration:** Allows applications to be configured without hardcoding values directly into their source code.
*    **Flexibility:** Easily adjust system behavior or application settings without modifying core files.
*    **Security:** Can be used to store sensitive information (though not ideal for highly sensitive data, as they can be viewed by other processes on the system if permissions are not strict).
*    **Portability:** Makes scripts and applications more portable across different environments.
*   **Automation:** Crucial for scripting and automating tasks, enabling scripts to adapt to different environments or user preferences.

---


# 📂 File Handles and 🧹 Text Processing in Linux

## 🔧 File Handles

In Linux, a **file handle** (or file descriptor) is an integer that uniquely identifies an open file in a process.

### Standard File Descriptors

| Descriptor | Name            | Description               |
|-----------:|------------------|---------------------------|
| `0`        | `stdin`         | Standard Input            |
| `1`        | `stdout`        | Standard Output           |
| `2`        | `stderr`        | Standard Error            |

### Redirecting File Handles

```bash
command > file       # stdout to file (overwrite)
command >> file      # stdout to file (append)
command 2> file      # stderr to file
command &> file      # stdout and stderr to file
command > file 2>&1  # stdout to file, stderr to stdout
```

### Example

```bash
ls > out.txt 2> err.txt    # separate stdout and stderr
```

## 📄 File Descriptors in Scripts

You can open, read, and write to file descriptors in Bash:

```bash
exec 3> myfile.txt      # open file for writing on FD 3
echo "Hello" >&3        # write to FD 3
exec 3>&-               # close FD 3
```

---

## 🛠️ Text Processing Tools

### 1. **cat** — Concatenate and display file contents

```bash
cat file.txt
```

### 2. **grep** — Search using patterns

```bash
grep "error" logfile.txt     # case-sensitive
grep -i "error" logfile.txt  # case-insensitive
```

### 3. **awk** — Pattern scanning and processing

```bash
awk '{ print $1, $3 }' file.txt
awk -F, '{ print $2 }' data.csv  # comma-separated
```

### 4. **sed** — Stream editor for filtering and transforming text

```bash
sed 's/old/new/' file.txt
sed -n '2,4p' file.txt         # print lines 2 to 4
```

### 5. **cut** — Remove sections from each line of files

```bash
cut -d',' -f1 data.csv         # extract first column
```

### 6. **tr** — Translate or delete characters

```bash
tr 'a-z' 'A-Z' < file.txt      # convert to uppercase
```

### 7. **sort** — Sort lines of text files

```bash
sort file.txt
sort -r file.txt              # reverse sort
```

### 8. **uniq** — Report or filter repeated lines

```bash
sort file.txt | uniq          # remove duplicates
uniq -c file.txt              # count duplicates
```

### 9. **head / tail** — Output start/end of files

```bash
head -n 10 file.txt
tail -f logfile.txt           # follow updates
```

---

## 📌 Example: Combine Tools

```bash
grep "error" logfile.txt | cut -d' ' -f5 | sort | uniq -c | sort -nr
```

> 🔍 **Explanation**: Extracts the 5th word from "error" lines, counts unique occurrences, and sorts by frequency.

---


# 🔐 Linux File Permissions

Linux uses a permission model to control who can read, write, or execute files and directories.

---

## 🧱 Permission Types

Each file/directory has **three sets** of permissions:

| Type     | Description        |
|----------|--------------------|
| `r`      | Read               |
| `w`      | Write              |
| `x`      | Execute            |

These apply to:

1. **User (u)** – the file owner  
2. **Group (g)** – members of the file’s group  
3. **Others (o)** – all other users  

---

## 🔍 Viewing Permissions

Use `ls -l` to list permissions:

```bash
ls -l
```

### Example Output

```
-rwxr-xr-- 1 alice staff  512 May 25 09:00 script.sh
```

### Breakdown

| Symbol    | Meaning                       |
|-----------|-------------------------------|
| `-`       | File type (`-` = file, `d` = directory) |
| `rwx`     | User: read, write, execute     |
| `r-x`     | Group: read, execute           |
| `r--`     | Others: read                   |

---

## 🔧 Changing Permissions

### `chmod` — Change file modes/permissions

```bash
chmod u+x file       # Add execute to user
chmod g-w file       # Remove write from group
chmod o=r file       # Set read only for others
```

### Symbolic vs Numeric Mode

#### Symbolic

```bash
chmod u+rwx,g+rx,o+r file
```

#### Numeric (Octal)

| rwx | Binary | Octal |
|-----|--------|-------|
| rwx | 111    | 7     |
| rw- | 110    | 6     |
| r-- | 100    | 4     |

```bash
chmod 755 file  # rwxr-xr-x
chmod 644 file  # rw-r--r--
```

---

## 👥 Changing Owner/Group

### `chown` — Change owner

```bash
chown user file
chown user:group file
```

### `chgrp` — Change group

```bash
chgrp group file
```

---

## 🔐 Special Permissions

### 1. **Setuid (`s`)**: Run as file owner  
```bash
chmod u+s file
```

### 2. **Setgid (`s`)**: Run as group  
```bash
chmod g+s dir
```

### 3. **Sticky Bit (`t`)**: Only owner can delete  
```bash
chmod +t /tmp
```

---

## 📌 Useful Commands

```bash
find . -type f -perm 0777         # Find files with 777 perms
chmod -R 755 /var/www             # Recursively change permissions
chown -R user:group /home/user    # Recursively change owner/group
```
