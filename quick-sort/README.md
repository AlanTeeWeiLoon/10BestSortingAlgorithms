# quick-sort

### Algorithm Description
- Choose an element to serve as a pivot
- Partitioning: Sort the array in such a manner that all elements less than the pivot are to the left, and all elements greater than the pivot are to the right.
- Call Quicksort recursively, taking into account the previous pivot to properly subdivide the left and right arrays

### Properties
- Space Complexity: O(1)
- Best Case: O(n*logn)
- Average Case: O(n*logn)
- Worst Case: O(n* n)
- Stable: No

---

### Quick Sort in JavaScript

```
<script>
import QuickSort from "./components/QuickSort.vue";

export default {
  name: "App",
  components: {
    QuickSort,
  },
  data() {
    return {
      nodes: [1, 2, 3, 4, 5, 6, 7, 8, 9, 10],
      delay: 200,
      lowerRange: 0,
      upperRange: 0,
    };
  },
  methods: {
    randomNum() {
      var arr = [];
      while (arr.length < 10) {
        var r = Math.floor(Math.random() * 100) + 1;
        if (arr.indexOf(r) === -1) arr.push(r);
      }
      this.nodes = arr;
    },
    comparer: (a, b) => a < b,
    quickSort(i = null, j = null) {
      setTimeout(() => {
        if (i === null) i = 0;
        if (j === null) j = this.nodes.length - 1;

        this.lowerRange = i;
        this.upperRange = j;

        if (i >= j) {
          return;
        }

        const pivot = this.partition(i, j);
        this.quickSort(i, pivot - 1);
        this.quickSort(pivot + 1, j);
      }, this.delay);

    },
    partition(min, max) {
      const pivot = max;
      let wall = min;
      for (let i = wall; i <= max; i++) {
        if (this.comparer(this.nodes[i], this.nodes[pivot])) {
          this.swap(i, wall);
          wall++;
        }
      }
      

      this.swap(wall, pivot);
      return wall;
    },
    swap(from, to) {
      const tmp = this.nodes[from];
      this.nodes[from] = this.nodes[to];
      this.nodes[to] = tmp;

    },
  },
};
</script>
```
### GIF Demo

#### Demo 1

<img src="https://github.com/AlanTeeWeiLoon/10BestSortingAlgorithms/blob/main/quick-sort/public/Images/Quick-Sort.gif" />

---

## Project setup
```
npm install
```

### Compiles and hot-reloads for development
```
npm run serve
```
