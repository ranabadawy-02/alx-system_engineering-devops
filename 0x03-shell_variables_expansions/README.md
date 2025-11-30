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

This script counts the number of directories in the PATH environment variable, ignoring empty entries.

## Description

It splits PATH into multiple lines and counts only non-empty entries.  
Empty entries (like `::`) are ignored.

## Usage

1. Make the script executable:
chmod +x 3-paths

2. Source or run the script:
. ./3-paths

3. Example output:
6

Example with PATH containing empty entries:
PATH=/bin::::/home:/usr:::::/home/me
. ./3-paths
6

## Notes

- The script is exactly two lines long.
- The first line is the shebang `#!/bin/bash`.
- The second line counts PATH directories using `tr` and `grep -c`.
- Works correctly even if PATH contains empty entries (::).


# 4-global_variables

This script prints all exported global variables in the current shell.

## Description

It uses `export -p` to list all global variables defined in the shell.  
This includes project-specific variables like `HBTN=89`.

## Usage

1. Make the script executable:
chmod +x 4-global_variables

2. Source the script:
. ./4-global_variables

3. Example output:
declare -x HBTN="89"
declare -x PATH="/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin"

## Notes

- The script is exactly two lines long.
- The first line is the shebang `#!/bin/bash`.
- The second line lists exported global variables using `export -p`.
- Works correctly when sourced.


# 5-local_variables

This script prints all local variables, environment variables, and functions in the current shell.

## Description

It uses the `declare -p` command to list all variables (local and environment) and functions defined in the shell.  
This includes shell variables like `BASH`, `COLUMNS`, and any user-defined variables or functions.

## Usage

1. Make the script executable:
chmod +x 5-local_variables

2. Source the script:
. ./5-local_variables

3. Example output:
BASH=/bin/bash
BASHOPTS=checkwinsize:cmdhist:complete_fullquote:expand_aliases:extglob:extquote:force_fignore:histappend:interactive_comments:progcomp:promptvars:sourcepath
BASH_VERSION='4.3.46(1)-release'
COLUMNS=133
...

## Notes

- The script is exactly two lines long.
- The first line is the shebang `#!/bin/bash`.
- The second line prints all variables and functions using `declare -p`.
- Works correctly when sourced.
