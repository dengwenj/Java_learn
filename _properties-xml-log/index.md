## Properties
* 是一个 Map 集合（键值对集合）
* 核心作用：Properties 是用来代表属性文件的，通过 Properties 可以读写属性文件中的内容
* public Properties(); 用于构建 Properties 集合对象（空容器）

## 使用 Properties 读取属性文件里的键值对数据
* public void load(InputStream is); 通过字节输入流，读取属性文件里的键值对数据
* public void load(Reader reader); 通过字符输入流，读取属性文件里的键值对数据
* public String getProperties(String key); 根据键获取值
* public Set<String> stringPropertyNames(); 获取全部键的集合（其实就是 keySet 方法的效果）

## 使用 Properties 把键值对数据写出到属性文件里去
* public Object setProperty(String key, String value); 保存键值对数据到 Properties 对象中去
* public void store(OutputStream os, String comments); 把键值对数据，通过字节输出流写出到属性文件里去
* public void store(Writer w, String comments); 把键值对数据，通过字符输出流写出到属性文件里去

## XML(全称 Extensible Markup Language，可扩展标记语言)
* 本质是一种数据的格式，可以用来存储复杂的数据结构，和数据关系

## XML 的特点
* XML 中的 "<标签名>" 称为一个标签或一个元素，一般是成对出现的
* XML 中的标签名可以自己定义（可扩展），但必须要正确的嵌套
* XML 中只能有一个根标签
* XML 中的标签可以有属性
* 如果一个文件中放置的事 XML 格式的数据，这个文件就是 XML 文件，后缀一般要写成.xml

## XML 的语法规则
* XML 文件的后缀名为：xml，文档声明必须是第一行
* <? xml version="1.0" encoding="UTF-8" ?>
* version: XML 默认的版本号码、该属性是必须存在的
* encoding: 本 XML 文件的编码
* XML 中可以定义注释信息：<!-- 注释内容 -->
* XML 中书写 "<"、"&" 等，可能会出现冲突，导致错误，此时可以用如下特殊字符代替
* &lt; < 小于
* &gt; > 大于
* &amp; & 和号
* &apos; ' 单引号
* &quot; " 引号
* XML 中可以写一个叫 CDATA 的数据区：<![CDATA[...内容...]]>，里面的内容可以随便写

## XML 的作用和应用场景
* 本质是一种数据格式，可以存储复杂的数据结构，和数据关系
* 应用场景：经常用来做为系统的配置文件，或者作为一种特殊的数据结构，在网络中进行传输

## 解析 XML 文件
* 使用程序读取 XML 文件中的数据
* 注意：我们并不需要自己写原始的 IO 流代码来解析 XML，难度较大！也相当繁琐
* 其实，有很多开源的，解析 XML 的包，最知名的事：Dom4j

## Dom4j 解析 XML 得到 Document 对象
* SAXReader：Dom4j 提供的解析器
* 构造方法：public SAXReader(); 构建 Dom4j 的解析器对象
* public Document read(String url); 把 XML 文件读成 Document 对象
* public Document read(InputStream is); 通过字节输入流读取 XML 文件

# Document
* Element getRootElement(); 获得根元素对象

## Element 提供的方法
* public String getName(); 得到元素名字
* public List<Element> elements(); 得到当前元素下所有子元素
* public List<Element> elements(String name); 得到当前元素下指定名字的子元素返回集合
* public Element element(String name); 得到当前元素下指定名字的子元素，如果有很多名字相同的返回第一个
* public String attributeValue(String name); 通过属性名直接得到属性值
* public String elementText(String 子元素名); 得到指定名称的子元素的文本
* public String getText(); 得到文本

## 如何使用程序把数据写出到 XML 文件中去？
* 推荐直接把程序里的数据拼接成 XML 格式，然后用 IO 流写出去

## 约束文档
* 专门用来限制 xml 书写格式的文档，比如：限制标签、属性应该怎么写
* 约束文档的分类
* 1、DTD 文档
* 2、Schema 文档

## XML 文档约束 - DTD 的使用
* 需求：利用 DTD 约束文档，约束一个 XML 文件的编写
* 1、编写 DTD 约束文档，后缀必须是 .dtd
* 2、在需要编写的 XML 文件中导入该 DTD 约束文档
* 3、然后 XML 文件，就必须按照 DTD 约束文档指定的格式进行编写，否则报错
* 可以约束 XML 文件的编写，不能约束具体的数据类型

## XML 文档约束 - schema 的使用
* 需求：利用 schema 文档约束，约束一个 XML 文件的编写
* 1、编写 schema 约束文档，后缀必须是 .xsd
* 2、在需要编写的 XML 文件中导入该 schema 约束文档
* 3、按照约束内容编写 XML 文件的标签

## 日志
* 希望系统能记住某些数据是被谁操作的，比如被谁删除了
* 想分析用户浏览系统的具体情况，以便挖掘用户的具体喜好
* 当系统在开发中或者上线后出现了 bug，该通过什么去分析、定位 bug

## 日志技术
* 可以将系统执行的信息，方便的记录到指定的位置（控制台、文件中、数据库中）
* 可以随时以开关的形式控制日志的启停，无需侵入到源代码中去进行修改

## Logback 日志框架有以下几个模块
* logback-core：基础模块，是其他两个模块依赖的基础
* logback-classic：完整实现了 slf4j API 的模块
* logback-access
* 想使用 Logback 日志框架，至少需要再项目中整合如下三个模块：
* slf4j-api：日志结构，logback-core，logback-classic

## Logback 快速入门
* 实现步骤
* 1、导入 Logback 框架到项目中
* 2、将 Logback 框架的核心配置文件 logback.xml 直接拷贝到 src 目录下
* 3、创建 Logback 框架提供的 Logger 对象，然后用 Logger 对象调用其提供的方法就可以记录系统的日志信息
* public static final Logger LOGGER = LoggerFactory.getLogger("类名);

## 核心配置文件 logback.xml
* 对 Logback 日志框架进行控制

## 什么是日志级别？
* 日志级别指的是日志信息的类型，日志都会分级别，常见的日志级别如下（优先级依次升高）：
* 1、trace：追踪，指明程序运行轨迹
* 2、debug：调式，实际应用中一般将其作为最低级别，而 trace 则很少使用
* 3、info：输出重要的运行信息，数据连接、网络连接、IO操作等，使用较多
* 4、warn：警告信息，可能会发生问题，使用较多
* 5、error：错误信息，使用较多

## 为什么要学习日志级别？
* <root level="info">...</root>，logger 配置文件里的
* 只有日志的级别是大于或等于核心配置文件配置的日志级别，才会被记录，否则不记录