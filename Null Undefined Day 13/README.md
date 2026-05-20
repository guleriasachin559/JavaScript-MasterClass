# Null Undefined:

## what do you mean by null??
```
- nothing is there in the memory.
- all the non primitive data types they are going to have the default value as null;

let username;  // Js automatically assigns the default value ---> undefined!!   ----> NO VALUE
console.log(username); // undefined


let person = {name:'Jatin'};
console.log(typeOf person); // Object
console.log(person.name);  // Jatin
console.log(person.age);  // if an attribute is not present in the object -> JS gives undefined.



function greet(personName){
    console.log(`Hello.......... ${personName} How are you ??`);
}

greet(`Katrina`); 

greet(); // If you are not passing the value the paramter will take the value as undefined!!
```

## What is the datatype of Undefined??
```
- console.log(typeOf username); //the typeOf Undefined!! is ---> Undefined itself....
```


## Null: 
```
- Undefined!! is a JS way -> that there is no value!!
- JS ------> null -------> No Value -------> Dev Explicity.

let user = null;
console.log(user);   // null

There is a bug in JS -- what is a type of Username
let username;
console.log(typeOf username); // undefined
console.log(typeOf user);     // The type of null ----> Object!!! 
// type of Undefined ---> Undefined.

console.log(user == username);  // Loose equality!!  --> true
console.log(user === username); // strict equality!! -> value+type -----> False 

```

