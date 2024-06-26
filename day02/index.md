## 什么是关键字？
* 被 Java 赋予了特定含义的英文单词

## 关键字的特点？
* 关键字的字母全部小写
* 常用的代码编辑器，对关键字有特殊颜色标记

## class 关键字是什么意思？
* class 关键字表示定义一个类，后面跟随类名

## 什么是字面量？
* 数据在程序中的书写格式

## Java 中字面量的分类？
* 整数类型、小数类型、字符串类型、字符类型、布尔类型、空类型

## 一些特殊字面量的书写
* 制表符：\t
* 空类型：null

## 什么是变量？
* 在程序的执行过程中，其值有可能发生改变的量(数据)
* 数据类型 变量名 = 数据值;

## 变量使用场景
* 当某个数据经常发生改变时，我们也可以用变量存储。当数据变化时，只要修改变量里面记录的值即可

## 变量的注意事项
* 只能存一个值
* 变量名不允许重复定义
* 一条语句可以定义多个变量
* 变量在使用之前一定要进行赋值
* 变量的作用域范围

## 计算机中的数据存储
* 在计算机中，任意数据都是以二进制的形式来存储的
* 二进制：有 0 和 1 组成，代码中以 0b 开头
* 八进制：有 0-7 组成，代码中以 0 开头
* 十进制：有 0-9 组成，前面不加任何前缀
* 十六进制：有 0-9 和 A-F 组成，代码中以 0x 开头

## 任意进制转十进制
* 公式：系数 * 基数的权次幂 相加
* 系数：就是每一位上的数
* 基数：当前进制数
* 权：从右往左，依次为 0 1 2 3 4 5

## 十进制转任意进制
* 除基取余法
* 不断的除以基数（几进制，基数就是几）得到余数，直到商为 0，再将余数倒着拼接起来即可

## 三原色
* 计算机中的颜色采用光学三原色
* 光学三原色：红、绿、蓝，也称之为 RGB
* 可以写成十进制形式（255, 255, 255）
* 也可以写成十六进制形式（FFFFFF）

## 计算机的存储规则
* Text 文本 -> 数字(转二级制)、字母(查询码表转成数字然后转二进制)、汉字(查询码表转成数字然后转二进制)
* Image 图片：通过每一个像素点中的 RGB 三原色来存储
* Audio 音频：对声音的波形图进行采样再存储，采样率越高，存储的越精确

## 数据类型
* Java 语言的数据类型分为：基本数据类型、引用数据类型
* 基本数据leix的四类八种：
* 整数类型：byte | short | int | long
* 浮点型类型：float | double
* 字符类型： char
* boolean 类型：true | false
* byte 的取值范围：-128~127
* 整数和浮点数取值范围大小关系：double > float > long > int > short > byte
* long 类型变量：需要加入 L 标识(大小写都可以)
* float 类型变量：需要加入 F 标识（大小写都可以）

## 标识符
* 就是给类、方法、变量等起的名字
* 标识符命名规则 --- 硬性要求(由数字、字母、下划线_和美元符$组成，不能以数字开头，不能是关键字，区分大小写)
* 标识符命名规则 --- 软性建议(小驼峰命名法: 方法、变量，大驼峰命名法：类名)

## 键盘录入
* Java 帮我们写好了一个类叫 Scanner，这个类可以接收键盘输入的数字
