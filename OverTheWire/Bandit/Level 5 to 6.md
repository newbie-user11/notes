Same thing as earlier levels - Follow level instructions.
Password: lrIWWI6bB37kxfiCQZqUdOIYfr6eEeqR

Accessing password for level 6 is tricky. Too many directories with too many files. Thankfully, there are criteria for the file that contains the password:
1) human readable
2) 1033 bytes in size
3) not executable

These criteria can be used to create a command that targets the file containing password. 

Useful: 
`find /home/bandit5/inhere/maybehere*/ -type f -size 1033c -not -executable -print0 | xargs -0 file`
*Which part of above code meets which criteria:
1) human readable **`file -b`**
2) 1033 bytes in size **`-size 1033c`**
3) not executable **`-not -executable`**

Additionally, -print0 important to get bash to read spaces in filenames. See **`xargs -0`**, the -0 is also to get xargs to handle spaces in filenames.

Password for level 6: P4L4vucdmLnm8I7Vl7jG1ApGSfjYKqJU
