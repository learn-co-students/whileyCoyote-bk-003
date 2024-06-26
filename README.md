# `while`y Coyote

## Objectives

1. Practice using loops.
2. Encounter an infinite loop situation.

##### Advanced

1. Use `arc4random_uniform()` to generate a value within a specified range.

## Introduction

Whiley Coyote is chasing us so, like Road Runner, we need to make sure that we stay one step ahead of him! To help us out, Road Runner is waiting 50 steps away from us with an anvil ready to drop on Whiley Coyote and flatten him into the ground. This means that we need to run 51 steps to ensure we don't get hit by the anvil ourselves. For each step we take, let's imitate Road Runner by printing "Meep! Meep!" to the console.

## Instructions

To track our steps, let's implement a `do-while` loop:

```objc
do {
    statements
} while (condition)
```

1. Open the `whileyCoyote.xcodeproj` file and navigate to the `application:didFinishLaunchingWithOptions:` method in the `FISAppDelegate.m` implementation file.
2. Write a `do-while` loop that `NSLog()`s "Meep! Meep!". Write `YES` inside the conditional `()`. 
  * Hit run (`⌘``R`) and watch and your console printouts. You've just created an infinite loop! Hit stop (`⌘``.`).
3. Declare an `NSUInteger` variable called `steps` before the `do-while` loop in order to count the steps. Start `steps` at `0` ("zero") and set the loop's conditional to pass if `steps` is less than or equal to `50`.
  * Hit run and watch your console printouts. It's an infinite loop again! That's because we're not incrementing our counter inside the loop so the conditional will keep passing forever.
4. Insert `steps++;` into the loop's implementation body beneath the `NSLog()`. This will add one to `steps` each time the loop runs.
  * Hit run. You should see a total of 51 `Meep! Meep!`s. **Hint:** *Instead of counting the* `Meep! Meep!`*s, think about how you can print the value of the* `steps` *integer along with each* `Meep! Meep!`.
5. Whiley Coyote gets frustrated easily and pulls out a sign that reads "YOU'RE CUCKOO!" every ten steps or so.
  * At the beginning of the loop, add an `if` statement that checks whether `steps` is an even factor of `10` and also greater than `0`. **Hint:** *Use the modulus operator* `%` *to calculate the remainder of dividing* `steps` *by ten.*
  * Insert an `NSLog()` that prints `YOU'RE CUCKOO!` into the `if` statement.
  * Hit run. You should see `YOU'RE CUCKOO!` mixed into the `Meep! Meep!`s in your console output.
6. Immediately after this `if` statement, add a new `if` statement that checks when `steps` equals `50`. Insert an `NSLog()` that prints a string describing the sound of the anvil falling on Whiley Coyote (e.g. `@"SMASH!"`).
  * Hit run. Your console output should end with:

```
...
Meep! Meep!
Meep! Meep!
YOU'RE CUCKOO!
SMASH!
Meep! Meep!
```

## Advanced

Whiley Coyote is actually pretty clever despite constantly getting outsmarted by Road Runner. Now that he's expecting the anvil to drop on him after 50 steps, Road Runner says that we need to randomize our plan to drop the anvil.
	
1. Define a new `NSUInteger anvil` variable before the loop and set it equal to `arc4random_uniform(25) + 26`. This generates a random integer from `26` to `50`. Replace the two occurrences of `50` in the conditionals with the `anvil` variable.
  * Hit run a few different times. Notice that the Road Runner drops the anvil after a different number of steps each time.
2. Play around with the range of the `anvil` variable by changing the integers that affect the usage of `arc4random_uniform()`.

<a href='https://learn.co/lessons/whileyCoyote' data-visibility='hidden'>View this lesson on Learn.co</a>
