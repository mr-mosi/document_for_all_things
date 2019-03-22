# How To Code Javascrip?

## Important Notes

#### 1. Numbers, Strings and Operators

1. `1 << 2;`: Shifts `1` two times.
2. **Infinity;**: result of e.g. 1/0
3. **-Infinity;**: result of e.g. -1/0
4. **NaN;**: result of e.g. 0/0, stands for 'Not a Number'
6. Equality is ===
7. Inequality is !==
8. Double equals ignore the type e.g "5" == 5; // = true
9. access characters in a string with `charAt`
"This is a string".charAt(0); // = 'T'
10. Use `substring` to get larger pieces. 
"Hello world".substring(0, 5); // = "Hello"
11. `length` is a property, so don't use (). 
"Hello".length; // = 5
12. false, null, undefined, NaN, 0 and "" are falsy; everything else is truthy. Note that 0 is falsy and "0" is truthy, even though 0 == "0".

#### 2. Variables, Arrays and Objects

1. If you leave the var keyword off, you won't get an error...
someOtherVar = 10;

...but your variable will be created in the **global** scope, not in the scope you defined it in.

2. We have ++ and -- like C lang. someVar++ // = add one to someVar
3. myArray.unshift(3); // Add 3 as the first element
4. someVar = myArray.shift(); // Remove first element and return it
5. Join all elements of an array with semicolon
var myArray0 = [32,false,"js",12,56,90];
myArray0.join(";") // = "32;false;js;12;56;90"
6. Get subarray of elements from index 1 (include) to 4 (exclude)
myArray0.slice(1,4); // = [false,"js",12]