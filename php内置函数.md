### php内置函数
##### 一、数组篇
#### 1、array_combine($arr1,$arr2);
```
解释：
函数作用：将两个长度一致的数组按键值对形式组成新的数组。注意参数数组长度要一样；
$arr1的元素为key，$arr2的元素为value

例子：
$a = [1,2,3];
$b = ['a','b','c'];
$c = array_combine($a,$b);

$c输出为:
Array
(
   [1] => a
   [2] => b
   [3] => c
)
```

#### 2、range($start,$end);
```
解释：
函数作用：创建一个在指定范围的数组。包含$start和$end

例子：
$c = range(1,4);
$c 输出为：
[1,2,3,4]

$c = ['a','f'];
$c输出为：
['a','b','c','d','e','f']


```

#### 3、array_chunk($arr,$size,$boolean);
```
解释：
函数作用：将数组按指定长度拆分为多个数组。
$arr:原数组
$size:新数组长度。最后一个新数组长度可能不足$size。
$boolean:新数组索引是否保留原数组键名。默认false，新数组索引从0开始。

例子：
$a = ['a','b','c','d','e'];
$b = array_chunk($a,2,true);
$c = array_chunk($a,2);
print_r($b);
print_r($c);

$b输出为：
Array
(
   [0] => Array
       (
           [0] => a
           [1] => b
       )
   [1] => Array
       (
           [2] => c
           [3] => d
       )
   [2] => Array
       (
           [4] => e
       )
)

$c输出为：
Array
(
   [0] => Array
       (
           [0] => a
           [1] => b
       )
   [1] => Array
       (
           [0] => c
           [1] => d
       )
   [2] => Array
       (
           [0] => e
       )
)
```

#### 4、array_count_values($arr);
```
解释：
函数作用：计数原数组中的元素个数，并以键值对形式的数组返回。键为元素，值为该元素在原数组中出现的次数。
例子：
$a=array("A","Cat","Dog","A","Dog");
print_r(array_count_values($a));

结果输出：
Array ( [A] => 2 [Cat] => 1 [Dog] => 2 )
```

#### 5、array_diff_assoc($arr1,$arr2...);
```
解释：
函数作用：返回一个数组，该数组元素属于$arr1中的键值对，但没有在后续数组中出现过的键值对元素。

例子：
$a1=array("a"=>"red","b"=>"green","c"=>"blue","d"=>"yellow");
$a2=array("a"=>"red","f"=>"green","g"=>"blue");
$a3=array("h"=>"red","b"=>"green","g"=>"blue");

$result=array_diff_assoc($a1,$a2,$a3);
print_r($result);

输出结果为：
Array
(
   [c] => blue
   [d] => yellow
)
```
