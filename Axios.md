## What is Axios?
Promise-based HTTP client for the browser.It provides a single API for dealing with XMLHttpRequests. Besides that, it wraps the requests using a polyfill for ES6 new promise syntax.<br><br>
### what axios can do:
- Make XMLHttpRequests from the browser
- Make http requests from node.js
- Supports the Promise API
- Intercept request and response
- Transform request and response data
- Cancel requests
- Automatic transforms for JSON data
### Installing:
1. Using npm:
```
npm install axios
```
2. Using yarn:
```
yarn add axios
```
## How to use Axios with React-native:
1. Install axios and import in the project.
```
import axios from 'axios';
```
2. Make a GET request. You use axios.get(url) with a URL from an API endpoint to get a promise which returns a response object.
```
axios.get(`https:/baseUrl.com/users`)
      .then(res => {
        const persons = res.data;
        this.setState({ persons });
      })
  }
  ```
3.  Make a POST Request. Using POST gives you the same response object with information that you can use inside of a then call.
To complete the POST request, you first capture the user input. Then you add the input along with the POST request, which will give you a response. You can then console.log the response, which should show the user input in the form.<br>
```
axios.post(`https://baseURL.com/users`, { user })
      .then(res => {
        console.log(result);
        console.log(result.data);
      })
      ```
##  Use of async and await
you can use async and await to work with promises.

The await keyword resolves the promise and returns the value. The value can then be assigned to a variable. For Example:
```
handleSubmit = async event => {
  event.preventDefault();

  //
  const response = await API.delete(`users/${this.state.id}`);

  console.log(response);
  console.log(response.data);
};
```
## Base Instance in Axios
It is a good practise to set up a base instance in which we can define a URl and other configuration elements. For Example:
```
import axios from 'axios';

export default axios.create({
  baseURL: `http://itunes.com/`
});
```