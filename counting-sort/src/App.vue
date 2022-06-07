<template>
  <div>
    <CountingSort msg="Counting Sort" />
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
    <button @click="countingSort(data.arrNum)">Click for Counting Sort</button>
  </div>
</template>

<script>
import CountingSort from "./components/CountingSort.vue";

export default {
  name: "App",
  components: {
    CountingSort,
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

      this.data.arrNum = outputArr;
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
