# Catsup 中文文档

这里是 [Catsup](https://github.com/whtsky/catsup) 的中文文档，主要由 [whtsky](http://whouz.com) 维护。

文档在这里： http://catsup-zh.readthedocs.org/en/latest/


关于更新：
首先添加上游分支
```bash
git remote add upstream git@github.com:whtsky/catsup.git
```

然后，上游分支（也就是 catsup 主项目）更新得时候，在文档这里进行更新：
```bash
git pull upstream [master 或 develop]
```

每次 Catsup 发布新版本之后，合并 master 分支并进行翻译，翻译完成之后的版本打上 tag 。