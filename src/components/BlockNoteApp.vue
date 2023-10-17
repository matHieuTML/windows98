<template>
    <div id="blocknote" class="page-shadow">
      <section class="tittle"><img src="../assets/blocknote.png" alt="un blocknote"> Block Note</section>
      <div class="close box-shadow" v-on:click="close('blocknote')">X</div>
      <article class="subtittle">
        <div></div>
        <p>File</p>
        <p>Edit</p>
        <p>Format</p>
        <p>View</p>
        <p>Help</p>
      </article>
        <textarea name="text" id="" cols="108" rows="32"></textarea>
    </div>
</template>

<script>

export default {
  name: 'BlockNoteApp',

  
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
#blocknote{
  position: absolute;
  top: 10%;
  left: 10%;
  width: 900px;
  height: 576px;
  background: #c0c0c0;
}
</style>
