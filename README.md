# 一、前期环境准备

## 1.1 准备conda

现在使用Python都推荐使用conda。conda是一个包管理工具，使用它的好处在于它可以帮助我们科学的管理我们在使用Python的时候所需要库，同时它还可以帮助我们创造Python环境，这样在不同的项目中，我们都可以使用不同的Python环境，彼此之间互不干扰。

目前Anaconda有两种版本，一种叫Anaconda，另一种叫Miniconda。二者的区别在于Anaconda预先帮助我们下好了很多科学计算需要的库文件，所以Anaconda比Miniconda大得多。由于我们后面环境配置中，会涉及到爬虫环境的准备过程，所以我们这里下载较小的Miniconda即可。Miniconda安装步骤如下：

- 去官网下载Miniconda安装包
- 安装到自己喜欢的位置

具体详细的安装步骤，可以百度，有很多写得很好的教程，这里就不再赘述。

## 1.2 创建爬虫虚拟环境

这里再给大家说一说虚拟环境的重要性，由于Python的版本有很多，同时Python各种库的环境也有很多，所以在不同的项目中可能会用到不同的版本信息。为了使各个项目之间互相不影响，那么我们选择为每个项目创建虚拟环境，这样就不用在运行不同的项目时，来回切换Python及其库文件了。

创建爬虫虚拟环境只需要一行代码，如下所示：

```shell
conda create -n SPIDER python=3.7 --file SpiderRequiments.txt
```

解释一下各参数的意义：

- conda create -n：这个是使用conda创建虚拟环境的命令

- SPIDER：这个是我们为爬虫虚拟环境取的名字，是自己定义的

- python=3.7：这个是我们指定的Python的版本

- --file SpiderRequiments.txt：添加了这句话后，虚拟环境在创建的时候，就会把SpiderRequirements.txt里所指定的库文件一同安装到虚拟环境中去，SpiderRequirements.txt的内容如下

  ```txt
  beautifulsoup4
  requests
  selenium
  jupyter
  notebook
  ```

## 1.3 准备visual studio code

visual studio code是微软推出的一款开源的跨平台编辑器，它集成了jupyter的运行环境，所以我们可以直接使用visual studio code打开jupyter notebook来写我们的爬虫代码。

visual studio code配置爬虫编辑环境的步骤如下：

- 安装python的扩展程序
- 打开一个工作目录，作为爬虫的工作目录
- 创建第一个文件，如00-SpiderDemo.ipynb：这个时候直接就进入了jupyter notebook的编辑界面
- 点击左下角，选择Python的虚拟环境，这里选择我们所创建的SPIDER

最后测试一下，输入

```python
import requests
print (requests.__version__)
```

如果能够输出版本信息，那么说明我们前期的搭建工作已经成功了，如下所示：

![GJPaIs.png](https://s1.ax1x.com/2020/04/02/GJPaIs.png)

## 1.4 Q&A

1. Q：为什么要使用visual studio code

   A：因为visual studio code是一个跨平台的，轻量级的，功能强大的编辑器，是目前广受程序员们推崇的编辑器。在学习Python爬虫的时候，visual studio code可以涵盖我们需要的所有功能，同时它安装方便，操作简单，运行快速。所以我们选择在visual studio code中学习爬虫。

2. Q：为什么要使用conda

   A：conda是Python中非常实用的工具，它可以帮助我们很好的管理我们本地的Python环境。打个比方，目前我们学习爬虫，我们可以在本地创建一个SPIDER虚拟环境，专门用来爬虫；如果今后我们要学习机器学习了，我们又可以在本地给机器学习专门创建一个虚拟环境。这两个项目有各自的环境，它们不会互相干扰。

3. Q：jupyter notebook是什么

   A：jupyter notebook是一个非常实用的交互式编辑页面，它本质上也是Python的一个库。有了它之后，我们可以一边写代码，一边写markdown文档，方便我们后期总结；同时，它可以以模块化运行我们的代码，方便我们即使的看到我们所写代码的输出内容。这在学习阶段，特别的重要。



# 二、开始学习爬虫

