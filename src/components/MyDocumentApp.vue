<template>
    <div id="mydocument"  class="page-shadow">
      <section class="tittle"><img src="../assets/my-document.png" alt="un my-document"> My Document</section>
      <div class="close box-shadow" v-on:click="close('mydocument')">X</div>
      <article class="subtittle">
        <div></div>
        <p>File</p>
        <p>Edit</p>
        <p>Format</p>
        <p>View</p>
        <p>Help</p>
      </article>
      <div class="content">
        <article >
          <img src="../assets/valorant.png" alt="">
          <p>Valorant</p>
        </article>
        <article>
          <img src="../assets/vs-code.png" alt="">
          <p>vs code</p>
        </article>
        <article>
          <img src="../assets/discord.png" alt="">
          <p>discord</p>
        </article>
      </div>
    </div>
</template>

<script>


export default {
  name: 'MyDocumentApp',
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
#mydocument{
  position: absolute;
  top: 40%;
  left: 5%;
  width: 400px;
  height: 300px;
  background: #c0c0c0;
}

</style>
