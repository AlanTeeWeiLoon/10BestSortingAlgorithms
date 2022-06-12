<template>
  <div>
    <RadixSort msg="Radix Sort" />
    <div>
      <button @click="randomNum">Click to random generate 10 numbers</button>
    </div>
    <div>
      <table class="center">
        <tr>
          <td
            v-for="num in data.arrNum"
            v-bind:key="num"
            style="width: 2em; font-size: x-large; font-weight: bold"
          >
            {{ num }}
          </td>
        </tr>
      </table>
    </div>
    <button @click="radixSort(data.arrNum)">Click for Radix Sort</button>
  </div>
</template>

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

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
.center {
  margin-left: auto;
  margin-right: auto;
  margin-top: 1em;
  margin-bottom: 1em;
}
</style>
