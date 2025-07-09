
-> `===` is called the strict equality operator .
strict doesn't perform type coercion and so it only returns 
true when both values are exactly the same (the value and type) .

```js
if(18 === '18') // false
if(18 === 18) // true 
```

------------------------------
-> `==` does preform the type coercion 

```js
if(18 == '18') // true
if(18 == 18)   // true 
```


----------------------
in practice always use ---> `===` to avoid unexpected bugs .