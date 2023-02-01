---
title: TalentOrg' Interview (remote) 
date: 2023-01-28 09:25:00
img: https://images.pexels.com/photos/355465/pexels-photo-355465.jpeg?auto=compress&cs=tinysrgb&w=1260&h=750&dpr=2
top: true
hide: false
cover: true
coverImg: https://images.pexels.com/photos/355465/pexels-photo-355465.jpeg?auto=compress&cs=tinysrgb&w=1260&h=750&dpr=2
toc: true
mathjax: false
summary: Interview notes, purely algorithmic.
categories: Interview
reprintPolicy: cc_by
tags:
  - Remote Job
  - Interview
---
## Question
<div class="markdown-question markdown-question-snippet text-left"><p>You are keeping score for a baseball game with strange rules. The game consists of several rounds, where the scores of past rounds may affect future rounds' scores.</p>
<p>At the beginning of the game, you start with an empty record. You are given a list of strings ops, where ops[i] is the ith operation you must apply to the record and is one of the following:</p>
<ul>
<li>An integer x - Record a new score of x.</li>
<li>"+" - Record a new score that is the sum of the previous two scores. It is guaranteed there will always be two previous scores.</li>
<li>"D" - Record a new score that is double the previous score. It is guaranteed there will always be a previous score.</li>
<li>"C" - Invalidate the previous score, removing it from the record. It is guaranteed there will always be a previous score.<br>Return the sum of all the scores on the record. The test cases are generated so that the answer fits in a 32-bit integer.</li>
</ul>
<pre><code>Example 1:

Input: ops = ["5","2","C","D","+"]
Output: 30
Explanation:
"5" - Add 5 to the record, record is now [5].
"2" - Add 2 to the record, record is now [5, 2].
"C" - Invalidate and remove the previous score, record is now [5].
"D" - Add 2 * 5 = 10 to the record, record is now [5, 10].
"+" - Add 5 + 10 = 15 to the record, record is now [5, 10, 15].
The total sum is 5 + 10 + 15 = 30.
</code></pre>
<pre><code>Example 2:

Input: ops = ["5","-2","4","C","D","9","+","+"]
Output: 27
Explanation:
"5" - Add 5 to the record, record is now [5].
"-2" - Add -2 to the record, record is now [5, -2].
"4" - Add 4 to the record, record is now [5, -2, 4].
"C" - Invalidate and remove the previous score, record is now [5, -2].
"D" - Add 2 * -2 = -4 to the record, record is now [5, -2, -4].
"9" - Add 9 to the record, record is now [5, -2, -4, 9].
"+" - Add -4 + 9 = 5 to the record, record is now [5, -2, -4, 9, 5].
"+" - Add 9 + 5 = 14 to the record, record is now [5, -2, -4, 9, 5, 14].
The total sum is 5 + -2 + -4 + 9 + 5 + 14 = 27.
</code></pre>
<pre><code>Example 3:

Input: ops = ["1","C"]
Output: 0
Explanation:
"1" - Add 1 to the record, record is now [1].
"C" - Invalidate and remove the previous score, record is now [].
Since the record is empty, the total sum is 0.
</code></pre>
<p>Constraints:</p>
<p>1 &lt;= ops.length &lt;= 1000<br>ops[i] is "C", "D", "+", or a string representing an integer in the range [-3 * 104, 3 * 104].<br>For operation "+", there will always be at least two previous scores on the record.<br>For operations "C" and "D", there will always be at least one previous score on the record.</p>
</div>


## Answer

```function solution(a) {
    // Write your answer here
    if (!Array.isArray(a) || a.length <= 0) return 0;
    for (let i =0; i < a.length; i++) {
      let curStr = (a[i]).toString().toUpperCase();
      if(isNaN(+curStr)){
        switch (curStr){
          case 'C':
            if(i > 0){
              a.splice(i-1, 2)
            };
          case 'D':
            if(i >= 1){
              let nextNum = parseInt(a[i-2]) * 2
              a.splice(i-1,1,nextNum)
            };
          case '+':
            if(i >= 2){
              let nextNum = parseInt(a[i-1]) + parseInt(a[i-2])
              a.splice(i,1,nextNum)
            };
        }
      }
    }
    function sum(arr) {
      let s = 0;
      arr.forEach(function(val, idx, arr) {
        s += parseInt(val);
      }, 0);
      return s;
    };
    return sum(a)
  }

  // DO NOT DELETE
  module.exports = {
    solution
  }

```

## Summary
To be honest, I failed this interview, but I think it also could have been recorded and realized that I have to work on the Algorithms.
