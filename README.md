# Grocery List Workshop

Groceries API is available at
```
https://hrsf-grocery-list.herokuapp.com/api/groceries
```

Note: Heroku may take some time to spin up the application if it's gone to sleep due to inactivity 😴

## Routes
### ```POST /api/groceries```
Inserts a grocery item.
#### Parameters
| Param | Type | Description |
| ------------- | ------------- | ------------- |
| item | string | Name of grocery item |
| quantity | integer | Quantity of grocery item |

#### Response
| Param | Type | Description |
| ------------- | ------------- | ------------- |
| id | integer | ID of grocery item |

#### Status codes
| Status | Description |
| ------------- | ------------- |
| 201 | Item successfully inserted |
| 400 | Bad request |

#### Example usage
```javascript
// jQuery AJAX
$.ajax({
  method: 'POST',
  url: 'https://hrsf-grocery-list.herokuapp.com/api/groceries',
  data: { 
    item: 'apple', 
    quantity: 1 
  },
  success: (data) => console.log(data.id),
  error: console.log
})

// Promises
axios.post('https://hrsf-grocery-list.herokuapp.com/api/groceries', { 
  item: 'apple', 
  quantity: 1 
 })
 .then(({ data }) => console.log(data.id))

// Async/Await
const { data } = await axios.post('https://hrsf-grocery-list.herokuapp.com/api/groceries', {
  item: 'apple',
  quantity: 1
});
console.log(data.id)
```
### ```GET /api/groceries```
Gets all groceries.
#### Status codes
| Status | Description |
| ------------- | ------------- |
| 200 | Query was successful |
| 500 | Internal server error |
#### Example usage
```javascript
// jQuery AJAX
$.ajax({
  method: 'GET',
  url: 'https://hrsf-grocery-list.herokuapp.com/api/groceries',
  success: (data) => console.log(data.id),
  error: console.log
})

// Promises
axios.get('https://hrsf-grocery-list.herokuapp.com/api/groceries')
  .then(({ data }) => console.log(data))

// Async/Await
const { data } = await axios.get('https://hrsf-grocery-list.herokuapp.com/api/groceries')
console.log(data)
```

Example response
```
[
  {
    id: 1,
    item: 'apple',
    quantity: 5
  },
  {
    id: 2,
    item: 'banana',
    quantity: 6
  }
]
```

### ```DELETE /api/groceries/:id```
Deletes a grocery item by ID.


#### Status codes
| Status | Description |
| ------------- | ------------- |
| 200 | Query was successful |
| 500 | Internal server error |
#### Example usage
```javascript
axios.delete('/api/groceries/1')
```
