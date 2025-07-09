


![[Pasted image 20250617042434.png]]


* Content : text , images , etc.
* Padding : transparent area around the content , inside of the box .
* Border : goes around the padding and the content .
* Margin : space between boxes .
* Fill area : area that gets filled with background color or background image ( anything inside the border ).

first reset all padding and margin to zero 
```css
*{
	margin  : 0;
	padding : 0;
	/* alawyas use it */
	box-sizing : border-box;
}
```

without using the box-sizing if my width =100px and height = 50px and i do padding like 20px the width become = 140px and height  become = 90px

if i use it the width and height doesn't change


to select the selector inside specific element

```css
element-name selector{

}

/* ex  to select the patagraph inside the id call your-name */
#your-name p {

}
```