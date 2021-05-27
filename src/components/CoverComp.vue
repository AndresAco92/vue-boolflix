<template>
  <div class="container">
    <p>{{Covers.title}}</p>
    <p>{{Covers.original_title}}</p>
    <p>Lang: {{Covers.original_language}}</p>
    <p>{{Covers.vote_average}}</p>

  </div>
</template>

<script>
export default {
  name: 'CoverComp',
  props:{
    Covers: Object
  }
}
</script>

<style lang='scss'>

  .container{
    width: 200px;
    height: 300px;
    text-align: center;
    background-color: black;
    color: #fff;
    padding: 10px;
    border: 1px solid red;
  }

</style>