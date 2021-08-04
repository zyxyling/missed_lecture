---
title: Markdown
abbrlink: 50148
summary: Markdown基本语法
---

# Markdown基本语法



[toc]

## 1、标题

​	n个#+空格+标题，enter，转化为相应n级标题

#-->

# Header 1

## Header 2

### Header3

#### Header4

##### Header 5

## 2、斜体、粗体、加粗斜体、删除线

```
*斜体*
_斜体_
**粗体**
__粗体__
***加粗斜体***
~~删除线~~
```

*斜体*

_斜体_

**粗体**

**粗体**

***加粗斜体***

~~删除线~~

## 3.引用

* 多级引用

```
可多层嵌套
>引用某人的一句话
>>两层嵌套
```

>>>多层嵌套
>>>
>>>   ```
>>>
>>>   ```

   >引用某人的一句话
   >
   >> > 两层嵌套
>> >
   >> > > > 多层嵌套

   - 引用代码块

     > ​    这是引用的代码块形式

   ```java
   protected void onCreate(Bundle savedInstanceState) {
       super.onCreate(savedInstanceState);
    setContentView(R.layout.activity_main);
   }
   ```

## 4、列表

**无序列表**

```
   - one
   * two
   + three
```

		* one
	
		* two

  * three

    

**有序列表**

​	数字+ .

  1. one
  2. two

## 5、表格


* #### 居左：

```
:----
```

* #### 居中:

  ```
  :----:或者-----
  ```

* #### 居右:

  ```
  ----:
  ```

| 标题 | 标题 | 标题 |
| ---- | :--: | ---: |
|      |      |      |
|      |      |      |
|      |      |      |

```
姓名|技能|排行
--|:--:|--:
刘备|哭|大哥
关羽|打|二哥
张飞|骂|三弟
```

| 姓名 | 技能 | 排行 |
| ---- | :--: | ---: |
| 刘备 |  哭  | 大哥 |
| 关羽 |  打  | 二哥 |
| 张飞 |  骂  | 三弟 |

## 6、链接

```
[描述]（链接地址）
```

