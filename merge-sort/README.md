# merge-sort

### Algorithm Description
- Divide the input sequence of length n into two subsequences of length n/2;
- Merge sort is used for these two subsequences respectively;
- Merge the two sorted subsequences into a final sorted sequence.

### Properties
- Space Complexity: O(n)
- Time Complexity: O(n*log(n))
- Stable: Yes
- Parallelizable :yes 

---

### Merge Sort in JavaScript

```
function mergeSort(arr) {
      if (arr.length <= 1) return arr;

      let mid = Math.floor(arr.length / 2);
      let left = mergeSort(arr.slice(0, mid));
      let right = mergeSort(arr.slice(mid));
      return merge(left, right);
    },

    function merge(arr1, arr2) {
      let i = 0;
      let j = 0;
      let results = [];
      while (i < arr1.length && j < arr2.length) {
        if (arr2[j] > arr1[i]) {
          results.push(arr1[i]);
          i++;
        } else {
          results.push(arr2[j]);
          j++;
        }
      }
      while (i < arr1.length) {
        results.push(arr1[i]);
        i++;
      }
      while (j < arr2.length) {
        results.push(arr2[j]);
        j++;
      }
      return results;
    },
```
### GIF Demo

#### Demo 1
<img src="https://github.com/AlanTeeWeiLoon/10BestSortingAlgorithms/blob/main/merge-sort/public/Images/merge-sort.gif" />

---

## Project setup
```
npm install
```

### Compiles and hot-reloads for development
```
npm run serve
```


