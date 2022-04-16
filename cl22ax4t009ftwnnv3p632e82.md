## Postman API 101

## What is an API and how does it work?
Application Programming Interface or API is a pipeline to transfer data from client application to server and vice versa in from of `requests` and `responses` or in other words an API acts as a medium of communication between the client and server over a network. Imagine that you went to your favorite restaurant, sitting on the table you call the waiter to order something (say pizza) then the waiter pass your order to the chef. Now there are two possibilities either you get your pizza or the waiter returns with a message that "Sorry sir the pizza you just ordered is currently out of stock please order something else "

Here you are the `client-side application` the `chef` is the server and the `waiter` is an API who is passing your `request` to the server and brings a `response` for you.


![restaurant](https://cdn.hashnode.com/res/hashnode/image/upload/v1650129573276/o0ecygyP7.png)

## Why do we need an API?

Consider a situation where you are building an app like Uber and it will have some basic services like `authentication`, `maps ` for location service `email service ` for sending invoices and newsletters or a `payment service` for accepting payments. Now you can access all these services through API's like `Google maps ` for location services `auth0` for handing the authentication `amazon sqs` for emails and `stripe` for payments. All I want to say is that you can access any software service through` API's ` who don't have to create all these services from scratch. Also using an `API` will be more cost effective than creating a service from scratch. And believe me there is an `API` for everything, all you need to do is implement.

![API](https://cdn.hashnode.com/res/hashnode/image/upload/v1650132830522/LTDB5-52q.png)

## What is Postman and why should we use it?

Postman is an `API` collaborative development tool which makes it easy to create, test, develop and use an `API` through a wonderful `UI `. And it is used by global and top fortune organizations like `PayPal`, `Uber` , etc. So test any API ,  you can share your works or develop an API with you team at the same time using a public or private workplace. You can even write tests or check for security issues, and many more.

![using postman](https://cdn.hashnode.com/res/hashnode/image/upload/v1650133718322/h6hzY4Lnz.png)


## Request and Response in depth 
As I have mentioned earlier, how an `API` works now let's understand about the `request` and `responses ` in depth.  Talking about `request` when you search for something in google you are actually making a request to the google server passing a query. See the image below, you can see the url is `https://www.google.com/search?q=hello` here `https:\\` is the protocol for your request `www.google.com` is the address of the `server` , `\search` is the `endpoint` and `?q=hello` your `query`. 
 
![google search](https://cdn.hashnode.com/res/hashnode/image/upload/v1650136018281/ayNJR5w7n.png)

Don't get confused, I am making it easy for you. Suppose the teacher asked Ram to bring him a book for the library. Here` Asking` is the request protocol `ram` is the host name for the server, `library` is the endpoint and `book ` is the query 

![client.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1650136880202/AV9P6xhrv.png)

### Request methods

![method.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1650137142154/LQwXzkDgk.png)

Now if you have requested something you are definitely going to get a response with a status code. 
Making it simple, your search results will be your response. An API can return a repose in many forms like `Html`, `XML`, `JSON` ,etc. and the most important thing that a response brings is a status code. Status codes helps us to understand the type of our response. Suppose if you send a `GET` request you may get data with a satus code of `200`  means success or may get `404` means not found or if you send  `PUT` or `POST` or `DELETE`  you may get `201` for created `204` no content  or `500` internal server error .

## Start using postman
 [Create a postman account](https://identity.getpostman.com/signup)

### Create a workspace (means creating a project)
Go to Home>Workspaces>Create Workspace 
![create workspace](https://cdn.hashnode.com/res/hashnode/image/upload/v1650138007344/SOjBmTDKR.png)

Name your workspace> Add a summary > select the visibility > hit on `Create Workspace`

![create workspace 2](https://cdn.hashnode.com/res/hashnode/image/upload/v1650138201031/Mo2qgUfo-.png)

### Create a collection 
Collection means group of saved requests. We can create a new collection or can simply `fork` (means copying) a collection to our workspace. To create a new collection in your workspace,  in the left click on`+` > add a name to your collection > click on `:` to add a new request 

![create collection](https://cdn.hashnode.com/res/hashnode/image/upload/v1650138886180/NbuUu0kyo.png)


![add name ](https://cdn.hashnode.com/res/hashnode/image/upload/v1650138931923/PHGBfvri3.png)


![add request](https://cdn.hashnode.com/res/hashnode/image/upload/v1650139005967/IkcWxbOwG.png)

## Fork a collection 
visit a collection > click on `...` > scroll down and select `create a fork`> add a label and select your workspace location > click on `create fork`


![fork1](https://cdn.hashnode.com/res/hashnode/image/upload/v1650139281295/3hAhHyrSu.png)


![fork 2](https://cdn.hashnode.com/res/hashnode/image/upload/v1650139324672/0Uo3GTwS6.png)


![fork created](https://cdn.hashnode.com/res/hashnode/image/upload/v1650139352575/2MRvWsuh0.png)

### `get`

A `get `request is used when we want to get some data from an API.
Suppose If I ask you that what is name?
you will reply me your name (Say, my name is Jhon).
In this example you are the API, my question is the get request and your answer is the response. Now let's perform this task in real.

Open the postman click on the `+` tab to create a new request and then select Get request form the dropdown and paste
this [URL](https://jsonplaceholder.typicode.com/posts) in the `Enter request URL` place holder and then click on the send

%[https://www.youtube.com/watch?v=zPVxg9CeabU]

So, in this above video you can see that on sending a get request using postman, we got a response i.e. data as JSON (JavaScript Object Notation) with a status code 200.


### `post`
 A `post` request is used when we want to send data to a server using an API.
Suppose you have written something on a paper, so in this case what you have written is the data and the pencil you are using is the API and the paper is the server.

Now again in the postman then paste the same URL, this time choose post request from the dropdown, then click on body > raw >json and write some json content in the placeholder and hit the send button 
```{
    "userId": 697,
    "id": 10,
    "title": "post request ",
    "body": "this request is created by kk"
}```

%[https://www.youtube.com/watch?v=JfCW_l2YTKg]
 
### `put`
A `put` request is used when we want to update any data that we have posted earlier to the server, using API. 
Suppose you have written an essay on a paper and now you want to update something in it, in this case   Your pencil will be API and the paper will be the server and you can update anything on the paper 

Now again in the postman then paste the  [URL](https://jsonplaceholder.typicode.com/posts/1), this time choose `put` request from the dropdown, then click on `body` > `raw` >`json `and write some json content in the placeholder this time lets change the content  

```
{
   "title":"This title is updated" 
}
```
%[https://www.youtube.com/watch?v=VBQzvSYUDV0]

We have again got a status 200 which means that output request was successful 

### `delete`
A `delete` request is used to delete some data from a server using an API.
Considering the last example, after writing an essay, now you want to erase it using an eraser, in this case your paper will be the server and eraser will be the API.
Now again in the postman let's send a delete request to this [URL](https://jsonplaceholder.typicode.com/posts/1),

%[https://www.youtube.com/watch?v=Spf80HIsWzk]

 We have again got a status 200 which means that output request was successful 


## Conclusion 
I hope this article will help everyone to acquire adequate knowledge required for getting started with postman. Feel free to share this article with your peers and do hit a ❤️ if you love my article. Feel free to ask any query in the comment section. 

## Connect 
[Twitter ](https://twitter.com/kumarkalyan_)

[Likedin](https://www.linkedin.com/in/kumar009/)