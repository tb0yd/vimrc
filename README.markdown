The Best .vimrc Ever (tm)
---

## Installation:

You'll need vim compiled with Ruby support. To find out if your vim supports Ruby, run this:

    vim --version

If you see `+ruby`, you're good to go. If you see `-ruby`, then your vim doesn't have Ruby. On Ubuntu, you can get a version of vim with Ruby by running:

    sudo apt-get install vim-nox

If that doesn't work, you can compile from source. On Ubuntu, you can do:

    sudo apt-get install build-essential libncurses mercurial python python-dev ruby ruby-dev
    hg clone https://code.google.com/p/vim/
    ./configure --with-features=huge --enable-rubyinterp --enable-pythoninterp --with-python-config-dir=/usr/lib/python2.7-config --enable-perlinterp --enable-cscope --prefix=/usr
    make VIMRUNTIMEDIR=/usr/share/vim/vim74
    sudo make install

Now you can install the vimrc:

    mkdir ~/.vim
    git clone git://github.com/tmacwill/vimrc.git ~/.vim
    git clone https://github.com/gmarik/Vundle.vim.git ~/.vim/bundle/Vundle.vim
    ln -s ~/.vim/.vimrc ~/.vimrc
    vim +BundleInstall +qall
    cd ~/.vim/bundle/Command-T/ruby/command-t
    ruby extconf.rb
    make

Don't forget to create the undo directory:

    mkdir ~/.vim/undo

You'll also probably want ctags installed. On Ubuntu, you can do:

    sudo apt-get install ctags

## Color Schemes

The default color scheme is Slate, which comes with MacVim.

Other available (awesome) colorschemes:

* jellybeans
* skittles_dark
* molokai
* wombat256mod

## Font

These fonts are available: https://github.com/Lokaltog/powerline-fonts.

I personally like Monaco, size 13, because it helps my eyes not die while coding.

## Shortcuts

* ; maps to :
* ,a: ack from the current directory
* ,b: browse tags
* ,c: toggle comments
* ,C: toggle block comments
* ,e: open file in new tab
* ,l: toggle NERDTree
* ,h: open a shell in a new tab
* ,m: toggle mouse support
* ,p: toggle paste mode
* ,o: open file
* ,s: split window
* ,t: new tab
* ,w: close tab
* kj: enter normal mode and save
* Ctrl+{h,j,k,l}: move among windows
