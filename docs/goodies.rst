Goodies
===========

.. _preview-server:

预览服务器
----------------
预览服务器可以让你不用部署就看到自己的站点 ::

    catsup server
    catsup server -p 8000

当

+ 站点的源文件夹(默认是 ``posts`` ) 中发生更改的时候（比如创建新的文章，修改已有的文章）
+ 你的主题文件夹中发生更改的时候（为 Catsup 写主题的时候会很有用）
+ Catsup 主程序发生变化（为 Catsup 编写代码的时候会很有用）

的时候， 预览服务器会自动重新生成你的站点。

.. note:: 当运行预览服务器的时候， Catsup 会忽视掉 ``site.url`` 并把生成的文件保存到一个临时文件夹中。

.. _deploy:

部署支持
----------------
可以帮助你通过 Git 或 rsync 快速部署你的站点 ::

    catsup deploy # 通过默认方式部署
    catsup rsync # 通过 rsync 部署
    catsup git # 通过 git 部署


Webhook
---------
如果你把站点的源文件保存在 GitHub 或 Bitbucket 上， Catsup 可以在你 push 到 Git 仓库的时候自动更新、生成你的站点。

你需要把站点的 repo clone 下来并开启 Webhook 服务 ::

    git clone git://path/to/your/site.git
    cd site
    catsup webhook -p 12580

.. attention:: Catsup 的 webhook 功能并不会以守护进程运行，这意味着你可能需要 Supervisor_ 这类工具来守护 webhook

之后你需要在 GitHub 或 BitBucket 中做一些配置，这里以 GitHub 为例：

+ 打开项目的 "Admin" 页面
+ 点击 “Service Hooks”
+ 在 "available service hooks" 中, 点击 “WebHook URLs“
+ 输入 Webhook URL [1]_
+  点击 “Update Settings”

.. [1] 如果你服务器的 IP 地址为 1.2.3.4 , 你应该输入 ``http://1.2.3.4:12580/webhook``

之后每当你 push 到 GitHub, Catsup 都会自动更新并生成你的站点。

.. _Supervisor: http://pypi.python.org/pypi/supervisor/
