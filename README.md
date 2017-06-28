# atom-plugins
* [atom-plugins](#1)
* [how to use global esLint config of airbnb](#2)

## <h2 id="1">atom-plugins</h2>
|插件名称|描述|快捷键|
|:----:|:----:|:----:|
|markdown-preview-plus|markdown实时预览|ctrl+shift+m|
|go-to-line|行数跳转|ctrl+g|
|autocomplete-paths|路径补全||
|simplified-chinese-menu|汉化||
|project-manager|一个atom窗口管理多个项目||
|autocomplete-plus|代码自动补全||
|atom-ternjs|js代码自动补全||
|es6-javascript|es6快捷输入|看配置文件|
|hyperclick|变量定义跳转|ctrl+鼠标左键|
|js-hyperclick|变量定义跳转|ctrl+鼠标左键|
|highlight-selected|高亮选择||
|pigments|rgb数据转颜色显示||
|platformio-ide-terminal|atom直接打开终端||
|pretty-json|json格式排版/排序|ctrl+shift+p<br/>输入json选择样式|
|linter-jsonlint|json语法检查||
|last-cursor-position|跳转光标到前/后一次|前次:alt+-<br/>后次:alt+shift+-|
|file-icons|好看的文件图标||
|tool-bar|工具条支持||
|tool-bar-almighty|快捷工具条依赖tool-bar||
|Sublime-Style-Column-Selection|块选择与列编辑|shift+鼠标左键|
|docblockr|快速注释助手|输入"/**"回车|
|language-babel|js代码babel转义||
|linter|语法检查||
|linter-eslint|js语法检查||
|linter-ui-default|语法检查错误显示UI||
|atom-react-native-autocomplete|react-native语法补全||
|atom-bootstrap3|bootstrap3快捷输入||
|atom-beautify|代码格式化|ctrl+shift+p beautify|
|sync-settings|同步atom配置到其他电脑|查看配置文件|
|todo-show|搜索代码中出现的TODO等标记生成表格|alt+shift+t|
|busy-signal|状态栏||
|linter-ui-default|好看的linterUI||
|script|在atom中运行代码|shift+ctrl+b|

## <h2 id="2">how to use global esLint config of [airbnb](https://github.com/airbnb/javascript)</h2>
```shell
sudo cnpm install -g eslint
sudo cnpm install -g eslint-config-airbnb
sudo cnpm install -g eslint-plugin-import
sudo cnpm install -g eslint-plugin-react
sudo cnpm install -g eslint-plugin-jsx-a11y
gedit ~/.eslintrc.json
```

输入

```json
{
    "extends": "airbnb",
    "installedESLint": true,
    "plugins": [
        "react"
    ]
}
```

如果需要4空格对齐和忽略jquery语法中的变量未定义等错误,使用下面的配置

```json
{
    "extends": "airbnb",
    "installedESLint": true,
    "plugins": [
        "react"
    ],
    "env": {
        "jquery": true
    },
    "rules": {
        "indent": ["error", 4]
    }
}
```

在atom中安装linter插件和linter-eslint插件,并修改linter-eslint的缺省设置配置:<br>
* 去掉Disable when no ESLint config is found的钩。
* 勾上Use global ESLint installation的钩。
