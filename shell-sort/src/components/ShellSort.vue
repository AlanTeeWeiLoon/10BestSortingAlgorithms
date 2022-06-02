<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    
    <p>
      Shell sort is an optimized version of Insertion sort.
    </p>
    <p>
      It differs from insertion sort in that it prioritizes elements that are farther apart. Shell sorting is also called shrinking incremental sorting.
    </p>
    
    
  </div>
</template>

<script>
export default {
  name: 'ShellSort',
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
