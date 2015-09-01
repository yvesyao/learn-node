# Files
## mission-9-juggling-async.js
```js
var http = require('http'),
    urls = process.argv,
    urlCnt = urls.length - 2,
    result = [],
    count = 0;

function printResults() {
    console.log(result.join('\n'));
}
function queryResult(url, index) {
    http.get(url, function (res) {
        //mine
        var _result = '';
        res.setEncoding('utf8');//设置后，接收到的数据就会转换为字符串（本来是Buffer）
        res.on('data', function (data) {
            _result += data;
        }).on('end', function () {
            result[index] = _result;
            if(++count == urlCnt) {
                printResults();
            }
        });
    }).on('error', function (e) {
        console.log("Got error: " + e.message);
    });

}
for(var i = 0; i < urlCnt; ++i) {
   queryResult(urls[i + 2], i);
}
```
# Command
```console

```
    
# Output
```html
........
```
    
# Notes
