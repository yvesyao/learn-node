# Files
## mission-10-tcp-time-server.js
```js
var net = require('net'),
    port = process.argv[2],
    server = net.createServer(serverAction);
server.listen(port);
function serverAction(socket) {
    var date = new Date();
    socket.end(date.getFullYear() + '-' + formatNumber(date.getMonth() + 1) + '-' + formatNumber(date.getDate()) + ' ' + formatNumber(date.getHours()) + ':' + formatNumber(date.getMinutes()) + '\n');
}
function formatNumber(integer) {
    return (integer/10 < 1 ? '0' : '') + integer;
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
- net
- tcp
- socket