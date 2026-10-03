# tmux config

My tmux setup, built around [tmux-scrollable](https://github.com/yanglited/tmux-scrollable):
niri-style scrollable tiling, where new columns scroll in from the right instead of
squeezing your panes.

![tmux-scrollable demo](https://raw.githubusercontent.com/yanglited/tmux-scrollable/main/demo.gif)

## What is in it

- **tmux-scrollable**: `Alt+n` opens a column to the right, `Alt+r` cycles its width
  through 30% / 50% / 90%, moving focus scrolls the strip.
- **vim-tmux-navigator**: `Ctrl+hjkl` moves between vim splits and tmux panes alike.
- **tmux-resurrect**: `prefix Ctrl+s` saves sessions, `prefix Ctrl+r` restores them.
- **tmux-yank** and **tmux-sensible**.
- `Alt+hjkl` swaps the current pane with its neighbour.
- `prefix v` opens the pane's scrollback in nvim (vim as fallback), in a popup if a
  program is running.
- Splits open in the current pane's path; pane titles on top; a readable status bar.

The prefix is the default `Ctrl+b`. `prefix ?` lists every binding.

## Requirements

tmux **3.8 or newer** with the cursor patch from tmux-scrollable; see its
[requirements](https://github.com/yanglited/tmux-scrollable#requirements) for the build
steps. On tmux 3.7 the plugin refuses to load and everything else here still works.

## Try it

Back up your own config first, then:

```sh
mv ~/.config/tmux ~/.config/tmux.bak 2>/dev/null; mv ~/.tmux.conf ~/.tmux.conf.bak 2>/dev/null
git clone https://github.com/yanglited/tmux.git ~/.config/tmux
git clone https://github.com/tmux-plugins/tpm ~/.config/tmux/plugins/tpm
tmux kill-server 2>/dev/null; tmux
```

Inside tmux press `prefix I` (Ctrl+b, then Shift+i) so TPM installs the plugins, then
try `Alt+n`.

To go back: `tmux kill-server`, remove `~/.config/tmux`, and restore the `.bak` copies.

## Editing

After changing `tmux.conf`, reload with `tmux source ~/.config/tmux/tmux.conf`. After
adding a plugin line, reload and then press `prefix I`. `prefix U` updates plugins.

This directory is a submodule of my private dotfiles and lives at `~/.config/tmux`.
