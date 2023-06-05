<p align="center">
<b>xonsh-prewarmed</b> - is the script to run interactive <a href="https://xon.sh">xonsh</a> session in milliseconds using prewarmed <a href="https://www.gnu.org/software/screen/">GNU Screen</a> session from the background.
</p>

<p align="center">  
If you like the idea click ⭐ on the repo and and <a href="https://twitter.com/intent/tweet?text=Nice%20xontrib%20for%20the%20xonsh%20shell!&url=https://github.com/anki-code/xonsh-prewarmed" target="_blank">tweet</a>.
</p>

## How it works

On first run of `xonsh-screen-prewarmed` script it creates additional reserved xonsh session in [GNU Screen](https://www.gnu.org/software/screen/) manager in the background. On the next runs of the script it uses the reserved sessions and create new reserved sessions in the background. As result the speed of run the new interactive xonsh sessions are equal to the `screen` speed.

## Installation

```xsh
wget https://raw.githubusercontent.com/anki-code/xonsh-prewarmed/main/xonsh-screen-prewarmed
chmod +x xonsh-screen-prewarmed
```

## Usage

```xsh
./xonsh-screen-prewarmed
```

## Add another session manager

Feel free to add another session manager (e.g. `tmux`, `zellij`) by creating `xonsh-<manager>-prewarmed`.
