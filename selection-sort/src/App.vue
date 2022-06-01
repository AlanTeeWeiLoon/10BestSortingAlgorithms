<template>
<div>
  <SelectionSort msg="Selection Sort"/>
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
    <button @click="selectionSort(data.arrNum)">
        Click for Selection Sort
      </button>
  </div>
    
</template>

<script>
import SelectionSort from './components/SelectionSort.vue'

export default {
  name: 'App',
  components: {
    SelectionSort
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

    selectionSort(array){
      let n = array.length;
        
    for(let i = 0; i < n; i++) {
        // Finding the smallest number in the subarray
        let min = i;
        for(let j = i+1; j < n; j++){
            if(array[j] < array[min]) {
                min=j; 
            }
         }
         if (min != i) {
             // Swapping the elements
             let tmp = array[i]; 
             array[i] = array[min];
             array[min] = tmp;      
        }
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
