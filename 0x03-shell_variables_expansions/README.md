# 0-alias

This script creates an alias for the `ls` command.  

## Description

When executed with `source`, it sets `ls` to actually run `rm *`, which means listing files will instead remove them.  
The original `ls` command can still be accessed by using `\ls`.  

## Usage

1. Make the script executable:
   chmod +x 0-alias
2. Source the script in your shell:
   source ./0-alias
3. Test the alias:
   ls       # Will remove all files in the current directory
   \ls      # Will list files normally

## Notes

- This script is exactly two lines long.
- The first line is the shebang `#!/bin/bash`.
- The second line defines the alias.
- Always use caution when running this alias, as `rm *` deletes files.


# 1-hello_you

This script prints "hello" followed by the current Linux username.

## Description

It uses the `whoami` command to reliably get the current logged-in user and prints a greeting.

## Usage

1. Make the script executable:
chmod +x 1-hello_you

2. Run the script:
./1-hello_you

Example output:
hello julien

## Notes

- The script is exactly two lines long.
- The first line is the shebang `#!/bin/bash`.
- The second line prints the greeting using `whoami`.



# 2-path

This script appends the directory /action to the end of the PATH environment variable.

## Description

It ensures that when the shell looks for a program, /action will be checked last.  
This is done by exporting a new PATH with /action appended.

## Usage

1. Make the script executable:
chmod +x 2-path

2. Source the script in the current shell:
source ./2-path

3. Verify PATH:
echo $PATH

Example output:
/home/julien/bin:/home/julien/.local/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/games:/usr/local/games:/snap/bin:/action

## Notes

- The script is exactly two lines long.
- The first line is the shebang `#!/bin/bash`.
- The second line appends /action to PATH using `export`.
- Must use `source` to update the current shell's PATH.


# 3-paths

This script counts the number of directories in the PATH environment variable.

## Description

It splits the PATH variable on colons `:` and counts the number of entries, including empty ones.

## Usage

1. Make the script executable:
chmod +x 3-paths

2. Source or run the script:
. ./3-paths

3. Example output:
6

## Notes

- The script is exactly two lines long.
- The first line is the shebang `#!/bin/bash`.
- The second line counts PATH directories using an array and outputs the total number.
- Works correctly even if PATH contains empty entries (::).
