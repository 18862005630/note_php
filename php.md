### note php
#### 1、4种标记风格(默认第一种，且第一种尾标签可以省略)
```
<?php
	echo "第一种标记风格";
?>

<script language="php">
	echo '第二种标记风格';
</script>

<? echo "第三种标记风格"; ?>

<%
	echo "第四种标记风格";
%>
```

#### 2、php数据类型
```
4种标量类型： 
boolean（布尔类型）true/false 不区分大小写
integer(整型)
float/double(浮点型)
string(字符串)

2种复合类型：

array（数组）:

$arr = ('a','b','c');
or
$arr = array(key1=value1,key2=>value2);
or
$arr[key] = value;

object（对象）

2种特殊类型：
resource(资源)
NULL
```

#### 3、强制类型转换
```
$num1 = '3.14';
$num2 = (integer)$num1;		------第一种强制类型转换方法
echo $num2;		--------3
echo $num1;		--------3.14,原值不变
echo settype($num1,'integer');		------1，类型转换成功输出1，转换失败输出0，settype函数有输出值，且改变原值value，此为第二种强制类型转换方法
echo $num1;		--------3
```

#### 4、字符串操作函数
```
#### 一、字符串去空和特殊字符
charlist特殊字符包括：
\0 :NULL
\t :tab制表符
\n :换行符
\x0B:垂直制表符
\r :回车符
"" :空格
charlist为可选，非必须参数

a.去除字符串中所有的空格或指定特殊字符
trim($str,charlist)
b.去除字符串左侧的空格或指定字符串
ltrim($str,charlist)
c.去除字符串右侧的空格或指定字符串
rtrim($str,charlist)

#### 二、转义、还原字符串数据
手动转义是通过转义字符'\'，改变转义字符后面的字符含义

自动转义、还原：
a.addslashes($str) 转义
b.stripslashes($str) 还原

此自动转义还原用于缓存文件，一般转义成八进制显示，如缓存文件名之类
a.addcslashes($str,charlist)	----自动转义，charlist为需要指定的字符串，为必填参数
b.stripcslashes($str)	-----自动还原为原字符串


#### 三、字符串长度，截取
int strlen($str) 获取字符串长度，中文占2个字符

截取英文字符串：substr($str,$start,$len)
$str:需要截取的字符串
$start:字符串截取的开始位置，正向截取时第一个位置为0
此变量为负数时，表示从倒数第$start位置开始截取，包含当前$strat位置的字符
$len:字符串截取的长度，为负数时，表示截取到末尾第$len个位置的字符，且不包含当前$len位置的字符

截取中文字符串：mb_substr($str,$start,$len,'utf-8')

#### 四、字符串比较
a.按字节进行字符串比较（多用于用户登录比较用户名和密码，区分大小写更安全）
strcmp($str1,$str2)		-----需要区分大小写，相等输出0，str1大于str2输出正数，小于时输出负数
strcasecmp($str1,$str2)		-----不区分大小写

```