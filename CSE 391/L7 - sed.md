17 February 2025

---
### Quick notes
- 

### To do
- [x] Pre-lecture 7 ✅ 2025-02-17
- [ ] Homework 7

---
## Lecture Notes

[Sed Command in Linux/Unix with examples - GeeksforGeeks](https://www.geeksforgeeks.org/sed-command-in-linux-unix-with-examples/)

`sed` will always create a backup file in case you need to revert it.
`filename.type.bak` is the backup file
	you can do `mv filename.type.bak filename.type` to revert the changes

Structure of `sed`: `sed -r 's/REGEX/TEXT' filename.type`

**Example:** Replacing all @uw.edu with @cs.washington.edu in emails.txt
- `sed -r 's/uw.edu/cs.washington.edu' emails.txt` - problem: uw.edu might be in someones username
- `sed -r 's/@uw.edu/@cs.washington.edu' emails.txt` - but this would also match @uwsedu
- `sed -r 's/@uw\.edu/@cs.washington.edu' emails.txt` - ignores the `.`





---
Back to: [[CSE 391 - Class Details]]

#ComputerScience