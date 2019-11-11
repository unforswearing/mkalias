# aliaser

> An alias management / directory navigation tool.

<img src="https://raw.githubusercontent.com/unforswearing/aliaser/master/aliaser-example-new.gif">

<br>

## Installation

Aliaser is a single bash function, so you can clone / download this repo and source the file directly:

```bash
> git clone https://github.com/unforswearing/aliaser.git .
> cd aliaser
> source aliaser.bash

```

Or install with [basher](https://github.com/basherpm/basher)

```
$ basher install unforswearing/aliaser
$ include unforswearing/aliaser aliaser
```

<br>

## Usage

Typing `aliaser help` produces the following help text:

```
aliaser <option> [alias name]

options:
  -h|help         display this help message
  -o|open         open the alias file with the default gui editor (e.g. TextEdit)
  -l|list         list aliases saved in alias file
  -e|edit         edit alias file in $EDITOR
  -r|rm           remove alias from alias file
  -d|dir          create an alias from the current directory (alias name is basename)
  -n|name         create an alias from the current directory with a user defined name
  -s|search       search alias file and execute selection
  -a|searchall    search all aliases system wide and execute selection
  -c|command      create an alias from the previous command with a user defined name

examples:
  aliaser rm "aliasname"      remove alias named "aliasname" from alias file
  aliaser -n "favoritedir"    add an alias for the current directory named
                              "favoritedir" to alias file

be sure to source the alias file in your .bashrc or .bash_profile
```

<br>

## Running Aliaser

When `aliaser` is run for the first time it will create a `.aliaser` directory that contains the alias text file. Use `aliaser open` to view the this file in your default `.txt` file editor. You may also use `aliaser edit` to edit this file in your terminal.

Add `source ~/.aliaser/aliaser.txt` to your `bash_profile ` before creating your first alias. Aliases created via `aliaser` are available immediately.

After sourcing `aliaser`, you can navigate to a directory and make some aliases:

```bash
$ cd ~/scripts; aliaser -d myscripts
```

Or create an alias for a command immediately after execution:

```bash
  # command
  $ b=1; while [ $b -le 2 ]; do tput flash; sleep .02; b=$((b + 1)); done

  # create alias for command
  $ aliaser -c "flash_terminal"
```

<br>


Note that `aliaser search` uses [listbox](https://github.com/gko/listbox) to generate a list of results. `aliaser` will execute the selected option.

For example:

```
> aliaser search script

  Search results for "script"
  ---------------------------
⇨ alias scripts='cd ~/Documents/Shared/Scripts'
  alias googleappsscript='cd ~/Documents/Shared/Scripts/-GoogleAppsScript'
  alias bashscripts='cd ~/Documents/Shared/Scripts/-Bash'
  CANCEL SEARCH
```

<br>

