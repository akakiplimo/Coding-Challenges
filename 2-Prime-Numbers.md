# Prime Number Algorithm Mastery - 7-Day Learning Plan

## Core Concepts You Must Understand (First Principles)

### 1. **What is a Prime Number?**

A number greater than 1 that has exactly two divisors: 1 and itself.

**Key insights:**

- 1 is NOT prime (only one divisor)
- 2 is the ONLY even prime
- All other primes are odd
- If a number has a divisor, it has one ≤ √n

### 2. **Mathematical Foundation**

- **Divisibility**: If `a % b === 0`, then b divides a
- **Square root optimization**: If n = a × b and a ≤ b, then a ≤ √n
- **Why check up to √n?** Any factor larger than √n has a corresponding factor smaller than √n

### 3. **JavaScript Fundamentals Needed**

- Functions and return statements
- Loops (for, while)
- Conditionals (if/else)
- Arrays (push, iteration)
- Math.sqrt()
- Modulo operator (%)

---

## 7-Day Mastery Schedule

### **Day 1: Understanding Prime Numbers & Mathematical Foundation**

**Morning Session (45 min) - Pure Theory:**

1. Write down the definition of prime numbers in your own words
2. List all primes from 1-50 by hand (no calculator)
3. Draw a diagram explaining why we only check up to √n

**Exercise 1.1:** Manual prime checking (by hand, no code)

```
Is 17 prime? Check divisors: 2, 3, 4 (up to √17 ≈ 4.12)
  17 ÷ 2 = 8.5 (not divisible)
  17 ÷ 3 = 5.67 (not divisible)
  17 ÷ 4 = 4.25 (not divisible)
  Therefore: 17 is PRIME

Is 21 prime? Check divisors: 2, 3, 4 (up to √21 ≈ 4.58)
  21 ÷ 2 = 10.5 (not divisible)
  21 ÷ 3 = 7 (divisible!)
  Therefore: 21 is NOT PRIME

Is 29 prime? Check divisors: 2, 3, 4, 5 (up to √29 ≈ 5.38)
Is 91 prime? Check divisors up to √91 ≈ 9.54
```

**Afternoon Session (60 min) - Pattern Recognition:**

**Exercise 1.2:** Understanding optimizations
Answer these questions in writing:

- Why can we skip even numbers after checking 2?
- Why can we increment by 2 (i += 2) when checking divisors?
- What's the smallest prime? What's special about it?
- Can negative numbers be prime? Why or why not?
- Is 0 prime? Is 1 prime? Why?

**Exercise 1.3:** Prime number patterns

```
Find patterns in these prime sequences:
2, 3, 5, 7, 11, 13, 17, 19, 23, 29, 31, 37, 41, 43, 47

Questions:
- How many primes are even?
- What's the pattern in the gaps between consecutive primes?
- Are there any primes that end in 5 (other than 5)?
- Why do primes get less frequent as numbers get larger?
```

**Evening Session (45 min) - Pseudocode:**

**Exercise 1.4:** Write pseudocode (not real code) for isPrime

```
function isPrime(n):
    // Write step-by-step logic in plain English
    // Example:
    // Step 1: if n is less than 2, return false
    // Step 2: if n equals 2, return true
    // Step 3: ...
```

**Exercise 1.5:** Trace execution manually
For isPrime(25), write down EVERY step:

```
Input: n = 25
Step 1: Is 25 < 2? No, continue
Step 2: Is 25 == 2? No, continue
Step 3: Is 25 even (25 % 2 == 0)? No, continue
Step 4: Check divisors from 3 to √25 = 5
  Check 3: 25 % 3 == 0? 25/3 = 8.33... No
  Check 5: 25 % 5 == 0? 25/5 = 5. Yes!
Step 5: Return false (not prime)
```

Do this manual trace for: 13, 16, 49, 53

---

### **Day 2: JavaScript Fundamentals & Basic Loops**

**Morning Session (60 min) - JavaScript Basics:**

**Exercise 2.1:** Modulo operator practice

