# Starting Uxntal and Uf Forth.

This repository contains example code and excercises from the book ["Starting Forth"](https://www.forth.com/wp-content/uploads/2018/01/Starting-FORTH.pdf),
implemented in [Uxntal](https://wiki.xxiivv.com/site/uxntal.html) (`.tal`) and in [Uf Forth](https://gitlab.com/b2495/uf) (`.f`), separated by chapter.

## Uxn

### Installation

```zsh
$ git clone https://git.sr.ht/\~rabbits/uxn
$ cd uxn
$ mkdir ~/bin
$ sudo apt install libsdl2-dev  # Ubuntu
$ ./build.sh --install          # copies executables to ~/bin
$ cp boot.rom ~/roms
$ export PATH=~/bin:$PATH
```

### Updating

```zsh
$ cd uxn
$ git pull
$ ./build.sh --install
$ cp boot.rom ~/roms
```

### Configuration

```zsh
alias asm="~/bin/uxnasm"            # assembler
alias cli="~/bin/uxncli"            # command line interface
alias emu="~/bin/uxnemu"            # graphical emulator
alias uxn="uxnemu ~/roms/boot.rom"  # Varvara's Potato OS

export PATH=~/bin:$PATH
```

### Workflow

```zsh
$ edit file-name.tal
$ uxnasm file-name.tal rom-name.rom && uxncli rom-name.rom
$ uxncli rom-name.rom > file-name-output.txt
```

## Uf

### Installation

```zsh
$ git clone https://gitlab.com/b2495/uf
$ cd uf
$ uxnasm kernel.tal kernel.rom
$ uxncli kernel.rom <uf.f
$ cp ufx.rom uf.rom uf0.rom ~/roms
$ sudo apt install rlwrap  # for read line editing support
```

### Updating

```zsh
$ cd uf
$ git pull
$ uxnasm kernel.tal kernel.rom
$ uxncli kernel.rom <uf.f
$ cp ufx.rom uf.rom uf0.rom ~/roms
```

### Configuration

```zsh
alias ufx="uxnemu ~/roms/ufx.rom"         # core + uxn + graphical
alias uf="rlwrap uxncli ~/roms/uf.rom"    # core + uxn
alias ufo="rlwrap uxncli ~/roms/uf0.rom"  # core
```

## Updating configuration

```zsh
$ micro ~/zshrc  # do edits
$ source ~/.zshrc
```
