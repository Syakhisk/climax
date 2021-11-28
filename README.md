# climax
![](https://user-images.githubusercontent.com/63556086/143784554-3d9c2212-de63-4bc2-ae6f-32a2178ce0b8.png)

My knowledge base, a note of how I (should) use the terminal (and other tools that revolves around it), Made mostly to help me remember what I learned. Take it sort of like a cheatsheet.

The content of this repo should be categorized into smaller section such as `shell`, `tmux`, `vim`, and so on. If it's not, I'm probably ~~too lazy to do that~~ working on something else.

## Setup and Tools
- [zsh](http://zsh.org/) (shell)
- [bash](http://www.gnu.org/software/bash/) (shell - mainly for scripting)
- [oh-my-zsh](https://github.com/ohmyzsh/ohmyzsh) (zsh configuration framework)
- [starship](https://github.com/starship/starship) (zsh prompt)
- [tmux](https://github.com/tmux/tmux) (terminal multiplexer)
- [fzf](https://github.com/junegunn/fzf) (cli fuzzy finder)
- [neovim](https://github.com/neovim/neovim) (more extensible vim)
- [lunarvim](https://github.com/lunarvim/lunarvim) (neovim IDE-like configuration layer)

## Table of Contents
- [Shell](#shell)
  - [Shell Shortcuts](#shell-shortcuts)
  - [Scripting](#scripting)

## Shell

### Shell vs Terminal
> **terminal** -> text input/output environment  
> **console** -> physical terminal (ancient stuff)  
> **shell** -> command line interpreter (such as bash, zsh, fish, etc)  
> **terminal emulator** -> virtual terminal on your screen

Source:  
https://askubuntu.com/a/506628  
https://unix.stackexchange.com/a/4132

<!--
### Environment Variables
**$EDITOR**  
**$PATH**
-->

<!--
### Alias and Functions
-->

### Shell Shortcuts

> Note that some of the shortcut are not available by default, In `oh-my-zsh` these are available by default. Don't try to remember them, use what you need and it'll stick if it's useful.

**Clearing screen**  

Press `Ctrl-L` to clear the screen. This is useful when you are already typing something and you want to clear the screen.

**Shell history**  

| key      | action                                                             |
| -        | -                                                                  |
| `Ctrl-R` | search shell history (instead of pressing the up arrow repeatedly) |
| `Ctrl-P` | go back in history (easier to press than up arrow)                 |
| `Ctrl-N` | go forward in history (this too)                                   |


**Jumping around the line**  

| key      | action                            |
| -        | -                                 |
| `Ctrl-A` | jump to the beginning of the line |
| `Ctrl-E` | jump to the end of the line       |
| `Ctrl-F` | jump forward one character        |
| `Alt-F`  | jump forward one word             |
| `Ctrl-B` | jump backward one character       |
| `Alt-B`  | jump backward one word            |

**Manipulating text** 

| key      | action                                      |
| -        | -                                           |
| `Ctrl-W` | delete word to the left of the cursor       |
| `Alt-D`  | delete word to the right of the cursor      |
| `Ctrl-U` | delete line to the whole line               |
| `Ctrl-K` | delete line to the right of the cursor      |
| `Ctrl-D` | delete character to the right of the cursor |
| `Ctrl-H` | delete character to the left of the cursor  |
| `Ctrl-Y` | paste the last deleted text                 |

> Example use-case:
<details>
<summary>
You are typing a command and forgot to add a positional arguments
</summary>
```bash
$ find . -name "*.js" -exec cat {} \; # <-- your cursor is there
```
If you want to add -maxdepth 1 after the `.` you can do it by:
- `Ctrl-A` to jump to the beginning of the line
- `Alt-F` to jump forward one word
- `Ctrl-B` to jump backward one character
- Insert the arguments  

> Seems like a lot of work, but it should make you faster once you get used to it.
</details>

**Execute the line but keep the line after execution**  
Press `Alt-A` to execute the line and keep the line after execution. (discover this while writing this section lol)

```bash
$ echo "hello" # <-- Press <Alt-A>
hello
$ echo "hello" # <-- the line is still there

```

### Scripting 
> I tend to use bash for scripting because I feel like it's more universal and portable (not sure 🤔).

**Shebang**  
The `#!/bin/bash` is a way to tell the shell that this is script should be interpreted as a bash script, the same way you would use `#!/usr/bin/python3` or `#!/bin/node`. What that means is you can just run the script directly without specifying the interpreter.

However to avoid path issues, you should always use the `#!/bin/env <interpreter>` instead.

in myscript:
```bash
#!/bin/env bash
echo "foo"
```

in shell:
```bash
$ ./myscript
foo

$ myscript # <-- if you already have the script in your $PATH, you can just run it like this
foo
```

<!--
### STDIN, STDOUT, STDERR
-->

<!--
### Pipe and Redirection
-->

## Note
Open an issue if there are incorrect information or if you want to give suggestions.
