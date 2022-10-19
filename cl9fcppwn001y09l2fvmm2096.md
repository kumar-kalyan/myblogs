# Get started with pusher channels

## Introduction 
Pusher  channels helps you to enable next level realime features to your applications like data filtering, realtime location, advanced chart analysis etc. This artcicle will help you  get  a clear idead about pusher channels and its  use case  and  also we will go through a  handson demo with pusher cache channels which is currently in beta.

## Pusher  channels use cases 


- Realtime charts and  graphs for stock market analysis , ad revenue models , user engagemnet analytics,etc.  

- Presence indicators for active users or collaborators  in streams , word docs , code repls etc.
- Realtime location tracking for live location features commonly used  in delivery apps or realtime traffic  analytics. 
- Chat  engament  for group or solo chats, game  rooms , etc.  
- Realtime results for chat poles, surveys , live score, etc .

## Why use pusher ?
- Managed web sockets for hndling millions  of active users , low-latency and automatic  fallbacks 
-  Flexible pub-sub messaging usin event based API  for borowers, mobile devices and IOT apps
- Presence channels, queryable  API and webhooks  for collaboration and channel infos, event driven architechture, etc.
_ And the most important everthing is end to end encrypting with high level security algorithims 

## Pusher channel  overview and types 
Channels are best way to filter data and authorizing  people who have  subscribed to it. In simple words imagine you have joined a discod server and  you subscribed to meme channel so now you will only receive the updates from the meme channels only again let's say you are the moderator of that sever and now only you and other moderators have access to the  moderators only channel and not other memebers in the server.

### channel types


-  `public channels` can be subscribed by anyone 
-  `private channels` which gives you more freedom to controll access and authorization 
- `private encrypted channels` a more advace level of encrytion which even pusher won't  gets  acccess without authorization . Well  you can create some dark channels using this feature.
- `presence channels ` which is basically an extension of  the private channels and it lets you to gets user info and data through subscription
- `cache channels ` currently in beta  and lets your app to remember the last published message  and delivers  when the client gets subscribed 


## Hands on with cache channels
 
- Create  a free account  [here](https://dashboard.pusher.com/channels) and hit on create app


![pusher channels dashboard ](https://cdn.hashnode.com/res/hashnode/image/upload/v1666071539390/CqG_B3nEu.png align="left")

Select a cluster and choose your tech stack 

![app creation pusherjs](https://cdn.hashnode.com/res/hashnode/image/upload/v1666071677004/grjyUzX0U.png align="left")

## Server code
```
const Pusher = require('pusher');
const express = require('express');
const bodyParser = require('body-parser');
const cors = require('cors');

const app = express();

app.use(cors());
app.use(bodyParser.urlencoded({ extended: false }));
app.use(bodyParser.json());
const pusher = new Pusher({
  appId: "1493532",
  key: "5fde9d181c3e5cfaed37",
  secret: "380e1e094262a855e634",
  cluster: "ap2",
  useTLS: true
});
app.set('PORT', process.env.PORT || 5000);

app.post('/score', (req, res) => {
  const score = req.body;
  pusher.trigger('cache-channel-score', 'update', score)
  res.send(score)
})
app.listen(5000, () => {
  console.log('Listning on port 5000')
})
```
make sure to use the `cache-channel-` convention for using a cache channel 

## the Front end code 
```
// import Chat from "./Chat";
import "./App.css";
import { useState, UseEffect, useEffect } from "react";
import axios from "axios";
import Pusher from "pusher-js";
function App() {
  const [score, setScore] = useState(0);
  useEffect(() => {

    console.log(score);
    var pusher = new Pusher("5fde9d181c3e5cfaed37", {
      cluster: "ap2",
    });
    const channel = pusher.subscribe("cache-channel-score");
    channel.bind("update", (data) => {
      axios.post("http://localhost:5000/score", score);
    });
  });

  const handeSubmit = () => {
    setScore(score + 1);
  };

  return (
    <div className="App">
      <h1>{score}</h1>
      <button onClick={handeSubmit}>Update Score </button>
    </div>
  );
}

export default App;

```

![app score ](https://cdn.hashnode.com/res/hashnode/image/upload/v1666166527914/EWau2rLNT.png align="left")

everytime I click on update the score  will be updated and the event will be triggered  and my pusher dashboard is also updated 

![update ](https://cdn.hashnode.com/res/hashnode/image/upload/v1666166608180/BddI-u1XE.png align="left")

![pusher dashboard ](https://cdn.hashnode.com/res/hashnode/image/upload/v1666166652764/T2NnugKR9.png align="left")

## conclusion 
Now I how you guys  guys can get started with pusher cache channels 
