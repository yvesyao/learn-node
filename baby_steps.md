# Files
## mission-2-baby-steps.js

    var params = process.argv,
        length = params.length,
        sum = 0;
    for(var i = 2; i < length; ++i) {
        var num = +params[i];
        if(!isNaN(num)) {
            sum += num;
        } else {
            break;
        }
    }
    console.log(sum);
    
# Command

    node mission-2-baby-steps.js 1 2 3
    
# Output

    6
    
# Notes

- Arguments starts at the 3th element(index 2)
         [ 'node', '/path/to/your/program.js', '1', '2', '3' ]
- All elements of process.argv are **strings** and you may need to coerce them into numbers. You can do this by prefixing the property with + or passing it to Number().
        +process.argv[2]
        Number(process.argv[2])