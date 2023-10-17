<template>
  <div class="icone" :id="iconId">
    <img src="../assets/demineur.png" :alt="altMiniature">
    <p>{{ msg }}</p>

  </div>
</template>

<script>


export default {
  name: 'DemiNeur',
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
    margin-bottom: -14px;
  }
  p{
    max-width: 65px;
  }
  .icone{
    position: absolute;
  }
  #icone-3{
    top: 95px;
    left: 15px;
  }
</style>
