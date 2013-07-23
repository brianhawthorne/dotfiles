# .bashrc

# Source global definitions
if [ -f /etc/bashrc ]; then
	. /etc/bashrc
fi

# User specific aliases and functions
export EDITOR=vim

force_color_prompt=yes

alias cirl2='ssh 169.229.248.232'

if [ "$TERM" != "dumb" ] && [ -x /usr/bin/dircolors ]; then
    eval "`dircolors -b`"
    alias ls='ls --color=auto'
fi

alias vi=vim
alias ll='ls -lh'
alias la='ls -A'
alias l='ls -CF'
alias less='less -R'
alias diff='colordiff'
alias grin='grin --use-color'
alias pylab='ipython -pylab'


# Eg. "apply ls /tmp /usr" runs "ls /tmp" then "ls /usr"
function apply ()
{
  cmd=$1
  shift
  for x in $*; do $cmd $x; done
}

# Build and install a cabal package locally
function haskell-build ()
{
  DIR=$1
  ( cd $DIR;
    runghc Setup.*hs configure --user --prefix=$HOME
    runghc Setup.*hs build
    runghc Setup.*hs install
  )
}

function pushdp () {
  pushd "$(python -c "import os.path as _, ${1}; \
    print _.dirname(_.realpath(${1}.__file__))"
  )"
}

function _activate {
    source $HOME/virtualenvs/$1/bin/activate
    cd $HOME/$1
}
#alias activate-project='_activate project'

export TERM=xterm-256color 
export OPCODEDIR=/usr/local/lib/csound/plugins
export CSSTRNGS=/usr/local/share/locale
export JAVA_HOME=/usr/lib/jvm/java-6-sun/

alias svndiff='svn diff --diff-cmd=colordiff | less'

