# week2学习笔记
```
payload = {
    "keyword":"文学与传媒学院",
    "p":"1"
}
session = HTMLSession()
r = session.get("http://www.nfu.edu.cn/index.php/home/article/search.html", params=payload)
```
* 运行后返回结果为200，则是跳转成功
* keyword表示要查找的关键词
* p表示页数
```
r.html.html 
with open ("D:/20春_Web数据挖掘_week02_nfu_文学与传媒学院.html", encoding = "utf8", mode = "w") as fp:
    fp.write(r.html.html)
```
* 将读取到的网页文字档，保存为本地html文档
  * 代码为 with open("HTML档需保存的路径＋文档名"，encoding="utf8",mode="w") as fp: fp.write(r.html.html)
```
解析后.xpath('//div[@class="news_title"]/a/@title')
解析后.xpath('//div[@class="news_title"]/a/text()')
```
* 比较这两个xpath后面的值，总结了：
  * 当要取a标签里的值，如```<a title="值">文</a>```，需用用到@＋元素
  * 当要取是取a标签的文本，如``` <a>文本（text）</a> ```，需要用到text()
```
r.html.xpath('//div[@class="news_title"]/preceding-sibling::font/text()')
```
* preceding-sibling:: 表示获取[兄节点](https://blog.csdn.net/hb5cn/article/details/84937449)
  * 因为最靠近font标签的是下级的div标签，所以用preceding-sibling::表示获取div的兄节点标签font的文本内容，这样避免xpath过长
