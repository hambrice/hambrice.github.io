---
layout: post
title:      "Space: The Complex Frontier"
date:       2018-09-17 19:01:53 -0400
permalink:  space_the_complex_frontier
---


While I have been working on numerous things since graduating from the Flatiron School's program, one of my largest focuses has been on developing my Computer Science(CS) fundamentals. I learned so much during the program, but one of the biggest challenges I will face as I begin my career in web development will be handling scalability. When building small projects on my own, worrying about the size of inputs or the time functions has largely been irrelevant, as I'm dealing with a minimal amount of data. However, when it comes to working for a large company, I have begun to learn the importance of considering these concepts.

One of the first things almost everything I have read in regards to CS introduces is the concept of Big O Notation, and while there exist numerous resources on learning about Big O Notation and the related time complexity, one thing I have found is that space complexity is not often as clearly explained. Given that, I decided to do a deeper dive into it so I could better understand both sides of the complexity question.

When creating an algorithm, the time it takes to complete is not the only aspect to be considered. If you create an algorithm that runs quickly, but is creating tons of arrays in the process, you might start to run into issues with the amount of available memory. Therefore, space complexity, while typically not as large of a concern as time complexity, must also be considered. 

One thing I found on my search was some discrepancies in the use of certain terms. Auxilliary space is defined as the extra space created by an algorithm, ignoring the actual size of the inputs. While some resources I found seemed to equate auxilliary space with space complexity, others stated that space complexity must also consider the size of the inputs as well (meaning that space complexity is actually the auxilliary space plus the input space.) The latter idea can be illustrated with Insertion Sort:

```
function insertionSort(array) {
  for (let i=1; i < array.length; i++) {
	  for (let j=0; j < i; j++) {
		  if (nums[i] < nums[j]) {
        let spliced = nums.splice(i, 1);
        nums.splice(j, 0, spliced[0]);
		}
	}
}
```

In this example, the auxilliary space would be O(1), as 'spliced' is our only created variable, and spliced only ever equals one 'thing' at a time. However, given that 'array' has a size of n, if we consider the size of inputs in additional to our auxilliary space, then the space complexity of Insertion Sort would be O(n+1), or simply O(n). 

I was a little confused by the inconsistencies of the terms, but it seems part of the issue is that modern languages abstract spatial storage, making it more difficult to truly know what's going on under the hood in regards to memory. 

My current take-away is that while time complexity is typically the more important one to consider, it's also to be aware of space complexity and the challenges it may present. Further, it is beneficial to be aware of the differences between auxilliary space and space complexity that takes into account the size of the inputs as well. I'm confident that as I begin my coding career, these concepts will be important to understand to better handle the huge amounts of data that can be presented!

