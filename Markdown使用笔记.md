# Typora练习

## 标题练习

#### #+空格+标题名为一级标题

有几个#就是几级标题

## 段落练习

#### 在行末尾添加两个空格表示重新开始一个新的段落  

## 字体练习

#### 1.一个*开头或者一个_开头并结束表示斜体

*我是斜体*

_我也是斜体_

*和_是等价的

#### 2.两个*开头结尾表示粗体

**我是粗体**

#### 3.三个*开头结尾表示粗斜体

___我是粗斜体___

#### 4.一行中只有三个以上的*、-、_来建立一个分割线

___

#### 5.两个~~开头结尾表示添加删除线

~~我是删除线~~

#### 6.<u>标签可以表示下划线

<u>我是下划线</u>

#### 7.注明文本时在行首需要加上空格，不在行首不需要空格

 [^在这里写上要注明的文本]

## 列表练习

#### 1.无序列表使用*、+、-加上空格来表示

* 无序列表第一项
* 无序列表第二项
* 无序列表第三项  

#### 2.有序列表使用数字并加上.号+空格表示

1. 有序列表第一项
2. 有序列表第二项
3. 有序列表第三项
4. 两下回车退出列表编辑

#### 3.列表嵌套只需在子列表中的选项添加四个空格

1. 一级列表第一项：
       - 第一项嵌套的第一个元素
       - 第一项嵌套的第二个元素
2.  一级列表第二项：
       - 第二项嵌套的第一个元素
       - 第二项嵌套的第二个元素

## 区块练习

#### 1.引用区块是在段落开头使用>符号+空格

> 引用区块
>
> 我在练习

#### 2.区块嵌套，一个>是最外层，两个>是第一层嵌套

> 我是最外层区块
>
> > 我是第一层嵌套
> >
> > > 我是第二层嵌套
> > >
> > > 第二层嵌套结束
> >
> > 第一层嵌套结束
>
> 最外层嵌套结束



#### 3.区块中使用列表

> 区块中使用列表
>
> 1. 第一项
> 2. 第二项
>
> + 第一项
> + 第二项

#### 4.列表中使用区块

+ 第一项

  > 我在练习
  >
  > 我还在练习

+ 第二项

  > 回车起结束的意思
  >
  > 每次回车结束一项

## 写入代码练习

#### 1.函数或片段的代码用esc下面的反引号键包起来

`print()`函数

#### 2.代码区块使用```包裹一段代码

```java
for(int i=0;i<n;i++){
    System.out.println(i)
}
```

## 链接练习

#### 1.普通链接使用[链接名称]+(链接地址)或者<链接地址

[百度一下](http://www.baidu.com)  <https://www.baidu.com>

#### 2.高级链接通过变量设置一个链接，变量赋值在文档末尾进行

这个链接用1作为网址变量[百度一下][1]

这个链接用百度一下作为网址变量[baidu][百度一下]

[1]: http://www.baidu.com
[百度一下]: http://www.baidu.com

## 图片练习

#### 直接把图片拖进来就好，但是不能粘贴复制

![手绘](C:\Users\hp\Pictures\手绘.jpg)

## 表格练习

#### 1.制作表格使用 | 来分隔不同的单元格，使用 - 来分隔表头和其他行

| 表头1  | 表头2  |  表头3 | 表头4  |
| :----: | :----- | -----: | ------ |
| 单元格 | 单元格 | 单元格 | 单元格 |
| 单元格 | 单元格 | 单元格 | 单元格 |

