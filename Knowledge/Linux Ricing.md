#index
+ [[Arch Linux Install Guide]]
+ [[Post Installation Software]]
+ [[Manage Dot Files]]
## TODO With my system

+ Aplicaciones para ver imágenes
+ cups para concectar impresoras
+ Portapapeles ?
+ Emoji selector ?
+ Trash management ?
+ aliases for zsh:
```
sudo pacman -Rns -> p remove (lo mismo con paru)

# simplify
alias p="sudo pacman -S"
alias icat="kitty +kitten icat"
alias copy="xclip -sel clip "

# terminal color output
alias ls="lsd"
alias ll="lsd -l"
alias cat="bat"
alias diff='diff --color=auto'
alias grep='grep --color=auto'
alias ip='ip -color=auto'
export LESS='-R --use-color -Dd+r$Du+b'

#trash managment
alias tr="trash-put"
alias rm="trash-put" 
alias trl="trash-list"
alias trr="trash-restore"

#dotfiles git
alias dot-git='/usr/bin/git --git-dir=$HOME/.dotfiles_repo/ --work-tree=$HOME'
```