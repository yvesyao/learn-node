# Files
## mission-6-modular.js
```js
var dir = process.argv[2],
    ext = process.argv[3],
    mymodule = require('./module-for-6.js');
mymodule(dir, ext, function(err, data) {
    if (err) {
        console.log(err);
        return;
    }
    console.log(data.join('\n'));
});
```
## module-for-6.js
```js
module.exports = function(dir, ext, callback) {
    var fs = require('fs'),
        path = require('path'),
        result = [];
    fs.readdir(dir, function(err, files) {
        if (err) return callback(err);
        var length = files && files.length;
        for(var i = 0; i < length; ++i) {
            var filePath = files[i];
            if(path.extname(filePath).substr(1) === ext) {
                result.push(filePath);
            }
        }
        callback(null, result);
    })
};
```
# Command
```console
node mission-6-modular.js ./ js
```
    
# Output
```
mission-1-hello.js
mission-10-tcp-time-server.js
mission-11-http-server.js
mission-12-http-uppercaserer.js
mission-13-http-json-api-server.js
mission-2-baby-steps.js
mission-3-io.js
mission-4-async-io.js
mission-5-filtered-ls.js
mission-6-modular.js
mission-7-http-client.js
mission-8-http-collect.js
mission-9-juggling-async.js
module-for-6.js
test-http.js
```
    
# Notes

- exports
- require