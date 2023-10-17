<template>
  <div class="icone" :id="iconId">
    <img src="../assets/my-document.png" :alt="altMiniature">
    <p>{{ msg }}</p>

  </div>
</template>

<script>


export default {
  name: 'MyDocument',
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
    margin-bottom: -8px;
  }
  p{
    max-width: 80px;
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
  #icone-4{
    top: 169px;
    left: 5px;
  }
</style>
