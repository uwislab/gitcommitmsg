# 基于Web的Git的commit信息自动生成工具

#### 介绍 2025年03月24
基于纯HTML的Git的commit信息全自动生成工具，符合vue开源社区格式，生成的commit信息可以直接拷贝使用。单HTML文件格式，非常方便部署，拷贝到Web服务器根目录即可。

#### 软件架构
这个HTML文件实现的是一个Commit Message Builder，用于帮助用户生成规范的Git提交信息。

这个软件采用了前端单页面应用的架构，主要由HTML、CSS和JavaScript组成，实现了用户界面的渲染、用户交互处理以及提交信息的生成和复制功能。

使用了Flexbox布局（`.container`）来实现左右两部分的布局。

- **提交信息生成函数 `generateCommitMessage()`**：
    - 首先清空 `#commit-message` 区域的内容。
    - 对用户输入的主题和关闭的问题进行验证，如果输入不合法则显示错误提示并终止函数执行。
    - 获取用户输入的各项信息，如类型、作用域、主题、正文、破坏性变更、关闭的问题等。
    - 根据获取的信息生成规范的提交信息，并将其显示在 `#commit-message` 区域。
    - 启用复制按钮。
- **验证函数 `validateIssuesClosed()`**：
    - 使用正则表达式验证用户输入的关闭问题的格式是否正确。
- **复制函数 `copyToClipboard()`**：
    - 获取 `#commit-message` 区域的文本内容。
    - 创建一个临时的 `textarea` 元素，将文本内容设置为其值，并将其添加到页面中。
    - 选择 `textarea` 中的文本并尝试复制到剪贴板。
    - 根据复制结果显示相应的提示信息，并在一定时间后隐藏提示信息。
    - 移除临时的 `textarea` 元素。

#### 交互流程
1. 用户在左侧输入相关信息，如选择类型、输入作用域、主题等。
2. 用户点击“Generate Commit Message”按钮，触发 `generateCommitMessage()` 函数。
3. 函数对用户输入进行验证，如果输入合法则生成提交信息并显示在右侧的 `#commit-message` 区域，同时启用复制按钮。
4. 用户点击“Copy to Clipboard”按钮，触发 `copyToClipboard()` 函数，将生成的提交信息复制到剪贴板。

#### 优点和不足

#### 优点
- 简单易用，用户界面清晰，操作方便。
- 采用内联CSS和JavaScript，代码结构紧凑，易于维护。

#### 不足
- 缺乏对用户输入的实时验证，只有在点击生成按钮时才进行验证。
- 没有与后端进行交互，无法将生成的提交信息直接提交到Git仓库。
- 没有考虑浏览器兼容性问题，如 `document.execCommand('copy')` 在一些现代浏览器中可能不被支持。


#### 安装教程

1.  直接将HTML文件拷贝到Web服务器的根目录，然后使用浏览器访问即可。

#### 使用说明

1.  在Web页面中填写各项即可，点击生成，即可生成Git的commit信息。
2.  如果commit信息不对，可以反复修改。
3.  点击复制，即可把生成的commit信息复制到剪贴板，然后拷贝到Git中使用。

#### 参与贡献

1.  Fork 本仓库
2.  新建 Feat_xxx 分支
3.  提交代码
4.  新建 Pull Request


#### 特技

1.  使用 Readme\_XXX.md 来支持不同的语言，例如 Readme\_en.md, Readme\_zh.md
2.  Gitee 官方博客 [blog.gitee.com](https://blog.gitee.com)
3.  你可以 [https://gitee.com/explore](https://gitee.com/explore) 这个地址来了解 Gitee 上的优秀开源项目
4.  [GVP](https://gitee.com/gvp) 全称是 Gitee 最有价值开源项目，是综合评定出的优秀开源项目
5.  Gitee 官方提供的使用手册 [https://gitee.com/help](https://gitee.com/help)
6.  Gitee 封面人物是一档用来展示 Gitee 会员风采的栏目 [https://gitee.com/gitee-stars/](https://gitee.com/gitee-stars/)
