# Markdown Usage（编辑模式查看源码）


1、标题的几种写法：

第一种：

前面带#号，后面带文字，分别表示h1-h6,上图可以看出，只到h6，而且h1下面会有一条横线，注意，#号后面有空格
# 标题1
## 标题2
### 标题3
#### 标题4
##### 标题5
###### 标题6

第二种：

标题1
========
标题2
-------
这种方式好像只能表示一级和二级标题，而且=和-的数量没有限制，只要大于一个就行

第三种：

# 标题1 #
## 标题2 ##
### 标题3 ###
#### 标题4 ####
##### 标题5 #####
###### 标题6 ######


这里的标题支持h1-h6，为了减少篇幅，我就偷个懒，只写前面二个，这个比较好理解，相当于标签闭合，注意，标题与#号要有空格

那既然3种都可以使用，可不可以混合使用呢？我试了一下，是可以的，但是为了让页面标签的统一性，不建议混合使用，推荐使用第一种，比较简洁，全面

为了搞清楚原理，我特意在网上搜一下在线编写markdown的工具，发现实际上是把这些标签最后转化为html标签，如图：



在线地址请看这里： markdown在线编辑 （只是想看看背后的转换原理，没有广告之嫌）

2、列表

我们都知道，列表分为有序列表和无序列表，下面直接展示2种列表的写法：

###无序列表
* 1
* 2
* 3
+ 1
+ 2
+ 3
- 1
- 2
- 3

可以看到，无序列表可以用* ， + ， — 来创建，用在线编辑器看，实际上是转换成了ul>li ，所以使用哪个都可以，推荐使用*吧

    

有序列表就相对简单一点，只有这一种方式，注意，数字后面的点只能是英文的点，特别注意，有序列表的序号是根据第一行列表的数字顺序来的，比如说：

###有序列表
1. 列表3
2. 列表2
3. 列表1


第一组本来是3 2 1 倒序，但是现实3 4 5 ，后面一组 序号是乱的， 但是还是显示 3 4 5 ，这点必须注意了

 

3、区块引用

比如说，你想对某个部分做的内容做一些说明或者引用某某的话等，可以用这个语句
* 1
  > 区块引用1
  > 区块引用2
  > 区块引用3
  > 区块引用4
* 2
  > 区块引用5
  > 区块引用6
  > 区块引用7
  > 区块引用8
* 3
  > 区块引用9
  > 区块引用10
  > 区块引用11
  > 区块引用12
  

无序列表下方的便是引用，可以有多种用途，看你的需求了，用法就是在语句前面加一个 > ，注意是英文的那个右尖括号，注意空格

引用因为是一个区块，理论上是应该什么内容都可以放，比如说：标题，列表，引用等等，看看下图：

> * 1
>  > 区块引用1
>  > 区块引用2
>  > 区块引用3
>  > 区块引用4
> * 2
>  > 区块引用5
>  > 区块引用6
>  > 区块引用7
>  > 区块引用8
> * 3
>  > 区块引用9
>  > 区块引用10
>  > 区块引用11
>  > 区块引用12

将上面的代码稍微改一下，全部加上引用标签，就变成了一个大的引用，还有引用里面还有引用，那引用嵌套引用还没有别的写法呢？

> 一级引用
>> 二级引用 
>>> 三级引用
>>>> 四级引用 
>>>>> 五级引用 
>>>>>> 六级引用 

上图可以看出，想要在上一次引用中嵌套一层引用，只需多加一个>，理论上可以无限嵌套，我就不整那么多了，注意：多层嵌套的>是不需要连续在一起的，只要在一行就可以了，中间允许有空格，但是为了好看，还是把排版搞好吧

 

4、华丽的分割线

分割线可以由* - _（星号，减号，底线）这3个符号的至少3个符号表示，注意至少要3个，且不需要连续，有空格也可以
*****************************
* * *
-----------------------
- - - - 
__________________
_ _ _
   

应该看得懂吧，但是为了代码的排版好看，你们自己定规则吧，前面有用到星号，建议用减号

 

5、链接

支持2种链接方式：行内式和参数式，不管是哪一种，链接文字都是用 [方括号] 来标记。

[我的github](https://github.com/devgis)   

上图可知，行内式的链接格式是：链接的文字放在[]中，链接地址放在随后的（）中，举一反三，经常出现的列表链接就应该这样写：

*[我的github](https://github.com/devgis)   
*[我的github](https://github.com/devgis)   

链接还可以带title属性，好像也只能带title，带不了其他属性，注意，是链接地址后面空一格，然后用引号引起来

*[我的github](https://github.com/devgis "这是title")   
*[我的github](https://github.com/devgis "这也是title")   

这是行内式的写法，参数式的怎么写：

*[我的github]:https://github.com/devgis "这是title"  
*[我的github]:https://github.com/devgis "这也是title"

这就好理解了，就是把链接当成参数，适合多出使用相同链接的场景，注意参数的对应关系，参数定义时，这3种写法都可以：

[foo]: http://example.com/ "Optional Title Here"

[foo]: http://example.com/ 'Optional Title Here'

[foo]: http://example.com/ (Optional Title Here)

还支持这种写法，如果你不想混淆的话：

[foo]: <http://example.com/> "Optional Title Here"

其实还有一种隐式链接的写法，但是我觉得那种写法不直观，所以就不写了，经常用的一般就上面2种，如果你想了解隐式链接，可以看我文章最后放出的参考地址

 

6、图片

图片也有2种方式：行内式和参数式，
![我是图片](http://e.hiphotos.baidu.com/image/h%3D300/sign=8000a165df1b0ef473e89e5eedc551a1/b151f8198618367afe76969623738bd4b21ce5fa.jpg)
[新图片]:http://c.hiphotos.baidu.com/image/h%3D300/sign=d4c9df02d7b44aed464eb8e4831d876a/bf096b63f6246b605ee26e3ce6f81a4c500fa28e.jpg

啊看图片![新图片]吧
   

用法跟链接的基本一样，唯一的不同就是，图片前面要写一个！（这是必须的），没什么好说的

 

7、代码框

这个就比较重要了，很多时候都需要展示出一些代码

如果代码量比较少，只有单行的话，可以用单反引号包起来，如下：

'<div><p>这是单行代码</p></div>'

要是多行这个就不行了，多行可以用这个：
### 多行
#### 多行
`````` 注释
<div>
<p>这是单行代码</p>
</div>
`````` 
    

多行用三个反引号，如果要写注释，可以在反引号后面写

8、表格

这个写的有点麻烦，注意看
###表格

|name|age|sex|
|:---------------:|:---------------|---------------:|
|zhangsan|20|boy|
|lisi|19|jj|

|title|remark|
|---------------|---------------|
|1|this is 1|
|2|this is 2|

|name|age|sex|
|-|-|-|
|zhangsan|20|boy|
|lisi|19|jj|

    

从这3种不同写法看，表格的格式不一定要对的非常起，但是为了好看，对齐肯定是最好的，第一种的分割线后面的冒号表示对齐方式，写在左边表示左对齐，右边为右对齐，两边都写表示居中，还是有点意思的，不过现实出来的结果是，表格外面并没有线框包起来，不知道别人的怎么弄的

 

9、强调

*字体倾斜*
_字体倾斜_

**字体加粗**
__字体加粗__

一个星号或者是一个下划线包起来，会转换为<em>倾斜，如果是2个，会转换为<strong>加粗

10、转义

* \\
* \,
* \*
* \#
* .....

就不一一列举了，基本上跟js转义是一样的

11、删除线
~~我是删除线~~