[西工大课程平台](http://learn.nwpu.edu.cn/)

## 7、图片

```
！[图片文本(可忽略)](图片地址“图片title”)
![](img src="C:\Users\lenovo\Pictures\励志壁纸\fec091886201672ddba90ff2915b8baf.jpg" style="zoom:80%;" /)
```

![1002137](C:\Users\lenovo\Pictures\壁纸\1002137.jpg)



## 8、分割线

```
***
---
```

---

***



## 9、代码框

注意反引号位置：1的左边

分为行内代码和代码块

* 行内代码使用 `代码` 标识,可嵌入文字中

  `create database hero;`

* 代码块使用4个空格或```标识

  \```
  代码
  \```

  

  代码语法高亮在``` 后面加上 `空格`和语言名称

  \``` 语言
  //注意语言前面有空格
  代码
  \```

`

~~~java

``` java
// java前面有空格
protected void onCreate(Bundle savedInstanceState) {
    super.onCreate(savedInstanceState);
    setContentView(R.layout.activity_main);
}
```
~~~



## 10、注解

```css
这是一个脚注的例子[^1]

[^1]: 这里是脚注
```

这是一个脚注的例子[^1]

[^\1]:这里是脚注



## 11、插入目录

### 1） 自动生成

直接输入`[toc]`，1-6个#均会被捕获

### 2）npm语法

* 全局安装doctoc插件

  ```
  npm i doctoc -g // install 简写 i
  ```

* 在md文件目录下  ，右键，git bash here，执行

  ```
  doctoc demo.md
  ```

  ![1597317993640](C:\Users\lenovo\AppData\Roaming\Typora\typora-user-images\1597317993640.png)



## 12、绘图



[markdown 绘制流程图、时序图、甘特图]( https://blog.csdn.net/kl28978113/article/details/93617103 )

- 流程图——指定 `mermaid`（样式流程图） 或 `flow` （标准流程图）解析语言
- 时序图——指定 `sequence`（标准时序图） 或 `mermaid`（样式时序图） 解析语言
- 甘特图——指定 `mermaid` 解析语言





### 1）流程图

#### flow



**说明：**

 流程图大致分为两部分：

​		第一段：定义元素

​		第二段：定义元素之间的走向 



**定义元素：**

```
tag=>type: content:>url
```

- tag就是元素名字，

- type是这个元素的类型，有6中类型：

  * start         # 开始

  * end           # 结束

  * operation     # 操作

  * subroutine    # 子程序

  * condition     # 条件

  * inputoutput   # 输入或产出

  * content就是在框框中要写的内容，注意type后的冒号与文本之间一定要有个空格。

  * url是一个连接，与框框中的文本相绑定

    

**连接元素：**

 用**->**来连接两个元素，需要注意的是condition类型，因为他有yes和no两个分支 

```
c2(yes)->io->e 
c2(no)->op2->e
```



**应用：**

​	在代码块中，键入语法，选择语言`flow`

eg :one:

```
flow
st=>start: Start
op=>operation: Your Operation
cond=>condition: Yes or No?
e=>end
st->op->cond
cond(yes)->e
cond(no)->op
```

```flow
flow
st=>start: Start
op=>operation: Your Operation
cond=>condition: Yes or No?
e=>end
st->op->cond
cond(yes)->e
cond(no)->op
```



eg :two:

```
flow
st=>start: Start|past:>http://www.google.com[blank]
e=>end: End:>http://www.google.com
op1=>operation: get_hotel_ids|past
op2=>operation: get_proxy|current
sub1=>subroutine: get_proxy|current
op3=>operation: save_comment|current
op4=>operation: set_sentiment|current
op5=>operation: set_record|current

cond1=>condition: ids_remain空?
cond2=>condition: proxy_list空?
cond3=>condition: ids_got空?
cond4=>condition: 爬取成功??
cond5=>condition: ids_remain空?

io1=>inputoutput: ids-remain
io2=>inputoutput: proxy_list
io3=>inputoutput: ids-got

st->op1(right)->io1->cond1
cond1(yes)->sub1->io2->cond2
cond2(no)->op3
cond2(yes)->sub1
cond1(no)->op3->cond4
cond4(yes)->io3->cond3
cond4(no)->io1
cond3(no)->op4
cond3(yes, right)->cond5
cond5(yes)->op5
cond5(no)->cond3
op5->e
```

```flow
flow
st=>start: Start|past:>http://www.google.com[blank]
e=>end: End:>http://www.google.com
op1=>operation: get_hotel_ids|past
op2=>operation: get_proxy|current
sub1=>subroutine: get_proxy|current
op3=>operation: save_comment|current
op4=>operation: set_sentiment|current
op5=>operation: set_record|current

cond1=>condition: ids_remain空?
cond2=>condition: proxy_list空?
cond3=>condition: ids_got空?
cond4=>condition: 爬取成功??
cond5=>condition: ids_remain空?

io1=>inputoutput: ids-remain
io2=>inputoutput: proxy_list
io3=>inputoutput: ids-got

st->op1(right)->io1->cond1
cond1(yes)->sub1->io2->cond2
cond2(no)->op3
cond2(yes)->sub1
cond1(no)->op3->cond4
cond4(yes)->io3->cond3
cond4(no)->io1
cond3(no)->op4
cond3(yes, right)->cond5
cond5(yes)->op5
cond5(no)->cond3
op5->e
```





#### mermaid

参考：

* [markdown绘图插件----mermaid简介]( https://blog.csdn.net/wangyaninglm/article/details/52887045 )

* [【简明版】有道云笔记Markdown指南]( http://note.youdao.com/iyoudao/?p=2411 )





## 13、图标

英文模式下，输入冒号`:` ,再输入其它一个或多个数字或字母

:100:

:1st_place_medal:

:2nd_place_medal:

:point_up_2:

:3rd_place_medal:

:zero::one::two::three::four::five::six::seven::eight::nine::keycap_ten:

:accept::baby::baby_bottle::baby_chick::arrow_down_small::e-mail::camera_flash::dog::sparkling_heart:



## 14、项目符号

-[]

-[x]

-[ ]



