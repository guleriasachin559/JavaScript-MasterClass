# Array Methods

## Reduce()
```


let data = [10,20,30,40];

// I want to do the sum of all the array  - 1st Approach
let sum = 0;
for(let number of data){
    sum = sum+number;
}
console.log(sum);

// 2nd Approach
let result = data.reduce(function (accumulated, number){
    accumulated = accumulated+number;
    return accumulated;

}, 0)// this zero is the default value of accumulated
console.log(result)

// Using the Arrow Operator 
let result = data.reduce((accumulated, number) => {
   return accumulated = accumulated+number}, 0)// this zero is the default value of accumulated
console.log(result)


// Dry run 
1. all the values 10,20,30... are first going to be stored in the number variable.
2. accumulated is the variable which we have created and whole default value is 0.
3. so we have the accumulated = 0 , number = 10 for the first iteration.
4. and then we are going to calculate the accumulated = accumulated+number==> 0+10= 10.
5. now accumulated = 10, number = 20, accumulated = 10+20 =30,
6. accumulated = 30, number = 30, accumulated = 30+30= 60.
7. accumulated = 60, number = 40, accumulated = 60+40= 100.
```


## Concat()
```
->

let a = [10,20,30];
let b = [20,30];
let c = [100];

let ans = a.concat(b,c);
console.log(ans); // [10,20,30,20,30,100];
console.log(a); // [10,20,30]


// Using the spread operator 
console.log([..a,..b,..c]); // [10,20,30,20,30,100]
```