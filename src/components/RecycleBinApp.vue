<template>
    <div id="recyclebin" class="page-shadow">
      <section class="tittle"><img src="../assets/recycle-bin.png" alt="une poubelle"> Recycle Bin</section>
      <div class="close box-shadow" v-on:click="close('recyclebin')">X</div>
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
          <img src="../assets/wordpress.png" alt="">
          <p>Wordpress</p>
        </article>
        <article id="windows11">
          <img src="../assets/windows-11.png" alt="">
          <p>Windows 11</p>
        </article>
      </div>
    </div>
</template>

<script>


export default {
  name: 'RecycleBinApp',
}
</script>

<style scoped>
#recyclebin{
  position: absolute;
  top: 10%;
  left: 10%;
  width: 300px;
  height: 289px;
  background: #c0c0c0;
}
</style>
