# Files
## mission-10-tcp-time-server.js
```js
var http = require('http'),
    fs = require('fs'),
    port = process.argv[2],
    path = process.argv[3],
    server = http.createServer(function(req, res) {
        var fsStream = fs.createReadStream(path);
        fsStream.pipe(res);
    });
server.listen(port);
```
# Command
```console

```
    
# Output
```html
........
```
    
# Notes
- createReadStream(path)
- src.pipe(dest)