```javascript
// Write a program to test your understanding of %
console.log(10 % 2); // What will this print?
console.log(10 % 3); // What will this print?
console.log(17 % 5); // What will this print?

// Write a function that checks if a number is even
function isEven(num) {
  // Your code
}

// Write a function that checks if a number is divisible by 3
function isDivisibleBy3(num) {
  // Your code
}

// Write a function that checks if a number is divisible by another number
function isDivisibleBy(num, divisor) {
  // Your code
}

// Test all your functions
console.log(isEven(10)); // true
console.log(isEven(7)); // false
console.log(isDivisibleBy3(9)); // true
console.log(isDivisibleBy3(10)); // false
console.log(isDivisibleBy(20, 4)); // true
console.log(isDivisibleBy(20, 3)); // false
```

**Exercise 2.2:** Loop fundamentals

```javascript
// Print numbers 1 to 10
for (let i = 1; i <= 10; i++) {
  console.log(i);
}

// Print only even numbers from 1 to 20
// Your code here

// Print only odd numbers from 1 to 20
// Your code here

// Print numbers from 10 down to 1
// Your code here

// Print multiples of 3 from 3 to 30
// Your code here
```

**Afternoon Session (60 min) - Math.sqrt() and Loop Optimization:**

**Exercise 2.3:** Understanding Math.sqrt()

```javascript
// Write and test these:
console.log(Math.sqrt(4)); // 2
console.log(Math.sqrt(9)); // 3
console.log(Math.sqrt(16)); // 4
console.log(Math.sqrt(25)); // 5
console.log(Math.sqrt(17)); // 4.123...
console.log(Math.sqrt(100)); // 10

// Write a function that checks if a number is a perfect square
function isPerfectSquare(num) {
  // Your code
}

// Test it
console.log(isPerfectSquare(16)); // true
console.log(isPerfectSquare(17)); // false
console.log(isPerfectSquare(25)); // true
```

**Exercise 2.4:** Loop up to square root

```javascript
// Print all divisors of 36
// (Numbers that divide evenly into 36)
const n = 36;
for (let i = 1; i <= n; i++) {
  if (n % i === 0) {
    console.log(i);
  }
}

// Now print divisors only up to √36
// Compare: how many iterations did you save?

// Do the same for n = 100
// How many iterations did you save?
```

**Evening Session (45 min) - Combining Concepts:**

**Exercise 2.5:** Check divisibility up to square root

```javascript
// Write a function that checks if n has any divisors
// between 2 and √n (not including 1 and n itself)
function hasDivisors(n) {
  // Your code here
  // Return true if it has divisors, false otherwise
}

// Test cases
console.log(hasDivisors(10)); // true (divisors: 2, 5)
console.log(hasDivisors(13)); // false (prime)
console.log(hasDivisors(15)); // true (divisors: 3, 5)
console.log(hasDivisors(17)); // false (prime)
```

---

### **Day 3: Building isPrime Function**

**Morning Session (60 min) - First Implementation:**

**Exercise 3.1:** Implement isPrime WITHOUT looking at reference
Close all tabs. Write from memory based on what you learned:

```javascript
function isPrime(num) {
  // Your implementation here
  // Remember:
  // 1. Handle numbers less than 2
  // 2. Handle 2 specially
  // 3. Check if even
  // 4. Loop from 3 to sqrt(num)
}

// Test cases - all must pass
console.log(isPrime(1)); // false
console.log(isPrime(2)); // true
console.log(isPrime(3)); // true
console.log(isPrime(4)); // false
console.log(isPrime(5)); // true
console.log(isPrime(9)); // false
console.log(isPrime(17)); // true
console.log(isPrime(20)); // false
console.log(isPrime(97)); // true
console.log(isPrime(100)); // false
```

**Exercise 3.2:** Step-by-step debugging
If your isPrime doesn't work, debug it step by step:

```javascript
function isPrime(num) {
  console.log('Testing:', num);

  if (num < 2) {
    console.log('Less than 2, returning false');
    return false;
  }

  if (num === 2) {
    console.log('Equals 2, returning true');
    return true;
  }

  if (num % 2 === 0) {
    console.log('Even number, returning false');
    return false;
  }

  console.log('Checking divisors up to', Math.sqrt(num));
  for (let i = 3; i <= Math.sqrt(num); i += 2) {
    console.log('Checking divisor:', i);
    if (num % i === 0) {
      console.log('Found divisor!', i, 'returning false');
      return false;
    }
  }

  console.log('No divisors found, returning true');
  return true;
}

// Test with debugging
isPrime(15);
```

