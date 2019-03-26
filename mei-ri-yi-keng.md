# 每日一坑

## Git

### Merge conflicts: try **meld**

Configuration

```text
$ sudo apt-get install meld
$ git config --global merge.tool meld
```

Usage

```text
$ git mergetool
```

[@Zhihu](https://www.zhihu.com/question/21215715/answer/17540457)

### Adding SSH key to SSH agent

1. Start the ssh-agent in the background. `eval "$(ssh-agent -s)"`
2. `ssh-add ~/.ssh/id_rsa`

## Latex

* `no 'ngerma' error`:   

  `sudo apt-get texlive-lang-german`

* `no 'siunitx.sty' error`:   

  `sudo apt-get texlive-science`  

### Pseudocode

[@LatexWiki](https://en.wikibooks.org/wiki/LaTeX/Algorithms)

The package is loaded like  
`\usepackage[]{algorithm2e}`  
and a simple example, taken from the v4.01 manual, is

```text
\begin{algorithm}[H]
 \KwData{this text}
 \KwResult{how to write algorithm with \LaTeX2e }
 initialization\;
 \While{not at end of this document}{
  read current\;
  \eIf{understand}{
   go to next section\;
   current section becomes this one\;
   }{
   go back to the beginning of current section\;
  }
 }
 \caption{How to write algorithms}
\end{algorithm}
```

## VS Code

### Install

Do not use version from _Ubuntu Sotfware_. It's a snap version and you can't use pinyin input in it. Downloading from [official link](https://code.visualstudio.com/download) can avoid this.

Use `code` in terminal.

### Remove snap VS Code

If sadly, you have already installed vscode by snap:

```text
sudo snap remove vscode
hash -r
```

The second command will remove all saved command locations and make `code` =&gt; original vscode again.

## [Gadgetron](http://gadgetron.github.io/)

### Install JDK and HDF Viewer

> sudo apt-get install hdfviewer ==&gt; `[warning] /usr/bin/hdfview: JVM flavor 'sun' not understood`

Follow [this](https://blog.csdn.net/Solomon1558/article/details/52490910).

1. Install JDK, add to PATH
2. `sudo apt-get install hdfviewer` still doesn't work. 
3. Installing beta version 3.0.0 following [this](https://askubuntu.com/questions/907159/hdfview-working-in-ubuntu-17-04) works. 

### Tips

* Please use `conda activate` instead of direct run. \(Can't install by `cmake` =&gt; only install by `conda` =&gt; use `conda` environment\)

## ISMRMRD

Use `conda install -c inati ismrmrd-python` install `ismrmrd`.  
Don't know why but from `cmake` installation, `import ismrmrd` doesn't work.

## Anaconda

### Init

CommandNotFoundError: Your shell has not been properly configured to use 'conda activate'.  
If your shell is Bash or a Bourne variant, enable conda for the current user with

`$ echo ". /home/so2liu/anaconda3/etc/profile.d/conda.sh" >> ~/.bashrc`

or, for all users, enable conda with

`$ sudo ln -s /home/so2liu/anaconda3/etc/profile.d/conda.sh /etc/profile.d/conda.sh`

The options above will permanently enable the 'conda' command, but they do NOT put conda's base \(root\) environment on PATH. To do so, run

`$ conda activate`

## Server in ISS

### pip

In `linse3`, `pip` is for `python 3.4`. \(Use `pip --version` to ensure this.\) Use `pip3 install xxx --user` to install module for `python 3.6` local user.

## Python
- In order to import py document in subfolder, there must be a `__init__.py` (even empty) in subfolder. This could solve the error such as `ImportError: No module named motion.CNN2D`. 

- `seaborn` save figure to pdf:
```
ax = sns.heatmap(time_matrix, annot=True, fmt=".2f", linewidths=.5, xticklabels=train_len_set, yticklabels=data_set_set)
fig = ax.get_figure()
fig.savefig('nn_time.pdf', dpi=400)
``` 

## Maybe I will read...

### 如何系统地学习Node.js？

如果没有javascript基础建议先看「Eloquent Javascript」，篇幅不太长，可读性又比犀牛书好很多。

然后是nodejs的书，个人感觉刚开始接触的话看书不是很好的选择。之前曾经看过leanpub的nodejs入门和一点smashing node，感觉这些书上来就从架设http服务器开始是有点跑偏了。nodejs刚发布时展示的就是一个http服务器，包括现在nodejs官网首页例子也是这样。但如果你之前没有用其他语言做过服务器，理解例子里那些架构的内在逻辑和如何进行自己的变通不是一件容易的事。更何况很多人根本不需要架设服务器。

后来我上了 [Nodeschool](http://nodeschool.io)，跟着推荐教程完成了node基础和streaming的所有练习，才觉得豁然开朗了。nodejs原本就是关于io的语言，fs/stream/buffer这些才是基础，而不是http。

后来学了gulp，就可以拿来做各种各样的项目构建工作了。gulp中可以很方便的使用各种npm包，研究这些包的源码，了解了大量nodejs原理和实战方式。这之后再看深入浅出nodejs之类的书，系统的补完知识结构。

作者：[王楠](https://www.zhihu.com/question/21567720/answer/43837344)

### [GTD 入门应该从哪些资料开始？](https://www.zhihu.com/question/23051794)

如果你是初学时间管理，千万别从GTD开始，那东西根本就不是初学者应该接触的东西，GTD这个系统本来也不是给初学者用的，整个系统过于复杂，难度过高.  
初学者应该学什么：

* 番茄工作法：学会快速集中注意力，尽量一次完成一次事。
* 要事第一：坚持每天完成第二象限（重要而不紧急）的事情。每天完成3-6件要事。
* 做好周回顾：每周花上一定时间对本周的事情做个总结和回顾。  

时间管理初入门时一定别太复杂，规则越简单越好，找一些轻量化的效率工具来使用。

我在微信（read01）上发起的100天行动，完全符合这几项，只要你能坚持100天，时间管理就入门了，当你把这几件事形成习惯之后，再把精力放在GTD上，成功的机会能大一点。

100天行动规则：  
1. 每天坚持完成三个番茄工作法，一次只做一件事。  
2. 每天在早上10点半前完成当天工作中最重要的三件事，这三件事你可以在早上决定这件事是什么？  
3. 梦想番茄：每天用最少1个番茄时间完成你的梦想、重要而不紧急或你一直想做而没有行动的事情，比如学门新的技能、运动、外语、阅读。具体的事情你自己行动。  
这三项必须要选择一项进行，每天记录，每周总结。最好在手机用印象笔记之类的软件来记录.

作者：[warfalcon](https://www.zhihu.com/question/23051794/answer/24689356)

May be useful later...

{% hint style="info" %}
Super-powers are granted randomly so please submit an issue if you're not happy with yours.
{% endhint %}

Once you're strong enough, save the world:

```text
// Ain't no code for that yet, sorry
echo 'You got to trust me on this, I saved the world'
```

