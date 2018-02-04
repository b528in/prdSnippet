# prdSnippet

## 介绍

产品经理在写作需求文档过程中，会用到通用的控件描述，而且控件复杂起来还容易遗漏规则。所以本项目的目的就是：

* 收集常见的产品需求文档写作片段，加以复用
* 在写作过程中根据提示核查，防止规则遗漏
* 让文档看起来美美哒，这离不开[Markdown](https://zh.wikipedia.org/zh-cn/Markdown)
* 偷懒

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

snippet文件结构如下:

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
## Snippets

### stepper
步进器 可以设置步长，上限，下限，是否支持输入框输入

### badge
badgen:badge notification 表示无数字的徽标
badgem:badge messages 表示有数字的徽标，可设置最大的消息数目

### radio
radio:单选按钮，可设置选项名称、选项值、选项状态

