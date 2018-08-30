## install

### basic tool
```
  sudo apt install -y zsh vim git curl
```    

### oh-my-zsh
1. install [oh-my-zsh](https://github.com/robbyrussell/oh-my-zsh)
```
  sh -c "$(curl -fsSL https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"
```
2. change the default shell to zsh
```
  sudo chsh -s /bin/zsh
```
3. zsh [theme](https://github.com/robbyrussell/oh-my-zsh/wiki/themes)
```
  ZSH_THEME="ys"
```
4. zsh plugins install, more [awesome zsh plugins](https://github.com/unixorn/awesome-zsh-plugins)
  * [zsh-syntax-highlighting](https://github.com/zsh-users/zsh-syntax-highlighting)<br>
      ```
      git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting
      ```
  * [zsh-autosuggestions](https://github.com/zsh-users/zsh-autosuggestions)<br>
      ```
      git clone https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions
      ```
5. ~.zshrc config
  ```
    plugins=(
      git
      fasd
      syntax-highlighting
      zsh-autosuggestions
    )
  ```
### [fasd](https://github.com/clvv/fasd) install
  a tool keeps track of files and directories you have accessed
  ```
    sudo add-apt-repository ppa:aacebedo/fasd
    sudo apt-get update
    sudo apt-get install fasd
  ```
### [fzf](https://github.com/junegunn/fzf) install
  fuzzy finder , awesome tool !
  1. install via git
  ```
    git clone --depth 1 https://github.com/junegunn/fzf.git ~/.fzf
    ~/.fzf/install
  ```
  2. fzf config
  ```
    export FZF_DEFAULT_OPTS="--height 40% --layout=reverse --preview '(highlight -O ansi {} || cat {}) 2> /dev/null | head -500'"
  ```
### [PathPikcer](https://github.com/facebook/PathPicker) install
  Facebook PathPicker
  1. setup a app directory
  ```
    mkdir -p ~/.app/bin
    echo "# Setup app
          # ---------
          if [[ ! "$PATH" == */home/chen/.app/bin* ]]; then
            export PATH="$PATH:/home/chen/.app/bin"
          fi
        " > .app.zsh
  ```
  2. install via git
  ```
    git clone https://github.com/facebook/PathPicker.git ~/.app/fpp
    cd ~/.app/bin
    ln -s ~/.app/bin/fpp fpp
  ```
  3. add to zshrc
  ```
    [ -f ~/.app.zsh ] && source ~/.app.zsh
  ```
 ### [ag](https://github.com/ggreer/the_silver_searcher)(The Silver Searcher) 
   super fast grep
   ```
    sudo apt-get install silversearcher-ag
   ```
  
 ### [cheat.sh](https://github.com/chubin/cheat.sh)
  ```
    sudo apt install rlwrap
    curl https://cht.sh/:cht.sh > ~/.app/bin/cht.sh
    chmod +x ~/.app/bin/cht.sh
  ```
 
 ### vim with lua support
  install on Ubuntu 18.04.1 LTS
  1. install libary
  ```
    sudo apt-get install libncurses5-dev libgnome2-dev libgnomeui-dev \
      libgtk2.0-dev libatk1.0-dev libbonoboui2-dev \
      libcairo2-dev libx11-dev libxpm-dev libxt-dev python-dev \
      python3-dev ruby-dev lua5.1-dev libperl-dev
  ```
  2. install lua5.1
  ```
    wget http://www.lua.org/ftp/lua-5.1.5.tar.gz
    tar -xvf lua-5.1.5.tar.gz
    cd lua-5.1.5
    make
    make install
  
  ```
  3. remove old vim
  ```
    dpkg -l | grep vim
    sudo apt-get remove vim vim-common vim-runtime vim-tiny
  ```
  4. install vim via source
  ```
    git clone https://github.com/vim/vim.git
    cd vim
    ./configure --with-features=huge \
                --enable-multibyte \
                --enable-rubyinterp=yes \
                --enable-pythoninterp=yes \
                --with-python-config-dir=/usr/lib/python2.7/config \
                --enable-python3interp=yes \
                --with-python3-config-dir=/usr/lib/python3.6/config \
                --enable-perlinterp=yes \
                --enable-luainterp=yes \
                --enable-gui=gtk2 --enable-cscope --prefix=/usr
    make VIMRUNTIMEDIR=/usr/share/vim/vim81
    sudo make install
    
    #to check vim version
    vim --version | grep -E "lua|python"
  ```
  
  ## refer to
  * [awesome-cli-apps](https://github.com/agarrharr/awesome-cli-apps)
  * [awesome-command-line-apps](https://github.com/herrbischoff/awesome-command-line-apps)
  * [堪称神器的命令行](https://www.zhihu.com/question/59227720)
  * [the-art-of-command-line](https://github.com/jlevy/the-art-of-command-line)
