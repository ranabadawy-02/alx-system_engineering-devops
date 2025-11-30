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
