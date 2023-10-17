<template>
    <div id="internet" class="page-shadow">
      <section class="tittle"><img src="../assets/internetexplorer.png" alt="internet c'est fun"> Internet Explorer</section>
      <div class="close box-shadow" v-on:click="close('internetexplorer')">X</div>
      <article class="subtittle">
        <div></div>
        <p>File</p>
        <p>Edit</p>
        <p>Format</p>
        <p>View</p>
        <p>Help</p>
        <span id="blackbackground">
          <img src="../assets/windows-0.png" alt="logo">
        </span>
      </article>
      <hr>
      <article class="opt-internet" >
        <div class="opt-barre" id="op-barre-tool"></div>
        <span>
          <img src="../assets/internet-arrow-left.png" alt="back">
          <p>Back</p>
        </span>
        <span>
          <img src="../assets/internet-arrow-right.png" alt="forward">
          <p>Forward</p>
        </span>
        <span>
          <img src="../assets/internet-stop.png" alt="stop">
          <p>Stop</p>
        </span>
        <span>
          <img src="../assets/refresh.png" alt="">
          <p>Refresh</p>
        </span>
        <span>
          <img src="../assets/home.png" alt="">
          <p>Home</p>
        </span>
        <span>
          <img src="../assets/search.png" alt="">
          <p>Search</p>
        </span>
        <span>
          <img src="../assets/favoris.png" alt="">
          <p>Favorites</p>
        </span>
        <span>
          <img src="../assets/history-1.png" alt="">
          <p>History</p>
        </span>
      </article>
      <hr>
      <article class="subtittle">
        <div></div>
        <p>adress</p>
        <span id="search-bar">
          <img src="../assets/internetexplorer.png" alt="">
          <p>https://www.google.com/</p>
          <div>▼</div>
        </span>
        <span id="go">Go</span>
      </article>
      <hr>
      <div id="google-page">
        <img src="../assets/google-logo.png" alt="">
        <div id="google-search-div">
          <p>search the web with Google!</p>
          <input type="text" id="search">
          <div>
            <button v-on:click="searchGoogle()">Google search</button>
            <button>I'm feeling lucky</button>
          </div>
        </div>
      </div>
    </div>
</template>

<script>


export default {
  name: 'InternetExplorerApp',
  methods: {
      searchGoogle(){
      let search = document.getElementById('search').value;
      window.open('https://www.google.com/search?q='+search);
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  #internet{
  position: absolute;
  top: 5%;
  left: 30%;
  width: 650px;
  height: 600px;
  background: #c0c0c0;
}
.opt-barre{
  margin-right: 25px;
  margin-left: 12px;
  margin-top: -5px;
  width: 2px;
  height: 20px;
  background: #f2f2f2;
  box-shadow: 1px 1px 0 #818181;
}

.opt-internet{
  display: flex;
  justify-content: flex-start;
  align-items: center;
  color: grey;
  height: 40px;
}
.opt-internet span{
  cursor: pointer;
  margin-right: 35px ;
}
.opt-internet span img{
  width: 20px;
  height: 20px;
  margin-bottom: -14px;
  filter: grayscale(100%);
}
.opt-internet span:hover{
  color: black;
}
#search-bar{
  box-shadow: -2px -2px #818181, -2px 0 #818181, 0 -2px #818181, -4px -4px black, -4px 0 black, 0 -4px black, 2px 2px #e0dede, 0 2px #e0dede, 2px 0 #e0dede, 2px -2px #818181, -2px 2px #e0dede, -4px 2px black, -4px 4px white, 4px 4px white, 4px 0 white, 0 4px white, 2px -4px black, 4px -4px white;
  background: white;
  display: flex;
    align-items: center;
  height: 22px;
  width: 290px;
  margin-left: 4px;
  color: black;
  margin-bottom: 6px !important;
}
#search-bar img{
  margin-left: 4px;
  width: 15px;
  height: 15px;
}
#search-bar div{
  box-shadow: -2px -2px #818181, -2px 0 #818181, 0 -2px #818181, -4px -4px black, -4px 0 black, 0 -4px black, 2px 2px #e0dede, 0 2px #e0dede, 2px 0 #e0dede, 2px -2px #818181, -2px 2px #e0dede, -4px 2px black, -4px 4px white, 4px 4px white, 4px 0 white, 0 4px white, 2px -4px black, 4px -4px white;
  background: white;
  background: #818181;
  width: 13px;
  height: 12px;
  position: absolute;
  left: 338px;
  top: 135px;
  display: flex;
  justify-content: center;
  align-items: center;
}
#go{
  color: #6f6f6f;
  margin-left:16px ;

}
#google-page{
  box-shadow: -2px -2px #818181, -2px 0 #818181, 0 -2px #818181, -4px -4px black, -4px 0 black, 0 -4px black, 2px 2px #e0dede, 0 2px #e0dede, 2px 0 #e0dede, 2px -2px #818181, -2px 2px #e0dede, -4px 2px black, -4px 4px white, 4px 4px white, 4px 0 white, 0 4px white, 2px -4px black, 4px -4px white;
  background: white;
  margin-left: 4px;
  width: 639px;
  height:414px;
  display: flex;
  justify-content: flex-start;
  align-items: center;
  flex-direction: column;
}

#google-page img{
  width: 70%;
  height: 35%;
}
#google-search-div{
  color: black;
  font-size: 13px;
  font-weight: 600;
  background: #dfdede;
  display: flex;
  flex-direction: column;
  justify-content: space-around;
  align-items: center;
  width: 100%;
  margin-top: 10px;
  padding-top: 6px;
  padding-bottom: 10px;
}
#google-search-div input{
  width: 270px;
  height: 15px;
}
#google-search-div div{
  margin-top:9px ;
}
#internet hr{
  width: 649px;
  height: 0.4px;
  background: #b7b7b7;
  box-shadow: 1px 0 #6f6f6f;
  margin-top: -2px !important ;
}
</style>
