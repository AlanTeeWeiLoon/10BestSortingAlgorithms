# counting-sort

### Algorithm Description
- Find out the maximum element (let it be max ) from the given array. 
- Initialize an array of length max+1 with all elements 0. This array is used for storing the count of the elements in the array.
- Store the count of each element at their respective index in count array. 
- Store cumulative sum of the elements of the count array. It helps in placing the elements into the correct index of the sorted array.
- Find the index of each element of the original array in the count array. This gives the cumulative count. Place the element at the index calculated.
- After placing each element at its correct position, decrease its count by one.

### Properties
- Space complexity: O(k)
- Best case performance: O(n+k)
- Average case performance: O(n+k)
- Worst case performance: O(n+k)
- Stable: Yes

---

### Counting Sort in JavaScript

```
countingSort(inputArr, n = inputArr.length) {
      let k = Math.max(...inputArr);
      let t;
      //Create a temporary with 0 zero value
      //as the same length of max elemet + 1
      const temp = new Array(k + 1).fill(0);

      //Count the frequency of each element in the original array
      //And store it in temp array
      for (let i = 0; i < n; i++) {
        t = inputArr[i];
        temp[t]++;
      }

      //Update the count based on the previous index
      for (let i = 1; i <= k; i++) {
        // Updating elements of count array
        temp[i] = temp[i] + temp[i - 1];
      }

      //Output arr
      const outputArr = new Array(n).fill(0);

      for (let i = n - 1; i >= 0; i--) {
        // Add elements of array A to array B
        t = inputArr[i];
        outputArr[temp[t] - 1] = t;

        // Decrement the count value by 1
        temp[t] = temp[t] - 1;
      }

      return outputArr;
    },
```
### GIF Demo

#### Demo 1

<img src="https://github.com/AlanTeeWeiLoon/10BestSortingAlgorithms/blob/main/counting-sort/public/Images/Coounting-Sort.gif" />

---

## Project setup
```
npm install
```

### Compiles and hot-reloads for development
```
npm run serve
```
