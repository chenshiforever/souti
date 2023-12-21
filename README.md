# souti-api
网课搜题的api，自己的服务器，限制了请求频率


网课题库查题接口API 更新时间: 2023/12/8


### 接口介绍

支持各种网课平台的答案查询

收录很多道题目，并在不断更新。

#### 题目数据来源于互联网，非爬取网课平台题库，如有侵权请联系删除

### 接口地址

| 方法 | URL                                         | 传递参数                         | 
| -----| --------------------------------------------| --------------------------------|
|post  | [http://152.136.105.246/search](http://152.136.105.246/search) | question=问题
请求频率:5s/次

python语法
```python
import requests

url = "http://152.136.105.246/search"

payload='question=12345'
headers = {
  'Content-Type': 'application/x-www-form-urlencoded'
}

response = requests.request("POST", url, headers=headers, data=payload)

print(response.text)
```
nodejs语法
```nodejs
var axios = require('axios');
var qs = require('qs');
var data = qs.stringify({
  'question': '12345' 
});
var config = {
  method: 'post',
  url: 'http://152.136.105.246/search',
  headers: { 
    'Content-Type': 'application/x-www-form-urlencoded'
  },
  data : data
};

axios(config)
.then(function (response) {
  console.log(JSON.stringify(response.data));
})
.catch(function (error) {
  console.log(error);
});

```
js语法
```
var myHeaders = new Headers();
myHeaders.append("Content-Type", "application/x-www-form-urlencoded");

var urlencoded = new URLSearchParams();
urlencoded.append("question", "12345");

var requestOptions = {
  method: 'POST',
  headers: myHeaders,
  body: urlencoded,
  redirect: 'follow'
};

fetch("http://152.136.105.246/search", requestOptions)
  .then(response => response.text())
  .then(result => console.log(result))
  .catch(error => console.log('error', error));
```
php语法
```php
<?php
$client = new Client();
$headers = [
  'Content-Type' => 'application/x-www-form-urlencoded'
];
$options = [
'form_params' => [
  'question' => '12345'
]];
$request = new Request('POST', 'http://152.136.105.246/search', $headers);
$res = $client->sendAsync($request, $options)->wait();
echo $res->getBody();
?>
```
返回样例
```json
[
  {
    "scores": 37,
    "question": "智慧职教: 螺纹的画法中，说法正确的是（     ）。",
    "answer": "内外螺纹连接时，按照外螺纹绘制。\u0001螺纹终止线用粗实线。\u0001无论是内螺纹还是外螺纹，剖面线都绘制到粗实线。\u0001钻孔底部的锥角为120°"
  },
  {
    "scores": 31.8,
    "question": "智慧职教: 燃烧的特征有",
    "answer": "发光\u0001发热\u0001新物质"
  },
  {
    "scores": 31.8,
    "question": "智慧职教: 性格的特征是（）。",
    "answer": "态度特征\u0001意志特征\u0001情绪特征\u0001理智特征"
  },
  {
    "scores": 28.6,
    "question": "智慧职教: 下面是螺纹在图样上的标注，其中正确的是（ ）",
    "answer": "M16-5g6g"
  },
  {
    "scores": 28,
    "question": "智慧职教: 传动螺纹要求有较高的效率，常采用（ ）",
    "answer": "多线螺纹"
  },
  {
    "scores": 27.3,
    "question": "智慧职教: 螺纹按旋向分为左旋和右旋两种。",
    "answer": "正确"
  }
]
```

### 接口地址

| URL                                | 传递参数                    | 
| -----------------------------------| --------------------------- |
| http://152.136.105.246/img?src=url | src=图片url                 
图片OCR识别文字接口，直接传图片地址就行，[样例图片](https://gimg2.baidu.com/image_search/src=http%3A%2F%2Fb-ssl.duitang.com%2Fuploads%2Fitem%2F201611%2F07%2F20161107124135_nS5CW.jpeg&refer=http%3A%2F%2Fb-ssl.duitang.com&app=2002&size=f9999,10000&q=a80&n=0&g=0n&fmt=auto?sec=1701889418&t=a5879f1d1505d88cf1ea430a19401da3)，识别结果：[年年月月花相似岁岁年年人相同还是一个人●●●](http://152.136.105.246/img?src=https://gimg2.baidu.com/image_search/src=http%3A%2F%2Fb-ssl.duitang.com%2Fuploads%2Fitem%2F201611%2F07%2F20161107124135_nS5CW.jpeg&refer=http%3A%2F%2Fb-ssl.duitang.com&app=2002&size=f9999,10000&q=a80&n=0&g=0n&fmt=auto?sec=1701889418&t=a5879f1d1505d88cf1ea430a19401da3)


