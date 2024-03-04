# Starting Uxntal and Uf Forth.

This repository contains example code and excercises from the book ["Starting Forth"](https://www.forth.com/wp-content/uploads/2018/01/Starting-FORTH.pdf),
implemented in [Uxntal](https://wiki.xxiivv.com/site/uxntal.html) (`.tal`) and in [Uf Forth](https://gitlab.com/b2495/uf) (`.f`), separated by chapter.

## Uxn

### Installation

```zsh
$ git clone https://git.sr.ht/\~rabbits/uxn
$ cd uxn
$ mkdir ~/bin
$ ./build.sh --install  # copies executables to ~/bin
$ export PATH=~/bin:$PATH
```

### Updating

```zsh
$ cd uxn
$ git pull
$ ./build.sh --install
```

### Configuration

```zsh
alias asm="~/bin/uxnasm"
alias cli="~/bin/uxncli"
alias emu="~/bin/uxnemu"
alias uxn="uxnemu ~/roms/boot.rom"

export PATH=~/bin:$PATH
```

## Uf

### Installation

```zsh
$ git clone https://gitlab.com/b2495/uf
$ cd uf
$ uxnasm kernel.tal kernel.rom
$ uxncli kernel.rom <uf.f
$ cp ufx.rom uf.rom uf0.rom ~/bin
$ sudo apt install rlwrap
```

### Updating

```zsh
$ cd uf
$ git pull
$ uxnasm kernel.tal kernel.rom
$ uxncli kernel.rom <uf.f
$ cp ufx.rom uf.rom uf0.rom ~/bin
```

### Configuration

```zsh
alias ufx="uxnemu ~/roms/ufx.rom"
alias uf="rlwrap uxncli ~/roms/uf.rom"
alias ufo="rlwrap uxncli ~/roms/uf0.rom"
```

## Updating configuration

```zsh
$ micro ~/zshrc  # do edits
$ source ~/.zshrc
```
