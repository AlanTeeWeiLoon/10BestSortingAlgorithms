<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    
    <p>
      Bucket sort is a comparison sort algorithm that operates on elements by dividing them into different buckets and then sorting these buckets individually. 
    </p>
    <p>
      Each bucket is sorted individually using a separate sorting algorithm like insertion sort, or by applying the bucket sort algorithm recursively.
    </p>
    <p>
      Bucket sort is mainly useful when the input is uniformly distributed over a range.
    </p>
    
    
  </div>
</template>

<script>
export default {
  name: 'BucketSort',
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
