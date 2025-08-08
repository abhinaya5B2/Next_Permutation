# Next_Permutation:
Given an array of integers representing a permutation (i.e., all elements are unique), find the next lexicographically greater permutation. If the current arrangement is the last permutation, return the first (sorted) permutation.

🔍 Lexicographical Order:
This is the order in which words appear in a dictionary. For numbers, it means:

Compare from left to right

As soon as one number is greater than the other, that determines the order

For example:

css
Copy
Edit
[1, 2, 3] < [1, 3, 2] < [2, 1, 3]
🧠 Approach / Logic:
Step 1: Find the pivot (first decreasing element from the end)
Traverse the array from the end to the start.

Find the first index i such that:

css
Copy
Edit
arr[i] < arr[i + 1]
Why? Because that's where the next permutation can be increased.

Step 2: Find the just greater element on the right
Again, from the end of the array, find the first index j such that:

css
Copy
Edit
arr[j] > arr[i]
This gives us the smallest number greater than arr[i], to swap with.

Step 3: Swap arr[i] and arr[j]
This increases the value at position i, making the number slightly bigger.

Step 4: Reverse the subarray from i+1 to the end
Why? Because the subarray after i was in decreasing order.

To make it the smallest possible (next permutation), we reverse it into ascending order.

📌 Edge Case:
If no such i is found in Step 1 (i.e., the array is strictly decreasing), it means:

It's the last permutation

So, we reverse the whole array to get the first (sorted) permutation

