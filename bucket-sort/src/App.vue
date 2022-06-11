<template>
  <div>
    <BucketSort msg="Bucket Sort" />
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

    bucketSort(arr) {
      setTimeout(() => {
        if (arr.length === 0) {
          return arr;
        }
        let i,
          minValue = arr[0],
          maxValue = arr[0],
          bucketSize = 5;
        arr.forEach(function (currentVal) {
          if (currentVal < minValue) {
            minValue = currentVal;
          } else if (currentVal > maxValue) {
            maxValue = currentVal;
          }
        });
        let bucketCount = Math.floor((maxValue - minValue) / bucketSize) + 1;
        let allBuckets = new Array(bucketCount);
        for (i = 0; i < allBuckets.length; i++) {
          allBuckets[i] = [];
        }
        arr.forEach(function (currentVal) {
          allBuckets[Math.floor((currentVal - minValue) / bucketSize)].push(
            currentVal
          );
        });
        arr.length = 0;
        allBuckets.forEach((bucket) => {
          this.InsertionSort(bucket);
          bucket.forEach(function (element) {
            arr.push(element);
          });
        });
      }, 200);
      this.data.arrNum = arr;
    },
    
    InsertionSort(arr) {
      let length = arr.length;
      let i, j;
      for (i = 1; i < length; i++) {
        let temp = arr[i];
        for (j = i - 1; j >= 0 && arr[j] > temp; j--) {
          arr[j + 1] = arr[j];
        }
        arr[j + 1] = temp;
      }
      return arr;
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
