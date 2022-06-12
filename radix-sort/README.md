# radix-sort

### Algorithm Description
- Finding the maximum element
- Count the number of digits of the maximum number
- Arrange the numbers on the basis of the least significant digit
- Arrange the numbers according to the next significant digit
- Keep performing the process until the most significant digit

### Properties
- Space complexity: O(k + n)
- Best case performance: O(k * n)
- Average case performance: O(k * n)
- Worst case performance: O(k * n)
- Stable: Yes

---

### Radix Sort in JavaScript

```
<script>
import RadixSort from "./components/RadixSort.vue";

export default {
  name: "App",
  components: {
    RadixSort,
  },
  data() {
    return {
      data: {
        arrNum: [1, 2, 3, 4, 5, 6, 7, 8, 9, 10],
      },
    };
  },
  methods: {
    randomNum() {
      var arr = [];
      while (arr.length < 10) {
        var r = Math.floor(Math.random() * 100) + 1;
        if (arr.indexOf(r) === -1) arr.push(r);
      }
      this.data.arrNum = arr;
    },

    getDigit(num, place) {
      return Math.floor(Math.abs(num) / Math.pow(10, place)) % 10;
    },

    digitCount(num) {
      if (num === 0) return 1;
      return Math.floor(Math.log10(Math.abs(num))) + 1;
    },

    mostDigits(nums) {
      let maxDigits = 0;
      for (let i = 0; i < nums.length; i++) {
        maxDigits = Math.max(maxDigits, this.digitCount(nums[i]));
      }
      return maxDigits;
    },

    radixSort(arrOfNums) {
      let maxDigitCount = this.mostDigits(arrOfNums);
      for (let k = 0; k < maxDigitCount; k++) {
        let digitBuckets = Array.from({ length: 10 }, () => []);
        for (let i = 0; i < arrOfNums.length; i++) {
          let digit = this.getDigit(arrOfNums[i], k);
          digitBuckets[digit].push(arrOfNums[i]);
        }
        // New order after each loop
        arrOfNums = [].concat(...digitBuckets);
      }
      this.data.arrNum = arrOfNums;
    },
  },
};
</script>
```
### GIF Demo

#### Demo 1
<img src="https://github.com/AlanTeeWeiLoon/10BestSortingAlgorithms/blob/main/radix-sort/public/Images/Radix-Sort.gif" />

---

## Project setup
```
npm install
```

### Compiles and hot-reloads for development
```
npm run serve
```
