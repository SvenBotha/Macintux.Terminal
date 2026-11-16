# Install checklist

Source: DevOps Toolbox, "I Tried Everything. This is the Best Terminal Setup" (https://www.youtube.com/watch?v=QpiZOKul1U8).
Each item becomes `modules/<name>/` holding its config and an `install.sh` (install the tool, back up the existing config, symlink the repo config).
Homebrew on macOS and Linux. Casks are macOS only.

## Terminal
- [ ] ghostty: `brew install --cask ghostty` (Linux: distro package). Config: font, colours, `macos-option-as-alt = true` so omp's Alt+Shift chords work, and start tmux on launch.
- [ ] Nerd Font: `font-meslo-lg-nerd-font` (already in the dotfiles install.sh).

## Multiplexer
- [ ] tmux: `brew install tmux`. Split the config into `reset.conf` (prefix plus baseline unbinds) and `tmux.conf` (sources `reset.conf`, then plugins).
- [ ] TPM: `git clone https://github.com/tmux-plugins/tpm ~/.tmux/plugins/tpm`
- [ ] catppuccin/tmux (theme)
- [ ] omerxx/tmux-sessionx (fuzzy session picker; needs fzf, bat, zoxide)
- [ ] omerxx/tmux-floax (floating pane; set size, colour, key, and path-follow)
- [ ] sesh: `brew install sesh`, plus presets in `sesh.toml` (a "nvim config" session and a "tmux conf" session)

## Worktrees and agents
- [ ] worktrunk: `brew install worktrunk`, shell hook `eval "$(wt config shell init zsh)"`
- [ ] workmux: `brew install raine/workmux/workmux`, `~/.config/workmux/config.yaml` with the agent set to omp
- [x] omp: `modules/omp` submodule (SvenBotha/Macintux.omp). Live copy is `~/.omp/agent` itself; install with `modules/omp/install.sh` (pinned version + config).
- [ ] Skipped: pi, pi's `/head` (omerxx/pi-head), and the ASD-STE100 extension (omp is the agent)

## Shell
- [ ] zsh plus zsh-autosuggestions and zsh-syntax-highlighting
- [ ] starship: `brew install starship`, lean prompt showing only git, AWS, Go, and Python
- [ ] eza: `brew install eza` (`ls`/`ll` aliases)
- [ ] zoxide: `brew install zoxide` (`z`, `zi`)
- [ ] fzf: `brew install fzf` (Ctrl-R history; sessionx needs it)
- [ ] atuin: `brew install atuin`, search in a tmux popup, Ctrl-R left to fzf
- [ ] Skipped: nushell (`nu -c ls`)

## Editor and files
- [ ] neovim: `brew install neovim`. Move the existing `nvim/` config into a module (not LazyVim).
- [ ] superfile: `brew install superfile` (`spf`)
- [ ] television: `brew install television` (`tv`), shell hook `eval "$(tv init zsh)"`
- [ ] mise: `brew install mise`, `eval "$(mise activate zsh)"` (replaces direnv; Nix optional and skipped)

## Mentioned, not daily drivers
- Herdr and TUIOS (other multiplexers): skip.
