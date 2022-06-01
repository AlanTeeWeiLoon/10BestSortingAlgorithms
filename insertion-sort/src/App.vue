<template>
<div>
  <InsertionSort msg="Insertion Sort"/>
  <div>
      <button @click="randomNum">
        Click to random generate 10 numbers
      </button>
    </div>
    <div>
    <table class="center">
      <tr>
        <td v-for="(num) in data.arrNum" v-bind:key="num" style="width:2em;font-size: x-large;font-weight: bold;">{{num}}</td>
      </tr>
    </table>
    </div>
    <button @click="insertionSort(data.arrNum)">
        Click for Insertion Sort
      </button>
  </div>
    
</template>

<script>
import InsertionSort from './components/InsertionSort.vue'

export default {
  name: 'App',
  components: {
    InsertionSort
  },
  data(){
		return {
			data: {
        arrNum: [1,2,3,4,5,6,7,8,9,10]
      }
    }
  },
  methods: {
    randomNum(){
      var arr = [];
      while(arr.length < 10){
          var r = Math.floor(Math.random() * 100) + 1;
          if(arr.indexOf(r) === -1) arr.push(r);
      }
      this.data.arrNum=arr;
    },

    insertionSort(array){
      for (let i = 1; i < array.length; i++) {
    let currentValue = array[i]
    let j
    for (j = i - 1; j >= 0 && array[j] > currentValue; j--) {
      array[j + 1] = array[j]
    }
    array[j + 1] = currentValue
  }
      this.data.arrNum = array
    }
  },
}
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
  margin-top:1em;
  margin-bottom:1em;
}
</style>
