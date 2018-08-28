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

### [fd](https://github.com/sharkdp/fd) install
  A simple, fast and user-friendly alternative to 'find'
  Download the latest .deb package from the [release page](https://github.com/sharkdp/fd/releases) and install it via
  ```
  sudo dpkg -i fd_7.0.0_amd64.deb
  ```
### [fzf](https://github.com/junegunn/fzf) install
  fuzzy finder , awesome tool !
  install via git
  ```
  git clone --depth 1 https://github.com/junegunn/fzf.git ~/.fzf
  ~/.fzf/install
  ```
### [PathPikcer](https://github.com/facebook/PathPicker) install
  Facebook PathPicker
  1. setup a app directory
  ```
  mkdir -p ~/.app/bin
  echo "# Setup fzf
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
  
  
  
  
  ## refer to
  * [awesome-cli-apps](https://github.com/agarrharr/awesome-cli-apps)
  * [awesome-command-line-apps](https://github.com/herrbischoff/awesome-command-line-apps)
  * [堪称神器的命令行](https://www.zhihu.com/question/59227720)
  
