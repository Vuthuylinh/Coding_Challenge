# Maximum Sum Subarray of Size K (easy)

### Prompt:

Given an array of possitive numbers and a positive number `k`, find the maximum sum of any contiguous subarray of size `k`.

### Example 1:

- Input: [2, 1, 5, 1, 3, 2], k=3
- Output: 9
- Explanation: Subarray with maximum sum is [5, 1, 3].

### Example 2:

- Input: [2, 3, 4, 1, 5], k=2
- Output: 7
- Explanation: Subarray with maximum sum is [3, 4].

# Solution

### Approach

- using sliding window
- Initialize starting point (index); start =0
- initialize window_sum =0
- initialize result/maxSum = 0 then compare and keep track
- using 1 for loop

```js
  function max_sub_array_of_size_k(k, array){
    let maxSum = 0;
    let start = 0;
    let windowSum=0;
    for(let end =0; end<array.length; end++){
      windowSum +=array[end];
      if(end-start===k-1){
        maxSum = Math.max(maxSum,windowSum);
         windowSum -=array[start];
         start++;
      }
    }
    return maxSum;
  }
```

### Brute force

```js
function max_sub_array_of_size_k(k, array){
    let max=0;
    for(let i=0; i<array.length-k+1; i++){
      let sum=0
      for(let j=i; j<i+k; j++){
        sum +=array[j];
        max= Math.max(sum,max)
      }
    }
    return max;
  }
```
