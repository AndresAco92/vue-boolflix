<template>
  
  <header>
    <div class="left">
      <h1>ciao</h1>
    </div>
    <div class="right">
      <input
              placeholder="Scrivimi!"
              type="text"
              v-model="search_txt"
      >
      <button
              @click="$emit('searching',{text:search_txt, type:'movie'})"
      >FILMS
      </button>
      <button
              @click="$emit('searching',{text:search_txt, type:'tv'})"
      >TV
      </button>
      <button
              @click="$emit('searching',{text:search_txt, type:'all'})"
      >EVERY
      </button>
    </div>
  </header>

</template>

<script>
export default {
  name:'HeaderComp',
  data(){
    return{
      search_txt:''
    }
  }
}
</script>

<style lang='scss' scoped>

  header{
    height: 70px;
    background-color: #000;
    display: flex;
    justify-content: space-between;
    border-bottom: 2px solid red;
    .left,
    .right{
      height: 100%;
      display: flex;
      align-items: center;
    }
    .left{
      padding-left: 20px;
      color: #fff;
      &:hover{
        cursor: pointer;
        transform: scale(1.1);
      }
    }
    .right{
      padding-right: 20px;
      input:hover,
      button:hover{
        cursor: pointer;
        transform: scale(1.1);
      }
      input{
        margin-right: 20px;
        border-radius: 5px;
        color: red;
        padding: 2px;
      }
      button{
        padding: 1px 3px;
      }
    }
  }

</style>