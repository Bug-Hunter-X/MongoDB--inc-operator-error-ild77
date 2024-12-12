# MongoDB $inc operator error
This repository demonstrates an incorrect usage of the `$inc` operator in a MongoDB update query. The `$inc` operator is used to increment a numeric field by a specified value. In this example, the value being passed to `$inc` is a string, which causes an error.

## Bug
The bug lies in the following line of code:
```javascript
db.collection('myCollection').updateOne({ _id: 1 }, { $inc: { field: '1' } });
```
The value `'1'` is a string, not a number. The `$inc` operator requires a numeric value.

## Solution
The solution is to pass a number to the `$inc` operator, as shown below:
```javascript
db.collection('myCollection').updateOne({ _id: 1 }, { $inc: { field: 1 } });
```