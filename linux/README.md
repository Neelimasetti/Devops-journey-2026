# Linux for DevOps
This folder contains my Linux learning notes and practice.

## Why Linux for DevOps?
Most servers run on Linux. DevOps engineers must be comfortable
working from the Linux terminal.

---

## Basic Commands Learned

| Command | Purpose |
|-------|--------|
| pwd | Show current directory |
| ls | List files and folders |
| cd | Change directory |
| mkdir | Create a directory |
| touch | Create a file |
| rm | Delete file/folder |
| cp | Copy files |
| mv | Move or rename files |
| cat | View file content |
| nano | Edit files |

---

## Hands-on Practice

- Created folders and files
- Navigated directories
- Edited files using nano
- Deleted test files safely

---

## Permissions & Ownership (Intro)

- Read (r)
- Write (w)
- Execute (x)

## Practice Example

mkdir practice
cd practice
touch test.txt
echo "Hello Linux" > test.txt
cat test.txt

output
hello linux

issues faced 
Issue: File had no output when using cat  
Cause: Created `text.txt` but wrote data into `test.txt`  
Fix: Used correct filename consistently

every file has 3 permission groups
r = read
w = write
x = execute

### Script Execution Behavior

Observed that scripts can run without execute permission
when executed using `bash script.sh`.

Key learning:
- `./script.sh` requires execute permission
- `bash script.sh` requires only read permission

------------------------------------------------------------------

# Linux for DevOps 🐧

This section contains my Linux learning notes, hands-on labs, and practical exercises completed as part of my DevOps learning journey.

---

# Why Linux for DevOps?

Linux is the most widely used operating system for servers and cloud environments.

As a DevOps Engineer, understanding Linux is essential for:

* Server administration
* Application deployment
* Troubleshooting
* Automation
* Cloud operations

---

# Linux Fundamentals

## Basic Commands Practiced

| Command | Purpose                |
| ------- | ---------------------- |
| pwd     | Show current directory |
| ls      | List files and folders |
| cd      | Change directory       |
| mkdir   | Create directory       |
| touch   | Create file            |
| cp      | Copy files             |
| mv      | Move or rename files   |
| rm      | Delete files/folders   |
| cat     | Display file contents  |
| nano    | Edit files             |
| vi      | Edit files using Vim   |

---

# Hands-on Practice

### File Operations

```bash
mkdir practice
cd practice

touch file1.txt
touch file2.txt

cp file1.txt file3.txt
mv file2.txt newfile.txt

ls
```

### Output Verification

```bash
cat file1.txt
```

---

# Linux Permissions

Linux permissions control access to files and directories.

## Permission Types

| Symbol | Meaning |
| ------ | ------- |
| r      | Read    |
| w      | Write   |
| x      | Execute |

## Permission Groups

Every file has permissions for:

* Owner
* Group
* Others

Example:

```bash
-rwxr-xr--
```

---

# chmod Practice

```bash
chmod 777 project.txt
chmod 755 project.txt
chmod 644 project.txt
```

## Learning

* 777 gives access to everyone
* 755 is common for scripts/directories
* 644 is common for regular files

### Security Note

Avoid using 777 unless absolutely necessary.

Follow the Principle of Least Privilege.

---

# Script Execution Behavior

Observed that scripts can run without execute permission when executed using:

```bash
bash script.sh
```

### Key Learning

```bash
./script.sh
```

Requires execute permission.

```bash
bash script.sh
```

Requires only read permission.

---

# User Management

## User Creation

```bash
sudo useradd -m dev1
sudo useradd -m dev2
```

## Password Assignment

```bash
sudo passwd dev1
sudo passwd dev2
```

## Group Management

```bash
groupadd devops

usermod -aG devops dev1
usermod -aG devops dev2
```

## Verification

```bash
groups dev1
groups dev2
```

### Skills Learned

* Creating users
* Creating groups
* Adding users to groups
* Managing access permissions

---

# Ownership Management

## Change Owner

```bash
sudo chown dev1 project.txt
```

## Change Owner and Group

```bash
sudo chown dev1:devops project.txt
```

### Skills Learned

* File ownership management
* Group ownership management

---

# Shared Directory Practice

```bash
sudo mkdir /shared

sudo chown dev1:devops /shared

chmod 770 /shared
```

### Learning

Only group members can access the directory.

Others are denied access.

---

# Compression & Archiving

## Create Archive

```bash
tar -cvf data.tar data/
```

### Flags

* c = create
* v = verbose
* f = file

## Compress Archive

```bash
gzip data.tar
```

Result:

```text
data.tar.gz
```

## Extract Archive

```bash
tar -xvf data.tar.gz
```

---

# Disk Usage Analysis

## Check Disk Space

```bash
df -h
```

## Check Folder Size

```bash
du -sh data
```

## Largest Files

```bash
du -ah | sort -rh | head
```

### Skills Learned

* Storage monitoring
* Capacity analysis
* Identifying large files

---

# Package Management

## Update Package List

```bash
sudo apt update
```

## Install Package

```bash
sudo apt install git
```

## Verify Installation

```bash
git --version
```

## Remove Package

```bash
sudo apt remove git
```

---

# Linux Networking

## Check IP Address

```bash
ip a
```

## Test Connectivity

```bash
ping google.com
```

## DNS Lookup

```bash
nslookup google.com
```

## Check Internet Access

```bash
curl google.com
```

## Routing Table

```bash
ip route
```

### Skills Learned

* Checking network configuration
* Testing internet connectivity
* DNS troubleshooting
* Understanding routing

---

# Linux Filters

## Create Sample File

```bash
echo -e "apple\nbanana\napple\norange\nbanana" > fruits.txt
```

## Remove Duplicates

```bash
sort fruits.txt | uniq
```

## Count Lines

```bash
wc -l fruits.txt
```

## Display First Lines

```bash
head fruits.txt
```

## Display Last Lines

```bash
tail fruits.txt
```

---

# Grep Practice

## Search Text

```bash
grep "apple" fruits.txt
```

## Case Insensitive Search

```bash
grep -i "apple" fruits.txt
```

## Display Line Numbers

```bash
grep -n "banana" fruits.txt
```

## Search Running Processes

```bash
ps -ef | grep ssh
```

---

# Shell Scripting

## Simple Script

```bash
echo "Welcome to Linux Lab"
date
whoami
```

## Variables

```bash
name="Student"

echo "Hello $name"
```

## Conditional Statements

```bash
if [ -f fruits.txt ]
then
 echo "File exists"
else
 echo "File not found"
fi
```

### Skills Learned

* Creating scripts
* Variables
* Conditions
* Execution permissions

---

# Key Linux Skills Gained

✅ File and Directory Management

✅ Permissions and Ownership

✅ User and Group Management

✅ Compression and Archiving

✅ Package Management

✅ Networking Basics

✅ Text Processing and Filters

✅ Grep Usage

✅ Shell Scripting Fundamentals

---

# DevOps Relevance

Linux is the foundation of modern DevOps practices.

The skills practiced here are directly applicable to:

* Cloud servers
* Docker containers
* Kubernetes nodes
* CI/CD systems
* Production environments

