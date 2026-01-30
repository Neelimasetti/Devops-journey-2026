# Linux for DevOps
This folder contains my Linux learning notes and practice.
# Linux for DevOps 🐧

This section contains my Linux learning notes and hands-on practice
for DevOps engineering.

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
