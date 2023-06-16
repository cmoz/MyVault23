# Pre-problem
Q1 - What is the equivalent of $$2^{-1}, 2^{-2},2^{-3}$$
$$A) \frac{1}{2},\frac{1}{20},\frac{1}{200}$$
$$B) \frac{1}{2},\frac{1}{4},\frac{1}{8}$$
$$C) -2, -4, -8$$
Q2 - What is the correct scientific notation for the value 101? (1.01E2, 0.101E3,101E3)

# Lecture code-along
### Sums of powers of two
Let's encode integers as the addition of powers of two from:$$n=\{3,2,1,0\}$$
Encode the value `6` with a 5-bit number. 

Generalize to allow negative powers of two:$$n=\{3,2,1,0,-1,-2,-3\}$$
Encode the value `6.5`, `6.25`, `6.75`.

## Learn IEEE-754 by discovery
Bring a screen to [IEEE interactive app](https://www.h-schmidt.net/FloatConverter/IEEE754.html)

### Pi encoding
Enter Pi with 50 decimal points: $$\Pi = 3.1415926535897932384626433832795028$$
Enter a common and convenient representation for Pi $$\Pi = 3.14159$$
Compare the errors in encoding both *Pi* values. Now, progressively delete digits from pi until you only have 3 left. 

- Q1 - How is the error behaving with the respect to the number of digits. 

### Counting up
Enter the value 1, 2, 3, 4, 5, 6 successively to observe how the IEEE-754 behaves. Make notes on how you believe the encoding works. 

## Forensic 
### The sign bit

### The exponent

### The mantissa

## Oddball values
Look at 0, Infinity, NaN

## Why must programmers know about encoding error?
A well-known case of a software bug that resulted in serious consequences during the Gulf War in 1991. Here is a summary of the issue:

The Patriot missile system was designed by the United States to intercept incoming missiles. During the Gulf War, a number of Patriot systems were deployed to protect military and civilian areas from Iraqi Scud missile attacks. However, one of these systems failed to intercept a Scud missile in Dharan, Saudi Arabia, resulting in 28 deaths.

The problem was traced back to a flaw in the software that controlled the system. The bug was in the system's clock. The Patriot system represented time as an integer count of tenths of seconds, which it multiplied by 1/10 to get the current time. However, the actual value of 1/10 (0.1) cannot be precisely represented as a binary floating-point number, which the computer used. Instead, the computer had a slight error in the 20th decimal place.

This tiny error, when multiplied by the large number representing the number of tenths of seconds that had passed since the system was last booted, resulted in a significant error. Specifically, the time error after 100 hours of operation, which was the time of the failed intercept, was approximately 0.34 seconds.

This time error was critical because the system used time to calculate the velocity of the incoming Scud and predict its future position. An error of 0.34 seconds over a missile travelling at high speed is enough to put the predicted position off by many hundreds of meters. As a result, the Patriot missile failed to hit the incoming Scud, causing the loss of life.

It's worth noting that the software bug was known before the incident and a patch was available, but it had not been installed on the system in question. This tragic event emphasizes the importance of seemingly minor details in software systems, especially in high-stakes systems such as missile defense.

Evaluate the encoding error for `0.1` using [IEEE interactive app](https://www.h-schmidt.net/FloatConverter/IEEE754.html).

# Post problems
## PP1
Most practical whole number can be expressed without encoding error in a IEEE-754 value. Why? 
1) Because all whole numbers are automatically stored as integers.
2) Because all whole numbers can be expressed as a sum of powers of two.
3) This statement isn't true even for relatively small numbers if they are larger than $$2^{n_{word}}$$ for any value of *n*.

Can you possibly explain using plain language why the lowest positive whole number that cannot be represented with a floating point is: $$2^{n_{mantissa} + 1} + 1$$
_If we shift the radix point beyond the mantissa by one place, it is impossible to place a new 1 to express the value 1 over this._

On a 64-bit system, this value is: `9,007,199,254,740,993`. So, for most applications, all practical whole numbers can be expressed without errors. 
[source](https://stackoverflow.com/questions/3793838/which-is-the-first-integer-that-an-ieee-754-float-is-incapable-of-representing-e)

## PP2
How many rational values can be precisely expressed (with an error of 0) between +Infinity and -Infinity using the C type `float`. [Note on the nature of Infinity](https://brilliant.org/wiki/infinity-is-the-number-at-the-end-of-the-real/#:~:text=Infinity%20is%20a%20%22real%22%20and,on%20the%20real%20number%20line.)

### Answer
There are 32-bit and three of the encodings are excluded: both Infinities and Nan. So: $$2^{32}-3$$
This problem seems harder to solve than it actually is. The purpose of this problem is for students to realize that only a very, very small subset of real numbers (or rational number even) that can be expressed precisely in a 32-bit computer. In the end, it is good enough, and made even better with `double`

# Lab idea
Use the project `encodng_error.c` to plot accumulated error for the values$$k_a=\{0.1,0.11,0.111,0.1111,...,0.11111111\}$$
$$k_b=\{1.1,1.11,1.111,1.1111,...,1.11111111\}$$
So they may gain an insight that the encoding error isn't a function of precision. Maybe try in 

# GPT prompts to generate practice problems

