# web_mining
### C-3代码
```
df = pd.DataFrame(
    {
"职称" : r.html.xpath('//*[@class="name-text"]/text()'),
"链结" : r.html.xpath('//*[@class="flex-2 job-name"]/@href'),
"薪水" : r.html.xpath('//*[@class="text-warning flex-1"]/text()'),


    }
)
df.to_excel("D:/20春_Web数据挖掘_week02_liepin.xlsx", sheet_name="搜查结果")
df
```
