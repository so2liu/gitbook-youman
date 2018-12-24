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

@[Zhihu](https://www.zhihu.com/question/21215715/answer/17540457)

## Maybe I will read...

* 如何系统地学习Node.js？  

  如果没有javascript基础建议先看「Eloquent Javascript」，篇幅不太长，可读性又比犀牛书好很多。  

  然后是nodejs的书，个人感觉刚开始接触的话看书不是很好的选择。之前曾经看过leanpub的nodejs入门和一点smashing node，感觉这些书上来就从架设http服务器开始是有点跑偏了。nodejs刚发布时展示的就是一个http服务器，包括现在nodejs官网首页例子也是这样。但如果你之前没有用其他语言做过服务器，理解例子里那些架构的内在逻辑和如何进行自己的变通不是一件容易的事。更何况很多人根本不需要架设服务器。  

  后来我上了 [http://nodeschool.io，跟着推荐教程完成了node基础和streaming的所有练习，才觉得豁然开朗了。nodejs原本就是关于io的语言，fs/stream/buffer](http://nodeschool.io，跟着推荐教程完成了node基础和streaming的所有练习，才觉得豁然开朗了。nodejs原本就是关于io的语言，fs/stream/buffer) 这些才是基础，而不是http。  

  后来学了gulp，就可以拿来做各种各样的项目构建工作了。gulp中可以很方便的使用各种npm包，研究这些包的源码，了解了大量nodejs原理和实战方式。这之后再看深入浅出nodejs之类的书，系统的补完知识结构。  

  作者：[王楠](https://www.zhihu.com/question/21567720/answer/43837344)

Maybe used later...

{% hint style="info" %}
Super-powers are granted randomly so please submit an issue if you're not happy with yours.
{% endhint %}

Once you're strong enough, save the world:

```text
// Ain't no code for that yet, sorry
echo 'You got to trust me on this, I saved the world'
```

