<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    
    <p>
      Insertion sort is a simple sorting algorithm that builds the final sorted array (or list) one item at a time. 
    </p>
    <p>
      It is much less efficient on large lists than more advanced algorithms such as quicksort, heapsort, or merge sort.
    </p>
    
    
  </div>
</template>

<script>
export default {
  name: 'InsertionSort',
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
