# omadora-dotfiles

Default user configuration for [Omadora](https://github.com/stallmer/omadora),
managed with [chezmoi](https://www.chezmoi.io/).

The Omadora image applies this repository on first login with `omadora-setup`.
Run `omadora-setup` again to pull and apply updates, or `omadora-setup --force`
to re-apply it over local changes.

This repository is public so a fresh install can fetch it without logging in.
Never commit secrets here.

## Layout

- `dot_config/alacritty/alacritty.toml` becomes `~/.config/alacritty/alacritty.toml`.
- `dot_config/alacritty/themes/create_noctalia.toml` is a placeholder that Noctalia
  later overwrites with the active theme (a `create_` file is written once and
  never overwritten by chezmoi).
- `dot_config/noctalia/omadora.toml` becomes `~/.config/noctalia/omadora.toml` and
  includes the image's `/etc/xdg/noctalia/10-omadora.toml` (the idle timeouts and
  the default theme). Noctalia 5.6.0 or later reads that file on its own; Fedora
  44 ships 5.4.1, which does not, so this include is what loads it.
- `dot_config/niri/config.kdl` includes the image's `/etc/niri/config.kdl` and
  Noctalia's `~/.config/niri/noctalia.kdl` (also a `create_` placeholder).

System defaults for Niri and Noctalia live in the image (`/etc/niri`,
`/etc/xdg/noctalia`), not here, so image updates reach every user. Put only
per-user settings in this repository.
