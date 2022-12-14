## js基础

## 变量
1. 变量就是一个用来存储数据的容器
2. 声明变量使用var关键字
3. 变量的声明
```js
 var name = `右侧叫表达式`
 //var 是声明变量的关键字
 //name 是变量的名字
 //= 赋值运算符
 // 等号=右边叫表达式
```
4. var提升变量，只是把变量提升到作用域的最顶层，变量的赋值不会提升，依然保留原始位置

## 内存分配
1. 内存中的栈【有序存储】：存储基础数据类型的数据【字符串，数字，布尔值】
2. 内存中的堆【无序存储】：存储的是复杂/引用类型的数据【对象，数组】

## 变量命名规范
1. 【重点】变量名不可以是js的关键字或保留字
2. 变量的名字不可以用数字开头，更不能是纯数字和其他非英文字母的字符，虽然可以用中文，做变量名字，但一般不这么写
3. 变量可以使用`$`、`_`、以及英文字母做变量名
4. 命名的时候应该遵循语义化规则：让变量有实际的含义，实在不行可以使用拼音【不推荐】
5. 对于多个单词拼接的变量名应该使用驼峰命名法：
 - 大驼峰命名法：myname=>MyName;每个单词的首字母大写
 - 小驼峰命名法：myname=>myName;除了第一个单词，剩下的单词首字母大写
 6. 变量的首字母应该对应着数据类型
 - 字符串：`var s_name`
 - 数字：`var n_name`
 

 ## 作用域
 - 定义：程序生效的空间
 - 全局的作用域：script【脚本】
   - 顶级对象：window、document
   - window又叫BOM
   - document又叫DOM
   - BOM包含着DOM
 - 局部的作用域：function【函数】、module【es6】
   - 顶级对象：this
   - 内部声明的变量
   - 声明在局部作用域中的变量不可以在外部使用，但是如果不使用关键字声明变量，否则会背提升到全局作用域中
   - 函数天生有返回值，返回默认是undefined


   ## 数据类型
   ## 基本数据类型【内存的栈里面存储】
   - 数字
   - 字符串
   - 布尔值
   - 空值 null
   - 未定义 undefined
   - 不是数字 nan

   ## 引用数据类型
   - 对象
   - 数组
   - 函数
   - 正则

   ## 基本数据类型和引用数据类型区别
   - 基本数据类型在赋值的时候是在栈里面开一个新的空间，多个变量使用同一个值，也是对值的深拷贝，每个值拥有独立的空间
   - 引用数据类型在赋值的时候是在堆里面开一个空间，把存储空间的标识码赋给了变量，多个变量赋值同为一个对象的时候，只是简单地复用了标识码的引用，俗称浅拷贝。


   ## 类型转换
   1. 字符串->数组
   2. 字符串->数组
   3. 所有的数据互相之间都可以转换

   ## 显示转换
   很直观的从代码上可以看出来是在转换数据类型
  1. 使用数据的构造函数：String()
  2. 使用方法，比如转成字符串可以使用toString方法
   ## 隐式转换
  1. if的表达式可以隐式转换
  2. +任何值和字符串，都会被转成字符串
  3. 除了+，其他的减乘除都是尝试把数据转换成数字进行计算
  4. 逻辑运算符也会隐式转换数据


  ## 数据类型检测
  1. typeof：对基本数据类型检测好用，对于引用数据类型全都是object
  2. instanceof：检测一个值是不是属于一个数据原型上的，对于引用速狙很精准，对于基本数据不精准
  3. constructor：可以检测基本数据类型和引用数据类型，但是对于控制类型，不能检测出来，因为空值类型没有构造函数
  4. Object.prototype.toString.call()：可以检测所有的数据类型