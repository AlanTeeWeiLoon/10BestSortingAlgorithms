<template>
  <div>
    <QuickSort msg="Quick Sort" />
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
    <button @click="quickSort(data.arrNum)">Click for Quick Sort</button>
  </div>
</template>

<script>
import QuickSort from "./components/QuickSort.vue";

export default {
  name: "App",
  components: {
    QuickSort,
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

    QuickSort(array) {
      if(array.length <= 1){
   this.data.arrNum = array;
  }

  const pivot = array[array.length - 1];
  const leftArr = [];
  const rightArr = [];

  for(let i=0; i < array.length-1;i++){
    if(array[i] < pivot){
      leftArr.push(array[i]);
    }
    else{
      rightArr.push(array[i])
    }
  }

  this.data.arrNum =  [...QuickSort(leftArr) ,pivot,...QuickSort(rightArr)];
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
