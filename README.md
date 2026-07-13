These are my personal [`navi`](https://github.com/denisidoro/navi) cheatsheets.

## Setup

Clone the repo and add it to navi's path (`$NAVI_PATH`).

```sh
git clone git@github.com:Nemoden/navi-cheatsheets.git ~/Projects/navi-cheatsheets
```

Bash/zsh (`~/.bashrc` / `~/.zshrc`):

```sh
export NAVI_PATH="$HOME/Projects/navi-cheatsheets:$NAVI_PATH"
```

Fish — an example from my setup, `~/.config/fish/functions/add_navi_path.fish`:

```fish
function add_navi_path -d "adds path to NAVI_PATH" -a path
  if command -sq navi
      if test -d $path
          if not contains $path $NAVI_PATH
              set -gx --prepend NAVI_PATH $path
          end
      end
  end
end
```

called from `~/.config/fish/config.fish`:

```fish
add_navi_path ~/Projects/navi-cheatsheets
```
