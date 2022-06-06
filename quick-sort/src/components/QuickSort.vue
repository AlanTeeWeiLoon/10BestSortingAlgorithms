<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    
    <p>
      Quicksort is a popular sorting algorithm that is often faster in practice compared to other sorting algorithms. 
    </p>
    <p>
      It utilizes a divide-and-conquer strategy to quickly sort data items by dividing a large array into two smaller arrays. 
    </p>
    
    
  </div>
</template>

<script>
export default {
  name: 'QuickSort',
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
