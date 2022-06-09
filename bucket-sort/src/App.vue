<template>
  <div>
    <BucketSort msg="Shell Sort" />
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
    <button @click="bucketSort(data.arrNum)">Click for Bucket Sort</button>
  </div>
</template>

<script>
import BucketSort from "./components/BucketSort.vue";

export default {
  name: "App",
  components: {
    BucketSort,
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

    bucketSort(array) {
      let n = array.length;

      //Start with a really large gap, and then reduce the gap until there isn't any
      //With this, the gap starts as half of the array length, and then half of that every time
      for (let gap = Math.floor(n / 2); gap > 0; gap = Math.floor(gap / 2)) {
        //Do a insertion sort for each of the section the gap ends up dividing
        for (let i = gap; i < n; i += 1) {
          //We store the current varible
          let temp = array[i];

          //This is the insection sort to sort the section into order
          let j;
          for (j = i; j >= gap && array[j - gap] > temp; j -= gap) {
            array[j] = array[j - gap];
          }

          array[j] = temp;
        }
      }
      this.data.arrNum = array;
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
