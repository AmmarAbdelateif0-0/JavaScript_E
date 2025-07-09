strict mode is the mode which makes it easier for us to write a secure JavaScript code.

==so the strict mode really helped us avoid this kind of bugs.==

to active this mode
```js
'use strict'; // in the beginning of the script file
```

And when secure, I mean that strict mode makes it easier for us developers to avoid accidental errors.

So basically it helps us introduce the bugs into our code

and that's because of 2 reasons.

* strict mode forbids us to do certain things

 * it will actually create visible errors for us


```js
let hasDriversLicense = false;
const passTest = true ;
if(passTest) hasDriverLicense =true //hasDriverLicense not hasDriversLicense
if(hasDriversLicense) console.log('i can drive');

// here nothing happend and and console don't show to us where's error
```



```js
'use strict'
let hasDriversLicense = false;
const passTest = true ;
if(passTest) hasDriverLicense =true //hasDriverLicense not hasDriversLicense
if(hasDriversLicense) console.log('i can drive');

// the console will give us an error ->  hasDriverLicense is not defined (ReferenceError)
```

Now another thing that strict mode does is to introduce a short list of variable names that are reserved for features that might be added to the language a bit later.

example
```js
'use strict'
let interface = 'Audio';
// console will give us an error -> unexpected strict mode reserved word
```