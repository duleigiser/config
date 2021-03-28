# on-my-zsh
```
# macOS 系统自带了zsh, 一般不是最新版，如果需要最新版可通过Homebrew来安装(确认安装了Homebrew)
brew install zsh zsh-completions


# 把zsh设为默认shell，如果shell列表中没有zsh或者你没有使用chsh权限的时候，不起作用
echo $SHELL    
[sudo] chsh -s $(which zsh)  或 chsh -s /bin/zsh

# 安装 oh my zsh 之前必须安装 zsh，否则会收到如下提示：Zsh is not installed! Please install zsh first!
# 通过git下载 
git clone git://github.com/robbyrussell/oh-my-zsh.git ~/.oh-my-zsh

# Oh-My-Zsh 的默认配置文件在：~/.zshrc。编辑～/.zshrc 修改主题，这里我用的是 ys 主题，更多主体看[这里](https://github.com/robbyrussell/oh-my-zsh/wiki/Themes)，直接修改即可，无需下载
ZSH_THEME="ys"
# !!!! 重启终端后有效 或 使用 source ~/.zshrc 更新配置

# 题外话，不太想显示主机名，所以直接干掉主机名
# 编辑 ~/.oh-my-zsh/themes/ys.zsh-theme，最后面改成这样
PROMPT="
%{$terminfo[bold]$fg[blue]%}#%{$reset_color%} \
%(#,%{$bg[yellow]%}%{$fg[black]%}%n%{$reset_color%},%{$fg[cyan]%}%n) \
%{$fg[white]%}in \
%{$terminfo[bold]$fg[yellow]%}%~%{$reset_color%}\
${hg_info}\
${git_info}\
 \
%{$fg[white]%}[%*] $exit_code
%{$terminfo[bold]$fg[red]%}$ %{$reset_color%}"
```

## oh-my-zsh 插件推荐

### autojump
```
# 安装步骤

# ------ mac -------
brew install autojump
vim ~/.zshrc
# 在文件里找到plugins，添加
plugins=(autojump)
# 在文件末尾添加
[[ -s $(brew --prefix)/etc/profile.d/autojump.sh ]] && . $(brew --prefix)/etc/profile.d/autojump.sh
source $ZSH/oh-my-zsh.sh
# 最后
source ~/.zshrc
```

### zsh-autosuggestion

```
# 安装
git clone git://github.com/zsh-users/zsh-autosuggestions $ZSH_CUSTOM/plugins/zsh-autosuggestions
vim ~/.zshrc
# 在文件里找到plugins，添加
plugins=(
  autojump
  zsh-autosuggestions
)
source ~/.zshrc
```

### zsh-syntax-highlighting 

`日常用的命令会高亮显示，命令错误显示红色`

```
# 安装
git clone git://github.com/zsh-users/zsh-syntax-highlighting $ZSH_CUSTOM/plugins/zsh-syntax-highlighting
vim ~/.zshrc
# 在文件里找到plugins，添加
plugins=(
  autojump
  zsh-autosuggestions
  zsh-syntax-highlighting
)
source ~/.zshrc
```
