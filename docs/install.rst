.. _installation:

安装
==============


如果你对 Python 足够熟悉，我强烈建议你把所有东西都装到 Virtualenv 里面。

如果你使用 OS X ，请确保你安装了 *Command Line Tools* .

使用 Pip 安装
-------------------------
使用 Pip 安装 Catsup 十分容易 ::

    (sudo) pip install catsup


从旧版本升级
-------------------------------
从旧版本升级也很容易 ::

    (sudo) pip install catsup --upgrade

用 Git 安装
-----------------
使用 Git 安装可以获得最新版本 ::

    git clone git://github.com/whtsky/catsup.git
    cd catsup

    # 我们使用了 git submodule 来管理主题
    # 如果你不喜欢默认主题（当前版本是 sealscript ）
    # 你可以跳过接下来的两条命令
    git submodule init
    git submodule update

    python setup.py install

Cann’t find Python.h ?
-----------------------
Catsup 使用 misaka 作为 Markdown 引擎，这个库需要编译才能使用。如果你在使用 Ubuntu ，可以运行 ::

    (sudo) apt-get install python-dev

