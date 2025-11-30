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

This script prints all local variables and environment variables in the current shell in the `VAR=value` format.

## Description

It uses the `set` command to list all shell variables and functions.  
Unlike `declare -p`, `set` outputs variables without the `declare` prefix, matching the checker’s expected output.

## Usage

1. Make the script executable:
chmod +x 5-local_variables

2. Source the script:
. ./5-local_variables

3. Example output:
BASH=/usr/bin/bash
BASHOPTS=checkwinsize:cmdhist:complete_fullquote:extquote:force_fignore:globasciiranges:hostcomplete:interactive_comments:progcomp:promptvars:sourcepath
COLUMNS=133
...

## Notes

- The script is exactly two lines long.
- The first line is the shebang `#!/bin/bash`.
- The second line lists all local variables, environment variables, and functions using `set`.
- Works correctly when sourced.


# 6-create_local_variable

This script creates a local shell variable named BEST with the value "School".

## Description

- The variable is local to the current shell session when sourced.
- Assigning a value to BEST does not export it to child processes.

## Usage

1. Make the script executable:
chmod +x 6-create_local_variable

2. Source the script in the shell:
. ./6-create_local_variable

3. Example:
echo $BEST
School

## Notes

- The script is exactly two lines long.
- The first line is the shebang `#!/bin/bash`.
- The second line assigns the value "School" to the local variable BEST.


# 7-create_global_variable

This script creates a global shell variable named BEST with the value "School".

## Description

- The variable is exported, making it available to all child processes of the shell.
- Using `export` ensures that programs run from the shell can access BEST.

## Usage

1. Make the script executable:
chmod +x 7-create_global_variable

2. Source the script in the shell:
. ./7-create_global_variable

3. Example:
echo $BEST
School

## Notes

- The script is exactly two lines long.
- The first line is the shebang `#!/bin/bash`.
- The second line creates and exports the variable BEST.

# 8-true_knowledge

This script prints the result of adding 128 to the value stored in the environment variable TRUEKNOWLEDGE.

## Description

- The script uses shell arithmetic `$((...))` to calculate the sum.
- The result is printed followed by a new line.

## Usage

1. Make the script executable:
chmod +x 8-true_knowledge

2. Set the environment variable and run the script:
export TRUEKNOWLEDGE=1209
./8-true_knowledge

3. Example output:
1337

## Notes

- The script is exactly two lines long.
- The first line is the shebang `#!/bin/bash`.
- The second line prints the sum of 128 and $TRUEKNOWLEDGE.


# 9-divide_and_rule

This script prints the result of dividing the environment variable POWER by DIVIDE.

## Description

- The script uses shell arithmetic `$((...))` to perform integer division.
- The result is printed followed by a new line.
- Both POWER and DIVIDE must be exported in the environment.

## Usage

1. Make the script executable:
chmod +x 9-divide_and_rule

2. Set the environment variables and run the script:
export POWER=42784
export DIVIDE=32
./9-divide_and_rule

3. Example output:
1337

## Notes

- The script is exactly two lines long.
- The first line is the shebang `#!/bin/bash`.
- The second line performs the division and prints the result.

# 10-love_exponent_breath

This script displays the result of raising the environment variable BREATH to the power of LOVE.

## Description

- The script uses shell arithmetic `$((...))` with the `**` operator for exponentiation.
- The result is printed followed by a new line.
- Both BREATH and LOVE must be exported in the environment.

## Usage

1. Make the script executable:
chmod +x 10-love_exponent_breath

2. Set the environment variables and run the script:
export BREATH=4
export LOVE=3
./10-love_exponent_breath

3. Example output:
64

## Notes

- The script is exactly two lines long.
- The first line is the shebang `#!/bin/bash`.
- The second line performs exponentiation and prints the result.


# 11-binary_to_decimal

This script converts a binary number stored in the environment variable BINARY to decimal (base 10).

## Description

- The script uses shell arithmetic `$((2#...))` to interpret the value of BINARY as a binary number.
- The result is printed followed by a new line.
- The BINARY variable must be exported in the environment.

## Usage

1. Make the script executable:
chmod +x 11-binary_to_decimal

2. Set the environment variable and run the script:
export BINARY=10100111001
./11-binary_to_decimal

3. Example output:
1337

## Notes

- The script is exactly two lines long.
- The first line is the shebang `#!/bin/bash`.
- The second line converts the binary number to decimal and prints the result.
