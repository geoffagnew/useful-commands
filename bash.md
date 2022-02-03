# Pipes and redirection

1. Piping is used to send streams from 1 process to another.
2. Redirection is used to send streams to and from files.

| Symbol        | Function                      |
| ------------- |-------------------------------|
| \|             | Pipe                          |
| >             | Output redirection (truncate) |
| >>            | Output redirection (append)   |
| <             | Input redirection             |
| <<            | Here document                 |

# Commands and built-ins

Examples of commands: `ls`, `rm`, `grep`. These commands are separate from bash that exist on the system. But bash includes some build-in commands as well.

To check if something we run is a command or a built-in by running: `command -V COMMAND_NAME`. For example, `command -V df`.

Examples of built-in bash commands: 
`echo`: outputs text, ends the line with a newline character

Built-ins take precendent over commands if they exist. They will always be run over commands first unless specified otherwise.

To see documentation about built-ins, use the command `help`

# Brackets and braces in bash

In bash, parentheses, brackets, and braces act as commands themselves.

# Bash expansions and substitutions

Expansions and substitutions are used when you need to access/work with something that you don't know the value of. They're intepreted when they're run, and they replace themselves with a value, or set of values.

| Representation| Name                          |
| ------------- |-------------------------------|
| ~             | Tilde expansion. Represents the user's $HOME environment variable. Used in paths to represent the current user's home directory.|
| {...}         | Brace expansion. Creates sets or ranges. Useful when you need keep part of a path the same, but need to replace a part of it. |
| ${...}        | Parameter expansion. Recall stored values and transform those values in various ways. The most straight forward use of parameter expansion is setting a value, then retrieving it. |
| $(...)        | Command substitution. Puts the output of one command inside another. Often used together with string manipulation tools, to extract part of a commands output. Such as a path, IP address, etc., that needs to be handed back up to the parent command. Often used with tools like `grep` and `awk` to extract specific pieces of text from output. |
| $((...))      | Arithmetic expansion. Perform mathematical calculations and use the resulting value in other commands. |

#### Examples of brace expansion
```
echo I am c{a,u,o}t
Output: I am cat, cut, cot
```
```
echo {0..10}
Output: 0 1 2 3 4 5 6 7 8 9 10
```
#### Examples of parameter expansion
```
greeting="Hell0 there!"
echo ${greeting}
Output: Hello there!
```
Example of pattern substitution with parameter expansion (replace the first instance of the match 'there', with 'everybody)
```
echo ${greeting/there/everybody}
Output: Hello everybody!
```
#### Examples of command substitution
```
uname -r
Output: 5.10.17-v7l+

echo "The kernel is $(uname -r)"
Output: The kernel is 5.10.17-v7l+
```
