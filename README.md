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

*JQuery扩展方法*
###### 1.基本方法
```doc
字符串空值判断
$.isNullOrEmpty("....") true:空;false:非空;

检测是否url地址
$.checkUrl(url) true:http或https开头url;false:非url;

返回url域名(主机地址最后带/)
$.protocol.domain()

获取当前Url参数值
$.UrlParams.get(paramkey)
paramkey:	url参数名

向当前url后面追加参数
$.UrlParams.adds(args)
args:	参数集(如:{key1:arg1,key2:arg2,...}或[{...}])
返回:	追加参数后完整的url

向当前url后面追加参数
$.UrlParams.add(keyname, value)
keyname:	参数键
value:		参数值
返回:	追加参数后完整的url

移除url参数
$.UrlParams.remove(key)
key:	需要移除参数的键
返回:	移除参数后完整的url

设置url中的参数值
$.UrlParams.set(key,value)
key:	需要设置的参数键
value:	需要设置的参数值
返回:	更新参数值后完整的url

根据脚本文件名获取脚本引用地址
$.getScriptUrl(scriptname)
scriptname:	脚本文件名(包含.js)
返回:	脚本文件url地址

获取GUID
$.GUID()
返回:	32+4位的GUID随机数

生成随机数
$.GetRandomNum(min,max)
min:	最小随机数
max:	最大随机数
返回:	在min和max范围内的随机数

限制字符串(可用于输入框输入固定长度的字符串)
(一个汉字算两个字符)
$.StrLimit(sourcestr, len)
sourcestr:	原字符串
len:		要限制的长度
返回:	从索引0开始,len长度的字符串
```
###### 2.GET\POST\PUT\DELETE\PATCH请求
```doc
以下数据提交和返回均是json;
在发起请求头里添加了以下两个参数:
token:$.cookie('token')	//因此在登录成功后要将token设置到cookie中
client:"h5" //服务端用于区分是哪个端做的请求


GET请求
$.Request.getRequest(url, data, successCall, completeCall)
url:	请求的完整url
data:	提交的数据{"key1":value1,"key2":value2,...}
successCall:	请求成功回调
function(response){
	//response为请求成功返回的结果
}
completeCall:	请求完成回调
function(){
	//请求完成回调
}
```