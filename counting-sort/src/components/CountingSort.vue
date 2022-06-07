<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    
    <p>
      Counting sort is a sorting technique based on keys between a specific range. 
    </p>
    <p>
      It works by counting the number of objects having distinct key values (kind of hashing). Then do some arithmetic to calculate the position of each object in the output sequence. 
    </p>
    
    
  </div>
</template>

<script>
export default {
  name: 'CountingSort',
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
