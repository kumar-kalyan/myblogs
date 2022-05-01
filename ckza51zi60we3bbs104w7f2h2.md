## JavaScript string & methods

## Intro

JavaScript is the most popular language for web development, almost 95% of websites or webapps uses JavaScript, so it is essential for one to know about JavaScript if working on web. In this article I will explain about Strings in JavaScript which is one of the most important concepts of programming and also something which we use in our daily life.

## All about Strings 
 
String is basically a sentence or you can say a collection or a list of characters, like the content in this article are strings displayed to you. or suppose while you search something on google you get a list of links, or while you enter some characterized data like a paragraph in a survey form, they are also strings. In JavaScript `String` can be defined using `var` or `let` keyword

```
var str = "hello world, I'm a string";

console.log(str);
console.log(typeof str);

```
![String console ](https://cdn.hashnode.com/res/hashnode/image/upload/v1644080735167/fI4SAWr3h.png)


## Methods in String 

### length 

Suppose you want to find the length of a String (number of characters in a String ) in that case you can use 

```
var str = "hello world, I'm a string";
console.log(str.length);

```

![length of a String ](https://cdn.hashnode.com/res/hashnode/image/upload/v1644081253403/6gSowpd7g.png)

### Uppercase & Lowercase 

Suppose you want to capitalize each letter in String or you want every single character in your string to be in lowercase, well in that case you can use 
 

```
var capstr = "hello world";
var lowerstr = "HELLO WORLD";
console.log(capstr.toLowerCase());
console.log(lowerstr.toUpperCase());
``` 


![change case ](https://cdn.hashnode.com/res/hashnode/image/upload/v1644081581359/wGsYKCpnW.png)

### Extracting a part from a String 

Suppose you got a feeling to extract a particular part from a given string, in that case you can use three different ways 


```
var str = "Hello World!";
console.log(str.slice(0, 5));
console.log(str.substring(0, 5));
console.log(str.substr(0, 5));
``` 
see every single method here takes two parameters former is the `start ` and later is the `end ` 

![extract](https://cdn.hashnode.com/res/hashnode/image/upload/v1644081990217/X7R3Ocbr6.png)

### split, trim & concat
often as a developer you will get situations where you need to trim the entered string to save database space in that case you can use the trim method in JavaScript 
which will remove all the extra spaces from the two sides of a String 

```
var str = "   Hello World!   ";
console.log(str.trim());
``` 

![trim](https://cdn.hashnode.com/res/hashnode/image/upload/v1644082463647/zFBSG26YCT.png)


Now you got a feeling   to divide a string form a particular mark, like if I ask you to divide a string where you get an exclamation mark `!` in that case you can use split method which will return you an array 


```
var str = "Hello, World! lol";
console.log(str.split(" "));
console.log(str.split(","));
console.log(str.split("!"));

``` 

![split](https://cdn.hashnode.com/res/hashnode/image/upload/v1644082731961/14gh9OJyd.png)

And now if you want to join two springs like first name and last lame you can use `concat()` or use can do this using a `+`  operator 

```
var firstName = "Dev ";
var lastName = "K";
var fullname = firstName.concat(" " + lastName);
var fullnameTwo = firstName + " " + lastName;
console.log(fullname);
console.log(fullnameTwo);

```

![concat](https://cdn.hashnode.com/res/hashnode/image/upload/v1644082966933/g4_4wJn1A.png)

### play with characters 

 Suppose if I ask you to return a character from a String in that case you can use 
 `chatAt(position)` and this will return you the character at a given position 
 
```
var str = "Hello World!";
console.log(str.charAt(0));
```


![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1644083183208/wrDsWOn9G.png)

And now if you want to get the character code of a particular character in a String in that case you can use `charCodeAt(position)` and this will return you the character code of a character at a given  position 
 
```
var str = "Hello World!";
console.log(str.charCodeAt(0));
```


![character code](https://cdn.hashnode.com/res/hashnode/image/upload/v1644083349918/HqGjODxkw.png)

 see this returns the` 72` which is the character code of `H `

##Conclusion 

So , this was all about the most common JavaScript String methods that we use in our daily life as a developer so If you like my article make sure to share this with your peers and colleagues. Stay Happy , Stay Safe 


## Connect 
 <a href="https://twitter.com/kumarkalyan_">
  <img align="left" width="100px" src="https://cdn.jsdelivr.net/npm/simple-icons@v3/icons/twitter.svg" />