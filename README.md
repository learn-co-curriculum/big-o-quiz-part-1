# Day 3: Work Out Big O Quiz Part 1

In this quiz, we'll calculate the time and space complexity for two of the algorithm challenges from Phase 1. After this quiz, we encourage you to look at your own solutions for the same problems and calculate Big O for them too.

1. Multiple-choice

Calculate the time and space complexity for the following code. We've included both JS and Ruby for the same function.

<h3>JavaScript</h3>
<pre>
<code>
function reverseString(str) {
  let reversed = "";

  for (let i = str.length - 1; i > -1; --i) {
    reversed = reversed + str[i];
  }

  return reversed;
}
</code>
</pre>

<h3>Ruby</h3>
<pre>
<code>
def reverse_string(str)
  reversed_str = ""

  str.chars.each do |char|
    reversed_str = char + reversed_str
  end

  reversed_str
end
</code>
</pre>

- Time: O(n), Space: O(n)
  - Correct! The runtime and space directly correlate to the length of the string. The reversed string and input will be the same length and the number of iterations over the string is also equal to the length of the string.
- Time: O(1), Space: O(n)
  - Not quite. This procedure doesn't run in constant time. Take a look at how it iterates over the string. It does require linear space, however, since the reversed string will be of equal length to the input.
- Time: O(n), Space: O(2n)
  - Not quite. It does run in linear time, since it iterates over each character once. However, if you recall from the readings, we always drop coefficients for Big O.
- I don't know
  - Don't worry. With time and practice, it'll start to sink in.

2. Multiple-choice

Calculate the time and space complexity for the following code. We've included both JS and Ruby for the same function.

<h3>JavaScript</h3>
<pre>
<code>
function fibonacci(num) {
  if (num < 2) {
    return num;
  }

  let lastTwo = [0, 1];

  for (let i = 0; i < num - 1; ++i) {
    const sum = lastTwo[0] + lastTwo[1];
    lastTwo = [lastTwo[1], sum];
  }

  return lastTwo[1];
}
</code>
</pre>

<h3>Ruby</h3>
<pre>
<code>
def fibonacci(num)
  last_two = [0, 1]

  return last_two[num] if num < 2

  i = num - 1

  while i > 0
    sum = last_two[0] + last_two[1]
    last_two = [last_two[1], sum]
    i -= 1
  end

  last_two.last
end
</code>
</pre>

- Time: O(n), Space: O(1)
  - Err Mehrr Gerrd! You got it!! Time complexity is O(n) because the number of iterations through the while loop is directly proportional to the input value `num`, and that's the weakest link. The space complexity is constant. It doesn't matter if `n` is 0 or 100, this algorithm always relies on the same amount of data: an integer input, an array with two elements, and a variable to track the iterations. 
- Time: O(n), Space: O(n)
  - Not quite. The time complexity is linear because the number of iterations through the while loop is directly proportional to the input value `num`. However, the amount of space used doesn't change with the input size. Think about what this algorithm stores if the input is 2 versus 10.
- Time: O(1), Space: O(2n)
  - Not quite. Take a look at the while loop. How many iterations will occur if `num` is 3 versus 5? Also think about what's being stored as the input grows. Is the amount of space required changing? Does the array (`lastTwo`, `last_two`) ever change in length?
- I don't know
  - Don't worry. With time and practice, it'll start to sink in.