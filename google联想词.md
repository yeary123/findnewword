# 获取 Google 联想词（data-entityname 纯文本）

在浏览器控制台执行以下代码，可获取联想建议列表的纯文本（去掉 `<b>` 等标签）：

```javascript
const items = document.querySelectorAll('li[data-entityname]');
const names = Array.from(items).map(li => {
  const raw = li.getAttribute('data-entityname');
  const div = document.createElement('div');
  div.innerHTML = raw.replace(/&lt;/g, '<').replace(/&gt;/g, '>').replace(/&amp;/g, '&');
  return (div.textContent || div.innerText || '').trim();
});
console.log(names);
```

执行后，`names` 即为联想词列表数组。

---

## Google Trends 批量链接

关键词数组对应的 Explore 链接（`date=now 7-d`, `geo=Worldwide`）：

| 关键词 | 链接 |
|--------|------|
| image to text | https://trends.google.com/explore?q=image%20to%20text&date=now%207-d&geo=Worldwide |
| humanize ai text | https://trends.google.com/explore?q=humanize%20ai%20text&date=now%207-d&geo=Worldwide |
| image to text converter | https://trends.google.com/explore?q=image%20to%20text%20converter&date=now%207-d&geo=Worldwide |
| bold text generator | https://trends.google.com/explore?q=bold%20text%20generator&date=now%207-d&geo=Worldwide |
| fancy text generator | https://trends.google.com/explore?q=fancy%20text%20generator&date=now%207-d&geo=Worldwide |
| blank text | https://trends.google.com/explore?q=blank%20text&date=now%207-d&geo=Worldwide |
| invisible text | https://trends.google.com/explore?q=invisible%20text&date=now%207-d&geo=Worldwide |
| bold text | https://trends.google.com/explore?q=bold%20text&date=now%207-d&geo=Worldwide |
| audio to text | https://trends.google.com/explore?q=audio%20to%20text&date=now%207-d&geo=Worldwide |
| sublime text | https://trends.google.com/explore?q=sublime%20text&date=now%207-d&geo=Worldwide |
