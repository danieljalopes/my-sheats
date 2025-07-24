# Kotlin Fundamentals


## var and val

Variable with type val become contants one instantiated.
Variable with type var can change types at any time

```kotlin
fun main() {

    val name = "Dilip"
    println(name)

    //name = "Dilip1"

    var age = 34
    println(age)
    age = 35
    println(age)

    val salary = 30000L
    println(salary)

    val course = "Kotlin Spring"
    println("course : $course and the course length is ${course.length}")

    val multiLine = "ABC \n DEF"
    println(multiLine)

    val multiLine1 = """
        ABC
        DEF        
    """.trimIndent()

    println(multiLine1)


}
```

## Types in Kotlin
- In Kotlin there are no distinction between primitives and wrapper types
- All numbers in Kotlin are represented as types
  - Integer types - Byte, Short, Int, Long
  - Floating-Point Types - Float, Double
  - Character Type - char

## Loops and Ranges
```kotlin
fun main() {

    val range = 1..10
    for (i in range){
        println("i : $i")
    }

    val reverseRange = 10 downTo 1
    for (i in reverseRange){
        println("reverseRange : $i")
    }

    for (i in reverseRange step 2){
        println("reverseRange with Skip: $i")
    }
}
```

## while and dowhile loop

```kotlin

fun main() {
    
    exploreWhile()
    exploreDoWhile()
}

fun exploreDoWhile() {
    var i = 0
    do{
        println("Value of i is : $i")
        i++
    }while (i < 5)

}

fun exploreWhile() {
    var x = 1
    while (x < 5){
        println("Value of x is : $x")
        x++
    }

}
```

## break, labels and return

In Kotlin, it is possible to assign a label to a loop and interact with it from an inner loop: break and continue.

To assign a label you use this syntax `label_name@`.

To exit from a loop you can use the `break` keyword. But if you are in an inner loop and meet a condition where you want to terminate the outer loop, you can use `break@loop_name`.

To exit from a function you can use the `return` keyword on any point of the function.
````kotlin

fun main() {

  for(i in 1..5){
    println("i in $i")
    if(i==3) break
  }

  label()

  for(i in 1..5){
    println("i in return $i")
    if(i==3) return
  }

  println("End of the Program!")
}

fun label() {

  loop@ for(i in 1..5){
    println("i in label $i")
    //if(i==3) break@loop
    innerloop@ for(j in 1..5){
      println("j in label $j")
      //if(j==2) break@innerloop
      if(j==2) continue@loop

    }
  }

}
````

## Functions in Kotlin
### Defining and invoking functions

This is a basic syntax of a function
```code
  ┌-> keyword that states this is a function
  |       ┌-> function name
  |       |
 fun printHello(){
                               ┐
     println("Hello World!")   ├-> function body
                               ┘ 
 }
```


```kotlin

fun printName(name: String) {
    println("Name is : $name")
}
                ┌-> named argument
                |              ┌-> return type  
             ┌--┴--┐        ┌--┴─-┐
fun addition(x: Int, y: Int) : Int {
    return x+y
}

// creating a function as an expression
fun addition_approach1(x: Int, y: Int)  = x+y



fun main() {

    val unit = printName("Dilip")
    println("unit is $unit")
    val result = addition(1, 2)
    println("Result is $result")

    val result1 = addition_approach1(1, 2)
    println("Result is $result1")
}
```
A function can have a return type `Unit`, wich means the function returs `void`.

### Default values and named arguments
Kotlin's functions can have named arguments with default values, like Typescript:
- email -  is a string with default value ""
- dob - is of type Localdate with the value given by LocalDate.now()

```kotlin

fun printPersonDetails(
    name: String,
    email: String = "",
    dob: LocalDate = LocalDate.now()
) {

    println("Name is $name and the email is $email and the dob is $dob")

}

// several way to use the printPersonDetails function
fun main() {
    printPersonDetails("Dilip", "abc@gmail.com", LocalDate.parse("2000-01-01"))

    printPersonDetails("Dilip")
    printPersonDetails(name = "Dilip", dob=LocalDate.parse("2000-01-01"))
    printPersonDetails( dob=LocalDate.parse("2000-01-01"), name = "Dilip", email = "abc@gmail.com")
}

```

### Top-level functions & properties

- Functions that do not belong to a class, are Top-level functions
  - In Java, functions can only be part of a class
  - In Java applications, you can find classes that only have static methods
- Kotlin avoids this by using top-level functions in **Kotlin files** 

- Properties that do not belong to a class, are called **top-level properties**


