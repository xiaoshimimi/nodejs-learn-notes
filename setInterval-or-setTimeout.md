**Usage:**

```
var interval = setInterval(callback, delay[, arg][, ...]);
clearInterval(interval);
var timeout = setTimeout(callback, delay[, arg][, ...]);
clearTimeout(timeout);
```

__Example:__
```
function computeArea(x,y){
  return x*y;
}
var interval = setInterval(computeArea, 1000, Math.random(10), Math.random(10));
```

* * *

* __Remember:__
  * Don't use '()' in first parameter, just put the function name
  * Parameters are put after delay
