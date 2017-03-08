# agst3

Androguard for Sublime Text 3

代码来自 [as-st-1.9](https://code.google.com/archive/p/androguard/downloads) ，此版本是 Sublime Text 2 的插件。

但是此插件无法在 Sublime Text 3 上面正常使用，原因如下：

1. 由于 Sublime Text 3 内置 Python3.3，和之前 Sublime Text 2 使用的 Python2.X 不兼容，插件使用的是 2.X 的语法
2. 由于 Sublime Text 3 把插件的文件夹作为 module，所以插件 `from ... import` 会提示 `ImportError: No module named xxx`，找不到 module

原因找到了，那么想要原插件能运行在 Sublime Text 3 上面，需要：

1. 使用 Python 内置的 `2to3` 进行代码兼容，此工具处理不了的，手动修改
2. 修改 `from ... import` ，加上文件夹名称

此插件的修改工作放在工作之余，更新较慢，敬请期待正式可用版本。