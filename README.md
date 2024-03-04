# Starting Uxntal and Uf Forth.

This repository contains example code and excercises from the book ["Starting Forth"](https://www.forth.com/wp-content/uploads/2018/01/Starting-FORTH.pdf),
implemented in [Uxntal](https://wiki.xxiivv.com/site/uxntal.html) (`.tal`) and in [Uf Forth](https://gitlab.com/b2495/uf) (`.f`), separated by chapter.

## Uxn

### Installation

```zsh
$ git clone https://git.sr.ht/\~rabbits/uxn  # first time only
$ cd uxn
$ git pull  # updating only
$ mkdir ~/bin
$ ./build.sh --install
$ export PATH=~/bin:$PATH
```

### Configuration

```zsh
alias asm="~/bin/uxnasm"
alias cli="~/bin/uxncli"
alias emu="~/bin/uxnemu"
alias uxn="uxnemu ~/roms/boot.rom"
alias bug="uxnemu ~/roms/beetbug.rom"
alias lin="uxncli ~/roms/uxnlin.rom"
alias bal="uxncli ~/roms/uxnbal.rom"
alias rea="uxncli ~/roms/uxnrea.rom"
alias blim="uxncli ~/roms/drifblim.rom"
alias ufor="uxncli ~/roms/uxnfor.rom"

export PATH=~/bin:$PATH
```

## Uf

### Installation

```zsh
$ git clone https://gitlab.com/b2495/uf  # first time only
$ cd uf
$ git pull  # updating only
$ uxnasm kernel.tal kernel.rom
$ uxncli kernel.rom <uf.f
$ cp ufx.rom uf.rom uf0.rom ~/bin
$ sudo apt install rlwrap
```

### Configuration

```zsh
alias ufx="uxnemu ~/roms/ufx.rom"
alias uf="rlwrap uxncli ~/roms/uf.rom"
alias ufo="rlwrap uxncli ~/roms/uf0.rom"
```

## Update configuration

```zsh
$ micro ~/zshrc  # do edits
$ source ~/.zshrc
```
