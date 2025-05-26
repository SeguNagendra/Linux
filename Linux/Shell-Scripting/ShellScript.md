# Complete Shell Script Guide (Markdown Version with Explanations)

Shell scripting is a powerful method to automate commands and tasks in Unix/Linux systems. This complete guide covers everything from basics to advanced features with brief explanations to help you understand better.

---

## 🧰 What is a Shell Script?

A **shell script** is a file containing a sequence of commands for a Unix-based shell to execute. It's commonly used to automate tasks like backups, monitoring, and file processing, saving time and reducing manual errors.

---

## 🛠️ Basic Structure of a Shell Script

```bash
#!/bin/bash
# This is a comment

echo "Hello, World!"
```

* `#!/bin/bash` — Shebang to specify the shell interpreter (Bash in this case).
* `#` — Used to write comments (ignored by the shell).
* `echo` — Prints text to the terminal.

---

## 🔤 Variables

Variables are used to store data such as strings or numbers.

```bash
name="John"
echo "My name is $name"
```

* Use `=` without spaces.
* Reference variables with `$`.

### Environment Variables

These are predefined variables provided by the shell.

```bash
echo $HOME
echo $PATH
```

---

## 📥 Reading Input

You can prompt the user to enter input during script execution.

```bash
echo "Enter your name:"
read username
echo "Welcome, $username!"
```

* `read` takes user input and stores it in a variable.

---

## 🔁 Control Structures

### if-else

Used to execute commands based on conditions.

```bash
if [ "$name" == "John" ]; then
  echo "Hi, John!"
else
  echo "You're not John."
fi
```

### if-elif-else

Allows multiple conditions to be checked.

```bash
if [ $age -lt 13 ]; then
  echo "Child"
elif [ $age -lt 20 ]; then
  echo "Teen"
else
  echo "Adult"
fi
```

### case

An alternative to `if` for handling multiple choices.

```bash
case $1 in
  start)
    echo "Starting..."
    ;;
  stop)
    echo "Stopping..."
    ;;
  *)
    echo "Unknown command"
    ;;
esac
```

---

## 🔄 Loops

Loops are used to repeat a set of commands.

### for Loop

```bash
for i in 1 2 3; do
  echo "Number: $i"
done
```

* Runs the loop 3 times, printing numbers 1 to 3.

### while Loop

```bash
count=1
while [ $count -le 5 ]; do
  echo "Count: $count"
  ((count++))
done
```

* Continues while the condition is true.

### until Loop

```bash
until [ $count -gt 5 ]; do
  echo "Count: $count"
  ((count++))
done
```

* Runs until the condition becomes true.

---

## 🧩 Functions

Functions group commands into reusable blocks.

```bash
greet() {
  echo "Hello, $1"
}

greet "World"
```

* `$1` accesses the first argument passed to the function.

---

## 🎯 Command Line Arguments

Used to pass values to scripts at runtime.

```bash
echo "Script name: $0"
echo "First argument: $1"
echo "Total arguments: $#"
echo "All arguments: $@"
```

* `$0` is the script name, `$1` is the first argument.
* `$#` is the number of arguments, `$@` lists all.

---

## 📂 Arrays

Arrays allow storing multiple values in a single variable.

```bash
fruits=(apple banana cherry)
echo "First: ${fruits[0]}"
echo "All: ${fruits[@]}"
```

---

## 🧾 File I/O

Scripts often need to read from and write to files.

### Writing to a File

```bash
echo "This is a line." > file.txt
```

* `>` overwrites the file.

### Appending to a File

```bash
echo "Another line." >> file.txt
```

* `>>` appends to the file.

### Reading from a File

```bash
while read line; do
  echo $line
done < file.txt
```

* Reads file line-by-line.

---

## 🚦 Exit Status

Every command returns an exit status.

```bash
command
if [ $? -eq 0 ]; then
  echo "Success"
else
  echo "Failed"
fi
```

* `$?` gives the exit status of the last command.

---

## 🧪 Testing Operators

Used in conditions:

* `-eq`, `-ne`, `-gt`, `-lt`, `-ge`, `-le` — Numeric comparisons.
* `-z`, `-n` — Check string length.
* `-f`, `-d`, `-e` — File checks.

---

## 🔧 Useful Commands

| Command | Description             |
| ------- | ----------------------- |
| `echo`  | Print output            |
| `read`  | Get user input          |
| `date`  | Display date/time       |
| `cut`   | Extract text segments   |
| `grep`  | Search text patterns    |
| `awk`   | Pattern scanning        |
| `sed`   | Stream editor           |
| `chmod` | Change file permissions |

---

## 🔐 File Permissions

```bash
chmod +x script.sh
./script.sh
```

* `chmod +x` makes the script executable.

---

## 🧠 Tips & Best Practices

* Use `set -e` to stop the script on errors.
* Quote variables to avoid word splitting.
* Use functions for better organization.
* Use `shellcheck` to find script issues.
* Validate input and handle errors.

---

## 🗓️ Scheduling Scripts

Use `cron` to run scripts on a schedule.

```bash
crontab -e
```

Example:

```bash
0 9 * * * /home/user/backup.sh
```

* Runs the backup script at 9:00 AM every day.

---

## 🧼 Debugging Scripts

```bash
bash -x script.sh
```

* Shows command execution step-by-step.
* Use `set -x` and `set +x` to enable/disable debugging in specific sections.

---

## 📌 Sample Shell Script

```bash
#!/bin/bash

log_file="log.txt"
echo "Starting script..." > $log_file

for i in {1..5}; do
  echo "Line $i" >> $log_file
done

echo "Script finished." >> $log_file
```

* Creates a log file and writes numbered lines to it.

---

## ✅ Conclusion

Shell scripting is an essential skill for any Linux user, system administrator, or DevOps engineer. With practice, you can automate complex workflows and save a lot of time.

---

*Created with ❤️ in Markdown for better readability and learning.*
