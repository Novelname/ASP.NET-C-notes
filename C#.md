# C#语言基础

### 常用命名空间
>using system

|命名空间|功能|
| -------------------- | --------------------------------------------------------------------------- |
| System               | 提供基本类，如提供字符串操作的String类                                      |
| System.Configuration | 提供处理配置文件中数据的类                                                  |
| System.Data          | 提供对ADO.NET类的访问，如提供数据缓存的DataSet类                            |
| System.Linq          | 提供使用LINQ进行查询的类和接口，如包含标准查询运算符的Queryable类           |
| System.Web           | 提供使浏览器与服务器相互通信的类和接口，如用于读取客户端信息的HTTPRequest类 |
| System.Web.Security  | 提供在Web服务器实现ASP.NET安全性的类，如用于验证用户凭据的MemberShip类      |
| System.Web.UI        | 提供用于创建ASP.NET网站用户界面的类和接口，如每个Web窗体都继承的Page类|
|System.Web.UI.HTMLControls                      ||
|System.Web.UI.WebControls    ||
|System.Web.UI.WebControls.WebParts   |提供用于创建个性化Web部件页的类和接口，如呈现模块化用户界面的Part类   |
|System.Xml.Linq    | 提供用于LINQ to XML的类，如获取XML元素的Xelement类  |
### 程序注解
多行注释为/* */

单行注释为 //

类、方法、属性、接口的注释采用XML文档格式注释

### 命名规则
#### Pascal形式
&emsp;&emsp;指将标识符的首字母和后面连接的每个单词的首字母都大写，如BackColor
#### Camel形式
&emsp;&emsp;指标识符的首字母小写，而每个后面连接的单词的首字母都大写，如backColor
#### 常用标识符的大小写方式对应表
| 标识符         | 方式   | 实例      |
| -------------- | ------ | -------------- |
| 类             | Pascal | APPDomain      |
| 枚举类型       | Pascal | ErrorLevel     |
| 枚举值         |        | FatelError     |
| 事件           |        | ValueChanged   |
| 异常类         |        | WebException   |
| 只读的静态字段 |        | RedValue       |
| 接口           |        | IDisposable    |
| 方法           |        | ToString       |
| 命名空间       |        | System.Drawing |
| 参数           | Camel  | typeName       |
| 属性           | Pascal | BackColor      |
| 变量名         | Camel  | dateConnetion  |
#### 命名的其他规则
* 常量名都要使用大写字母，用下划线"_"分割单词
* 除局部循环变量外，一般变量名不得取单个字符
* 类的成员变量(属性所对应的变量)使用前缀"_"
* 接口的命名在名字前加上"I"前缀，如IDisposable
#### 常用控件名简写对照表
| 控件名 | 简写 | 控件名 | 简写 |
| -------------------------- | ------ | ---------------------- | ------ |
| Label                      | lbl    | TextBox                | txt    |
| Button                     | btn    | LinkButton             | lnkbtn |
| ImageButton                | imgbtn | DropDownList           | ddl    |
| ListBox                    | lst    | DataGrid               | dg     |
| DataList                   | dl     | CheckBox               | chk    |
| CheckBoxList               | chkls  | AdRotator              | ar     |
| RadioButtonList            | rdolt  | Table                  | tbl    |
| Panel                      | pnl    | Caleder                | cld    |
| RadionButton               | rdo    | Image                  | img    |
| RangeValidator             | rv     | RequiredFieldValidator | rfv    |
| CompareValidator           | cv     | ValidatorSummary       | vs     |
| RegularExpressionValidator | rev    |                        |        |
#### 常量声明
`const`
>C#不区分大小写
### 修饰符
public 访问不受限制，任何地方都可以访问
internal  在当前程序中能被访问
protected  在所属的类或派生类中能被访问
protected internal  在当前的程序或派生类中能被访问
private  在所属的类中能被访问
static 静态变量又称静态字段。
readonly

### 局部变量作用范围
* 块级：作用域范围最小的变量，在块结束后即被删除。
* 方法级：作用于声明变量的方法中，在方法外即不能访问。
* 对象级：作用于定义类的所有方法中，只有相应的ASP.NET页面结束时才被删除。

### 数据类型
* 值类型
&emsp;&emsp;值类型的变量直接包含它们的数据，而引用类型存储对它们的数据的引用。一个变量的操作不会影响另一个变量；而对于引用类型，两个变量可能引用同一个对象，因此对一个变量的操作可能会影响到另一个变量。
  1. 简单类型：整数类型、布尔类型(true/false)、字符类型(Unicode，一个字符长度为16位)和实数类型(float-f/F、double、decimal-M/m)：
  2. 结构类型 struct
  3. 枚举类型 enum，枚举中每个元素默认是整数类型。且第一个值为0。
#### 常用转义符对应表
| 转义符 | 对应字符 | 转义符 | 对应字符  |
| ------ | ------- | ------ | -------- |
| \\'    | 单引号   | \\a    | 感叹号   |
| \\"    | 双引号   | \\n    | 换行     |
| \\     | 反斜杠   | \\r    | 回车     |
| \\0    | 空字符   | \b     | 退格     |
* 引用类型
  1. class类型---->Object类型(System.Object)、String类型
&emsp;&emsp;Int32.Parse()方法或Convert.ToString()类
  2. 接口类型---->常用来描述组件对外能提供的服务，不能定义数据，只能定义方法、属性、事件等。包含在接口中的方法不定义具体实现，而是在接口的继承类中实现。
  3. 数组类型---->一组数据类型相同的元素集合。
  4. 委托类型---->委托是一种安全地封装方法的类型，类似于C和C++中的函数指针。委托是类型安全的。
### 装箱和拆箱
* 装箱和拆箱是实现值类型和引用类型相互转换的桥梁。
* 装箱的核心是把值类型转化为对象类型，也就是创建一个对象并把值赋给对象。
* 拆箱的核心是把对象类型转换为值类型，即把值从对象实例中复制出来。
### 流程控制
* 选择结构
  1. if语句
  2. switch语句
* 循环结构
  1. while语句
  2. do-while循环
  3. for语句
  4. foreach语句 (foreach(数据类型 循环变量 in 集合))
### 异常处理
* 异常的产生常由于激发了某个异常的条件，使得操作无法正常进行。
* 异常处理能使程序更加健壮，容易让程序员对捕获的错误进行处理
* 异常处理常用两种形式：throw和try...catch...finally
  1. throw语句用于抛出异常错误信息
  2. try...catch...finally
&emsp;&emsp;异常捕获由try块完成，处理异常的代码放在catch块，而在finally块中的代码不论是否有异常发生总会被执行。catch块可多个。
```
try{
  //可能出错的语句序列
}
catch(异常声明1){
  //捕获异常后执行的语句序列
}
catch(异常声明2){

}
finally{
  //总是执行的语句块
}
```
