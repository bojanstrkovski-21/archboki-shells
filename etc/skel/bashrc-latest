## EXPORT ###
export EDITOR='nvim'
export VISUAL='nvim'
export HISTCONTROL=ignoreboth:erasedups
export PAGER='most'
export TERMINAL='kitty'

[ "$XDG_SESSION_DESKTOP" = "KDE" ] && export QT_QPA_PLATFORMTHEME="" || export QT_QPA_PLATFORMTHEME=qt6ct 

#Ibus settings if you need them
#type ibus-setup in terminal to change settings and start the daemon
#delete the hashtags of the next lines and restart
#export GTK_IM_MODULE=ibus
#export XMODIFIERS=@im=dbus
#export QT_IM_MODULE=ibus

#export DESKTOP_SESSION="chadwm_boki"
#export XDG_CURRENT_DESKTOP="chadwm-boki"

export PATH="$HOME/.emacs.d/bin:$PATH"
#export PATH="/usr/bin:$PATH"
# If not running interactively, don't do anything
[[ $- != *i* ]] && return
[[ -x $(command -v starship) ]] && eval "$(starship init bash)"
eval "$(zoxide init bash)"
eval "$(fzf --bash)"


#PS1='[\u@\h \W]\$ '

if [ -d "$HOME/.bin" ] ;
  then PATH="$HOME/.bin:$PATH"
fi

if [ -d "$HOME/.local/bin" ] ;
  then PATH="$HOME/.local/bin:$PATH"
fi

if [ $TILIX_ID ] || [ $VTE_VERSION ]; then
        source /etc/profile.d/vte.sh
fi
#ignore upper and lowercase when TAB completion
bind "set completion-ignore-case on"

### ALIASES ###



#create a file called .bashrc-personal and put all your personal aliases
#in there. They will not be overwritten by skel.

[[ -f ~/.bashrc-personal ]] && . ~/.bashrc-personal
[[ -f ~/.config/bash_aliases/arch-aliases ]] && . ~/.config/bash_aliases/arch-aliases
[[ -f ~/.config/bash_aliases/debian-aliases ]] && . ~/.config/bash_aliases/debian-aliases
[[ -f ~/.config/bash_aliases/fedora-aliases ]] && . ~/.config/bash_aliases/fedora-aliases
[[ -f ~/.config/bash_aliases/opensuse-aliases ]] && . ~/.config/bash_aliases/opensuse-aliases
[[ -f ~/.config/bash_aliases/void-aliases ]] && . ~/.config/bash_aliases/void-aliases
[[ -f ~/.config/bash_aliases/xmonad-aliases ]] && . ~/.config/bash_aliases/xmonad-aliases


# # ex = EXtractor for all kinds of archives
# # usage: ex <file>
ex ()
{
  if [ -f $1 ] ; then
    case $1 in
      *.tar.bz2)   tar xjf $1   ;;
      *.tar.gz)    tar xzf $1   ;;
      *.bz2)       bunzip2 $1   ;;
      *.rar)       unrar x $1   ;;
      *.gz)        gunzip $1    ;;
      *.tar)       tar xf $1    ;;
      *.tbz2)      tar xjf $1   ;;
      *.tgz)       tar xzf $1   ;;
      *.zip)       unzip $1     ;;
      *.Z)         uncompress $1;;
      *.7z)        7z x $1      ;;
      *.deb)       ar x $1      ;;
      *.tar.xz)    tar xf $1    ;;
      *.tar.zst)   tar xf $1    ;;
      *)           echo "'$1' cannot be extracted via ex()" ;;
    esac
  else
    echo "'$1' is not a valid file"
  fi
}



# reporting tools - install when not installed
#fastfetch
#neofetch
#screenfetch
#alsi
#paleofetch
#fetch
#hfetch
#sfetch
#ufetch
#ufetch-arco
#pfetch
#sysinfo
#sysinfo-retro
#cpufetch
#colorscript random
#hyfetch
#catnip
#seq 1 $(tput cols) | sort -R | sparklines | lolcat

#pamac
alias pamac-unlock="sudo rm /var/tmp/pamac/dbs/db.lock"

#create a file called .bashrc-personal and put all your personal aliases
#in there. They will not be overwritten by skel.

[[ -f ~/.bashrc-personal ]] && . ~/.bashrc-personal

# autoscripts
export PATH="$HOME/.local/bin/autoscripts":$PATH

export NVM_DIR="$HOME/.nvm"
[ -s "$NVM_DIR/nvm.sh" ] && \. "$NVM_DIR/nvm.sh"  # This loads nvm
[ -s "$NVM_DIR/bash_completion" ] && \. "$NVM_DIR/bash_completion"  # This loads nvm bash_completion


# Automatically do an ls after each cd, z, or zoxide
cd ()
{
	if [ -n "$1" ]; then
		builtin cd "$@" && ls
	else
		builtin cd ~ && ls
	fi  
}

export PYTHONPATH=~/.local/lib/python3/dist-packages/
export LD_LIBRARY_PATH=~/.local/lib/x86_64-linux-gnu/
export GI_TYPELIB_PATH=~/.local/lib/x86_64-linux-gnu/girepository-1.0/
export PATH=$PATH:~/.cargo/bin/

function my_ip() # Get IP adress.
{
   curl ifconfig.co
}

function sysinfo()   # Get current host related info.
{
    echo -e "\n${BRed}System Informations:$NC " ; uname -a
    echo -e "\n${BRed}Online User:$NC " ; w -hs |
             cut -d " " -f1 | sort | uniq
    echo -e "\n${BRed}Date :$NC " ; date
    echo -e "\n${BRed}Server stats :$NC " ; uptime
    echo -e "\n${BRed}Memory stats :$NC " ; free
    echo -e "\n${BRed}Public IP Address :$NC " ; my_ip
    echo -e "\n${BRed}Open connections :$NC "; netstat -pan --inet;
    echo -e "\n${BRed}CPU info :$NC "; cat /proc/cpuinfo ;
    echo -e "\n"
}

