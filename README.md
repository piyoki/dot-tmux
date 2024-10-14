# TMUX Configuration

<!-- vim-markdown-toc GFM -->

* [Reload Configuration](#reload-configuration)
* [Plugins Manager](#plugins-manager)
* [Copy and Paste](#copy-and-paste)

<!-- vim-markdown-toc -->

## Reload Configuration

```bash
tmux source-file ~/.tmux.conf
```

## Plugins Manager

Install Tmux Plugin Manager

```bash
git clone https://github.com/tmux-plugins/tpm ~/.tmux/plugins/tpm
```

Put this at the bottom of ~/.tmux.conf

```bash
# List of plugins
set -g @plugin 'tmux-plugins/tpm'
set -g @plugin 'tmux-plugins/tmux-sensible'

# Other examples:
# set -g @plugin 'github_username/plugin_name'
# set -g @plugin 'github_username/plugin_name#branch'
# set -g @plugin 'git@github.com:user/plugin'
# set -g @plugin 'git@bitbucket.com:user/plugin'

# Initialize TMUX plugin manager (keep this line at the very bottom of tmux.conf)
run '~/.tmux/plugins/tpm/tpm'
```

Reload TMUX environment so TPM is sourced:

```bash
# type this in terminal if tmux is already running
tmux source ~/.tmux.conf
```

Installing plugins

- Add new plugin to `~/.tmux.conf` with set `-g @plugin` '...'
- Press `prefix` + `I` (capital i, as in Install) to fetch the plugin.

Uninstalling plugins

- Remove (or comment out) plugin from the list.
- Press `prefix + alt + u` (lowercase u as in uninstall) to remove the plugin.

Key Bindings

`prefix + I`

- Installs new plugins from GitHub or any other git repository
- Refreshes TMUX environment

`prefix + U`

- updates plugin(s)

`prefix + alt + u`

- remove/uninstall plugins not on the plugin list

## Copy and Paste

Source: https://www.seanh.cc/2020/12/27/copy-and-paste-in-tmux/

- `Ctrl + b [` enters copy mode
- `Ctrl + b ]` - pastes from tmux’s most recently created paste buffer (i.e. pastes the most recently copied text)
- `Ctrl + b =` or `tmux choose-buffer` on the command line shows you all the paste buffers and lets you choose one to paste from
