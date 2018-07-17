---
title: Axios
category: JavaScript libraries
---

### Usage

```bash
npm i axios
```

```javascript
const axios = require('axios')
```

### Get

```javascript
// async await
let response = axios.get('/user?ID=12345')

// promises
axios.get('/user?ID=12345')
  .then(function (response) {
    // handle success
    console.log(response);
  })
  .catch(function (error) {
    // handle error
    console.log(error);
  })
```

### Post

```javascript
// async await
let response =   axios.post('/user', {
    firstName: 'Fred',
    lastName: 'Flintstone'
  })

// promises
axios.post('/user', {
    firstName: 'Fred',
    lastName: 'Flintstone'
  })
  .then(function (response) {
    console.log(response);
  })
  .catch(function (error) {
    console.log(error);
  });
```

