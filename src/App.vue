<template>
  <div id="screen">

    <InternetExplorer msg="Internet Explorer" v-on:dblclick="afficher('internetexplorer')" icon-id="icone-1" />
    <BlockNote msg="block note" v-on:dblclick="afficher('blocknote')" icon-id="icone-2"/>
    <DemiNeur msg="demineur" v-on:dblclick="afficher('demineur')" icon-id="icone-3" />
    <MyDocument msg="My Document" v-on:dblclick="afficher('mydocument')" icon-id="icone-4" />
    <RecycleBin msg="Recycle Bin" v-on:dblclick="afficher('recyclebin')" icon-id="icone-5" />

    <BlockNoteApp v-if="appblocknote == true"/>
    <InternetExplorerApp v-if="appinternetexplorer == true"/>
    <DemiNeurApp v-if="appdemineur == true"/>
    <MyDocumentApp v-if="appmydocument == true"/>
    <RecycleBinApp v-if="apprecyclebin == true"/>

    <div id="menustart" v-if="menustart == true ">
      <section id="titre">
        <h2>Windows 98</h2>
      </section>
      <section id="menustart-app">
        <article v-on:click="afficherMenu('blocknote')">
          <img class="racourci-app-toolbar"  src="./assets/blocknote.png" alt="">
          Block note
        </article>
        <article v-on:click="afficherMenu('internetexplorer')">
          <img class="racourci-app-toolbar"  src="./assets/internetexplorer.png" alt="">
          Internet Explorer
        </article>
        <hr>
        <article v-on:click="afficherMenu('demineur')">
          <img class="racourci-app-toolbar"  src="./assets/demineur.png" alt="">
          Minesweeper
        </article>
        <article >
          <img src="./assets/valorant.png" alt="">
          <p>Valorant</p>
        </article>
        <hr>
        <article>
          <img src="./assets/vs-code.png" alt="">
          <p>vs code</p>
        </article>
        <article>
          <img src="./assets/discord.png" alt="">
          <p>discord</p>
        </article>
      </section>
    </div>
    <div id="toolbar">
      <div id="menu" class="box-shadow" v-on:click="start()">
        <img alt="Vue logo" src="./assets/download.png">
      </div>
      <span id="span1-toolbar"></span>
      <img class="racourci-app-toolbar" v-on:click="afficher('blocknote')" src="./assets/blocknote.png" alt="">
      <img class="racourci-app-toolbar" v-on:click="afficher('internetexplorer')" src="./assets/internetexplorer.png" alt="">
      <img class="racourci-app-toolbar" v-on:click="afficher('demineur')" src="./assets/demineur.png" alt="">
      <span></span>
      <div v-if="appblocknote == true" class="box-shadow onglet">
        <img src="./assets/blocknote.png" alt="un blocknote">
        <h3>Block Note</h3>
      </div>
      <div v-if="appinternetexplorer == true" class="box-shadow onglet">
        <img src="./assets/internetexplorer.png" alt="internet">
        <h3>Internet Explorer</h3>
      </div>
      <div v-if="appdemineur == true" class="box-shadow onglet">
        <img src="./assets/demineur.png" alt="internet">
        <h3>demineur</h3>
      </div>
      <div v-if="appmydocument == true" class="box-shadow onglet">
        <img src="./assets/my-document.png" alt="internet">
        <h3>My Document</h3>
      </div>
      <div v-if="apprecyclebin == true" class="box-shadow onglet">
        <img src="./assets/recycle-bin.png" alt="internet">
        <h3>Recycle Bin</h3>
      </div>
    </div>
  </div>
</template>

<script>
import BlockNote from './components/BlockNote.vue';
import BlockNoteApp from './components/BlockNoteApp.vue';

import InternetExplorer from './components/InternetExplorer.vue';
import InternetExplorerApp from './components/InternetExplorerApp.vue';

import DemiNeur from './components/DemiNeur.vue';
import DemiNeurApp from './components/DemiNeurApp.vue';

import MyDocument from './components/MyDocument.vue';
import MyDocumentApp from './components/MyDocumentApp.vue';

import RecycleBin from './components/RecycleBin.vue';
import RecycleBinApp from './components/RecycleBinApp.vue';
let application = null;


export default {
  name: 'App',
  components: {
    BlockNote, BlockNoteApp, InternetExplorer, InternetExplorerApp, DemiNeur, DemiNeurApp, MyDocument, MyDocumentApp, RecycleBin, RecycleBinApp
}, 
  data() {
    return {
      application: application,
      appblocknote: false,
      appdemineur: false,
      appinternetexplorer: false,
      appmydocument: false,
      apprecyclebin: false,
      menustart: false,
    }
  },
  methods: {
    afficher(app) {
     this['app' + app] = true;
    },
    close(app){
      this['app' + app] = false;
    },
    start(){
        if(this.menustart == false){
          this.menustart = true;
        }else{
          this.menustart = false;
        }
    },
    afficherMenu(app){
      this['app' + app] = true;
      if(this.menustart == false){
          this.menustart = true;
        }else{
          this.menustart = false;
        }
    }

  }
}
</script>

<style>
input[type="text"]:focus, input[type="password"]:focus, textarea:focus{
	outline: none;
}
.disabled{
  pointer-events: none;
}

