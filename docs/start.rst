.. _get-started:

快速起步
================

这部分文档需要你安装 Catsup 。如果你没有，最好先去 :ref:`安装 <installation>`

建立一个新站点
-------------------
用 Catsup 建立一个新站点非常容易 ::

    $ mkdir site
    $ cd site
    $ catsup init

让我们看看发生了什么 ::

    $ ls
    config.json posts

在执行 ``catsup init`` 之后， Catsup 创建了一个配置文件 ``config.json`` 和一个空白的文章目录 ``posts``

现在，该配置这个新站点啦。

配置你的站点
-----------------------

Catsup 可以被高度自定义，但你只要改几个设置就可以让你的站点跑起来啦 :

+ ``site.name`` : 站点的名字
+ ``site.description`` : 站点的描述
+ ``site.url`` : 站点的 URL 。比如 ``http://example.com`` 或者 ``http://example.com/site``
+ ``author.name`` : 你的名字

如果你想要深入了解配置文件的话，情看一看 :ref:`配置 <configuration>`

配置完站点之后，该开始写文章啦。

写文章和独立页面
-------------------------

让我们先写一个文章 ::

    vim posts/hello-world.md

一个 Hello World 文章看起来是这样的 ::

    # Hello, World!

    - time: 2013-08-25 23:30
    - tags: hello world

    ---

    你好, 世界!
    这是我在 Catsup 中的第一篇文章.
    我在用 **MarkDown** 写东西!
    <strong>哇，还支持 HTML </strong>

    ```python
    print("I love python")
    ```

然后，让我们写一个独立页面来介绍你的站点 ::

    vim posts/about.md

一个「关于」页面看起来是这样的 ::

    # 关于这个站点

    - time: 2013-08-25 23:31
    - type: page

    ----

    Hi!
    这个站点是用 [catsup](https://github.com/whtsky/catsup). 生成的


想要深入了解文章语法？可以去看看 :ref:`文章语法 <post-syntax>` 文档。

生成站点
-----------------
在写完文章和独立页面之后，该生成站点然后四处宣传啦！

但是别急，先预览一下这个站点 ::

    catsup server

然后打开你的浏览器，进入 http://127.0.0.1:8888 .

如果你想要获取关于预览服务器的更多信息，请前往 :ref:`预览服务器 <preview-server>` 。


在预览完站点，确定一切无误之后，让我们来生成站点 ::

    catsup build

看看发生了什么 ::

    $ ls
    config.json deploy posts


部署站点
------------------

部署到 GitHub Pages
````````````````````````

感谢 GitHub, 我们有了一个绝佳的站点部署平台。

你需要一个叫做 `YOUR_GITHUB_USERNAME.github.io` 的 repo 。 如果你还没有，现在去 `创建一个 <https://github.com/repositories/new>`_ 吧。


然后修改你的配置文件， 将 ``deploy`` 部分改成这样 ::

    "deploy": {
        "default": "git",

        "git": {
            "repo": "git@github.com:YOUR_GITHUB_USERNAME/YOUR_GITHUB_USERNAME.github.io.git",
            "branch": "master",
            "delete": true
        }
    },

用你的 GitHub 用户名（ 比如 ``whtsky`` ） 替换掉 ``YOUR_GITHUB_USERNAME`` 。

在这之后，让我们把站点部署到 GitHub Pages 上 ::

    catsup build && catsup deploy

然后打开 http://YOUR_GITHUB_USERNAME.github.io 来细细品味你的新站点吧。

部署到自己的服务器上
```````````````````````````

Catsup 也支持通过 rsync 进行部署。在继续之前，你需要确保你的服务器上运行着 rsync 。

然后修改你的配置文件， 将 ``deploy`` 部分改成这样 ::

    "deploy": {
        "default": "rsync",

        "rsync": {
            "ssh_port": 22,
            "ssh_user": "USER_NAME_HERE",
			"ssh_host": "IP_ADDRESS_OF_YOUR_SERVER",
            "document_root": "DEPLOY_TO_WHICH_PATH",
        }
    },

这里有份儿例子 ::

    "deploy": {
        "default": "rsync",

        "rsync": {
            "ssh_port": 22,
            "ssh_user": "whtsky",
			"ssh_host": "whouz.com",
            "document_root": "~/whouz.com",
        }
    },

在这之后，让我们通过 rsync 部署我们的站点 ::

    catsup build && catsup deploy


读一读 :ref:`部署支持 <deploy>` 来详细了解这个功能。
