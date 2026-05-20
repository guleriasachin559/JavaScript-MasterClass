# Control Statement
```
- Using which i can decide a certain line of certain peace of code those thing whether to execute or not to execute.

- 1) Conditional statements
                1) If
                2) If-else
                3) if
                   else if
                   else
                4) Switch Case   
  2) Loops
  3) Jumps

 Note:  If the condition is going to be true then only the javascript is going to execute these conditional statements.
```

## Conditional Statements: If Statement
```
- console.log("hello")
console.log("jatin")
console.log("katrina")

if(10>50) //IF this statement is true then only the next line will be executed.
    console.log("Sachinguleria");
    console.log("hello"); // But this is printed

if(10>50){
    console.log("Sachinguleria");
    console.log("hello");
}

if(0){   // Zero is a falsy value
    console.log("Sachinguleria");
    console.log("hello");
}


if(1){   // 1 is a truthy value so it will execute the if block
    console.log("Sachinguleria");
    console.log("hello");
}
```

## Conditional Statement: If- Else statement
```
- If the condition is true ----> Execute the if Block of code else execute the else block of code.

let age = -9;

if(age>=18){
    console.log("The person is an adult");
}
else if(age> 0 && age <18){
    console.log("The person is still a child");
}
else{
    console.log("Invalid age!! age should be greater than 0")
}
```