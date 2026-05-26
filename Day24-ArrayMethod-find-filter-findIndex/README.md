# Array Methods

## Filters()
```
-> Returns a NEW array containing only elements where the callback is truthy.

Example:

let data = [10,20,30,50];

let result = data.filter(function (value) {
    return value >= 30;
})
console.log(result); // [30, 50]

// Dry run of above code 
-> Arrays --> Object ---> { "0": 10, "1": 20, "2":30, "3":50, length: 4}





```

## Create the Object Array  -> [{}]
```
let data = [{'name': 'Jatin','id': 101, 'salary':1000}
{'name': 'uday','id': 201, 'salary':2000}
{'name': 'Raj','id': 302, 'salary':500}
{'name': 'rohit','id': 111, 'salary':400}

];

console.log(data);
console.log(data.name);
console.log(data.id);
console.log(data.salary);

let result = data.filter(function(user) {
    return user.salary>=500
})

console.log(result); // 

let result = data.filter(function(user) {
    return user.id===101
})
console.log(result); // 
```

## find()
```
-> Returns the first match, or undefined
-> find stops at the first match, use filter when you want all matches.

let ans = data.find(function (user){
    return user.id === 101
})
console.log(ans);  // [{'name': 'Jatin','id': 101, 'salary':1000}]


let ans = data.find(function (user){
    return user.id === 501
})
console.log(ans); // Undefined
```

## findIndex()
```
let index = data.find(function (user){
    return user.id === 105
})
console.log(index); //  -1



let index = data.find(function (user){
    return user.id === 201
})
console.log(index); //  1
```
