# 跨站脚本攻击(XSS)
这个事例是一个基于node.js express框架的反射形XSS的演示。

## 如何使用

```
docker run --rm -it -p 3000:3000 $(docker build -q .)
```

启动后服务会监听3000端口，启用浏览器访问。请求时，添加参数xss相应的值会反射到页面中。

例1：
请求：`http://localhost:3000/?xss=%3Ciframe%20src=%22//examlpe.com/%22%3E%3C/iframe%3E`。结果：会在返回的页面上创建iframe，并显示相应的内容。
例2：
请求：`http://localhost:3000/?xss=%3Cimg%20src=%22null%22%20onerror=%22alert('xss')%22%3E`。结果：会在返回的页面上弹窗显示“xss”。

