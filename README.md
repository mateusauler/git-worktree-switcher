# Git worktree switcher :zap:
Switch between git worktrees with speed. :zap:

<img src = "https://i.imgur.com/nPdneDT.gif" width="600" alt="demo of switching between git worktrees" />

## This fork includes:

- Fish completions work dinamically.
- The `list` subcommand is now `names`, which lists out only the worktree basenames.
- Completions work with spaces & special characters.
- Doesn't create a new shell instance when changing directory.
- Running `wt`, instead of `wt -`, goes to the main worktree (similar to how `cd` itself works).
- Checks for updates automatically once per day on the first invocation.

## Installation
Download the script from the [Release section](https://github.com/mateusauler/git-worktree-switcher/releases).

Make the script executable.

```bash
$ chmod +x wt
```

Copy the executable to any directory in your `$PATH`

```bash
$ sudo cp wt /usr/local/bin
```

## Tab Autocompletion :zap:

**For Bash**
```bash
sudo cp completions/wt_completion /etc/bash_completion.d
```

Add this to the end of your `~/.bashrc`:
```bash
eval "$(command wt init bash)"
```

**For ZSH**
> Note: completion file for zsh has `_` prefix


Find paths where you can store your completion
```bash
print -rl -- $fpath
```

Copy completion script to one of that location and restart the shell.

```bash
sudo cp completions/_wt_completion <one-of-$fpath>

exec zsh
```

Add this to the end of your `~/.zshrc`:
```bash
eval "$(command wt init zsh)"
```

**For Fish**
```bash
cp completions/wt.fish ~/.config/fish/completions
```

Add this to the end of your `~/.config/fish/config.fish`:
```bash
command wt init fish | source
```

---
Tab autocompletion works for switching between your worktrees.
```bash
wt <TAB> <TAB>

# OR

wt <completion-characters> <TAB>
```

## Usage
Switch between worktrees.
You can do a text search to change to the worktree directory.

```bash
$ wt <worktree-name/search-term>
```

Go to root worktree directory

```bash
$ wt
```

List out all the worktree names.

```bash
$ wt names
```

Show help message

```bash
$ wt help
```

Update to the latest release

```bash
$ wt update
```

Show the CLI version

```bash
$ wt version
```
