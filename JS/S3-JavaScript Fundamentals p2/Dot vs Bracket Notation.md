
there's two ways of getting a property from an object.

==* with the dot notation.==

```js
objectname.key // value
```

```js
const ammar ={
firstName : 'ammar',
lastName  : 'abdo' ,
age       : 2025 -2003,
job       : 'student'
friends   : ['anas','ali' ,'b3dsh']
};
console.log(ammar); // show all properties in alpha bit order
console.log(ammar.firstName); // 'ammar'
console.log(ammar.friends[1]) // 'ali'
```

add a property after declaration.
```js
ammar.location = 'Egypt';

console.log(ammar.location) // 'Egypt'
```

------------------------------------

 ==*  with  the bracket notation==

```js
objectname['key']; // value
```


```js
const ammar ={
firstName : 'ammar',
lastName  : 'abdo' ,
age       : 2025 -2003,
job       : 'student'
friends   : ['anas','ali' ,'b3dsh']
};

console.log(ammar['lastName']) // abdo

const nameKey = 'Name';

console.log(ammar['first' + nameKey]) // 'ammar'
console.log(ammar['last'  + nameKey]) // 'abdo'

```

we can let the user choose which property he wants.

```js
const property = prompet("what do you want to know about me? choose between firstName, lastName, age, job and friends.");

// bracket accept the expression
console.log(ammar[property]) // value

// dot does't accept the expression
console.log(ammar.property) // undefined
```


add a property after declaration.
```js
ammar['location'] = 'Egypt';

console.log(ammar['location']) // 'Egypt'
```