# Fedora安装美化

上操作系统的课，这老师非得装Linux，说起Linux,从初三那年我有一台笔记本开始，那笔记本安装Windows，真是没意思😞️，我就装了ubuntu，那时候Linux的distribution都玩遍了，那时候觉得deepin和elementory os的ui还可以，后来我才明白那时候是真的傻啊。不过玩了这么久的linux，还是只喜欢RPM系的和gnome这个桌面。好久没用没在笔记本💻️上面装linux了，是觉得OS X和Windows以及一台Fedora的服务器已经够用了。

![&#x7A33;&#x5B9A;&#x5F3A;&#x5927;](https://i.loli.net/2018/10/07/5bba12ea4c4d9.png)

## 下载安装镜像

* [官网](https://getfedora.org/zh_CN/)下载

![Fedora 28](https://i.loli.net/2018/10/07/5bba12ea4ffcb.png)

## 将安装镜像刷入到u盘

### 烧录镜像到u盘

* 使用dd命令\(macOS和Linux\)

  插入😎️U盘，查看分区`diskutil list`,如图，我的u盘被系统挂载到了_**/dev/disk3**_,现在要先卸载它，不然等下写盘的时候会提示设备忙的，`diskutil unmountDisk /dev/disk3`,好了，准备好你的镜像文件，键入如下命令：

```bash
sudo dd if=/path/to/imagefile of=/dev/disk3 bs=4m  #注意if是input file 的意思，of是out put 的意思，这里在键入if=后，将你的镜像文件拖入终端，of=后面接你要操作的磁盘，即我们的u盘
```

 由于没用加参数，所以在整个写入过程中不会有任何提示 

![&#x5199;&#x5165;&#x5B8C;&#x6BD5;](https://i.loli.net/2018/10/09/5bbcb01f4efb9.png)

![&#x5378;&#x8F7D;&#x78C1;&#x76D8;&#x5E76;&#x70E7;&#x5F55;&#x955C;&#x50CF;](https://i.loli.net/2018/10/09/5bbcb0535c3f6.png)

* 使用第三方工具

  这里推荐使用开源软件`etcher`,它支持的平台范围很广，包括`OS X`、`Linux`和`Windows`,[官网地址](https://etcher.io)

### 免u盘安装\(仅Windows下\)

* \(免u盘\)新建分区，fat32，将镜像文件解压到该分区，添加引导

## 开始安装，设置挂载点

* 设置引导分区
* 设置根分区

> 注意：但凡有修改源安装软件的在操作,在修改源之后都需要使用`sudo dnf update`更新,不然包管理工具会找不到软件的.

## 装机必备软件

首先，更新下系统\(建议\)  如果太大了，也没必要安装。  保持一颗平常心，你需要耐心等待。 

![&#x66F4;&#x65B0;](https://i.loli.net/2018/10/09/5bbcb1775d11a.png)

![&#x559D;&#x676F;&#x8336;&#xFF0C;&#x56DE;&#x6765;](https://i.loli.net/2018/10/09/5bbcb1baec65a.png)

![Update System](https://i.loli.net/2018/10/09/5bbcb11ed94c8.png)

* some useful software

  ```bash
  sudo dnf install vim git zsh curl screen wget nmap -y
  ```



![&#x5E38;&#x7528;&#x8F6F;&#x4EF6;](https://i.loli.net/2018/10/09/5bbcb21d09cca.png)



* google-chrome

  ```bash
  sudo dnf install fedora-workstation-repositories
  sudo dnf config-manager --set-enabled google-chrome
  sudo dnf update
  sudo dnf install google-chrome-stable #如果找不到包，退出当前shell重试安装
  ```

![&#x6700;&#x597D;&#x7684;&#x6D4F;&#x89C8;&#x5668;&#xFF0C;&#x6CA1;&#x6709;&#x4E4B;&#x4E00;](https://i.loli.net/2018/10/09/5bbcb65c583db.png)

## 安装主题管理器

* gnome tweak tool

  ```bash
  sudo yum -y install gnome-tweak-tool
  ```

## 图标主题更改

* paper图标

  ```bash
  sudo dnf config-manager --add-repo https://download.opensuse.org/repositories/home:snwh:paper/Fedora_25/home:snwh:paper.repo
  sudo dnf install paper-icon-theme
  ```

* papirus图标

  ```bash
  wget -qO- https://raw.githubusercontent.com/PapirusDevelopmentTeam/papirus-icon-theme/master/install.sh | sh
  ```

![papirus icon](https://i.loli.net/2018/10/09/5bbcb248b346d.png)

* materia主题 

  ```bash
  sudo dnf copr enable tcg/themes
  sudo dnf install materia-theme
  ```

![materia theme](https://i.loli.net/2018/10/09/5bbcb3ce63367.png)

在优化\(gnome-tweak\)中应用图标和主题 

![&#x5E94;&#x7528;&#x56FE;&#x6807;&#x548C;&#x4E3B;&#x9898;](https://i.loli.net/2018/10/09/5bbcb34e27dd1.png)

## 更换Shell

* Zsh 自带的`bash`功能没有那么强大，这里推荐安装zsh，`zsh`不仅功能强大，而且插件丰富，主题也特别多。

  ```bash
  sh -c "$(curl -fsSL https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"
  ```

* powerline

```bash
git clone https://github.com/jeremyFreeAgent/oh-my-zsh-powerline-theme.git powerline-theme
cd powerline-theme;./install_in_omz.sh
```

powerline还可以，不过感觉没powerlevel9k功能强大

* powerlevel9k

  作为一款`zsh`的主题，自定义功能极强，在github上面收获6k+的小星星。

 

![Fedora&#x66F4;&#x6362;Terminal&#x5B57;&#x4F53;](https://i.loli.net/2018/10/09/5bbcb4f5a0893.png)

![powerlevel9k](https://i.loli.net/2018/10/09/5bbcb7febebc3.png)

桌面环境美化后的效果。 

![&#x6700;&#x7EC8;&#x7F8E;&#x5316;&#x6548;&#x679C;](https://i.loli.net/2018/10/09/5bbcb553bf1a9.png)

## Vim插件安装

* Airline
* 插件管理系统

## 更换引导程序

* clover引导

  

![OS X](https://i.loli.net/2018/10/07/5bba0b1b776d3.png)

![&#x6CA1;&#x6709;fedora&#x7684;&#x56FE;&#x6807;&#xFF0C;&#x6211;&#x6362;&#x6210;freebsd&#x7684;&#x56FE;&#x6807;&#x4E86;](https://i.loli.net/2018/10/07/5bba0b1bcdd74.png)

![Clover&#x5F15;&#x5BFC;](https://i.loli.net/2018/10/07/5bba0b1c88f57.png)

