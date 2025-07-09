

## JavaScript Assignment Operators

Assignment operators assign values to JavaScript variables.

| Operator | Example | Same As    |
| -------- | ------- | ---------- |
| =        | x = y   | x = y      |
| +=       | x += y  | x = x + y  |
| -=       | x -= y  | x = x - y  |
| *=       | x *= y  | x = x * y  |
| /=       | x /= y  | x = x / y  |
| %=       | x %= y  | x = x % y  |
| **=      | x **= y | x = x ** y |

---

## Shift Assignment Operators

| Operator | Example  | Same As     |
| -------- | -------- | ----------- |
| <<=      | x <<= y  | x = x << y  |
| >>=      | x >>= y  | x = x >> y  |
| >>>=     | x >>>= y | x = x >>> y |
 ( >>>= ) -> ==unsigned== right shift

-------

## Bitwise Assignment Operators

|Operator|Example|Same As|
|---|---|---|
|&=|x &= y|x = x & y|
|^=|x ^= y|x = x ^ y|
|\|=|x \|= y|x = x \| y|

---

## Logical Assignment Operators

|Operator|Example|Same As|
|---|---|---|
|&&=|x &&= y|x = x && (x = y)|
|\|=|x \|= y|x = x \| (x = y)|
|??=|x ??= y|x = x ?? (x = y)|

* ==**&&=**== -> The **Logical AND assignment operator**
	mean
	```js
	if(x){
		x=y
	}
	```

* ==**||=**== -> The **Logical OR assignment operator**
	mean
	```js
	if(!x){
		x=y
	}
```

* **==??= ==** -> The **Nullish coalescing assignment**
	mean
	```js
	if(x==null || x == undefiened){
		 x=y
	}
	```
	