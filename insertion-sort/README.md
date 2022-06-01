# insertion-sort

### Algorithm Description
- Starting from the first element, the element can be considered sorted
- Take the next element and scan from back to front in the sorted sequence of elements
- If the element (sorted) is greater than the new element, move the element to the next position
- Repeat step 3 until you find the position where the sorted element is less than or equal to the new element
- After inserting the new element at that position
- Repeat steps 2~5

### Properties
- Space Complexity: O(1)
- Time Complexity: O(n), O(n* n), O(n* n) for Best, Average, Worst cases respectively.
- Best Case: array is already sorted
- Average Case: array is randomly sorted
- Worst Case: array is reversely sorted.
- Sorting In Place: Yes
- Stable: Yes

---

### Insertion Sort in JavaScript

```
insertionSort(array){
      for (let i = 1; i < array.length; i++) {
    let currentValue = array[i]
    let j
    for (j = i - 1; j >= 0 && array[j] > currentValue; j--) {
      array[j + 1] = array[j]
    }
    array[j + 1] = currentValue
  }
      return array;
    }
```
### GIF Demo

#### Demo 1

<img src="https://github.com/AlanTeeWeiLoon/10BestSortingAlgorithms/blob/main/insertion-sort/public/Images/Insertion-Sort-1.gif" />

---

## Project setup
```
npm install
```

### Compiles and hot-reloads for development
```
npm run serve
```
