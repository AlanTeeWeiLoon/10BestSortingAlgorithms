<template>
  <div>
    <HeapSort msg="Heap Sort" />
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
    <button @click="heapSort(data.arrNum)">Click for Heap Sort</button>
  </div>
</template>

<script>
import HeapSort from "./components/HeapSort.vue";

export default {
  name: "App",
  components: {
    HeapSort,
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

    buildMaxHeap(arr) {
      let i = Math.floor(arr.length / 2 - 1);

      while (i >= 0) {
        this.heapify(arr, i, arr.length);
        i -= 1;
      }
    },

    heapify(heap, i, max) {
      let index;
      let leftChild;
      let rightChild;

      while (i < max) {
        index = i;

        leftChild = 2 * i + 1;

        rightChild = leftChild + 1;

        if (leftChild < max && heap[leftChild] > heap[index]) {
          index = leftChild;
        }

        if (rightChild < max && heap[rightChild] > heap[index]) {
          index = rightChild;
        }

        if (index === i) {
          return;
        }

        this.swap(heap, i, index);

        i = index;
      }
    },

    swap(arr, firstItemIndex, lastItemIndex) {
      const temp = arr[firstItemIndex];

      arr[firstItemIndex] = arr[lastItemIndex];
      arr[lastItemIndex] = temp;
    },

    heapSort(arr) {
      setTimeout(() => {
        this.buildMaxHeap(arr);

        let lastElement = arr.length - 1;

        while (lastElement > 0) {
          this.swap(arr, 0, lastElement);
          this.heapify(arr, 0, lastElement);
          lastElement -= 1;
        }
      }, 200);
      this.data.arrNum = arr;
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
