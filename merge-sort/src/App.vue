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
            v-for="(num, i) in data.arrNum"
            v-bind:key="i"
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
        resultArray:[]
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
				this.data.arrNum = this.runMergeSort(arr);
			},
			runMergeSort(input) {
				if (input.length <= 1) return input;
				// divide Array in half, figure out middle
				const middle = Math.floor(input.length / 2);
				// divide array into left and right
				const left = input.slice(0, middle);
				const right = input.slice(middle);
				return this.merge(this.runMergeSort(left), this.runMergeSort(right));
			},
			merge(left, right) {
				const resultArray = [];
				let leftIndex = 0;
				let rightIndex = 0;
				while (leftIndex < left.length && rightIndex < right.length) {
					const leftEl = left[leftIndex];
					const rightEl = right[rightIndex];
					if (leftEl.value < rightEl.value) {
						resultArray.push(leftEl);
            this.data.resultArray.push(leftEl);
						leftIndex++;
					} else {
						resultArray.push(rightEl);
            this.data.resultArray.push(rightEl);
						rightIndex++;
					}
				}
				return [
					...resultArray,
					...left.slice(leftIndex),
					...right.slice(rightIndex),
				];
			},

    
  }
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
