# Quering-Arrays-Js
This is a repository showing how to query arrays or perform operations on them in javascript.
# Use operations to query arrays-in Javascript:
## 1.Filtering
Find an item by using find()
```
let iceCreamFlavors = ["Chocolate", "Strawberry", "Vanilla", "Pistachio", "Neapolitan", "Mint Chip"];
iceCreamFlavors.find(flavor => flavor === "Chocolate") // "Chocolate"
```
The find() operation runs the function that you provided as input for each item. If the operation finds the searched-for element, it returns the element.
If it doesn't find the element, it returns undefined.

## 2.Filter items with a common property by using filter()

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

## 3.Check a condition by using some()
