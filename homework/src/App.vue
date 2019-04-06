<template>
  <div id="app">
    <header-top/>
    <div class="button">
      <p class="operating">操作区域</p>
      <div class="buttonRect" v-bind:class="{showButton:isbool}" @click="ClickEvent()">
        <div class="buttonCircle" v-bind:class="{active:!isbool}"></div>
      </div>
    </div>
    <div v-bind:class="{showdisplay:isbool}" class="showAll">
      <div class="Current_price">
        <p class="operating">当前价格</p>
        <input type="text" v-model="value" v-on:focus="focus()">
      </div>

      <Progress-bar v-bind:value="value"/>
    </div>
    <div class="showImg">
      <img src="./assets/logo.png" alt="">
    </div>
  </div>
</template>
<script>
  import show from './components/index'
  import showHeader from './components/header'

  export default {
    name: 'App',
    components: {
      'Progress-bar': show,
       'header-top':showHeader
    },
    data() {
      return {
        isbool: false,
        value: 400,
      }
    },
    methods: {
      ClickEvent() {
        this.isbool=!this.isbool
      },
      focus(){
        this.value=0
      }
    },
  }
</script>

<style>
  * {
    margin: 0;
    padding: 0;
  }

  #app {
    width: 692px;
    margin: 0 auto;
  }

  header {
    width: 100%;
    display: flex;
    flex-wrap: wrap;
    justify-content: space-between;
  }

  #Gradient_one {
    width: 100%;
    height: 19px;
    background: linear-gradient(90deg, #FAD961, #F76B1C);
  }

  .Original_price, .Reserve_price {
    width: 62.5px;
    height: 40px;
    margin-top: 15px;
    display: flex;
    flex-direction: column;
    text-align: center;
  }

  p {
    font-family: PingFangSC-Regular;
    font-size: 14px;
    color: #888888;
  }

  .button {
    height: 32px;
    margin-top: 52px;
    display: flex;
  }

  .operating {
    width: 68px;
    color: #000000;
    font-size: 16px;
    text-align: center;
    align-self: center;
    margin-right: 32px;
  }

  .buttonRect {
    width: 62px;
    height: 100%;
    background: #4A90E2;
    justify-content: flex-end;
    border-radius: 20px;
    display: flex;

  }

  .showButton {
    justify-content: flex-start;
    background-color: #B4B7BB;
  }

  .buttonCircle {
    width: 30px;
    height: 30px;
    background-color: #FFFFFF;
    border-radius: 32px;
    border: 1px solid #B4B7BB;
  }

  .active {
    border: 1px solid #4A90E2;
  }

  .showAll {
    margin-top: 120px;
    display: block;
  }

  .showdisplay {
    display: none;
  }

  .Current_price {
    height: 36px;
    display: flex;
  }

  input {
    background: #FFFFFF;
    border: 1px solid #979797;
    width: 156px;
    padding-left: 15px;
  }

  main {
    width: 100%;
    display: flex;
    flex-wrap: wrap;
    margin-top: 192px;
    justify-content: space-between;
  }

  .Display_bar {
    width: 100%;
    height: 20px;
    background: #D8D8D8;
    border: 1px solid #979797;
  }

  .progress_bar {
    height: 100%;
    border-radius: 0 10px 10px 0;
    background: linear-gradient(90deg, #FAD961, #F76B1C);
  }

  .down_bar {
    background: #F5A623;
    width: 3px;
    height: 15px;
  }

  .down_bar:nth-child(2) {
    position: absolute;
    left: 50%;
  }

  .showImg {
    width: 100%;
    margin-top: 227px;
    display: flex;
    justify-content: center;
  }

  img {
    align-self: center;
  }

  @media screen and (min-width: 992px) {
    img {
      width: 200px;
    }
  }

  @media screen and (min-width: 1200px) {
    img {
      width: 300px;
    }
  }

  @media screen and (min-width: 1600px) {
    img {
      width: 500px;
    }
  }
</style>
