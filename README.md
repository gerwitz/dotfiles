# gerwitz does dotfiles

These are my [dotfiles](https://dotfiles.github.io/). There are many like them, but these are mine.

This is based on [Zach Holman's repository](https://github.com/holman/dotfiles/), so if you're looking for something similar, I suggest starting there.

## How it works

[zsh](http://www.zsh.org) is assumed.

Most of the folders are only for organization. A few files are special:

- **bin/**: Anything in `bin/` will get added to your `$PATH` and be made
  available everywhere.
- **Brewfile**: This is a list of applications for [Homebrew Cask](https://caskroom.github.io) to install: things like Chrome and 1Password and Adium and stuff. Might want to edit this file before running any initial setup.
- **topic/\*.zsh**: Any files ending in `.zsh` get loaded into your
  environment.
- **topic/path.zsh**: Any file named `path.zsh` is loaded first and is
  expected to setup `$PATH` or similar.
- **topic/completion.zsh**: Any file named `completion.zsh` is loaded
  last and is expected to setup autocomplete.
- **topic/install.sh**: Any file named `install.sh` is executed when you run `script/install`. To avoid being loaded automatically, its extension is `.sh`, not `.zsh`.
- **topic/\*.symlink**: Any file ending in `*.symlink` gets symlinked into
  your `$HOME`. This is so you can keep all of those versioned in your dotfiles
  but still keep those autoloaded files in your home directory. These get
  symlinked in when you run `script/bootstrap`.

## How I use it

```sh
git clone https://github.com/gerwitz/dotfiles.git ~/.dotfiles
cd ~/.dotfiles
script/bootstrap
```

## Keeping up to date

`dot` is in bin and does the needful.

## The shoulders of giants

There are many, many ways to do this. I forked Holman's because it meshed well with my needs and feels resilient. He in turn learned from others, but his contribution is most substantial so he remains listed in [LICENSE](LICENSE.md).
