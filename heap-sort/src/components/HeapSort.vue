<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <p>
      Heap sort is a comparison-based sorting technique based on Binary Heap data structure. 
    </p>
    <p>
      It is similar to selection sort where we first find the minimum element and place the minimum element at the beginning. 
    </p> 
  </div>
</template>

<script>
export default {
  name: 'HeapSort',
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
