# Starting UXN Tal and UF Forth.

This repository contains example code and excercises from the book ["Starting Forth"](https://www.forth.com/wp-content/uploads/2018/01/Starting-FORTH.pdf),
implemented in [Uxntal](https://wiki.xxiivv.com/site/uxntal.html) (`.tal`) and in [Uf Forth](https://gitlab.com/b2495/uf) (`.f`), separated by chapter.

## UXN

### Installation

```zsh
$ git clone https://git.sr.ht/\~rabbits/uxn
$ cd uxn
$ mkdir ~/bin
$ sudo apt install libsdl2-dev wget  # Ubuntu
$ pkg install sdl2 wget              # Android Termux
$ ./build.sh --install               # copies executables to ~/bin
$ cp boot.rom ~/roms
$ export PATH=~/bin:$PATH
$ cd ~/.config/micro
$ mkdir syntax && cd syntax
$ # Setup UXN Tal syntax highlighting for the micro editor.
$ wget https://hacklab.nilfm.cc/dotfiles/raw/main/micro/syntax/uxn.yaml
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
# ~/.zshrc
alias asm="~/bin/uxnasm"            # assembler
alias cli="~/bin/uxncli"            # command line interface
alias emu="~/bin/uxnemu"            # graphical emulator
alias uxn="uxnemu ~/roms/boot.rom"  # Varvara's Potato OS

export PATH=~/bin:$PATH
```

### Workflow

```zsh
$ micro file-name.tal
$ uxnasm file-name.tal fil-name.rom && uxncli file-name.rom
$ uxncli rom-name.rom &> file-name.txt
```

## UF

### Installation

```zsh
$ git clone https://gitlab.com/b2495/uf
$ cd uf
$ uxnasm kernel.tal kernel.rom
$ uxncli kernel.rom <uf.f
$ cp ufx.rom uf.rom uf0.rom ~/roms
$ sudo apt install rlwrap                 # CLI REPL readline editing support
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
# ~/.zshrc
alias ufx="uxnemu -2x ~/roms/ufx.rom"     # core + uxn + graphical
alias uf="rlwrap uxncli ~/roms/uf.rom"    # core + uxn
alias ufo="rlwrap uxncli ~/roms/uf0.rom"  # core
```

## Updating configuration

```zsh
$ micro ~/zshrc    # do edits
$ source ~/.zshrc  # reload configs
```

### Workflow

```zsh
$ micro file-name.fth  # edit code
$ uf < file-name.fth   # give uf a file to read as code (exits when finished though!)
$ uf                   # repl + copy paste code
```
