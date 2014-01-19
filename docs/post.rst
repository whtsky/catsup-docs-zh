.. _post-syntax:

文章语法
=============

Catsup 目前支持三种格式的文章： :ref:`Markdown <post-markdown-syntax>`, :ref:`纯文本 <post-text-syntax>` 和 :ref:`HTML <post-html-syntax>`.


.. _post-markdown-syntax:

Markdown 格式的文章
-------------------

总览
~~~~~~~~~

文章的扩展名应为 ``.md`` 或 ``.markdown`` .

一个 Hello World 文章应该是这样的 ::

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
+ :ref:`元数据 <post-meta>`
+ 正文

标题
~~~~~~~~~~~~~~~~~~~~~~

标题应该始终在文章的第一行，并且以 ``#`` 起头。

正文
~~~~~~~~~~~~~~~~~~~~~~

分隔符下的一切都是正文，正文应该以 Markdown 形式书写。

代码高亮
~~~~~~~~~~~~~~~~~~~~~~

Catsup 支持 GitHub 风格的代码高亮，就像这样 ::

    ```python
    print("Hello World!")
    ```


.. _post-text-syntax:

纯文本格式的文章
-------------------

有时候你只是想写些东西而不想去考虑文章的格式，那么你应该选择纯文本格式的文章。

纯文本格式的文章的扩展名应该是 ``.txt`` 。

最简单的纯文本格式的文章看起来是这样的 ::

    Hello!
    This is a text post.

如果你想要加一些元数据的话，你应该使用 YAML 格式的元数据 ::

    ---
    title: Hello, World!
    tags: Hello, World
    time: 2014-01-04 20:56
    ---

    Hello, World! I'm a text post.


.. _post-html-syntax:

HTML 格式的文章
--------------

HTML 格式的文章就像 :ref:`纯文本格式的文章 <post-text-syntax>`, 但是你可以在文章正文中使用 HTML .

HTML 格式的文章的扩展名应该是 ``.html`` .

文章样例 ::

    ---
    title: Hello, World!
    tags: Hello, World
    time: 2014-01-04 20:56
    ---

    <p>I'm writing HTML in catsup</p>


.. _post-meta:

元数据
-------

元数据是关于文章的一些信息。
元数据不是必须的，如果你的文章有元数据的话，记得在元数据下面加上 :ref:`分隔符 <post-separator>`

+ time: 文章是何时写成的，比如 ``2013-08-25 11:10``
+ tags: 文章的 Tag ，以英文逗号分割，比如 ``Python, Program``
+ type: 设置为 ``page`` 来把这篇文章转换为一个独立页面
+ description: 文章的描述
+ comment: 设置为 ``disabled`` 来禁止评论
+ permalink: 文章的永久链接地址，比如 ``/this-post``

.. _post-separator:
分隔符
---------------

分隔符将文章元数据与正文分割开。分隔符应该至少有三个 ``-`` ::

    ---

当然他也可以更长 ::

    ----------------



独立页面
--------

独立页面是一种特殊的文章。可以通过在元数据中添加 ``- type: page`` 将一篇普通文章转换为元数据。

普通文章和独立页面之间有什么区别呢？

+ 独立页面没有 Tags
+ 独立页面不会在归档页面和分页页面中出现
+ 一般来说，每一页的导航部分都会有独立页面的连接
