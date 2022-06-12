<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    
    <p>
      Radix sort is an integer sorting algorithm that sorts data with integer keys by grouping the keys by individual digits that share the same significant position and value (place value). 
    </p>
    <p>
      Radix sort uses counting sort as a subroutine to sort an array of numbers.
    </p>
    
    
  </div>
</template>

<script>
export default {
  name: 'RadixSort',
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
