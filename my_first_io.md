# Files
## mission-3-io.js

    var fs = require('fs'),
        content = fs.readFileSync(process.argv[2]).toString();
    console.log(content.split('\n').length - 1);
    
# Command

    node mission-3-io.js ./mission-3-io.js
    
# Output

    3
    
# Notes

### fs.readSync
- Synchronous version of *fs.read*. Returns the number of *bytesRead*.
- returns *Buffer*