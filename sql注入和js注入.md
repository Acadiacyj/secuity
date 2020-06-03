# sql注入和js注入的学习和防范

菜鸟程序员的一步步提升，记录备忘。

sql注入和js是极为常见的安全性问题。

### 产生后果

通过注入js代码，进行跨站脚本攻击，窃取用户数据。
修改网页内容，虽然只是在客户端，但是同样有很大问题，如欺骗页面或绕过安全验证
...

## js注入

## 出现位置

在url或输入框/表单中输js脚本

### url中
在地址框中输入
```markdown
JavaScrip:alert('1111')
JavaScript:alert(document.input.submit.value='1111')
...
```
即可看到效果


### 输入框/表单
在输入框中输入js脚本，如input等
```markdown
<script>alert("1111")</script> 
```
进入提交后的页面（提交input中输入的<script>到数据库,网页再从数据库请求数据显示在界面上，执行js），即可看到效果

## 防范
1.表单中的注入，当数据显示时用HTML编码任何网站用户输入的数据，如：<%=Html.Encode(aaa.bbb)%>。即将如 < 和 > 符号替换为 HTML 实体，如 &lt; 和 &gt;。
2.表单中的注入，再将用户的数据传回数据库前使用
```markdown
StringEscapeUtils.escapeHtml（"<script>alert("1111")</script>"); 
```

## sql注入

## 出现位置
拼接在sql查询语句后，查出数据库数据

### 防范
1..过滤URL非法SQL字符
2.输入文本框防注入





有错误请多多指正，谢谢
