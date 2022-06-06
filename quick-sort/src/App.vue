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
            v-for="num in nodes"
            v-bind:key="num"
            style="width: 2em; font-size: x-large; font-weight: bold"
          >
            {{ num }}
          </td>
        </tr>
      </table>
    </div>
    <button @click="quickSort()">Click for Quick Sort</button>
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
