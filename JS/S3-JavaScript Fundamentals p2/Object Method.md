
```js
const ammar ={
	firstName : 'ammar',
	lastName  : 'abdo' ,
	birthDate : 2003,
	job       : 'student',
	friends   : ['anas','ali' ,'b3dsh'],
	/*Method*/
	/*
	calcAge   : function (birthDate){
		return 2025 - birthDate;
	}
	*/
	/*
	calcAge   : function (){
		//console.log(this); // show the object properties
		return 2025 - this.birthDate;
	}
	*/
	calcAge   : function (){
		this.age = 2025 - this.birthDate; // create a new porperty
		return age;
	}
};

console.log(ammar.calcAge(2003)) // 22 
console.log(ammar['calcAge'](2003)) // 22 
```