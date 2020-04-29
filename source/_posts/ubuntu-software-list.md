
### 安装文泉驿微米黑字体
apt install fonts-wqy-icrohei

<!--More -->

### Install Git:
apt install git

output
``
将会同时安装下列软件：
  git-man liberror-perl
建议安装：
  git-daemon-run | git-daemon-sysvinit git-doc git-el git-email git-gui gitk
  gitweb git-cvs git-mediawiki git-svn
下列【新】软件包将被安装：
  git git-man liberror-perl
``

### chinese man pages:
sudo apt install manpages-zh

### Vim
sudo apt install vim ctags vim-doc vim-scripts


### Vim拷贝系统剪切板
先检查是否支持clipboard:
vim --version | grep clipboard

如果显示+Clipboard等字样，表示支持这一功能，此时可以用以下命令操作：
"+y 代替y将选中的内容复制到系统剪切板，效果同ctrl+C
"+p 代替p将剪切板中的内容复制到指定位置，效果同ctrl+V

如果需要用y直接代替"+y复制到剪切板，可以在.vimrc中配置：
vim ./vimrc
增加如下行：
set clipboard=unnamed

如果版本中不支持Clipboard，即出现-Clipboard。
先安装需要的软件包：
sudo apt install vim-gtk

