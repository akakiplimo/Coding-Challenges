---
title: Prime Number Algorithm Mastery - First Principles Learning Plan
slug: Learn/JavaScript/Prime_Numbers_Mastery
page-type: guide
status: experimental
---

{{LearnSidebar}}

This guide provides a structured 7-day learning plan to master prime number detection algorithms from first principles, focusing on the `isPrime()` function and finding primes within intervals.

## Prerequisites

Before starting this guide, you should be familiar with:

- [JavaScript basics](/en-US/docs/Learn/JavaScript/First_steps)
- [Functions](/en-US/docs/Web/JavaScript/Guide/Functions)
- [Loops and iteration](/en-US/docs/Web/JavaScript/Guide/Loops_and_iteration)
- [Arrays](/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array)

## Learning objectives

By the end of this guide, you will be able to:

- Implement a prime number checker from memory
- Find all prime numbers within a given interval
- Understand and apply optimization techniques (√n, even number skipping)
- Handle edge cases in mathematical algorithms
- Trace algorithm execution manually

---

## Core Concepts (First Principles)

### What is a prime number?

A **prime number** is a natural number greater than 1 that has exactly two divisors: 1 and itself.

**Key insights:**

- 1 is NOT prime (only one divisor)
- 2 is the ONLY even prime
- All other primes are odd
- If a number has a divisor, it has one ≤ √n

### Mathematical foundation

**Divisibility**
: If `a % b === 0`, then b divides a evenly.

**Square root optimization**
: If n = a × b and a ≤ b, then a ≤ √n. This means we only need to check divisors up to the square root.

**Why check up to √n?**
: Any factor larger than √n must have a corresponding factor smaller than √n.

### JavaScript fundamentals required

- {{jsxref("Statements/function", "Functions")}} and {{jsxref("Statements/return", "return")}} statements
- {{jsxref("Statements/for", "for")}} loops
- {{jsxref("Statements/if...else", "Conditionals")}}
- {{jsxref("Array")}} methods ({{jsxref("Array/push", "push()")}})
- {{jsxref("Math.sqrt()")}}
- {{jsxref("Operators/Remainder", "Modulo operator")}} (`%`)

---

## 7-Day Learning Schedule

### Day 1: Understanding Prime Numbers (Theory)

**Duration:** 2 hours

#### Morning session (30 min) - Study

1. Write down the definition of prime numbers in your own words
2. List all primes from 1-50 by hand
3. Explain why we only check up to √n (draw it out)

#### Afternoon session (45 min) - Exercises

**Exercise 1.1: Check if prime (by hand, no code)**

```plain
Is 17 prime? Check divisors: 2, 3, 4 (up to √17 ≈ 4.12)
Is 21 prime? Check divisors: 2, 3
Is 29 prime? Check divisors: 2, 3, 4, 5 (up to √29 ≈ 5.38)
```

**Exercise 1.2: Pattern recognition**

Answer these questions:

- Why can we skip even numbers after checking 2?
- Why can we increment by 2 (`i += 2`) when checking divisors?
- What's the smallest prime? What's special about it?

#### Evening session (30 min) - Code

Write pseudocode (not real code) for `isPrime()`:

```plain
function isPrime(n):
    if n < 2: return false
    if n == 2: return true
    if n is even: return false
    for each odd number from 3 to sqrt(n):
        if n divides evenly by this number:
            return false
    return true
```

---

### Day 2: Building isPrime from Scratch

**Duration:** 2 hours

#### Morning session (45 min) - Exercises

**Exercise 2.1: Implement isPrime WITHOUT looking at reference**

Close all tabs. Write from memory:

```js
function isPrime(num) {
  // Your implementation here
}

// Test cases - all must pass
console.log(isPrime(1));   // false
console.log(isPrime(2));   // true
console.log(isPrime(3));   // true
console.log(isPrime(4));   // false
console.log(isPrime(17));  // true
console.log(isPrime(20));  // false
console.log(isPrime(97));  // true
```

