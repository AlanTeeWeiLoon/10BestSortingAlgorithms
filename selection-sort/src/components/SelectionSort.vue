<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    
    <p>
      Selection Sort is one of the simpler and more intuitive sorting algorithms. It is an in-place, unstable, comparison algorithm.
    </p>
    <p>
      Selection sort is a sorting algorithm in which the given array is divided into two subarrays, the sorted left section, and the unsorted right section.
    </p>
    
    
  </div>
</template>

<script>
export default {
  name: 'SelectionSort',
  props: {
    msg: String
  },
  

  
}


</script>

<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
