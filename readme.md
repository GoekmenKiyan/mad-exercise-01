# MAD - Exercise 01
## Tasks
* Watch the Kotlin Crashcourse Video in Moodle or complete the tutorials **[Introduction to programming in Kotlin](https://developer.android.com/courses/pathways/android-basics-compose-unit-1-pathway-1)** and **[Kotlin fundamentals](https://developer.android.com/courses/pathways/android-basics-compose-unit-2-pathway-1
)**.
* Answer the questions inside this Readme.md file and push it to your repository.
* Submit your coding solution of the Number Guessing Game inside the repository.
* Submit the link to your repository in Moodle.

## Questions
### Describe how Kotlin handles null safety. What are nullable types and non-null types in Kotlin? (0,5 points)

<span style="color:blue">Provide your answer here! </span>
> Note: you can also use code snippets to illustrate your answer. 

```kotlin 
// example code snippet
val a: String = "value" // non-null type
```

- When do you get a null expection?
- When you have an object, which didn't get initialized or filled with null. Any you try to call a mehtod ojn this object which won't work, because a non existing value can't call a method.

- Kotlin is basically designed, that you can't use/assign null values.
- var a: String = "Hello World!" // Non-null type
- var a = null // Compiler error. NUll has to be explicitly assigned

- Kotlin offers the option, to assign the value null, but it has to be done specifically.
- var b: String? = "Hello World!"
- var b = null // This works, because var b is of the type "nullable"

- Nullable Types:
- These are the types, which can hold "null" as a value.
- To assign a variable with this value, you have to add an "?" to its type (see question before)
- NUllable Typed need somem sort of special handling in order to prevent null pointer exceptions

- Non-null Types:
- These are types, which can't hold "null" as a value.
- you can't simply assign "null" as its value. It has to be a "non-null" value.
- You also can't assign "null" as a value later on, if it has been assigned with a "non-null" value beforehand.

### What are lambda expressions and higher order functions in Kotlin? Why would you store a function inside a variable? (0,5 points)

<span style="color:blue">Provide your answer here!</span>

- Lambda Expressions:
- Lambda expressions are so-called "function literals".
- Function literals are functions, that do not get delcared, but instead passed on as an expresion immediately.
- With lambda expressions, you can create variables that store functions, call these variables like functions, and store them in other variables that you can call like functions.

- Higher Order Functions:
- This type of function is function, that can take functions as parameters, or returns a function.

- Storing Functions:
- Functions are also data types and can therefore be store in variables.
- By storing afunction inside of a variable you have the ability to change the behaviour of a piece of your app at runtime.
- You can nest composbale functions to build layouts.

### Provide a solution for the following number guessing game inside `App.kt`. (3 points)

## Number Guessing Game in Kotlin
The game is a simple number guessing game. The task is to generate a random, max 9-digit, number. The number must **not contain repeating digits**. Valid digits are 1-9.
Ask the user to guess the max 9-digit number. The game is finished when the user guesses the correct digits in the correct order.
In each round, the user gets feedback about the number of correct digits and the number of correct digits in the correct position.
The output should be in the format "n:m", where "n" is the number of digits guessed correctly regardless of their position, 
and "m" is the number of digits guessed correctly at their correct position. Here are some examples:

This example shows the game flow with 4-digits to guess (the default argument)

Generated number: 8576
-	User input: 1234, Output: 0:0
-	User input: 5678, Output: 4:1
-	User input: 5555, Output: 1:1
-	User input: 3586, Output: 3:2
-	User input: 8576, Output: 4:4 -> user wins

Take a look into the provided code structure in `src/main/kotlin/App.kt`. Implement the following methods (lambda expressions):
- _playNumberGame(digitsToGuess: Int = 4)_ (1 point): The main game loop that handles user input and game state. Make use of _generateRandomNonRepeatingNumber_ and _checkUserInputAgainstGeneratedNumber_ here. This function also utilizes a default argument 
- _generateRandomNonRepeatingNumber_ (1 point): A lambda expression that generates a random number with non-repeating digits of a specified length.
- _checkUserInputAgainstGeneratedNumber_ (1 point): A lambda expression that compares the user's input against the generated number and provides feedback.

``CompareResult.kt`` This class is a data structure which helps with bundling the result of the comparison of the user input and the generated number. Look at the toSting() and use it in your output.

Run the project with `./gradlew run` and test your implementation with the provided tests in `src/test/kotlin/AppTest.kt` with `./gradlew test`.

# Project Structure
The project is structured into two main Kotlin files:

**App.kt**: Contains the main game logic and functions.

**AppTest.kt**: Contains unit tests for the various functions in App.kt.

