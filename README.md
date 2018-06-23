JS工具(字符串规格化、get/post/put/delete/patch请求、基本验证处理)
--------
*js字符串格式化*
```doc
方法:	String.prototype.format = function(args)
参数args:	param1,param2,...
返回:	经过格式化替换之后的内容
示例:	"{0},{1}".format("val1","val2");
```
*js正则验证*
```doc
方法:	String.prototype.validate = function(regularStr)
参数:
regularStr	正则表达式;(也可以引用$.validateRegular.xxx正则)
返回:	true验证成功,false失败;
示例:	"验证内容".validate($.validateRegular.OnlyNumber)
```
* [正则验证规则参数](/valid_rule.md)

*正则过滤*
```doc
方法:	String.prototype.filterString = function(regularStr)
参数:
regularStr	正则表达式
示例:	"今天是晴天".filterString("[天]+") 输出:天天
```
*统计字符串长度*
```doc
方法:	String.prototype.byteLength = function()
返回:	统计字符串的长度(汉字按2个字节计算)
示例:	"空ab1".byteLength()  输出长度为5
```
*比较两字符串是否相等*
```doc
方法:	String.prototype.equals = function(strarg)
参数:	strarg为其中一组比较内容
示例:
var str1="abc";
var str2="Abc";
str1.equals(str2) 输出 false
```
*比较两字符串是否相等(忽略大小写)*
```doc
方法:	String.prototype.equalsIgnoreCase = function(strarg)
参数:	strarg为其中一组比较内容
示例:
var str1="abc";
var str2="Abc";
str1.equalsIgnoreCase(str2) 输出 true
```
*字符串是否包含子字符串*
```doc
方法:	String.prototype.isContainerThisString = function(thisStr)
参数:	thisStr要查找的字符串
示例:	"qazabc5678".isContainerThisString("abc") 输出 true
```
*字符串从索引0开始是否包含指定字符*
```doc
方法:	String.prototype.isContainerThisCharByInitials = function(thisStr)
参数:	thisStr要查找的字符串
示例:	"qazabc5678".isContainerThisCharByInitials("abc") 输出 false
```
*字符串结尾是否包含指定字符*
```doc
方法:	String.prototype.isContainerThisCharByEnd = function(thisStr)
参数:	thisStr要查找的字符串
示例:	"qazabc5678".isContainerThisCharByEnd("78") 输出 true
```
*字符串反转*
```doc
方法:	String.prototype.reverseString = function()
示例:	"abc".reverseString() 输出 cba
```