.. _configuration:

配置
===============

Catsup 的配置文件是一个标准的 JSON 文件

总览
------------

默认的配置文件看起来是这样的 :

.. literalinclude:: config.json
    :language: json


Site & Author & Config
------------------------

这几项配置起来十分容易。

如果你要用 Google Analytics 的话，记得修改 ``config.analytics`` ::

    "config": {
        "source": "posts",
        "static_source": "static",
        "output": "deploy",
        "static_output": "deploy/static",
        "static_prefix": "/static/",
        "analytics": ""
    },


Permalink
-------------

通过修改 ``config.permalink`` ，你可以轻松的自定义任何页面的永久链接。

下面这些 Post 页面的永久链接风格比较有参考价值 :

+ ``/{title}.html``
+ ``{filename}.html``
+ ``/{date}/{title}/``
+ ``/{filename}/``
+ ``/{date}/{filename}/``
+ ``/{datetime.year}/{filename}/``

注意，在 :ref:`文章元数据 <post-meta>` 中定义的永久链接会被优先使用。

比如说，在配置文件里，你自定义了 Post 页面的永久链接 ::

    "permalink": {
        "post": "/{title}/",
        "feed": "/feed.xml"
    },

然后在你的某篇文章中，你在 :ref:`元数据 <post-meta>` 中自定义了一个永久链接 ::

    # About

    - datetime: 2013-08-30 12:00
    - type: page
    - permalink: /about-the-site

    -------

    This is a about page

那么，这篇文章的永久链接将会是 ``/about-the-site`` .

Comment
----------

Catsup 支持两种评论系统: `Disqus <http://disqus.com>`_ 和 `多说 <http://duoshuo.com>`_

如果你更喜欢多说的话，可以轻松的把评论系统设置成多说 ::

    "comment": {
        "allow": true,
        "system": "duoshuo",
        "shortname": "catsup"
    },

如果你在评论系统中有自己的站点的话，记得把 ``comment.shortname`` 改成你自己的 ::

    "comment": {
        "allow": true,
        "system": "disqus",
        "shortname": "my_site"
    },

如果你不希望开启评论系统，那么就关掉它吧 ::

    "comment": {
        "allow": false
    },

如果你只是希望部分文章不背评论，可以在 :ref:`元数据 <post-meta>` 中设置 ``- comment: disabled``

Deploy & Theme
----------------

这几项配置起来十分容易。

如果还不太明白的话，去看看 :ref:`部署支持 <deploy>` 和你主题的文档吧。
