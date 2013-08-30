.. _post-syntax:

文章语法
=============

总览
-----------

一个文章的扩展名应该是 ``.md`` 或者 ``.markdown`` .

一个 Hello World 文章看起来是这样的 ::

    # Hello, World!                          <---- This is title

    - time: 2013-08-25 23:30                 <---- This is meta
    - tags: hello world

    ---

    Hello, World!                            <---- This is content
    This is my first post in catsup.
    I'm writing in **MarkDown** !
    <strong>HTML is supported, too</strong>

    ```python
    print("I love python")
    ```

一篇文章由三部分构成:

+ 标题
+ 元数据
+ 正文

标题
--------

标题应该始终在文章的第一行，以 ``#`` 起头。

.. _post-meta:

元数据
-------

元数据是关于文章的一些信息，元数据位于标题之下，分隔符之上。


+ time: 文章是何时写成的，比如 ``2013-08-25 11:10``
+ tags: 文章的 Tag ，以英文逗号分割，比如 ``Python, Program``
+ type: 设置为 ``page`` 来把这篇文章转换为一个独立页面
+ description: 文章的描述
+ comment: 设置为 ``disabled`` 来禁止评论
+ permalink: 文章的永久链接地址，比如 ``/this-post``

分隔符
---------------

分隔符将文章元数据与正文分割开。分隔符应该至少有三个 ``-`` ::

    ---

当然他也可以更长 ::

    ----------------

正文
-----------

分隔符下的一切都是正文，正文应该以 Markdown 形式书写。

代码高亮
-----------------

Catsup 支持 GitHub 风格的代码高亮，就像这样 ::

    ```python
    print("Hello World!")
    ```


独立页面
--------

独立页面是一种特殊的文章。可以通过在元数据中添加 ``- type: page`` 将一篇普通文章转换为元数据。

普通文章和独立页面之间有什么区别呢？

+ 独立页面没有 Tags
+ 独立页面不会在归档页面和分页页面中出现
+ 一般来说，每一页的导航部分都会有独立页面的连接