**Exercise 2.2: Debug broken implementations**

Fix these intentionally broken versions:

```js
// Version A - What's wrong?
function isPrime(num) {
  if (num < 2) return false;
  for (let i = 2; i < num; i++) {
    if (num % i === 0) return false;
  }
  return true;
}

// Version B - What's wrong?
function isPrime(num) {
  if (num <= 2) return false;
  for (let i = 2; i <= Math.sqrt(num); i++) {
    if (num % i === 0) return false;
  }
  return true;
}

// Version C - What's wrong?
function isPrime(num) {
  if (num < 2) return false;
  if (num === 2) return true;
  for (let i = 3; i <= Math.sqrt(num); i++) {
    if (num % i === 0) return false;
  }
  return true;
}
```

> **Note:** Version A is inefficient (checks all numbers), Version B incorrectly rejects 2, Version C skips checking divisibility by 2.

#### Afternoon session (45 min)

**Exercise 2.3: Trace execution by hand**

For `isPrime(25)`, write down every iteration:

```plain
num = 25
25 < 2? No
25 === 2? No
25 % 2 === 0? No
i = 3: 25 % 3 === 0? No (25/3 = 8.33...)
i = 5: 25 % 5 === 0? Yes! → return false
```

Do this for: 13, 16, 29

#### Evening session (30 min)

**Exercise 2.4: Rewrite isPrime 3 times from memory**

Delete your code and rewrite it completely from scratch 3 times.
Time yourself. **Goal:** under 2 minutes each time.

---

### Day 3: Arrays and Iteration Fundamentals

**Duration:** 2.5 hours

#### Morning session (45 min) - Exercises

**Exercise 3.1: Basic array operations**

```js
// Create empty array and add elements
const nums = [];
for (let i = 1; i <= 10; i++) {
  nums.push(i);
}

// Filter even numbers
const evens = [];
for (let i = 0; i < nums.length; i++) {
  if (nums[i] % 2 === 0) {
    evens.push(nums[i]);
  }
}
```

**Exercise 3.2: Range iteration patterns**

Write functions without looking:

```js
// Generate array of numbers from start to end
function range(start, end) {
  // Your code
}

// Count how many numbers from start to end are divisible by 3
function countDivisibleBy3(start, end) {
  // Your code
}
```

#### Afternoon session (1 hour)

**Exercise 3.3: Combine isPrime with arrays**

Without looking at reference:

```js
// 1. Create array of first 10 prime numbers
function firstNPrimes(n) {
  // Your code
}

// 2. Count primes between 1 and 100
function countPrimes(max) {
  // Your code
}

// 3. Find largest prime less than n
function largestPrimeBefore(n) {
  // Your code
}
```

---

### Day 4: Building findPrimesInInterval

**Duration:** 2 hours

#### Morning session (30 min) - Study

Break down the problem:

1. Need to check every number from start to end
2. For each number, check if it's prime
3. If prime, add to results array
4. Return results array

#### Morning continued (45 min)

**Exercise 4.1: Write findPrimesInInterval WITHOUT reference**

```js
function findPrimesInInterval(start, end) {
  // Your implementation
}

// Test cases
console.log(findPrimesInInterval(1, 10));    // [2, 3, 5, 7]
console.log(findPrimesInInterval(10, 20));   // [11, 13, 17, 19]
console.log(findPrimesInInterval(50, 60));   // [53, 59]
console.log(findPrimesInInterval(1, 1));     // []
console.log(findPrimesInInterval(2, 2));     // [2]
```

#### Afternoon session (1 hour)

**Exercise 4.2: Variations practice**

Implement these variations from memory:

```js
// Return count instead of array
function countPrimesInInterval(start, end) {
  // Your code
}

// Return sum of all primes in interval
function sumPrimesInInterval(start, end) {
  // Your code
}

// Find all prime pairs (twin primes) in interval
// Twin primes differ by 2: (3,5), (11,13), (17,19)
