### QueryList php数据抓取
#### Thinkphp5中使用
##### 1、composer安装
>https://www.php.cn/php-weizijiaocheng-390846.html
命令composer查看安装是否成功
##### 2、Thinkphp5中安装querylist
项目根目录下执行 >composer require jaeger/querylist
```
use QL\QueryList;

class Test{
	$url = "....";
	//微信推文采集规则
	$rules = [
            'title' => ['.rich_media_title','text'],
            'date' => ['#post-date','text'],
            'author' => ['#meta_content>.rich_media_meta:eq(2)','text'],
            'content' => ['#js_content','html'],
            'view_source' => ['#js_view_source','href'],
            'image' => ['img','data-src']
        ];
	$data = QueryList::Query($url,$rules);
	print_r($data->getData());

	API文档:http://www.querylist.cc/docs/guide/v4/overview

```

