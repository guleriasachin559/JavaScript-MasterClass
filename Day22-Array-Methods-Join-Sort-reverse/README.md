# Array Method

## Join() Method??
```
-> Join all elements into a single string with a seperator.

Example: 
const path = ["home", "jatin", "sdet"];
console.log(path.join("/"));  // 'home/jatin/sdet'
console.log(path.join(">"));  // 'home>jatin>sdet'

let data = [10,20,30];
let result = data.join('%');
console.log(result); // [10%20%30]

```

## reverse() Method ??  -> it will reverse the original Array.
```
-> Reverse the Array IN PLACE and returns it. Mutates the original.

let data2 = data.reverse() // [30,20,10]
console.log(data2); // [30,20,10]
console.log(data);  // [30,20,10]

```

## I don't want to reverse the original Array -> So we have the 'SPREAD OPERATOR' -> this will create a shalo copy of that Array.
```
-> let names = ["Raj", "Uday", "deepak"];
->let x = [...names].reverse();  // deepak, uday and raj
console.log(x); // ["deepak", "Uday", "deepak"]
console.log(names); // ["Raj", "Uday", "deepak"]


let names = ['Uday', 'deepak', 'jatin'];
let backup = names; //
let backup = [];
for(let index=0; index<names.length; index++){
        backup[index] = names[index];
}
console.log(backup);
console.log(names);

```

## Sort() ?? 
```
-> Sorts in place, Default is LEXICOGRAPHIC, not numeric.
-> LEXICOGRAPHIC : that the data is going to be sort in the diction order.
const nums = [10, 1, 21, 2, 100];

nums.sort();
console.log(nums); // [1, 10, 100, 2, 21]

let numberData = [1,2,10,21,100];
numberData.sort();
console.log(numberData); // [1,10,100,2,21]

// But I want to sort on the copy of an Array
let numberData = [1,2,10,21,100];
let numberDataCopy = [...numberData].sort();
console.log(numberDataCopy);
console.log(numberData);


// But If you want to sort in an Ascending Order.
numberData.sort((a,b) =>a-b) // if the result is negative that mean the sequence is correct. positive no mean then it is going to change the position.
console.log(numberData); //  

// But If you want to sort in an decending Order.
numberData.sort((a,b) =>b-a) // if the result is negative that mean the sequence is correct. positive no mean then it is going to change the position.
console.log(numberData); //  

```