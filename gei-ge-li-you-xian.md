# 给个理由先
## Javascript
```
function greaterThan(n) {
return m => m > n;
}
let greaterThan10 = greaterThan(10);
console.log(greaterThan10(11));
// → true
```

```
function noisy(f) {
return (...args) => {
console.log("calling with", args);
let result = f(...args);
console.log("called with", args, ", returned", result);
return result;
};
}
noisy(Math.min)(3, 2, 1);
// → calling with [3, 2, 1]
// → called with [3, 2, 1] , returned 1
```

