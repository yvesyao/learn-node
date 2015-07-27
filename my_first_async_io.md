# Files
## mission-4-async-io.js

    var fs = require('fs');
    fs.readFile(process.argv[2], 'utf8', function(err, data) {
        if (err) throw err;
        console.log(data.split('\n').length - 1);
    })
    
# Command

    node mission-4-async-io.js ./mission-3-io.js
    
# Output

    3
    
# Notes

### fs.readFile(filename[, options], callback)
- *filename* String
- *options* Object
    - encoding String | Null default = null
    - flag String default = 'r'
- *callback* Function

>Asynchronously reads the entire contents of a file. Example:
 
    fs.readFile('/etc/passwd', function (err, data) {
      if (err) throw err;
      console.log(data);
    });
    
 The callback is passed two arguments (err, data), where data is the contents of the file.
 
 If no encoding is specified, then the raw buffer is returned.