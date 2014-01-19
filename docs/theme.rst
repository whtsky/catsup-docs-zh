主题
========

总览
---------

安装一个主题 ::

    catsup install git_repo

比如，安装 `Theme Clean <https://github.com/whtsky/catsup-theme-clean>`_ ::

    catsup install clean

列出所有已安装的主题 ::

    catsup themes

结构
----------

Catsup 使用 Jinja2 模板引擎。如果你想要开发自己的主题，你需要先了解 Jinja 2 。

你可以看看以下几个主题来了解如何开发自己的 Catsup 主题 ：

+ `Theme Clean <https://github.com/whtsky/catsup-theme-clean>`_
+ `Theme Sealscript <https://github.com/whtsky/catsup-theme-sealscript>`_

一个 Catsup 主题看起来是这样的 ::

    ├── README.md                      <-------- how to install/customize your theme.
    ├── static                         <-------- static files
    │   ├── css
    │   │   ├── pygments_style.css     <-------- catsup uses Pygments to highlight code
    │   │   └── style.css
    ├── templates                      <-------- template files
    │   ├── 404.html
    │   ├── archive.html
    │   ├── archives.html
    │   ├── page.html
    │   ├── post.html
    │   └── tag.html
    │   └── tags.html
    ├── filters.py                     <--------- filters defined by theme
    └── theme.py                       <--------- meta file


元数据
-----------

一个主题元数据文件的例子 ::

    name = 'sealscript'
    author = 'Lyric'
    homepage = 'https://github.com/whtsky/catsup-theme-sealscript'
    post_per_page = 3
    vars = {
        "github": "whtsky",
    }

一个主题元数据包括 :

+ name
+ author
+ homepage
+ post_per_page
+ vars


变量
----------

全局变量
~~~~~~~~~~~~~~~~~~

+ generator: Catsup 的 Generator 实例.
+ site: 配置文件中的 ``site`` .
+ author: 配置文件中的 ``author`` .
+ config: 配置文件中的 ``config`` .
+ comment: 配置文件中的 ``commment`` .
+ theme: 配置文件中的 ``theme.vars`` .
+ pages: 当前站点的所有独立页面

模板变量
~~~~~~~~~~~~~~~~~~~~~~

只有几个模板有模板变量。

+ pagination: ``page.html`` 中特有的模板变量。
+ post: ``post.html`` 中特有的模板变量。
+ permalink: 当前页面的永久链接 ::

    <link rel="canonical" href="{{ permalink }}"/>


内置函数
------------------------

static_url
~~~~~~~~~~~~~~~~~~
Static URL 返回给定静态文件的 URL  ::

    <link rel="stylesheet" href="{{ static_url("css/style.css") }}" type="text/css" />

url_for
~~~~~~~~~~~~~~~~~~~

url for 返回给定对象的永久链接地址 ::

    <a href="{{ url_for('index') }}">{{ site.name }}</a>

    <a href="{{ url_for(post) }}">{{ post.title }}</a>

    <link rel="alternate" type="application/rss+xml" href="{{ url_for('feed') }}" title="{{ site.name }}" />

过滤器
-----------

``filters.py`` 中的所有函数都会被注册为过滤器。 Catsup 也内置了一些过滤器：

+ xmldatetime

模板宏
---------------
Catsup 有一些强大的模板宏，可以让你更加轻松的编写模板。

+ render_comment(post): 为给定的文章渲染评论
+ meta(post): 为给定的文章渲染 meta 标签。应当在 <head> 中被调用。
+ analytics(): 渲染统计代码。

使用内置的模板宏的 ``post.html`` 例子 ::

    <html>
        <head>
            <title>{{ post.title }}</title>
            {% from 'utils.html' import meta, analytics %}
            {{ meta(post) }}
            {{ analytics() }}
            <link rel="canonical" href="{{ permalink }}"/>
        </head>
        <body>
            <article>
                <h1>{{ post.title }}</h1>
                {{ post.content }}
                {% from 'utils.html' import render_comment %}
                {{ render_comment(post) }}
            </article>
        </body>
    </html>
