# bubble-sort

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

<img src="https://github.com/AlanTeeWeiLoon/10BestSortingAlgorithms/blob/main/bubble-sort/public/Images/Bubble-Sort.gif" />


## Project setup
```
npm install
```

### Compiles and hot-reloads for development
```
npm run serve
```
