# Markdown语法的简要规则

## 1、标题

    # Header 1
    ## Header 2
    ### Header 3
    #### Header 4
    ##### Header 5
    ###### Header 6 

# Header 1
## Header 2
### Header 3
#### Header 4
##### Header 5
###### Header 6

标题是每篇文章都需要也是最常用的格式，在 Markdown 中，如果一段文字被定义为标题，只要在这段文字前加`#`号即可。
总共六级标题，建议在井号后加一个空格，这是最标准的 Markdown 语法。

## 2、列表

	#### 无序列表

	* 1
	* 2
	* 3

	#### 有序列表

	1. 1
	2. 2
	3. 3

#### 无序列表

* 1
* 2
* 3

#### 有序列表

1. 1
2. 2
3. 3

熟悉 HTML 的同学肯定知道有序列表与无序列表的区别，在 Markdown 下，列表的显示只需要在文字前加上`-`或`*`即可变为无序列表，有序列表则直接在文字前加`1.` `2.` `3.` 符号要和文字之间加上一个字符的空格。

## 3、引用

	> Email-style angle brackets
	> are used for blockquotes.

	> > And, they can be nested.

	> #### Headers in blockquotes
	> 
	> * You can quote a list.
	> * Etc.

> Email-style angle brackets
> are used for blockquotes.

> > And, they can be nested.

> #### Headers in blockquotes
> 
> * You can quote a list.
> * Etc.

如果你需要引用一小段别处的句子，那么就要用引用的格式，只需要在文本前加入`>`这种尖括号（大于号）即可

## 4、图片与链接

#### 链接

    [http://example.com](http://example.com "example.com")
    <example@example.com>
    
    [example][id]
    
    [id]: http://example.com/ "Title"


[http://example.com](http://example.com "example.com")

<example@example.com>

[example][id]

[id]: http://example.com/ "Title"

#### 图片

	![Mou icon](http://25.io/mou/Mou_128.png "Mou icon")
    
    ![Mou icon][id]
    
    [id]: http://25.io/mou/Mou_128.png "Title"
    

![Mou icon](http://25.io/mou/Mou_128.png "Mou icon")

![Mou][id1]

[id1]:http://25.io/mou/Mou_128.png "Mou"

插入链接与插入图片的语法很像，区别在一个`!`号

图片为：`![]()`

链接为：`[]()`

## 5、粗体与斜体

#### 粗体

    **strong**
    __strong__
    
**strong**  
__strong__

#### 斜体

    *emphasize*
    _emphasize_
    
*emphasize*  
_emphasize_

Markdown 的粗体和斜体也非常简单，用两个`*`包含一段文本就是粗体的语法，用一个`*`包含一段文本就是斜体的语法。

## 6、代码块

#### 单行代码

    `Code`
`Code`

#### 多行代码

        Code block
        with multilines
-

    Code block
    with multilines
    
***

    ```
    Code
    with multiple lines
    ```

```
Code
with multiple lines
```

## 7、分割线

    ---
    * * *
    - - - -
    
---
* * *
- - -

## 8、角标

	footnote.[^1]
    
    [^1]: This is a note

footnote.[^1]

[^1]: This is a note

## 9、删除线

    ~~text~~

~~text~~

## 10、表格

    H1 | H2 | H3
    -- | -- | --
    C1 | C2 | C3

H1 | H2 | H3
-- | -- | --
C1 | C2 | C3

    Header Left    | Header Centered    | Header Right 
    :------------- | :----------------: | --------------:
    Left    | Center    | Right   

Header Left    | Header Centered    | Header Right 
:-- | :--: | --:
Left    | Center    | Right 

## 11、跳转

    **[Title](id:anchor1)**
**[Title](id:anchor1)**

    Click this [link](#anchor1) to go to title.
Click this [link](#anchor1) to go to title.
