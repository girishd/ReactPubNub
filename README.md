# ReactPubNub

This is a quick example of getting PubNub running in a React Native project.

## Step 1: Initialize React Native Project

`react-native init ReactPubNub`

[![1.InitReact.jpg](https://s12.postimg.org/4vit9du65/1_Init_React.jpg)](https://postimg.org/image/lw1pi277d/)

## Step 2: Edit package.json to include PubNub dependencies

[![2.PackageJson.jpg](https://s17.postimg.org/p590ink4v/2_Package_Json.jpg)](https://postimg.org/image/nq7ftxj1n/)

## Step 3: Fetch PubNub SDK

`npm install`

## Step 4: Import PubNub and intialize PubNub object

Modify `index.android.js` and `index.ios.js`

```javascript
import React, { Component } from 'react';
import {
  AppRegistry,
  StyleSheet,
  Text,
  View
} from 'react-native';

import PubNub from 'pubnub'

class ReactPubNub extends Component {
  render() {
    return (
    );
  }
}

const pubnub = new PubNub({
    subscribeKey: "demo",
    publishKey: "demo",
    ssl: true
})

pubnub.addListener({
    message: function(message) {
        console.log(message);
        // handle message
    }
})

pubnub.subscribe({ 
    channels: ['girish'] 
});


AppRegistry.registerComponent('ReactPubNub', () => ReactPubNub);

```

## Step 5: Run logger to view subscribed messages received by the device
`react-native log-android`

[![3.AndroidLog.jpg](https://s13.postimg.org/6wvx1e43b/3_Android_Log.jpg)](https://postimg.org/image/7mepdr4mr/)

## Step 6: Profit
[![4.Profit.jpg] (http://i0.kym-cdn.com/photos/images/newsfeed/000/495/314/e2b.png)] 
