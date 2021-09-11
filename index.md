# iterm2配置教程
我相信很多人都想要一个自己喜欢的自定义风格的终端，iterm2是一个特别好的选择，能够配置出比原生终端颜值更高的系统。这个博客也是写给我自己的，因为自己也很容易忘记怎么配置这个终端。
## 第一步 下载
首先可以去官网下载iterm2，链接 https://iterm2.com/.

## 第二步 配置
把iterm2配制成默认终端

![image](https://user-images.githubusercontent.com/35141949/132940596-f2f1df03-fef6-4e57-a976-1727e4e51415.png)

之后可以配置一下iterm2的theme。
在这里推荐一个网络中比较受欢迎的主题，可通过该网址下载 https://ethanschoonover.com/solarized/
下载完以后，手动打开Preferences页面或者同时按 'command' 和 ','按钮快捷键打开，然后根据以下步骤引入主题
```
Profile=>Colors=>Color Presets=>Import
```

## 第三步 下载oh-my-zsh
首先通过
```
cat /etc/shells
```
查看是否已经有zsh，有的话就直接去下载oh-my-zsh，没有的话还是需要下载zsh的
通过
```
chsh -s /bin/zsh
```
切换到zsh

下载on-my-zsh 链接 https://ohmyz.sh/#install 就是引用以下的命令即可安装。
```
$ sh -c "$(curl -fsSL https://raw.github.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```
接下来可运行
```
vim ~/.zshrc
```
把主题改成下图推荐的主题（当然可以自己在找喜欢的主题）

![image](https://user-images.githubusercontent.com/35141949/132941209-071185a7-c6ea-498e-aeef-3a9d0961af62.png)


## 第四步 需要下载字体
因为存在乱码的情况，需要通过下载字体并且引入到iterm2才能解决问题。
下载字体的地址 https://github.com/powerline/fonts
```
git clone https://github.com/powerline/fonts.git
cd fonts
./install.sh
```
这样就安装好字体了
这个时候你就可以在preferences中找到下载字体的选项了

![image](https://user-images.githubusercontent.com/35141949/132941708-63fe7239-b6da-4ebe-ada3-5640addb0eb3.png)

## 第五步 高亮
我通过看别人的推荐方式有两种
第一种：
下载插件
```
git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting
```
并在/.zshrc中的
![image](https://user-images.githubusercontent.com/35141949/132941916-bd4cda7e-4362-49e0-af00-9947d28930b0.png)

这个位置添加插件名字 “zsh-syntax-highlighting“
然后重启终端

第二种：
执行以下命令
```
brew install zsh-syntax-highlighting
```
下载好以后可以在/.zshrc最后一行添加
```
source /具体安装地址/zsh-syntax-highlighting.zsh
```
然后执行
```
source /.zshrc
```

## 第六步 自动补充
先执行以下命令
```
git clone git://github.com/zsh-users/zsh-autosuggestions $ZSH_CUSTOM/plugins/zsh-autosuggestions
```
然后去/.zshrc中根据下图进行修改

![image](https://user-images.githubusercontent.com/35141949/132942068-e5ccf7ce-77b0-4506-95b8-91cc25cf900d.png)

之后source /.zshrc就可以自动实现补充了。
