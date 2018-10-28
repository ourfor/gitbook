# GitHub初级玩法

使用[Github](https://github.com)一年又余了，感觉_**GitHub**_还是非常好用的，在这个平台上不仅能学到很多东西，还能认识一些有意思的人。最近同学对GitHub很感兴趣，不知道该如何入门，顺手记录一下。这是一篇5000字+的多图长文\(**持续更新ING**\)。 

## `GitHub`是做什么的？

* GitHub是全球最大的同行社交平台，业界人称`GayHub`, 去年微软喜提全球最大的社交平台_**GitHub**_, 好吧，上面是来搞笑的😄, _**GitHub**_是一个代码托管的平台，类似于这样的平台还有`GitLab`、`Coding`、`Bitbucket`等等；之所以叫GitHub是因为它只支持`Git`这一种版本控制工具。GitHub这个单词拆分开来就是`Git`和`Hub`,用过`Usb Hub`的人都知道hub是一个类似集线器的东西。

[**Thank you for 10 years**](https://github.com/ten#)

## 开始使用GitHub

* [x] 注册GitHub账号
* [x] 建立Repo, 添加`ssh key`
* [x] git的简单使用以及一些GUI的GitHub客户端
* [x] Commit Histery 以及 issue
* [x] 如何编写README文件
* [x] 如何贡献代码-- Pull request
* [x] 如何为项目添加开源协议
* [x] 如何在GitHub上面写日记
* [x] 为项目添加web文档
* [x] 编译、部署以及添加贴纸

先准备写这些吧。 **多图警告**⚠️, 本博客文章配有大量图片, 请注意流量。

下面以全球最大的开源社区`GitHub`为例\(今年是GitHub十周年\)。

#### 注册GitHub账号

首先，在浏览器中打开[GitHub](https://github.com), 映入眼帘的是一只黑色章鱼🐙猫🐱，是不是和我的衣服上的标志差不多😝。



![GitHub](https://i.loli.net/2018/10/25/5bd139d1c1fc5.png)



* `Sign in`就是登陆啦，如果你注册了一个账号就直接登陆就是喽
* `Sign up`注册一个新的账号

![Sign up](http://p923bw9fi.bkt.clouddn.com/sing_up.png)

* `Username`填一个简单一点的英文名，因为以后你的博客可以通过`Username.github.io`来访问的，所以起一个好点的、不太长的名字就很有必要了，比如我的这个`Username`是`ourfor`,很短也很好记。
* `Email address`填个QQ邮箱📮也是OK的啦
* `Password`这个你懂得😳😳
* `step2和step3`这个由于我注册过了，我就没打开看了，你看着填吧。

> 这个B的英语我也是服了。

注册完登陆我们就来到了这样的一个界面：

  

![Home Page](https://i.loli.net/2018/10/25/5bd13b2126bbb.png)

我们打开页面右上角的`Setting`, 打开`Your Profile`, 就会跳转到我们的个人主页： 

![&#x4E0D;&#x8981;&#x76D7;&#x6211;&#x7684;&#x56FE;&#xFF0C;&#x518D;&#x76D7;&#x5C31;&#x5168;&#x7EFF;&#x4E86;&#x1F606;](https://i.loli.net/2018/10/25/5bd13c3caae63.png)

**下载git**

这里我们的主角登场了，就是[Git](https://git-scm.com/), 对于_**Unix-Like**_的操作系统, 就不用下载了, 直接从源安装就好了。对于`Windows`操作系统, 下载最新的[Git](https://github.com/git-for-windows/git/releases/download/v2.19.1.windows.1/Git-2.19.1-64-bit.exe)。

以Windows上面为例： 安装完我们的Git之后, 我们需要生成一对`SSH Key`, 打开安装的`Git bash`。

在`Windows10` 的搜索框中查找_**Git bash**_,或者点击Windows徽键，在最近添加中打开，在`Git bash`键入如下命令：

```bash
pwd                #print working directory显示当前路径。
```

**创建Repo**

新建一个`Repository`，点击页面上面的`New repository`

 

![New repository](http://p923bw9fi.bkt.clouddn.com/new_repository.png)



* 这个`Repository name`,你随意,不过并不建议用中文名.
* `Public`就是这个，点击`Create repository`就可以完成创建。
* `Description`可选，建议勾选☑️`Initialize this repository with a README`

这时候就会打开仓库主页，依次点击页面右侧的`Clone or download`、`Use SSH`复制框中的`Repo`地址，待会要用。

**添加部署密钥.**

打开`Git bash`，输入`ssh-keygen -t rsa -C "2320813747@qq.com"`,这个邮箱地址换成你的。连续四次回车就生成了一对密钥。

```bash
Your identification has been saved in /c/Users/zip/.ssh/id_rsa.
Your public key has been saved in /c/Users/zip/.ssh/id_rsa.pub.
```

它会告诉你密钥生成在那个文件夹,上面是我的密钥生成路径，下面要相应替换成你的，使用`cat`来查看公钥内容：

```bash
cat /c/Users/zip/.ssh/id_rsa.pub
```

复制输出的内容，打开`GitHub`，点击页面右侧头像旁边的倒三角，打开`Settings`，在页面左侧的`Personal settings`下面定位到`SSH and GPG keys`这一栏,点击右侧的`New SSH key`来添加一个密钥，其中`Title`随意,`Key`填写上一步`Git bash`里面生成的那个。最后`Add SSH key`就行了。

![Add SSH keys](https://i.loli.net/2018/10/25/5bd15a0c89c96.png)

#### git的简单使用

**git命令**

下面命令均在`Git bash`或`Terminal`中执行。 打开我们的项目仓库页面, 复制仓库地址。将远程仓库克隆到本地计算机：

 

![Repo Address](https://i.loli.net/2018/10/25/5bd188e2f1e3c.png)



```bash
git clone git@github.com:ourfor/Java_note.git # 使用ssh方式clone, 那么你必须在该仓库中添加你的ssh key, 所以对于别人项目你只能使用https的方式clone。
或
git clone https://github.com/ourfor/Java_note.git
```

接下来我们为Repo添加文件, 这里我使用数据流重定向来创建一个文件。

```bash
echo -e "hello world" > firstfile.c # 你没必要这么骚吧, 直接在文件管理器里面移个文件进去不就好了
```

是不是这样我们放在项目目录下的文件就变成我们的项目文件了呢？肯定不是啊, 那我不是随便放个文件都能改变你的项目文件了, 再者, 版本控制肯定是会有版本记录的啊！这时候我们就需要手动添加文件到我们的项目文件了。

```bash
git add firstfile.c # 添加firstfile.c到项目
```

如果每次这样添加不麻烦吗？有时候我都不知道生成了什么文件, 更简易的方法是每次添加项目目录里面的所有文件：

```bash
git add . # 或者git add -A A就是all的缩写
```

**GUI的GitHub客户端**

对于GitHub的GUI客户端我是比较推荐[GitKraken](https://www.gitkraken.com/)尽管它在我的电脑里面已经打入冷宫很长一段时间了, 不过它确实比Web端的美观一点, 对各个平台的支持都比较好。还是比较习惯用git的命令来管理.

![GitKraken](https://i.loli.net/2018/10/25/5bd15c3865a22.png)

#### 如何编写README文件

READMD文件作为我们项目的一个说明文件, 我们如何编辑README文件,才能让它美观简洁呢？README文件以后缀.md结尾，它支持markdown语法，同时支持部分html语法，在每个repo中，它会自动解析README.md这个文件.

由于经常使用markdown写笔记和文章,都已经形成自己的风格了,所以下面的语法介绍是我经常使用的, 有很多等价的语法，不再此处一一列举 Markdown语法： 一级标题: \# 二级标题: \#\# 等等...

```text
# 算法概述
## 递归与分治策略
```

加粗: **第一个认识的人就是你**

```text
**第一个认识的人就是你**
```

倾斜: _很高兴_

```text
*很高兴*
```

加粗并倾斜: _**nice**_

```text
***nice***
```

插入代码：

* 插入c语言代码：

  ```c
  #include <iostream>
  #include <stdio.h>
  int main(){
    printf("Hello world\n");
    return 0;
  }
  ```

```text
```c
#include <iostream>
#include <stdio.h>
int main(){
    printf("Hello world\n");
    return 0;
}
```

```text
- 插入shell命令
```bash
sudo dnf install git -y
sudo dnf update -y
```

```text
```bash
sudo dnf install git -y
sudo dnf update -y
```

```text
规则就是三个反引号+需要` 语法高亮 `的<strong>语言类型</strong>

引用书中的话或名人名言:

<blockquote class="normal">书籍是人类进步的阶梯 ---- 高尔基</blockquote>

```markdown
> 书籍是人类进步的阶梯 ---- 高尔基
```

小黑点:

* 你还是这么好看

```text
- 你还是这么好看
```

任务列表\(有x显示为勾选，留空表示不勾选\):

* [x] 高等数学
* [ ] 线性代数

```text
- [x] 高等数学
- [ ] 线性代数
```

反白:

```text
` root ` 在Unix/Linux操作系统中是指具有最高权限的用户
```

`root` 在Unix/Linux操作系统中是指具有最高权限的用户

删除线:

```text
~~~浮生若梦, 为欢几何.~~~
```

~~~浮生若梦, 为欢几何.~~~

文章分割线:

```text
---
```

插入图片:

```text
![life](https://i.loli.net/2018/10/06/5bb815d8e14fd.jpg)
```

![life](https://i.loli.net/2018/10/06/5bb815d8e14fd.jpg)

* 方括号内部是对图片的描述，在github是不会显示出来的,也就是html中的alt
* 圆括号里面的网址可以是图片的绝对路径地址也可以是相对路径

添加超链接: [GitHub](https://github.com)

```text
[GitHub](https://github.com)
```

表格:

```text
|这是表头|A|B|
|:-|-:|:-:|
|h|a|b|
```

实际效果:

| 这是表头 | A | B |
| :--- | ---: | :---: |
| h | a | b |

* `:-` 这是左对齐
* `-:` 这是右对齐
* `:-:` 这是居中对齐

显然这种表格是很简单的, 对于更加复杂的表格, markdown就有点心有余而力不足了, 还好兼容html, 我们就可以用html的方式插入表格:



|  | 星期一 | 星期二 | 星期三 | 星期四 | 星期五 |
| :--- | :---: | :---: | :---: | :---: | :---: |
| 第一节 | 高等数学A\(理化214\) | 线性代数\(理化327\) | 软件综合\(一\)\(机房\) | 程序设计基础\(理化327\) | 软件综合\(一\)\(机房\) |
| 第二节 |  |  |  |  |  |
| 第三节 | 程序设计基础\(理化327\) | 大学英语\(至105\) | 大学体育\(体育馆\) |  |  |
| 第四节 |  |  |  |  |  |
| 午安 | 我的课表居然这么满🍎🍏🍐🍑🍒🍓🥝🍅 |  **** |  |  |  |
| 第五节 | 程序设计基础\(机房\) | 面向对象软件方法学\(至308\) | 算法分析与设计\(至308\) |  | 操作系统\(至116\) |
| 第六节 |  |  |  |  |  |
| 第七节 |  |  |  |  |  |
| 第八节 |  |  |  |  |  |
| 傍晚 | 认识你真好🍇🍈🍉🍊🍋🍌🍍 |  |  |  |  |
| 第一节 | Java校选课\(至502\) |  |  |  | 概率论与数理统计\(至117\) |
| 第二节 |  |  |  |  |  |
| 第三节 |  |  |  |  |  |

**HTML代码** 

```markup
<table>
<th>
  <td align=center>星期一</td>
  <td align=center>星期二</td>
  <td align=center>星期三</td>
  <td align=center>星期四</td>
  <td align=center>星期五</td>
  </th>
  <tr>
  <td>第一节</td>
  <td align=center rowspan=2>高等数学A(理化214)</td>
  <td align=center rowspan=2>线性代数(理化327)</td>
  <td align=center rowspan=4>软件综合(一)(机房)</td>
  <td align=center rowspan=2>程序设计基础(理化327)</td>
  <td align=center rowspan=4>软件综合(一)(机房)</td>
  </tr>
  <tr>
  <td>第二节</td>
  </tr>
  <tr>
  <td>第三节</td>
  <td align=center rowspan=2>程序设计基础(理化327)</td>
  <td align=center rowspan=2>大学英语(至105)</td>
  <td align=center rowspan=2>大学体育(体育馆)</td>
  </tr>
  <tr>
  <td>第四节</td>
  </tr>
  <tr>
  <td align=center>午安</td>
  <td align=center colspan=5>我的课表居然这么满🍎🍏🍐🍑🍒🍓🥝🍅</td>
  </tr>
  <tr>
  <td>第五节</td>
  <td align=center rowspan=4>程序设计基础(机房)</td>
  <td align=center rowspan=3>面向对象软件方法学(至308)</td>
  <td align=center rowspan=3>算法分析与设计(至308)</td>
  <td></td>
  <td align=center rowspan=3>操作系统(至116)</td>
  </tr>
  <tr>
  <td>第六节</td>
  <td></td>
  
  </tr>
  <tr>
  <td>第七节</td>
  <td></td>
  </tr>
  <tr>
  <td>第八节</td>
  <td></td>
  <td></td>
  <td></td>
  <td></td>
  </tr>
  <tr>
  <td align=center>傍晚</td>
  <td align=center colspan=5>认识你真好🍇🍈🍉🍊🍋🍌🍍</td>
  </tr>
  <tr>
  <td>第一节</td>
  <td align=center rowspan=3>Java校选课(至502)</td>
  <td></td>
  <td></td>
  <td></td>
  <td align=center rowspan=3>概率论与数理统计(至117)</td>
  </tr>
  <tr>
  <td>第二节</td>
  <td></td>
  <td></td>
  <td></td>
  </tr>
  <tr>
  <td>第三节</td>
  <td></td>
  <td></td>
  <td></td>
  </tr>
</table>
```

数学公式:

> 数学是科学的语言, 学习笔记里面怎么可以没有数学公式呢？

* `\\(a + b\\)`

  \\(a + b\\) 

* `$$a + b$$`

  $$a + b$$ 

* `$$\sum_{i=0}^n i^2 = \frac{(n^2+n)(2n+1)}{6}$$`

  $$\sum_{i=0}^n i^2 = \frac{(n^2+n)(2n+1)}{6}$$

* `$$\mathscr{ABCDEFGHIJKLMNOPQRSTUVWXYZ}$$`

  $$\\mathscr{ABCDEFGHIJKLMNOPQRSTUVWXYZ}$$ 

markdown编辑的时候最好用`$`符号括起来。否则就需要转义字符 比如一个`$`就是是这样:`$\sum_{i=0}^n i^2 = \frac{(n^2+n)(2n+1)}{6}$`:

$\sum\_{i=0}^n i^2 = \frac{\(n^2+n\)\(2n+1\)}{6}$

`$$\sum_{i=0}^n i^2 = \frac{(n^2+n)(2n+1)}{6}$$` $$\sum_{i=0}^n i = \frac{n+1}{2}$$

原本语法中两个`\\`, 你还需要加一个`\`来转义:

$$
\begin{pmatrix}
    1 & a_1 & a_1^2 & \cdots & a_1^n \\\
    1 & a_2 & a_2^2 & \cdots & a_2^n \\\
    \vdots  & \vdots& \vdots & \ddots & \vdots \\\
    1 & a_m & a_m^2 & \cdots & a_m^n    
    \end{pmatrix}
$$

我不是学**数学**的所以我很少用数学公式，如果你对数学公式的用法感兴趣你可以看看[Mathjax官网](https://www.mathjax.org/)的说明。一般的markdown编辑器和解析器都支持`Mathjax`

$$
\begin{pmatrix}
    🍇 & 🍈 & 🍉 & 🍊 \\\
    🍋 & 🍌 & 🍍 & 🍎 \\\
    🍏 & 🍐 & 🍑 & 🍒 \\\
    🍓 & 🥝 & 🍅 & 😳  
    \end{pmatrix}
$$

