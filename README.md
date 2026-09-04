# ka

Keep tmux sessions alive by sending `Enter` to them on an interval.

Useful for long-running interactive tools that stall waiting for a keypress.

## Install

```sh
cp ka ~/.local/bin/ka && chmod +x ~/.local/bin/ka
```

## Usage

```sh
ka continue <session> [interval]   # start sending Enter (default every 3s)
ka stop <session>|all              # stop one session or all
ka status                          # list sessions being kept alive
```

`continue` and `stop` also accept the short aliases `c` and `s`. `status` accepts `ls`.

Each loop runs detached in the background and exits on its own when the tmux
session goes away. PID files live in `~/.cache/ka/`.
