# bubble-sort

### Algorithm Description
- Compare adjacent elements. If the first is larger than the second, swap the two
- Do the same for each pair of adjacent elements, from the first pair at the beginning to the last pair at the end, so that the last element should be the largest number
- Repeat the above steps for all elements except the last one
- Repeat steps 1~3 until the sorting is complete

### Properties
- Space complexity: O(1)
- Best case performance: O(n)
- Average case performance: O(n*n)
- Worst case performance: O(n*n)
- Stable: Yes

---

### Bubble Sort in JavaScript

```
bubbleSort(array){
      for (let i = 0; i < array.length; i++) {
        for (let j = 0; j < array.length; j++) {
          if (array[j] > array[j + 1]) {
            let temp = array[j];
            array[j] = array[j + 1];
            array[j + 1] = temp;
          }
        }
      }
      return array；
}
```
### GIF Demo

#### Demo 1
<img src="https://github.com/AlanTeeWeiLoon/10BestSortingAlgorithms/blob/main/bubble-sort/public/Images/Bubble-Sort.gif" />

#### Demo 2
<img src="https://github.com/AlanTeeWeiLoon/10BestSortingAlgorithms/blob/main/bubble-sort/public/Images/Bubble-Sort-1.gif" />

---

## Project setup
```
npm install
```

### Compiles and hot-reloads for development
```
npm run serve
```
