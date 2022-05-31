<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    
    <p>
      Bubble Sort is the simplest sorting algorithm that works by repeatedly swapping the adjacent elements if they are in the wrong order. 
    </p>
    <p>
      This algorithm is not suitable for large data sets as its average and worst case time complexity is quite high.
    </p>
    
    
  </div>
</template>

<script>
export default {
  name: 'BubbleSort',
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
