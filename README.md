# Quering-Arrays-Js
This is a repository showing how to query arrays or perform operations on them in javascript.
# Use operations to query arrays-in Javascript:
## 1.Filtering
Find an item by using `find()`
```
let iceCreamFlavors = ["Chocolate", "Strawberry", "Vanilla", "Pistachio", "Neapolitan", "Mint Chip"];
iceCreamFlavors.find(flavor => flavor === "Chocolate") // "Chocolate"
```
The `find()` operation runs the function that you provided as input for each item. If the operation finds the searched-for element, it returns the element.
If it doesn't find the element, it returns undefined.

## 2.Filter items with a common property by using `filter()`

```let iceCreamFlavors = [
  { name: "Chocolate", type: "Chocolate" }, 
  { name: "Strawberry", type: "fruit"}, 
  { name: "Vanilla", type: "Vanilla"}, 
  { name: "Pistachio", type: "Nuts"}, 
  { name: "Neapolitan", type: "Chocolate"}, 
  { name: "Mint Chip", type: "Chocolate"}
];
iceCreamFlavors.filter(flavor => flavor.type === "Chocolate")
 [{ name: "Chocolate", type: "Chocolate" }, 
   { name: "Neapolitan", type: "Chocolate"},
   { name: "Mint Chip", type: "Chocolate"}]
```

## 3.Check a condition by using `some()`
Imagine a scenario where a person orders icream from icreamFlavours without "nuts".
You'd check your inventory using `some()` method as shown
```
iceCreamFlavors.some(flavor => flavor.type === "Nuts") // true
iceCreamFlavors.filter(flavor => flavor.type !== "Nuts") // returns everything except for Pistachio.
```
## 4.Projections map
Projection is when you are trying to change or modify your aray in javascript.
A scenario where we neeed to introduce price property for each flavor, we'll use the `map()` method as shown:
```
let iceCreamFlavors = [
  { name: "Chocolate", type: "Chocolate" }, 
  { name: "Strawberry", type: "fruit"}, 
  { name: "Vanilla", type: "Vanilla"}, 
  { name: "Pistachio", type: "Nuts"}, 
  { name: "Neapolitan", type: "Chocolate"}, 
  { name: "Mint Chip", type: "Chocolate"}
];
iceCreamFlavors.map(flavor => {
  flavor.price = 1;
  return flavor;
}) // every item now has a new property price: 1
```
## 5.Aggregations
Assuming that our cash machine receipts are stored in one long array, which looks like the code below
```
let sales = [{
 date : '2021-05-01',
 amount: 2
},
{
 date : '2021-05-01',
 amount: 1
}
// and so on...
]
```
You could use a for loop to sum it all together, like this:
```
let sum = 0;
for( let i =0; i< sales.length; i++) {
  sum += sales[i].amount; 
}
```
To reduce this long list I'll introduce the `reduce()` method.The idea of this method is to reduce a long list to a single item,
which could be either an object or a number
To use `reduce()`, you need to provide it with a function that takes two parameters, an accumulated value and the current value in the loop.
Within the function, you should recalculate the accumulated value by using the current value. The second argument to reduce() is the starter value. Because you want to use reduce() in this case to calculate sales, your function should update the accumulated value with the value of what's on the amount property for each item. Your starter value should be 0. With this in mind, here's what the code looks like:
```
sales.reduce((acc, curr) => acc + curr.amount, 0);
```
