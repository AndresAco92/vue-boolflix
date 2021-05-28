<template>
  <div class="container">
    <p>{{card.title}}</p>
    <p>{{card.original_title || card.original_name}}</p>
    <p>Lang: {{card.original_language}}</p>
    <p>{{card.vote_average}}</p>
  </div>
</template>

<script>
export default {
  name: 'CoverComp',
  props:{
    card:Object
  },
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