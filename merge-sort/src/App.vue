<template>
  <div>
    <MergeSort msg="Merge Sort" />
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
    <button @click="mergeSort(data.arrNum)">Click for Merge Sort</button>
  </div>
</template>

<script>
import MergeSort from "./components/MergeSort.vue";

export default {
  name: "App",
  components: {
    MergeSort,
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

     mergeSort(arr) {
      if (arr.length <= 1){
        this.data.arrNum = arr;
      } 

      let mid = Math.floor(arr.length / 2);
      let left = arr.slice(0, mid);
      console.log("left",left)
      let right = arr.slice(mid);
      console.log("right",right)


      this.merge(left, right);
    },

     merge(arr1, arr2) {
      let i = 0;
      let j = 0;
      let results = [];
      while (i < arr1.length && j < arr2.length) {
        if (arr2[j] > arr1[i]) {
          results.push(arr1[i]);
          i++;
        } else {
          results.push(arr2[j]);
          j++;
        }
      }
      console.log("results",results)
      while (i < arr1.length) {
        results.push(arr1[i]);
        i++;
      }
      console.log("results1",results)
      while (j < arr2.length) {
        results.push(arr2[j]);
        j++;
      }
      this.data.arrNum = results;
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