**Afternoon Session (75 min) - Debug Broken Implementations:**

**Exercise 3.3:** Fix these intentionally broken versions

```javascript
// Version A - What's wrong? Fix it.
function isPrimeA(num) {
  if (num < 2) return false;
  for (let i = 2; i < num; i++) {
    if (num % i === 0) return false;
  }
  return true;
}
// Hint: This works but is very slow. Why? How can you optimize?

// Version B - What's wrong? Fix it.
function isPrimeB(num) {
  if (num <= 2) return false;
  for (let i = 2; i <= Math.sqrt(num); i++) {
    if (num % i === 0) return false;
  }
  return true;
}
// Hint: Test with isPrimeB(2). What happens?

// Version C - What's wrong? Fix it.
function isPrimeC(num) {
  if (num < 2) return false;
  if (num === 2) return true;
  for (let i = 3; i <= Math.sqrt(num); i++) {
    if (num % i === 0) return false;
  }
  return true;
}
// Hint: Test with isPrimeC(4) or isPrimeC(6). What happens?

// Version D - What's wrong? Fix it.
function isPrimeD(num) {
  if (num < 2) return false;
  if (num === 2) return true;
  if (num % 2 === 0) return false;
  for (let i = 3; i <= num; i += 2) {
    if (num % i === 0) return false;
  }
  return true;
}
// Hint: This is correct but slow. How can you optimize?
```

**Exercise 3.4:** Trace execution by hand
For `isPrime(25)`, write down every iteration:

```
Input: num = 25
Line 1: 25 < 2? No
Line 2: 25 === 2? No
Line 3: 25 % 2 === 0? No (25 is odd)
Line 4: Loop from i=3 to i<=5 (sqrt(25)=5), step by 2
  Iteration 1: i = 3
    25 % 3 === 0? 25/3 = 8.33... No
  Iteration 2: i = 5
    25 % 5 === 0? 25/5 = 5. Yes!
    Return false
```

Do this manual trace for: 13, 16, 29, 49

**Evening Session (45 min) - Memory Practice:**

**Exercise 3.5:** Rewrite isPrime 5 times from memory

1. Delete your code completely
2. Rewrite it from scratch
3. Test with all test cases
4. Repeat 5 times

Time yourself each time. Goal: under 3 minutes each.

Attempt 1: **\_** minutes
Attempt 2: **\_** minutes  
Attempt 3: **\_** minutes
Attempt 4: **\_** minutes
Attempt 5: **\_** minutes

---

### **Day 4: Arrays and Iteration Mastery**

**Morning Session (60 min) - Array Fundamentals:**

**Exercise 4.1:** Basic array operations

```javascript
// Create empty array and add elements
const nums = [];
for (let i = 1; i <= 10; i++) {
  nums.push(i);
}
console.log(nums); // [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]

// Filter even numbers into new array
const evens = [];
for (let i = 0; i < nums.length; i++) {
  if (nums[i] % 2 === 0) {
    evens.push(nums[i]);
  }
}
console.log(evens); // [2, 4, 6, 8, 10]

// Now you try: filter odd numbers
const odds = [];
// Your code here

// Filter numbers divisible by 3
const divisibleBy3 = [];
// Your code here

// Filter numbers greater than 5
const greaterThan5 = [];
// Your code here
```

**Exercise 4.2:** Range generation

```javascript
// Write a function that creates an array from start to end
function range(start, end) {
  const result = [];
  // Your code here
  return result;
}

// Test it
console.log(range(1, 5)); // [1, 2, 3, 4, 5]
console.log(range(10, 15)); // [10, 11, 12, 13, 14, 15]
console.log(range(0, 3)); // [0, 1, 2, 3]
```

**Afternoon Session (75 min) - Combining isPrime with Arrays:**

**Exercise 4.3:** Filter primes from an array

```javascript
// Given an array of numbers, return only the primes
function filterPrimes(numbers) {
  const primes = [];
  // Your code here using isPrime
  return primes;
}

// Test it
console.log(filterPrimes([1, 2, 3, 4, 5, 6, 7, 8, 9, 10]));
// Should return [2, 3, 5, 7]

console.log(filterPrimes([10, 11, 12, 13, 14, 15, 16, 17]));
// Should return [11, 13, 17]
```

