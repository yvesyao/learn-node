# Files
## mission-7-http-client.js
```js
var http = require('http'),
    url = process.argv[2];

http.get(url, function(res) {/*
    console.log("Got response: ", res.statusCode);
    console.log('headers', res.headers);
    console.log('raw headers', res.rawHeaders);*/
    res. setEncoding('utf8');//设置后，接收到的数据就会转换为字符串（本来是Buffer）
    /*res.on("data", function (data) {//mine
        console.log(data);
    })*/
    res.on('data', console.log);//这种方法更高级一些！
}).on('error', function(e) {
    console.log("Got error: " + e.message);
});
```
# Command
```console
node mission-7-http-client.js www.baidu.com
```
    
# Output
```html
<!DOCTYPE HTML PUBLIC "-//IETF//DTD HTML 2.0//EN">
<html><head>
<title>400 Bad Request</title>
</head><body>
<h1>Bad Request</h1>
<p>Your browser sent a request that this server could not understand.<br />
</p>
</body></html>
```
    
# Notes

- http
- get
- response