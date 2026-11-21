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

System defaults for Niri and Noctalia live in the image (`/etc/niri`,
`/etc/xdg/noctalia`), not here, so image updates reach every user. Put only
per-user settings in this repository.