**Exercise 4.4:** Count primes in a range

```javascript
// Count how many primes are between 1 and max
function countPrimes(max) {
  let count = 0;
  // Your code here
  return count;
}

// Test it
console.log(countPrimes(10)); // 4 (primes: 2,3,5,7)
console.log(countPrimes(20)); // 8 (primes: 2,3,5,7,11,13,17,19)
console.log(countPrimes(100)); // 25
```

**Exercise 4.5:** First N primes

```javascript
// Create an array of the first n prime numbers
function firstNPrimes(n) {
  const primes = [];
  let num = 2;
  // Your code here
  // Hint: keep checking numbers until you have n primes
  return primes;
}

// Test it
console.log(firstNPrimes(5)); // [2, 3, 5, 7, 11]
console.log(firstNPrimes(10)); // [2, 3, 5, 7, 11, 13, 17, 19, 23, 29]
```

**Evening Session (45 min) - More Array Challenges:**

**Exercise 4.6:** Additional challenges

```javascript
// Find the largest prime less than n
function largestPrimeBefore(n) {
  // Your code here
  // Start from n-1 and go down
}

console.log(largestPrimeBefore(20)); // 19
console.log(largestPrimeBefore(100)); // 97

// Sum of all primes up to n
function sumOfPrimesUpTo(n) {
  // Your code here
}

console.log(sumOfPrimesUpTo(10)); // 2+3+5+7 = 17
console.log(sumOfPrimesUpTo(20)); // 2+3+5+7+11+13+17+19 = 77

// Find all twin primes up to n
// Twin primes are pairs that differ by 2: (3,5), (5,7), (11,13)
function twinPrimesUpTo(n) {
  // Your code here
  // Return array of arrays: [[3,5], [5,7], ...]
}

console.log(twinPrimesUpTo(20));
// [[3,5], [5,7], [11,13], [17,19]]
```

---

### **Day 5: Building findPrimesInInterval**

**Morning Session (60 min) - Understanding the Problem:**

**Exercise 5.1:** Break down the problem
Write in your own words:

1. What does "interval" mean? (range from start to end)
2. What do we need to check? (every number in the range)
3. What do we need to return? (array of primes found)
4. What function helps us? (isPrime)

Pseudocode:

```
function findPrimesInInterval(start, end):
    create empty array called primes
    for each number from start to end:
        if number is prime:
            add it to primes array
    return primes array
```

**Exercise 5.2:** Implement findPrimesInInterval WITHOUT reference

```javascript
function findPrimesInInterval(start, end) {
  // Your implementation
}

// Test cases
console.log(findPrimesInInterval(1, 10));
// [2, 3, 5, 7]

console.log(findPrimesInInterval(10, 20));
// [11, 13, 17, 19]

console.log(findPrimesInInterval(50, 60));
// [53, 59]

console.log(findPrimesInInterval(1, 1));
// []

console.log(findPrimesInInterval(2, 2));
// [2]

console.log(findPrimesInInterval(20, 30));
// [23, 29]
```

**Afternoon Session (75 min) - Edge Cases and Variations:**

**Exercise 5.3:** Handle edge cases

```javascript
// What should happen in these cases?
// Implement and test:

console.log(findPrimesInInterval(5, 2));
// start > end - should return empty array? or swap them?

console.log(findPrimesInInterval(-5, 5));
// negative start - should still work

console.log(findPrimesInInterval(0, 0));
// single number (0) - should return []

console.log(findPrimesInInterval(100, 100));
// single number (100) - should return []

console.log(findPrimesInInterval(97, 97));
// single prime - should return [97]
```

**Exercise 5.4:** Variations to practice

```javascript
// Return count instead of array
function countPrimesInInterval(start, end) {
  // Your code
}

console.log(countPrimesInInterval(1, 10)); // 4
console.log(countPrimesInInterval(1, 100)); // 25

// Return sum of all primes in interval
function sumPrimesInInterval(start, end) {
  // Your code
}

console.log(sumPrimesInInterval(1, 10)); // 2+3+5+7 = 17
console.log(sumPrimesInInterval(1, 20)); // 77

// Find all prime pairs (twin primes) in interval
function twinPrimesInInterval(start, end) {
  // Your code - returns array of pairs
  // Twin primes differ by 2: (3,5), (11,13), (17,19)
}

console.log(twinPrimesInInterval(1, 20));
// [[3,5], [5,7], [11,13], [17,19]]

// Return primes in descending order
function primesInIntervalDescending(start, end) {
  // Your code
}

console.log(primesInIntervalDescending(1, 20));
// [19, 17, 13, 11, 7, 5, 3, 2]
```

