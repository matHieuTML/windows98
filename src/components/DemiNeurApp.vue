<template>
    <div id="demineur" class="page-shadow">
      <section class="tittle"><img src="../assets/demineur.png" alt="le jeu du démineur"> Minesweeper</section>
      <div class="close box-shadow" v-on:click="close('demineur')">X</div>
      <article class="subtittle">
        <div></div>
        <p>Game</p>
        <p>Help</p>
      </article>
      <div id="score">
        <img src="../assets/minesweeper-screen.png" alt="">
        <div>
          <img class="reaction" src="../assets/emoji-happy.png" alt="" v-if="gameOver == false">
          <img class="reaction" src="../assets/emoji-sad.png" alt="" v-if="gameOver == true">
        </div>
        <img src="../assets/minesweeper-screen.png" alt="">
      </div>
      <div id="game" :class="{disabled: gameDisabled}">
        <span id="s1" v-on:click="showNum(1)"><p style="color:blue;" v-if="num1 == true">1</p></span>
        <span id="s2" v-on:click="showBomb(1)" :style="{backgroundColor: bgcolor1}"><img src="../assets/demineur.png" alt="" v-if="bomb1 == true"> </span>
        <span id="s3" v-on:click="showNum(2)"> <p style="color:blue;" v-if="num2 == true">1</p></span>
        <span id="s4" v-on:click="changeBackground(1)" :style="{backgroundColor: bg1}"></span>
        <span id="s5" v-on:click="changeBackground(2)" :style="{backgroundColor: bg2}"></span>
        <span id="s6" v-on:click="changeBackground(3)" :style="{backgroundColor: bg3}"></span>
        <span id="s7" v-on:click="changeBackground(4)" :style="{backgroundColor: bg4}"></span>
        <span id="s8" v-on:click="showNum(3)"><p style="color:blue;" v-if="num3 == true">1</p></span>
        <span id="s9" v-on:click="showNum(4)"><p style="color:blue;" v-if="num4 == true">1</p></span>
        <span id="s10" v-on:click="showNum(5)"><p style="color:blue;" v-if="num5 == true">1</p></span>
        <span id="s11" v-on:click="showNum(6)"><p style="color:blue;" v-if="num6 == true">1</p></span>
        <span id="s12" v-on:click="showNum(7)"><p style="color:blue;" v-if="num7 == true">1</p></span>
        <span id="s13" v-on:click="showNum(8)"><p style="color:blue;" v-if="num8 == true">1</p></span>
        <span id="s14" v-on:click="changeBackground(5)" :style="{backgroundColor: bg5}"></span>
        <span id="s15" v-on:click="showNum(19)"><p style="color:blue;" v-if="num19 == true">1</p></span>
        <span id="s16" v-on:click="showNum(18)"><p style="color:blue;" v-if="num18 == true">1</p></span>
        <span id="s17" v-on:click="showNum(17)"><p style="color:blue;" v-if="num17 == true">1</p></span>
        <span id="s18" v-on:click="showNum(9)"><p style="color:blue;" v-if="num9 == true">1</p></span>
        <span id="s19" v-on:click="showBomb(2)" :style="{backgroundColor: bgcolor2}" > <img src="../assets/demineur.png" alt="" v-if="bomb2 == true"></span>
        <span id="s20" v-on:click="showNum(10)"><p style="color:blue;" v-if="num10 == true">1</p></span>
        <span id="s21" v-on:click="changeBackground(6)" :style="{backgroundColor: bg6}"></span>
        <span id="s22" v-on:click="showNum(11)"><p style="color:blue;" v-if="num11 == true">1</p></span>
        <span id="s23" v-on:click="showBomb(3)" :style="{backgroundColor: bgcolor3}"><img src="../assets/demineur.png" alt="" v-if="bomb3 == true"></span>
        <span id="s24" v-on:click="showNum(12)"><p style="color:blue;" v-if="num12 == true">1</p></span>
        <span id="s25" v-on:click="showNum(13)"><p style="color:blue;" v-if="num13 == true">1</p></span>
        <span id="s26" v-on:click="showNum(14)"><p style="color:blue;" v-if="num14 == true">1</p></span>
        <span id="s27" v-on:click="showNum(15)"><p style="color:blue;" v-if="num15 == true">1</p></span>
        <span id="s28" v-on:click="changeBackground(7)" :style="{backgroundColor: bg7}"></span>
        <span id="s29" v-on:click="showNum(20)"><p style="color:blue;" v-if="num20 == true">1</p></span>
        <span id="s30" v-on:click="showNum(21)"><p style="color:orangered;" v-if="num21 == true">2</p></span>
        <span id="s31" v-on:click="showNum(22)"><p style="color:orangered;" v-if="num22 == true">2</p></span>
        <span id="s32" v-on:click="showNum(23)"><p style="color:blue;" v-if="num23 == true">1</p></span>
        <span id="s33" v-on:click="showNum(24)"><p style="color:blue;" v-if="num24 == true">1</p></span>
        <span id="s34" v-on:click="showNum(25)"><p style="color:blue;" v-if="num25 == true">1</p></span>
        <span id="s35" v-on:click="showNum(26)"><p style="color:blue;" v-if="num26 == true">1</p></span>
        <span id="s36" v-on:click="changeBackground(8)" :style="{backgroundColor: bg8}"></span>
        <span id="s37" v-on:click="showNum(27)"><p style="color:blue;" v-if="num27 == true">1</p></span>
        <span id="s38" v-on:click="showBomb(4)" :style="{backgroundColor: bgcolor4}"><img src="../assets/demineur.png" alt="" v-if="bomb4 == true"></span>
        <span id="s39" v-on:click="showNum(28)"><p style="color:blue;" v-if="num28 == true">1</p></span>
        <span id="s40" v-on:click="showNum(29)"><p style="color:blue;" v-if="num29 == true">1</p></span>
        <span id="s41" v-on:click="showBomb(5)" :style="{backgroundColor: bgcolor5}"><img src="../assets/demineur.png" alt="" v-if="bomb5 == true"></span>
        <span id="s42" v-on:click="showNum(30)"><p style="color:blue;" v-if="num30 == true">1</p></span>
        <span id="s43" v-on:click="changeBackground(9)" :style="{backgroundColor: bg9}"></span>
        <span id="s44" v-on:click="showNum(31)"><p style="color:blue;" v-if="num31 == true">1</p></span>
        <span id="s45" v-on:click="showNum(32)"><p style="color:blue;" v-if="num32 == true">1</p></span>
        <span id="s46" v-on:click="showNum(33)"><p style="color:blue;" v-if="num33 == true">1</p></span>
        <span id="s47" v-on:click="showNum(34)"><p style="color:blue;" v-if="num34 == true">1</p></span>
        <span id="s48" v-on:click="showNum(35)"><p style="color:blue;" v-if="num35 == true">1</p></span>
        <span id="s49" v-on:click="showNum(36)"><p style="color:blue;" v-if="num36 == true">1</p></span>
      </div>
    </div>
