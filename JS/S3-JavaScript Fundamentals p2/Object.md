
in an array the element have no name, you can access them  only using the index. 

```js
const ammar =[
	'ammar',
	'abdo'.
	2025 - 2003,
	'student'
]
```

to solve that problem we have another data structure  in JavaScript  which is `object`.

in `object` we actually define key value pairs and so then we can give each of these values here a name.

there are multiple ways of creating objects.

--------------
a- object literal syntax.

```js
const /*let or var*/ objectname = {
key : value ,
key : value
};

//to access the element
console.log(objectname.key) // value
```

==key is also called property==

ex
```js
const ammar ={
firstName : 'ammar',
lastName  : 'abdo' ,
age       : 2025 -2003,
job       : 'student'
friends   : ['anas','ali' ,'b3dsh']
};

```


we use objects to essentially ==group together different variables that really belong together== such as the properties of `ammar` that we've been working with.

the big difference between objects and arrays, is that in objects, the order of these values does not matter at all when we want to retrieve them. 

So in arrays, the order in which we specify the elements matters a lot
because that's how we access these elements, right? 

So we can only access array elements using their order number.

This means that we should use arrays for more order data, and objects for more unstructured data And data that we actually want to name, and then retrieve from the object, based on that name.

next lec ->
[[Dot vs Bracket Notation]]
[[Object Method]]
