<p align="center">
<b>xonsh-prewarmed</b> is to run interactive <a href="https://xon.sh">xonsh</a> session in milliseconds using prewarmed session from the background screen.
</p>

<p align="center">  
If you like the idea click ⭐ on the repo and and <a href="https://twitter.com/intent/tweet?text=Nice%20xontrib%20for%20the%20xonsh%20shell!&url=https://github.com/anki-code/xonsh-prewarmed" target="_blank">tweet</a>.
</p>

## How it works

On first run of `xonsh-prewarmed-*` script it creates additional reserved xonsh session in the background. On the next runs of the script it uses the reserved sessions and create new reserved sessions in the background. As result the speed of run the new interactive xonsh sessions is milliseconds.

## Installation

```xsh
git clone https://github.com/anki-code/xonsh-prewarmed
cd xonsh-prewarmed
chmod +x xonsh-prewarmed-*
```

## Usage

[GNU Screen](https://www.gnu.org/software/screen/):
```xsh
./xonsh-prewarmed-screen
```
[Tmux](https://github.com/tmux/tmux/wiki):
```xsh
./xonsh-prewarmed-tmux
```
[zellij](https://zellij.dev/):
```xsh
./xonsh-prewarmed-zellij
```

### Detect that xonsh was prewarmed 

Use `XONSH_PREWARMED` environment variable to detect that xonsh was prewarmed in `~/.xonshrc`:

```xsh
if __xonsh__.env.get('XONSH_PREWARMED', False):
    print('This xonsh session was prewarmed!')
```

## Cheatsheet

### Share history between sessions

If you're using SQLite history backend in xonsh you can use `history pull` command to get history from other sessions.

### GNU Screen

Basics:

* When you run `screen` the new session will be started and your current terminal will be attached to it.
* You can put the screen session to background by pressing `Ctrl + a` and then press `d`. After this your terminal will be detached from the session but the session will stay active in background.
* Run `screen -ls` to get list of all sessions. The `sess_id` is the number before dot.
* Run `screen -r <sess_id>` to attach `Detached` session to the current terminal.
* Run `screen -rd <sess_id>` to detach the `Attached` session and attach to the current terminal.
* Run `env | grep STY` to get current `sess_id`.

## Add another session manager

Feel free to add another session manager (e.g. `zellij`) by creating `xonsh-prewarmed-<manager>`.
