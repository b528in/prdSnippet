# prdSnippet

产品经理在写作需求文档过程中，常会用到通用的控件描述，或者容易遗漏规则。所以本项目的目的就是：

* 收集常见的产品需求文档写作片段，加以复用
* 用以在写作过程中核查，防止规则遗漏
* 让文档看起来美美哒，这离不开[Markdown](https://zh.wikipedia.org/zh-cn/Markdown)

**同时借助sublime text 3中的snippet功能，最终实现像写代码一样，通过关键词输入，提示控件内容，然后补全参数即可。**

举个例子，比如 radio 单选按钮：

* 描述：单选按钮允许用户在有限数量的选项中选择其中之一；
* 选项属性：名称、选项值、选项状态；
* 状态有：选中、非选中、禁用；

假如已经在sublime text 3中创建好了radio的snippet，那么我只需要键入radio+<kbd>tab</kbd>就可以写出：

```markdown

单选按钮：

|     选项名称  | 选项值 | 状态  |
| ------------ | --- | ---------|
| 选项1 |  选项值 | 非选中|
| 选项2 |  选项值 | 选中|
| 选项3 |  选项值 | 禁用|

```

通过markdown语法解析后显示为：


|     选项名称  | 选项值 | 状态  |
| ------------ | --- | ---------|
| 选项1 |  选项值 | 非选中|
| 选项2 |  选项值 | 选中|
| 选项3 |  选项值 | 禁用|

然后通过切换<kbd>tab</kbd>来选择各个选项的值或者删除每一行。
演示如下：



```xml

<snippet>
  <content><![CDATA[

单选按钮：

|     选项名称  | 选项值 | 状态  |
| ------------ | --- | ---------|
| 选项1 |  ${1:选项1} | ${2:非选中}|
${3:| 选项2 |  ${4:选项2} | ${5:选中}|
${6:| 选项3 |  ${7:选项3} | ${8:禁用}|}}

]]>
  </content>
	<!-- Optional: Set a tabTrigger to define how to trigger the snippet -->
	<tabTrigger>radio</tabTrigger>
	<!-- Optional: Set a scope to limit where the snippet will trigger -->
	<scope>text.html.markdown</scope>
  <description>单选按钮允许用户在有限数量的选项中选择其中之一<description>
</snippet>

```
## gif 

![Demo](https://github.com/renxiangbin/prdSnippet/blob/master/radio_test.gif)

## 我怎么使用呢？

当前可以手动安装，等snippet积累到一定的数量，我会提交到 [package control](https://packagecontrol.io/browse)中。

1. git clone 或者下载项目
2. 在sublime中找到 Browser Packages
3. 把项目放到Packages文件夹中即可

## 我可以根据我的文档写作习惯修改吗？

Certainly,Do whatever you want to do!


## 找组织

如果你是用其它高效的方式同开发交流产品需求文档，也欢迎你加入我们。同开发人员高效的沟通，是我们的根本目的。

1. 讨论帖可以来这里：[V2EX](https://www.v2ex.com/t/427898)
2. 想聊一聊可以来这里：[Telegram](https://t.me/joinchat/EukrYA1RDmDQ4qhYNosiwg)

## 如果你想参与进来，非常欢迎：

1. Fork it!
2. 创建你的特性分支: git checkout -b my-new-feature
3. 提交commit: git commit -m 'Add some feature'
4. push: git push origin my-new-feature
5. Submit a pull request

---

## 参考内容：

- [什么是Markdown？](https://zh.wikipedia.org/zh-cn/Markdown)
- 超棒的编辑器 [sublime text 3](https://www.sublimetext.com/)
- 关于sublime text 3 snippet参见[官方文档](http://sublimetext.info/docs/en/extensibility/snippets.html)
- Git教程参见[Git教程](https://www.liaoxuefeng.com/wiki/0013739516305929606dd18361248578c67b8067c8c017b000)。

