# Files
## mission-8-http-collect.js
```js
var http = require('http'),
    url = process.argv[2],
    count = 0;

function printResults() {
    console.log(result.join('\n'));
}
function queryResult(url) {
    http.get(url, function (res) {
        //mine
        var _result = '';
        res.setEncoding('utf8');//设置后，接收到的数据就会转换为字符串（本来是Buffer）
        res.on('data', function (data) {
            _result += data;
            count += data.length;
        }).on('end', function () {
            console.log(count);
            console.log(_result);
        });
    }).on('error', function (e) {
        console.log("Got error: " + e.message);
    });

}
queryResult(url);

```
# Command
```console
node mission-8-http-collect.js http://www.baidu.com
```
    
# Output
```html
........
```
    
# Notes

- response:data/end