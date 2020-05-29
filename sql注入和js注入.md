# sql注入和js注入的学习和防范

菜鸟程序员的一步步提升，记录备忘，同时分享。

平时一直没空写blog，今天项目上处理安全性问题。
sql注入和js是极为常见的安全性问题。

### 产生后果

通过注入js代码，进行跨站脚本攻击，窃取用户数据。
修改网页内容
...

## js注入

### 出现位置

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

## sql注入

##出现情况
拼接在sql查询语句后，查出数据库数据