**Evening Session (45 min) - Integration Practice:**

**Exercise 5.5:** Build a prime number utility object

```javascript
const PrimeUtils = {
  isPrime: function (num) {
    // Your isPrime code
  },

  findInInterval: function (start, end) {
    // Your findPrimesInInterval code
  },

  count: function (start, end) {
    // Your countPrimesInInterval code
  },

  sum: function (start, end) {
    // Your sumPrimesInInterval code
  },
};

// Test the utility object
console.log(PrimeUtils.isPrime(17));
console.log(PrimeUtils.findInInterval(1, 20));
console.log(PrimeUtils.count(1, 100));
console.log(PrimeUtils.sum(1, 10));
```

---

### **Day 6: Performance, Optimization & Advanced Patterns**

**Morning Session (60 min) - Performance Analysis:**

**Exercise 6.1:** Count operations manually
For checking if 100 is prime, count how many iterations:

```
Without any optimization:
Check: 2, 3, 4, 5, ..., 99
Total iterations: 98

With √n optimization:
Check: 2, 3, 4, ..., 10 (√100 = 10)
Total iterations: 9

With √n + skip evens after 2:
Check: 2, then 3, 5, 7, 9
Total iterations: 5

Savings: 98 → 5 = 95% reduction!
```

Now calculate for these numbers:

- How many checks for isPrime(49)?
- How many checks for isPrime(121)?
- How many checks for isPrime(1000)?

**Exercise 6.2:** Time comparison

```javascript
function isPrimeUnoptimized(num) {
  if (num < 2) return false;
  for (let i = 2; i < num; i++) {
    if (num % i === 0) return false;
  }
  return true;
}

function isPrimeOptimized(num) {
  if (num < 2) return false;
  if (num === 2) return true;
  if (num % 2 === 0) return false;
  for (let i = 3; i <= Math.sqrt(num); i += 2) {
    if (num % i === 0) return false;
  }
  return true;
}

// Compare performance
console.time('unoptimized');
for (let i = 0; i < 10000; i++) {
  isPrimeUnoptimized(i);
}
console.timeEnd('unoptimized');

console.time('optimized');
for (let i = 0; i < 10000; i++) {
  isPrimeOptimized(i);
}
console.timeEnd('optimized');

// What's the speed difference?
```

**Afternoon Session (90 min) - Sieve of Eratosthenes:**

**Exercise 6.3:** Understand the Sieve by hand
Find all primes from 1-30 using the Sieve algorithm:

```
Step 1: Write numbers 2-30
2 3 4 5 6 7 8 9 10 11 12 13 14 15 16 17 18 19 20 21 22 23 24 25 26 27 28 29 30

Step 2: Circle 2 (it's prime), cross out multiples of 2
2 3 X 5 X 7 X 9 X 11 X 13 X 15 X 17 X 19 X 21 X 23 X 25 X 27 X 29 X

Step 3: Circle 3 (next uncrossed), cross out multiples of 3
2 3 X 5 X 7 X X X 11 X 13 X X X 17 X 19 X X X 23 X 25 X X X 29 X

Step 4: Circle 5 (next uncrossed), cross out multiples of 5
2 3 X 5 X 7 X X X 11 X 13 X X X 17 X 19 X X X 23 X X X X X 29 X

Step 5: Circle 7, no more multiples to cross in this range

Primes found: 2, 3, 5, 7, 11, 13, 17, 19, 23, 29
```

**Exercise 6.4:** Implement Sieve of Eratosthenes

```javascript
function sieveOfEratosthenes(max) {
  // Create array of booleans, initially all true
  // true means "potentially prime"
  const isPrime = new Array(max + 1).fill(true);
  isPrime[0] = false;
  isPrime[1] = false;

  // Your code here
  // For each number i from 2 to √max:
  //   If isPrime[i] is true:
  //     Mark all multiples of i as false

  // Collect all numbers that are still marked true
  const primes = [];
  // Your code here

  return primes;
}

// Test it
console.log(sieveOfEratosthenes(30));
// [2, 3, 5, 7, 11, 13, 17, 19, 23, 29]

console.log(sieveOfEratosthenes(100).length);
// Should be 25
```

