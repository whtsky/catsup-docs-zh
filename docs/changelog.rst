更新日志
============

Version 0.3.0
--------------

+ 添加多格式的文章支持.
+ 添加 ``config.config.static_source``.
+ 添加 ``config.config.static_output``.
+ 支持无元素的文章.
+ 支持为文章自定义永久链接.
+ 支持 TXT 格式的文章.
+ 支持 HTML 格式的文章.
+ 支持 YAML 格式的元素.
+ 重写 `catsup install`
+ 正确的 Twitter Card URL 支持.
+ 移除基于文件的缓存系统.
+ 提高描述的创造.
+ 修整代码.

Version 0.2.1
--------------

+ 修复 Build 的 Bugs.

Version 0.2.0
--------------

+ 支持生成网站地图.
+ 添加 `catsup watch` 命令.
+ 添加 `catsup clean` 命令.
+ 为渲染 markdown 添加缓存.
+ 为 ``url_for`` 添加缓存.
+ 为 ``static_url`` 添加缓存.
+ 使用 Jinja2 的 Bytecode Cache.
+ 不要再运行 ``catsup server`` 时生成统计代码.
+ 在加载配置和文章时输出所用时间.
+ 改变 json 引擎为 `ujson`.

Version 0.1.0
--------------

+ 为 ``static_url`` 使用完整的 mod5 哈希值.
+ 支持页面.
+ 当运行 ``catsup server`` 时，将站点创建在 tempdir.
+ 添加 ``config.site.description``.
+ 使用 ``config.comment.shortname`` 来替代 ``config.comment.disqus`` 和 ``config.comment.duoshuo``.
+ 当你的站点正在运行 ``catsup server`` 时自动跟新主题和文章.
+ 在运行 ``catsup server`` 时使用本地静态文件.
+ post_per_page 变量现在由主题定义.
+ 现在 catsup 在源代码文件中复制 non-markdown 文件来部署.
+ 移除概要.
+ 移除 markdown 自动转义.
+ 添加 sub 目录支持.
+ 支持自定义永久链接.
+ 重写 generator, parser 和 server.
+ 不要在部署前更新你的文章.

Version 0.0.8
--------------

+ 重写标签和文章代码.
+ 添加部署支持.(通过 git 和 rsync).

Version 0.0.7
--------------

发布于 Feb. 7, 2013

+ 为写作主题添加页数.
+ 把 excerpt 重命名为 summary.
+ 添加主题工具.
+ 支持主题过滤.
