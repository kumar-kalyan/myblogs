## Building a JavaScript Countdown timer in just 10 mins

##  Intro 
In this article I am going to build a beautiful countdown timer just using html , CSS and vanilla JavaScript. 
Our countdown timer will show us the time left till a particular date and time. 

## Making the structure 
We all know that Html is used for structuring an web dev project.
```
<main>
      <h1>Time remaining for the Fest</h1>
      <div class="countdown-container">
        <div class="days-c">
          <p class="big-text" id="days"></p>
          <span>Days</span>
        </div>
        <div class="hours-c">
          <p class="big-text" id="hours"></p>
          <span>Hours</span>
        </div>
        <div class="minutes-c">
          <p class="big-text" id="minutes"></p>
          <span>Minutes</span>
        </div>
        <div class="seconds-c">
          <p class="big-text" id="seconds"></p>
          <span>Seconds</span>
        </div>
      </div>
    </main>
    
``` 
Here I am putting all the micro elements of our countdown timer within a `div` so that we can give our timer a box like shape and a beautiful UI by adding a background image .Again I have separated the `<p>` & `<span>` within a separate `div` with different class names to classify each of the elements i.e. days, hrs , mins and  seconds. Let's  make it easy , consider the `body` element is the whole screen of any device and the `<div class='countdown-timer '></div>` is a box, containing four more boxes i.e. the days, hrs, mins and seconds. See the image below 

![countdown](https://cdn.hashnode.com/res/hashnode/image/upload/v1646656034076/ELtJX9xSZ.png)

## Designing our timer 
Now our structure is ready so let's add some CSS to give our countdown timer a beautiful look.

### `<body>`
I want all my elements to the center of a screen also I want the whole screen to have a background color  and to make these things happen I will use 
```
body
{
  display: flex;
  align-items: center;
  justify-content: center;
  background-color: #eeee;
}
```
### `<main>`
Here I am going to create a beautiful box like structure having a height and with of 25 and 30 rems respectively  with a beautiful background image 
```
main {
  background: url(https://images.unsplash.com/photo-1646429411544-b735d4c77bb7?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=872&q=80);
  height: 25rem;
  width: 30rem;
  color: white;
  border-radius: 10px;
}
```

![main](https://cdn.hashnode.com/res/hashnode/image/upload/v1646657059179/gK_luWXhx.png)

this is how it looks like now 

### fixing the font an size 
```
.countdown-container span {
  margin: 1.5rem;
  font-size: 1rem;
  font-weight: 500;
}

.big-text {
  margin: 1rem;
  font-size: 3rem;
  font-weight: bolder;
  padding: 5px;
}

```

![font](https://cdn.hashnode.com/res/hashnode/image/upload/v1646657711719/QKzoDB7eX.png)

### Aligning the `countdown-container`
```
.countdown-container {
  padding: 1rem;
  margin: 1rem;
  display: flex;
  justify-content: center;
  font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
}

```
![at last ](https://cdn.hashnode.com/res/hashnode/image/upload/v1646658160016/Cwao7KGia.png)

## Adding the values dynamically
Now our styling part is over so let's add the timer values dynamically, and for this I will add some JavaScript to it 

### grabbing the elements 
Now we will grab our micro elements to add values 
```
const days = document.getElementById('days')
const hours = document.getElementById('hours')
const minutes = document.getElementById('minutes')
const seconds = document.getElementById('seconds')

``` 
### defining and calling a function 

As we are building a countdown timer we need a `date` object , also we will use the JavaScript `Math.floor()` for filtering desires values. Now, the first task is to get the remaining time 
 
 ```
 //the final date   
    const fest = new Date(2022, 3, 2);
  // the system date   
  const current = new Date();
  //time remianing   
  const sec = (fest - current) / 1000;
```
we are subtraction of two days will provide us a value in milliseconds so  we diving it with 1000 to get the value in seconds now lets convert it to days , hrs , mins and sec
```
    const d = Math.floor(sec / 3600 / 24);
    const hrs = Math.floor(sec / 3600) % 24;
    const min = Math.floor(sec / 60) % 60;
    const s = Math.floor(sec) % 60
   
```
Now we have our values so let's  add these to our html dynamically using the `innerText` property 

```
    days.innerText = d;
    hours.innerText = hrs;
    minutes.innerText = min;
    seconds.innerText = s;
```
now to change the values every second we will use the `setInterval(handler, milisec)`

### putting it together 
```
const days = document.getElementById('days')
const hours = document.getElementById('hours')
const minutes = document.getElementById('minutes')
const seconds = document.getElementById('seconds')

function goCountown() {
  //the final date   
    const fest = new Date(2022, 3, 2);
  // the system date   
  const current = new Date();
  //time remianing   
  const sec = (fest - current) / 1000;
    const d = Math.floor(sec / 3600 / 24);
    const hrs = Math.floor(sec / 3600) % 24;
    const min = Math.floor(sec / 60) % 60;
    const s = Math.floor(sec) % 60
    days.innerText = d;
    hours.innerText = hrs;
    minutes.innerText = min;
    seconds.innerText = s;
}
goCountown()

setInterval(goCountown, 1000)
```  
## Conclusion 
I this article I have covered some important topics like CSS flex , JavaScript Dates and Math.floor(). I hope this article will help everyone to gain web dev basic knowledge. Feel free to comment , react and share this article if you love this. Thanks for giving you precious time for  reading my article. Stay tuned for the next. Happy coding !

## Connect 
[Twitter](https://twitter.com/kumarkalyan_)
[LinkedIn](https://www.linkedin.com/in/kumar009/)
  