**Exercise 6.5:** Compare Sieve vs isPrime approach

```javascript
// Method 1: Using isPrime in a loop
function findPrimesMethodA(max) {
  const primes = [];
  for (let i = 2; i <= max; i++) {
    if (isPrime(i)) primes.push(i);
  }
  return primes;
}

// Method 2: Using Sieve
function findPrimesMethodB(max) {
  return sieveOfEratosthenes(max);
}

// Time both methods
console.time('Method A (isPrime loop)');
findPrimesMethodA(10000);
console.timeEnd('Method A (isPrime loop)');

console.time('Method B (Sieve)');
findPrimesMethodB(10000);
console.timeEnd('Method B (Sieve)');

// Which is faster for finding many primes?
```

**Evening Session (30 min) - When to Use Each Method:**

**Exercise 6.6:** Decision making
Answer these questions:

```
Scenario 1: Check if a single number (like 17) is prime
Best approach: _______________
Why: _______________

Scenario 2: Find all primes from 1 to 100
Best approach: _______________
Why: _______________

Scenario 3: Find all primes from 1 to 1,000,000
Best approach: _______________
Why: _______________

Scenario 4: Check if 10 different numbers are prime
Best approach: _______________
Why: _______________
```

---

### **Day 7: Mastery Through Repetition & Final Assessment**

**Morning Session (60 min) - Complete From Memory Round 1:**

**Exercise 7.1:** Full implementation - no references allowed
Close ALL tabs and code editors. Set timer for 20 minutes.

Implement from memory:

```javascript
// 1. isPrime function
function isPrime(num) {
  // Your code
}

// 2. findPrimesInInterval function
function findPrimesInInterval(start, end) {
  // Your code
}

// 3. countPrimesInInterval function
function countPrimesInInterval(start, end) {
  // Your code
}

// ALL these tests must pass:
console.log(isPrime(1) === false);
console.log(isPrime(2) === true);
console.log(isPrime(17) === true);
console.log(isPrime(100) === false);

console.log(
  JSON.stringify(findPrimesInInterval(1, 10)) === JSON.stringify([2, 3, 5, 7]),
);
console.log(
  JSON.stringify(findPrimesInInterval(20, 30)) === JSON.stringify([23, 29]),
);

console.log(countPrimesInInterval(1, 10) === 4);
console.log(countPrimesInInterval(1, 100) === 25);
```

Time: **\_** minutes
Errors found: **\_**
Result: PASS / FAIL

**Afternoon Session (90 min) - Timed Challenges:**

**Exercise 7.2:** Speed challenge - Repeat 4 times
Delete everything. Rewrite both functions from scratch. Time yourself.

Challenge 1:

- Time: **\_** minutes
- Errors: **\_**

Challenge 2:

- Time: **\_** minutes
- Errors: **\_**

Challenge 3:

- Time: **\_** minutes
- Errors: **\_**

Challenge 4:

- Time: **\_** minutes
- Errors: **\_**

Goal: Complete in under 10 minutes with zero errors

**Exercise 7.3:** Variation challenge
Implement these related functions from memory (15 min each):

```javascript
// 1. Find the nth prime number
function nthPrime(n) {
  // Return the nth prime (1st prime is 2, 2nd is 3, etc.)
}

console.log(nthPrime(1)); // 2
console.log(nthPrime(10)); // 29
console.log(nthPrime(25)); // 97

// 2. Check if a number is a sum of two primes (Goldbach)
function isSumOfTwoPrimes(num) {
  // Return true if num can be expressed as sum of two primes
}

console.log(isSumOfTwoPrimes(10)); // true (3+7 or 5+5)
console.log(isSumOfTwoPrimes(11)); // false

// 3. Find prime factors of a number
function primeFactors(num) {
  // Return array of prime factors
}

console.log(primeFactors(12)); // [2, 2, 3]
console.log(primeFactors(30)); // [2, 3, 5]
console.log(primeFactors(17)); // [17]
```

