# Client-Server Communication Discussion Questions

## Objectives

* Explain what the `fetch` function is used for
* Use `fetch` to retrieve data from a server

## Exercise

Each of the following code samples accesses an API with CityBike data from
data.gov. Take a look at each sample and answer the associated question(s).

To run the code samples yourself, open the browser DevTools and copy/paste the
code into the console.

### Example 1

Why does the following code snippet result in the error shown below? How can we
fix it?

```javascript
const url = "https://data.cityofnewyork.us/api/views/p94q-8hxh"
fetch(url).then(console.log)
/*
Refused to connect to 'https://data.cityofnewyork.us/api/views/p94q-8hxh' because it violates the document's Content Security Policy.
Promise {<rejected>: TypeError: Failed to fetch
    at <anonymous>:2:1}
Uncaught (in promise) TypeError: Failed to fetch
    at <anonymous>:2:1
*/
```

### Example 2

What will be logged by the following code? Why?

```javascript
const url = "https://data.cityofnewyork.us/api/views/p94q-8hxh"
const data = fetch(url)

console.log(data)
```

### Example 3

What will be logged by the following code? Describe in your own words what's
happening in each line of code.

```javascript
const url = "https://data.cityofnewyork.us/api/views/p94q-8hxh"
fetch(url)
  .then(function(response){
    return response.json()
  }).then(console.log)
```

### Bonus

How would you implement a function called `getJSON` so that the below code works
as outlined?

```javascript
const url = "https://data.cityofnewyork.us/api/views/p94q-8hxh" // CityBike Data from data.gov

getJSON(url).then(console.log)
// {id: "p94q-8hxh", name: "Citi Bike Live Station Feed (JSON)", attribution: "CitiBike", attributionLink: "http://citibikenyc.com/stations/json", averageRating: 0, …}``
```