#blackbackground{
  width: 40px;
  height: 35px;
  background: black;
  margin-left: 410px;
}
#app {
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: white;
  margin-top: 60px;
  display: flex;
  justify-content: center;
  align-items: center;
  font-family: Arial,sans-serif;
  font-size: 12px;
  font-weight: 100;
  letter-spacing: .025em;
  -webkit-font-smoothing: none;
}
body{
  background: black;
}
#screen{
  position: relative;
  background: #008080;
  width:1100px;
  height: 700px;
}
#toolbar{
  position: absolute;
 width: 1099px;
 height: 35px;
 background: #c0c0c0;
 bottom: 0;
 box-shadow: 0 -2px #fffdfc, 0 -4px #cce9eb;
 display: flex;
 justify-content:flex-start ;
 align-items: center;
}
#toolbar span{
  width: 2px;
  height: 20px;
  background: #f2f2f2;
  box-shadow: 1px 1px 0 #818181;
  margin-left: 5px;
}
#toolbar #span1-toolbar{
  margin-left: 10px;
  margin-right: 5px;
}
#toolbar .racourci-app-toolbar{
  width: 18px;
  height: 18px;
  margin-right: 5px;
  margin-left: 5px;
}
#toolbar .racourci-app-toolbar:hover{
  cursor: pointer;
}
#menu{
  margin-left:10px;
  padding-right:3px;
}
#menu img{
  max-width: 50px;
}
.box-shadow{
  box-shadow: -2px -2px #e0dede, -2px 0 #e0dede, 0 -2px #e0dede, -4px -4px white, -4px 0 white, 0 -4px white, 2px 2px #818181, 0 2px #818181, 2px 0 #818181, 2px -2px #e0dede, -2px 2px #818181, -4px 2px white, -4px 4px black, 4px 4px black, 4px 0 black, 0 4px black, 2px -4px white, 4px -4px black;
  cursor: pointer;
}

.box-shadow:active{
  box-shadow: -2px -2px #818181, -2px 0 #818181, 0 -2px #818181, -4px -4px black, -4px 0 black, 0 -4px black, 2px 2px #e0dede, 0 2px #e0dede, 2px 0 #e0dede, 2px -2px #818181, -2px 2px #e0dede, -4px 2px black, -4px 4px white, 4px 4px white, 4px 0 white, 0 4px white, 2px -4px black, 4px -4px white;

}
.onglet{
  margin-left: 13px;
  padding-left: 4px;
  height: 20px;
  min-width: 120px;
  display: flex;
  align-items: center;
  color: black;
}
.onglet img{
  width: 18px;
  height: 18px;
}
.page-shadow{
  box-shadow: -2px -2px #e0dede, -2px 0 #e0dede, 0 -2px #e0dede, -4px -4px white, -4px 0 white, 0 -4px white, 2px 2px #818181, 0 2px #818181, 2px 0 #818181, 2px -2px #e0dede, -2px 2px #818181, -4px 2px white, -4px 4px black, 4px 4px black, 4px 0 black, 5px 4px black, 2px -4px white, 4px -4px black;
}
.tittle{
  background :linear-gradient(90deg, #000184, #0f80cd);
  width: 99%;
  padding-left: 1%;
  padding-bottom: 7px;
  padding-top: 7px;
  font-size: 15px;
  text-align: left;
}
.tittle img {
  width: 15px;
  height: 15px;
  margin-right: 5px;
}
.subtittle{
  display: flex;
  align-items: center;
  margin-left: 5px;
}

#windows11{
  margin-top: 16px;
  margin-left: -5px;
}

.reaction{
  width:20px !important ;
  height: 20px;
}
.subtittle div{
  width: 2px;
  height: 20px;
  background: #f2f2f2;
  box-shadow: 1px 1px 0 #818181;
  margin-right: 5px;
  margin-left: 5px;
  
}
.subtittle p{
  margin-right:5px;
  margin-left: 5px;
  cursor: pointer;
  color: grey;
}
.subtittle p:hover{
color : black;
}
.close{
  background: #c0c0c0;
  min-width: 19px;
  max-width: 20px;
  height: 15px;
  position: absolute;
  right: 5px;
  top: 8px;
  color: black;
  font-weight:400 ;
}
#menustart{
  width:280px;
  height: 400px;
  background: #c0c0c0;
  position: absolute;
  top: 37.3%;
  left: 0%;
  display: flex;

}
#titre{
  background :linear-gradient(90deg, #000184, #0f80cd);
  height: 100%;
  width: 20%;
  display: flex;
  align-items: flex-end;
  justify-content: center;
}
#titre h2 {
  rotate: -90deg;
  white-space: nowrap;
  font-size: 30px;
  margin-bottom: 80px !important;
}
#menustart-app{
  width: 80%;
  height: 100%;
}
#menustart-app article{
display: flex;
align-items: center;
justify-content: flex-start;
}
#menustart-app article:hover{
  background: #000184;
  cursor: pointer;
}
#menustart-app article img{
  width: 30px;
  margin: 10px;
}
.content{
  margin-left: 2%;
  width: 96%;
  height: 74%;
  background: lightgrey;
  display: flex;
  justify-content: flex-start;
  align-items: flex-start;
}
.content article{
  margin: 20px;
  color: black;
  cursor: pointer;
}
.content article img{
  width: 40px;
  margin-bottom: -12px;
}
</style>
