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

### fs.readFileSync
- Synchronous version of *fs.readFile*. Returns the number of *filename*.
- If the encoding option is specified then this function returns a string. Otherwise it returns a *Buffer*.