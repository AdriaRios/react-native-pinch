# Pinch 👌

Callback and promise based HTTP client that supports SSL pinning for React Native.

## Installation

Using NPM:
```
npm install react-native-pinch
```

Using Yarn:
```
yarn add react-native-pinch
```

## Pinch API

### Request Schema

Requests can be made by using the `fetch(url[, config, [callback]])` method of Pinch.

## Example
*Examples are using the ES6 standard*

### Using Promises
```javascript
import pinch from 'react-native-pinch';

pinch.fetch('https://my-api.com/v1/endpoint', {
  method: 'post',
  headers: { customHeader: 'customValue' },
  body: {
    firstName: 'Jake',
    lastName: 'Moxey'
  }, 
  sslPinning: {
    cert: 'my-cool-cert'
  }
})
  .then(res => console.log(`We got your response! Response - ${res}`))
  .catch(err => console.log(`Whoopsy doodle! Error - ${err}`))
```

### Using Callbacks
```javascript
import pinch from 'react-native-pinch';

pinch.fetch('https://my-api.com/v1/endpoint', {
  method: 'post',
  headers: { customHeader: 'customValue' },
  body: {
    firstName: 'Jake',
    lastName: 'Moxey'
  }, 
  sslPinning: {
    cert: 'my-cool-cert'
  }
}, (err, res) => {
  if (err) {
    console.error(`Whoopsy doodle! Error - ${err}`);
    return null;
  }
  console.log(`We got your response! Response - ${res}`);
})
```

## Response Schema
```javascript
{
  bodyString: '',
  
  headers: {},
  
  status: 200,
  
  statusText: 'OK'
}
```
