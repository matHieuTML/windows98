<template>
  <div class="icone" :id="iconId">
    <img src="../assets/blocknote.png" :alt="altMiniature">
    <p>{{ msg }}</p>

  </div>
</template>

<script>

export default {
  name: 'BlockNote',
  props: {
    msg: String,
    iconId: String,
    altMiniature: String,
    source: String,
  }
  
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  .icone:hover{
    cursor: pointer;
  }
  img{
    width: 48px;
    margin-bottom: -10px;
  }
  p{
    max-width: 65px;
  }
  .icone{
    position: absolute;
  }
  #icone-1{
    top: 5px;
    left: 5px;
  }
  #icone-2{
    top:5px;
    left: 100px;
  }
</style>
