# JVM 编程任务
-------------------

**感谢您参与我们的 Java 开发测试，您需要完成以下几个步骤。**

*注意：整个开发过程应该控制在1-2个小时内完成。*

## 准备
* 我们不强制要求您一定要用 java 语言开发，只要是可以在 JVM（Java7 或者 Java8） 上运行的语言都可以（Groovy, Scala... ）。
* 我们不关心您使用什么构建工具，但是您要做到 IDE 无关，并保证我们签出即可运行。
* 我们不关心您使用什么样的持久化方式（可以使用内存），但是一定要内嵌到程序中，因为我们不会专门再去安装一个 Mysql 或者 MongoDB。

## 任务
* Fork 这个 Repo（如果您不知道如何去做的话，Google 之）。
* 创建一个可编译的工程。
* 我们的需求是一个交易记录，交易信息包含「交易 ID」、「创建时间」、「交易状态（例如是否交易成功）」、「交易类型（例如支付还是退款）」、「交易金额」、「交易币种（例如美元还是人民币）」、「客户信息」
* 客户信息包含「客户 ID」、「客户姓名」即可
* 通过 Rest 的方式暴露一个创建交易的接口
* 通过 Rest 的方式暴露一个按交易状态查询交易列表的接口

## 测试
1. 使用用户张三创建一条86元5角人民币的交易记录，验证交易状态为等待付款，并且交易的金额是正确的。
2. 使用你所习惯的测试框架，初始化3条交易成功信息，2条交易失败信息。验证查询接口按全部状态查询共5条交易，只查询成功的交易是3条，只查询失败的交易是2条。


## 完成后
1. 提交代码到您的 Github 仓库。
2. 给我们发送一个 Pull request，我们会 Review 您的代码。

## 其他
* 如果您的构建和运行过程比较难以理解的话，建议您修改 Readme 的这个地方添加一些说明文字。
* 附：
* 代码放在了javaRepository仓库里。对于任务当中的实现难点有：1.之前不知道什么是REST方式去暴露一个接口，完成后大概有所了解；2.内嵌到程序到中的持久化方式不知道怎么实现，期初设想是将对象直接序列化存储在项目文件中，使用时再逆序列化取出。后来直接就直接在执行接口时去产生需要的对象；3.创建交易信息本计划是使用JSP有页面输入参数，提交到接口再保存为对象，接着在输出XML，但是由JSP传递参数调试出现问题，只得直接使用URL去提交参数；4.使用的Jersey框架，因为发现它的配置和讲解实例较多，而且支持将对象转化为XML文件；5.添加交易信息后返回的对象转换为XML时长出现问题，原因还没找出；6.测试使用的是Junit，一共就两个测试用例；7.对于完成这道题的收获就是大致对WebService和REST有了初步了解，同时对于自己的如今的快速学习能力还需要锻炼。
