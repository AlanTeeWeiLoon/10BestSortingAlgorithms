# selection-sort

### Algorithm Description
- Find the smallest (largest) value in the sequence, swap it with the first element
- Select the smallest (largest) value from the remaining unsorted elements and place it first
- Repeat this step until the sequence is in order

### Properties
- Space Complexity:  O(n)
- Time Complexity:  O(n2)
- Sorting in Place:  Yes
- Stable:  No

---

### Selection Sort in JavaScript

```
selectionSort(array){
      let n = array.length;
        
    for(let i = 0; i < n; i++) {
        // Finding the smallest number in the subarray
        let min = i;
        for(let j = i+1; j < n; j++){
            if(array[j] < array[min]) {
                min=j; 
            }
         }
         if (min != i) {
             // Swapping the elements
             let tmp = array[i]; 
             array[i] = array[min];
             array[min] = tmp;      
        }
    }
      return array;
    }
```
### GIF Demo

#### Demo 1
<img src="https://github.com/AlanTeeWeiLoon/10BestSortingAlgorithms/blob/main/selection-sort/public/Images/Selection-Sort-1.gif" />

---

## Project setup
```
npm install
```

### Compiles and hot-reloads for development
```
npm run serve
```