**Evening Session (60 min) - Teaching & Reflection:**

**Exercise 7.4:** Explain to someone else (or write it down)
Write a tutorial explaining these concepts as if teaching a beginner:

1. What is a prime number? (3-4 sentences)
2. Why do we check up to √n? (include a diagram or example)
3. Why is 1 not prime? (mathematical reason)
4. How does isPrime work? (step-by-step walkthrough)
5. How does findPrimesInInterval work?
6. When should you use Sieve vs isPrime?

**Exercise 7.5:** Create your own cheat sheet
Without looking at any references, create a one-page summary:

```
PRIME NUMBERS CHEAT SHEET

Definition:
_______________

Key Properties:
1. _______________
2. _______________
3. _______________

isPrime Algorithm:
Step 1: _______________
Step 2: _______________
...

Common Mistakes to Avoid:
- _______________
- _______________

Performance Tips:
- _______________
- _______________

Code Template:
[Write your templates]
```

**Exercise 7.6:** Final mastery assessment
One last time - implement everything from scratch with NO help:

- isPrime
- findPrimesInInterval
- One bonus function of your choice

Time limit: 15 minutes
Must be perfect (zero errors)

Result: PASS / FAIL
Time: **\_** minutes

---

## Week Completion Checklist

By the end of Day 7, you should be able to:

**Understanding:**

- [ ] Explain what a prime number is in your own words
- [ ] Explain why we check up to √n (with diagram/example)
- [ ] Explain why 1 is not prime
- [ ] Explain why 2 is the only even prime
- [ ] Understand when to use different algorithms

**Skills:**

- [ ] Write isPrime from memory in under 3 minutes
- [ ] Write findPrimesInInterval from memory in under 5 minutes
- [ ] Identify and fix bugs in prime-checking code
- [ ] Handle edge cases correctly (0, 1, 2, negatives, empty intervals)
- [ ] Trace execution by hand for any input
- [ ] Implement variations (count, sum, nth prime, etc.)

**Performance:**

- [ ] Understand time complexity implications
- [ ] Implement optimizations (√n, skip evens)
- [ ] Know when to use Sieve vs isPrime
- [ ] Calculate iteration counts for different approaches

---

## Daily Time Investment

**Minimum:** 2 hours/day
**Recommended:** 2.5-3 hours/day
**Distribution:**

- 40% hands-on coding practice
- 30% problem-solving exercises
- 20% theory and understanding
- 10% review and reflection

---

## Study Tips for Maximum Retention

1. **Delete and rewrite** - Never edit, always start fresh
2. **No copy-paste** - Type everything yourself
3. **Trace by hand** - Draw out the execution for problem inputs
4. **Test edge cases** - 0, 1, 2, negatives, large numbers
5. **Explain out loud** - If you can teach it, you understand it
6. **Time yourself** - Speed comes from understanding
7. **No peeking** - Struggle builds stronger memory
8. **Sleep on it** - Your brain consolidates learning overnight
9. **Review previous days** - Spaced repetition is key
10. **Track progress** - Keep notes on time and errors

---

## Common Mistakes to Watch For

```javascript
// Mistake 1: Forgetting that 2 is prime
if (num <= 2) return false;  // WRONG! 2 is prime

// Mistake 2: Not handling 1 correctly
if (num < 1) return false;   // WRONG! Should be < 2

// Mistake 3: Checking all numbers instead of just up to √n
for (let i = 2; i < num; i++)  // SLOW! Should be i <= Math.sqrt(num)

// Mistake 4: Not skipping even numbers
for (let i = 2; i <= Math.sqrt(num); i++)  // SLOW! Should start at 3, increment by 2

// Mistake 5: Checking even numbers in the interval
for (let num = start; num <= end; num++)  // Works but wasteful for large ranges
```

---

## What Success Looks Like

After 7 days:

- You can implement isPrime perfectly from memory in 2-3 minutes
- You can implement findPrimesInInterval perfectly from memory in 5-7 minutes
- You understand WHY each line of code exists
- You can explain the algorithms to someone else
- You can debug prime-related code quickly
- You can implement variations and extensions
- You feel confident tackling similar algorithmic problems

Remember: The goal isn't memorization—it's **deep understanding** that makes implementation natural and automatic.

Good luck! 🚀