</template>

<script>


export default {
  name: 'DemiNeurApp',
  data () {
    return {
      gameOver: false,
      gameDisabled: false,
      bomb1: false,
      bgcolor1: 'rgb(152, 152, 152)',
      bomb2: false,
      bgcolor2: 'rgb(152, 152, 152)',
      bomb3: false,
      bgcolor3: 'rgb(152, 152, 152)',
      bomb4: false,
      bgcolor4: 'rgb(152, 152, 152)',
      bomb5: false,
      bgcolor5: 'rgb(152, 152, 152)',
      num1: false,
      num2: false,
      num3: false,
      num4: false,
      num5: false,
      num6: false,
      num7: false,
      num8: false,
      num9: false,
      num10: false,
      num11: false,
      num12: false,
      num13: false,
      num14: false,
      num15: false,
      num16: false,
      num17: false,
      num18: false,
      num19: false,
      num20: false,
      num21: false,
      num22: false,
      num23: false,
      num24: false,
      num25: false,
      num26: false,
      num27: false,
      num28: false,
      num29: false,
      num30: false,
      num31: false,
      num32: false,
      num33: false,
      num34: false,
      num35: false,
      num36: false,
      bg1: 'rgb(152, 152, 152)',
      bg2: 'rgb(152, 152, 152)',
      bg3: 'rgb(152, 152, 152)',
      bg4: 'rgb(152, 152, 152)',
      bg5: 'rgb(152, 152, 152)',
      bg6: 'rgb(152, 152, 152)',
      bg7: 'rgb(152, 152, 152)',
      bg8: 'rgb(152, 152, 152)',
      bg9: 'rgb(152, 152, 152)'
    }
  },
  methods:{
    changeBackground(num){
      if (num >= 1 && num <= 9) {
        this['bg' + num] = 'white';
      }
    },
    showBomb(num){
      this.gameOver = true;
      if(this.gameOver == true){
        this.gameDisabled = true;
      }
      if (num >= 1 && num <= 5) {
        this['bomb' + num] = true;
        this['bgcolor' + num] = 'red';
      }
    },
    showNum(number) {
  if (number >= 1 && number <= 36) {
    this['num' + number] = true;
  }
  }
  
}
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
#demineur{
  position: absolute;
  top: 9%;
  left: 15%;
  width: 300px;
  height: 400px;
  background: #c0c0c0;
}
#score{
  width: 80%;
  margin-top: 15px;
  margin-left: 10%;
  height:52px;
  box-shadow: -2px -2px #818181, -2px 0 #818181, 0 -2px #818181, -4px -4px black, -4px 0 black, 0 -4px black, 2px 2px #e0dede, 0 2px #e0dede, 2px 0 #e0dede,  2px -2px #818181, -2px 2px #e0dede, -4px 2px black, -4px 4px white, 4px 4px white, 4px 0 white, 0 4px white, 2px -4px black, 4px -4px white;
  display: flex;
  justify-content: space-around;
  align-items: center;
}
#score img{
  width: 55px;
}
#score div {
  box-shadow: -2px -2px #818181, -2px 0 #818181, 0 -2px #818181, -4px -4px black, -4px 0 black, 0 -4px black, 2px 2px #e0dede, 0 2px #e0dede, 2px 0 #e0dede,  2px -2px #818181, -2px 2px #e0dede, -4px 2px black, -4px 4px white, 4px 4px white, 4px 0 white, 0 4px white, 2px -4px black, 4px -4px white;
  width: 26px;
  height: 26px;
  display: flex;
  justify-content: center;
  align-items: center;
}
#game{
  box-shadow: -2px -2px #818181, -2px 0 #818181, 0 -2px #818181, -4px -4px black, -4px 0 black, 0 -4px black, 2px 2px #e0dede, 0 2px #e0dede, 2px 0 #e0dede,  2px -2px #818181, -2px 2px #e0dede, -4px 2px black, -4px 4px white, 4px 4px white, 4px 0 white, 0 4px white, 2px -4px black, 4px -4px white;
  width: 57%;
  margin-top: 15px;
  margin-left: 21.5%;
  display: flex;
  flex-wrap:wrap ;
  justify-content: space-around;
  align-items: flex-start;

}
#game span{
  margin: 2px;
  width:20px;
  height: 20px;
  background: rgb(152, 152, 152);
  display: flex;
  justify-content: center;
  align-items: center;
}
#game span:hover{
  cursor: pointer;
}
#game span img{
  width: 16px;
}
</style>
